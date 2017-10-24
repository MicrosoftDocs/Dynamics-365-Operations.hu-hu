--- 
title: "Anyagjegyzékek létrehozása (csak 2016. február)"
description: "Ez a feladat anyagjegyzék-struktúra létrehozására koncentrál egy késztermékhez és egy félkész termékhez."
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
ms.sourcegitcommit: e089c105a48924d8cb42f34d711125b157c3af2e
ms.openlocfilehash: f8ad4b0e230fb0f018355e486e3b898895a61f28
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-boms-february-2016-only"></a><span data-ttu-id="87181-103">Anyagjegyzékek létrehozása (csak 2016. február)</span><span class="sxs-lookup"><span data-stu-id="87181-103">Create BOMs (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="87181-104">Ez a feladat anyagjegyzék-struktúra létrehozására koncentrál egy késztermékhez és egy félkész termékhez.</span><span class="sxs-lookup"><span data-stu-id="87181-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="87181-105">Ez az anyagjegyzék-számítási sorozat negyedik feladata.</span><span class="sxs-lookup"><span data-stu-id="87181-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="87181-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="87181-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="87181-107">Anyagjegyzék létrehozása egy félkész termékhez</span><span class="sxs-lookup"><span data-stu-id="87181-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="87181-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87181-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="87181-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="87181-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="87181-110">Válassza ki a BOM_2 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="87181-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="87181-111">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="87181-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="87181-112">Kattintson az Anyagjegyzék verziókra.</span><span class="sxs-lookup"><span data-stu-id="87181-112">Click BOM versions.</span></span>
5. <span data-ttu-id="87181-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87181-113">Click New.</span></span>
6. <span data-ttu-id="87181-114">Kattintson az Anyagjegyzék és az Anyagjegyzék verzió elemre.</span><span class="sxs-lookup"><span data-stu-id="87181-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="87181-115">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="87181-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="87181-116">Például írja be a BOM_2 értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="87181-117">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="87181-118">Ebben a példában adja meg vagy válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="87181-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="87181-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87181-119">Click OK.</span></span>
10. <span data-ttu-id="87181-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87181-120">Click New.</span></span>
11. <span data-ttu-id="87181-121">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="87181-122">Ehhez a példához írja be a következőt: ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="87181-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="87181-123">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="87181-124">Ebben a példában adja meg vagy válassza ki a következőt: 11.</span><span class="sxs-lookup"><span data-stu-id="87181-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="87181-125">Kattintson a Fejléc gombra.</span><span class="sxs-lookup"><span data-stu-id="87181-125">Click Header.</span></span>
14. <span data-ttu-id="87181-126">Kattintson a Jóváhagyás lehetőségre az anyagjegyzékek jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="87181-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="87181-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87181-127">Click OK.</span></span>
16. <span data-ttu-id="87181-128">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87181-128">Click Approve.</span></span>
    * <span data-ttu-id="87181-129">A Jóváhagyás gomb az Anyagjegyzék-verziók szakaszban van az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="87181-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="87181-130">Ha nem látható, kattintson a Fejléc elemre az Anyagjegyzékek lapon a Jóváhagyás megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="87181-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="87181-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87181-131">Click OK.</span></span>
18. <span data-ttu-id="87181-132">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="87181-132">Click Activate.</span></span>
19. <span data-ttu-id="87181-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="87181-133">Close the page.</span></span>
20. <span data-ttu-id="87181-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="87181-134">Close the page.</span></span>
21. <span data-ttu-id="87181-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="87181-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="87181-136">Anyagjegyzék létrehozása egy késztermékhez</span><span class="sxs-lookup"><span data-stu-id="87181-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="87181-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="87181-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="87181-138">Válassza ki a BOM_1 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="87181-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="87181-139">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="87181-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="87181-140">Kattintson az Anyagjegyzék verziókra.</span><span class="sxs-lookup"><span data-stu-id="87181-140">Click BOM versions.</span></span>
4. <span data-ttu-id="87181-141">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87181-141">Click New.</span></span>
5. <span data-ttu-id="87181-142">Kattintson az Anyagjegyzék és az Anyagjegyzék verzió elemre.</span><span class="sxs-lookup"><span data-stu-id="87181-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="87181-143">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="87181-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="87181-144">Például írja be a BOM_1 értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="87181-145">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="87181-146">Ebben a példában adja meg vagy válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="87181-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="87181-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87181-147">Click OK.</span></span>
9. <span data-ttu-id="87181-148">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87181-148">Click New.</span></span>
10. <span data-ttu-id="87181-149">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="87181-150">Ehhez a példához írja be a következőt: ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="87181-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="87181-151">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="87181-152">Ehhez a példához válassza ki a következőt: 11.</span><span class="sxs-lookup"><span data-stu-id="87181-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="87181-153">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87181-153">Click New.</span></span>
13. <span data-ttu-id="87181-154">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="87181-155">Ehhez a példához írja be a következőt: ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="87181-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="87181-156">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="87181-157">Ebben a példában adja meg vagy válassza ki a következőt: 11.</span><span class="sxs-lookup"><span data-stu-id="87181-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="87181-158">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87181-158">Click New.</span></span>
16. <span data-ttu-id="87181-159">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="87181-160">Ehhez a példához írja be a következőt: BOM_2.</span><span class="sxs-lookup"><span data-stu-id="87181-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="87181-161">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="87181-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="87181-162">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="87181-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="87181-163">Ebben a példában adja meg vagy válassza ki a 11. raktárat.</span><span class="sxs-lookup"><span data-stu-id="87181-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="87181-164">Kattintson a Fejléc gombra.</span><span class="sxs-lookup"><span data-stu-id="87181-164">Click Header.</span></span>
20. <span data-ttu-id="87181-165">Kattintson a Jóváhagyás lehetőségre az anyagjegyzékek jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="87181-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="87181-166">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87181-166">Click OK.</span></span>
22. <span data-ttu-id="87181-167">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="87181-167">Click Approve.</span></span>
    * <span data-ttu-id="87181-168">A Jóváhagyás gomb az Anyagjegyzék-verziók szakaszban van az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="87181-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="87181-169">Ha nem látható, kattintson a Fejléc elemre az Anyagjegyzékek lapon a Jóváhagyás megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="87181-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="87181-170">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="87181-170">Click OK.</span></span>
24. <span data-ttu-id="87181-171">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="87181-171">Click Activate.</span></span>
25. <span data-ttu-id="87181-172">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="87181-172">Close the page.</span></span>
26. <span data-ttu-id="87181-173">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="87181-173">Close the page.</span></span>
27. <span data-ttu-id="87181-174">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="87181-174">Close the page.</span></span>

