---
title: Vizuális ütemezés lean manufacturing céljára
description: Ez a cikk a kanbanütemező tábláról nyújt tájékoztatást, amelynek használatával a termeléstervező a kanbanfeladatok termelési tervének szabályozására és optimalizálására használható.
author: johanhoffmann
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisualization, KanbanBoardUnplannedJobs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a743be96867c1f325e6fe01f23355c27cb4d0cc0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875188"
---
# <a name="visual-scheduling-for-lean-manufacturing"></a>Vizuális ütemezés lean manufacturing céljára

[!include [banner](../includes/banner.md)]

Ez a cikk a kanbanütemező tábláról nyújt tájékoztatást, amelynek használatával a termeléstervező a kanbanfeladatok termelési tervének szabályozására és optimalizálására használható.

Ez a cikk a kanbanütemező tábláról nyújt tájékoztatást, amelynek használatával a termeléstervező a kanbanfeladatok termelési tervének szabályozására és optimalizálására használható.

A Kanbanütemezési tábla lehetővé teszi, hogy a termeléstervező ellenőrizze és optimalizálja a kanbanfeladatok termelési tervét. Átláthatóvá teszi a kanbanfeladatok áramlását, és olyan eszközt ad a termeléstervező kezébe, amely optimalizálja és beállítja a termelési tervet a lean manufacturing munkacella számára.

## <a name="visual-scheduling-of-kanban-jobs"></a>Kanbanfeladatok vizuális ütemezése
A kanbanfeladat egy vagy több kanbanfeladatból állhat. Két típusú kanbanfeladat létezik:

-   Feldolgozás
-   Átvitel

Csak **Feldolgozás** típusú feladatokat ütemezhet. A kanbanfeladatot és annak tulajdonságait – például a tevékenység idejét – a termelési kanbanfolyamatban határozhatja meg. A termelési kanbanfolyamatban a kanbanfeladat is hozzá van rendelve egy munkacellához. A munkacella napi kapacitását az erőforráscsoportban beállított munkacella-kapacitás alapján számítja ki a rendszer. Ezt a kapcsolódó naptárban a napi munkaidő módosítja. Kanbanfeladat ütemezése esetén a feladat betölti a munkacella kapacitását. A Kanbanütemezési tábla fő jellemzői a következők:

-   A termelési terv lean munkacellában történő grafikus ábrázolása. Ez az áttekintés megjeleníti a tervezett kanbanfeldolgozási feladatokat a megadott időszakokra.
-   Olyan eszköz, amely lehetővé teszi a nem tervezett kanbanfeladatok ütemezését, valamint a korábban ütemezett feladatok újraütemezését.

## <a name="kanban-schedule-board"></a>Kanbanütemező tábla
A **Kanbanütemezési tábla** lap hét fő elemet tartalmaz a következő ábrán látható módon. 

![Kanbanütemező tábla.](./media/kanban-schedule-board-1024x554.png)
1.  Műveleti panel
2.  Mezők szűrése
3.  Nem tervezett feladatok gomb
4.  Időszak csomópontja
5.  Kanbanfeladat
6.  Kapacitássáv
7.  Időskála

### <a name="view-the-time-scale"></a>Az időskála megtekintése

A tábla időszakokra van osztva, ezek mindegyikét egy csomópont (4) jeleníti meg. Az időszakcsomópontok a függőleges tengelyen jelennek meg, és a vízszintes tengely egy olyan időskálát (7) jeleníti meg, amely az időszak hosszát mutatja. Egy időszak hossza egy nap vagy egy hét lehet. Az időszak hosszát a kijelölt Kanbanütemezési táblához (2 kiválasztott munkacella konfigurációja határozza meg). Minden időszakcsomópont esetében a Kanbanütemezési tábla jelzi, hogy az ütemezett kanbanfeladatok mennyire töltik meg az időszakot. Jelzi az időszak maximális kapacitását is. Ha az ütemezett teljesítmény meghaladja a maximális kapacitást, az időszak túlterheltnek minősül, és egy piros figyelmeztető jel látható. Az ütemezett kanbanfeladat egy olyan időszakban jelenik meg, amely ütemezett kezdési és befejezési időpontokkal (5) rendelkezik. A feladat hossza megegyezik a tevékenység idejével. A kanbanfeladatok egymást átfedően jelennek meg egy időszakban, ha tevékenységi időpontjaik meghaladják a munkacella munkaidejét.

### <a name="view-job-status"></a>A feladat állapotának megjelenítése

