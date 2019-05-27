---
title: Nyersanyagok létrehozása (csak 2016. február)
description: Ez a feladat a késztermékek és a félkész termékek komponenseinek létrehozását összpontosít.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 869acddf6f7e9754bb4952176ded4b22c74eaffd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563296"
---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="46690-103">Nyersanyagok létrehozása (csak 2016. február)</span><span class="sxs-lookup"><span data-stu-id="46690-103">Create raw materials (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46690-104">Ez a feladat a késztermékek és a félkész termékek komponenseinek létrehozását összpontosít.</span><span class="sxs-lookup"><span data-stu-id="46690-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="46690-105">Ez az anyagjegyzék-számítási sorozat harmadik feladata.</span><span class="sxs-lookup"><span data-stu-id="46690-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="46690-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="46690-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="46690-107">Az első anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="46690-107">Create the first material</span></span>
1. <span data-ttu-id="46690-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="46690-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-109">Click New.</span></span>
3. <span data-ttu-id="46690-110">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="46690-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="46690-111">Ennél a példánál adja meg az ITEM_A lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46690-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="46690-112">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-113">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46690-113">Select STD.</span></span> <span data-ttu-id="46690-114">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="46690-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="46690-115">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-116">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="46690-116">For example, select Audio.</span></span> <span data-ttu-id="46690-117">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="46690-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="46690-118">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-119">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="46690-119">Select SiteWH.</span></span> <span data-ttu-id="46690-120">A bemutatóhoz csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="46690-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="46690-121">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-122">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="46690-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="46690-123">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46690-123">Select None.</span></span>  
8. <span data-ttu-id="46690-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="46690-124">Click OK.</span></span>
9. <span data-ttu-id="46690-125">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="46690-126">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-126">Click Default order settings.</span></span>
11. <span data-ttu-id="46690-127">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-128">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="46690-129">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-130">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="46690-131">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-132">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="46690-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-133">Close the page.</span></span>
15. <span data-ttu-id="46690-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-134">Close the page.</span></span>
16. <span data-ttu-id="46690-135">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="46690-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="46690-136">Kattintson az ITEM_A lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="46690-137">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="46690-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="46690-138">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="46690-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="46690-139">Ehhez a példához írja be a következőt: M2.</span><span class="sxs-lookup"><span data-stu-id="46690-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="46690-140">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="46690-141">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-141">Click Item price.</span></span>
21. <span data-ttu-id="46690-142">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-142">Click New.</span></span>
22. <span data-ttu-id="46690-143">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-144">Ebben a példában válassza a 10 lehetőséget, az elszámolóár költségszámítási típust.</span><span class="sxs-lookup"><span data-stu-id="46690-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="46690-145">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-146">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="46690-147">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="46690-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="46690-148">Ehhez a példához írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="46690-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="46690-149">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="46690-149">Click Save.</span></span>
26. <span data-ttu-id="46690-150">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="46690-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-151">Close the page.</span></span>
28. <span data-ttu-id="46690-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="46690-153">A második anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="46690-153">Create the second material</span></span>
1. <span data-ttu-id="46690-154">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-154">Click New.</span></span>
2. <span data-ttu-id="46690-155">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="46690-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="46690-156">Ehhez a példához írja be a következőt: ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="46690-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="46690-157">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-158">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46690-158">Select STD.</span></span> <span data-ttu-id="46690-159">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="46690-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="46690-160">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-161">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="46690-161">For example, select Audio.</span></span> <span data-ttu-id="46690-162">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="46690-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="46690-163">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-164">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="46690-164">Select SiteWH.</span></span> <span data-ttu-id="46690-165">A példához csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="46690-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="46690-166">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-167">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="46690-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="46690-168">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46690-168">Select None.</span></span>  
7. <span data-ttu-id="46690-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="46690-169">Click OK.</span></span>
8. <span data-ttu-id="46690-170">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="46690-171">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-171">Click Default order settings.</span></span>
10. <span data-ttu-id="46690-172">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-173">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="46690-174">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-175">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="46690-176">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-177">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="46690-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-178">Close the page.</span></span>
14. <span data-ttu-id="46690-179">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-179">Close the page.</span></span>
15. <span data-ttu-id="46690-180">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="46690-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="46690-181">Kattintson az ITEM_B lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="46690-182">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="46690-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="46690-183">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="46690-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="46690-184">Ehhez a példához írja be a következőt: M2.</span><span class="sxs-lookup"><span data-stu-id="46690-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="46690-185">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="46690-186">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-186">Click Item price.</span></span>
20. <span data-ttu-id="46690-187">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-187">Click New.</span></span>
21. <span data-ttu-id="46690-188">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-189">Ehhez a példához válassza ki a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="46690-189">For this example, select 10.</span></span> <span data-ttu-id="46690-190">Ez az Elszámolóár költségszámítási típus.</span><span class="sxs-lookup"><span data-stu-id="46690-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="46690-191">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-192">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="46690-193">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="46690-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="46690-194">A bemutató céljára írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="46690-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="46690-195">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="46690-195">Click Save.</span></span>
25. <span data-ttu-id="46690-196">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="46690-197">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-197">Close the page.</span></span>
27. <span data-ttu-id="46690-198">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="46690-199">A harmadik anyag létrehozása</span><span class="sxs-lookup"><span data-stu-id="46690-199">Create the third material</span></span>
1. <span data-ttu-id="46690-200">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-200">Click New.</span></span>
2. <span data-ttu-id="46690-201">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="46690-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="46690-202">A bemutató céljára írja be a következőt: ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="46690-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="46690-203">Az Elem modellcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-204">Válassza az STD lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46690-204">Select STD.</span></span> <span data-ttu-id="46690-205">Az STD az elszámolóár rövidítése, és a költségszámításokkal dolgozva ez a leggyakrabban használt modell.</span><span class="sxs-lookup"><span data-stu-id="46690-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="46690-206">Az Elemcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-207">Válassza például a következőt: Audió.</span><span class="sxs-lookup"><span data-stu-id="46690-207">For example, select Audio.</span></span> <span data-ttu-id="46690-208">Nincs hatással a költségszámításokra.</span><span class="sxs-lookup"><span data-stu-id="46690-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="46690-209">A Tárolási dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-210">SiteWH kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="46690-210">Select SiteWH.</span></span> <span data-ttu-id="46690-211">A bemutatóhoz csak a helyet és a raktárat használjuk.</span><span class="sxs-lookup"><span data-stu-id="46690-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="46690-212">A Nyomon követési dimenzió mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-213">A nyomon követési dimenziókat nem használjuk ennél a példánál.</span><span class="sxs-lookup"><span data-stu-id="46690-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="46690-214">Válassza a Nincs lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="46690-214">Select None.</span></span>  
7. <span data-ttu-id="46690-215">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="46690-215">Click OK.</span></span>
8. <span data-ttu-id="46690-216">A Művelet panelen kattintson a Készletkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="46690-217">Kattintson az Alapértelmezett rendelésbeállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-217">Click Default order settings.</span></span>
10. <span data-ttu-id="46690-218">A Beszerzési hely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-219">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="46690-220">A Készlethely mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-221">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="46690-222">Az Értékesítési hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-223">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="46690-224">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-224">Close the page.</span></span>
14. <span data-ttu-id="46690-225">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-225">Close the page.</span></span>
15. <span data-ttu-id="46690-226">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="46690-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="46690-227">Kattintson az ITEM_C lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="46690-228">Bontsa ki a Költségkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="46690-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="46690-229">Írjon be egy értéket a Költségcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="46690-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="46690-230">Ehhez a példához írja be a következőt: M1.</span><span class="sxs-lookup"><span data-stu-id="46690-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="46690-231">A Művelet panelen kattintson a Költségkezelés elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="46690-232">Kattintson a Cikk ára elemre.</span><span class="sxs-lookup"><span data-stu-id="46690-232">Click Item price.</span></span>
20. <span data-ttu-id="46690-233">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-233">Click New.</span></span>
21. <span data-ttu-id="46690-234">A Verzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-235">Ehhez a példához válassza ki a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="46690-235">For this example, select 10.</span></span> <span data-ttu-id="46690-236">Ez az Elszámolóár költségszámítási típus.</span><span class="sxs-lookup"><span data-stu-id="46690-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="46690-237">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46690-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="46690-238">Ehhez a példához válassza ki a következőt: 1. hely.</span><span class="sxs-lookup"><span data-stu-id="46690-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="46690-239">Adjon meg egy számot az Ár mezőben.</span><span class="sxs-lookup"><span data-stu-id="46690-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="46690-240">Ehhez a példához írja be a következőt: 10.</span><span class="sxs-lookup"><span data-stu-id="46690-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="46690-241">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="46690-241">Click Save.</span></span>
25. <span data-ttu-id="46690-242">Kattintson a Függő árak aktiválása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46690-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="46690-243">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-243">Close the page.</span></span>
27. <span data-ttu-id="46690-244">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="46690-244">Close the page.</span></span>

