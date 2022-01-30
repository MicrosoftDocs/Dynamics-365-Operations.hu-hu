---
title: A beszerzési irányelvek áttekintése
description: Ez a cikk a beszerzési irányelvekkel kapcsolatos információkról nyújt tájékoztatást. A beszerzési irányelv az igénylési folyamatot szabályozó szabályok gyűjteménye. A beszerzési irányelvek lehetővé teszik a beszerzési rendszergazdáknak a beszerzési stratégia megvalósítását a szervezet stratégiai beszerzési követelményihez igazodó irányelv struktúrájának létrehozásával.
author: Henrikan
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqSourcingPolicyRule, SysPolicy, SysPolicyListPage, PurchReqControlRule, RequisitionReplenishCatAccessPolicyRule, PurchReApprovalPolicyRule, RequisitionReplenishControlRule, PurchReqControlRFQRule
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "11614"
- intro-internal
ms.assetid: 729a304d-0f3f-4ccb-bd5b-46ee0976c57f
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3cc150ae1a912fbfb4daf505e4240786c2f380a3
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7982277"
---
# <a name="purchasing-policies-overview"></a>A beszerzési irányelvek áttekintése

[!include [banner](../includes/banner.md)]

Ez a cikk a beszerzési irányelvekkel kapcsolatos információkról nyújt tájékoztatást. A beszerzési irányelv az igénylési folyamatot szabályozó szabályok gyűjteménye. A beszerzési irányelvek lehetővé teszik a beszerzési rendszergazdáknak a beszerzési stratégia megvalósítását a szervezet stratégiai beszerzési követelményihez igazodó irányelv struktúrájának létrehozásával.

Egy beszerzési irányelv irányelvszabályokból épül fel. Irányelvszabály definiálásakor elsőként ki kell választania egy irányelvszabály-típust. Ezután a szabály beállításainak, a kezdő dátumának és záró dátumának meghatározásával hozhat létre szabályt a szabálytípushoz.  

Például egy rendszergazda létrehoz egy irányelvet, kiválasztja a **Katalógus-irányelv** szabálytípust, majd az irányelvhez hozzáad egy katalógus-irányelvszabályt. Ez a katalógus-irányelvszabály meghatározza azt, hogy belső beszerzéshez a Kaland katalógust kell használni. A beszerzési irányelv egy adott szervezethez való társítása után a társított szervezet alkalmazottai igénylések létrehozásakor látják a Kaland katalógust.

## <a name="assigning-policies-to-organizations"></a>Irányelvek hozzárendelése szervezetekhez
Egy irányelv életbe léptetése előtt azt társítani kell egy szervezethez. A beszerzési irányelvek a **Beszerzés belső ellenőrzése** hierarchiacélhoz vannak rendelve. Ezért a beszerzési irányelvek csak olyan szervezetekre érvényesek, amelyek **Beszerzés belső ellenőrzése** hierarchiacélú hierarchiákban szerepelnek. Szervezeteket a CompanyInfo táblában, a jogi személyek egyszerűsített listájából is kiválaszthat. Ezek a jogi személyek az irányelv-keretrendszerben „Vállalatok”-ként vannak megjelölve.

## <a name="determining-which-rule-to-apply"></a>Alkalmazandó szabályok meghatározása
A beszerzési irányelvek konfigurálásának módjától függően több szabály is érinthet egy szervezethez tartozó felhasználókat. Az alábbi példák a beszerzési irányelvek konfigurálásának különböző lehetőségeit szemléltetik és megmutatják, hogyan történik az irányelvek alkalmazása egy tranzakciónál.

### <a name="example-1-simple-purchasing-policy-configuration"></a>1. példa: Beszerzési irányelv egyszerű konfigurálása

Kisebb, kevésbé összetett szervezetek beállíthatják a beszerzési irányelveket jogi személyek szerint, ehhez elegendő csupán a Vállalatok szervezeti hierarchia használata.  

