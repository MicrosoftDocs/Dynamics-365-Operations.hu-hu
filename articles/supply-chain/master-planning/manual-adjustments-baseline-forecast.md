---
title: "A kiinduló előrejelzés manuális kiigazítása"
description: "Ez a cikk bemutatja, hogyan végezhet a manuális kiigazítást egy kiinduló előrejelzésen és hogyan tekintheti meg az előrejelzés részleteit."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72704
ms.assetid: e7c5d44e-07bc-40b1-a4b3-8ba46483ef9e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 218374cdb6b5588648422d97c04fb60f26e47ac7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="make-manual-adjustments-to-the-baseline-forecast"></a><span data-ttu-id="cf6b8-103">A kiinduló előrejelzés manuális kiigazítása</span><span class="sxs-lookup"><span data-stu-id="cf6b8-103">Make manual adjustments to the baseline forecast</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cf6b8-104">Ez a cikk bemutatja, hogyan végezhet a manuális kiigazítást egy kiinduló előrejelzésen és hogyan tekintheti meg az előrejelzés részleteit.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-104">This article explains how you can make manual adjustments to a baseline forecast and view details of the forecast.</span></span> 

<span data-ttu-id="cf6b8-105">Manuális kiigazítások elvégzése előtt fontos tisztázni néhány, különféle oldalakon megjelenő fogalmat.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-105">Before you make manual adjustments, it's important that you understand a few concepts on various pages.</span></span>

## <a name="grid-on-the-adjusted-demand-forecast-page"></a><span data-ttu-id="cf6b8-106">A Módosított igény-előrejelzés oldalon lévő rács</span><span class="sxs-lookup"><span data-stu-id="cf6b8-106">Grid on the Adjusted demand forecast page</span></span>
<span data-ttu-id="cf6b8-107">A **Módosított igény-előrejelzés** oldal tartalmaz egy rácsot, amelynek szerkezete a következő:</span><span class="sxs-lookup"><span data-stu-id="cf6b8-107">The **Adjusted demand forecast** page includes a grid that has the following structure:</span></span>

-   <span data-ttu-id="cf6b8-108">Az első oszlopban azok a cikkek, cikkfelosztási kulcsok, vállalatok, stb. jelennek meg, amelyekre vonatkozóan az előrejelzést generálták.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-108">The first column shows the items, item allocation keys, companies, and so on, that the forecast has been generated for.</span></span> <span data-ttu-id="cf6b8-109">Az oldal alcíme a rácsban megjelenített aktuális előrejelzési dimenziókat írja le.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-109">The subtitle of the page provides a description of the current forecast dimensions that are shown in the grid.</span></span> <span data-ttu-id="cf6b8-110">Ha például az oldal alcíme **Vállalat / Hely / Cikkfelosztási kulcs**, és a rács egyik sorának fejléce **USMF / 1 / D\__Alloc**, akkor az a sor az USMF vállalatra, 1. helyre és **D\__Alloc** cikkfelosztási kulcsra vonatkozó előrejelzést mutatja.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-110">For example, if the subtitle of the page is **Company / Site / Item allocation key**, and one of the row headers in the grid is **USMF / 1 / D\_Alloc**, that row shows the forecast for the USMF company, site 1, and the **D\_Alloc** item allocation key.</span></span>
-   <span data-ttu-id="cf6b8-111">A további oszlopok azokat az előrejelzési időszakokat jelölik, amelyekre az előrejelzést generálták.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-111">Subsequent columns represent the forecast buckets that the forecast has been generated for.</span></span> <span data-ttu-id="cf6b8-112">Az egyes oszlopfejlécek az adott oszlopban megjelenített előrejelzési időszak első napját adják meg.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-112">Each column header is the first date of the forecast bucket that the column shows.</span></span>
-   <span data-ttu-id="cf6b8-113">A cellákban lévő értékek mutatják az előrejelzést, amely egyetlen cikkre, cikkfelosztási kulcsra, stb. és az adott előrejelzési időszakra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-113">The values in the cells represent the forecast for one item, item allocation key, and so on, for that specific forecast bucket.</span></span>

## <a name="forecast-aggregation-and-deaggregation"></a><span data-ttu-id="cf6b8-114">Előrejelzés aggregációja és deaggregációja.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-114">Forecast aggregation and deaggregation</span></span>
<span data-ttu-id="cf6b8-115">Az oldal alcíme megmutatja az előrejelzés-aggregáció szintjét.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-115">The subtitle of the page shows the level of forecast aggregation.</span></span> 

