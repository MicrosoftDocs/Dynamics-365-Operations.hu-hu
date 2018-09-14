--- 
title: "Kiadott termék létrehozása egyetlen vállalat részére"
description: "Ez az eljárás végigvezeti egyetlen kiadott termék létrehozásán egy legális egységgel összefüggésben."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 9265ee4311ac89ae88ff7dd089519251828b1e3c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-released-product-for-a-single-company"></a><span data-ttu-id="d3ad2-103">Kiadott termék létrehozása egyetlen vállalat részére</span><span class="sxs-lookup"><span data-stu-id="d3ad2-103">Create a released product for a single company</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d3ad2-104">Ez az eljárás végigvezeti egyetlen kiadott termék létrehozásán egy legális egységgel összefüggésben.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-104">This procedure walks through how to create a single released product in the context of a single legal unit.</span></span> <span data-ttu-id="d3ad2-105">A kiadott termék létrehozása után az azonnal csak ebben az egységben elérhető.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-105">After the released product is created,  it's immediately available in this unit only.</span></span> <span data-ttu-id="d3ad2-106">Ezt a folyamatot lefuttathatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-106">You can walk through this procedure in demo data company USMF.</span></span> <span data-ttu-id="d3ad2-107">Ezt a feladatot általában egy terméktervező végzi el.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-107">This task is usually performed by a product designer.</span></span>


## <a name="create-a-released-product"></a><span data-ttu-id="d3ad2-108">Kiadott termék létrehozása</span><span class="sxs-lookup"><span data-stu-id="d3ad2-108">Create a released product</span></span>
1. <span data-ttu-id="d3ad2-109">Ugrás a Kiadott termékek elemre.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-109">Go to Released products.</span></span>
2. <span data-ttu-id="d3ad2-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-110">Click New.</span></span>
3. <span data-ttu-id="d3ad2-111">Írjon be egy értéket a Termékszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-111">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="d3ad2-112">Ha termékszám automatikusan nem kerül bele a Termékszám mezőbe, írjon be egy egyedi termékszámot.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-112">If a product number is not automatically entered in the Product number field, type a unique product number.</span></span> <span data-ttu-id="d3ad2-113">Ez a lépés csak akkor szükséges, ha nem lett számsorozat beállítva a termékszámokhoz.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-113">This step is only  required if no number sequence has been set up for product numbers.</span></span>  
4. <span data-ttu-id="d3ad2-114">Írjon be egy értéket a Terméknév mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-114">In the Product name field, type a value.</span></span>
    * <span data-ttu-id="d3ad2-115">A Termék neve alapértelmezés szerint a keresési névből származik.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-115">The Product name is defaulted to the search name.</span></span> <span data-ttu-id="d3ad2-116">Ha szükséges, a keresési nevet módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-116">If needed, you can select to change the search name.</span></span>  
