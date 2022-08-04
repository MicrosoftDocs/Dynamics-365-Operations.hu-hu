---
title: Vizuális és jóslék végrehajtása
description: Ez a témakör azt ismerteti, hogyan lehet figyelni az igényvezérelt anyagigény-tervezés (DDMRP) adatkeresési pontokat, pufferzónákat, tervezett rendeléseket és előzményeket.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqDDMRPWorkspace, ReqDecouplingPointsStatusByNetFlow, ReqDecouplingPointStatusByOnHand, ReqPlannedOrderForm, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: e3afdd10860494b3cfe73a113a0e4e8fb07682a1
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186568"
---
# <a name="visual-and-collaborative-execution"></a>Vizuális és jóslék végrehajtása

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Ez a témakör azt ismerteti, hogyan lehet figyelni az igényvezérelt anyagigény-tervezés (DDMRP) adatkeresési pontokat, pufferzónákat, tervezett rendeléseket és előzményeket.

## <a name="visually-track-buffers-and-quantities-for-a-selected-item"></a>Egy kijelölt cikk pufferének és mennyiségének vizuális követése

A Microsoft vizuálisan Dynamics 365 Supply Chain Management nyomon követheti, hogy hogyan változnak a pufferek, az készletmennyiségek és a nettó áramlási szintek az idő szerint bármely kiválasztott kiadott terméknél. A diagramok megnyitásához és áttekintéshez hajtsa végre a következő lépéseket.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válasszon egy kiadott cikket, amely be van állítva felfelé és felfelé. (További tájékoztatás: [Készlet pozicionása](ddmrp-inventory-positioning.md).)
1. A Munkaablak Terv lapján **válassza** a Cikkfedezet **lehetőséget**.
1. A Cikkfedezet **lapon** válasszon ki egy olyan cikkfedezeti rekordot, amely létrehoz egy lefedő pontot. (Ez a rekord egy fedezeti csoport nevét mutatja, amely a felfokozási pontok létrehozására van beállítva.)
1. Válassza az **Kéznél fület** . Ez a lap egy diagramot tartalmaz, amely bemutatja az időben módosult készletmennyiségeket, valamint a tervezési optimalizálás futtatásakor egy adott időszakra rögzített, az adott készletszint értékét. A lap tartalmaz egy táblát is, amely megmutatja, hogy az alábbi kategóriák közül melyekbe esik az egyes rögzített, az árhoz rögzített kategóriák:

    - **Kritikusan alacsony** – az időszakban a minimum felének kisebb.
    - **Alacsony** – a minimum és a minimum között van.
    - **Átlagos kéznél –** a minimum és a minimum plusz a zöld zóna között.
    - **Átlag feletti –** átlag feletti.

    ![Korábbi, az <a0/-a1><a2/5><a2/5><a2/5><a2/5><a2](media/ddmrp-on-hand-graph.png "Korábbi, az <a0/-a1><a2/<a2/5><a2/<a2/<a")

    > [!NOTE]
    > Az Készlet **lapon** **használt színek a Pufferértékek lapon használthoz hasonló színek tartományaitól eltérő tartományokat képviselnek.**

1. A Pufferértékek lap kiválasztásával megtekintheti, hogy hogyan változtak a pufferértékek az idő szerint, **és** hogyan viszonyulnak a készlet és a nettó áramlás szintjeihez.

    ![Korábbi készlet- és nettóáramlási szintek a Pufferértékek lapon.](media/ddmrp-buffer-values-graph.png "Korábbi készlet- és nettóáramlási szintek a Pufferértékek lapon")

## <a name="track-the-status-and-planned-orders-for-all-decoupling-points"></a>Az összes karbantartáspont állapotának és tervezett rendelésének nyomon követése

Az **igényvezérelt MRP-munkaterület** számos eszközt kínál, a fő teljesítménymutatók (KPI) és a kapcsolódó tervezett rendelések állapotának áttekintése. A megnyitásához nyissa meg az Alaptervezés **\> munkaterületének igényvezérelt \> MRP-fájlját**.

