---
title: Bevételelszámolás újbóli felosztása – 2. eset
description: Ebben a cikkben az újbóli felosztásnak azt az esetét mutatjuk be, amelyben két értékesítési rendelést adnak meg, majd a vevő az első értékesítési rendelés számlázása után hozzáad egy további cikket a szerződéshez. Amikor új cikket ad hozzá egy szerződéshez, a cikket hozzáadhatja egy új vagy egy meglévő értékesítési rendeléshez.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: dec8dba9848b77e5c0a1007102789c8f88185fbc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904844"
---
# <a name="revenue-recognition-reallocation--scenario-2"></a>Bevételelszámolás újbóli felosztása – 2. eset

[!include [banner](../includes/banner.md)]

Ebben a cikkben az újbóli felosztásnak azt az esetét mutatjuk be, amelyben két értékesítési rendelést adnak meg, majd a vevő az első értékesítési rendelés számlázása után hozzáad egy további cikket a szerződéshez. Amikor új cikket ad hozzá egy szerződéshez, a cikket hozzáadhatja egy új vagy egy meglévő értékesítési rendeléshez.

Ennél az esetnél a **Számlajavítások feladása a Kinnlevőségekbe** beállítás a **Nem** értékre van állítva. Ez a beállítás a **Bevételelszámolás** lapon, a **Főkönyvi paraméterek** oldalon található. (**Bevételelszámolás \> Beállítás \> Főkönyvi paraméterek**).

[![Számlajavítások feladása a Kinnlevőségekbe beállítva a Nem értékre.](./media/12_rev-rec-scenarios.png)](./media/12_rev-rec-scenarios.png)

Létrehoznak egy értékesítési rendelt az US\_SI\_0003 nevű vevőhöz. A vevő telepítési szolgáltatásokat (cikkszám: S0001) és támogatási csomagot (cikkszám: S0008) vásárol egy laptophoz, de magát a laptopot még nem választotta ki. A telepítési szolgáltatásokhoz kapcsolódó bevételt a rendszer a laptop vásárlásának dátumáig késlelteti. A rendszer a támogatási csomagra vonatkozó bevételt késlelteti, és 12 hónapra lebontva számolja el, a szerződés dátumtartományának megfelelően.

[![Az értékesítési rendelés sorai a telepítési szolgáltatásokhoz és a támogatási csomaghoz.](./media/13_rev-rec-scenarios.png)](./media/13_rev-rec-scenarios.png)

Az értékesítési rendelést visszaigazolták. Mivel mindkét cikk esetében be van állítva a bevételi ár felosztása, a rendszer az értékesítési rendelés visszaigazolásakor kiszámítja a bevételi árat. A **Bevételi ár felosztása** oldalon megtekintheti a rendszer által könyvelt bevételt (a Műveletpanel **Értékesítési rendelés** oldalán, a **Kezelés** lapon, a **Bevételelszámolás** csoportban válassza a **Bevételi ár felosztása** lehetőséget). A telepítési szolgáltatásokra vonatkozó 250,00 $ összegű bevételt a rendszer feladja a Halasztott bevétel számlára. A támogatási csomagra vonatkozó 150,00 $ összegű bevétel is a Halasztott bevétel számlára kerül. A bevételi árak összegének meg kell egyeznie a bevételi ár felosztásának rögzítésére beállított sorok összegével (400,00 $).

[![Bevételi ár felosztása oldal.](./media/14_rev-rec-scenarios.png)](./media/14_rev-rec-scenarios.png)

Az értékesítési rendelést hiánytalanul kiszámlázzák. A következő illusztráción a számlához feladott könyvelési tétel látható.

[![A teljesen kiszámlázott értékesítési rendelés könyvelési tétele.](./media/15_rev-rec-scenarios.png)](./media/15_rev-rec-scenarios.png)

Létrejön a bevételelszámolási ütemezés is, de a rendszer még egyik bevételt sem számolja el.

[![Bevételelszámolási ütemezés oldal.](./media/16_rev-rec-scenarios.png)](./media/16_rev-rec-scenarios.png)

Néhány nappal később az ügyfél kiválaszt egy laptopot. Bevisznek egy második értékesítési rendelést.

[![Az értékesítési rendelés sora a laptophoz.](./media/17_rev-rec-scenarios.png)](./media/17_rev-rec-scenarios.png)

A második értékesítési rendelést is visszaigazolják. Mivel ez az értékesítési rendelés csak egy sort tartalmaz, az értékesítési rendelés visszaigazolásakor nem kerül sor a bevételi ár felosztására. A rendszer csak akkor végzi el a bevételi ár felosztását, ha két vagy több egyedi tételről van szó, és ha ezeknél a tételeknél be van állítva a bevételi ár felosztása.

Ha ez az új értékesítési rendelés a vevő szerződését érintő egyetlen módosítás, most már le lehet futtatni az újbóli felosztás folyamatát. A két értékesítési rendelés egyikében válassza az **Ár újbóli felosztása új rendelési sorokba** lehetőséget az **Ár újbóli felosztása új rendelési sorokba** oldal megnyitásához. Másik lehetőségként lépjen a **Bevételelszámolás \> Időszakos feladatok \>Ár újbóli felosztása új rendelési sorokba** lehetőségre. Válassza ki a két értékesítési rendelést és a megfelelő értékesítésirendelés-sorokat, majd válassza az **Újbóli felosztás frissítése** lehetőséget. Az **Újból felosztott összeg** oszlopban megjelenik az egyes értékesítésirendelés-sorok új bevételi ára.

