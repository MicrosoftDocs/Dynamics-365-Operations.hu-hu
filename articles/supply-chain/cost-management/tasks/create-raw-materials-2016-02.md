--- 
title: "Nyersanyagok létrehozása (csak 2016. február)"
description: "Ez a feladat a késztermékek és a félkész termékek komponenseinek létrehozását összpontosít."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3d77dcc20fe7402af83dd724e7fef848977e5bf8
ms.openlocfilehash: f6af7b93d8d1d9a6f7474f24177b16e5295e90d6
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="5a568-103">Nyersanyagok létrehozása (csak 2016. február)</span><span class="sxs-lookup"><span data-stu-id="5a568-103">Create raw materials (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5a568-104">Ez a feladat a késztermékek és a félkész termékek komponenseinek létrehozását összpontosít.</span><span class="sxs-lookup"><span data-stu-id="5a568-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="5a568-105">Ez az anyagjegyzék-számítási sorozat harmadik feladata.</span><span class="sxs-lookup"><span data-stu-id="5a568-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="5a568-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="5a568-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="5a568-107">Az első anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="5a568-107">Create the first material</span></span>
1. <span data-ttu-id="5a568-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="5a568-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-109">Click New.</span></span>
3. <span data-ttu-id="5a568-110">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5a568-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="5a568-111">Ennél a példánál adja meg az ITEM_A lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a568-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="5a568-112">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-113">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a568-113">Select STD.</span></span> <span data-ttu-id="5a568-114">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="5a568-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="5a568-115">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-116">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="5a568-116">For example, select Audio.</span></span> <span data-ttu-id="5a568-117">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="5a568-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="5a568-118">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-119">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="5a568-119">Select SiteWH.</span></span> <span data-ttu-id="5a568-120">A bemutatóhoz csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="5a568-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="5a568-121">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-122">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="5a568-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="5a568-123">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a568-123">Select None.</span></span>  
8. <span data-ttu-id="5a568-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5a568-124">Click OK.</span></span>
9. <span data-ttu-id="5a568-125">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="5a568-126">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-126">Click Default order settings.</span></span>
11. <span data-ttu-id="5a568-127">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-128">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="5a568-129">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-130">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="5a568-131">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-132">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="5a568-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-133">Close the page.</span></span>
15. <span data-ttu-id="5a568-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-134">Close the page.</span></span>
16. <span data-ttu-id="5a568-135">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5a568-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5a568-136">Kattintson az ITEM_A lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="5a568-137">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5a568-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="5a568-138">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5a568-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="5a568-139">Ehhez a példához írja be a következőt: M2.</span><span class="sxs-lookup"><span data-stu-id="5a568-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="5a568-140">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="5a568-141">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-141">Click Item price.</span></span>
21. <span data-ttu-id="5a568-142">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-142">Click New.</span></span>
22. <span data-ttu-id="5a568-143">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-144">Ebben a példában válassza a 10 lehetőséget, az elszámolóár költségszámítási típust.</span><span class="sxs-lookup"><span data-stu-id="5a568-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="5a568-145">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-146">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="5a568-147">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="5a568-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="5a568-148">Ehhez a példához írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="5a568-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="5a568-149">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5a568-149">Click Save.</span></span>
26. <span data-ttu-id="5a568-150">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="5a568-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-151">Close the page.</span></span>
28. <span data-ttu-id="5a568-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="5a568-153">A második anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="5a568-153">Create the second material</span></span>
1. <span data-ttu-id="5a568-154">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-154">Click New.</span></span>
2. <span data-ttu-id="5a568-155">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5a568-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="5a568-156">Ehhez a példához írja be a következőt: ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="5a568-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="5a568-157">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-158">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a568-158">Select STD.</span></span> <span data-ttu-id="5a568-159">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="5a568-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="5a568-160">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-161">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="5a568-161">For example, select Audio.</span></span> <span data-ttu-id="5a568-162">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="5a568-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="5a568-163">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-164">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="5a568-164">Select SiteWH.</span></span> <span data-ttu-id="5a568-165">A példához csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="5a568-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="5a568-166">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-167">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="5a568-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="5a568-168">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a568-168">Select None.</span></span>  
7. <span data-ttu-id="5a568-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5a568-169">Click OK.</span></span>
8. <span data-ttu-id="5a568-170">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="5a568-171">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-171">Click Default order settings.</span></span>
10. <span data-ttu-id="5a568-172">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-173">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="5a568-174">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-175">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="5a568-176">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-177">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="5a568-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-178">Close the page.</span></span>
14. <span data-ttu-id="5a568-179">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-179">Close the page.</span></span>
15. <span data-ttu-id="5a568-180">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5a568-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5a568-181">Kattintson az ITEM_B lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="5a568-182">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5a568-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="5a568-183">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5a568-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="5a568-184">Ehhez a példához írja be a következőt: M2.</span><span class="sxs-lookup"><span data-stu-id="5a568-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="5a568-185">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="5a568-186">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-186">Click Item price.</span></span>
20. <span data-ttu-id="5a568-187">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-187">Click New.</span></span>
21. <span data-ttu-id="5a568-188">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-189">Ehhez a példához válassza ki a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="5a568-189">For this example, select 10.</span></span> <span data-ttu-id="5a568-190">Ez az Elszámolóár költségszámítási típus.</span><span class="sxs-lookup"><span data-stu-id="5a568-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="5a568-191">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-192">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="5a568-193">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="5a568-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="5a568-194">A bemutató céljára írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="5a568-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="5a568-195">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5a568-195">Click Save.</span></span>
25. <span data-ttu-id="5a568-196">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="5a568-197">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-197">Close the page.</span></span>
27. <span data-ttu-id="5a568-198">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="5a568-199">A harmadik anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="5a568-199">Create the third material</span></span>
1. <span data-ttu-id="5a568-200">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-200">Click New.</span></span>
2. <span data-ttu-id="5a568-201">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5a568-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="5a568-202">A bemutató céljára írja be a következőt: ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="5a568-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="5a568-203">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-204">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a568-204">Select STD.</span></span> <span data-ttu-id="5a568-205">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="5a568-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="5a568-206">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-207">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="5a568-207">For example, select Audio.</span></span> <span data-ttu-id="5a568-208">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="5a568-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="5a568-209">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-210">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="5a568-210">Select SiteWH.</span></span> <span data-ttu-id="5a568-211">A bemutatóhoz csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="5a568-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="5a568-212">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-213">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="5a568-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="5a568-214">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a568-214">Select None.</span></span>  
7. <span data-ttu-id="5a568-215">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5a568-215">Click OK.</span></span>
8. <span data-ttu-id="5a568-216">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="5a568-217">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-217">Click Default order settings.</span></span>
10. <span data-ttu-id="5a568-218">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-219">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="5a568-220">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-221">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="5a568-222">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-223">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="5a568-224">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-224">Close the page.</span></span>
14. <span data-ttu-id="5a568-225">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-225">Close the page.</span></span>
15. <span data-ttu-id="5a568-226">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5a568-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5a568-227">Kattintson az ITEM_C lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="5a568-228">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5a568-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="5a568-229">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5a568-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="5a568-230">Ehhez a példához írja be a következőt: M1.</span><span class="sxs-lookup"><span data-stu-id="5a568-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="5a568-231">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="5a568-232">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="5a568-232">Click Item price.</span></span>
20. <span data-ttu-id="5a568-233">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-233">Click New.</span></span>
21. <span data-ttu-id="5a568-234">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-235">Ehhez a példához válassza ki a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="5a568-235">For this example, select 10.</span></span> <span data-ttu-id="5a568-236">Ez az Elszámolóár költségszámítási típus.</span><span class="sxs-lookup"><span data-stu-id="5a568-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="5a568-237">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5a568-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5a568-238">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5a568-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="5a568-239">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="5a568-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="5a568-240">Ehhez a példához írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="5a568-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="5a568-241">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5a568-241">Click Save.</span></span>
25. <span data-ttu-id="5a568-242">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5a568-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="5a568-243">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-243">Close the page.</span></span>
27. <span data-ttu-id="5a568-244">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5a568-244">Close the page.</span></span>