![Igényvezérelt MRP-munkaterület](media/ddmrp-workspace.png "Igényvezérelt MRP-munkaterület")

## <a name="get-overviews-of-decoupling-points-and-planned-orders"></a>Áttekintés a pontkeresési pontokról és a tervezett rendelésekről

Az Igényvezérelt **MRP-munkaterületen** túl az Ellátásilánc-kezelés több olyan oldalt is biztosít, amelyeken megtekintheti a DDMRP beállításokat, az adatkeresési pontokat és a tervezett rendeléseket. Ezeken a lapokon a műveletpanelen kényelmes gombok is használhatók, amelyek a pufferek kezelésére, az alaptervezés futtatására és más kapcsolódó nézetek megnyitására használhatók.

- A felfokozási pontok nettó áramlási szint szerinti állapotának megtekintéséhez nettó **\>\> áramlás szerint menjen az Alaptervezés DDMRP \> Tölcsérei pontállapothoz.**
- A megfelelő pontállapot aktuális **\>\> készletszint szerinti megtekintéséhez menjen az Alaptervezés DDMRP \> Pontszámupling pontállapota aktuális készlet szerint ponthoz.**
- Az alaptervezés **\>\> DDMRP tervezett pontszámú rendeléseit az Alaptervezés DDMRP \> tervezett rendelésekkel lehet megtekinteni.**
- Az átfutási idők megtekintéséhez menjen **\>\> az Alaptervezés DDMRP \> Visszacsatolt átfutási ideje osztályra.**

## <a name="clean-up-decoupling-point-buffer-values"></a>Lecsatolási pont pufferértékének tisztítása

Az idő során a rendszer nagy mennyiségű előzményadatot hoz létre, amelyek a folyamatban lévő pufferszámításokkal kapcsolatosak. Az előzményadatok az adattérfogat növekedését eredményezik, és végső soron hatással lehetnek a rendszer teljesítményére. Ezért javasoljuk, hogy időnként tisztítást takarítson meg a régi tetszetelésipont-pufferértékek között.

> [!WARNING]
> A tisztítási feladat eltávolítja a korábbi pufferérték-beállításokat és az előzmény-készlet/nettó áramlás adatait. Nem megfordítható.

A következő lépések szerint tisztítást kell tartani a tartalékpont pufferértékeivel.

1. Ugrás az Alaptervezés **\>\> DDMRP felsztornózása \> pontpufferértékek tisztítására.**
1. A Tisztítási **pont pufferértékek** párbeszédpanelen állítsa be a következő mezőket:

    - **Napnál régebbi** rekordok törlése – adja meg a megtartott rekord korát napokban. A program minden olyan rekordot törölni fog, amely régebbi, mint ez az érték.
    - **Alapterv** – válasszon egy olyan alaptervet, amely tartalmazza azokat a cikkeket, amelyekre kihat ez a tisztítás. A tisztítás a terv **minden** elemét alkalmazni fogja az ezen a párbeszédpanelen megadott szűrőbeállítások alkalmazása után.

1. A kötegelt feladat **által** **·** **futtatott** rekordok halmazának korlátozására a Gyorslapra vonatkozó rekordokon a Lekérdezés párbeszédpanel megnyitásához válassza a Szűrő lehetőséget. Ez a párbeszédpanel pont úgy [működik](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md), mint az Ellátásilánc-kezelés többi háttérben futó feladatának esetében.
1. A háttérben **futó** futtatás gyors oldalon adja meg, hogy mikor és milyen gyakran kell a tisztítást futtatni. A mezők ugyanúgy működnek, mint a Supply Chain Management más, [háttérben futó feladattípusai](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).
1. Az **ÚJ feladat kötegelt feladatok várólistájára való felvételének az OK** gombra való felvétele a végrehajtáshoz.
