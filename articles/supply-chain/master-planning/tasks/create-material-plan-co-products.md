---
title: Társtermékek anyagfelhasználási tervének létrehozása
description: A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2958f1e5c2e8a0cfa9cc6312f688d3b11b8e013c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "337141"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="12194-103">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="12194-103">Create a material plan for co products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="12194-104">A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek.</span><span class="sxs-lookup"><span data-stu-id="12194-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="12194-105">Ez az eljárás az USP2 bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="12194-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="12194-106">Társtermék szükségletének létrehozása</span><span class="sxs-lookup"><span data-stu-id="12194-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="12194-107">Ugrás az Alapértelmezett irányítópultra.</span><span class="sxs-lookup"><span data-stu-id="12194-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="12194-108">Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.</span><span class="sxs-lookup"><span data-stu-id="12194-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="12194-109">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="12194-109">Click New.</span></span>
4. <span data-ttu-id="12194-110">Kattintson az Értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="12194-110">Click Sales order.</span></span>
5. <span data-ttu-id="12194-111">Írjon be egy értéket a Vevői számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="12194-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="12194-112">Példa: US-001</span><span class="sxs-lookup"><span data-stu-id="12194-112">Example: US-001</span></span>  
6. <span data-ttu-id="12194-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12194-113">Click OK.</span></span>
7. <span data-ttu-id="12194-114">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12194-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="12194-115">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="12194-115">Example: P6003</span></span>  
8. <span data-ttu-id="12194-116">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="12194-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="12194-117">Példa: 50000</span><span class="sxs-lookup"><span data-stu-id="12194-117">Example: 50000</span></span>  
9. <span data-ttu-id="12194-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="12194-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="12194-119">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="12194-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="12194-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12194-120">Close the page.</span></span>
2. <span data-ttu-id="12194-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12194-121">Close the page.</span></span>
3. <span data-ttu-id="12194-122">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="12194-122">Click Master planning.</span></span>
4. <span data-ttu-id="12194-123">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="12194-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="12194-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="12194-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="12194-125">Példa: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="12194-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="12194-126">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="12194-126">Click Run.</span></span>
7. <span data-ttu-id="12194-127">Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.</span><span class="sxs-lookup"><span data-stu-id="12194-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="12194-128">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="12194-128">Click Filter.</span></span>
9. <span data-ttu-id="12194-129">A listából válassza ki a Mező = Cikkszám sort.</span><span class="sxs-lookup"><span data-stu-id="12194-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="12194-130">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="12194-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="12194-131">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="12194-131">Example: P6003</span></span>  
11. <span data-ttu-id="12194-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12194-132">Click OK.</span></span>
12. <span data-ttu-id="12194-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12194-133">Click OK.</span></span>
13. <span data-ttu-id="12194-134">Kattintson a Tervezett rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="12194-134">Click Planned orders.</span></span>
14. <span data-ttu-id="12194-135">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="12194-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="12194-136">Például szűkítsen a Cikkszám mezővel a „P6000” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="12194-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="12194-137">Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="12194-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="12194-138">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="12194-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="12194-139">Válassza ki a szűrő által visszaadott sorok egyikét.</span><span class="sxs-lookup"><span data-stu-id="12194-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="12194-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="12194-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="12194-141">Bontsa ki vagy csukja össze az Igénykövetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="12194-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="12194-142">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="12194-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="12194-143">A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.</span><span class="sxs-lookup"><span data-stu-id="12194-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="12194-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12194-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="12194-145">Társtermék szükségletének létrehozása</span><span class="sxs-lookup"><span data-stu-id="12194-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="12194-146">Ugrás az Alapértelmezett irányítópultra.</span><span class="sxs-lookup"><span data-stu-id="12194-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="12194-147">Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.</span><span class="sxs-lookup"><span data-stu-id="12194-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="12194-148">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="12194-148">Click New.</span></span>
4. <span data-ttu-id="12194-149">Kattintson az Értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="12194-149">Click Sales order.</span></span>
5. <span data-ttu-id="12194-150">Írjon be egy értéket a Vevői számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="12194-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="12194-151">Példa: US-001</span><span class="sxs-lookup"><span data-stu-id="12194-151">Example: US-001</span></span>  
6. <span data-ttu-id="12194-152">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12194-152">Click OK.</span></span>
7. <span data-ttu-id="12194-153">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="12194-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="12194-154">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="12194-154">Example: P6003</span></span>  
8. <span data-ttu-id="12194-155">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="12194-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="12194-156">Példa: 50000</span><span class="sxs-lookup"><span data-stu-id="12194-156">Example: 50000</span></span>  
9. <span data-ttu-id="12194-157">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="12194-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="12194-158">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="12194-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="12194-159">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="12194-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="12194-160">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="12194-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="12194-161">Példa: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="12194-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="12194-162">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="12194-162">Click Run.</span></span>
4. <span data-ttu-id="12194-163">Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.</span><span class="sxs-lookup"><span data-stu-id="12194-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="12194-164">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="12194-164">Click Filter.</span></span>
6. <span data-ttu-id="12194-165">A listából válassza ki a Mező = Cikkszám sort.</span><span class="sxs-lookup"><span data-stu-id="12194-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="12194-166">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="12194-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="12194-167">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="12194-167">Example: P6003</span></span>  
8. <span data-ttu-id="12194-168">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12194-168">Click OK.</span></span>
9. <span data-ttu-id="12194-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="12194-169">Click OK.</span></span>
10. <span data-ttu-id="12194-170">Kattintson a Tervezett rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="12194-170">Click Planned orders.</span></span>
11. <span data-ttu-id="12194-171">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="12194-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="12194-172">Például szűkítsen a Cikkszám mezővel a „P6000” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="12194-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="12194-173">Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="12194-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="12194-174">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="12194-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="12194-175">Válassza ki a szűrő által visszaadott sorok egyikét.</span><span class="sxs-lookup"><span data-stu-id="12194-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="12194-176">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="12194-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="12194-177">Bontsa ki vagy csukja össze az Igénykövetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="12194-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="12194-178">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="12194-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="12194-179">A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.</span><span class="sxs-lookup"><span data-stu-id="12194-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="12194-180">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12194-180">Close the page.</span></span>
17. <span data-ttu-id="12194-181">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="12194-181">Click Master planning.</span></span>
18. <span data-ttu-id="12194-182">Ugorjon az Alaptervezés > Beállítás > Alaptervezés paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="12194-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="12194-183">Válassza a Nem lehetőséget Az összes tervezési folyamat letiltása mezőben.</span><span class="sxs-lookup"><span data-stu-id="12194-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="12194-184">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="12194-184">Close the page.</span></span>