5. <span data-ttu-id="d3ad2-117">A Cikkmodellcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-117">In the Item model group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d3ad2-118">A cikkmodell csoportok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy a rendszer hogyan kezelje a cikkeket a cikkbevételezéseknél és -kiadásoknál.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-118">The item model groups contain settings that determine how items are controlled and handled on item receipts and issues.</span></span> <span data-ttu-id="d3ad2-119">A beállítások azt is megszabják, hogy a rendszer hogyan számítsa ki a cikkek fogyasztását.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-119">The settings also determine how the consumption of items are calculated.</span></span>  
6. <span data-ttu-id="d3ad2-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d3ad2-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-121">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="d3ad2-122">A Cikkcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-122">In the Item group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d3ad2-123">A cikkcsoportok segítségével a cikkjellemzők szerint csoportosítva kezelheti a készletet.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-123">Item groups are used to manage inventory by dividing inventory items into groups based on item characteristics.</span></span> <span data-ttu-id="d3ad2-124">Például, az adatoknak a fő számlák felé történő feladásának módjának kezeléséhez létrehozhat egy sor különböző cikkcsoportot, amely egy adott fő számlához tartozik.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-124">For example, to manage how information is posted to main accounts, you can create a series of different item groups that are associated with specific main accounts.</span></span> <span data-ttu-id="d3ad2-125">Ennek segítségével nyomon követhetők a cikkek készletértéke azok különböző szakaszában.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-125">This lets you track the inventory value of items at different stages.</span></span>  
9. <span data-ttu-id="d3ad2-126">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-126">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="d3ad2-127">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-127">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="d3ad2-128">A Tárolási dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-128">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d3ad2-129">A tárolási dimenziók segítenek a cikkek raktárban való tárolásának és raktárból való kivételének szabályozásában.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-129">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="d3ad2-130">Például a tárolási dimenzió lehet a Hely és a Raktár.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-130">For example, a storage dimension can be Site and Warehouse.</span></span>  
12. <span data-ttu-id="d3ad2-131">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-131">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="d3ad2-132">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-132">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="d3ad2-133">A Nyomon követési dimenzió csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-133">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d3ad2-134">A nyomon követési dimenziócsoport meghatározza, hogy mely nyomon követési dimenziókat adhatja hozzá egy termékhez.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-134">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="d3ad2-135">Például a kötegszám, és a sorozatszám is használható a készletcikkek nyomon követésére.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-135">For example, the batch number and serial number are used to track inventory items.</span></span>  
15. <span data-ttu-id="d3ad2-136">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-136">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="d3ad2-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-137">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="d3ad2-138">A Készletegység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-138">In the Inventory unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d3ad2-139">A készletegység határozza meg, hogy egy termék mennyisége milyen módon van megadva annak készleten való tárolásakor.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-139">The inventory unit determines how the product is quantified when it's stored in inventory.</span></span>  
18. <span data-ttu-id="d3ad2-140">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-140">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="d3ad2-141">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-141">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="d3ad2-142">A Beszerzési egység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-142">In the Purchase unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d3ad2-143">A beszerzési egység meghatározza, hogy egy termék mennyisége milyen módon van megadva, amikor az megvételre kerül egy szállítótól.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-143">The purchase unit determines how the product is quantified when it’s purchased from a vendor.</span></span>  
21. <span data-ttu-id="d3ad2-144">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-144">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="d3ad2-145">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-145">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="d3ad2-146">Az Értékesítési egység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-146">In the Sales unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d3ad2-147">Az értékesítési egység meghatározza, hogy egy termék mennyisége milyen módon van megadva, amikor az eladásra kerül egy ügyfél számára.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-147">The sales unit determines how the product is quantified when it’s sold to a customer.</span></span>  
24. <span data-ttu-id="d3ad2-148">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-148">In the list, find and select the desired record.</span></span>
25. <span data-ttu-id="d3ad2-149">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-149">In the list, click the link in the selected row.</span></span>
26. <span data-ttu-id="d3ad2-150">Az Anyagjegyzékegység mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-150">In the BOM unit field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d3ad2-151">Az anyagjegyzékegység határozza meg, hogy egy termék mennyisége milyen módon van megadva, amikor az hozzáadásra kerül egy anyagjegyzékhez.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-151">The BOM unit determines how the product is quantified when including it in a bill of materials (BOM).</span></span>  
27. <span data-ttu-id="d3ad2-152">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-152">In the list, find and select the desired record.</span></span>
28. <span data-ttu-id="d3ad2-153">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-153">In the list, click the link in the selected row.</span></span>
29. <span data-ttu-id="d3ad2-154">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-154">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d3ad2-155">Az Értékesítési áfacsoporton belüli cikkáfacsoport határozza meg, hogy az adott elemekhez milyen módon kerüljön kiszámításra a forgalmi adó.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-155">The item sales tax group in the Sales taxation group determines how sales tax is calculated for each item.</span></span>  
30. <span data-ttu-id="d3ad2-156">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-156">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="d3ad2-157">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-157">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="d3ad2-158">A Cikkáfacsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-158">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d3ad2-159">A Beszerzési áfacsoporton belüli cikkáfacsoport határozza meg, hogy az adott elemekhez milyen módon kerüljön kiszámításra a beszerzési adó.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-159">The item sales tax group in the Purchase taxation group determines how purchase tax is calculated for each item.</span></span>  
33. <span data-ttu-id="d3ad2-160">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-160">In the list, find and select the desired record.</span></span>
34. <span data-ttu-id="d3ad2-161">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-161">In the list, click the link in the selected row.</span></span>
35. <span data-ttu-id="d3ad2-162">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-162">Click OK.</span></span>

## <a name="add-product-characteristics"></a><span data-ttu-id="d3ad2-163">Termékjellemzők megadása</span><span class="sxs-lookup"><span data-stu-id="d3ad2-163">Add product characteristics</span></span>
1. <span data-ttu-id="d3ad2-164">Bontsa ki vagy csukja össze a Készletkezelés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-164">Expand or collapse the Manage inventory section.</span></span>
2. <span data-ttu-id="d3ad2-165">Adjon meg egy számot a Nettó tömeg mezőben.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-165">In the Net weight field, enter a number.</span></span>
3. <span data-ttu-id="d3ad2-166">Adjon meg egy számot a Tárasúly mezőben.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-166">In the Tare weight field, enter a number.</span></span>
4. <span data-ttu-id="d3ad2-167">Adjon meg egy számot a Bruttó mélység mezőben.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-167">In the Gross depth field, enter a number.</span></span>
5. <span data-ttu-id="d3ad2-168">Adjon meg egy számot a Bruttó szélesség mezőben.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-168">In the Gross width field, enter a number.</span></span>
6. <span data-ttu-id="d3ad2-169">Adjon meg egy számot a Bruttó magasság mezőben.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-169">In the Gross height field, enter a number.</span></span>
7. <span data-ttu-id="d3ad2-170">A Térfogat mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-170">In the Volume field, enter a number.</span></span>

## <a name="add-financial-dimensions"></a><span data-ttu-id="d3ad2-171">Pénzügyi dimenziók hozzáadása</span><span class="sxs-lookup"><span data-stu-id="d3ad2-171">Add financial dimensions</span></span>
1. <span data-ttu-id="d3ad2-172">Bontsa ki vagy csukja össze a Pénzügyi dimenziók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-172">Expand or collapse the Financial dimensions section.</span></span>
2. <span data-ttu-id="d3ad2-173">A BusinessUnit mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-173">In the BusinessUnit field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="d3ad2-174">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="d3ad2-174">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="d3ad2-175">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-175">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d3ad2-176">A CostCenter mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-176">In the CostCenter field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="d3ad2-177">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="d3ad2-177">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d3ad2-178">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-178">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="d3ad2-179">A Részleg mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-179">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="d3ad2-180">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="d3ad2-180">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="d3ad2-181">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-181">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="d3ad2-182">Az ItemGroup mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-182">In the ItemGroup field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="d3ad2-183">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="d3ad2-183">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="d3ad2-184">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d3ad2-184">In the list, click the link in the selected row.</span></span>


