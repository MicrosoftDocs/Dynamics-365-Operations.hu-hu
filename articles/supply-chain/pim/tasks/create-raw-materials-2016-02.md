--- 
title: "Nyersanyagok létrehozása (2016. február)"
description: "Ez a feladat a késztermékek és a félkész termékek komponenseinek létrehozását összpontosít."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="c5538-103">Nyersanyagok létrehozása (2016. február)</span><span class="sxs-lookup"><span data-stu-id="c5538-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c5538-104">Ez a feladat a késztermékek és a félkész termékek komponenseinek létrehozását összpontosít.</span><span class="sxs-lookup"><span data-stu-id="c5538-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="c5538-105">Ez az anyagjegyzék-számítási sorozat harmadik feladata.</span><span class="sxs-lookup"><span data-stu-id="c5538-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="c5538-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="c5538-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="c5538-107">Az első anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="c5538-107">Create the first material</span></span>
1. <span data-ttu-id="c5538-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="c5538-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-109">Click New.</span></span>
3. <span data-ttu-id="c5538-110">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5538-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c5538-111">Ennél a példánál adja meg az ITEM_A lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5538-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="c5538-112">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-113">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5538-113">Select STD.</span></span> <span data-ttu-id="c5538-114">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="c5538-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="c5538-115">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-116">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="c5538-116">For example, select Audio.</span></span> <span data-ttu-id="c5538-117">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="c5538-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="c5538-118">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-119">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="c5538-119">Select SiteWH.</span></span> <span data-ttu-id="c5538-120">A bemutatóhoz csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="c5538-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="c5538-121">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-122">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="c5538-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c5538-123">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5538-123">Select None.</span></span>  
8. <span data-ttu-id="c5538-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c5538-124">Click OK.</span></span>
9. <span data-ttu-id="c5538-125">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="c5538-126">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-126">Click Default order settings.</span></span>
11. <span data-ttu-id="c5538-127">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-128">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c5538-129">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-130">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c5538-131">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-132">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="c5538-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-133">Close the page.</span></span>
15. <span data-ttu-id="c5538-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-134">Close the page.</span></span>
16. <span data-ttu-id="c5538-135">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c5538-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c5538-136">Kattintson az ITEM_A lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="c5538-137">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c5538-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="c5538-138">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5538-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c5538-139">Ehhez a példához írja be a következőt: M2.</span><span class="sxs-lookup"><span data-stu-id="c5538-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="c5538-140">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="c5538-141">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-141">Click Item price.</span></span>
21. <span data-ttu-id="c5538-142">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-142">Click New.</span></span>
22. <span data-ttu-id="c5538-143">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-144">Ebben a példában válassza a 10 lehetőséget, az elszámolóár költségszámítási típust.</span><span class="sxs-lookup"><span data-stu-id="c5538-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="c5538-145">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-146">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="c5538-147">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="c5538-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c5538-148">Ehhez a példához írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="c5538-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="c5538-149">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c5538-149">Click Save.</span></span>
26. <span data-ttu-id="c5538-150">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="c5538-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-151">Close the page.</span></span>
28. <span data-ttu-id="c5538-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="c5538-153">A második anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="c5538-153">Create the second material</span></span>
1. <span data-ttu-id="c5538-154">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-154">Click New.</span></span>
2. <span data-ttu-id="c5538-155">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5538-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c5538-156">Ehhez a példához írja be a következőt: ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="c5538-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="c5538-157">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-158">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5538-158">Select STD.</span></span> <span data-ttu-id="c5538-159">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="c5538-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="c5538-160">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-161">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="c5538-161">For example, select Audio.</span></span> <span data-ttu-id="c5538-162">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="c5538-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="c5538-163">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-164">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="c5538-164">Select SiteWH.</span></span> <span data-ttu-id="c5538-165">A példához csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="c5538-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="c5538-166">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-167">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="c5538-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c5538-168">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5538-168">Select None.</span></span>  
7. <span data-ttu-id="c5538-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c5538-169">Click OK.</span></span>
8. <span data-ttu-id="c5538-170">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="c5538-171">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-171">Click Default order settings.</span></span>
10. <span data-ttu-id="c5538-172">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-173">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="c5538-174">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-175">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c5538-176">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-177">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c5538-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-178">Close the page.</span></span>
14. <span data-ttu-id="c5538-179">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-179">Close the page.</span></span>
15. <span data-ttu-id="c5538-180">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c5538-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c5538-181">Kattintson az ITEM_B lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="c5538-182">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c5538-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="c5538-183">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5538-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c5538-184">Ehhez a példához írja be a következőt: M2.</span><span class="sxs-lookup"><span data-stu-id="c5538-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="c5538-185">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="c5538-186">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-186">Click Item price.</span></span>
20. <span data-ttu-id="c5538-187">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-187">Click New.</span></span>
21. <span data-ttu-id="c5538-188">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-189">Ehhez a példához válassza ki a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="c5538-189">For this example, select 10.</span></span> <span data-ttu-id="c5538-190">Ez az Elszámolóár költségszámítási típus.</span><span class="sxs-lookup"><span data-stu-id="c5538-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="c5538-191">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-192">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="c5538-193">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="c5538-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c5538-194">A bemutató céljára írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="c5538-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="c5538-195">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c5538-195">Click Save.</span></span>
25. <span data-ttu-id="c5538-196">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="c5538-197">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-197">Close the page.</span></span>
27. <span data-ttu-id="c5538-198">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="c5538-199">A harmadik anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="c5538-199">Create the third material</span></span>
1. <span data-ttu-id="c5538-200">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-200">Click New.</span></span>
2. <span data-ttu-id="c5538-201">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5538-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="c5538-202">A bemutató céljára írja be a következőt: ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="c5538-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="c5538-203">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-204">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5538-204">Select STD.</span></span> <span data-ttu-id="c5538-205">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="c5538-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="c5538-206">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-207">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="c5538-207">For example, select Audio.</span></span> <span data-ttu-id="c5538-208">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="c5538-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="c5538-209">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-210">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="c5538-210">Select SiteWH.</span></span> <span data-ttu-id="c5538-211">A bemutatóhoz csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="c5538-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="c5538-212">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-213">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="c5538-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="c5538-214">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c5538-214">Select None.</span></span>  
7. <span data-ttu-id="c5538-215">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c5538-215">Click OK.</span></span>
8. <span data-ttu-id="c5538-216">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="c5538-217">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-217">Click Default order settings.</span></span>
10. <span data-ttu-id="c5538-218">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-219">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="c5538-220">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-221">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="c5538-222">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-223">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="c5538-224">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-224">Close the page.</span></span>
14. <span data-ttu-id="c5538-225">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-225">Close the page.</span></span>
15. <span data-ttu-id="c5538-226">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="c5538-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c5538-227">Kattintson az ITEM_C lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="c5538-228">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="c5538-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="c5538-229">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c5538-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="c5538-230">Ehhez a példához írja be a következőt: M1.</span><span class="sxs-lookup"><span data-stu-id="c5538-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="c5538-231">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="c5538-232">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="c5538-232">Click Item price.</span></span>
20. <span data-ttu-id="c5538-233">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-233">Click New.</span></span>
21. <span data-ttu-id="c5538-234">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-235">Ehhez a példához válassza ki a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="c5538-235">For this example, select 10.</span></span> <span data-ttu-id="c5538-236">Ez az Elszámolóár költségszámítási típus.</span><span class="sxs-lookup"><span data-stu-id="c5538-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="c5538-237">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="c5538-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="c5538-238">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="c5538-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="c5538-239">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="c5538-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="c5538-240">Ehhez a példához írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="c5538-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="c5538-241">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="c5538-241">Click Save.</span></span>
25. <span data-ttu-id="c5538-242">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c5538-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="c5538-243">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-243">Close the page.</span></span>
27. <span data-ttu-id="c5538-244">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c5538-244">Close the page.</span></span>


