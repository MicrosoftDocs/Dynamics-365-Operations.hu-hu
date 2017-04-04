---
title: "Hajtsa végre a módosításokat az eredeti előrejelzési kézi"
description: "Ez a cikk bemutatja, hogyan végezhet a manuális kiigazítást egy kiinduló előrejelzésen és hogyan tekintheti meg az előrejelzés részleteit."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 24caafcd01875f04cf3ae5299aadcf9b38ac0e15
ms.lasthandoff: 03/31/2017


---

# <a name="make-manual-adjustments-to-the-baseline-forecast"></a>Hajtsa végre a módosításokat az eredeti előrejelzési kézi

Ez a cikk bemutatja, hogyan végezhet a manuális kiigazítást egy kiinduló előrejelzésen és hogyan tekintheti meg az előrejelzés részleteit. 

Manuális kiigazítások elvégzése előtt fontos tisztázni néhány, különféle oldalakon megjelenő fogalmat.

## <a name="grid-on-the-adjusted-demand-forecast-page"></a>A Módosított igény-előrejelzés oldalon lévő rács
A **Módosított igény-előrejelzés** oldal tartalmaz egy rácsot, amelynek szerkezete a következő:

-   Az első oszlopban azok a cikkek, cikkfelosztási kulcsok, vállalatok, stb. jelennek meg, amelyekre vonatkozóan az előrejelzést generálták. Az oldal alcíme a rácsban megjelenített aktuális előrejelzési dimenziókat írja le. Például, ha a lap az alcím **cég / hely / cikk felosztási kulcs**, és a rács a sorfejlécek egyik **USMF / 1 / D\_felosztás %**, sor mutatja az előrejelzés, a USMF vállalat, 1, hely és a **D\_lefoglalása** cikkfelosztási kulcs.
-   A további oszlopok azokat az előrejelzési időszakokat jelölik, amelyekre az előrejelzést generálták. Az egyes oszlopfejlécek az adott oszlopban megjelenített előrejelzési időszak első napját adják meg.
-   A cellákban lévő értékek mutatják az előrejelzést, amely egyetlen cikkre, cikkfelosztási kulcsra, stb. és az adott előrejelzési időszakra vonatkozik.

## <a name="forecast-aggregation-and-deaggregation"></a>Az összesítés előrejelzés és a deaggregation
Az oldal alcíme megmutatja az előrejelzés-aggregáció szintjét. 

Ha például az oldal alcíme **Vállalat / Hely / Felosztási kulcs / Cikkszám / Szín / Méret / Konfiguráció / Stílus**, nincs előrejelzés-aggregáció, és az előrejelzés a cikk és cikkdimenziók szintjén jelenik meg. Az aggregáció módosításához használja az** Előrejelzési dimenziók megváltoztatása** oldalt, amelyet alkalmazás menüjéből nyithat meg. 

Az előrejelzés módosításához kattintson bármelyik elérhető cellára, és írja be a kiigazított előrejelzési értéket. A szerkesztett cella ezután rögtön félkövérré válik, ezzel jelezve, hogy a benne látható előrejelzést nem az igény-előrejelzési szolgáltatás hozta létre, hanem az egy manuálisan kiigazított érték. 

Ha módosítja az aggregációt annak érdekében, hogy az oldal összesítettebb adatokat jelenítsen meg, az aggregált előrejelzést alkotó egyedi előrejelzési sorokat az **Igény-előrejelzési sorok** oldalon láthatja. 

Tegyük fel például, hogy Ön a cikk szintjén generálta az előrejelzést, de tudja, hogy az adott cikk iránti kereslet egy promóció vagy hasonló esemény miatt minden helyen nőni fog. Ebben az esetben az **Előrejelzési dimenziók megváltoztatása** oldalon megadhatja az aggregációt a következőképpen: **Vállalat / Cikkfelosztási kulcs / Cikk**. Kiigazíthatja a cikkre vonatkozó globális, minden helyre kiterjedő előrejelzést a **Módosított igény-előrejelzés** rácsban. A változtatás egyes helyekre való hatásának megtekintéséhez nyissa meg az **Igény-előrejelzési sorok** oldalt. Ezen az oldalon minden egyes helynél megjelenik egy, az adott cikkre vonatkozó sor, továbbá megjelenik a kiigazított előrejelzési mennyiség és az eredeti előrejelzési mennyiség. 

Az előre jelzett mennyiség kiigazítása az összesített szinten történik, a rendszer a módosítás az összesítés létrehozott sorok között elosztandó használja súlyozott felosztás. 

Manuális kiigazítást az **Igény-előrejelzési sorok** oldalon is végezhet az **Összmennyiség** értékének, vagy a deaggregációs rács **Mennyiség** celláinak módosításával.

## <a name="viewing-details-of-the-forecast"></a>Az előrejelzés részleteinek megtekintése
Az előrejelzéssel kapcsolatosan további információkat tekinthet meg az** Igény-előrejelzés részletei** oldal megnyitásával. 

Az **Igény-előrejelzés részletei** oldalon az alábbi adatok jelennek meg grafikus és táblázatos formában:

-   Igényelőzmények, amelyeken az előrejelzések alapulnak.
-   Az Alaptervezés által használt aktuális előrejelzés.
-   Az új igény-előrejelzési értékek és az azokat kiigazító, manuálisan megadott mennyiségek.
-   Az előre jelzett értékek megbízhatósági intervalluma.
-   Az előrejelzés generálásához használt előrejelzési modell. Aggregált adatok megtekintésekor egy lista jelenik meg az összes aggregált idősorozathoz használt összes módszerrel.
-   A belső modellpontosság (MAPE). Az előrejelzés pontosságával kapcsolatos további információkért lásd: [Előrejelzés pontosságának megfigyelése](monitor-forecast-accuracy.md).

**Megjegyzések:**

-   Az oldal **Előrejelzés** szakaszában megjelenő megbízhatósági intervallum a megbízhatósági intervallum alsó és felső határértéke közti különbséget mutatja meg. Az alsó és felső határértékek megtekintéséhez vigye az egérmutatót az **Igényelőzmények és előrejelzés grafikusan** szakasz diagramja fölé.
-   A Dynamics 365 műveletek igény-előrejelzés Microsoft Azure gép Learning szolgáltatás használatakor megadhatja az előrejelzés generált kell megbízhatósági szint százalékos. A megbízhatósági intervallum olyan értékek tartományból áll, amelyek az igény-előrejelzés jó becslését adják. A 95%-os megbízhatósági szint azt jelenti, hogy 5% a kockázata annak, hogy az igény-előrejelzés eredménye a megbízhatósági intervallum tartományán kívül esik.

Az előrejelzés manuális kiigazításait az **Igény-előrejelzés részletei** oldalon is elvégezheti, az **Előrejelzés** szakasz **Előrejelzés** sorában lévő értékek megváltoztatásával.

<a name="see-also"></a>Lásd még
--------

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)

[Generating a statistical baseline forecast](generate-statistical-baseline-forecast.md)


