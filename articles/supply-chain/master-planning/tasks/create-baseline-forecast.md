--- 
title: "Kiinduló előrejelzés létrehozása"
description: "A termeléstervező létrehozhat egy kiinduló előrejelzést az idősorozat szerinti előrejelzési modell használatával vagy az igényelőzmények átmásolásával."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e6363ee48c0d13c79a6c623205dfa10f50d6070f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-baseline-forecast"></a><span data-ttu-id="0e063-103">Kiinduló előrejelzés létrehozása</span><span class="sxs-lookup"><span data-stu-id="0e063-103">Create a baseline forecast</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0e063-104">A termeléstervező létrehozhat egy kiinduló előrejelzést az idősorozat szerinti előrejelzési modell használatával vagy az igényelőzmények átmásolásával.</span><span class="sxs-lookup"><span data-stu-id="0e063-104">A production planner can create a baseline forecast either by using time series forecast models or by copying the historical demand.</span></span> <span data-ttu-id="0e063-105">Ez az eljárás bemutatja, hogyan hozhat létre kiinduló előrejelzést az egy cikkfelosztási kulcsot használó termékekhez az igényelőzmények átmásolásával.</span><span class="sxs-lookup"><span data-stu-id="0e063-105">This procedure shows how to copy the historical demand to create a baseline forecast for all products using one item allocation key.</span></span> 


## <a name="set-up-an-item-allocation-key"></a><span data-ttu-id="0e063-106">Cikkfoglalási kulcs beállítása</span><span class="sxs-lookup"><span data-stu-id="0e063-106">Set up an item allocation key</span></span>
1. <span data-ttu-id="0e063-107">Ugorjon az Alaptervezés > Beállítás > Vállalatközi tervezőcsoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e063-107">Go to Master planning > Setup > Intercompany planning groups.</span></span>
2. <span data-ttu-id="0e063-108">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="0e063-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="0e063-109">Például szűrjön a Név mezőben a „10” érték megadásával.</span><span class="sxs-lookup"><span data-stu-id="0e063-109">For example, filter on the Name field with a value of '10'.</span></span>
    * <span data-ttu-id="0e063-110">Az igény-előrejelzés a jogi személyek között történik.</span><span class="sxs-lookup"><span data-stu-id="0e063-110">Demand forecasting runs across legal entities.</span></span> <span data-ttu-id="0e063-111">Ezért kell beállítania egy vállalatközi tervezőcsoportba az összes céget, amelyek számára előrejelzéseket kíván generálni.</span><span class="sxs-lookup"><span data-stu-id="0e063-111">That's why you need to set up all the companies for which you want to generate forecasts in one intercompany planning group.</span></span>  
3. <span data-ttu-id="0e063-112">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="0e063-112">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="0e063-113">Kattintson a Cikkfelosztási kulcsok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e063-113">Click Item allocation keys.</span></span>
    * <span data-ttu-id="0e063-114">Válassza ki az összes cikkfelosztási kulcsot, amelyhez létre kívánja hozni az előrejelzést.</span><span class="sxs-lookup"><span data-stu-id="0e063-114">Select all the item allocation keys for which you want to create forecasts.</span></span>  
5. <span data-ttu-id="0e063-115">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0e063-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0e063-116">Válassza ki a D_Aloc cikkfelosztási kulcsot.</span><span class="sxs-lookup"><span data-stu-id="0e063-116">Select D_Aloc item allocation key.</span></span>  
6. <span data-ttu-id="0e063-117">Kattintson > .</span><span class="sxs-lookup"><span data-stu-id="0e063-117">Click >.</span></span>
7. <span data-ttu-id="0e063-118">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e063-118">Close the page.</span></span>
8. <span data-ttu-id="0e063-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e063-119">Close the page.</span></span>

