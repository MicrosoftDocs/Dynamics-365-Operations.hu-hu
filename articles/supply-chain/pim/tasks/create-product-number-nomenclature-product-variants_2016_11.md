---
title: Termékszám elnevezési rendszerének létrehozása konfigurált termékváltozatokhoz
description: Ez az eljárás bemutatja, hogyan állítható be termékszámozás-elnevezési rendszer konfigurált termékváltozatok számára, és hogyan rendelhető hozzá konfigurálható alaptermékhez.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a837721db5281b0626f37b7a793349b91afa6f85
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147756"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="aaeaf-103">Termékszám elnevezési rendszerének létrehozása konfigurált termékváltozatokhoz</span><span class="sxs-lookup"><span data-stu-id="aaeaf-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aaeaf-104">Ez az eljárás bemutatja, hogyan állítható be termékszámozás-elnevezési rendszer konfigurált termékváltozatok számára, és hogyan rendelhető hozzá konfigurálható alaptermékhez.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="aaeaf-105">Az eljárás emellett bemutatja, hogyan készíthető konfigurációelnevezési rendszer termékkonfigurációs modell összetevőjéhez.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="aaeaf-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="aaeaf-107">Az új termékszám-elnevezési rendszer a D0004 alaptermékhez van rendelve.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="aaeaf-108">Ezt a feladatot általában egy terméktervező végzi.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="aaeaf-109">Termékszámozási rendszer létrehozása</span><span class="sxs-lookup"><span data-stu-id="aaeaf-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="aaeaf-110">Kattintson a Termékváltozat modelldefinícióra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="aaeaf-111">Kattintson a Termékek elnevezési rendszere elemre</span><span class="sxs-lookup"><span data-stu-id="aaeaf-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="aaeaf-112">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-112">Click New.</span></span>
4. <span data-ttu-id="aaeaf-113">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="aaeaf-114">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="aaeaf-115">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-115">Click Add.</span></span>
7. <span data-ttu-id="aaeaf-116">Kattintson az Alaptermék száma elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-116">Click Product master number.</span></span>
8. <span data-ttu-id="aaeaf-117">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-117">Click Add.</span></span>
9. <span data-ttu-id="aaeaf-118">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-118">Click Text constant.</span></span>
10. <span data-ttu-id="aaeaf-119">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="aaeaf-120">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="aaeaf-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-121">Click Add.</span></span>
13. <span data-ttu-id="aaeaf-122">Kattintson a Konfiguráció lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-122">Click Configuration.</span></span>
14. <span data-ttu-id="aaeaf-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="aaeaf-124">Termékszámozási rendszer hozzárendelése az alaptermékhez</span><span class="sxs-lookup"><span data-stu-id="aaeaf-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="aaeaf-125">Kattintson az Összes alaptermék elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-125">Click Product masters.</span></span>
2. <span data-ttu-id="aaeaf-126">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="aaeaf-127">Például szűkítsen a Termékszám mezőre a „D” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="aaeaf-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="aaeaf-129">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-129">Click Edit.</span></span>
5. <span data-ttu-id="aaeaf-130">Válassza az Igen lehetőséget az Elnevezési rendszer használata mezőben.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="aaeaf-131">A Termékváltozat-számozási rendszer mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="aaeaf-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-132">Close the page.</span></span>
8. <span data-ttu-id="aaeaf-133">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="aaeaf-134">Elnevezési rendszer létrehozása egy termékkonfigurációs modell összetevőjéhez</span><span class="sxs-lookup"><span data-stu-id="aaeaf-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="aaeaf-135">Kattintson a Termékkonfigurációs modellek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="aaeaf-136">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="aaeaf-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="aaeaf-138">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-138">Click Edit.</span></span>
5. <span data-ttu-id="aaeaf-139">Válassza az Igen lehetőséget a Konfiguráció elnevezési rendszerének használata mezőben.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="aaeaf-140">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-140">Click Add.</span></span>
7. <span data-ttu-id="aaeaf-141">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-141">Click Attribute value.</span></span>
8. <span data-ttu-id="aaeaf-142">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="aaeaf-143">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="aaeaf-144">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-144">Click Add.</span></span>
11. <span data-ttu-id="aaeaf-145">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-145">Click Text constant.</span></span>
12. <span data-ttu-id="aaeaf-146">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="aaeaf-147">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="aaeaf-148">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-148">Click Add.</span></span>
15. <span data-ttu-id="aaeaf-149">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-149">Click Attribute value.</span></span>
16. <span data-ttu-id="aaeaf-150">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="aaeaf-151">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="aaeaf-152">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-152">Click Add.</span></span>
19. <span data-ttu-id="aaeaf-153">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-153">Click Text constant.</span></span>
20. <span data-ttu-id="aaeaf-154">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="aaeaf-155">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="aaeaf-156">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-156">Click Add.</span></span>
23. <span data-ttu-id="aaeaf-157">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-157">Click Attribute value.</span></span>
24. <span data-ttu-id="aaeaf-158">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="aaeaf-159">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="aaeaf-160">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-160">Click Add.</span></span>
27. <span data-ttu-id="aaeaf-161">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-161">Click Text constant.</span></span>
28. <span data-ttu-id="aaeaf-162">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="aaeaf-163">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="aaeaf-164">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-164">Click Add.</span></span>
31. <span data-ttu-id="aaeaf-165">Kattintson az Attribútum értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-165">Click Attribute value.</span></span>
32. <span data-ttu-id="aaeaf-166">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="aaeaf-167">Az Attribútum mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="aaeaf-168">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-168">Click Add.</span></span>
35. <span data-ttu-id="aaeaf-169">Kattintson a Szöveges állandó elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-169">Click Text constant.</span></span>
36. <span data-ttu-id="aaeaf-170">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="aaeaf-171">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="aaeaf-172">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-172">Click Add.</span></span>
39. <span data-ttu-id="aaeaf-173">Kattintson a Számsorozat értéke elemre.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="aaeaf-174">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="aaeaf-175">A Számsorrend mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="aaeaf-176">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-176">Close the page.</span></span>
43. <span data-ttu-id="aaeaf-177">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-177">Close the page.</span></span>
44. <span data-ttu-id="aaeaf-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="aaeaf-178">Close the page.</span></span>

