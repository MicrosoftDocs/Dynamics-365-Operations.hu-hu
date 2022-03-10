---
title: Visszatérítések létrehozása a pénztárban
description: Ez a témakör azt ismerteti, hogyan lehet visszatérítéseket kezdeményezni a készpénzben fizetett, azonnal átvett tranzakciókhoz vagy vevői rendelésekhez a Microsoft Dynamics 365 Commerce pénztár (POS) alkalmazásban.
author: hhainesms
ms.date: 02/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.20
ms.openlocfilehash: 3250f702f033fb8b00763542fd8342c089b47b2e
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349691"
---
# <a name="create-returns-in-pos"></a>Visszatérítések létrehozása a pénztárban

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet visszatérítéseket kezdeményezni a készpénzben fizetett, azonnal átvett tranzakciókhoz vagy vevői rendelésekhez a Microsoft Dynamics 365 Commerce pénztár (POS) alkalmazásban.

> [!NOTE]
> A Commerce 10.0.20 és újabb kiadásaiban , a POS-terminálon elérhető egy új funkció, amelynek neve **Egyesített visszaküldés-feldolgozási élmény a pénztárban**. Ez a funkció egységesebb és következetesebb visszárufolyamatot biztosít a pénztárban, függetlenül attól, hogy milyen tranzakciótípus (azonnal fizetett és átvett tranzakció vagy vevői rendelés) vagy eredeti csatorna alkalmazásával hozták létre a rendelést. Javasoljuk, hogy minden szervezet kapcsolja be ezt az új funkciót, hogy segítsen javítani a POS-terminálon keresztüli visszáru-feldolgozás általános megbízhatóságát.
>
> A funkciót a bekapcsolása után nem lehet kikapcsolni.

## <a name="process-returns-by-using-the-return-transaction-operation"></a>Visszáru feldolgozása visszáru-tranzakciós művelettel

Azt ajánljuk, hogy adja hozzá a visszáru-tranzakció műveletet a POS [képernyőelrendezéséhez](pos-screen-layouts.md). A Commerce 10.0.20-as verzió előtti kiadásokban a visszáru-tranzakciós művelet csak a készpénzben fizetett és azonnal átvett tranzakciók visszáruinak feldolgozását támogatja megfelelően. Miután bekapcsolta a **Egyesített visszaküldés-feldolgozási élmény a pénztárban** funkciót a Commerce 10.0.20 vagy újabb verzióban, a visszárutranzakció művelet a vevői rendelésekből származó visszáru feldolgozását is támogatja, például a már kiszámlázott „átvételi” és „kiszállított” rendeléseket is.

A visszáru-tranzakciós műveletből a felhasználók a következő négy keresési feltétel valamelyikével kereshetnek készpénzben fizetett és azonnal átvett tranzakciókat és vevői rendeléseket. A felhasználók eszköz billentyűzetével, a képernyőn megjelenő billentyűzettel vagy vonalkódolvasóval adhatják meg ezeket a feltételeket.

- Nyugtaazonosító
- Rendelésszám
- Csatorna hivatkozási azonosítója (más néven rendelés-visszaigazolás azonosítója)
- Számla azonosítója

Ha a keresési feltételeknek megfelelő tranzakció vagy rendelés található, megjelenik a **Visszaküldendő termékek** lap. Itt a felhasználók megadhatja a visszaküldött cikkeket. Visszárumennyiségeket és okkódokat is megadhatjak.

A POS a visszárutermékek listájában szereplő minden rendelési sorban megjeleníti az eredeti beszerzési mennyiség és a korábban feldolgozott visszárumennyiségek adatait. A felhasználó által a rendeléssorhoz megadott visszárumennyiség nem lehet kisebb, mint a **Visszáruként elérhető** mező értéke.

![Visszaküldendő termékek lap.](media/returnslist.png)

Ha a visszáru feldolgozása során a felhasználó rendelkezik a fizikai termékkel, és a termékhez vonalkód is van, akkor a felhasználó beolvashatja a vonalkódot a visszáru regisztrálásához. A vonalkódok minden beolvasása egy cikkel növeli a visszahozott mennyiséget. Ha azonban a vonalkód címkéje tartalmaz beágyazott mennyiséget, ez a mennyiség lesz megadva a **Visszaküldés most** mezőben.

