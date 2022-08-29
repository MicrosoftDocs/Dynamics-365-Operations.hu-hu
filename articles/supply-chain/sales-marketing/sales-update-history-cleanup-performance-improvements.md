---
title: Értékesítési előzményadatok tisztításának ütemezése
description: Ez a témakör azt mutatja be, hogyan lehet javítani a rendszer teljesítményét az értékesítési frissítések előzményeinek rendszeres időközönként futtatott ismétlődő feladatának ütemezésével.
author: myvakalo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e9a4dd5372afa8a0452449d1cb9121107e6e1610
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335503"
---
# <a name="schedule-sales-history-data-cleanup"></a>Értékesítési előzményadatok tisztításának ütemezése

[!include [banner](../includes/banner.md)]

Alapműveletének részeként a Microsoft Dynamics 365 Supply Chain Management folyamatosan generálja és tárolja az értékesítési előzmények frissítési adatait. Az idő során előfordulhat, hogy nagy mennyiségű lejárt értékesítési előzményadat halmozott lesz a rendszerben. Az összesített adatok teljesítmény- és működési problémákat okozhatnak az értékesítési rendelésekhez kapcsolódó dokumentumok feladása során. (Ezek közé tartoznak az értékesítési rendelések visszaigazolásai, az értékesítési csomagjegyzékek, az értékesítési kitárolási listák és a számlák). Emiatt az értékesítés frissítési *előzményeinek* tisztítási ismétlődő feladatát be kell állítania és ütemezni, hogy a rendszer rendszeres időközönként fusson. Ez a feladat eltávolítja az értékesítési előzmények már nem szükséges frissítési adatait.

Ha az értékesítési frissítések *előzményeinek* tisztítási ismétlődő feladatát használja, javasoljuk, *hogy* engedélyezze az Értékesítési előzmények tisztítása teljesítményjavítások funkcióját, ami hatékonyabbé teszi a feladat futtatását. (Ennek ellenére a feladat a funkció engedélyezése nélkül is futtatható.)

## <a name="turn-on-the-sales-history-cleanup-features"></a>Az értékesítési előzmények tisztítási funkcióinak bekapcsolás

*Az* értékesítési frissítések előzményeinek tisztítási ismétlődő feladatának, valamint az ebben a cikkben ismertetett összes funkciónak a beállítását úgy állíthatja be és használhatja, *·* *hogy* engedélyezi az Értékesítési előzmények tisztítása teljesítményjavításokat és az értékesítések frissítésének előzményeinek tisztítását a Funkciókezelés kori funkciói alapján, az alábbi alszakaszok szerint.

### <a name="sales-history-cleanup-performance-improvements"></a>Értékesítési előzmények adattisztítási teljesítményének javításai

Az **Értékesítési előzményadatok megtisztítása** időszakos kötegelt feladat hosszú ideig tart, ha ritkán olyan környezetben futtatják, ahol nagy mennyiségű értékesítési frissítés van. Az *Értékesítési előzmények tisztítása teljesítményjavításai* szolgáltatás ilyen helyzetekben csökkentheti a futási időtartamot, és javíthatja a megbízhatóságot.

A funkció a következőképpen javítja a meglévő tisztítási feladatot:

- A tisztítást kötegekre osztja (a testreszabásokkal módosíthatja a kötegméretet).
- Maximum 2 óráig fog futni (testreszabásokkal módosíthatja az időtartamot).
- Ahol lehetséges, az adatbázissal kapcsolatos funkciókat használ a zárolási versengés minimalizálásához, hogy a tisztítás során ne kelljen csatlakoztatni a tranzakciós táblákat.

A funkció engedélyezése után az **Értékesítések frissítési előzményeinek tisztítása** kötegelt feladat (**Értékesítési és marketing \> Időszakos feladatok \> Tisztítás \> Értékesítés frissítési előzményeinek tisztítása**) a korábbiakkal megegyezően fog futni, de jobb teljesítménnyel és maximum 2 órás működéssel fog futni. Ez azt jelenti, hogy egy adott megőrzési időkeret minden adatának tisztítása többször is szükséges lehet.

A funkció használata előtt be kell kapcsolva lennie a rendszeren. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Értékesítés és marketing*
- **Funkció neve:** *Értékesítési előzmények adattisztítási teljesítményének javításai*

### <a name="clean-up-sales-update-history-based-on-age"></a>Értékesítésfrissítési előzmények tisztítása kor alapján

Az *értékesítések frissítésének* *kor* alapján funkció alapján való tisztítása funkcióval megadhatja az értékesítési frissítések előzményeinek időszakos feladat futtatásakor megtartható rekordok maximális korát. A régebbi rekordok törlődni fognak. Ez a funkció akkor hasznos, ha a feladatot rendszeresen futtatásra van beállítva, mivel a kor számítása mindig a feladat futási dátumának megfelelően történik. Ha nem használja ezt a funkciót, akkor csak azt a dátumot állíthatja be, amely a legrégebbit megtartja.

