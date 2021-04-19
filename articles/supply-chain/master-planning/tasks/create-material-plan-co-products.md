---
title: Társtermékek anyagfelhasználási tervének létrehozása
description: A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d910b89330865b0bcf3f6cd05b761506f339a45f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841671"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="e2000-103">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="e2000-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e2000-104">A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek.</span><span class="sxs-lookup"><span data-stu-id="e2000-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="e2000-105">Ez az eljárás az USP2 bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e2000-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="e2000-106">Társtermék szükségletének létrehozása</span><span class="sxs-lookup"><span data-stu-id="e2000-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="e2000-107">Ugrás az Alapértelmezett irányítópultra.</span><span class="sxs-lookup"><span data-stu-id="e2000-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="e2000-108">Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.</span><span class="sxs-lookup"><span data-stu-id="e2000-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="e2000-109">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="e2000-109">Click New.</span></span>
4. <span data-ttu-id="e2000-110">Kattintson az Értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="e2000-110">Click Sales order.</span></span>
5. <span data-ttu-id="e2000-111">Írjon be egy értéket a Vevői számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e2000-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="e2000-112">Példa: US-001</span><span class="sxs-lookup"><span data-stu-id="e2000-112">Example: US-001</span></span>  
6. <span data-ttu-id="e2000-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2000-113">Click OK.</span></span>
7. <span data-ttu-id="e2000-114">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e2000-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="e2000-115">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="e2000-115">Example: P6003</span></span>  
8. <span data-ttu-id="e2000-116">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2000-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="e2000-117">Példa: 50000</span><span class="sxs-lookup"><span data-stu-id="e2000-117">Example: 50000</span></span>  
9. <span data-ttu-id="e2000-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e2000-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="e2000-119">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="e2000-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="e2000-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e2000-120">Close the page.</span></span>
2. <span data-ttu-id="e2000-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e2000-121">Close the page.</span></span>
3. <span data-ttu-id="e2000-122">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="e2000-122">Click Master planning.</span></span>
4. <span data-ttu-id="e2000-123">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e2000-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="e2000-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2000-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e2000-125">Példa: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="e2000-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="e2000-126">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="e2000-126">Click Run.</span></span>
7. <span data-ttu-id="e2000-127">Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.</span><span class="sxs-lookup"><span data-stu-id="e2000-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="e2000-128">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="e2000-128">Click Filter.</span></span>
9. <span data-ttu-id="e2000-129">A listából válassza ki a Mező = Cikkszám sort.</span><span class="sxs-lookup"><span data-stu-id="e2000-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="e2000-130">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e2000-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="e2000-131">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="e2000-131">Example: P6003</span></span>  
11. <span data-ttu-id="e2000-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2000-132">Click OK.</span></span>
12. <span data-ttu-id="e2000-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2000-133">Click OK.</span></span>
13. <span data-ttu-id="e2000-134">Kattintson a Tervezett rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="e2000-134">Click Planned orders.</span></span>
14. <span data-ttu-id="e2000-135">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="e2000-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="e2000-136">Például szűkítsen a Cikkszám mezővel a „P6000” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="e2000-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="e2000-137">Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="e2000-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="e2000-138">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="e2000-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e2000-139">Válassza ki a szűrő által visszaadott sorok egyikét.</span><span class="sxs-lookup"><span data-stu-id="e2000-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="e2000-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2000-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="e2000-141">Bontsa ki vagy csukja össze az Igénykövetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e2000-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="e2000-142">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2000-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e2000-143">A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.</span><span class="sxs-lookup"><span data-stu-id="e2000-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="e2000-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e2000-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="e2000-145">Társtermék szükségletének létrehozása</span><span class="sxs-lookup"><span data-stu-id="e2000-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="e2000-146">Ugrás az Alapértelmezett irányítópultra.</span><span class="sxs-lookup"><span data-stu-id="e2000-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="e2000-147">Kattintson az Értékesítési rendelés feldolgozása és lekérdezése menüpontra.</span><span class="sxs-lookup"><span data-stu-id="e2000-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="e2000-148">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="e2000-148">Click New.</span></span>
4. <span data-ttu-id="e2000-149">Kattintson az Értékesítési rendelés gombra.</span><span class="sxs-lookup"><span data-stu-id="e2000-149">Click Sales order.</span></span>
5. <span data-ttu-id="e2000-150">Írjon be egy értéket a Vevői számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e2000-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="e2000-151">Példa: US-001</span><span class="sxs-lookup"><span data-stu-id="e2000-151">Example: US-001</span></span>  
6. <span data-ttu-id="e2000-152">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2000-152">Click OK.</span></span>
7. <span data-ttu-id="e2000-153">A cikkmezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e2000-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="e2000-154">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="e2000-154">Example: P6003</span></span>  
8. <span data-ttu-id="e2000-155">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2000-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="e2000-156">Példa: 50000</span><span class="sxs-lookup"><span data-stu-id="e2000-156">Example: 50000</span></span>  
9. <span data-ttu-id="e2000-157">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="e2000-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="e2000-158">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="e2000-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="e2000-159">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="e2000-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="e2000-160">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2000-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e2000-161">Példa: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="e2000-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="e2000-162">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="e2000-162">Click Run.</span></span>
4. <span data-ttu-id="e2000-163">Bontsa ki vagy csukja össze a Belefoglalandó rekordok részt.</span><span class="sxs-lookup"><span data-stu-id="e2000-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="e2000-164">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="e2000-164">Click Filter.</span></span>
6. <span data-ttu-id="e2000-165">A listából válassza ki a Mező = Cikkszám sort.</span><span class="sxs-lookup"><span data-stu-id="e2000-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="e2000-166">Érték beírása a Feltétel mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e2000-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="e2000-167">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="e2000-167">Example: P6003</span></span>  
8. <span data-ttu-id="e2000-168">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2000-168">Click OK.</span></span>
9. <span data-ttu-id="e2000-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e2000-169">Click OK.</span></span>
10. <span data-ttu-id="e2000-170">Kattintson a Tervezett rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="e2000-170">Click Planned orders.</span></span>
11. <span data-ttu-id="e2000-171">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="e2000-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="e2000-172">Például szűkítsen a Cikkszám mezővel a „P6000” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="e2000-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="e2000-173">Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="e2000-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="e2000-174">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="e2000-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e2000-175">Válassza ki a szűrő által visszaadott sorok egyikét.</span><span class="sxs-lookup"><span data-stu-id="e2000-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="e2000-176">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2000-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="e2000-177">Bontsa ki vagy csukja össze az Igénykövetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e2000-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="e2000-178">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="e2000-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="e2000-179">A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.</span><span class="sxs-lookup"><span data-stu-id="e2000-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="e2000-180">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e2000-180">Close the page.</span></span>
17. <span data-ttu-id="e2000-181">Kattintson az Alaptervezés parancsra.</span><span class="sxs-lookup"><span data-stu-id="e2000-181">Click Master planning.</span></span>
18. <span data-ttu-id="e2000-182">Ugorjon az Alaptervezés > Beállítás > Alaptervezés paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="e2000-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="e2000-183">Válassza a Nem lehetőséget Az összes tervezési folyamat letiltása mezőben.</span><span class="sxs-lookup"><span data-stu-id="e2000-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="e2000-184">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e2000-184">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]