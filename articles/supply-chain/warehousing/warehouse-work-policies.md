---
title: Munkairányelvek
description: Ez a témakör ismerteti a munkával kapcsolatos irányelvek beállítását.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 08c04caeace7b8ced40915ace1561d817426cba3
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429929"
---
# <a name="work-policies"></a>Munkairányelvek

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani a rendszert és a raktári alkalmazást úgy, hogy támogassák a munkairányelveket. Ez a funkció a beszerzési vagy átmozgatási rendelések fogadása, illetve a termelési folyamatok befejezése esetén a készlet gyors regisztrálására használható, eltárolási munka létrehozása nélkül. Ez a témakör általános tájékoztatást tartalmaz. Az azonosítótábla-beszerzéssel kapcsolatos részletes információk: [Azonosítótábla-bevételezés a raktári alkalmazás használatával](warehousing-mobile-device-app-license-plate-receiving.md).

A munkairányelvek azt vezérlik, hogy a gyártott cikk készként jelentésekor vagy a raktári alkalmazásba történő bevételezéskor történik-e a raktári munka létrehozása. Minden munkairányelvet úgy állíthat be, hogy meghatározza a feltételeket: a munkarendelés-típusokat és folyamatokat, a készlet helyét és a termékeket (ha van). Például egy beszerzési rendelést az *A0001* terméknél el kell fogadni a *RECV* helyen a *24*-es raktárban. Később a termék egy másik folyamatban lesz felhasználva a *RECV* helyen. Ebben az esetben munkairányelvet állíthat be, amellyel megakadályozhatja, hogy az eltárolási munka létrejöjjön, amikor egy dolgozó jelenti a beérkezett *A0001* terméket a *RECV* helyen.

> [!NOTE]
> - Ahhoz, hogy egy munkairányelv aktív legyen, legalább egy helyet meg kell határozni a **Munkairányelvek** lap **Készlethelyek** gyorslapján. 
> - Nem határozhatja meg ugyanazt a helyet több munkairányelvhez.
> - A mobileszköz menüelemek **Címkenyomtatás** lehetősége nem nyomtat azonosítótábla címkét munka létrehozása nélkül.

## <a name="activate-the-features-in-your-system"></a>A rendszer szolgáltatásainak aktiválása

Ha azt szeretné, hogy az ebben a témakörben ismertetett összes funkció elérhető legyen a rendszerben, kapcsolja be a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) következő két funkcióját:

- Azonosítótábla bevételezés fejlesztései
- Munkairányelv fejlesztései bejövő munkára vonatkozóan

## <a name="the-work-policies-page"></a>Munkairányelvek oldal

A munkairányelvek beállításához menjen a **Raktárkezelés \> Beállítás \> Munka \> Munkairányelvek** lehetőségre. Ezután minden Gyorslapon állítsa be a mezőket a következő alszakaszokban leírtaknak megfelelően.

### <a name="the-work-order-types-fasttab"></a>Munkarendelés típusai gyorslap

A **Munkarendelés típusa** gyorslapon adja hozzá az összes Munkarendelés-típust, valamint a kapcsolódó munkafolyamatokat, amelyekre a munkairányelv vonatkozik. A munkairányelvek a következő munkarendelés-típusokat és kapcsolódó munkafolyamatokat támogatják.

| Munkarendelés típusa | Munkafeldolgozás |
|---|---|
| Nyersanyag kitárolása| Minden kapcsolódó folyamat |
| Társ- és melléktermék betárolása | Minden kapcsolódó folyamat |
| Késztermékek betárolása | Minden kapcsolódó folyamat |
| Átmozgatási bevételezés | Azonosítótábla bevételezése (és eltárolása) |
| Beszerzési rendelések | <ul><li>Azonosítótábla bevételezése (és eltárolása)</li><li>Rakomány – cikk bevételezése (és eltárolása)</li><li>Beszerzésirendelés-sor bevételezése (és eltárolása)</li><li>Beszerzési rendelés – cikk bevételezése (és eltárolása)</li></ul> |