<span data-ttu-id="cf6b8-116">Ha például az oldal alcíme **Vállalat / Hely / Felosztási kulcs / Cikkszám / Szín / Méret / Konfiguráció / Stílus**, nincs előrejelzés-aggregáció, és az előrejelzés a cikk és cikkdimenziók szintjén jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-116">For example, if the subtitle of the page is **Company / Site / Allocation key / Item number / Color / Size / Configuration / Style**, there is no forecast aggregation, and the forecast is shown at the level of the item and its dimensions.</span></span> <span data-ttu-id="cf6b8-117">Az aggregáció módosításához használja az **Előrejelzési dimenziók megváltoztatása** oldalt, amelyet alkalmazás menüjéből nyithat meg.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-117">To change the aggregation, use the **Change forecast dimensions** page, which you can open from the application menu.</span></span> 

<span data-ttu-id="cf6b8-118">Az előrejelzés módosításához kattintson bármelyik elérhető cellára, és írja be a kiigazított előrejelzési értéket.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-118">To modify the forecast, click in any of the cells that are available, and type the adjusted forecast value.</span></span> <span data-ttu-id="cf6b8-119">A szerkesztett cella ezután rögtön félkövérré válik, ezzel jelezve, hogy a benne látható előrejelzést nem az igény-előrejelzési szolgáltatás hozta létre, hanem az egy manuálisan kiigazított érték.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-119">The edited cell immediately becomes bold to indicate that the forecast that it shows isn't the forecast that the demand forecasting service created, but has been manually adjusted.</span></span> 

<span data-ttu-id="cf6b8-120">Ha módosítja az aggregációt annak érdekében, hogy az oldal összesítettebb adatokat jelenítsen meg, az aggregált előrejelzést alkotó egyedi előrejelzési sorokat az **Igény-előrejelzési sorok** oldalon láthatja.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-120">If you change the aggregation to make the page show more aggregated data, you can use the **Demand forecast lines** page to see the individual forecast lines that make up the aggregated forecast.</span></span> 

<span data-ttu-id="cf6b8-121">Tegyük fel például, hogy Ön a cikk szintjén generálta az előrejelzést, de tudja, hogy az adott cikk iránti kereslet egy promóció vagy hasonló esemény miatt minden helyen nőni fog.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-121">For example, you've generated the forecast at the item level, but you know that the demand for this item will increase across all sites because of a promotion or another similar event.</span></span> <span data-ttu-id="cf6b8-122">Ebben az esetben az **Előrejelzési dimenziók megváltoztatása** oldalon megadhatja az aggregációt a következőképpen: **Vállalat / Cikkfelosztási kulcs / Cikk**.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-122">In this case, you can set the aggregation to **Company / Item allocation key / Item** on the **Change forecast dimensions** page.</span></span> <span data-ttu-id="cf6b8-123">Kiigazíthatja a cikkre vonatkozó globális, minden helyre kiterjedő előrejelzést a **Módosított igény-előrejelzés** rácsban.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-123">You can adjust the global forecast for the item across all sites in the **Adjusted demand forecast** grid.</span></span> <span data-ttu-id="cf6b8-124">A változtatás egyes helyekre való hatásának megtekintéséhez nyissa meg az **Igény-előrejelzési sorok** oldalt.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-124">To see the effect of your change across all sites, open the **Demand forecast lines** page.</span></span> <span data-ttu-id="cf6b8-125">Ezen az oldalon minden egyes helynél megjelenik egy, az adott cikkre vonatkozó sor, továbbá megjelenik a kiigazított előrejelzési mennyiség és az eredeti előrejelzési mennyiség.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-125">On this page, you will see one line for the item for each site, the adjusted forecast quantity, and the original forecast quantity.</span></span> 

<span data-ttu-id="cf6b8-126">Ha az előre jelzett mennyiség kiigazítása aggregált szinten történik, a rendszer súlyozott felosztás alapján felosztja a változást az aggregációt alkotó sorok között.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-126">When the adjustment of the forecasted quantity is made at an aggregated level, the system uses weighted allocation to distribute the change among the lines that create the aggregation.</span></span> 

<span data-ttu-id="cf6b8-127">Manuális kiigazítást az **Igény-előrejelzési sorok** oldalon is végezhet az **Összmennyiség** értékének, vagy a deaggregációs rács **Mennyiség** celláinak módosításával.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-127">You can also make manual adjustments on the **Demand forecast lines** page, by modifying either the **Total quantity** value or the **Quantity** cells in the de-aggregation grid.</span></span>

## <a name="viewing-details-of-the-forecast"></a><span data-ttu-id="cf6b8-128">Az előrejelzés részleteinek megtekintése</span><span class="sxs-lookup"><span data-stu-id="cf6b8-128">Viewing details of the forecast</span></span>
<span data-ttu-id="cf6b8-129">Az előrejelzéssel kapcsolatosan további információkat tekinthet meg az **Igény-előrejelzés részletei** oldal megnyitásával.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-129">You can open the **Demand forecast details** page to view more information about the forecast.</span></span> 

<span data-ttu-id="cf6b8-130">Az **Igény-előrejelzés részletei** oldalon az alábbi adatok jelennek meg grafikus és táblázatos formában:</span><span class="sxs-lookup"><span data-stu-id="cf6b8-130">The **Demand forecast details** page shows the following information in graphical and tabular formats:</span></span>