[![Új bevételi árak az Ár újbóli felosztása új rendelési sorokba oldalon.](./media/18_rev-rec-scenarios.png)](./media/18_rev-rec-scenarios.png)

Ezután válassza a **Várható bizonylat** lehetőséget, hogy megtekinthesse azokat a könyvelési tételeket, amelyeket csak a főkönyvbe adnak fel. Mivel a **Számlajavítások feladása a Kinnlevőségekbe** lehetőség a **Nem** értékre van állítva a **Főkönyvi paraméterek** oldalon, az újbóli felosztás feldolgozásakor nem történik változás a kinnlevőségekben.

[![Könyvelési tételek a Várható bizonylat oldalon.](./media/19_rev-rec-scenarios.png)](./media/19_rev-rec-scenarios.png)

A **Várható bizonylat** oldalon az utolsó három sor sztornírozza a feladott számláról származó eredeti könyvelési tételt. Az első négy sor alkotja a számlához feladott új könyvelési tételt. Fontos tudni, hogy az új számla nem jelenik meg a vevő számára. Az újbóli felosztás után a vevő még további 426,00 $ összeggel tartozik, ezt az összeget egy új könyvelési tétellel fel kell adni a kinnlevőségekbe. A beszámított adó és a késleltetett bevétel összege: 188,69 $ + 314,48 $ + 26,00 $ = 529,17 $. A késleltetett bevétel összege az újbóli felosztás miatt módosult. A különbséget (103,17 $) fel kell adni a Részleges számlabevétel elszámolási számlára. Amikor az újbóli felosztásba bevont második értékesítési rendeléshez tartozó számlát is feladják, a rendszer törli ezt az egyenleget.

Az újbóli felosztás befejezéséhez válassza a **Feldolgozás** lehetőséget. A program kéri, hogy adja meg a feladás dátumát, akkor is, ha nem adott fel semmit. Az újbóli felosztás befejezése után az egyes értékesítési rendelések **Bevételi ár felosztása** oldalán megjelenik a két értékesítési rendelés összes tételére vonatkozó felosztás. Más szóval minden értékesítési rendelés **Bevételi ár felosztása** oldalán szerepelni fog egy cikk, amely nem létezik az adott értékesítési rendelésben, mert ez ugyanannak a szerződésnek a része, de egy másik értékesítési rendeléshez tartozik.

> [!TIP]
> Ha szeretne magyarázatot arról, hogy miért jelennek meg itt ezek a cikkek, további oszlopokat adhat a rácshoz, például: **Újrafelosztási azonosító** és **Értékesítési rendelés**.
> 
> [![További oszlopok a Bevételi ár felosztása oldalon.](./media/20_rev-rec-scenarios.png)](./media/20_rev-rec-scenarios.png)

A 00036-os értékesítési rendelésben a bevételelszámolási ütemezés az új bevétel újrafelosztási ára alapján frissült. Ebből az értékesítési rendelésből nyissa meg a **Bevételelszámolási ütemezés** oldalt. Korábban 13 sor tartozott az S0008-as cikkhez (ehhez a cikkhez 12 hónapos ütemezést adtak meg). Jelenleg 39 sor van: az eredeti ütemezés 13 sora, 13 sztornírozott ütemezési sor, valamint az új bevételi áron alapuló 13 sor.

[![A Bevételelszámolási ütemezés frissített oldala 39 sorral az S0008 cikkhez.](./media/21_rev-rec-scenarios.png)](./media/21_rev-rec-scenarios.png)

Hasonlóképpen az S0001 cikk korábban két sort tartalmazott, míg most hatot tartalmaz.

[![A Bevételelszámolási ütemezés frissített oldala hat sorral az S0001 cikkhez.](./media/22_rev-rec-scenarios.png)](./media/22_rev-rec-scenarios.png)

Ha a **Bizonylat** lehetőséget választja a 000036-os értékesítési rendelésnél, a számlanapló az eredeti könyvelési tételt jeleníti meg. A sztornírozó tétel és az értékesítési rendelésből származó új könyvelési tétel megtekintéséhez válassza a **Bevételkiigazítások** lehetőséget a Műveletpanelen, majd válassza a **Bizonylat** lehetőséget.

[![000036-os értékesítési rendelés.](./media/23_rev-rec-scenarios.png)](./media/23_rev-rec-scenarios.png)

Ezután nyissa meg az **Összes vevő** oldalt (**Kinnlevőségek \> Vevők \> Összes vevő**), válassza ki az **US\_SI\_0003** vevőt, majd válassza a **Tranzakciók** lehetőséget. Megjelenik a 000036-os értékesítési rendelés nyitott számlája. Ha kiválasztja a bizonylatot, az eredeti könyvelési tételt fogja látni, nem pedig az újbóli felosztásból származó új könyvelési bejegyzést. A kinnlevőségek között nem lehet megtekinteni a sztornírozó tételt és az új könyvelési tételt.

Most már kiszámlázható a második értékesítési rendelés. A vevőnek elküldött számla végösszege a következő: 1099,00 $ + 71,44 $ adó = 1170,44 $. A következő illusztráció a feladott könyvelési tételt mutatja.

[![Bizonylattranzakciók oldal a feladott könyvelési tétellel.](./media/24_rev-rec-scenarios.png)](./media/24_rev-rec-scenarios.png)

Mivel a bevétel és az értékesítés összege nagyobb 1170,44 $-nél, a rendszer feladja a különbözetet, ami –130,17 $. Ez az összeg törli a Részleges számlabevétel elszámolási számla egyenlegét. A rendszer az újbóli felosztás után feladja ezt az egyenleget az új könyvelési tételbe.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
