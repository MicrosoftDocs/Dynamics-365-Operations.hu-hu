---
title: Lezárt ajánlattétel ajánlatkéréshez
description: Ez a témakör leírja, hogyan lehet lepecsételt árajánlatokat beállítani, hogy a szállítói ajánlatokra adott válaszok titkosak maradjak, amíg a beszerzési személyzet fel nem választja őket.
author: GalynaFedorova
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 40f1735d7efa5131b1462963758b6b48eec78fea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890886"
---
# <a name="sealed-bidding-for-rfqs"></a>Lezárt ajánlattétel ajánlatkéréshez

[!include [banner](../includes/banner.md)]

A lezárt pályázatokkal a szállítói ajánlatok válaszai titkosak maradjak, amíg a beszerzési személyzet fel oldja azokat. Az ajánlatkéréshez (RFQ) kapcsolódó minden ajánlatkérés először az ajánlat lejárata után válik elérhetővé. Az ajánlat feloldása előtt ajánlatokhoz csak olyan dedikált felhasználói szerepkörök férhetnek hozzá, akik a szállítót képviselik.

> [!IMPORTANT]
> Az űrlapok módosítása és bővítése, illetve új űrlapok vagy üzleti logika létrehozása esetén előfordulhat, hogy kijátszható a védelem, amit a Microsoft a lezárt ajánlattételhez biztosít. Az ilyen módosítások, bővítmények, új űrlapok vagy üzleti logika használata, illetve az ilyen módosítások, bővítmények, új űrlapok vagy üzleti logika miatt nem használható lezárt ajánlatok kapcsán Ön vállalja a felelősséget.  A Microsoft nem vállal felelősséget az űrlapok módosítása, kiterjesztései, illetve az Ön által létrehozott új űrlapok vagy üzleti logika kapcsán felemerülő veszteségekért, illetve bármely harmadik fél által okozott egyéb veszteségért. A Microsoft nem nyújt technikai és egyéb támogatást az Ön vagy bármely harmadik fél által az Ön nevében végzett módosításokhoz, bővítményekhez, új űrlapokhoz vagy üzleti logikához. Kizárólag Ön felelős minden olyan törvény és szabályozás betartásáért, amely a lezárt ajánlatokra vonatkozik.

## <a name="how-bids-are-kept-secure"></a>Az ajánlatok biztonságának biztosítása

A lezárt pályázatok titkosítása asymmetrikus titkosítást alkalmaz az ajánla titkosítási kulcsához (KEK) és a szimmetrikus titkosítást az aktuális ajánlat titkosításához. A rendszer integrálva van a Microsoft Azure Key Vaulttal, hogy generálja és kezelje a lezárt ajánlatok titkosításához használt titkosítási kulcsokat. Minden egyes ajánlathoz saját titkosítási kulcs tartozik. Ez a titkosítás a Dynamics 365 Supply Chain Management alkalmazást futtató szervezet tulajdonában lévő kulcstartóján van őrizve. A rendszer igény szerint hozzáfér a kulcstartóhoz, valahányszor titkosítás és visszafejtés szükséges.

## <a name="setup-and-configuration"></a>Beállítás és konfigurálás

Ez a szakasz leírja azokat a előfeltételeket, amelyekre szükség van ahhoz, hogy olyan árajánlatkéréseket küldjön ki, amelyekhez lezárt pályázat szükséges.

### <a name="step-1-set-up-user-access-to-sealed-bidding"></a>1. lépés: Lezárt árajánlathoz való felhasználói hozzáférés beállítása

A lezárt ajánlatok használata esetén csak azok a felhasználók tekinthetik, szerkeszthetik és küldhetik el a az ajánlatokat, akik be vannak állítva kapcsolattartóként a szállítóhoz, amíg az ajánlattételi időszak le nem jár. Ezeknek a felhasználóknak rendelkezniük kell a **Szállító külső** szerepkörrel, és kapcsolattartóként kell beállítani őket a szállítói partnerhez. A kapcsolattartónak a szállítói együttműködésre való jogosultsággal is rendelkeznie kell, a [Szállítói együttműködés beállítása és karbantartásának](set-up-maintain-vendor-collaboration.md) rész leírása szerint.