Ha egy munkairányelvet úgy szeretne beállítani, hogy ugyanazon Munkarendelés-típus több munkafolyamatára vonatkozzon, akkor mindegyik munkafolyamathoz külön sort adjon hozzá a rácsnál.

A rács minden sorához állítsa be a **Munkalétrehozási mód** mezőt a következő értékek valamelyikére:

- **Soha** – Ez a munkairányelv megakadályozza, hogy raktárkezelési munka jöjjön létre a kiválasztott munkarendelési típushoz és a hozzá kapcsolódó munkafolyamathoz.
- **Áttárolás** – A munkairányelv létre fogja hozni az áttárolási munkát az **Áttárolási irányelv neve** mezőben kiválasztott irányelv használatával.

### <a name="the-inventory-locations-fasttab"></a>A készlet helyei gyorslap

A **Készlethelyek** gyorslapon adja meg az összes olyan helyet, ahol ezt a munkairányelvet alkalmazni szeretné. Ha nincs hely társítva a munkairányelvhez, a munkairányelv nem fog vonatkozni semmilyen folyamatra.

Nem határozhatja meg ugyanazt a helyet több munkairányelvhez.

Használhat olyan raktári helyet, amelyet a rendszer hozzárendelt egy helyprofilhoz, ahol az **Azonosítótábla követésének használata** lehetőség nincs bekapcsolva. Ebben az esetben a dolgozók közvetlenül az aktuális készletet fogják regisztrálni.

### <a name="the-products-fasttab"></a>A termékek gyorslapja

A **Termékek** lapon állítsa be a **Termék kiválasztása** mezőt, így vezérelheti, hogy melyik termékekre vonatkozzon az irányelv:

- **Mind** – Az irányelvet minden termékre alkalmazni kell.
- **Kiválasztott** – Az irányelv csak a rácsban felsorolt termékekre vonatkozik. A **Termékek** gyorslap eszköztárával hozzáadhat termékeket a rácshoz, illetve eltávolíthatja őket a rácsból.

## <a name="default-and-custom-to-locations"></a>Alapértelmezett és egyéni „fogadó” helyek

> [!NOTE]
> Ha azt szeretné, hogy a jelen szakaszban ismertetett funkciók elérhetők legyenek a rendszerben, akkor be kell kapcsolnia az *Azonosítótábla fogadásával kapcsolatos fejlesztések* és *Munkairányelvek fejlesztése a bejövő munkához* funkciót a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségben.

Korábban a rendszer csak az egyes raktárakhoz megadott alapértelmezett helyeken támogatta a fogadást. A következő munkalétrehozási folyamatokat használó mobileszköz menüelemek azonban most az **Alapértelmezett adatok használata** lehetőséget nyújtják. Ez a beállítás lehetővé teszi, hogy egy vagy több menüelemhez rendeljen hozzá egyéni „fogadó” helyet. (Ez a beállítás már elérhető volt más típusú menüelemekhez.)

- Azonosítótábla bevételezése (és eltárolása)
- Rakomány – cikk bevételezése (és eltárolása)
- Beszerzésirendelés-sor bevételezése (és eltárolása)
- Beszerzési rendelés – cikk bevételezése (és eltárolása)

A menüelem **Fogadó hely** beállítása felülírja a raktár alapértelmezett bevételezési helyét minden olyan rendelés esetében, amelyet az adott menüelem dolgoz fel.