A felhasználók manuálisan is kiválaszthatják a visszaküldendő cikkeket a **Visszaküldendő termékek** oldalon, majd a jobb oldali részletező ablak használatával frissíthetik a **Visszaküldés most** mezőt.

Ha egy tranzakcióhoz meg van adva a maximálisan elérhető **Visszaküldés most** mennyiség, akkor a felhasználó a Pénztár alkalmazássávján az **Összes kijelölése** művelettel beállíthatja a maximális visszaküldhető mennyiséget az összes sorhoz.

A felhasználónak minden olyan sornál, amelynél van **Visszaküldés most** mennyiség, a részletek panelen ki kell választania egy okkódot a visszaküldéshez. A készpénzben fizetett és azonnal átvett tranzakciók visszáruja esetén a visszaadott okkódok az üzlet funkcióprofiljában infókódként vannak beállítva. A vevői rendelések visszárujára vonatkozó okkódok a Dynamics 365 Commerce központ **Visszaadási okkódok** oldalán vannak konfigurálva.

Miután az egyes visszaadott cikkekhez beállította a visszaküldött mennyiséget és az okkódot, a felhasználó a feldolgozáshoz kiválaszthatja a POS alkalmazássávon a **Visszáru** műveletet. Megjelenik a POS tranzakciós lapja, ahol az előző lapon kiválasztott visszáru-elemeket hozzáadta a rendszer a kosárhoz. A cikkek most **Visszaküldés most** mennyiségei negatív mennyiségként jelennek meg a tranzakcióban, és a program kiszámítja a teljes visszatérítést.

A felhasználók akkor adhatnak hozzá sorokat a visszáru-tranzakcióhoz, ha csererendelést hoznak létre. A felhasználók további ad hoc visszáru-visszaküldési cikkeket is hozzáadhatnak a visszáru-tranzakcióhoz a hozzáadott pozitív mennyiségű értékesítési sorhoz a **Termékvisszaküldés** használatával.

> [!NOTE]
> A pénztárban a **Termék visszaküldése** művelet nem érvényesíti az eredeti tranzakciókat, és bármely termékek visszaküldését lehetővé teszi. Ezért azt ajánljuk, hogy csak jogosult felhasználó hajthassák végre ezt a műveletet vagy, hogy a művelet használata esetén vezetői felülbírálás szükséges legyen.

Ha a visszatérítés esedékes a fizetéskor, a szervezetek olyan [visszatérítési fizetési irányelveket](refund_policy_returns.md) konfigurálhatnak, amelyek korlátozzák a vevőknek történő visszatérítéshez használható fizetési módokat. Ha az eredeti tranzakció kifizetése hitelkártyával történt, a fizetés feldolgozója és a rendszer konfigurációja alapján, a felhasználóknak lehetősége lehet [visszatérítést fizetni az eredeti kártyára](dev-itpro/linked-refunds.md). Ebben az esetben a visszatérítés anélkül is feldolgozható, hogy a vevőnek újra le kellene húznia a hitelkártyáját. Az eredeti kifizetés jogkivonata lesz használva a visszatérítés kiadására.

## <a name="other-return-options-in-pos"></a>A POS egyéb visszáru lehetőségei

Ha az **Egyesített visszaküldés-feldolgozási élmény a pénztárban** funkció be van kapcsolva, akkor a felhasználók a pénztár **Napló megjelenítése** műveletével is kezdeményezhetik a visszatérítést egy azonnal fizetett és átvett tranzakcióhoz vagy vevői rendeléshez. Ezután kijelölhetnek egy tranzakciót a naplóban, majd kiválaszthatják a **Visszáru** műveletet a pénztár alkalmazássávján. Ez a művelet csak akkor érhető el, ha a rendelésben visszárusorok vannak. A **Visszáru-tranzakció** művelettel azonos felhasználói élményt indít el.