A Fabrikam egy kisvállalkozás, amelyen belül a beszerzési követelmények kevéssé változnak. A beszerzési szabályok csak a szervezet különböző jogi személyei esetén eltérőek. Például a Fabrikam kanadai, illetve USA-beli vállalatának alkalmazottai más katalógusokból és más szállítóktól rendelnek. Ezért a Fabrikam a beszerzési irányelveit a jogi személyek szintjén állítja be.  

A Fabrikam két beszerzési irányelvet hoz létre. Az A. házirend az egyesült államokbeli jogi személyre vonatkozik, 1111. A B. házirend az kanadai jogi személyre vonatkozik, 2222. Ha egy, az 1111-es jogi személyhez tartozó alkalmazott hoz létre beszerzési igénylést, az irányelvszabályokat a rendszer az A irányelvből származtatja. Például az alkalmazott számára látható termékkatalógust az A irányelv katalógus-irányelvszabálya határozza meg.  

Ha egy, a 2222-es jogi személyhez tartozó alkalmazott hoz létre beszerzési igénylést, az irányelvszabályokat a rendszer a B irányelvből származtatja.  

**Megjegyzés:** Amennyiben egy 1111-es jogi személyhez tartozó alkalmazott egy 2222-es jogi személyhez tartozó alkalmazott nevében vásárol egy cikket, a 2222-es jogi személyhez megadott irányelvszabályok (azaz a B irányelv irányelvszabályai) érvényesülnek.

### <a name="example-2-complex-purchasing-policy-configuration"></a>2. példa: Beszerzési irányelv összetett konfigurálása

Az előző példában az összes beszerzési szabály meghatározása egyetlen szervezeti hierarchiában, a Vállalatok szervezeti hierarchiában történt. Egy összetett szervezet azonban több szervezeti hierarchiára is definiálhat irányelveket.  


A Contoso egy nagyvállalat, amelyben az igénylési folyamat kézben tartásához összetett beszerzési szabályokra van szükség. A Contoso két különböző szervezeti hierarchiára vonatkozóan ad meg szabályokat: Részleg és Globális beszerzés ellenőrzése.  

Az 123 irányelv az Egyesült Királyságbeli értékesítés – Értékesítési osztályra vonatkozó Részleg szervezeti hierarchiára érvényes. Az 123 irányelvben szereplő, beszerzési igénylést ellenőrző szabály előírja, hogy minimális rendelési mennyiségre vonatkozó korlátozásokat kell bevezetni. Ebben a szabályban a **Minimális rendelési mennyiségre vonatkozó korlátozások érvényesítése** beállítás ki van választva.  

A 456 irányelv az Értékesítési- és marketingosztályra vonatkozó Globális beszerzés ellenőrzése szervezeti hierarchiára érvényes. Az 456 irányelvben szereplő, beszerzési igénylést ellenőrző szabály nem írja elő, hogy minimális rendelési mennyiségre vonatkozó korlátozásokat kell bevezetni. Ebben a szabályban a **Minimális rendelési mennyiségre vonatkozó korlátozások érvényesítése** beállítás nincs kiválasztva.  

Sam a Contonso Egyesült királyságbeli irodájában, az Egyesült Királyságbeli értékesítés – Értékesítési osztályon dolgozik. Az osztályára érvényesek mind a Részleg, mind a Globális beszerzés ellenőrzése szervezeti hierarchiákra vonatkozó irányelvek. Amikor Sam beszerzési igénylést hoz létre, a rendszernek el kell döntenie, hogy melyik irányelvet alkalmazza. A rendszergazda úgy állítja be a beszerzési irányelvek paramétereit, hogy a beszerzési irányelvek alkalmazása a következő elsőbbségi sorrend szerint történjen:

1.  Globális beszerzés ellenőrzése
2.  Részleg
3.  Vállalatok

Ezért a Sam által létrehozott beszerzési igénylésre a 456 irányelv érvényes, és a beszerzési igényléshez nem szükséges minimális rendelési mennyiség.

