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
ms.openlocfilehash: b51e4b4d00da2babb5128d8c4c22139b0c1853d4
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920729"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="4561e-103">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="4561e-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4561e-104">A termelési tervező megtervezi az anyagszükségleteket olyan cikkekhez, amelyek receptúra-társtermékek.</span><span class="sxs-lookup"><span data-stu-id="4561e-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="4561e-105">Ez az eljárás az USP2 bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="4561e-105">The demo data company used to create this procedure is USP2.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="4561e-106">Társtermék szükségletének létrehozása</span><span class="sxs-lookup"><span data-stu-id="4561e-106">Create requirement for a co-product</span></span>

1. <span data-ttu-id="4561e-107">Ugrás az **Értékesítés és marketing \> Munkaterületek \> Értékesítési rendelés feldolgozása és lekérdezése** elemre.</span><span class="sxs-lookup"><span data-stu-id="4561e-107">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="4561e-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-108">Select **New**.</span></span>
1. <span data-ttu-id="4561e-109">Válassza ki az **Értékesítési rendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-109">Select **Sales order**.</span></span>
1. <span data-ttu-id="4561e-110">Írjon be egy értéket a **Vevői számla** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4561e-110">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="4561e-111">Példa: US-001</span><span class="sxs-lookup"><span data-stu-id="4561e-111">Example: US-001</span></span>  
1. <span data-ttu-id="4561e-112">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-112">Select **OK**.</span></span>
1. <span data-ttu-id="4561e-113">A **Cikkszám** mezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4561e-113">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="4561e-114">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="4561e-114">Example: P6003</span></span>  
1. <span data-ttu-id="4561e-115">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4561e-115">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="4561e-116">Példa: 50000</span><span class="sxs-lookup"><span data-stu-id="4561e-116">Example: 50000</span></span>  
1. <span data-ttu-id="4561e-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-117">Select **Save**.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="4561e-118">Társtermékek anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="4561e-118">Create a material plan for co-products</span></span>

1. <span data-ttu-id="4561e-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4561e-119">Close the page.</span></span>
1. <span data-ttu-id="4561e-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4561e-120">Close the page.</span></span>
1. <span data-ttu-id="4561e-121">Válassza a **Alaptervezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-121">Select **Master planning**.</span></span>
1. <span data-ttu-id="4561e-122">A **Konstrukció** mezőben válassza a legördítő nyilat a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4561e-122">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
1. <span data-ttu-id="4561e-123">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="4561e-123">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="4561e-124">Példa: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="4561e-124">Example: MasterPlan</span></span>  
1. <span data-ttu-id="4561e-125">Válassza a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="4561e-125">Select **Run**.</span></span>
1. <span data-ttu-id="4561e-126">Bontsa ki vagy csukja össze a **Belefoglalandó rekordok** részt.</span><span class="sxs-lookup"><span data-stu-id="4561e-126">Expand or collapse the **Records to include** section.</span></span>
1. <span data-ttu-id="4561e-127">Válassza ki a **Szűrő** elemet.</span><span class="sxs-lookup"><span data-stu-id="4561e-127">Select **Filter**.</span></span>
1. <span data-ttu-id="4561e-128">A listából válassza ki a **Mező** = *Cikkszám* sort.</span><span class="sxs-lookup"><span data-stu-id="4561e-128">In the list, select the row for **Field** = *Item number*.</span></span>
1. <span data-ttu-id="4561e-129">Adjon meg egy értéket a **Feltétel** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4561e-129">In the **Criteria** field, type a value.</span></span>
    * <span data-ttu-id="4561e-130">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="4561e-130">Example: P6003</span></span>  
1. <span data-ttu-id="4561e-131">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-131">Select **OK**.</span></span>
1. <span data-ttu-id="4561e-132">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-132">Select **OK**.</span></span>
1. <span data-ttu-id="4561e-133">**Tervezett rendelések** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="4561e-133">Select **Planned orders**.</span></span>
1. <span data-ttu-id="4561e-134">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="4561e-134">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4561e-135">Például szűkítsen a **Cikkszám** mezővel a „P6000” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="4561e-135">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="4561e-136">Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="4561e-136">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
1. <span data-ttu-id="4561e-137">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="4561e-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="4561e-138">Válassza ki a szűrő által visszaadott sorok egyikét.</span><span class="sxs-lookup"><span data-stu-id="4561e-138">Select any of the rows returned by the filter.</span></span>  
1. <span data-ttu-id="4561e-139">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="4561e-139">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="4561e-140">Bontsa ki a **Igénykövetés** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4561e-140">Expand the **Pegging** section.</span></span>
1. <span data-ttu-id="4561e-141">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="4561e-141">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="4561e-142">A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.</span><span class="sxs-lookup"><span data-stu-id="4561e-142">The planned order is pegged to the sales order for the co-product.</span></span>  
1. <span data-ttu-id="4561e-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4561e-143">Close the page.</span></span>

## <a name="create-a-second-requirement-for-a-co-product"></a><span data-ttu-id="4561e-144">Társtermék második követelményének létrehozása</span><span class="sxs-lookup"><span data-stu-id="4561e-144">Create a second requirement for a co-product</span></span>

