---
title: Bevételelszámolás újbóli felosztása – 4. eset
description: Ebben a témakörben az újbóli felosztásnak azt az esetét mutatjuk be, amikor egy meglévő, részben kiszámlázott értékesítési rendelésből törölnek egy sort. Nem számít, hogy a sort eltávolítják az értékesítési rendelésből vagy Érvénytelenítve állapotra állítják, az eredmény ugyanaz lesz.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9b9aada2c110ea3b7e70157e6edce9647bbfd28fe307654e10f6d38585090563
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758945"
---
# <a name="revenue-recognition-reallocation--scenario-4"></a>Bevételelszámolás újbóli felosztása – 4. eset

[!include [banner](../includes/banner.md)]

Ebben a témakörben az újbóli felosztásnak azt az esetét mutatjuk be, amikor egy meglévő, részben kiszámlázott értékesítési rendelésből törölnek egy sort. Nem számít, hogy a sort eltávolítják az értékesítési rendelésből vagy Érvénytelenítve állapotra állítják, az eredmény ugyanaz lesz.

Ennél az esetnél a **Számlajavítások feladása a Kinnlevőségekbe** beállítás a **Nem** értékre van állítva. Ez a beállítás a **Bevételelszámolás** lapon, a **Főkönyvi paraméterek** oldalon található. (**Bevételelszámolás \> Beállítás \> Főkönyvi paraméterek**).

[![Számlajavítások feladása a Kinnlevőségekbe beállítva a Nem értékre.](./media/37_rev-rec-scenarios.png)](./media/37_rev-rec-scenarios.png)

Létrehoznak egy értékesítési rendelt az US\_SI\_0003 nevű vevőhöz. A vevő vásárol egy laptopot (cikkszám: S0012), telepítési szolgáltatásokat (cikkszám: S0001) és egy támogatási csomagot a laptophoz (cikkszám: S0008, „Sustained Engineering Service” (Folyamatos mérnöki szolgáltatás)). A laptophoz és a telepítési szolgáltatásokhoz kapcsolódó bevételt azonnal elszámolják. A rendszer a támogatási csomagra vonatkozó bevételt késlelteti, és 12 hónapra lebontva számolja el, a szerződés dátumtartományának megfelelően.

[![Az értékesítési rendelés sorai a laptophoz, a telepítési szolgáltatásokhoz és a támogatási csomaghoz.](./media/38_rev-rec-scenarios.png)](./media/38_rev-rec-scenarios.png)

Az értékesítési rendelést visszaigazolták. Mivel mindhárom cikk esetében be van állítva a bevételi ár felosztása, a rendszer az értékesítési rendelés visszaigazolásakor kiszámítja a bevételi árat. A **Bevételi ár felosztása** oldalon megtekintheti a rendszer által könyvelt bevételt (a Műveletpanel **Értékesítési rendelés** oldalán, a **Kezelés** lapon, a **Bevételelszámolás** csoportban válassza a **Bevételi ár felosztása** lehetőséget). A laptopra vonatkozó 995,84 $ bevételt a rendszer feladja a Bevétel számlára. A telepítési szolgáltatásokra vonatkozó 314,47 $ összegű bevétel a Bevétel számlára kerül. A támogatási csomagra vonatkozó 188,69 $ bevételt a rendszer feladja a Halasztott bevétel számlára. A bevételi árak összegének meg kell egyeznie a bevételi ár felosztásának rögzítésére beállított sorok összegével (1499,00 $).

[![Bevételi ár felosztása oldal.](./media/39_rev-rec-scenarios.png)](./media/39_rev-rec-scenarios.png)

A vevőnek kiszámlázzák a laptop és a támogatási csomag díját, de a telepítési szolgáltatásokat nem. A következő illusztráción a számlához feladott könyvelési tétel látható.

[![A kiszámlázott értékesítési rendelés könyvelési tétele.](./media/40_rev-rec-scenarios.png)](./media/40_rev-rec-scenarios.png)

A könyvelési tétel feladja az 1276,94 $ értéket a kinnlevőségekbe. Mivel azonban ez egy részleges számla, a bevétel/késleltetett bevétel plusz az adó összege nem egyezik a kinnlevőségekben szereplő összeggel. A különbséget (–14,47 $) fel kell adni a Részleges számlabevétel elszámolási számlára.

A program a bevételelszámolási ütemezést is létrehozza.

[![A részleges számla Bevételelszámolási ütemezés oldala.](./media/41_rev-rec-scenarios.png)](./media/41_rev-rec-scenarios.png)