A funkció használatához be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció kötelező, és nem lehet kikapcsolni. Ha 10,0,29-esnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák be- vagy kikapcsolhatják ezt a funkciót, ha a Funkciókezelés munkaterület korfunkciója alapján keresi meg az értékesítés frissítési előzményeinek tisztítását.

## <a name="set-up-and-schedule-the-sales-history-cleanup-periodic-task"></a>Az Értékesítési előzmények tisztítása ismétlődő feladat beállítása és ütemezése

Az Értékesítési előzmények időszakos feladatának *beállítását* és ütemezését a következő lépések szerint hajtsa végre.

1. A vállalat elemzéséhez meg kell határoznia, hogy hány napig kell megtartani az értékesítési rendelések feladási adatait. Általában javasolt a tisztítási feladat három hónapos, de legfeljebb hat hónapos futtatása.
1. Ugrás az Értékesítés **és marketing \> időszak feladatai \> – Értékesítésfrissítési \> előzmények tisztítása pontra**
1. Az Értékesítésfrissítési **előzmények** **párbeszédpanel** Paraméterek gyorsablakában állítsa be a következő mezőket:

    - **Adat tisztítása** – a következő értékek egyikének kiválasztásával adja meg a tisztítani kívánt rekordok típusát:

        - **Végrehajtva** – csak a teljesen feldolgozott rekordok törlése. Mivel nem valószínű, hogy lenne további használat ezekhez a rekordokhoz, ez a legbiztonságosabb beállítás.
        - **Végrehajtva és hibás** – a teljesen feldolgozott rekordok és a hibát észlelt rekordok törlése. Ez a beállítás a leggyakrabban használt. Előfordulhat, hogy a hibás rekordokat érdemes megvizsgálni, sőt kijavítani is, ahelyett, hogy a rekordokat automatikusan tisztítanák. Sok vállalat azonban úgy dönt, hogy ezeket a rekordokat is tisztítja egy hónap múlva, mivel valószínűleg már nem lesz jelentősége ettől az időponttól.
        - **Mind** – a végrehajtott, a hibás és a várakozó rekordok törlése. A várakozó rekordok érvényesek, de még nincsenek teljesen feldolgozva. A legtöbb esetben valószínűleg nem szeretné, hogy a rendszer automatikusan törölni tudja őket. Bizonyos helyzetekben előfordulhat azonban, hogy egy adott idő eltelte után a program automatikusan törli őket.

    - **Rekordok megtartása kor** alapján – adja meg, hogy a feladatok futtatásakor koruk alapján szeretné-e törölni a rekordokat, vagy törölni szeretné-e a rögzített dátum előtt létrehozott rekordokat. Ha a tisztítást ismétlődő feladatként ütemezi, *ezt* a beállítást Igen beállításra kell beállítani, mivel a kor számítása mindig a feladat futtatásának dátumára történik.

        - A Maximális kor mező engedélyezéséhez *állítsa* **Igen beállításra**. Ebben a mezőben adhatja meg a feladatok futtatásakor megtartott rekordok maximális korát. A Létrehozva **eddig mezőt** figyelmen kívül hagyja a rendszer.
        - Állítsa Nem beállításra *a* Létrehozás eddig **mező beállítását**. Ebben a mezőben adhatja meg a feladat futtatásakor megtartott rekordok legrégebbi létrehozási dátumát. A Rendszer **figyelmen kívül hagyja a Maximális kor** mezőt.

    - **Létrehozva eddig** – ez a beállítás csak akkor érvényes, **ha** a koron alapuló rekordok megtartása beállítás Nem beállításra *van beállítva*. A feladat futtatásakor megtartott rekordok legrégebbi létrehozási dátumának megadása. A program törli azokat a rekordokat, amelyek ezt a dátumot megelőzően létrejöttek.
    - **Maximális kor** – ez a beállítás csak akkor érvényes, **·** *ha a koron alapuló rekordok megtartása beállítás Igen beállításra van beállítva.* A feladat minden futtatásakor a rekordok maximális korának megadása (napokban megadásával). A régebbi rekordok törlődni fognak.

1. A futtatás **a háttérben gyorsablakban** adja meg, hogy mikor és milyen gyakran fusson a feladat. Ezekkel a beállításokkal valósíthatja meg az 1. lépésben meghatározott ütemezést. A mezők működnek, mint [az](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) Ellátásilánc-kezelés más típusú kötegelt feladatokkal kapcsolatos munkái.
1. Az **OK** gombra kattintva alkalmazza a beállításokat, és zárja be a párbeszédpanelt.
