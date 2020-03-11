---
title: Rács funkciói
description: Ez a témakör ismerteti a rács vezérlőelem számos erőteljes funkcióját. Az új rács funkciónak engedélyezve kell lennie ahhoz, hogy hozzáférhessen ezekhez a funkciókhoz.
author: jasongre
manager: AnnBe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7136edba828bf97b6e0c8d2a698b884640d680e5
ms.sourcegitcommit: 880f617d1d6e95eccbed762c7ea04398553c2ec0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036265"
---
# <a name="grid-capabilities"></a>Rács funkciói

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Az új rács vezérlőelem számos hasznos és erőteljes funkciót tartalmaz, amelyek a felhasználó hatékonyságának növelésére, az adatokkal kapcsolatos érdekesebb nézetek kialakítására és az adatokkal kapcsolatos jelentőségteljes rálátás megszerzésére használhatók. Ez a cikk a következő funkciókat mutatja be: 

-  Teljes összegek számítása
-  Adatok csoportosítása
-  A rendszer előtt történő gépelés
-  Matematikai kifejezések kiértékelése 

## <a name="calculating-totals"></a>Teljes összegek számítása
A Finance and Operations alkalmazásokban a felhasználók a számokat tartalmazó oszlopok alján látható összesítéseket megtekinthetik a rácsokban. Ezeket az összegeket a rács alján látható lábléc szakasz mutatja. 

### <a name="showing-the-grid-footer"></a>A rács láblécének megjelenítése
A Finance and Operations alkalmazásokban minden egyes táblázatos rács alján láblécterület található. A lábléc értékes információkat jeleníthet meg, amely a rácsban megjelenő adatokhoz kapcsolódik. Íme néhány példa az ilyen információkra:

- A táblázatból kiválasztott sorok száma (ha egynél több rekord van kiválasztva)
- Végösszegek a konfigurált numerikus oszlopok alján
- Az adathalmazban lévő sorok száma összesen 

Alapértelmezetten ez a lábléc rejtett, de egyszerűen be lehet kapcsolni. A rács láblécének megjelenítéséhez kattintson a jobb gombbal a rács egy oszlopának fejlécére, és válassza ki a **Lábléc megjelenítése** lehetőséget. Miután egy adott rácsnál bekapcsolta a láblécet, a rendszer emlékezni fog a beállításra mindaddig, amíg a felhasználó úgy nem dönt, hogy elrejti a láblécet. Ez úgy végezhető el, hogy a jobb gombbal rákattint egy oszlop fejlécére, és kiválasztja a **Lábléc elrejtése** lehetőséget.  Ne feledje, hogy egy jövőbeli frissítésben a **Lábléc megjelenítése/elrejtése** műveletet valószínűleg áthelyezzük. 

### <a name="specifying-columns-with-totals"></a>Összesítéssel ellátott oszlopok megadása
Jelenleg alapértelmezetten egy oszlop sem jeleníti meg az összegeket. Ezt a rács oszlopai szélességének beállításához hasonlóan egyszeri beállítási tevékenységnek tekintjük. Miután megadta, hogy szeretné egy oszlop összegeit megtekinteni, a rendszer a lap legközelebbi meglátogatásakor emlékezni fog a beállításra.  

Egy oszlopot kétféleképpen lehet az összegek megjelenítésére konfigurálni: 

- Kattintson a jobb gombbal az oszlopra, amelynek végösszegét látni szeretné, és válassza az **Összesen az oszlopban** lehetőséget. Ez a művelet három esemény előfordulását okozza:

    1. A lábléc láthatóvá válik. 
    2. A program menti a beállítást, hogy látni szeretné az oszlopra vonatkozó összeget. 
    3. Végösszegszámítás indul ehhez az oszlophoz, illetve az összes többihez is, amelyeknél korábban már beállította az összegek megtekintését. A végösszeg megjelenítéséhez szükséges idő az összesíteni kívánt adathalmaz méretétől függ.

- A lábléc láthatóvá válása után válassza a **Végösszeg megjelenítését** a lábléc területén azon oszlop alján, amelyre vonatkozóan összesítést szeretne látni. Ha nincsenek konfigurált oszlopok, akkor az összes numerikus oszlop esetében elérhetővé válik az **Összeg megjelenítése** gomb. 

    Miután legalább egy oszlopot konfigurált összesítésekhez, akkor az **Összeg megjelenítése** gomb csak a rámutatással vagy a fókusszal érhető el. A **Végösszeg megjelenítése** elem kiválasztási művelete csak elmenti az adott oszlop összesítésének megjelenítésére vonatkozó preferenciát, így a preferenciát a rendszer az oldal jövőbeli látogatásakor is alkalmazza. A láblécben ezt az állapotot egy gondolatjel jelöli, amely a oszlopban jelenik meg. (A másik lehetőség, hogy ha az adathalmaz elég kicsi, akkor egy összeg azonnal megjelenik.)