A vevő később úgy dönt, hogy mégsem vásárolja meg a telepítési szolgáltatásokat. Ezért ezt a sort eltávolítják az értékesítési rendelésből. Ne feledje, hogy az értékesítési rendelést nem lehet ismét megerősíteni, mivel csak a kiszámlázott sorok maradnak meg benne.

[![Az értékesítési rendelés a telepítési szolgáltatások sorának eltávolítása után.](./media/42_rev-rec-scenarios.png)](./media/42_rev-rec-scenarios.png)

Az értékesítési rendelést nem lehet megerősíteni, de újra fel lehet osztani. Az értékesítési rendelésnél válassza az **Ár újbóli felosztása új rendelési sorokba** lehetőséget az **Ár újbóli felosztása új rendelési sorokba** oldal megnyitásához. Válassza ki az értékesítési rendelés két fennmaradó sorát, majd válassza az **Újbóli felosztás frissítése** lehetőséget. Az **Újból felosztott összeg** oszlopban megjelenik az egyes fennmaradó értékesítésirendelés-sorok új bevételi ára.

[![Új bevételi árak az Ár újbóli felosztása új rendelési sorokba oldalon.](./media/43_rev-rec-scenarios.png)](./media/43_rev-rec-scenarios.png)

Ezután válassza a **Várható bizonylat** lehetőséget a könyvelési tételek megtekintéséhez.

[![Könyvelési tételek a Várható bizonylat oldalon.](./media/44_rev-rec-scenarios.png)](./media/44_rev-rec-scenarios.png)

A **Várható bizonylat** oldalon az utolsó öt sor sztornírozza a feladott számláról származó eredeti könyvelési tételt. Az első négy sorban szerepelnek a számlához feladott új könyvelési tételek. Fontos tudni, hogy az új számla nem jelenik meg a vevő számára. Az újbóli felosztás után a vevő még további 1276,94 $ összeggel tartozik, ezt az összeget egy új könyvelési tétellel fel kell adni a kinnlevőségekbe. Az új bevétel/halasztott bevétel és az adó összege: 1276,96 $. Így semmit nem kell feladni a Részleges számlabevétel elszámolási számlára.

Az újbóli felosztás befejezéséhez válassza a **Feldolgozás** lehetőséget. Meg kell adni a feladási dátumot. Ha befejeződött az újbóli felosztás, a **Bevételi ár felosztása** oldalon láthatja a két fennmaradó cikk árának újbóli felosztását.

[![Az ár újbóli felosztása a fennmaradó cikkek esetében a Bevételi ár felosztása oldalon.](./media/45_rev-rec-scenarios.png)](./media/45_rev-rec-scenarios.png)

A bevételelszámolási ütemezés az új bevétel újrafelosztási ára alapján frissült. Az értékesítési rendelésből nyissa meg a **Bevételelszámolási ütemezés** oldalt. Korábban 13 sor tartozott az S0008-as cikkhez (ehhez a cikkhez 12 hónapos ütemezést adtak meg). Jelenleg 39 sor van: az eredeti ütemezés 13 sora, 13 sztornírozott ütemezési sor, valamint az új bevételi áron alapuló 13 sor.

[![A Bevételelszámolási ütemezés frissített oldala 39 sorral az S0008 cikkhez.](./media/46_rev-rec-scenarios.png)](./media/46_rev-rec-scenarios.png)

Ha a **Bizonylat** lehetőséget választja, a számlanapló az eredeti könyvelési tételt jeleníti meg. A sztornírozó tétel és az értékesítési rendelésből származó új könyvelési tétel megtekintéséhez válassza a **Bevételkiigazítások** lehetőséget a Műveletpanelen, majd válassza a **Bizonylat** lehetőséget.

Ezután nyissa meg az **Összes vevő** oldalt (**Kinnlevőségek \> Vevők \> Összes vevő**), válassza ki az **US\_SI\_0003** vevőt, majd válassza a **Tranzakciók** lehetőséget. A **Vevői tranzakciók** oldalon csak az eredeti számla (000008) és az eredeti könyvelési tétel szerepel. Mivel a **Számlajavítások feladása a Kinnlevőségekbe** lehetőség a **Nem** értékre van állítva a **Főkönyvi paraméterek** oldalon, csak a főkönyv frissül. Ezért nem jelennek meg a sztornírozó és a frissített könyvelési tételek. Figyelje meg, hogy megjelennek a [3. esetnél](rev-rec-reallocation-scenario-3.md) létrehozott bevételkorrekciós tranzakciók.

[![Az eredeti könyvelési tétel a Vevői tranzakciók oldalon.](./media/47_rev-rec-scenarios.png)](./media/47_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]