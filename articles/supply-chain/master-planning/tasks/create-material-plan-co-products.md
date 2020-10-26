---
title: Társtermékek anyagfelhasználási tervének létrehozása
description: A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14de9a1085ac1cae88ad93c35385dd43c60ed4d1
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982209"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="b44a1-103">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="b44a1-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b44a1-104">A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek.</span><span class="sxs-lookup"><span data-stu-id="b44a1-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="b44a1-105">Ez az eljárás az USP2 bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b44a1-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="b44a1-106">Társtermék szükségletének létrehozása</span><span class="sxs-lookup"><span data-stu-id="b44a1-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="b44a1-107">Ugrás az Alapértelmezett irányítópultra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="b44a1-108">Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="b44a1-109">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="b44a1-109">Click New.</span></span>
4. <span data-ttu-id="b44a1-110">Kattintson az Értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-110">Click Sales order.</span></span>
5. <span data-ttu-id="b44a1-111">Írjon be egy értéket a Vevői számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b44a1-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="b44a1-112">Példa: US-001</span><span class="sxs-lookup"><span data-stu-id="b44a1-112">Example: US-001</span></span>  
6. <span data-ttu-id="b44a1-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-113">Click OK.</span></span>
7. <span data-ttu-id="b44a1-114">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b44a1-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="b44a1-115">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="b44a1-115">Example: P6003</span></span>  
8. <span data-ttu-id="b44a1-116">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="b44a1-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="b44a1-117">Példa: 50000</span><span class="sxs-lookup"><span data-stu-id="b44a1-117">Example: 50000</span></span>  
9. <span data-ttu-id="b44a1-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="b44a1-119">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="b44a1-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="b44a1-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b44a1-120">Close the page.</span></span>
2. <span data-ttu-id="b44a1-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b44a1-121">Close the page.</span></span>
3. <span data-ttu-id="b44a1-122">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-122">Click Master planning.</span></span>
4. <span data-ttu-id="b44a1-123">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b44a1-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="b44a1-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b44a1-125">Példa: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="b44a1-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="b44a1-126">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="b44a1-126">Click Run.</span></span>
7. <span data-ttu-id="b44a1-127">Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.</span><span class="sxs-lookup"><span data-stu-id="b44a1-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="b44a1-128">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-128">Click Filter.</span></span>
9. <span data-ttu-id="b44a1-129">A listából válassza ki a Mező = Cikkszám sort.</span><span class="sxs-lookup"><span data-stu-id="b44a1-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="b44a1-130">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b44a1-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="b44a1-131">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="b44a1-131">Example: P6003</span></span>  
11. <span data-ttu-id="b44a1-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-132">Click OK.</span></span>
12. <span data-ttu-id="b44a1-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-133">Click OK.</span></span>
13. <span data-ttu-id="b44a1-134">Kattintson a Tervezett rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="b44a1-134">Click Planned orders.</span></span>
14. <span data-ttu-id="b44a1-135">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="b44a1-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="b44a1-136">Például szűkítsen a Cikkszám mezővel a „P6000” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="b44a1-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="b44a1-137">Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="b44a1-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="b44a1-138">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="b44a1-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="b44a1-139">Válassza ki a szűrő által visszaadott sorok egyikét.</span><span class="sxs-lookup"><span data-stu-id="b44a1-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="b44a1-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="b44a1-141">Bontsa ki vagy csukja össze az Igénykövetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="b44a1-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="b44a1-142">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b44a1-143">A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.</span><span class="sxs-lookup"><span data-stu-id="b44a1-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="b44a1-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b44a1-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="b44a1-145">Társtermék szükségletének létrehozása</span><span class="sxs-lookup"><span data-stu-id="b44a1-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="b44a1-146">Ugrás az Alapértelmezett irányítópultra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="b44a1-147">Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="b44a1-148">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="b44a1-148">Click New.</span></span>
4. <span data-ttu-id="b44a1-149">Kattintson az Értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-149">Click Sales order.</span></span>
5. <span data-ttu-id="b44a1-150">Írjon be egy értéket a Vevői számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b44a1-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="b44a1-151">Példa: US-001</span><span class="sxs-lookup"><span data-stu-id="b44a1-151">Example: US-001</span></span>  
6. <span data-ttu-id="b44a1-152">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-152">Click OK.</span></span>
7. <span data-ttu-id="b44a1-153">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b44a1-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="b44a1-154">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="b44a1-154">Example: P6003</span></span>  
8. <span data-ttu-id="b44a1-155">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="b44a1-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="b44a1-156">Példa: 50000</span><span class="sxs-lookup"><span data-stu-id="b44a1-156">Example: 50000</span></span>  
9. <span data-ttu-id="b44a1-157">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="b44a1-158">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="b44a1-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="b44a1-159">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b44a1-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="b44a1-160">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b44a1-161">Példa: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="b44a1-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="b44a1-162">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="b44a1-162">Click Run.</span></span>
4. <span data-ttu-id="b44a1-163">Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.</span><span class="sxs-lookup"><span data-stu-id="b44a1-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="b44a1-164">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-164">Click Filter.</span></span>
6. <span data-ttu-id="b44a1-165">A listából válassza ki a Mező = Cikkszám sort.</span><span class="sxs-lookup"><span data-stu-id="b44a1-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="b44a1-166">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b44a1-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="b44a1-167">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="b44a1-167">Example: P6003</span></span>  
8. <span data-ttu-id="b44a1-168">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-168">Click OK.</span></span>
9. <span data-ttu-id="b44a1-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-169">Click OK.</span></span>
10. <span data-ttu-id="b44a1-170">Kattintson a Tervezett rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="b44a1-170">Click Planned orders.</span></span>
11. <span data-ttu-id="b44a1-171">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="b44a1-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="b44a1-172">Például szűkítsen a Cikkszám mezővel a „P6000” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="b44a1-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="b44a1-173">Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="b44a1-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="b44a1-174">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="b44a1-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="b44a1-175">Válassza ki a szűrő által visszaadott sorok egyikét.</span><span class="sxs-lookup"><span data-stu-id="b44a1-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="b44a1-176">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="b44a1-177">Bontsa ki vagy csukja össze az Igénykövetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="b44a1-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="b44a1-178">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b44a1-179">A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.</span><span class="sxs-lookup"><span data-stu-id="b44a1-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="b44a1-180">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b44a1-180">Close the page.</span></span>
17. <span data-ttu-id="b44a1-181">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-181">Click Master planning.</span></span>
18. <span data-ttu-id="b44a1-182">Ugorjon az Alaptervezés > Beállítás > Alaptervezés paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="b44a1-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="b44a1-183">Válassza a Nem lehetőséget Az összes tervezési folyamat letiltása mezőben.</span><span class="sxs-lookup"><span data-stu-id="b44a1-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="b44a1-184">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b44a1-184">Close the page.</span></span>

