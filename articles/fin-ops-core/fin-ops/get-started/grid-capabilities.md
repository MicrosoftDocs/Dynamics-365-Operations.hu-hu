---
title: Rács funkciói
description: Ez a témakör ismerteti a rács vezérlőelem számos erőteljes funkcióját. Az új rács funkciónak engedélyezve kell lennie ahhoz, hogy hozzáférhessen ezekhez a funkciókhoz.
author: jasongre
manager: AnnBe
ms.date: 01/20/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: b49d7823f48bcc9cdbb56b87d5fa72d46ddfa15c
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019811"
---
# <a name="grid-capabilites"></a>Rács funkciói

[!include [banner](../includes/banner.md)]

Az új rács vezérlőelem számos hasznos és erőteljes funkciót tartalmaz, amelyek a felhasználó hatékonyságának növelésére, az adatokkal kapcsolatos érdekesebb nézetek kialakítására és az adatokkal kapcsolatos jelentőségteljes rálátás megszerzésére használhatók. Ez a cikk a következő funkciókat mutatja be: 

-  Teljes összegek számítása
-  Adatok csoportosítása
-  A rendszer előtt történő gépelés
-  Matematikai kifejezések kiértékelése 

## <a name="calculating-totals"></a>Teljes összegek számítása
A Finance and Operations alkalmazásokban a felhasználók a számokat tartalmazó oszlopok alján látható összesítéseket megtekinthetik a rácsokban. Ezeket az összegeket a rács alján látható lábléc szakasz mutatja. 

### <a name="showing-the-grid-footer"></a>A rács láblécének megjelenítése
A Finance and Operations alkalmazások minden táblázatos rácsának alján van egy lábléc, amelyen a megjelenített adatokkal kapcsolatos értékes információk jeleníthetők meg. Ilyen adatok a következők: 
-  A táblázatból kiválasztott sorok száma (ha egynél több rekord van kiválasztva)
-  Végösszegek a konfigurált numerikus oszlopok alján
-  Az adathalmazban lévő sorok száma összesen 

Alapértelmezetten ez a lábléc rejtett, de egyszerűen be lehet kapcsolni. A rács láblécének megjelenítéséhez kattintson a jobb gombbal a rács egy oszlopának fejlécére, és válassza ki a **Lábléc megjelenítése** lehetőséget. Miután egy adott rácsnál bekapcsolta a láblécet, a rendszer emlékezni fog a beállításra mindaddig, amíg a felhasználó úgy nem dönt, hogy elrejti a láblécet. Ez úgy végezhető el, hogy a jobb gombbal rákattint egy oszlop fejlécére, és kiválasztja a **Lábléc elrejtése** lehetőséget.  Ne feledje, hogy egy jövőbeli frissítésben a **Lábléc megjelenítése/elrejtése** műveletet valószínűleg áthelyezzük. 

### <a name="specifying-columns-with-totals"></a>Összesítéssel ellátott oszlopok megadása
Jelenleg alapértelmezetten egy oszlop sem jeleníti meg az összegeket. Ezt a rács oszlopai szélességének beállításához hasonlóan egyszeri beállítási tevékenységnek tekintjük. Miután megadta, hogy szeretné egy oszlop összegeit megtekinteni, a rendszer a lap legközelebbi meglátogatásakor emlékezni fog a beállításra.  

Egy oszlopot kétféleképpen lehet az összegek megjelenítésére konfigurálni: 
1.  Kattintson a jobb gombbal a kívánt oszlopra, és válassza az **Összeg ebben az oszlopban** lehetőséget. Ez a művelet három dolgot eredményez. Először is láthatóvá teszi a láblécet. Másodszor, a program menti a beállítást, hogy látni szeretné az oszlopra vonatkozó összeget. Harmadszor, ez a művelet elindít egy összesítésszámítást ehhez az oszlophoz, illetve az összes többihez is, amelyeknél korábban már beállította az összegek megtekintését. Az összeg megjelenítéséhez szükséges idő közvetlenül függ az összesítendő adathalmaz méretétől.  

2.  Miután megtörtént a lábléc megjelenítése, rákattinthat azon oszlop alján lévő láblécen látható **Összeg megjelenítése** gombra, amely összegét meg akarja tekinteni. Ha nincsenek konfigurált oszlopok, akkor az összes numerikus oszlop esetében megjelenik az **Összeg megjelenítése** gomb. Ha legalább egy oszlopot konfigurált összesítésekhez, akkor az **Összeg megjelenítése** gomb csak a rámutatással vagy a fókusszal érhető el. Ez a művelet egyszerűen csak menti a beállítást, hogy ebben az oszlopban lévő jövőbeli látogatások során az összeg látható legyen. Ezt az állapotot a láblécben megjelenő gondolatjel jelöli (vagy, ha az adathalmaz kellően kicsi, az összeg azonnal megjelenik).