A mobileszközök menüelemének beállításához a következő lépések végrehajtásával támogathatja az egyéni helyen történő fogadást.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. Válassza ki vagy hozzon létre egy olyan menüelemet, amely a szakaszban korábban felsorolt munkafolyamatok egyikét használja.
1. Az **Általános** gyorslapon állítsa a **Alapértelmezett adatok használata** beállítást **Igen** értékre.
1. A műveleti ablakban válassza ki az **Alapértelmezett adatok** elemet.
1. Az **Alapértelmezett adatok** oldalon állítsa be a következő értékeket:

    - **Alapértelmezett adatok mező:** Állítsa be ezt a mezőt *Fogadó helynek*.
    - **Raktár:** Válassza ki a menüelemhez használandó célhelyet.
    - **Hely:** Ez a mező felsorolja a kiválasztott raktárnál elérhető összes hely azonosítóját. Ennek a mezőnek a beállítása azonban ténylegesen nem bír semmilyen hatással. Ezért akár üresen is hagyhatja. Mindazonáltal a listát használatja az **Előre megadott érték** mezőben kötelezően megadandó azonosító jóváhagyására.
    - **Előre megadott érték:** Adja meg a bevételezési hely erre a menüelemre vonatkozó helyazonosítóját.

> [!TIP]
> Egy munkairányelv csak akkor alkalmazható, ha az összes bevételezési hely szerepel a megfelelő munkairányelv-beállításban. Ennek a követelménynek az alkalmazása attól függetlenül megtörténik, hogy alapértelmezett raktári bevételezési helyet, vagy egyéni „fogadó” helyet használ-e.

## <a name="example-scenario-warehouse-receiving"></a>Példaforgatókönyv: raktári bevételezés

A *Beszerzési rendelési cikk bevételezési (és eltárolási)* folyamata által fogadott összes terméket regisztrálni kell az *FL-001* helyen, és elérhetőnek kell lenniük a *24.* raktárban. A munkát azonban nem szabad létrehozni. Azokat a termékeket, amelyeket bármilyen más folyamat fogad (más mobileszköz menüelemek használatával), regisztrálni kell az alapértelmezett raktár bevételezési helyén (*RECV*), és a munkát a szokásos módon kell létrehozni. (Ez a forgatókönyv nem jeleníti meg az alapértelmezett bevételezési beállításokat.)

Ennek a forgatókönyvnek a következő elemekre van szüksége:

- A *Beszerzési rendelési cikk bevételezése (és eltárolása)* folyamat munkairányelve az *FL-001* helyen taálható az összes termék esetében
- Alapértelmezett adatokat tartalmazó mobileszköz-menüelem, amely a **Záró hely** mezőt a *FL-001* értékre állítja

### <a name="prerequisites"></a>Előfeltételek

Ha azt szeretné, hogy a jelen forgatókönyvben ismertetett funkciók elérhetők legyenek a rendszerben, akkor be kell kapcsolnia az *Azonosítótábla fogadásával kapcsolatos fejlesztések* és *Munkairányelvek fejlesztése a bejövő munkához* funkciót a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségben.

Ez a forgatókönyv a standard bemutatóadatokat használja. Ezért, ha a munkát az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszerben kell dolgoznia, amelynél a szokásos demóadatok telepítve vannak. Ezenkívül ki kell választania az **USMF** jogi személyt.

### <a name="set-up-a-work-policy"></a>Munkairányelv beállítása

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkairányelvek** pontra.
1. Válassza az **Új** lehetőséget.
1. A **Munkairányelv neve** mezőben adja meg a *Nem beszerzési cikk eltárolási munkája* lehetőséget.
1. Válassza a **Mentés** lehetőséget.
1. A **Munkarendelés típusa** gyorslapon válassza a **Hozzáadás** lehetőséget ha sort szeretne hozzáadni egy rácshoz, majd állítsa be a következő értékeket az új sorhoz:

    - **Munkarendelés típusa:** *Beszerzési rendelések*
    - **Munkafolyamat:** *Beszerzési rendelési cikk bevételezése (és eltárolása)*
    - **Munkalétrehozási mód:** *Soha*
    - **Áttárolási irányelv neve:** Hagyja üresen ezt a mezőt.

1. A **Készlethelyek** gyorslapon válassza a **Hozzáadás** lehetőséget ha sort szeretne hozzáadni egy rácshoz, majd állítsa be a következő értékeket az új sorhoz:

    - **Raktár:** *24*
    - **Hely:** *FL-001*

