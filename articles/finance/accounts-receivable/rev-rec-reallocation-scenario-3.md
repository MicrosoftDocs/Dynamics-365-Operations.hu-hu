---
title: Bevételelszámolás újbóli felosztása – 3. eset
description: Ebben a témakörben az újbóli felosztásnak azt az esetét mutatjuk be, amikor egy meglévő, számlázott értékesítési rendeléshez új sort adnak hozzá. Amikor új cikket ad hozzá egy szerződéshez, a cikket hozzáadhatja egy új vagy egy meglévő értékesítési rendeléshez.
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
ms.openlocfilehash: 4242be761ed170155b70211d99eb5018fb254071
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356173"
---
# <a name="revenue-recognition-reallocation--scenario-3"></a>Bevételelszámolás újbóli felosztása – 3. eset

[!include [banner](../includes/banner.md)]

Ebben a témakörben az újbóli felosztásnak azt az esetét mutatjuk be, amikor egy meglévő, számlázott értékesítési rendeléshez új sort adnak hozzá. Amikor új cikket ad hozzá egy szerződéshez, a cikket hozzáadhatja egy új vagy egy meglévő értékesítési rendeléshez. Ez az eset azt is bemutatja, hogy mi történik akkor, ha a rendszer az újbóli felosztás miatt frissíti a kinnlevőségeket.

Ebben az esetben a **Számlajavítások feladása a Kinnlevőségekbe** lehetőség az **Igen** értékre van állítva. Ez a beállítás a **Bevételelszámolás** lapon, a **Főkönyvi paraméterek** oldalon található. (**Bevételelszámolás \> Beállítás \> Főkönyvi paraméterek**).

[![Számlajavítások feladása a Kinnlevőségekbe beállítva az Igen értékre.](./media/25_rev-rec-scenarios.png)](./media/25_rev-rec-scenarios.png)

Létrehoznak egy értékesítési rendelt az US\_SI\_0003 nevű vevőhöz. A vevő vásárol egy laptopot (cikkszám: S0012) és hozzá egy támogatási csomagot (cikkszám: S0008, „Sustained Engineering Service” (Folyamatos mérnöki szolgáltatás)). A laptophoz tartozó bevételt azonnal elszámolják. A rendszer a támogatási csomagra vonatkozó bevételt késlelteti, és 12 hónapra lebontva számolja el, a szerződés dátumtartományának megfelelően.

[![Az értékesítési rendelés sorai a laptophoz és a támogatási csomaghoz.](./media/26_rev-rec-scenarios.png)](./media/26_rev-rec-scenarios.png)

Az értékesítési rendelést visszaigazolták. Mivel mindkét cikk esetében be van állítva a bevételi ár felosztása, a rendszer az értékesítési rendelés visszaigazolásakor kiszámítja a bevételi árat. A **Bevételi ár felosztása** oldalon megtekintheti a rendszer által könyvelt bevételt (a Műveletpanel **Értékesítési rendelés** oldalán, a **Kezelés** lapon, a **Bevételelszámolás** csoportban válassza a **Bevételi ár felosztása** lehetőséget). A laptopra vonatkozó 1008,01 $ bevételt a rendszer feladja a Bevétel számlára. A támogatási csomagra vonatkozó 190,99 $ bevételt a rendszer feladja a Halasztott bevétel számlára. A bevételi árak összegének meg kell egyeznie a bevételi ár felosztásának rögzítésére beállított sorok összegével (1199,00 $).

[![Bevételi ár felosztása oldal.](./media/27_rev-rec-scenarios.png)](./media/27_rev-rec-scenarios.png)

Az értékesítési rendelést hiánytalanul kiszámlázzák. A következő illusztráción a számlához feladott könyvelési tétel látható.

[![A teljesen kiszámlázott értékesítési rendelés könyvelési tétele.](./media/28_rev-rec-scenarios.png)](./media/28_rev-rec-scenarios.png)

A program a bevételelszámolási ütemezést is létrehozza. Eltelik két hónap, amelyeknél a rendszer elszámolja a támogatási csomagból származó bevételt.

[![A Bevételelszámolási ütemezés oldal két hónap elteltével.](./media/29_rev-rec-scenarios.png)](./media/29_rev-rec-scenarios.png)

Ezen a ponton a vevő úgy dönt, hogy telepítési szolgáltatásokat (cikkszám: S0001) is vásárol. A cikket hozzáadják a meglévő értékesítési rendeléshez. A vevőnek jóvá kell hagynia, hogy módosítani szeretné a már teljesen kiszámlázott értékesítési rendelést, és ki kell választania az **Igen** lehetőséget.

[![Az értékesítési rendelés a telepítési szolgáltatások sorának hozzáadása után.](./media/30_rev-rec-scenarios.png)](./media/30_rev-rec-scenarios.png)

Ha ez az új cikk a vevő szerződését érintő egyetlen módosítás, most már le lehet futtatni az újbóli felosztás folyamatát. Az értékesítési rendelésnél válassza az **Ár újbóli felosztása új rendelési sorokba** lehetőséget az **Ár újbóli felosztása új rendelési sorokba** oldal megnyitásához. Válassza ki az értékesítési rendelés összes értékesítésirendelés-sorát, majd válassza az **Újbóli felosztás frissítése** lehetőséget. Az **Újból felosztott összeg** oszlopban megjelenik az egyes értékesítésirendelés-sorok új bevételi ára.