Ha hibázik, és a továbbiakban nem szeretné megjeleníteni az adott oszlopban szereplő összegeket, kattintson az egér jobb oldali gombjával az oszlopra, és válassza az **Összeg elrejtése** lehetőséget, vagy jelölje be az oszlop láblécében az **Összeg elrejtése** gombot. Ezt a beállítást a program a lap későbbi megtekintései esetére is elmenti. 

### <a name="calculating-totals"></a>Teljes összegek számítása
Ha olyan oldalra lép, amelyen látható a lábléc, és az oszlopokat már beállították összesítésekhez, akkor megtörténhet, hogy az összesítések nem jelennek meg a láblécben. A viselkedés függ az oldalon levő adathalmaz méretétől. Ha az adathalmaz kellően kicsi, a program automatikusan megjeleníti az összegeket, valamint az adathalmaz sorainak számát. Ha a láblécben az összesítésre konfigurált oszlopokban gondolatjeleket lát, akkor az adathalmaz túl nagy ahhoz, hogy a rendszer az összegeket azonnal megjelenítse, és az összegek kiszámításához explicit műveletre van szükség. Ehhez kattintson a láblécben a **Kiszámítás** gombra, vagy kattintson az jobb egérgombbal egy oszlopra, és válassza az **Összeg ebben az oszlopban** lehetőséget.  

Ha a kiszámítás túl sokáig tart, akkor a művelet a **Mégse** gombra kattintva érvényteleníthető. Néha azonban előfordulhat, hogy az adathalmaz túl nagy az összegek kiszámításához (a szervezet által meghatározott korlát), és a program értesíti, hogy tovább kell szűrnie az adatokat.

A program automatikusan frissíti az összegeket az adathalmazban lévő sorok frissítése, törlése vagy létrehozása során.  

## <a name="grouping-data"></a>Adatok csoportosítása
Az üzleti felhasználóknak gyakran kell ad hoc adatelemzést végezniük. Bár ez megoldható az adatok Microsoft Excel alkalmazásba való exportálásával és pivot táblákkal, a táblázatos rácsok **Csoportosítás** funkciója lehetővé teszi, hogy a felhasználok a Finance and Operations alkalmazásokban is érdekes módon szervezzék az adataikat. Mivel ez a funkció kiterjeszti az **Összegek** funkciót, a **Csoportosítás** azt is lehetővé teszi, hogy egy csoport szintjén részösszegek megadásával jelentőségteljes betekintést nyerjen az adatokba.

A funkció használatához kattintson a jobb egérgombbal a csoportosítani kívánt oszlopra, és válassza ki a **Csoportosítás az oszlop szerint** lehetőséget. Ez a művelet a kiválasztott oszlop szerint rendezi az adatokat, egy új csoportosítási oszlopot ad hozzá a rácshoz, majd az egyes csoportok elejére „fejlécsorokat” szúr be. Ezek a fejlécsorok a következő információkat tartalmazzák az egyes csoportokról: 
-  A csoport adatértéke 
-  Oszlop címkéje (ez az információ különösen akkor hasznos, ha a csoportosítás több szintje támogatott.)
-  A csoportban levő adatsorok száma
-  Részösszegek az összes olyan oszlophoz, amelyet összegek megjelenítésére konfiguráltak

A [Mentett nézetek](saved-views.md) engedélyezése esetén ezt a csoportosítást személyre szabhatja az oldal legközelebbi meglátogatásakori gyors hozzáférés részeként.  

Ha egy másik oszlophoz jelöli ki a **Csoportosítás az oszlop szerint** lehetőséget, akkor a program felülírja az eredeti csoportosítást, mivel a 10.0.9-es verzió platform Update 33 esetén csak egy csoportosítási szint támogatott.

Ha vissza szeretné vonni a csoportosítást egy rácsban, kattintson a jobb gombbal a csoportosítási oszlopra, és válassza a **Szétválasztás** lehetőséget.  


## <a name="evaluating-math-expressions"></a>Matematikai kifejezések kiértékelése
A hatékonyság javításaként a felhasználók matematikai képleteket írhatnak be a rács numerikus celláiba. A számítást nem kell a rendszeren kívüli alkalmazásban végezniük. Ha például a **=15\*4** értéket adja meg, majd a **Tab** billentyű lenyomásával kilép a mezőből, akkor a rendszer kiértékeli a kifejezést, majd a mezőbe a **60** értéket menti.

Ha azt szeretné, hogy a rendszer bizonyos értékeket kifejezésként ismerjen fel, akkor az értéket egyenlőségjellel (**=**) kell bevezetnie. A támogatott operátorokkal és szintaxissal kapcsolatos további tudnivalókat lásd: [Támogatott matematikai szimbólumok](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).  