1. <span data-ttu-id="4561e-145">Ugrás az **Értékesítés és marketing \> Munkaterületek \> Értékesítési rendelés feldolgozása és lekérdezése** elemre.</span><span class="sxs-lookup"><span data-stu-id="4561e-145">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="4561e-146">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-146">Select **New**.</span></span>
1. <span data-ttu-id="4561e-147">Válassza ki az **Értékesítési rendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-147">Select **Sales order**.</span></span>
1. <span data-ttu-id="4561e-148">Írjon be egy értéket a **Vevői számla** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4561e-148">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="4561e-149">Példa: US-001</span><span class="sxs-lookup"><span data-stu-id="4561e-149">Example: US-001</span></span>  
1. <span data-ttu-id="4561e-150">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-150">Select **OK**.</span></span>
1. <span data-ttu-id="4561e-151">A **Cikkszám** mezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4561e-151">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="4561e-152">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="4561e-152">Example: P6003</span></span>  
1. <span data-ttu-id="4561e-153">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4561e-153">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="4561e-154">Példa: 50000</span><span class="sxs-lookup"><span data-stu-id="4561e-154">Example: 50000</span></span>  
1. <span data-ttu-id="4561e-155">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-155">Select **Save**.</span></span>

## <a name="create-a-second-material-plan-for-co-products"></a><span data-ttu-id="4561e-156">Társtermékek második anyagfelhasználási tervének létrehozása</span><span class="sxs-lookup"><span data-stu-id="4561e-156">Create a second material plan for co-products</span></span>

1. <span data-ttu-id="4561e-157">A **Konstrukció** mezőben válassza a legördítő nyilat a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4561e-157">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="4561e-158">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="4561e-158">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="4561e-159">Példa: MasterPlan</span><span class="sxs-lookup"><span data-stu-id="4561e-159">Example: MasterPlan</span></span>  
3. <span data-ttu-id="4561e-160">Válassza a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="4561e-160">Select **Run**.</span></span>
4. <span data-ttu-id="4561e-161">Bontsa ki vagy csukja össze a **Belefoglalandó rekordok** részt.</span><span class="sxs-lookup"><span data-stu-id="4561e-161">Expand or collapse the **Records to include** section.</span></span>
5. <span data-ttu-id="4561e-162">Válassza ki a **Szűrő** elemet.</span><span class="sxs-lookup"><span data-stu-id="4561e-162">Select **Filter**.</span></span>
6. <span data-ttu-id="4561e-163">A listából válassza ki a **Mező** = *Cikkszám* sort.</span><span class="sxs-lookup"><span data-stu-id="4561e-163">In the list, select the row for **Field** = *Item number*.</span></span>
7. <span data-ttu-id="4561e-164">Adjon meg egy értéket a *Feltétel* mezőben.</span><span class="sxs-lookup"><span data-stu-id="4561e-164">In the *Criteria* field, type a value.</span></span>
    * <span data-ttu-id="4561e-165">Példa: P6003</span><span class="sxs-lookup"><span data-stu-id="4561e-165">Example: P6003</span></span>  
8. <span data-ttu-id="4561e-166">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-166">Select **OK**.</span></span>
9. <span data-ttu-id="4561e-167">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-167">Select **OK**.</span></span>
10. <span data-ttu-id="4561e-168">**Tervezett rendelések** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="4561e-168">Select **Planned orders**.</span></span>
11. <span data-ttu-id="4561e-169">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="4561e-169">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4561e-170">Például szűkítsen a **Cikkszám** mezővel a „P6000” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="4561e-170">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="4561e-171">Szűrés a receptúraelemmel, amely tartalmazza a cikk egy társtermékét, amelyre létrehozott egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="4561e-171">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="4561e-172">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="4561e-172">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="4561e-173">Válassza ki a szűrő által visszaadott sorok egyikét.</span><span class="sxs-lookup"><span data-stu-id="4561e-173">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="4561e-174">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="4561e-174">In the list, select the link in the selected row.</span></span>
14. <span data-ttu-id="4561e-175">Bontsa ki vagy csukja össze az **Igénykövetés** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4561e-175">Expand or collapse the **Pegging** section.</span></span>
15. <span data-ttu-id="4561e-176">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="4561e-176">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="4561e-177">A tervezett rendelés a társtermék értékesítési rendeléséhez van rögzítve.</span><span class="sxs-lookup"><span data-stu-id="4561e-177">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="4561e-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4561e-178">Close the page.</span></span>
17. <span data-ttu-id="4561e-179">Válassza a **Alaptervezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4561e-179">Select **Master planning**.</span></span>
18. <span data-ttu-id="4561e-180">Ugorjon az **Alaptervezés \> Beállítás \> Alaptervezés paraméterei** pontra.</span><span class="sxs-lookup"><span data-stu-id="4561e-180">Go to **Master planning \> Setup \> Master planning parameters**.</span></span>
19. <span data-ttu-id="4561e-181">Válassza a *Nem* lehetőséget **Az összes tervezési folyamat letiltása** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4561e-181">Select *No* in the **Disable all planning processes** field.</span></span>
20. <span data-ttu-id="4561e-182">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4561e-182">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]