Mivel azok a felhasználók, akik megfelelő engedélyekkel rendelkezik, és szállítói kapcsolattartóként be vannak állítva, hozzáférhetnek a szállító lezárt ajánlataihoz, fontos nyomon követni, hogy ki ezek a felhasználók. A felhasználókat és a biztonsági szerepköröket beállító a rendszergazda felelős a lezárt ajánlatokhoz való hozzáférés korlátozásáért, hogy csak azok a felhasználók számára legyenek elérhetők, akiknek valóban engedélyezett a megtekintésük.

### <a name="step-2-enable-the-sealed-bidding-feature"></a>2. lépés: A lezárt ajánlattétel funkció engedélyezése

Mielőtt elkezdené a funkció beállítását vagy használatát, győződjön meg arról, hogy az elérhető a rendszerben. A rendszergazdák használhatják a **[Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** munkaterület a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Beszerzés és forrás*
- **Funkció neve:** *Lezárt ajánlat árajánlatkéréshez*

### <a name="step-3-set-up-azure-key-vault"></a>3. lépés: Azure Key Vault beállítása

A Supply Chain Management titkosítási kulcsokkal védi az összes lezárt ajánlatot, és a megfelelő időpontig titokban tartja azokat. A szükséges kulcsok generálásához és kezeléséhez a Key Vault képességeit veszi igénybe. Emiatt a rendszer engedélyezéséhez be kell állítania egy kapcsolatot a Supply Chain Management és egy kulcstartó között.

> [!IMPORTANT]
> A lezárt ajánlattételhez használt kulcstartóknak a következő követelményeknek kell megfelelniük:
>
> - Ha fejlesztési és tesztelési célra egy tesztkörnyezetet használ, akkor külön kulcsra van szükség a tesztkörnyezethez és egy másik a termeléshez.
> - Az egyes kulcstartókat egy olyan Azure-előfizetésben kell létrehozni, amely a szervezetéhez (nem pedig a Supply Chain Management alkalmazáshoz használt előfizetéshez) van létrehozva.
> - Minden kulcstartót kizárólag a lezárt ajánlathoz kell használni. A lezárt ajánlat kulcstartóit más célra nem használhatja.

Minden ajánlat megkapja a saját titkos kulcsát. Ez a kulcs van minden alkalommal használva, amikor egy felhasználó megtekinti, frissíti vagy feloldja az ajánlatot.

A Key Vault létrehozza azt a kulcsot, amely beolvassa a titkos kódot amikor a szállító kiválasztja az **Ajánlat** lehetőséget a szállítói együttműködési felületen. A kulcs lejár egy adott idő után, amelyet a beszerzési vezető állít be a Supply Chain Management **Beszerzési és forrásparaméterek** oldalán. A kulcs lejárata után senki sem tudja megtekinteni, szerkeszteni vagy feloldani az ajánlatot. Emiatt fontos úgy beállítani a kulcs lejáratát, hogy legyen elég idő a pályázati folyamat befejezésére.

A következő három lépésben állíthatja be a kapcsolatot a Key Vault felé. Először be kell állítania egy kulcstartót a lezárt ajánlattételhez. Ezután beállítja, hogy a Supply Chain Management kommunikáljon a kulcstartóval. Végül beállíthatja a kulcs lejárati idejét.

### <a name="step-4-set-up-a-key-vault-to-use-with-sealed-bidding"></a>4. lépés Egy kulcstartó beállítása használatra a lezárt ajánlattételhez

A kulcstartó beállításához kövesse az alábbi lépéseket. A lépések sorrendje fontos.

1. Ha még nem beállított olyan Azure-előfizetést, amely elkülönül attól az előfizetéstől, ahol a Supply Chain Management fut állítsa be most.
1. Állítsa be a kulcstartót a különálló Azure-tárolóban. További információkért lásd: [Azure Key Vault tár karbantartása](https://support.microsoft.com/help/4040294/maintaining-azure-key-vault-storage).
1. Állítsa be a Supply Chain Management alkalmazást úgy, hogy a kulcshoz meghatározott ügyfélként működjön. További információkért lásd: [Azure Key Vault ügyél beállítása](https://support.microsoft.com/help/4040305/setting-up-azure-key-vault-client).

### <a name="step-5-configure-key-vault-parameters-in-supply-chain-management"></a>5. lépés: A Supply Chain Management Key Vault paramétereinek konfigurálása

A Supply Chain Management konfigurálához, hogy kommunikáljon a kulcstartóval a lezárt ajánlati folyamat során hajtsa végre ezeket a lépéseket.

1. Jelentkezzen be a Supply Chain Management szolgáltatásba, és lépjen a **Rendszerfelügyelet \> Beállítások \> Key Vault-paraméterek** menübe.
1. Rekord létrehozásához válassza az **Új** lehetőséget, és állítsa be a következő mezőket:

    - **Név** – írjon be egy nevet.
    - **Leírás** – Adjon meg egy leírást.
    - **Key Vault URL-címe** – Adja meg a kulcstartóhoz tartozó alapértelmezett URL-címet.
    - **Key Vault ügyfél**– Adja meg annak az Active Directory alkalmazásnak az interaktív ügyfélazonosítóját, amely a hitelesítési kulcstartóhoz van rendelve.
    - **Key Vault titkos kulcs** – Adja meg a tanúsítvány titkos hivatkozását.
    - **Lezárt ajánlattételhez engedélyezve** – Ezt a beállítást *Igen* értékre kell beállítani.

![Key Vault paraméterek oldala](media/sealed-bidding-key-vault-param.png "Key Vault paraméterek oldala")

> [!NOTE]
> Egyszerre csak egy kulcstartó-konfigurációt engedélyezhet a lezárt ajánlattételhez. Mielőtt letilt egy létező kulcstartó-konfigurációt, meg kell győződnie arról, hogy az azt használó lezárt ajánlatok fel vannak-e oldva. Vizsgálja meg az összes *Lezárt* típusú ajánlatkérési esetet, és ellenőrizze, hogy az ajánlatkérésre adott összes válasz fel van-e oldva.

### <a name="step-6-set-the-key-expiration-time"></a>6. lépés: A kulcs lejárati idejének beállítása

A következő lépések szerint állíthatja be az egyes ajánlatokhoz létrehozott kulcsra alkalmazott lejárati időt.

1. Nyissa meg a **Beszerzés és forrás paraméterei \> Beállítás \> Beszerzés és forrás paraméterei** menüpontot.
1. Az **Ajánlatkérés** lap **Ennyi nappal később** mezőjébe írja be, hogy hány napig tart ki az ajánlatkérési időszak. Ajánlatkérés létrehozásakor az itt megadott számú nap hozzá lesz adva a rendszerdátumhoz, hogy meghatározza az ajánlatkérés alapértelmezett lejárati dátumát.
1. A **Titkosítás kulcs lejárati napjának eltolása** mezőjébe írja be, hogy a kiadás után az összes titkosítási kulcs hány napig legyen érvényes. A titkosítási kulcs lejárata után senki sem tudja megtekinteni, szerkeszteni vagy feloldani az azt használó lezárt ajánlatot.

> [!TIP]
> A **Titkosítás kulcs lejárati napjának eltolása** mező értéke nem lehet kisebb, mint az **Ennyi nappal később** mező értéke.

### <a name="step-7-set-the-default-bid-type"></a><a name="set-default-bid-type"></a>7. lépés: Az alapértelmezett ajánlattípus beállítása

Minden ajánlatkérési esetnek van egy ajánlattípusa. Az ajánlat típusa határozza meg, hogy az ajánlatkérési eset nyitott vagy lezárt árajánlatot biztosít-e.

#### <a name="rfq-cases-that-dont-have-a-solicitation-type"></a>Ajánlatkérési esetek, amelyek nem rendelkeznek meghirdetési típussal

A következő lépések szerint állíthatja be az új társított meghirdetési típus nélküli ajánlatkérési esetekhez társított alapértelmezett ajánlatkérési típust.

1. Nyissa meg a **Beszerzés és forrás paraméterei \> Beállítás \> Beszerzés és forrás paraméterei** menüpontot.
1. Az **Ajánlatkérés** lapon állítsa az **Ajánlat típusa** mezőt *Lezárt* értékre.

#### <a name="rfq-cases-that-have-a-solicitation-type"></a>Ajánlatkérési esetek, amelyek rendelkeznek meghirdetési típussal

A következő lépések szerint állíthatja be az új társított meghirdetési típussal rendlkező ajánlatkérési esetekhez társított alapértelmezett ajánlatkérési típust.

1. Navigáljon a következő helyre: **Beszerzés és forrás \> Beállítás \> Ajánlatkérés \> Meghirdetés típusa**.
1. Hozzon létre új meghirdetési típust, vagy válasszon ki egy létező meghirdetési típust, ahol *Lezárt* ajánlattípust szeretne használni.
1. Állítsa az **Ajánlat típusa** mezőt *Lezárt* értékre.
1. Ismételje meg ezeket a lépéseket minden további meghirdetési típushoz, ahol lezárt ajánlatkérést kíván végrehajtani.

> [!TIP]
> Új ajánlatkérés létrehozásakor nem kell meghirdetési típust hozzárendelni. Meghirdetési típus hozzárendelése esetén az ajánlatkérés alapértelmezett ajánlattípusa lekérheti azt. Ellenkező esetben a Beszerzési és forrásparaméterek között meghatározott alapértelmezett meghirdetési típus használható.

## <a name="the-sealed-bidding-process"></a>A lezárt ajánlati folyamat

A lezárt árajánlatok szinte ugyanazt a folyamatot követik, mint az [Ajánlatkérések áttekintése](request-quotations.md) részben leírtak. A fő különbség az, hogy az ajánlati adatok és mellékleteik titkosítva maradnak, amíg az ajánlatot fel nem oldják.

> [!IMPORTANT]
> A [kérdőívek](/dynamicsax-2012/appuser-itpro/view-and-respond-to-questionnaires) nincsenek titkosítva, ezért nem használhatók bizalmas információk gyűjtésére

Itt következik egy áttekintés a folyamatról:

1. Ajánlatkérést létrehozhat és elküldhet egy vagy több szállítónak.
1. A szállítók a lezárt ajánlat beküldésével válaszolnak.
1. Az ajánlatokat az ajánlatbeküldés lejárati ideje után oldja fel.
1. Az ajánlatok láthatóvá válnak, kiértékelheti és összehasonlíthatja őket.
1. Az ajánlat elfogadása után egy beszerzési rendelést generál egy beszerzési szerződést generál vagy egy beszerzési igénylést frissít.

### <a name="create-an-rfq-case-that-uses-sealed-bidding"></a>Lezárt ajánlatot használó ajánlatkérési eset létrehozása

A lezárt ajánlatok esetén az ajánlatkérési eset létrehozása szinte teljesen megegyezik a nem lezárt ajánlatkérési eljárás folyamatával. A két ajánlatkérési eset létrehozásáról az [Ajánlatkérés létrehozása](tasks/create-request-quotation.md) rész tartalmaz tudnivalókat. Ez a szakasz néhány fontos szempontot mutat be lezárt ajánlatok létrehozásával kapcsolatosan.

A lezárt ajánlatok ajánlatkérési eseteink **Ajánlattípus** mezőjének *Lezárt* értékűnek kell lennie. Ezt az értéket háromféleképpen lehet egy ajánlatkérési esethez rendelni:

- Létrehozás után közvetlenül az ajánlatkérési eseten állítsa be az értéket.
- Adja meg a lezárt ajánlatot alapértelmezett ajánlattípusként a Beszerzés és forrásparaméterek között az összes ajánlatkérési esethez. (Lásd: [A cikk korábbi, alapértelmezett](#set-default-bid-type) ajánlattípus-szakaszának beállítása.)
- Új ajánlatkérési eset létrehozásakor válasszon ki egy meghirdetési típust, amely lezárt ajánlatkérésre van beállítva. (Lásd: [Az alapértelmezett ajánlattípus beállítása](#set-default-bid-type) szakaszt.)

Lezárt ajánlatok esetén az ajánlatkérési eset **Lejárati dátuma és időpontja** határozza meg, hogy a beküldött ajánlatokat mikor lehet feloldani. Az egyes sorok **Lejárati dátum és időpont** értéke meg fog egyezni a fejlécben található értékkel.

Ajánlatkérési eset elküldése után nem tudja módosítani az ajánlat típusát.

### <a name="vendors-respond-to-an-rfq"></a>Szállítók egy ajánlatkérésre reagálnak

A lezűrt ajánlatokra válaszoló szállítók ugyanazt az eljárást használják, mint amikor a nyitott ajánlatokra reagálnak, ahogy azt az [Ajánlatkérések kezelése a szállítói ajánlattételek munkaterületen](vendor-collaboration-work-customers-dynamics-365-operations.md#working-with-rfqs-in-the-vendor-bidding-workspace) szakasz részletezi. A nyitott és lezárt ajánlatokkal való munkával kapcsolatosan lásd: [Adja meg és hasonlítsa össze az Ajánlatkérés ajánlatait, és rendeljen hozzá szerződéseket](tasks/enter-compare-rfq-bids-award-contracts.md). A lezárt ajánlatok és a nyitott ajánlatok feldolgozása között az egyetlen különbség az, hogy amíg a beszerzési időszak le nem jár, a beszerzési szakemberek nem nyithatják meg a szállító lezárt ajánlatát. Csak a szállító kapcsolattartója nyithatja meg a szállító lezárt ajánlatát.

> [!IMPORTANT]
> Lezárt ajánlattétel esetén a szállítók csak PDF formátumban tölthetik fel a mellékleteket. A többi formátumot nem elfogadható.

Miután egy regisztrált szállítói felhasználó a lezárt ajánlatkérésen kiválasztja az **Ajánlat** lehetőséget, megadhatja ajánlata adatait, és ezek az adatok biztonságban maradnak. A szállítók menthetik a munkájukat az ajánlat előkészítése során, visszatérhetnek hozzá ahányszor csak szükséges, majd elküldhetik, amikor készen állnak. A szállítók az ajánlatukat megtekinthetik e beküldés után is. Ha a szállítóknak az elküldés után módosítaniuk kell az ajánlatukat, akkor visszahatják, frissíthetik és újraküldhetik bármikor az ajánlati időszak lejárata előtt.

A lezárt ajánlat esetén a következő feltételek érvényesek:

- Lezárt ajánlatok esetén a rendszer létrehoz egy *Ajánlatkérés* naplót.
- Amikor egy szállító ajánlatot küld, létrejönnek ajánlatkérési naplók, amelyek lezárt árral rendelkeznek.
- Az eset feloldása után olyan ajánlatkérési naplók jönnek létre, amelyekhez ár és összeg tartozik. Ezt a naplót úgy lehet elérni, hogy az **Ajánlatkérési naplók** lehetőséget választja az **Összes ajánlatkérés** lapon.
- A rendszer naplót tárol minden olyan műveletről, amely a felhasználók lezárt ajánlaton hajtanak végre. Ilyen művelet lehet az ajánlat megtekintése, szerkesztése és mentése. Ez a napló mind a szállító, mind a beszerzési szakemberek számára látható, akik hozzáférhetnek az ajánlathoz.
- Az ajánlat előrehaladtával a beszerzési szakemberek megtekinthetik az állapotát. Az állapot ekkor *A Szállító frissítést végez* Vagy a *Szállító által elküldve*.
- A lezárt ajánlat sorai mindaddig *Elküldött* állapotúak maradnak, amíg az ajánlatot fel nem oldják.
- Ha a szállító úgy dönt, hogy elutasítja az ajánlatot, az ajánlat **Válasz állapota** státusza *Szállító által elutasított* lesz. Ez az állapot a beszerzési személyzet számára látható lesz.
- A kérdőívek válaszai az adatbázisban **nem** titkosított formában tárolódnak. Ennek megfelelően nincsenek lezárva. Nem láthatók azonban az ajánlatkérési felhasználói felületen, amíg az esetet fel oldják.

### <a name="all-sealed-bid-activities-are-logged"></a>Minden lezárt ajánlati tevékenység naplózva van

A részletes napló az ajánlathoz kapcsolódó minden felhasználói tevékenységet és műveletet rögzít. A tevékenységnapló lehetővé teszi a szervezetek számára annak megállapítását, hogy élettartamuk során ki módosította az ajánlatot, illetve hogy milyen frissítések voltak. Lehetővé teszi továbbá a szervezetek számára annak megerősítését is, hogy csak erre jogosult személyek fértek hozzá a lezárt ajánlatokhoz. A tevékenységnapló minden ajánlat **Tevékenység** lapján elérhető.

### <a name="review-rfq-activity"></a>Ajánlatkérési tevékenység áttekintése

A rendszer naplózza az ajánlat minden interakcióját, és megtekinthető a **Tevékenység** oldalon. A következő ábrán egy példa látható.

![Példa a Tevékenység oldalra](media/sealed-bidding-rfq-activity.png "Példa a Tevékenység oldalra")

A szállítók úgy férhetnek hozzá a **Tevékenység** laphoz, hogy az **Ajánlatkérés lezűrt ajánlat** lapján kiválasztják a **Tevékenység** lehetőséget. A beszerzők úgy férhetnek hozzá, hogy az **Ajánlatkérés** lapon a **Tevékenység** lehetőséget választják. A tevékenységnapló teljes rálátást biztosít a szállítók és az ajánlatot elérő beszerzők számára. Tehát bármilyen jogosulatlan hozzáférés feltárható.

### <a name="unseal-sealed-bids"></a>Lezárt ajánlatok feloldása

Amikor a lezárt ajánlatkérési esethez beállított **Lejárati dátum és időpont** elmúlt, elérhetővé válik a **Feloldás** gomb. A kiválasztott ajánlatkérési esethez tartozó minden ajánlat feloldásához válassza a **Feloldás** lehetőséget. Ezután minden ajánlati adat és melléklet láthatóvá válik, hogy kezelni tudják az esetre adott válaszokat. Ezenkívül létrejönnek az elküldött ajánlatadatokat tartalmazó naplók is.

A rendszer naplózza a feloldási eseményt és megtekinthető a **Tevékenység** oldalon.

### <a name="process-accepted-bids"></a>Elfogadott ajánlatok feldolgozása

A korábban lezárt ajánlatok összehasonlításának és jóváhagyásának folyamata megegyezik a nyitott ajánlatok folyamatával. A még le nem adott ajánlatok pontozásának, összehasonlításának, elutasításának és elfogadásának módját lásd: [Adja meg és hasonlítsa össze az Ajánlatkérés ajánlatait, és rendeljen hozzá szerződéseket](tasks/enter-compare-rfq-bids-award-contracts.md).

## <a name="the-rfq-activity-log-can-never-be-deleted"></a>Az ajánlatkérési tevékenységnapló nem törölhető

Senki, még a rendszergazdák és a Microsoft ügyfélszolgálata sem szerkesztheti vagy törölheti az ajánlatkérési tevékenységnaplót. Ez a korlátozás segít biztosítani a lezárt ajánlati folyamat tisztességességét. Elősegíti a pontos auditnapló fenntartását is.
