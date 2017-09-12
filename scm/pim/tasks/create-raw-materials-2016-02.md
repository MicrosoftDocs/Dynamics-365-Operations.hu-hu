--- 
title: "Nyersanyagok létrehozása (csak 2016. február)"
description: "Ez a feladat a késztermékek és a félkész termékek komponenseinek létrehozását összpontosít."
author: BibiSp
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f1c10e0f8275d928c1455cd99105aece8780e7f0
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="5b6ec-103">Nyersanyagok létrehozása (csak 2016. február)</span><span class="sxs-lookup"><span data-stu-id="5b6ec-103">Create raw materials (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5b6ec-104">Ez a feladat a késztermékek és a félkész termékek komponenseinek létrehozását összpontosít.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="5b6ec-105">Ez az anyagjegyzék-számítási sorozat harmadik feladata.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="5b6ec-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="5b6ec-107">Az első anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="5b6ec-107">Create the first material</span></span>
1. <span data-ttu-id="5b6ec-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="5b6ec-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-109">Click New.</span></span>
3. <span data-ttu-id="5b6ec-110">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="5b6ec-111">Ennél a példánál adja meg az ITEM_A lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="5b6ec-112">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-113">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-113">Select STD.</span></span> <span data-ttu-id="5b6ec-114">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="5b6ec-115">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-116">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-116">For example, select Audio.</span></span> <span data-ttu-id="5b6ec-117">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="5b6ec-118">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-119">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-119">Select SiteWH.</span></span> <span data-ttu-id="5b6ec-120">A bemutatóhoz csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="5b6ec-121">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-122">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="5b6ec-123">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-123">Select None.</span></span>  
8. <span data-ttu-id="5b6ec-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-124">Click OK.</span></span>
9. <span data-ttu-id="5b6ec-125">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="5b6ec-126">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-126">Click Default order settings.</span></span>
11. <span data-ttu-id="5b6ec-127">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-128">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="5b6ec-129">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-130">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="5b6ec-131">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-132">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="5b6ec-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-133">Close the page.</span></span>
15. <span data-ttu-id="5b6ec-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-134">Close the page.</span></span>
16. <span data-ttu-id="5b6ec-135">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5b6ec-136">Kattintson az ITEM_A lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="5b6ec-137">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="5b6ec-138">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="5b6ec-139">Ehhez a példához írja be a következőt: M2.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="5b6ec-140">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="5b6ec-141">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-141">Click Item price.</span></span>
21. <span data-ttu-id="5b6ec-142">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-142">Click New.</span></span>
22. <span data-ttu-id="5b6ec-143">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-144">Ebben a példában válassza a 10 lehetőséget, az elszámolóár költségszámítási típust.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="5b6ec-145">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-146">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="5b6ec-147">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="5b6ec-148">Ehhez a példához írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="5b6ec-149">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-149">Click Save.</span></span>
26. <span data-ttu-id="5b6ec-150">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="5b6ec-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-151">Close the page.</span></span>
28. <span data-ttu-id="5b6ec-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="5b6ec-153">A második anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="5b6ec-153">Create the second material</span></span>
1. <span data-ttu-id="5b6ec-154">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-154">Click New.</span></span>
2. <span data-ttu-id="5b6ec-155">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="5b6ec-156">Ehhez a példához írja be a következőt: ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="5b6ec-157">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-158">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-158">Select STD.</span></span> <span data-ttu-id="5b6ec-159">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="5b6ec-160">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-161">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-161">For example, select Audio.</span></span> <span data-ttu-id="5b6ec-162">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="5b6ec-163">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-164">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-164">Select SiteWH.</span></span> <span data-ttu-id="5b6ec-165">A példához csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="5b6ec-166">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-167">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="5b6ec-168">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-168">Select None.</span></span>  
7. <span data-ttu-id="5b6ec-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-169">Click OK.</span></span>
8. <span data-ttu-id="5b6ec-170">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="5b6ec-171">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-171">Click Default order settings.</span></span>
10. <span data-ttu-id="5b6ec-172">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-173">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="5b6ec-174">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-175">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="5b6ec-176">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-177">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="5b6ec-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-178">Close the page.</span></span>
14. <span data-ttu-id="5b6ec-179">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-179">Close the page.</span></span>
15. <span data-ttu-id="5b6ec-180">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5b6ec-181">Kattintson az ITEM_B lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="5b6ec-182">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="5b6ec-183">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="5b6ec-184">Ehhez a példához írja be a következőt: M2.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="5b6ec-185">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="5b6ec-186">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-186">Click Item price.</span></span>
20. <span data-ttu-id="5b6ec-187">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-187">Click New.</span></span>
21. <span data-ttu-id="5b6ec-188">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-189">Ehhez a példához válassza ki a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-189">For this example, select 10.</span></span> <span data-ttu-id="5b6ec-190">Ez az Elszámolóár költségszámítási típus.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="5b6ec-191">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-192">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="5b6ec-193">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="5b6ec-194">A bemutató céljára írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="5b6ec-195">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-195">Click Save.</span></span>
25. <span data-ttu-id="5b6ec-196">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="5b6ec-197">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-197">Close the page.</span></span>
27. <span data-ttu-id="5b6ec-198">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="5b6ec-199">A harmadik anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="5b6ec-199">Create the third material</span></span>
1. <span data-ttu-id="5b6ec-200">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-200">Click New.</span></span>
2. <span data-ttu-id="5b6ec-201">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="5b6ec-202">A bemutató céljára írja be a következőt: ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="5b6ec-203">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-204">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-204">Select STD.</span></span> <span data-ttu-id="5b6ec-205">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="5b6ec-206">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-207">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-207">For example, select Audio.</span></span> <span data-ttu-id="5b6ec-208">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="5b6ec-209">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-210">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-210">Select SiteWH.</span></span> <span data-ttu-id="5b6ec-211">A bemutatóhoz csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="5b6ec-212">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-213">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="5b6ec-214">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-214">Select None.</span></span>  
7. <span data-ttu-id="5b6ec-215">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-215">Click OK.</span></span>
8. <span data-ttu-id="5b6ec-216">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="5b6ec-217">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-217">Click Default order settings.</span></span>
10. <span data-ttu-id="5b6ec-218">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-219">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="5b6ec-220">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-221">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="5b6ec-222">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-223">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="5b6ec-224">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-224">Close the page.</span></span>
14. <span data-ttu-id="5b6ec-225">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-225">Close the page.</span></span>
15. <span data-ttu-id="5b6ec-226">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5b6ec-227">Kattintson az ITEM_C lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="5b6ec-228">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="5b6ec-229">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="5b6ec-230">Ehhez a példához írja be a következőt: M1.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="5b6ec-231">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="5b6ec-232">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-232">Click Item price.</span></span>
20. <span data-ttu-id="5b6ec-233">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-233">Click New.</span></span>
21. <span data-ttu-id="5b6ec-234">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-235">Ehhez a példához válassza ki a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-235">For this example, select 10.</span></span> <span data-ttu-id="5b6ec-236">Ez az Elszámolóár költségszámítási típus.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="5b6ec-237">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5b6ec-238">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="5b6ec-239">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="5b6ec-240">Ehhez a példához írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="5b6ec-241">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-241">Click Save.</span></span>
25. <span data-ttu-id="5b6ec-242">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="5b6ec-243">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-243">Close the page.</span></span>
27. <span data-ttu-id="5b6ec-244">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5b6ec-244">Close the page.</span></span>


