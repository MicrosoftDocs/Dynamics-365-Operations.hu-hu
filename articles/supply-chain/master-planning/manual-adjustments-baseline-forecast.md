---
title: A kiinduló előrejelzés manuális kiigazítása
description: Ez a témakör bemutatja, hogyan végezhet a manuális kiigazítást egy kiinduló előrejelzésen és hogyan tekintheti meg az előrejelzés részleteit.
author: roxanadiaconu
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: afdcbb98c96b2a685f64a16886b9a064ed13c2c0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967030"
---
# <a name="make-manual-adjustments-to-the-baseline-forecast"></a>A kiinduló előrejelzés manuális kiigazítása

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan végezhet a manuális kiigazítást egy kiinduló előrejelzésen és hogyan tekintheti meg az előrejelzés részleteit. 

Manuális kiigazítások elvégzése előtt fontos tisztázni néhány, különféle oldalakon megjelenő fogalmat.

## <a name="grid-on-the-adjusted-demand-forecast-page"></a>A Módosított igény-előrejelzés oldalon lévő rács
A **Módosított igény-előrejelzés** oldal tartalmaz egy rácsot, amelynek szerkezete a következő:

-   Az első oszlopban azok a cikkek, cikkfelosztási kulcsok, vállalatok, stb. jelennek meg, amelyekre vonatkozóan az előrejelzést generálták. Az oldal alcíme a rácsban megjelenített aktuális előrejelzési dimenziókat írja le. Ha például az oldal alcíme **Vállalat / Hely / Cikkfelosztási kulcs**, és a rács egyik sorának fejléce **USMF / 1 / D\__Alloc**, akkor az a sor az USMF vállalatra, 1. helyre és **D\__Alloc** cikkfelosztási kulcsra vonatkozó előrejelzést mutatja.
-   A további oszlopok azokat az előrejelzési időszakokat jelölik, amelyekre az előrejelzést generálták. Az egyes oszlopfejlécek az adott oszlopban megjelenített előrejelzési időszak első napját adják meg.
-   A cellákban lévő értékek mutatják az előrejelzést, amely egyetlen cikkre, cikkfelosztási kulcsra, stb. és az adott előrejelzési időszakra vonatkozik.

## <a name="forecast-aggregation-and-de-aggregation"></a>Előrejelzés aggregációja és deaggregációja.
Az oldal alcíme megmutatja az előrejelzés-aggregáció szintjét. 

Ha például az oldal alcíme **Vállalat / Hely / Felosztási kulcs / Cikkszám / Szín / Méret / Konfiguráció / Stílus**, nincs előrejelzés-aggregáció, és az előrejelzés a cikk és cikkdimenziók szintjén jelenik meg. Az aggregáció módosításához használja az **Előrejelzési dimenziók megváltoztatása** oldalt, amelyet alkalmazás menüjéből nyithat meg. 

Az előrejelzés módosításához kattintson bármelyik elérhető cellára, és írja be a kiigazított előrejelzési értéket. A szerkesztett cella ezután rögtön félkövérré válik, ezzel jelezve, hogy a benne látható előrejelzést nem az igény-előrejelzési szolgáltatás hozta létre, hanem az egy manuálisan kiigazított érték. 

Ha módosítja az aggregációt annak érdekében, hogy az oldal összesítettebb adatokat jelenítsen meg, az aggregált előrejelzést alkotó egyedi előrejelzési sorokat az **Igény-előrejelzési sorok** oldalon láthatja. 

Tegyük fel például, hogy Ön a cikk szintjén generálta az előrejelzést, de tudja, hogy az adott cikk iránti kereslet egy promóció vagy hasonló esemény miatt minden helyen nőni fog. Ebben az esetben az **Előrejelzési dimenziók megváltoztatása** oldalon megadhatja az aggregációt a következőképpen: **Vállalat / Cikkfelosztási kulcs / Cikk**. Kiigazíthatja a cikkre vonatkozó globális, minden helyre kiterjedő előrejelzést a **Módosított igény-előrejelzés** rácsban. A változtatás egyes helyekre való hatásának megtekintéséhez nyissa meg az **Igény-előrejelzési sorok** oldalt. Ezen az oldalon minden egyes helynél megjelenik egy, az adott cikkre vonatkozó sor, továbbá megjelenik a kiigazított előrejelzési mennyiség és az eredeti előrejelzési mennyiség. 

Ha az előre jelzett mennyiség kiigazítása aggregált szinten történik, a rendszer súlyozott felosztás alapján felosztja a változást az aggregációt alkotó sorok között. 

Manuális kiigazítást az **Igény-előrejelzési sorok** oldalon is végezhet az **Összmennyiség** értékének, vagy a deaggregációs rács **Mennyiség** celláinak módosításával.

## <a name="viewing-details-of-the-forecast"></a>Az előrejelzés részleteinek megtekintése
Az előrejelzéssel kapcsolatosan további információkat tekinthet meg az **Igény-előrejelzés részletei** oldal megnyitásával. 

Az **Igény-előrejelzés részletei** oldalon az alábbi adatok jelennek meg grafikus és táblázatos formában:

-   Igényelőzmények, amelyeken az előrejelzések alapulnak.
-   Az Alaptervezés által használt aktuális előrejelzés.
-   Az új igény-előrejelzési értékek és az azokat kiigazító, manuálisan megadott mennyiségek.
-   Az előre jelzett értékek megbízhatósági intervalluma.
-   Az előrejelzés generálásához használt előrejelzési modell. Aggregált adatok megtekintésekor egy lista jelenik meg az összes aggregált idősorozathoz használt összes módszerrel.
-   A belső modellpontosság (MAPE). Az előrejelzés pontosságával kapcsolatos további információkért lásd: [Előrejelzés pontosságának megfigyelése](monitor-forecast-accuracy.md).

**Megjegyzések:**

-   Ha a Szolgáltatáskezelés segítségével engedélyezi az **Előrejelzési modellek kiválasztása az igény-előrejelzés részleteiben** lehetőséget, akkor kiválaszthatja a korábbi előrejelzésbe belefoglalni kívánt előrejelzési modelleket az **Igény-előrejelzés részletei** lapon.
-   Az oldal **Előrejelzés** szakaszában megjelenő megbízhatósági intervallum a megbízhatósági intervallum alsó és felső határértéke közti különbséget mutatja meg. Az alsó és felső határértékek megtekintéséhez vigye az egérmutatót az **Igényelőzmények és előrejelzés grafikusan** szakasz diagramja fölé.
-   Amennyiben az Igény-előrejelzés a Microsoft Azure gépi tanulás szolgáltatást használja, lehetősége van megadni azt a százalékos megbízhatósági szintet, amellyel a generált előrejelzésnek rendelkeznie kell. A megbízhatósági intervallum olyan értékek tartományból áll, amelyek az igény-előrejelzés jó becslését adják. A 95%-os megbízhatósági szint azt jelenti, hogy 5% a kockázata annak, hogy az igény-előrejelzés eredménye a megbízhatósági intervallum tartományán kívül esik.

Az előrejelzés manuális kiigazításait az **Igény-előrejelzés részletei** oldalon is elvégezheti, az **Előrejelzés** szakasz **Előrejelzés** sorában lévő értékek megváltoztatásával.

<a name="additional-resources"></a>További erőforrások
--------

[Előrejelzés pontosságának követése](monitor-forecast-accuracy.md)

[Statisztikai kiinduló előrejelzés létrehozása](generate-statistical-baseline-forecast.md)