[![Új bevételi árak az Ár újbóli felosztása új rendelési sorokba oldalon.](./media/31_rev-rec-scenarios.png)](./media/31_rev-rec-scenarios.png)

Ezután válassza a **Várható bizonylat** lehetőséget a könyvelési tételek megtekintéséhez. Mivel a **Számlajavítások feladása a Kinnlevőségekbe** lehetőség az **Igen** értékre van állítva a **Főkönyvi paraméterek** oldalon, ezeket a könyvelési tételeket a rendszer a hiteldokumentumon keresztül adja fel a főkönyvbe, és a kinnlevőségek között létrejön egy új számla.

[![Könyvelési tételek a Várható bizonylat oldalon.](./media/32_rev-rec-scenarios.png)](./media/32_rev-rec-scenarios.png)

A **Várható bizonylat** oldalon az utolsó négy sor sztornírozza a feladott számláról származó eredeti könyvelési tételt. Az első öt sorban szerepelnek a számlához feladott új könyvelési tételek. Fontos tudni, hogy az új számla nem jelenik meg a vevő számára. Az újbóli felosztás után a vevő még további 1276,94 $ összeggel tartozik, ezt az összeget egy új könyvelési tétellel fel kell adni a kinnlevőségekbe. A beszámított adó és a bevétel vagy a késleltetett bevétel összege: 995,83 $ + 188,69 $ + 77,94 $ = 1262,46 $. A bevétel vagy a késleltetett bevétel összege megváltozott az újbóli felosztás miatt. A különbséget (–14,48 $) fel kell adni a Részleges számlabevétel elszámolási számlára. Amikor az értékesítési rendeléshez hozzáadott új cikk számláját is feladják, a rendszer törli ezt az egyenleget.

Az újbóli felosztás befejezéséhez válassza a **Feldolgozás** lehetőséget. Meg kell adni a feladási dátumot. Ha befejeződött az újbóli felosztás, a **Bevételi ár felosztása** oldalon láthatja a három cikk árának újbóli felosztását.

[![Az ár újbóli felosztása a három cikk esetében a Bevételi ár felosztása oldalon.](./media/33_rev-rec-scenarios.png)](./media/33_rev-rec-scenarios.png)

A bevételelszámolási ütemezés az új bevétel újrafelosztási ára alapján frissült. Az értékesítési rendelésből nyissa meg a **Bevételelszámolási ütemezés** oldalt. Korábban 13 sor tartozott az S0008-as cikkhez (ehhez a cikkhez 12 hónapos ütemezést adtak meg). Jelenleg 39 sor van: az eredeti ütemezés 13 sora, 13 sztornírozott ütemezési sor, valamint az új bevételi áron alapuló 13 sor.

[![A Bevételelszámolási ütemezés frissített oldala 39 sorral az S0008 cikkhez.](./media/34_rev-rec-scenarios.png)](./media/34_rev-rec-scenarios.png)

Ha a **Bizonylat** lehetőséget választja, a számlanapló az eredeti könyvelési tételt jeleníti meg. A sztornírozó tétel és az értékesítési rendelésből származó új könyvelési tétel megtekintéséhez válassza a **Bevételkiigazítások** lehetőséget a Műveletpanelen, majd válassza a **Bizonylat** lehetőséget.

Ezután nyissa meg az **Összes vevő** oldalt (**Kinnlevőségek \> Vevők \> Összes vevő**), válassza ki az **US\_SI\_0003** vevőt, majd válassza a **Tranzakciók** lehetőséget. A **Vevői tranzakciók** oldalon látható az eredeti számla (000006), a sztornírozási dokumentum (000006-1), valamint az új számla (000006-2). A rendszer összeveti az eredeti számlát és a sztornírozási dokumentumot, így kijön a nullás egyenleg. A főkönyvre gyakorolt hatás megtekintéséhez ellenőrizze az egyes dokumentumokhoz tartozó bizonylatokat.

[![Az eredeti számla, a sztornírozási dokumentum és az új számla a Vevői tranzakciók oldalon.](./media/35_rev-rec-scenarios.png)](./media/35_rev-rec-scenarios.png)

A rendszer ismét kiszámlázza a hozzáadott cikk értékesítési rendelését. A vevőnek elküldött számla végösszege a következő: 300,00 $ + 19,50 $ adó = 319,50 $. A következő illusztráció a feladott könyvelési tételt mutatja.

[![Bizonylattranzakciók oldal a feladott könyvelési tétellel.](./media/36_rev-rec-scenarios.png)](./media/36_rev-rec-scenarios.png)

Mivel a bevétel és az értékesítés összege nagyobb 319,50 $-nél, a rendszer feladja a különbözetet, ami 14,48 $. Ez az összeg törli a Részleges számlabevétel elszámolási számla egyenlegét. A rendszer az újbóli felosztás után feladott új könyvelési tétellel frissítette az egyenleget.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]