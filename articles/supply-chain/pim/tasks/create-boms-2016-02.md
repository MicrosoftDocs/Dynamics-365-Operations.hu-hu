---
title: Anyagjegyzékek létrehozása (2016. február)
description: Ez a feladat anyagjegyzék-struktúra létrehozására koncentrál egy késztermékhez és egy félkész termékhez.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c5cfb8aae1a61d14f7a7969f688cb282530840d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568558"
---
# <a name="create-boms-february-2016"></a><span data-ttu-id="f7f5e-103">Anyagjegyzékek létrehozása (2016. február)</span><span class="sxs-lookup"><span data-stu-id="f7f5e-103">Create BOMs (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f7f5e-104">Ez a feladat anyagjegyzék-struktúra létrehozására koncentrál egy késztermékhez és egy félkész termékhez.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="f7f5e-105">Ez az anyagjegyzék-számítási sorozat negyedik feladata.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="f7f5e-106">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="f7f5e-107">Anyagjegyzék létrehozása egy félkész termékhez</span><span class="sxs-lookup"><span data-stu-id="f7f5e-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="f7f5e-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="f7f5e-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f7f5e-110">Válassza ki a BOM_2 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="f7f5e-111">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="f7f5e-112">Kattintson az Anyagjegyzék verziókra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-112">Click BOM versions.</span></span>
5. <span data-ttu-id="f7f5e-113">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-113">Click New.</span></span>
6. <span data-ttu-id="f7f5e-114">Kattintson az Anyagjegyzék és az Anyagjegyzék verzió elemre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="f7f5e-115">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="f7f5e-116">Például írja be a BOM_2 értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="f7f5e-117">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7f5e-118">Ebben a példában adja meg vagy válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="f7f5e-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-119">Click OK.</span></span>
10. <span data-ttu-id="f7f5e-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-120">Click New.</span></span>
11. <span data-ttu-id="f7f5e-121">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="f7f5e-122">Ehhez a példához írja be a következőt: ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="f7f5e-123">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="f7f5e-124">Ebben a példában adja meg vagy válassza ki a következőt: 11.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="f7f5e-125">Kattintson a Fejléc gombra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-125">Click Header.</span></span>
14. <span data-ttu-id="f7f5e-126">Kattintson a Jóváhagyás lehetőségre az anyagjegyzékek jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="f7f5e-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-127">Click OK.</span></span>
16. <span data-ttu-id="f7f5e-128">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-128">Click Approve.</span></span>
    * <span data-ttu-id="f7f5e-129">A Jóváhagyás gomb az Anyagjegyzék-verziók szakaszban van az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="f7f5e-130">Ha nem látható, kattintson a Fejléc elemre az Anyagjegyzékek lapon a Jóváhagyás megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="f7f5e-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-131">Click OK.</span></span>
18. <span data-ttu-id="f7f5e-132">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-132">Click Activate.</span></span>
19. <span data-ttu-id="f7f5e-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-133">Close the page.</span></span>
20. <span data-ttu-id="f7f5e-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-134">Close the page.</span></span>
21. <span data-ttu-id="f7f5e-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="f7f5e-136">Anyagjegyzék létrehozása egy késztermékhez</span><span class="sxs-lookup"><span data-stu-id="f7f5e-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="f7f5e-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f7f5e-138">Válassza ki a BOM_1 cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="f7f5e-139">A Művelet panelen kattintson a Mérnök elemre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="f7f5e-140">Kattintson az Anyagjegyzék verziókra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-140">Click BOM versions.</span></span>
4. <span data-ttu-id="f7f5e-141">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-141">Click New.</span></span>
5. <span data-ttu-id="f7f5e-142">Kattintson az Anyagjegyzék és az Anyagjegyzék verzió elemre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="f7f5e-143">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="f7f5e-144">Például írja be a BOM_1 értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="f7f5e-145">A Hely mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f7f5e-146">Ebben a példában adja meg vagy válassza ki az 1. helyet.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="f7f5e-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-147">Click OK.</span></span>
9. <span data-ttu-id="f7f5e-148">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-148">Click New.</span></span>
10. <span data-ttu-id="f7f5e-149">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="f7f5e-150">Ehhez a példához írja be a következőt: ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="f7f5e-151">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="f7f5e-152">Ehhez a példához válassza ki a következőt: 11.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="f7f5e-153">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-153">Click New.</span></span>
13. <span data-ttu-id="f7f5e-154">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="f7f5e-155">Ehhez a példához írja be a következőt: ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="f7f5e-156">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="f7f5e-157">Ebben a példában adja meg vagy válassza ki a következőt: 11.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="f7f5e-158">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-158">Click New.</span></span>
16. <span data-ttu-id="f7f5e-159">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="f7f5e-160">Ehhez a példához írja be a következőt: BOM_2.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="f7f5e-161">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="f7f5e-162">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="f7f5e-163">Ebben a példában adja meg vagy válassza ki a 11. raktárat.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="f7f5e-164">Kattintson a Fejléc gombra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-164">Click Header.</span></span>
20. <span data-ttu-id="f7f5e-165">Kattintson a Jóváhagyás lehetőségre az anyagjegyzékek jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="f7f5e-166">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-166">Click OK.</span></span>
22. <span data-ttu-id="f7f5e-167">Kattintson a Jóváhagyás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-167">Click Approve.</span></span>
    * <span data-ttu-id="f7f5e-168">A Jóváhagyás gomb az Anyagjegyzék-verziók szakaszban van az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="f7f5e-169">Ha nem látható, kattintson a Fejléc elemre az Anyagjegyzékek lapon a Jóváhagyás megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="f7f5e-170">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-170">Click OK.</span></span>
24. <span data-ttu-id="f7f5e-171">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-171">Click Activate.</span></span>
25. <span data-ttu-id="f7f5e-172">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-172">Close the page.</span></span>
26. <span data-ttu-id="f7f5e-173">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-173">Close the page.</span></span>
27. <span data-ttu-id="f7f5e-174">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f7f5e-174">Close the page.</span></span>