## <a name="policy-rules"></a>Irányelvszabályok
### <a name="catalog-policy-rule"></a>Katalógus irányelvszabálya

A katalógus-irányelvszabály meghatározza, hogy mely beszerzési katalógus látható a felhasználók számára beszerzési igénylés létrehozásakor. Ha egy felhasználó engedélyt kapott termékek megrendelésére egy másik felhasználó nevében, az igénylés a kérelmező jogi személye és üzemi egysége számára definiált katalógus-irányelvszabály használatával határozza meg azt, hogy melyik katalógust jelenjen meg. Katalógus-irányelvszabály definiálása előtt létre kell hoznia és közzé kell tennie egy beszerzési katalógust.

### <a name="category-access-policy-rule"></a>Kategóriához való hozzáférés irányelvszabálya

A kategória-hozzáférési irányelvszabály meghatározza, hogy a felhasználóknak beszerzési igénylések létrehozásakor mely kategóriákhoz van hozzáférésük. Amennyiben nincs megadva szabály, a beszerzési igényléshez minden beszerzési kategória hozzáadható.

1.  **A fölérendelt szabállyal együtt** lehetőség kiválasztásával alkalmazhatja a kategóriára a szülő szervezet kategória-hozzáférési irányelvszabályát.
2.  A **Rendelkezésre álló kategóriák** ablaktáblán adja meg, hogy a szabály mely kategóriákra vonatkozzon. Kategória választásakor a hierarchiában felette lévő összes kategória szintén belekerül a **Kiválasztott kategóriák** listába.
3.  Az **Alkategóriákkal** lehetőség kiválasztásával alkalmazhatja a szabályt a kijelölt kategória összes alkategóriájára.

### <a name="category-policy-rule"></a>Kategória irányelvszabálya

A kategória-irányelvszabály meghatározza, hogyan választhatnak ki szállítókat a felhasználók az egyes kategóriákhoz. Ezenkívül bevételezési és számlázási folyamatokra vonatkozó követelményeket is meghatároz.

### <a name="re-approval-rule-for-purchase-orders"></a>Beszerzési rendelések ismételt jóváhagyási szabálya

Az ismételt jóváhagyási szabály egy olyan választható szabály, amely meghatározza az ismételt jóváhagyás igénylésének feltételeit egy beszerzési rendelés megváltozása esetén. A beszerzési rendelések munkafolyamatában a kiválasztott mezők értékelésére kerül sor, amennyiben a munkafolyamatban be van állítva a „Beszerzési rendelés ismételt jóváhagyása szükséges” feltétel.

> [!NOTE]
> A könyvelési felosztás mindig alaphelyzetbe áll, ha az engedélyezett változáskezeléssel rendelkező jóváhagyott beszerzési rendelést megváltoztatják. Tehát tudnia kell, hogy ha el szeretné kerülni a beszerzési rendelés újbóli jóváhagyását bizonyos mezők megváltoztatásakor, akkor a Accounting distribution.changed mező NEM szerepeltethető kijelölt mezőként az újbóli jóváhagyásnál. 

### <a name="purchase-requisition-rfq-rule"></a>Beszerzési igénylés ajánlatkérési szabályai

A beszerzési igénylés ajánlatkérési szabálya meghatározza azokat a feltételeket, amelyek esetén ajánlatkérés szükséges a beszerzési igénylés valamelyik sorához. Ha egy sor megfelel a feltételeknek, megjelenik a „nem hivatalos ajánlatkérés” vagy „hivatalos ajánlatkérés” pecsét az igénylési sorban.

### <a name="purchase-requisition-control-rule"></a>Beszerzési igénylés ellenőrzési szabálya

A beszerzési igénylés ellenőrzési szabálya a **fogyasztás** típusú igénylésekhez nem kötelező szabály. Az ilyen típusú szabályok létrehozásakor különböző lapokon található beállításokat adhat meg:

