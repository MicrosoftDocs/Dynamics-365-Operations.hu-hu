---
title: Termékszám elnevezési rendszerének létrehozása konfigurált termékváltozatokhoz
description: Ez az eljárás bemutatja, hogyan állítható be termékszámozás-elnevezési rendszer konfigurált termékváltozatok számára, és hogyan rendelhető hozzá konfigurálható alaptermékhez.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f75d7e493255b9c09c10b121f388854861cb0fc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429515"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="47104-103">Termékszám elnevezési rendszerének létrehozása konfigurált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="47104-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="47104-104">Ez az eljárás bemutatja, hogyan állítható be termékszámozás-elnevezési rendszer konfigurált termékváltozatok számára, és hogyan rendelhető hozzá konfigurálható alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="47104-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="47104-105">Az eljárás emellett bemutatja, hogyan készíthető konfigurációelnevezési rendszer termékkonfigurációs modell összetevőjéhez.</span><span class="sxs-lookup"><span data-stu-id="47104-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="47104-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="47104-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="47104-107">Az új termékszám-elnevezési rendszer a D0004 alaptermékhez van rendelve.</span><span class="sxs-lookup"><span data-stu-id="47104-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="47104-108">Ezt a feladatot általában egy terméktervező végzi.</span><span class="sxs-lookup"><span data-stu-id="47104-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="47104-109">Termékszámozási rendszer létrehozása</span><span class="sxs-lookup"><span data-stu-id="47104-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="47104-110">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="47104-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="47104-111">Kattintson a Termékek elnevezési rendszere elemre</span><span class="sxs-lookup"><span data-stu-id="47104-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="47104-112">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-112">Click New.</span></span>
4. <span data-ttu-id="47104-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="47104-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="47104-114">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="47104-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="47104-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-115">Click Add.</span></span>
7. <span data-ttu-id="47104-116">Kattintson az Alaptermék száma elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-116">Click Product master number.</span></span>
8. <span data-ttu-id="47104-117">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-117">Click Add.</span></span>
9. <span data-ttu-id="47104-118">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-118">Click Text constant.</span></span>
10. <span data-ttu-id="47104-119">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="47104-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="47104-120">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="47104-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="47104-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-121">Click Add.</span></span>
13. <span data-ttu-id="47104-122">Kattintson a Konfiguráció lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47104-122">Click Configuration.</span></span>
14. <span data-ttu-id="47104-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="47104-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="47104-124">Termékszámozási rendszer hozzárendelése az alaptermékhez</span><span class="sxs-lookup"><span data-stu-id="47104-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="47104-125">Kattintson az Összes alaptermék elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-125">Click Product masters.</span></span>
2. <span data-ttu-id="47104-126">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="47104-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="47104-127">Például szűkítsen a Termékszám mezőre a „D” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="47104-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="47104-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="47104-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="47104-129">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47104-129">Click Edit.</span></span>
5. <span data-ttu-id="47104-130">Válassza az Igen lehetőséget az Elnevezési rendszer használata mezőben.</span><span class="sxs-lookup"><span data-stu-id="47104-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="47104-131">A Termékváltozat-számozási rendszer mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="47104-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="47104-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="47104-132">Close the page.</span></span>
8. <span data-ttu-id="47104-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="47104-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="47104-134">Elnevezési rendszer létrehozása egy termékkonfigurációs modell összetevőjéhez</span><span class="sxs-lookup"><span data-stu-id="47104-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="47104-135">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47104-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="47104-136">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="47104-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="47104-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="47104-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="47104-138">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47104-138">Click Edit.</span></span>
5. <span data-ttu-id="47104-139">Válassza az Igen lehetőséget a Konfiguráció elnevezési rendszerének használata mezőben.</span><span class="sxs-lookup"><span data-stu-id="47104-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="47104-140">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-140">Click Add.</span></span>
7. <span data-ttu-id="47104-141">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-141">Click Attribute value.</span></span>
8. <span data-ttu-id="47104-142">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="47104-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="47104-143">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="47104-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="47104-144">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-144">Click Add.</span></span>
11. <span data-ttu-id="47104-145">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-145">Click Text constant.</span></span>
12. <span data-ttu-id="47104-146">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="47104-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="47104-147">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="47104-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="47104-148">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-148">Click Add.</span></span>
15. <span data-ttu-id="47104-149">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-149">Click Attribute value.</span></span>
16. <span data-ttu-id="47104-150">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="47104-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="47104-151">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="47104-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="47104-152">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-152">Click Add.</span></span>
19. <span data-ttu-id="47104-153">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-153">Click Text constant.</span></span>
20. <span data-ttu-id="47104-154">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="47104-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="47104-155">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="47104-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="47104-156">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-156">Click Add.</span></span>
23. <span data-ttu-id="47104-157">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-157">Click Attribute value.</span></span>
24. <span data-ttu-id="47104-158">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="47104-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="47104-159">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="47104-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="47104-160">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-160">Click Add.</span></span>
27. <span data-ttu-id="47104-161">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-161">Click Text constant.</span></span>
28. <span data-ttu-id="47104-162">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="47104-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="47104-163">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="47104-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="47104-164">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-164">Click Add.</span></span>
31. <span data-ttu-id="47104-165">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-165">Click Attribute value.</span></span>
32. <span data-ttu-id="47104-166">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="47104-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="47104-167">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="47104-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="47104-168">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-168">Click Add.</span></span>
35. <span data-ttu-id="47104-169">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-169">Click Text constant.</span></span>
36. <span data-ttu-id="47104-170">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="47104-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="47104-171">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="47104-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="47104-172">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="47104-172">Click Add.</span></span>
39. <span data-ttu-id="47104-173">Kattintson a Számsorozat értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="47104-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="47104-174">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="47104-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="47104-175">A Számsorrend mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="47104-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="47104-176">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="47104-176">Close the page.</span></span>
43. <span data-ttu-id="47104-177">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="47104-177">Close the page.</span></span>
44. <span data-ttu-id="47104-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="47104-178">Close the page.</span></span>

