---
title: Anyagjegyzékek létrehozása (csak 2016. február)
description: Ez a feladat anyagjegyzék-struktúra létrehozására koncentrál egy késztermékhez és egy félkész termékhez.
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
ms.openlocfilehash: f132a3865b180a74d328ebc76ca29b2fc8aee85f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "332541"
---
# <a name="create-boms-february-2016-only"></a><span data-ttu-id="6735c-103">Anyagjegyzékek létrehozása (csak 2016. február)</span><span class="sxs-lookup"><span data-stu-id="6735c-103">Create BOMs (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6735c-104">Ez a feladat anyagjegyzék-struktúra létrehozására koncentrál egy késztermékhez és egy félkész termékhez.</span><span class="sxs-lookup"><span data-stu-id="6735c-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="6735c-105">Ez az anyagjegyzék-számítási sorozat negyedik feladata.</span><span class="sxs-lookup"><span data-stu-id="6735c-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="6735c-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="6735c-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="6735c-107">Anyagjegyzék létrehozása egy félkész termékhez</span><span class="sxs-lookup"><span data-stu-id="6735c-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="6735c-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6735c-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="6735c-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6735c-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="6735c-110">Válassza ki a BOM_2 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="6735c-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="6735c-111">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="6735c-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="6735c-112">Kattintson az Anyagjegyzék verziókra.</span><span class="sxs-lookup"><span data-stu-id="6735c-112">Click BOM versions.</span></span>
5. <span data-ttu-id="6735c-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6735c-113">Click New.</span></span>
6. <span data-ttu-id="6735c-114">Kattintson az Anyagjegyzék és az Anyagjegyzék verzió elemre.</span><span class="sxs-lookup"><span data-stu-id="6735c-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="6735c-115">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6735c-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="6735c-116">Például írja be a BOM_2 értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="6735c-117">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="6735c-118">Ebben a példában adja meg vagy válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="6735c-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="6735c-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6735c-119">Click OK.</span></span>
10. <span data-ttu-id="6735c-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6735c-120">Click New.</span></span>
11. <span data-ttu-id="6735c-121">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="6735c-122">Ehhez a példához írja be a következőt: ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="6735c-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="6735c-123">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="6735c-124">Ebben a példában adja meg vagy válassza ki a következőt: 11.</span><span class="sxs-lookup"><span data-stu-id="6735c-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="6735c-125">Kattintson a Fejléc gombra.</span><span class="sxs-lookup"><span data-stu-id="6735c-125">Click Header.</span></span>
14. <span data-ttu-id="6735c-126">Kattintson a Jóváhagyás lehetőségre az anyagjegyzékek jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="6735c-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="6735c-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6735c-127">Click OK.</span></span>
16. <span data-ttu-id="6735c-128">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6735c-128">Click Approve.</span></span>
    * <span data-ttu-id="6735c-129">A Jóváhagyás gomb az Anyagjegyzék-verziók szakaszban van az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="6735c-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="6735c-130">Ha nem látható, kattintson a Fejléc elemre az Anyagjegyzékek lapon a Jóváhagyás megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="6735c-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="6735c-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6735c-131">Click OK.</span></span>
18. <span data-ttu-id="6735c-132">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="6735c-132">Click Activate.</span></span>
19. <span data-ttu-id="6735c-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6735c-133">Close the page.</span></span>
20. <span data-ttu-id="6735c-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6735c-134">Close the page.</span></span>
21. <span data-ttu-id="6735c-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6735c-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="6735c-136">Anyagjegyzék létrehozása egy késztermékhez</span><span class="sxs-lookup"><span data-stu-id="6735c-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="6735c-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6735c-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="6735c-138">Válassza ki a BOM_1 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="6735c-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="6735c-139">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="6735c-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="6735c-140">Kattintson az Anyagjegyzék verziókra.</span><span class="sxs-lookup"><span data-stu-id="6735c-140">Click BOM versions.</span></span>
4. <span data-ttu-id="6735c-141">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6735c-141">Click New.</span></span>
5. <span data-ttu-id="6735c-142">Kattintson az Anyagjegyzék és az Anyagjegyzék verzió elemre.</span><span class="sxs-lookup"><span data-stu-id="6735c-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="6735c-143">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6735c-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="6735c-144">Például írja be a BOM_1 értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="6735c-145">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="6735c-146">Ebben a példában adja meg vagy válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="6735c-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="6735c-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6735c-147">Click OK.</span></span>
9. <span data-ttu-id="6735c-148">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6735c-148">Click New.</span></span>
10. <span data-ttu-id="6735c-149">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="6735c-150">Ehhez a példához írja be a következőt: ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="6735c-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="6735c-151">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="6735c-152">Ehhez a példához válassza ki a következőt: 11.</span><span class="sxs-lookup"><span data-stu-id="6735c-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="6735c-153">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6735c-153">Click New.</span></span>
13. <span data-ttu-id="6735c-154">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="6735c-155">Ehhez a példához írja be a következőt: ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="6735c-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="6735c-156">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="6735c-157">Ebben a példában adja meg vagy válassza ki a következőt: 11.</span><span class="sxs-lookup"><span data-stu-id="6735c-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="6735c-158">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6735c-158">Click New.</span></span>
16. <span data-ttu-id="6735c-159">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="6735c-160">Ehhez a példához írja be a következőt: BOM_2.</span><span class="sxs-lookup"><span data-stu-id="6735c-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="6735c-161">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="6735c-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="6735c-162">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6735c-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="6735c-163">Ebben a példában adja meg vagy válassza ki a 11. raktárat.</span><span class="sxs-lookup"><span data-stu-id="6735c-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="6735c-164">Kattintson a Fejléc gombra.</span><span class="sxs-lookup"><span data-stu-id="6735c-164">Click Header.</span></span>
20. <span data-ttu-id="6735c-165">Kattintson a Jóváhagyás lehetőségre az anyagjegyzékek jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="6735c-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="6735c-166">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6735c-166">Click OK.</span></span>
22. <span data-ttu-id="6735c-167">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6735c-167">Click Approve.</span></span>
    * <span data-ttu-id="6735c-168">A Jóváhagyás gomb az Anyagjegyzék-verziók szakaszban van az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="6735c-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="6735c-169">Ha nem látható, kattintson a Fejléc elemre az Anyagjegyzékek lapon a Jóváhagyás megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="6735c-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="6735c-170">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6735c-170">Click OK.</span></span>
24. <span data-ttu-id="6735c-171">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="6735c-171">Click Activate.</span></span>
25. <span data-ttu-id="6735c-172">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6735c-172">Close the page.</span></span>
26. <span data-ttu-id="6735c-173">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6735c-173">Close the page.</span></span>
27. <span data-ttu-id="6735c-174">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6735c-174">Close the page.</span></span>