-   A **Munkafolyamat elküldése** lapon beállíthatja azokat a mezőket, amelyeket a jóváhagyásra elküldendő igénylés igénylési sorában meg kell adni.
-   A **Rendelési mennyiségek** lapon beállíthatja azokat a mezőket, amelyek bizonyos körülmények között szükségesek a beszerzési igényléshez. Rendelési mennyiségeket is érvényesíthet.
-   A **Dátumok** lapon beállíthatja, hogy a könyvelési dátum és a kért dátum megegyezzen-e
-   A **Cím** lapon megadhatja, hogy a felhasználó számára engedélyezett-e a rendszerben új cím létrehozása a beszerzési igénylésre való alkalmazáshoz.

### <a name="requisition-purpose-rule"></a>Igénylésicél-szabály

A igénylésicél-szabály egy választható szabály, amely meghatározza az adott jogi személy számára engedélyezett igénylésicél-típust. Amennyiben ebben a szabályban nincs megadva másik cél, az igénylések célja létrehozáskor automatikusan **Felhasználás** lesz.

### <a name="replenishment-category-access-policy-rule"></a>Feltöltési kategória hozzáférési irányelvszabálya

A feltöltési kategória hozzáférési irányelvszabálya egy választható szabály, amely meghatározza egy adott jogi személy igénylési igényeinek kielégítéséhez elérhető termékeket, ha az igénylési cél **Feltöltés**.

### <a name="replenishment-control-rule"></a>Feltöltés-ellenőrzési szabály

A feltöltés-ellenőrzési szabály egy választható szabály, amely meghatározza azokat mezőket, amelyeket a jóváhagyásra beküldendő igénylés igénylési sorában meg kell adni, ha az igénylési cél **Feltöltés**.

### <a name="purchase-order-creation-and-demand-consolidation-rule"></a>Beszerzési rendelés létrehozására és igényösszesítésre vonatkozó szabály

A beszerzési rendelés létrehozására és igényösszesítésre vonatkozó szabály meghatározza egy beszerzési rendelés jóváhagyott beszerzési igénylésből való generálásakor használt irányelvszabályokat. Az ilyen típusú szabályok létrehozásakor különböző lapokon található beállításokat adhat meg:

-   A **Beszerzési rendelés felosztása** lapon meghatározhatja a beszerzési igénylési sorok különálló beszerzési rendelésekre való felosztásának feltételeit.
-   Az **Ár/engedmény átvitele** lapon megadhatja, hogy beszerzési rendelés létrehozásakor mely esetben kerüljön sor az ármegállapodások újraszámítására:
    -   **Csak ha nincs kereskedelmi megállapodás** – Az árak és az engedmények csak akkor vihetők át a beszerzési igénylésből, ha nincsenek alkalmazandó kereskedelmi megállapodások vagy alapár. Ha a cikkhez vagy a szállítóhoz tartozik kereskedelmi megállapodás vagy alapár, akkor a program a kereskedelmi megállapodás vagy alapár alapján újraszámolja az árakat és az engedményeket, és alkalmazza azokat a beszerzési rendelésre. Ha nincs más beállítás megadva, ez az alapértelmezett működés.
    -   **Mindig** – Az árak és az engedmények mindig átvihetők a beszerzési igénylésből.

    A kérelmezőnek engedélyezheti az ár és az engedmény átviteli módszerének megváltoztatását az egyes beszerzési igénylési soroknál, függetlenül az ár/engedmény definiált átviteli szabályától. Válassza ki a **Kézi felülbírálás engedélyezése beszerzésiigénylés-soronként** lehetőséget, ha engedélyezni szeretné ezt a képességet.