Ha hibázik, és a továbbiakban nem szeretné megjeleníteni az adott oszlopban szereplő összegeket, kattintson az egér jobb oldali gombjával az oszlopra, és válassza az **Összeg elrejtése** lehetőséget, vagy jelölje be az oszlop láblécében az **Összeg elrejtése** gombot. Ezt a beállítást a program a lap későbbi megtekintései esetére is elmenti. 

### <a name="calculating-totals"></a>Teljes összegek számítása
Ha olyan oldalra lép, amelyen látható a lábléc, és az oszlopokat már beállították összesítésekhez, akkor megtörténhet, hogy az összesítések nem jelennek meg a láblécben. A viselkedés függ az oldalon levő adathalmaz méretétől. Ha az adathalmaz kellően kicsi, a program automatikusan megjeleníti az összegeket, valamint az adathalmaz sorainak számát. Ha a láblécben az összesítésre konfigurált oszlopokban gondolatjeleket lát, akkor az adathalmaz túl nagy ahhoz, hogy a rendszer az összegeket azonnal megjelenítse, és az összegek kiszámításához explicit műveletre van szükség. Ehhez kattintson a láblécben a **Kiszámítás** gombra, vagy kattintson az jobb egérgombbal egy oszlopra, és válassza az **Összeg ebben az oszlopban** lehetőséget.  

Ha a kiszámítás túl sokáig tart, akkor a művelet a **Mégse** gombra kattintva érvényteleníthető. Néha azonban előfordulhat, hogy az adathalmaz túl nagy az összegek kiszámításához (a szervezet által meghatározott korlát), és a program értesíti, hogy tovább kell szűrnie az adatokat.

A program automatikusan frissíti az összegeket az adathalmazban lévő sorok frissítése, törlése vagy létrehozása során.  

## <a name="grouping-data"></a>Adatok csoportosítása
Az üzleti felhasználóknak gyakran kell ad hoc adatelemzést végezniük. Bár ez megoldható az adatok Microsoft Excel alkalmazásba való exportálásával és pivot táblákkal, a táblázatos rácsok **Csoportosítás** funkciója lehetővé teszi, hogy a felhasználok a Finance and Operations alkalmazásokban is érdekes módon szervezzék az adataikat. Mivel ez a funkció kiterjeszti az **Összegek** funkciót, a **Csoportosítás** azt is lehetővé teszi, hogy egy csoport szintjén részösszegek megadásával jelentőségteljes betekintést nyerjen az adatokba.

A funkció használatához kattintson a jobb egérgombbal a csoportosítani kívánt oszlopra, és válassza ki a **Csoportosítás az oszlop szerint** lehetőséget. Ez a művelet a kiválasztott oszlop szerint rendezi az adatokat, egy új csoportosítási oszlopot ad hozzá a rácshoz, majd az egyes csoportok elejére „fejlécsorokat” szúr be. Ezek a fejlécsorok a következő információkat tartalmazzák az egyes csoportokról: 
-  A csoport adatértéke 
-  Oszlop címkéje. Ez a funkció elsősorban akkor hasznos, ha a csoportosítás több szintje is támogatott.  
-  A csoportban levő adatsorok száma
-  Részösszegek az összes olyan oszlophoz, amelyet összegek megjelenítésére konfiguráltak

A [Mentett nézetek](saved-views.md) engedélyezése esetén ezt a csoportosítást személyre szabhatja az oldal legközelebbi meglátogatásakori gyors hozzáférés részeként.  

Ha egy oszlopon jelöli ki a **Csoportosítás az oszlop szerint** lehetőséget, akkor a program felülírja az eredeti csoportosítást, mivel a 10.0.9/platform Update 33 esetén csak egy csoportosítási szint támogatott.

Ha vissza szeretné vonni a csoportosítást egy rácsban, kattintson a jobb gombbal a csoportosítási oszlopra, és válassza a **Szétválasztás** lehetőséget.  


## <a name="evaluating-math-expressions"></a>Matematikai kifejezések kiértékelése
A termelékenység növelése érdekében a felhasználó matematikai képleteket vihet be egy rács numerikus celláiba ahelyett, hogy a számítást egy rendszeren kívüli alkalmazásban kellene elvégeznie. Megadhatja például a **=15\*4** értéket, és a tabulátorral kiléphet a mezőből. A rendszer kiértékeli a kifejezést, majd menti a „60” értéket a mezőbe.

Ha azt szeretné, hogy a rendszer bizonyos értékeket kifejezésként ismerjen fel, akkor az értéket egyenlőségjellel (**=**) kell bevezetnie. A támogatott operátorokkal és szintaxissal kapcsolatos további tudnivalókat lásd: [Támogatott matematikai szimbólumok](http://redhivesoftware.github.io/math-expression-evaluator/#supported-maths-symbols).  