## <a name="set-up-the-demand-forecasting-paramters"></a><span data-ttu-id="0e063-120">Igény-előrejelzési paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="0e063-120">Set up the demand forecasting paramters</span></span>
1. <span data-ttu-id="0e063-121">Ugorjon az Alaptervezés > Beállítás > Igény-előrejelzés > Igény-előrejelzési paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e063-121">Go to Master planning > Setup > Demand forecasting > Demand forecasting parameters.</span></span>
2. <span data-ttu-id="0e063-122">Bontsa ki Az előrejelzési algoritmus paraméterei szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0e063-122">Expand the Forecast algorithm parameters section.</span></span>
3. <span data-ttu-id="0e063-123">Az Előrejelzés-generálási stratégia mezőben válassza ki a „Korábbi igény átmásolása” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e063-123">In the Forecast generation strategy field, select 'Copy over historical demand'.</span></span>
4. <span data-ttu-id="0e063-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e063-124">Click Save.</span></span>

## <a name="create-a-baseline-forecast"></a><span data-ttu-id="0e063-125">Kiinduló előrejelzés létrehozása</span><span class="sxs-lookup"><span data-stu-id="0e063-125">Create a baseline forecast</span></span>
1. <span data-ttu-id="0e063-126">Ugorjon az Alaptervezés > Előrejelzés > Igény-előrejelzés > Statisztikai kiinduló előrejelzés generálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e063-126">Go to Master planning > Forecasting > Demand forecasting > Generate statistical baseline forecast.</span></span>
2. <span data-ttu-id="0e063-127">Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="0e063-127">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="0e063-128">Ha 2015. január 1-ei kezdődátumú értékesítési rendeléssel rendelkezik, adja meg ezt a dátumot.</span><span class="sxs-lookup"><span data-stu-id="0e063-128">If you have sales orders starting from January 1, 2015, enter this date.</span></span> <span data-ttu-id="0e063-129">Ellenkező esetben adja meg az értékesítési rendelés legkorábbi dátumát.</span><span class="sxs-lookup"><span data-stu-id="0e063-129">If you don't, enter the earliest date of your sales orders.</span></span>  
3. <span data-ttu-id="0e063-130">Adja meg a dátumot a „Záró dátum” mezőben.</span><span class="sxs-lookup"><span data-stu-id="0e063-130">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="0e063-131">Adja meg az értékesítési rendelések utolsó dátumát, például a „2015.03.31.” dátumot.</span><span class="sxs-lookup"><span data-stu-id="0e063-131">Enter the last date of your sales orders, for example '2015-03-31'.</span></span>  
4. <span data-ttu-id="0e063-132">Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="0e063-132">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="0e063-133">Adja meg a „2015.04.01.” dátumot.</span><span class="sxs-lookup"><span data-stu-id="0e063-133">Enter '2015-04-01'.</span></span> <span data-ttu-id="0e063-134">Ezt a napot automatikusan a következő előrejelzési időszak kezdő dátumaként használja majd a rendszer.</span><span class="sxs-lookup"><span data-stu-id="0e063-134">This date will be automatically calculated as the start date of the next forecasting bucket.</span></span>  
5. <span data-ttu-id="0e063-135">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0e063-135">Expand the Records to include section.</span></span>
6. <span data-ttu-id="0e063-136">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="0e063-136">Click Filter.</span></span>
7. <span data-ttu-id="0e063-137">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0e063-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0e063-138">Jelölje meg a sort, ahol a Mező = Vállalatközi tervezési csoport.</span><span class="sxs-lookup"><span data-stu-id="0e063-138">Mark the row where Field = Intercompany planning group.</span></span>  
8. <span data-ttu-id="0e063-139">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0e063-139">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="0e063-140">Adja meg az első feladatnál használt vállalatközi tervezési csoportot, például a 10-es számmal.</span><span class="sxs-lookup"><span data-stu-id="0e063-140">Type the intercompany planning group, for example, 10, that you used in the first task.</span></span>  
9. <span data-ttu-id="0e063-141">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="0e063-141">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0e063-142">Válassza ki a sort, ahol Mező = Cikkfelosztási kulcs.</span><span class="sxs-lookup"><span data-stu-id="0e063-142">Select the row where Field = Item allocation key.</span></span>  
10. <span data-ttu-id="0e063-143">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0e063-143">In the Criteria field, type a value.</span></span>
11. <span data-ttu-id="0e063-144">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0e063-144">Click OK.</span></span>
12. <span data-ttu-id="0e063-145">Bontsa ki a Fejlett paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0e063-145">Expand the Advanced parameters section.</span></span>
13. <span data-ttu-id="0e063-146">Az Előrejelzési időszak mezőben válassza ki a „Hónap” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e063-146">In the Forecast bucket field, select 'Month'.</span></span>
14. <span data-ttu-id="0e063-147">Az Előrejelzési horizont mezőbe írja be a „3” értéket.</span><span class="sxs-lookup"><span data-stu-id="0e063-147">In the Forecast horizon field, enter '3'.</span></span>
15. <span data-ttu-id="0e063-148">A Befagyasztási időkorlát mezőbe írja be az „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="0e063-148">In the Freeze time fence field, enter '1'.</span></span>
16. <span data-ttu-id="0e063-149">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0e063-149">Click OK.</span></span>