A felhasználók a pénztárban a **Rendelés visszahívása** művelettel is megkereshetik és visszahívhatják a vevői rendeléseket. (Ez a művelet nem használható kKészpénzzel fizetett, azonnal átvett tranzakciókhoz). Ebben az esetben a vevői rendelés kiválasztása után a pénztár alkalmazássávján a **Visszáru** művelettel lehet kezdeményezni a vevői rendelés visszavételét. Ez a művelet csak akkor érhető el, ha a rendelésben visszárusorok vannak. A **Visszáru-tranzakció** vagy **Napló megjelenítése** művelettel azonos felhasználói élményt indít el.

## <a name="return-orders-are-posted-to-commerce-headquarters-as-sales-orders"></a>A visszárurendelések értékesítési rendelésként vannak feladva a Commerce központ számára 

Ha az **Egyesített visszaküldés-feldolgozási élmény a pénztárban** funkció be van kapcsolva, minden, a pénztárban létrehozott visszáru értékesítési rendelésként írva a Commerce Headquarters alkalmazásba, negatív sorokkal. A Commerce 10.0.20-as verzióját megelőző verziókban a felhasználók kiválaszthatják hogy a visszárurendeléseket negatív sorokkal beküldött értékesítési rendelésként adják-e fel, vagy olyan visszárurendelések legyenek, amelyek a Visszáru szállítása esetére való azonosító (RMA) folyamaton keresztül jönnek létre. 

Az **Egyesített visszaküldés-feldolgozási élmény a pénztárban** folyamat során már elavult az RMA-folyamat használata a visszáru létrehozáshoz a pénztárban ki lett vezetve. A funkció bekapcsolása után minden visszaküldés negatív sorokat létrehozó értékesítési rendelésként jön létre.

## <a name="offline-return-processing-improvements"></a>Offline visszáru-feldolgozási fejlesztések

A legtöbb esetben, amikor egy visszaküldés feldolgozása a pénztárban történik, a rendszer megpróbálja valós idejű szolgáltatáshívást (RTS) indítani a Commerce Headquarters felé, hogy ellenőrizze a visszáru aktuális mennyiségét. Ezzel az ellenőrzéssel megelőzhetők olyan csalási szituációk, amikor a vevő több helyen próbálja meg visszaadni ugyanazt a cikket.

Annak érdekében, hogy kezelni lehessen azokat a helyzeteket, ahol az RTS-hívást hálózati vagy kapcsolati problémák miatt nem lehet végezni, egy folyamat lett bevezetve, amely rendszeres időközönként szinkronizálja a Commerce Headquarters rendszerből származó visszáru-mennyiségi adatokat az üzlet csatorna-adatbázisába. Ezen csatornaoldali visszáru-követés révén biztosítható, hogy a pénztárban megjelenő **Visszáruként elérhető** mennyiségek meglehetősen pontosak legyenek még akkor is, ha a pénztár offline állapotban van. Arról is gondoskodik, hogy a pénztár továbbra is ellenőrizze a csatornaoldali adatokat, hogy megelőzhetőek legyenek a csalások.

Az offline visszaküldési folyamatnak a megfelelő módon való alkalmazásához a szervezeteknek be kell ütemezniük a **Visszárumennyiségek frissítése** kötegelt feladatot a Commerce Headquarters alkalmazásba, hogy az gyakran fusson. Javasoljuk, hogy a feladat ugyanolyan gyakorisággal fusson, mint a P-feladat, amely új tranzakciókat kér le a Commerce-csatornákból a Commerce Headquarters alkalmazásba.

A **Visszárumennyiségek frissítése** feladat kiszámítja az a mennyiséget, amely visszáruként elérhető az összes értékesítési rendeléshez, ami megtalálható a Commerce központban. A feladat által kiszámított adatokat ezután el kell küldeni a csatorna-adatbázisoknak, hogy frissíthetők legyen az üzlet csatornái. Erre a célra a **Visszárumennyiségek** (1200) elosztási feladat szolgál. Mivel a visszáru mennyiségének adatai szinkronizálva vannak a Commerce Headquarters alkalmazásból, ha a visszáru feldolgozása a pénztárban történik, de az RTS-hívás nem hajtható végre, a pénztár csatornaoldali visszáruadatok alapján ellenőrizheti, hogy az adott értékesítési sor esetében érvényes **Visszáruként elérhető** mennyiségeket.

