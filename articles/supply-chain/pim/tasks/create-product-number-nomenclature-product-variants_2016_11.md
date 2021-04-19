---
title: Termékszám elnevezési rendszerének létrehozása konfigurált termékváltozatokhoz
description: Ez az eljárás bemutatja, hogyan állítható be termékszámozás-elnevezési rendszer konfigurált termékváltozatok számára, és hogyan rendelhető hozzá konfigurálható alaptermékhez.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f342831d95f9988f9bb7807bac986e43cb317e0f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820009"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="8b782-103">Termékszám elnevezési rendszerének létrehozása konfigurált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="8b782-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8b782-104">Ez az eljárás bemutatja, hogyan állítható be termékszámozás-elnevezési rendszer konfigurált termékváltozatok számára, és hogyan rendelhető hozzá konfigurálható alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="8b782-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="8b782-105">Az eljárás emellett bemutatja, hogyan készíthető konfigurációelnevezési rendszer termékkonfigurációs modell összetevőjéhez.</span><span class="sxs-lookup"><span data-stu-id="8b782-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="8b782-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="8b782-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8b782-107">Az új termékszám-elnevezési rendszer a D0004 alaptermékhez van rendelve.</span><span class="sxs-lookup"><span data-stu-id="8b782-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="8b782-108">Ezt a feladatot általában egy terméktervező végzi.</span><span class="sxs-lookup"><span data-stu-id="8b782-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="8b782-109">Termékszámozási rendszer létrehozása</span><span class="sxs-lookup"><span data-stu-id="8b782-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="8b782-110">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="8b782-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="8b782-111">Kattintson a Termékek elnevezési rendszere elemre</span><span class="sxs-lookup"><span data-stu-id="8b782-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="8b782-112">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-112">Click New.</span></span>
4. <span data-ttu-id="8b782-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8b782-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="8b782-114">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8b782-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="8b782-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-115">Click Add.</span></span>
7. <span data-ttu-id="8b782-116">Kattintson az Alaptermék száma elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-116">Click Product master number.</span></span>
8. <span data-ttu-id="8b782-117">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-117">Click Add.</span></span>
9. <span data-ttu-id="8b782-118">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-118">Click Text constant.</span></span>
10. <span data-ttu-id="8b782-119">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8b782-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="8b782-120">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8b782-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="8b782-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-121">Click Add.</span></span>
13. <span data-ttu-id="8b782-122">Kattintson a Konfiguráció lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8b782-122">Click Configuration.</span></span>
14. <span data-ttu-id="8b782-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8b782-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="8b782-124">Termékszámozási rendszer hozzárendelése az alaptermékhez</span><span class="sxs-lookup"><span data-stu-id="8b782-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="8b782-125">Kattintson az Összes alaptermék elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-125">Click Product masters.</span></span>
2. <span data-ttu-id="8b782-126">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="8b782-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="8b782-127">Például szűkítsen a Termékszám mezőre a „D” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="8b782-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="8b782-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8b782-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8b782-129">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8b782-129">Click Edit.</span></span>
5. <span data-ttu-id="8b782-130">Válassza az Igen lehetőséget az Elnevezési rendszer használata mezőben.</span><span class="sxs-lookup"><span data-stu-id="8b782-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="8b782-131">A Termékváltozat-számozási rendszer mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8b782-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="8b782-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8b782-132">Close the page.</span></span>
8. <span data-ttu-id="8b782-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8b782-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="8b782-134">Elnevezési rendszer létrehozása egy termékkonfigurációs modell összetevőjéhez</span><span class="sxs-lookup"><span data-stu-id="8b782-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="8b782-135">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8b782-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="8b782-136">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8b782-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="8b782-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8b782-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8b782-138">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8b782-138">Click Edit.</span></span>
5. <span data-ttu-id="8b782-139">Válassza az Igen lehetőséget a Konfiguráció elnevezési rendszerének használata mezőben.</span><span class="sxs-lookup"><span data-stu-id="8b782-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="8b782-140">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-140">Click Add.</span></span>
7. <span data-ttu-id="8b782-141">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-141">Click Attribute value.</span></span>
8. <span data-ttu-id="8b782-142">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8b782-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="8b782-143">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8b782-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="8b782-144">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-144">Click Add.</span></span>
11. <span data-ttu-id="8b782-145">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-145">Click Text constant.</span></span>
12. <span data-ttu-id="8b782-146">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8b782-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="8b782-147">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8b782-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="8b782-148">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-148">Click Add.</span></span>
15. <span data-ttu-id="8b782-149">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-149">Click Attribute value.</span></span>
16. <span data-ttu-id="8b782-150">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8b782-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="8b782-151">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8b782-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="8b782-152">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-152">Click Add.</span></span>
19. <span data-ttu-id="8b782-153">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-153">Click Text constant.</span></span>
20. <span data-ttu-id="8b782-154">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8b782-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="8b782-155">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8b782-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="8b782-156">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-156">Click Add.</span></span>
23. <span data-ttu-id="8b782-157">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-157">Click Attribute value.</span></span>
24. <span data-ttu-id="8b782-158">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8b782-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="8b782-159">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8b782-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="8b782-160">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-160">Click Add.</span></span>
27. <span data-ttu-id="8b782-161">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-161">Click Text constant.</span></span>
28. <span data-ttu-id="8b782-162">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8b782-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="8b782-163">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8b782-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="8b782-164">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-164">Click Add.</span></span>
31. <span data-ttu-id="8b782-165">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-165">Click Attribute value.</span></span>
32. <span data-ttu-id="8b782-166">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8b782-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="8b782-167">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8b782-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="8b782-168">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-168">Click Add.</span></span>
35. <span data-ttu-id="8b782-169">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-169">Click Text constant.</span></span>
36. <span data-ttu-id="8b782-170">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8b782-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="8b782-171">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8b782-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="8b782-172">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="8b782-172">Click Add.</span></span>
39. <span data-ttu-id="8b782-173">Kattintson a Számsorozat értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="8b782-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="8b782-174">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="8b782-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="8b782-175">A Számsorrend mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8b782-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="8b782-176">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8b782-176">Close the page.</span></span>
43. <span data-ttu-id="8b782-177">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8b782-177">Close the page.</span></span>
44. <span data-ttu-id="8b782-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8b782-178">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]