## <a name="visualize-the-demand-forecast"></a><span data-ttu-id="0e063-150">Igény-előrejelzés megjelenítése</span><span class="sxs-lookup"><span data-stu-id="0e063-150">Visualize the demand forecast</span></span>
1. <span data-ttu-id="0e063-151">Ugorjon az Alaptervezés > Előrejelzés > Igény-előrejelzés > Módosított igény-előrejelzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e063-151">Go to Master planning > Forecasting > Demand forecasting > Adjusted demand forecast.</span></span>
2. <span data-ttu-id="0e063-152">Az összesített nézet táblázatban válassza ki a cellát az 1. sor 2. oszlopában.</span><span class="sxs-lookup"><span data-stu-id="0e063-152">In the aggregated view table, select the cell in row 1, column 2.</span></span> <span data-ttu-id="0e063-153">Ez a második hónap, amelyhez előrejelzést hozott létre.</span><span class="sxs-lookup"><span data-stu-id="0e063-153">This is the second month for which you have created forecast.</span></span>
3. <span data-ttu-id="0e063-154">Állítsa a QtyCell értékét „400”-ra.</span><span class="sxs-lookup"><span data-stu-id="0e063-154">Set QtyCell to '400'.</span></span>
    * <span data-ttu-id="0e063-155">A cellában adjon meg egy másik számot, mint amit az előrejelzés mutatott, például: 400.</span><span class="sxs-lookup"><span data-stu-id="0e063-155">In the cell, enter a different number than the one that was forecasted, for example, 400.</span></span>  
4. <span data-ttu-id="0e063-156">Manuálisan helyesbítette az előrejelzést.</span><span class="sxs-lookup"><span data-stu-id="0e063-156">You have made a manual adjustment to the forecast.</span></span> <span data-ttu-id="0e063-157">Figyelje meg a grafikus jelölést a következő lépésben.</span><span class="sxs-lookup"><span data-stu-id="0e063-157">Notice the graphical indication in the next step.</span></span>
5. <span data-ttu-id="0e063-158">Kattintson az Előrejelzési sor részletei lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e063-158">Click Forecast line details.</span></span>
    * <span data-ttu-id="0e063-159">Ezen a lapon láthatja a pontossági értékeket, igényekkel kapcsolatos előzményeket és előrejelzéseket.</span><span class="sxs-lookup"><span data-stu-id="0e063-159">In this page, you can see the accuracy values, historical demand, and forecast.</span></span> <span data-ttu-id="0e063-160">Az előrejelzéseket is módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="0e063-160">You can make changes to the forecast as well.</span></span>  