Ha nem lehet RTS-hívásokat kezdeményezni, és a pénztár csatornaoldali adatokat használ a visszáru-ellenőrzéshez, egy figyelmeztető üzenet tájékoztatja a felhasználókat, hogy "offline" visszatérítést hoznak létre. Ebből következően tudják, hogy a pénztárban megjelenő **Visszáru elérhető** mennyiségei elavultak lehetnek, és már nem pontosak attól függően, hogy mikor történt meg utoljára a **Visszárumennyiségek frissítése** feladat feldolgozása és szinkronizálása a csatornával.

Egy vevő például legutóbb egy másik csatornában feldolgozta egy rendelési sor visszáruját, de az adatok még nem lettek szinkronizálva a csatorna-adatbázisokkal a **Visszárumennyiségek frissítése** feladat segítségével. A vevő ezután egy másik üzletbe megy, és megpróbálja újból visszaadni ugyanazt a cikket. Ebben az esetben, ha az üzlet nem tud a Commerce Headquarters alkalmazás felé RTS-hívást indítani, hogy valós idejű visszáru-adatokat kapjon, a pénztár lehetővé teszi a cikk ismételt visszavételét. A felhasználó azonban figyelmeztetést fog arról kapni, hogy a visszáru érvényesítésére használt információk elavultak lehetnek. A felhasználó által kapott üzenet csak egy figyelmeztető üzenet. Ez nem akadályozza meg, hogy a felhasználó folytassa a visszáru feldolgozását.

Ha a csatornaoldali információk valamilyen okból nem naprakészek, és az offline visszáru-feldolgozás olyan mennyiségre történik, amely meghaladja az **Elérhető visszáru** mennyiséget, akkor hiba jövet létre, amikor kimutatásfeladást futtat, hogy tranzakciót hozzon létre a Commerce központ alkalmazásban.

> [!NOTE]
> Ha be van az **Egyesített visszaküldés-feldolgozási élmény a pénztárban** funkció elérhetővé válnak a szerializált termék-visszaküldések érvényesítését támogató új választható funkciók. A további tudnivalókat lásd a [Sorozatszámmal szabályozott termékek visszaküldése a pénztárban (POS)](POS-serial-returns.md) részben.

## <a name="version-details"></a>Verzióadatok

Az alábbi lista tartalmazza a különböző összetevők minimális verziókövetelményét.
- Commerce Headquarters: 10.0.20-as verzió
- Commerce Scale Unit (STB): 9.30-as verzió
- Pénztár: 9.30-as verzió

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a>A megfelelő adószámítás engedélyezése a részleges mennyiséggel történő visszáru esetében

Ez a funkció biztosítja, hogy amikor egy rendelés visszáruja több számla igénybevételével történik, akkor az adók végső soron megegyezzenek az eredetileg felszámolt adó összegével.
1.  Nyissa meg a **Funkciókezelés** munkaterületet, és keresse meg a következőt: **A megfelelő adószámítás engedélyezése a részleges mennyiséggel történő visszáru esetében**.
2.  Válassza az **A megfelelő adószámítás engedélyezése a részleges mennyiséggel történő visszáru esetében** elemet, és kattintson az **Engedélyezés** lehetőségre.


## <a name="additional-resources"></a>További erőforrások

[Sorozatszámmal szabályozott termékek visszaküldése a pénztárban (POS)](POS-serial-returns.md)

[Korábban jóváhagyott és visszaigazolt tranzakciók csatolt visszatérítései](dev-itpro/linked-refunds.md)

[Visszáruk és visszatérítések irányelvének létrehozása és frissítése a csatornához](refund_policy_returns.md)

[A pénztár felhasználói felületének vizuális konfigurációja](pos-screen-layouts.md)