1. A **Termékek** gyorslapon állítsa a **Termék kiválasztása** mezőt *Mind* értékre.
1. Válassza a **Mentés** lehetőséget.

### <a name="set-up-a-mobile-device-menu-item-to-change-the-receiving-location"></a>Mobileszköz-menüelem beállítása a bevételező hely módosításához

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A bal oldali ablaktáblán válassza ki a meglévő **Beszerzés fogadása** menüelemet.
1. Az **Általános** gyorslapon állítsa a **Alapértelmezett adatok használata** beállítást *Igen* értékre.
1. Válassza a **Mentés** lehetőséget.
1. A műveleti ablakban válassza ki az **Alapértelmezett adatok** elemet.
1. Az **Alapértelmezett adatok** lapon, a Művelet ablaktáblán válassza az **Új** lehetőséget ha sort szeretne hozzáadni egy rácshoz, majd állítsa be a következő értékeket az új sorhoz:

    - **Alapértelmezett adatok mező:** *Záró hely*
    - **Raktár:** *24*
    - **Hely:** Hagyja üresen ezt a mezőt.
    - **Előre megadott érték:** *FL-001*

1. Válassza a **Mentés** lehetőséget.

### <a name="receive-a-purchase-order-without-creating-work"></a>Beszerzési rendelés fogadása munka létrehozása nélkül

A jelen szakaszban szereplő példa bemutatja, hogyan lehet beszerzési rendelést fogadni munkavégzés nélkül olyan helyen, amely eltér a raktárhoz alapértelmezetten beállított bevételezési helytől. Ez a példa a korábban Ön által létrehozott munkairányelvet és mobileszközelemet használja.

#### <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

1. Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.
1. Válassza az **Új** lehetőséget.
1. Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Szállítói számla:** *US-101*
    - **Telephely:** *2*
    - **Raktár:** *24*

1. Válassza az **OK** gombot a párbeszédpanel bezárásához, és egy új beszerzési rendelés megnyitásához.
1. A **Beszerzési rendeléssorok** gyorslapon állítsa be a következő értékeket az üres sorhoz:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *1*

1. Válassza a **Mentés** lehetőséget.
1. Jegyezze fel a beszerzési rendelés számát.

#### <a name="receive-a-purchase-order"></a>Beszerzési rendelés fogadása

1. Jelentkezzen be a mobileszközön a *24*-es raktárhoz. Felhasználói azonosító: *24*, jelszó: *1*.
1. Válassza ki a **Bejövő** lehetőséget.
1. Válassza a **Bevételezés fogadása** lehetőséget. A **Hely** mezőt *FL-001* értékre kell állítani.
1. Az előző eljárásban létrehozott beszerzési rendeléshez tartozó beszerzési rendelés számának megadása.
1. Adja meg a *A0001* értéket a **Cikkszám** mezőben.
1. Válassza ki az **OK** lehetőséget.
1. Írja be a *1* értéket a **Mennyiség** mezőbe.
1. Válassza ki az **OK** lehetőséget.

A beszerzési rendelés fogadva, de nincs hozzárendelve munka. Az aktuális készlet frissítve lett, és a *A0001* cikk *1* mennyisége elérhető az *FL-001* helyen.

## <a name="example-scenario-manufacturing"></a>Példaforgatókönyv: gyártás

A következő példában két termelési rendelés szerepel: a *PRD-001* és a *PRD-002*. A *PRD-001* termelési rendeléshez egy *Összeszerelés* nevű művelet tartozik, ahol az *SC1* termék a jelentés szerint elkészült leszállításra a *001* helyre. A *PRD-002* termelési rendeléshez egy *Festés* nevű művelet tartozik, ami felhasználja az *SC1* terméket a *001* helyről. A *PRD-002* termelési rendelés *RM1* nyersanyagot is felhasznál a *001* helyről. A Nyersanyag *RM1* tárolása a *BULK-001* raktári helyszínen történik, és kitárolásra kerül a *001* helyre a nyersanyag-kitárolási raktári munka segítségével. A kitárolási munka akkor jön létre, amikor a *PRD-002* termelés kiadásra kerül.