-   A **Cikkleírás átvitele** lapon átviheti a cikkleírást az igénylésből, ha az egy ajánlatkérésből származik.
-   Az **Árkülönbözet tűréshatára** lapon definiálhatja azokat a szabályokat, amelyekkel a beszerzési katalógus egy cikkének árnövekedésekor a jóváhagyott beszerzési igénylések visszairányíthatók az ellenőrzési folyamatba. Beállíthatja azt a maximális összeget, amellyel a beszerzés igényléseken szereplő cikkek nettó összege növelhető a beszerzési igénylés jóváhagyásának időpontja és a beszerzési rendelés létrehozásának időpontja között. A nettó összeg a következő képlettel számítható: (\[Mennyiség × (Egységár – Engedmény) ÷ Áregység\] + Beszerzés vegyes költségei) × (100 – Engedményszázalék) ÷ 100 A megadott ártűréshatárt túllépő beszerzési igénylési sorokat manuálisan kell feldolgozni. A **Hibafeldolgozás** lapon konfigurált szabályok határozzák meg a beszerzési igénylési sorok feldolgozásának módját.
-   A **Hibafeldolgozás** lapon adhatja meg azt a feldolgozási szabályt, amelyet akkor kell alkalmazni a beszerzési igénylésekre, ha szállítói hiba vagy ártűréshatár-hiba miatt nem sikerül az ellenőrzésük. Válasszon a következő lehetőségek közül:
    -   **Nincs művelet** – A beszerzési igénylési sorok a **Jóváhagyott beszerzési igénylések kiadása** oldalon maradnak. A beszerzési igénylési sorok állapota **Jóváhagyva** marad. A hibákat azonban meg kell oldani ahhoz, hogy beszerzési rendelést lehessen létrehozni a beszerzési igénylési sorokhoz.
    -   **Beszerzési igénylés sorának visszavonása** – A beszerzési igénylési sorok visszavonásra kerülnek. A kérelmező létrehozhat új beszerzési igénylést a visszavont sorokhoz, ha továbbra is kérelmezni kívánja a cikkeket.
    -   **Új sor létrehozása a beszerzési igénylésben** – A beszerzési igénylési sorok visszavonásra kerülnek. Ezután új beszerzési igénylések jönnek létre, amelyek csak azokat a beszerzési igénylési sorokat tartalmazzák, amelyek ellenőrzése sikertelen volt. Az új beszerzési igénylések **Tervezet** állapotúak lesznek a létrehozáskor. Ezek a beszerzési igénylések a hibák kijavítása után újból elküldhetők ellenőrzésre. A beszerzési igénylési sorok készítője értesítést kap a sorok visszavonásáról, valamint arról is, hogy új beszerzési igénylések jöttek létre a sikertelen beszerzési igénylési sorokhoz.
