---
title: Alaptervezés futtatásának megfigyelése
description: Ez a cikk bemutatja, hogy a termeléstervező hogyan látja, hogy folyamatban van-e az alaptervezés futtatása.
author: t-benebo
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da04ef95f2f7e411ecea3fadf7ff31b3502d3d99
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860754"
---
# <a name="monitor-a-master-planning-run"></a>Alaptervezés futtatásának megfigyelése

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a>Gantt-diagram használata az Alaptervezési folyamat megjelenítéséhez

Az **Alaptervezési folyamat megtekintése** lapon megtekintheti a múltbeli Alaptervezés futtatások adatait Gantt-diagramként. Ez a funkció segít megérteni az Alaptervezés különböző fázisaiban töltött időt. Egy aktuális aktív tervezési feladathoz az **Alaptervezési folyamat megtekintése** lapon nyomon követheti az előrehaladást, és megtekintheti a becsült hátralévő időt.

### <a name="turn-the-master-plan-progress-visualization-feature-on-or-off"></a>Az Alapterv folyamatjelző funkció be- és kikapcsolása

Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10.0.25-ösnél régebbi verziót futtat, *·*[akkor](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák be- vagy kikapcsolhatják ezt a funkciót, ha a Szolgáltatáskezelés munkaterületén az alaptervezés folyamatjelző szolgáltatását keresi.

### <a name="use-the-master-plan-progress-visualization-feature"></a>Az Alapterv folyamatjelző funkció használata

Az **Alaptervezés folyamatmegjelenítése** lap a múltbeli tervezési feladatok és az aktív tervezési feladatok megjelenítésére is képes. 

A korábbi tervezési feladatok megtekintéséhez két lehetőség közül választhat. 

1. Nyissa meg az **Alaptervezés \> Beállítás \> Tervek \> Alaptervek** elemet, majd kattintson a műveleti ablak **előzmények** elemére. Válassza ki a kívánt feladatot, válassza ki a **Lekérdezések** elemet, majd válassza a **Folyamatjelző megtekintése** lehetőséget.
1. Lépjen az **Alaptervezés \> Munkaterületek \> Alaptervezés** elemre, az Alaptervezés mozaikján kattintson az **Előzmények** hivatkozásra. Válassza ki a kívánt feladatot, válassza ki a **Lekérdezések** elemet, majd válassza a **Folyamatjelző megtekintése** lehetőséget.

Az aktív tervezési feladatok megtekintéséhez két lehetőség közül választhat. 
1. Lépjen az **Alaptervezés \> Munkaterületek \> Alaptervezés** elemre, a műveleti ablaktáblán kattintson a **Befejezetlen tervezési folyamat** elemre. Válassza ki a kívánt feladatot, válassza ki a **Lekérdezések** elemet, majd válassza a **Folyamatjelző megtekintése** lehetőséget.
1. Lépjen az **Alaptervezés \> Munkaterületek \> Alaptervezés** elemre, az Alaptervezés mozaikján kattintson az **Folyamatjelző megtekintése** hivatkozásra. Válassza ki a kívánt feladatot, válassza ki a **Lekérdezések** elemet, majd válassza a **Folyamatjelző megtekintése** lehetőséget.

Ne feledje, hogy csak egy tervezési feladat feldolgozása során tekinthetők meg az aktív feladatok.

### <a name="analyze-a-master-planning-job"></a>Alaptervezési feladat elemzése

A Gantt-diagramban a következő tervezési folyamatok kibontásával megjelenítheti az eltöltött idő további adatait:

- Inicializálás
- Adatok törlése és beszúrása
- Fedezettervezés
- Késések
- Műveletkérő üzenetek
- Véglegesítés
- Automatikus megerősítés

A Gantt-diagram hasznos eszköz, ha meg szeretné tekinteni a műveletkérő üzenetek használatával járó hatásokat.

#### <a name="navigation-in-the-gantt-chart"></a>Navigálás a Gantt-diagramon

- A kiválasztott csoport kibontásához és a részletek megjelenítéséhez válassza ki a fanézetben a pluszjelet (**+**).
- A kiválasztott csoport összecsukásához válassza ki a mínusz jelet (**–**) a fanézetben.
- A billentyűzetet navigálásra használhatja. A **Felfelé nyíl** és **Lefelé nyíl** billentyűk segítségével mozoghat a sorok között. A **Jobbra nyíl** és a **Balra nyíl** billentyűk segítségével bonthatja ki és csukhatja össze a csoportokat.
- A Gantt-diagram minden szintjének megnyitásához vagy bezárásához válassza az **Összes kibontása** vagy **Össze összecsukása** elemet.
- A kapcsolódó feldolgozási idő megtekintéséhez vigye a mutatót egy feladatra. (A feladatok a Gantt-diagram legalacsonyabb szintje.)

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a>További alaptervezési futtatás megtekintése a feladatok összehasonlításához

Ha kijelöl egy Alaptervezési feladatot a **További alaptervezés-futtatás megjelenítése** mezőben, akkor a Gantt-diagramban megtekinthet egy másik alaptervezés-futtatást és összehasonlíthatja a két feladatot.

#### <a name="bom-level-display"></a>Anyagjegyzék szintű megjelenítés

A fedezeti tervezés, a késések, a műveletek és a megerősítés esetén a megjelenített anyagjegyzékszint különböző.

- **Fedezeti tervezés** – az anyagjegyzékszintek a várakozásnak megfelelően jelennek meg. Ezek a fentről lefelé haladva kerülnek kiszámításra.

    **Példa:** AJ-szint 0, 1, 2

- **Késések** – az AJ-szintek a fedezeti tervezés AJ-szintjének a –1-gyel való szorzatával jelennek meg. (Más szóval negatív előjellel rendelkeznek.)

    **Példa:** AJ-szint -2, -1, 0

- **Műveletkérő üzenet** – az anyagjegyzékszintek a várakozásnak megfelelően jelennek meg. Ezek a fentről lefelé haladva kerülnek kiszámításra.

    **Példa:** AJ-szint 0, 1, 2

- **Automatikus megerősítés** – Az anyagjegyzék szintje 999 mínusz a fedezeti tervezés anyagjegyzék-szintje.

    **Példa:** AJ-szint 999, 998, 997

A következő táblázat összegzi a viselkedést.

| A megjelenített AJ-szint | Végtermék | Részösszetevő | Nyersanyag |
|---|---|---|---|
| Fedezettervezés | 0 | 1 | 2 |
| Késések | 0 | –1 | –2 |
| Műveletkérő üzenet | 0 | 1 | 2 |
| Automatikus megerősítés | 999 | 998 | 997 |

#### <a name="visualize-progress"></a>Folyamatjelző megjelenítése

Ha éppen futó alaptervezési feladatot jelenít meg, a folyamat a Gantt-diagram színeivel jeleníthető meg. A kék témára a következő színek érvényesek: Más színtémák esetében a színek különböznek.

- **Sötétkék** – Befejezett tervezési feladatok.
- **Narancs** – a jelenleg folyamatban lévő feladat.
- **Világoskék** – a hátralévő feladatok becslése.

A szín csak a Gantt-diagram legalacsonyabb szintjén jelenik meg. Az **összes kibontása** parancsra kattintva megtekintheti az Alaptervezési feladat összes feladatát. A fennmaradó feladatok becslése a múltbeli Alaptervezési feladatok alapján történik.

## <a name="run-master-planning-and-track-processing-time"></a>Alaptervezés futtatása és a feldolgozási idő nyomon követése

1. Az alapértelmezett irányítópulton válassza az **Alaptervezés** elemet.
1. A **Terv** mezőben adjon meg vagy válasszon ki egy értéket.
1. Válassza a **Futtatás** parancsot.
1. Állítsa be a **Feldolgozási idő nyomon követése** lehetőséget **Igen** értékre.
1. Adjon meg egy számot a **Szálak száma** mezőben.
1. **A szerepeltetni kívánt rekordok** gyorslapján válassza a **szűrő** elemet.
1. A rácsban válassza ki azt a sort, amelyben a **Mező** mezője a **Cikkszám** értékre van állítva.
1. A **Feltétel** mezőben adjon meg egy értéket.
1. Válassza ki az **OK** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]