[![Raktári munkairányelvek](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)

Amikor raktári munkairányelv konfigurálását tervezi ehhez az esethez, vegye figyelembe a következő információkat:

- A késztermékek betárolására vonatkozó raktári munkára nincs szükség, ha az *SC1* terméket úgy szerepelteti a jelentésben, mint amely a *PRD-001* termelési rendelésből elkészült, és a *001* helyre került. Ennek oka, hogy a *PRD-002* termelési rendelés *Festés* művelete *SC1* terméket használ fel ugyanazon a helyen.
- A nyersanyag kitárolására vonatkozó raktári munkára szükség van, hogy az *RM1* nyersanyagot át lehessen helyezni a *BULK-001* raktári helyszínről a *001* helyre.

Íme egy példa a munka-irányelvre, amelyet be lehet beállítani ezen szempontok alapján:

- **Munkairányelv neve:** *Nem eltárolási munka*
- **Munkarendelés típusok:** *Késztermékek eltárolása* és *Társtermék és melléktermékek eltárolása*
- **Készlethelyek:** *51*-es raktár és *001*-es hely
- **Termékek:** *SC1*

Az alábbi példaforgatókönyv lépésről lépésre ismerteti, hogyan lehet a raktári munkairányelvet beállítani ehhez a forgatókönyvhöz.

## <a name="example-scenario-report-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Példaforgatókönyv: Készként jelentés egy olyan helyre, amelynek szabályozása nem azonosítótáblán alapul

Az alábbi példaforgatókönyv azt mutatja meg, hogyan lehet egy jelentésben egy termelési rendelést készként szerepeltetni, ahol a leszállítás egy olyan helyre történik, amelynek szabályozása nem azonosítótáblán alapul.

Ez a forgatókönyv a standard bemutatóadatokat használja. Ezért, ha a munkát az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszerben kell dolgoznia, amelynél a szokásos demóadatok telepítve vannak. Ezenkívül ki kell választania az **USMF** jogi személyt.

### <a name="set-up-a-warehouse-work-policy"></a>Raktári munka-irányelv beállítása

A raktárkezelési folyamatok nem mindig tartalmaznak raktári munkát. A munka irányelveinek használatával megakadályozhatja a nyersanyag kitárolására és a befejezett termékek betárolására vonatkozó munka létrehozását egy termékkészletre vonatkozóan az adott helyeken.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkairányelvek** pontra.
1. Válassza az **Új** lehetőséget.
1. A **Munkairányelv neve** mezőben adja meg a *Nem eltárolási munka* lehetőséget.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A **Munkarendelés típusa** gyorslapon válassza a **Hozzáadás** lehetőséget ha sort szeretne hozzáadni egy rácshoz, majd állítsa be a következő értékeket az új sorhoz:

    - **Munkarendelés típusa:** *Késztermékek betárolása*
    - **Munkafolyamat:** *Az összes kapcsolódó munkafolyamat*
    - **Munkalétrehozási mód:** *Soha*
    - **Áttárolási irányelv neve:** Hagyja üresen ezt a mezőt.

1. Válassza a **Hozzáadás** lehetőséget újra, ha egy második sort szeretne hozzáadni egy rácshoz, majd állítsa be a következő értékeket az új sorhoz:

    - **Munkarendelés típusa:** *Társtermék és melléktermék betárolása*
    - **Munkafolyamat:** *Az összes kapcsolódó munkafolyamat*
    - **Munkalétrehozási mód:** *Soha*
    - **Áttárolási irányelv neve:** Hagyja üresen ezt a mezőt.

1. A **Készlethelyek** gyorslapon válassza a **Hozzáadás** lehetőséget ha sort szeretne hozzáadni egy rácshoz, majd állítsa be a következő értékeket az új sorhoz:

    - **Raktár:** *51*
    - **Hely:** *001*

1. A **Termékek** gyorslapon állítsa a **Termék kiválasztása** mezőt *Kiválasztott* értékre.
1. A **Termékek** gyorslapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.
1. Az új sorban állítsa a **Cikkszám** mezőt az *L0101* értékre.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="set-up-an-output-location"></a>A kimeneti helyek beállítása

1. Menjen a **Szervezet felügyelete \> Erőforrások \> Erőforráscsoportok** részhez.
1. A bal oldali ablaktáblában válassza az **5102**-es erőforráscsoportot.
1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Kimeneti raktár:** *51*
    - **Kimeneti hely:** *001*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

> [!NOTE]
> A *001* hely nem egy azonosítótáblás szabályozású hely. A nem azonosítótábla vezérlésű kimeneti helyet csak akkor állíthatja be, ha a megfelelő munkairányelveket létrehozták a helyre vonatkozóan.

### <a name="create-a-production-order-and-report-it-as-finished"></a>A Termelési jelentés létrehozása és készként történő jelentése.

1. Ugrás a **Gyártásvezérlés \> Termelési rendelések \> Minden termelési rendelés** lehetőségre.
1. A műveleti ablaktáblán válassza ki az **Új gyártási rendelés** elemet.
1. A **Gyártási rendelés létrehozása** párbeszédpanelen állítsa a **Cikkszám** mezőt *L0101* értéket.
1. Válassza a **Létrehozás** gombot a rendelés létrehozásához és a párbeszédpanel bezárásához.

    A program új termelési rendelést ad hozzá a rácshoz az **Összes termelési rendelés** oldalon.

    Hagyja kiválasztva az új termelési rendelést.

1. A Műveleti ablaktáblán a **Termelési rendelés** lapon a **Folyamat** csoportban válassza a **Becslés** lehetőséget.
1. A **Becslés** párbeszédpanelen olvassa el a becslést, majd az **OK** gombra kattintva zárja be a párbeszédpanelt.
1. A Műveleti ablaktáblán a **Termelési rendelés** lapon a **Folyamat** csoportban válassza a **Start** lehetőséget.
1. A **Start** párbeszédpanel **Általános** lapján állítsa az **Automatikus anyagjegyzék-felhasználás** mezőt *Soha* értékre.
1. Az **OK** gombra kattintva mentse a beállítást, és zárja be a párbeszédpanelt.
1. A Műveleti ablaktáblán a **Termelési rendelés** lapon a **Folyamat** csoportban válassza a **Készként jelentés** lehetőséget.
1. A **Készként jelentés** párbeszédpanel **Általános** lapján állítsa a **Hiba elfogadása** beállítást *Igen* értékre.
1. Az **OK** gombra kattintva mentse a beállítást, és zárja be a párbeszédpanelt.
1. A Művelet ablaktábla **Raktár** lapjának **Általános** csoportjában válassza a **Munka részletei** elemet.

Amikor a termelési rendelést készként jelentik, a rendszer nem hoz létre munkát eltárolásra. Ennek akkor történik, ha a munkairányelveket úgy határozzák meg, hogy megakadályozza a munka létrehozását, amikor a rendszer készként jelenti az *L0101* terméket a *001* helyen.

## <a name="more-information"></a>További információ

A mobileszköz-menüelemek beállításával kapcsolatos további tudnivalókat lásd: [Mobileszközök beállítása raktári munkához](configure-mobile-devices-warehouse.md).

Az azonosítótábla-beszerzéssel és a munkairányelvekkel kapcsolatos részletes információk: [Azonosítótábla-bevételezés a raktári alkalmazás használatával](warehousing-mobile-device-app-license-plate-receiving.md).

További információ a bejövő rakományok kezeléséről: [Beszerzési rendelések bejövő rakományának kezelése a raktárban](inbound-load-handling.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]