-   <span data-ttu-id="cf6b8-131">Igényelőzmények, amelyeken az előrejelzések alapulnak.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-131">The historical demand that the forecast predictions are based on.</span></span>
-   <span data-ttu-id="cf6b8-132">Az Alaptervezés által használt aktuális előrejelzés.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-132">The current forecast that is used by Master planning.</span></span>
-   <span data-ttu-id="cf6b8-133">Az új igény-előrejelzési értékek és az azokat kiigazító, manuálisan megadott mennyiségek.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-133">The new demand forecast values and the amounts they have been manually adjusted by.</span></span>
-   <span data-ttu-id="cf6b8-134">Az előre jelzett értékek megbízhatósági intervalluma.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-134">The confidence interval for the forecasted values.</span></span>
-   <span data-ttu-id="cf6b8-135">Az előrejelzés generálásához használt előrejelzési modell.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-135">The forecast model that was used to generate the forecast.</span></span> <span data-ttu-id="cf6b8-136">Aggregált adatok megtekintésekor egy lista jelenik meg az összes aggregált idősorozathoz használt összes módszerrel.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-136">If you're viewing aggregated data, you will see the list of all the methods that were used for all the aggregated time series.</span></span>
-   <span data-ttu-id="cf6b8-137">A belső modellpontosság (MAPE).</span><span class="sxs-lookup"><span data-stu-id="cf6b8-137">The internal model accuracy (MAPE).</span></span> <span data-ttu-id="cf6b8-138">Az előrejelzés pontosságával kapcsolatos további információkért lásd: [Előrejelzés pontosságának megfigyelése](monitor-forecast-accuracy.md).</span><span class="sxs-lookup"><span data-stu-id="cf6b8-138">For more information about forecast accuracy, see [Monitoring forecast accuracy](monitor-forecast-accuracy.md).</span></span>

<span data-ttu-id="cf6b8-139">**Megjegyzések:**</span><span class="sxs-lookup"><span data-stu-id="cf6b8-139">**Notes:**</span></span>

-   <span data-ttu-id="cf6b8-140">Az oldal **Előrejelzés** szakaszában megjelenő megbízhatósági intervallum a megbízhatósági intervallum alsó és felső határértéke közti különbséget mutatja meg.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-140">The confidence interval that appears in the **Forecast** section of the page represents the difference between the confidence interval upper limit and the confidence interval lower limit.</span></span> <span data-ttu-id="cf6b8-141">Az alsó és felső határértékek megtekintéséhez vigye az egérmutatót az **Igényelőzmények és előrejelzés grafikusan** szakasz diagramja fölé.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-141">To see the values for the upper and lower limits, hover over the chart in the **Historical demand and forecast graphically** section.</span></span>
-   <span data-ttu-id="cf6b8-142">Amennyiben a Finance and Operations Igény-előrejelző Microsoft Azure Machine Learning szolgáltatást használja, lehetősége van megadni azt a százalékos megbízhatósági szintet, amellyel a generált előrejelzésnek rendelkeznie kell.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-142">If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, you can specify the confidence level percentage that the forecast that is generated should have.</span></span> <span data-ttu-id="cf6b8-143">A megbízhatósági intervallum olyan értékek tartományból áll, amelyek az igény-előrejelzés jó becslését adják.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-143">A confidence interval consists of a range of values that act as good estimates for the demand forecast.</span></span> <span data-ttu-id="cf6b8-144">A 95%-os megbízhatósági szint azt jelenti, hogy 5% a kockázata annak, hogy az igény-előrejelzés eredménye a megbízhatósági intervallum tartományán kívül esik.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-144">A 95-percent confidence level percentage indicates that there is a 5-percent risk that the demand forecast falls outside the confidence interval range.</span></span>

<span data-ttu-id="cf6b8-145">Az előrejelzés manuális kiigazításait az **Igény-előrejelzés részletei** oldalon is elvégezheti, az **Előrejelzés** szakasz **Előrejelzés** sorában lévő értékek megváltoztatásával.</span><span class="sxs-lookup"><span data-stu-id="cf6b8-145">You can also make manual adjustments to the forecast on the **Demand forecast details** page, by modifying the values in the **Forecast** row in the **Forecast** section.</span></span>

<a name="see-also"></a><span data-ttu-id="cf6b8-146">Lásd még</span><span class="sxs-lookup"><span data-stu-id="cf6b8-146">See also</span></span>
--------

[<span data-ttu-id="cf6b8-147">Az előrejelzési pontosság megfigyelése</span><span class="sxs-lookup"><span data-stu-id="cf6b8-147">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)

[<span data-ttu-id="cf6b8-148">Statisztikai kiinduló előrejelzés generálása</span><span class="sxs-lookup"><span data-stu-id="cf6b8-148">Generating a statistical baseline forecast</span></span>](generate-statistical-baseline-forecast.md)



