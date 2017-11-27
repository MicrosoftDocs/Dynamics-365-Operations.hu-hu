--- 
title: "Útvonalak létrehozása (csak 2016. február)"
description: "Ez a feladat termelési útvonalak létrehozására koncentrál egy késztermékhez és egy félkész termékhez."
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
ms.sourcegitcommit: 273ced77a61d485426c0830556e4401e782e86c4
ms.openlocfilehash: 1ba2ae3ad92149636714701448d4dac8296d6613
ms.contentlocale: hu-hu
ms.lasthandoff: 10/24/2017

---
# <a name="create-routes-february-2016-only"></a><span data-ttu-id="3f2dd-103">Útvonalak létrehozása (csak 2016. február)</span><span class="sxs-lookup"><span data-stu-id="3f2dd-103">Create routes (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3f2dd-104">Ez a feladat termelési útvonalak létrehozására koncentrál egy késztermékhez és egy félkész termékhez.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-104">This task focuses on creating the production routes for a finished product and a semi-finished product.</span></span> <span data-ttu-id="3f2dd-105">Ez az anyagjegyzék-számítási sorozat ötödik feladata.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="3f2dd-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="3f2dd-107">Útvonal létrehozása egy félkész termékhez</span><span class="sxs-lookup"><span data-stu-id="3f2dd-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="3f2dd-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="3f2dd-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3f2dd-110">Válassza ki a BOM_2 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="3f2dd-111">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="3f2dd-112">Kattintson az Útvonalra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-112">Click Route.</span></span>
5. <span data-ttu-id="3f2dd-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-113">Click New.</span></span>
6. <span data-ttu-id="3f2dd-114">Kattintson az Útvonal és útvonalverzió lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-114">Click Route and route version.</span></span>
7. <span data-ttu-id="3f2dd-115">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="3f2dd-116">Írja be például a következőt: ROUTE_2.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="3f2dd-117">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="3f2dd-118">Ebben a példában adja meg vagy válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="3f2dd-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-119">Click OK.</span></span>
10. <span data-ttu-id="3f2dd-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-120">Click New.</span></span>
11. <span data-ttu-id="3f2dd-121">A Műveletek mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="3f2dd-122">Ehhez a példához válassza ki a Szerelvény lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="3f2dd-123">Adjon meg egy számot a Futási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="3f2dd-124">Például írja be a „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-124">For example, type 1.</span></span> <span data-ttu-id="3f2dd-125">A futási idő általában része a kiszámított cikkárnak.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="3f2dd-126">Az Útvonalcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="3f2dd-127">Ehhez a példához válassza ki a következőt: Std.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="3f2dd-128">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="3f2dd-129">A Beállítási kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="3f2dd-130">Ehhez a példához válassza ki a Szerelvény lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="3f2dd-131">Kattintson az Idők fülre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-131">Click the Times tab.</span></span>
17. <span data-ttu-id="3f2dd-132">A Beállítási idő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="3f2dd-133">Ehhez a példához írja be a következőt: 1.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-133">For this example, type 1.</span></span> <span data-ttu-id="3f2dd-134">A beállítási idő általában része a kiszámított cikkárnak.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="3f2dd-135">A Művelet panelen kattintson az Útvonalverzió elemre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="3f2dd-136">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-136">Click Approve.</span></span>
20. <span data-ttu-id="3f2dd-137">A „Szeretné jóvá is hagyni az útvonalat?” kérdésre válaszolva válassza ki az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="3f2dd-138">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-138">Click OK.</span></span>
22. <span data-ttu-id="3f2dd-139">A Művelet panelen kattintson az Útvonalverzió elemre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="3f2dd-140">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-140">Click Activate.</span></span>
24. <span data-ttu-id="3f2dd-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-141">Close the page.</span></span>
25. <span data-ttu-id="3f2dd-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="3f2dd-143">Útvonal létrehozása egy késztermékhez</span><span class="sxs-lookup"><span data-stu-id="3f2dd-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="3f2dd-144">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3f2dd-145">Válassza ki a BOM_1 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="3f2dd-146">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="3f2dd-147">Kattintson az Útvonalra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-147">Click Route.</span></span>
4. <span data-ttu-id="3f2dd-148">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-148">Click New.</span></span>
5. <span data-ttu-id="3f2dd-149">Kattintson az Útvonal és útvonalverzió lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-149">Click Route and route version.</span></span>
6. <span data-ttu-id="3f2dd-150">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="3f2dd-151">Ehhez a példához írja be a következőt: ROUTE_1.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="3f2dd-152">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="3f2dd-153">Ebben a példában adja meg vagy válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="3f2dd-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-154">Click OK.</span></span>
9. <span data-ttu-id="3f2dd-155">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-155">Click New.</span></span>
10. <span data-ttu-id="3f2dd-156">A Műveletek mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="3f2dd-157">Ehhez a példához válassza ki a Csomagolás lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="3f2dd-158">Adjon meg egy számot a Futási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="3f2dd-159">Ehhez a példához írja be a következőt: 1.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="3f2dd-160">Az Útvonalcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="3f2dd-161">Ehhez a példához válassza ki a következőt: Std.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="3f2dd-162">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="3f2dd-163">A Beállítási kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="3f2dd-164">Ehhez a példához válassza ki a Csomagolás lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="3f2dd-165">Kattintson az Idők fülre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-165">Click the Times tab.</span></span>
16. <span data-ttu-id="3f2dd-166">A Beállítási idő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="3f2dd-167">Ehhez a példához írja be a következőt: 1.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="3f2dd-168">A Művelet panelen kattintson az Útvonalverzió elemre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="3f2dd-169">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-169">Click Approve.</span></span>
19. <span data-ttu-id="3f2dd-170">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-170">Click OK.</span></span>
20. <span data-ttu-id="3f2dd-171">A Művelet panelen kattintson az Útvonalverzió elemre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="3f2dd-172">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-172">Click Activate.</span></span>
22. <span data-ttu-id="3f2dd-173">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-173">Close the page.</span></span>
23. <span data-ttu-id="3f2dd-174">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="3f2dd-175">A beállítási idő automatikus felhasználásának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="3f2dd-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="3f2dd-176">Ugrás a Gyártásvezérlés > Beállítás > Útvonalak > Útvonalcsoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="3f2dd-177">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3f2dd-178">A listában válassza a következőt: Std.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="3f2dd-179">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-179">Click Edit.</span></span>
4. <span data-ttu-id="3f2dd-180">Válassza ki az Igen lehetőséget a Beállítási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="3f2dd-181">A beállítási idő általában része a kiszámított cikkárnak.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="3f2dd-182">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-182">Click Save.</span></span>
6. <span data-ttu-id="3f2dd-183">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3f2dd-183">Close the page.</span></span>