A kanbanfeladatról bővebb információk találhatók az eszközleírásban, amely akkor jelenik meg, amikor az egérmutatót a feladat fölé viszi. Egy szimbólum nyújt a feladat állapotával kapcsolatos információkat. Például az óra azt jelzi, hogy a kanbanfeladat késésben van.

### <a name="use-colors-to-view-the-kanban-schedule-board"></a>A Kanbanütemezési tábla megtekintése színekkel

Javíthatja a Kanbanütemezési tábla által nyújtott áttekintést azzal, hogy színek segítségével különbözteti meg a kanbanfeladatokat egymástól. A kanbanfeladat színének beállítása a lean ütemezési csoportban történik, ahol összevonhatja azokat a termékeket, amelyeket ugyanabban a sorrendben kell előállítani. Ha a **Téma színeinek használata** gombra kattint a **Tábla** műveleti ablaktáblán, válthat az alkalmazás témaszínei és a lean ütemezési csoportban beállított színek között. Az egyes időszakok esetében a kapacitássáv (6) jelzi, hogy az időszak rendelkezésre álló óráiból hányra töltöttek be kanbanfeladatot. Ha az időszak túlterhelt, a kapacitássáv vastagabban és piros színnel jelenik meg. Ezek a funkciók a műveleti ablaktábla (1) **Tábla** lapján, a **Kanbanütemezési tábla** lap tetején érhetők el.

## <a name="plan-unplanned-jobs"></a>Nem tervezett feladatok tervezése
Nem tervezett kanbanfeladatokat ütemezhet a **Nem tervezett feladatok tervezése** párbeszédpanelből. A párbeszédpanel megnyitásához kattintson a **Nem tervezett feladatok** gombra, amely megjeleníti a nem tervezett feladatok aktuális számát. Másik lehetőségként kattintson a **Nem tervezett feladatok tervezése** lehetőségre a műveleti ablaktábla **Tábla** lapján. A párbeszédpanelen megjelenik a munkacella nem tervezett kanbanfeladatainak listája. Használhatja a **Szűrő** mezőt a rács minden mezőjének szűrésére. Például egy bizonyos termékre szűrheti a kanbanfeladatokat. Miután megkapja az ütemezni kívánt feladatok szűrt listáját, válassza ki azokat a listában, és kattintson az **OK** gombra. A feladatok ütemezésének automatikus tervezéséhez állítsa az **Automatikus tervezés** lehetőséget **Igen** értékre. Ebben az esetben a rendszer a feladatokat egy időszakra ütemezi azok esedékessége szerint. A feladatok időszakonként is ütemezhetők. Válasszon ki egy időszakot az **Időszak** mezőben. A következő ábrán egy példát láthat a **Nem tervezett feladatok tervezése** párbeszédpanelről. 

![Nem tervezett feladatok tervezése párbeszédpanel.](./media/plan-unplanned-jobs-1024x564.png)

## <a name="sequence-kanban-jobs-within-the-same-period"></a>Kanbanfeladatok sorrendbe helyezése ugyanazon időszakon belül
Módosíthatja egy vagy több kijelölt feladat sorrendjét egy időszakon belül. Ez a lehetőség akkor lehet hasznos, ha az időszakon belül bizonyos feladatoknak prioritást szeretne adni. Másik lehetőségként sorrendben helyezheti az azonos termékattribútumokkal rendelkező feladatokat a feladat végrehajtásának optimalizálása érdekében. A sorrendet húzással történő áthelyezéssel, vagy a **Visszafelé** és az **Előre** menüpontok használatával is módosíthatja a **Tábla** műveleti ablaktábla lapján.

## <a name="reassign-kanban-jobs-across-periods"></a>Kanbanfeladatok időszakok közötti átadása
A feladatokat egyik időszakból áthelyezheti a másikba. Ez a lehetőség akkor lehet hasznos, ha egy időszak túlterhelt, és szeretné beállítani a szabad kapacitással rendelkező időszakok terhelését. A feladatok átadását húzással történő áthelyezéssel, vagy a **Következő időszak** és az **Előző időszak** menüpontok használatával is módosíthatja a **Tábla** műveleti ablaktábla lapján.

## <a name="open-the-kanban-schedule-board"></a>Kanbanütemezési tábla megnyitása
A Kanbanütemezési táblát a menüelem használatával a következő lapokon nyithatja meg:

-   **Termelési terület** lap
-   **Kanbanfeladatok ütemezése** lap
-   **Termelési folyamat megjelenítése** lap


## <a name="additional-resources"></a>További erőforrások

[Kanbanfeladat ütemezése lean manufacturing céljára](lean-manufacturing-kanban-job-scheduling.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]