-   A **Beszerzési rendelés manuális létrehozása** lapon adhatja meg azokat a paramétereket, amelyek meghatározzák, hogy beszerzési igényléseket manuálisan kell-e feldolgozni, vagy automatikusan átalakíthatók beszerzési rendelésekké. A paraméterek vonatkozhatnak belső katalóguscikkekre, külső katalóguscikkekre vagy katalógusban nem szereplő cikkekre. Válasszon a következő lehetőségek közül:
    -   **Beszerzési rendelés manuális létrehozása** – Az összes beszerzési igénylés esetén manuálisan történik a beszerzési rendelések létrehozása.
    -   **Beszerzési rendelés automatikus létrehozása** – Az összes jóváhagyott beszerzési igénylés esetén automatikusan történik a beszerzési rendelések létrehozása. Egyik beszerzési igénylésnél sem kell kézzel létrehozni a beszerzési rendelést.
    -   **Beszerzési rendelések automatikus létrehozása, kivéve a megadott feltételek teljesülése esetén** – A megadott feltételeknek megfelelő beszerzési igénylések esetén a beszerzési rendelések létrehozása manuálisan történik. A jóváhagyott beszerzési igényléseket a program automatikusan beszerzési rendelésre alakítja át. Ha a **Beszerzési rendelések automatikus létrehozása, kivéve a megadott feltételek teljesülése esetén** lehetőséget választja, beszerzési kategóriákat és szállítókat vehet fel annak megadásához, hogy a jóváhagyott beszerzési igénylési sorok közül melyik sorok igényelnek kézi feldolgozást. Ez a beállítás vonatkozhat a belső katalóguscikkekre, a külső katalóguscikkekre és a katalógusban nem szereplő cikkekre is. Amikor beszerzési kategóriát választ, a beszerzési kategóriához tartozó összes alkategóriát is kiválasztja. Válassza az **Összes** lehetőséget egy meghatározott típusú beszerzési igénylési sor esetében, ha az összes ilyen típusú sornál kézi feldolgozást kíván megadni.

    Ha azt szeretné, hogy a beszerzési rendelések automatikusan jöjjenek létre a jóváhagyott beszerzési igénylésekből a beszerzési rendelések kötegelt létrehozási feladatának futtatásakor, akkor válassza ki a **Beszerzési rendelések automatikus létrehozásának végrehajtása kötegelt feladatként** lehetőséget. Ez a beállítás csak azokra a beszerzési igénylésekre érvényes, amelyek nem igényelnek kézi feldolgozást. Ha a beszerzési rendelések automatikus létrehozását kötegelt feladatként futtatja, ezt a tevékenységet ütemezheti olyan időpontra, amikor az erőforrások kevésbé korlátozottak. Amennyiben a beszerzési igénylési sorokra ki van választva az **Előleg szükséges** lehetőség, a jóváhagyott beszerzési igénylések manuális feldolgozásához válassza az **Az igénylés előlegfizetéshez való előkészítésének időpontja** lehetőséget. A kézi feldolgozásra kijelölt beszerzési igénylések szűrhetők, ha csak azokat a beszerzési igénylési sorokat kívánja megjeleníteni, amelyek előleget igényelnek.
-   Az **Igényösszevonás** lapon megadhatja azokat a paramétereket, amelyek meghatározzák, hogy a manuálisan feldolgozott beszerzési igénylések figyelembe vehetők-e a beszerzési igénylések összevonásakor. A paraméterek vonatkozhatnak belső katalóguscikkekre, külső katalóguscikkekre vagy katalógusban nem szereplő cikkekre. Válasszon a következő lehetőségek közül:
    -   **Igényösszevonás tiltása** – Igényösszevonáskor nem vehetőek figyelembe a jóváhagyott beszerzési igénylési sorok. Ez az alapértelmezett beállítás, és csak azokra a beszerzési igénylési sorokra vonatkozik, amelyek kézi feldolgozást igényelnek a beszerzési rendelések létrehozásához.
    -   **Igényösszevonás mindenkori engedélyezése** – Igényösszevonáskor minden jóváhagyott beszerzési igénylési sor figyelembe vehető. **Megjegyzés:** Ha az **Igényösszevonás mindenkori engedélyezése** beállítást választja az **Igényösszevonás** lapon, azonban a **Beszerzési rendelések automatikus létrehozása** beállítást a **Beszerzési rendelés manuális létrehozása** lapon, az összes beszerzési igénylést manuálisan kell feldolgozni.
    -   **Igényösszevonás engedélyezése a megadott feltételek teljesülése esetén** – Definiálhatja azokat a feltételeket, amelyek meghatározzák, hogy a jóváhagyott beszerzési igénylési sorok figyelembe vehetőek-e igényösszevonáskor. A beszerzési igénylési sorok mindegyik típusához beállíthatja a feltételeket a beszerzési kategória és a szállító szerint. Ha az **Igényösszevonás engedélyezése a megadott feltételek teljesülése esetén** lehetőséget választja, a beszerzési igénylési sorok mindegyik típusához beállíthatja a feltételeket a beszerzési kategória és a szállító szerint. Amikor beszerzési kategóriát választ, a beszerzési kategóriához tartozó összes alkategóriát is kiválasztja. Ha az **Összes** lehetőséget választja egy meghatározott sortípusnál, az adott sortípussal rendelkező összes beszerzési igénylési sor használható lesz az igényösszevonáshoz.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]