---
title: Útvonalak létrehozása (2016. február)
description: Ez a feladat termelési útvonalak létrehozására koncentrál egy késztermékhez és egy félkész termékhez.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, RouteInventProd, RouteGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a68b28c0e0ee14429a23d3241cabdae948d706d2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567855"
---
# <a name="create-routes-february-2016"></a><span data-ttu-id="92a8b-103">Útvonalak létrehozása (2016. február)</span><span class="sxs-lookup"><span data-stu-id="92a8b-103">Create routes (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="92a8b-104">Ez a feladat termelési útvonalak létrehozására koncentrál egy késztermékhez és egy félkész termékhez.</span><span class="sxs-lookup"><span data-stu-id="92a8b-104">This task focuses on creating the production routes for a finished product and a semi-finished product.</span></span> <span data-ttu-id="92a8b-105">Ez az anyagjegyzék-számítási sorozat ötödik feladata.</span><span class="sxs-lookup"><span data-stu-id="92a8b-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="92a8b-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="92a8b-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="92a8b-107">Útvonal létrehozása egy félkész termékhez</span><span class="sxs-lookup"><span data-stu-id="92a8b-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="92a8b-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="92a8b-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="92a8b-110">Válassza ki a BOM_2 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="92a8b-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="92a8b-111">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="92a8b-112">Kattintson az Útvonalra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-112">Click Route.</span></span>
5. <span data-ttu-id="92a8b-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-113">Click New.</span></span>
6. <span data-ttu-id="92a8b-114">Kattintson az Útvonal és útvonalverzió lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-114">Click Route and route version.</span></span>
7. <span data-ttu-id="92a8b-115">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="92a8b-116">Írja be például a következőt: ROUTE_2.</span><span class="sxs-lookup"><span data-stu-id="92a8b-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="92a8b-117">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="92a8b-118">Ebben a példában adja meg vagy válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="92a8b-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="92a8b-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-119">Click OK.</span></span>
10. <span data-ttu-id="92a8b-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-120">Click New.</span></span>
11. <span data-ttu-id="92a8b-121">A Műveletek mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="92a8b-122">Ehhez a példához válassza ki a Szerelvény lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="92a8b-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="92a8b-123">Adjon meg egy számot a Futási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="92a8b-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="92a8b-124">Például írja be a „1” értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-124">For example, type 1.</span></span> <span data-ttu-id="92a8b-125">A futási idő általában része a kiszámított cikkárnak.</span><span class="sxs-lookup"><span data-stu-id="92a8b-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="92a8b-126">Az Útvonalcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="92a8b-127">Ehhez a példához válassza ki a következőt: Std.</span><span class="sxs-lookup"><span data-stu-id="92a8b-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="92a8b-128">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="92a8b-129">A Beállítási kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="92a8b-130">Ehhez a példához válassza ki a Szerelvény lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="92a8b-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="92a8b-131">Kattintson az Idők fülre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-131">Click the Times tab.</span></span>
17. <span data-ttu-id="92a8b-132">A Beállítási idő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="92a8b-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="92a8b-133">Ehhez a példához írja be a következőt: 1.</span><span class="sxs-lookup"><span data-stu-id="92a8b-133">For this example, type 1.</span></span> <span data-ttu-id="92a8b-134">A beállítási idő általában része a kiszámított cikkárnak.</span><span class="sxs-lookup"><span data-stu-id="92a8b-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="92a8b-135">A Művelet panelen kattintson az Útvonalverzió elemre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="92a8b-136">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-136">Click Approve.</span></span>
20. <span data-ttu-id="92a8b-137">A „Szeretné jóvá is hagyni az útvonalat?” kérdésre válaszolva válassza ki az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="92a8b-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="92a8b-138">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-138">Click OK.</span></span>
22. <span data-ttu-id="92a8b-139">A Művelet panelen kattintson az Útvonalverzió elemre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="92a8b-140">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-140">Click Activate.</span></span>
24. <span data-ttu-id="92a8b-141">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="92a8b-141">Close the page.</span></span>
25. <span data-ttu-id="92a8b-142">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="92a8b-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="92a8b-143">Útvonal létrehozása egy késztermékhez</span><span class="sxs-lookup"><span data-stu-id="92a8b-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="92a8b-144">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="92a8b-145">Válassza ki a BOM_1 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="92a8b-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="92a8b-146">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="92a8b-147">Kattintson az Útvonalra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-147">Click Route.</span></span>
4. <span data-ttu-id="92a8b-148">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-148">Click New.</span></span>
5. <span data-ttu-id="92a8b-149">Kattintson az Útvonal és útvonalverzió lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-149">Click Route and route version.</span></span>
6. <span data-ttu-id="92a8b-150">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="92a8b-151">Ehhez a példához írja be a következőt: ROUTE_1.</span><span class="sxs-lookup"><span data-stu-id="92a8b-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="92a8b-152">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="92a8b-153">Ebben a példában adja meg vagy válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="92a8b-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="92a8b-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-154">Click OK.</span></span>
9. <span data-ttu-id="92a8b-155">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-155">Click New.</span></span>
10. <span data-ttu-id="92a8b-156">A Műveletek mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="92a8b-157">Ehhez a példához válassza ki a Csomagolás lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="92a8b-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="92a8b-158">Adjon meg egy számot a Futási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="92a8b-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="92a8b-159">Ehhez a példához írja be a következőt: 1.</span><span class="sxs-lookup"><span data-stu-id="92a8b-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="92a8b-160">Az Útvonalcsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="92a8b-161">Ehhez a példához válassza ki a következőt: Std.</span><span class="sxs-lookup"><span data-stu-id="92a8b-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="92a8b-162">Kattintson a Beállítás fülre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="92a8b-163">A Beállítási kategória mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="92a8b-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="92a8b-164">Ehhez a példához válassza ki a Csomagolás lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="92a8b-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="92a8b-165">Kattintson az Idők fülre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-165">Click the Times tab.</span></span>
16. <span data-ttu-id="92a8b-166">A Beállítási idő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="92a8b-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="92a8b-167">Ehhez a példához írja be a következőt: 1.</span><span class="sxs-lookup"><span data-stu-id="92a8b-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="92a8b-168">A Művelet panelen kattintson az Útvonalverzió elemre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="92a8b-169">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-169">Click Approve.</span></span>
19. <span data-ttu-id="92a8b-170">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-170">Click OK.</span></span>
20. <span data-ttu-id="92a8b-171">A Művelet panelen kattintson az Útvonalverzió elemre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="92a8b-172">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-172">Click Activate.</span></span>
22. <span data-ttu-id="92a8b-173">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="92a8b-173">Close the page.</span></span>
23. <span data-ttu-id="92a8b-174">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="92a8b-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="92a8b-175">A beállítási idő automatikus felhasználásának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="92a8b-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="92a8b-176">Ugrás a Gyártásvezérlés > Beállítás > Útvonalak > Útvonalcsoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="92a8b-177">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="92a8b-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="92a8b-178">A listában válassza a következőt: Std.</span><span class="sxs-lookup"><span data-stu-id="92a8b-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="92a8b-179">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="92a8b-179">Click Edit.</span></span>
4. <span data-ttu-id="92a8b-180">Válassza ki az Igen lehetőséget a Beállítási idő mezőben.</span><span class="sxs-lookup"><span data-stu-id="92a8b-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="92a8b-181">A beállítási idő általában része a kiszámított cikkárnak.</span><span class="sxs-lookup"><span data-stu-id="92a8b-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="92a8b-182">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="92a8b-182">Click Save.</span></span>
6. <span data-ttu-id="92a8b-183">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="92a8b-183">Close the page.</span></span>

