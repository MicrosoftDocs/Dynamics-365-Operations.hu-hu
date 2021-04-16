---
title: Számlastruktúrák létrehozása
description: Ez az útmutató bemutatja a számlastruktúra létrehozásának folyamatát.
author: aprilolson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aece2b79633802d28ba3b4fd8b51788e26c17a67
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815164"
---
# <a name="create-account-structures"></a><span data-ttu-id="248a6-103">Számlastruktúrák létrehozása</span><span class="sxs-lookup"><span data-stu-id="248a6-103">Create account structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="248a6-104">Ez az útmutató bemutatja a számlastruktúra létrehozásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="248a6-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="248a6-105">A lépés a USMF bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="248a6-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="248a6-106">Ugrás a következő útvonalra: **Navigációs ablaktábla > Modulok > Főkönyv > Számlatükör > Struktúrák > Számlastruktúrák konfigurálása**.</span><span class="sxs-lookup"><span data-stu-id="248a6-106">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="248a6-107">Az **Művelet ablaktáblán** kattintson az **Új** elemre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="248a6-107">On the **Action pane**, click **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="248a6-108">A **Számlastruktúra** mezőbe írjon be egy nevet, amely leírja a számlastruktúra célját.</span><span class="sxs-lookup"><span data-stu-id="248a6-108">In the **Account structure** field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="248a6-109">A **Leírás** mezőbe írjon be egy leírást, amely megadja a számlastruktúra célját.</span><span class="sxs-lookup"><span data-stu-id="248a6-109">In the **Description** field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="248a6-110">Kattintson az **Új** > lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="248a6-110">Click **Create**.</span></span>
6. <span data-ttu-id="248a6-111">A **Szegmensek és megengedett értékek** területen kattintson a **Szegmens hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="248a6-111">In the **Segments and allowed values**, click **Add segment**.</span></span>
7. <span data-ttu-id="248a6-112">A dimenziók listájában válassza ki a számlastruktúrához adandó dimenziót.</span><span class="sxs-lookup"><span data-stu-id="248a6-112">In the dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="248a6-113">A lista végén kattintson a **Szegmens hozzáadása** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="248a6-113">At the end of the list, click **Add segment**.</span></span>
9. <span data-ttu-id="248a6-114">Szükség szerint ismételje meg a 6–9. lépést.</span><span class="sxs-lookup"><span data-stu-id="248a6-114">Repeat step 6 to 9 as needed.</span></span>
10. <span data-ttu-id="248a6-115">Az **Megengedett értékek részletei** szakaszban jelölje ki a szegmenst a megengedett értékek módosításához.</span><span class="sxs-lookup"><span data-stu-id="248a6-115">In the **Allowed value details** section, select the segment to edit the allowed values.</span></span>
    <span data-ttu-id="248a6-116">Kattintson például a **Fő számla** mezőre.</span><span class="sxs-lookup"><span data-stu-id="248a6-116">For example, click the **Main Account** field.</span></span>  
11. <span data-ttu-id="248a6-117">A **Kezelő** mezőben válasszon ki egy lehetőséget, például a „között”, vagy a „tartalmazza” elemet.</span><span class="sxs-lookup"><span data-stu-id="248a6-117">In the **Operator** field, select an option, such as is between and includes.</span></span>
12. <span data-ttu-id="248a6-118">Érték beírása az **Érték** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="248a6-118">In the **Value** field, type a value.</span></span> <span data-ttu-id="248a6-119">Például 600 000.</span><span class="sxs-lookup"><span data-stu-id="248a6-119">For example, 600000.</span></span>  
13. <span data-ttu-id="248a6-120">Írjon be egy értéket a **–** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="248a6-120">In the **through** field, type a value.</span></span> <span data-ttu-id="248a6-121">Például 699 999.</span><span class="sxs-lookup"><span data-stu-id="248a6-121">For example, 699999.</span></span>  
14. <span data-ttu-id="248a6-122">Az **Engedélyezett érték részletei** szakaszban kattintson az **Alkalmaz** gombra.</span><span class="sxs-lookup"><span data-stu-id="248a6-122">In the **Allowed value details** section, click **Apply**.</span></span>
15. <span data-ttu-id="248a6-123">Szükség szerint ismételje meg a 10–15. lépést.</span><span class="sxs-lookup"><span data-stu-id="248a6-123">Repeat step 10 to 15 as needed.</span></span>  
16. <span data-ttu-id="248a6-124">Az **Engedélyezett érték részletei** szakaszban kattintson az **Új feltétel hozzáadása** gombra.</span><span class="sxs-lookup"><span data-stu-id="248a6-124">In the **Allowed value details** section, click **Add new criteria**.</span></span>
17. <span data-ttu-id="248a6-125">A Kezelő mezőben válasszon ki egy lehetőséget, például a „között”, vagy a „tartalmazza” elemet.</span><span class="sxs-lookup"><span data-stu-id="248a6-125">In the Operator field, select an option, such as is between and includes.</span></span>
18. <span data-ttu-id="248a6-126">Érték beírása az **Érték** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="248a6-126">In the **Value** field, type a value.</span></span> <span data-ttu-id="248a6-127">Például: 033.</span><span class="sxs-lookup"><span data-stu-id="248a6-127">For example, 033.</span></span>  
19. <span data-ttu-id="248a6-128">Írjon be egy értéket a **–** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="248a6-128">In the **through** field, type a value.</span></span> <span data-ttu-id="248a6-129">Például: 034.</span><span class="sxs-lookup"><span data-stu-id="248a6-129">For example, 034.</span></span>  
20. <span data-ttu-id="248a6-130">Kattintson az **Alkalmaz** gombra.</span><span class="sxs-lookup"><span data-stu-id="248a6-130">Click **Apply**.</span></span>
21. <span data-ttu-id="248a6-131">A rácson jelölje ki a szegmenst a megengedett értékek módosításához.</span><span class="sxs-lookup"><span data-stu-id="248a6-131">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="248a6-132">Például: költséghely.</span><span class="sxs-lookup"><span data-stu-id="248a6-132">For example, Cost Center.</span></span>  
22. <span data-ttu-id="248a6-133">Írjon be egy értéket a **Költséghely** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="248a6-133">In the **CostCenter field**, type a value.</span></span> <span data-ttu-id="248a6-134">Például 007..021.</span><span class="sxs-lookup"><span data-stu-id="248a6-134">For example, 007..021.</span></span>  
23. <span data-ttu-id="248a6-135">A **Szegmensek és megengedett értékek** területen kattintson a **Hozzáadás** elemre.</span><span class="sxs-lookup"><span data-stu-id="248a6-135">In the **Segments and allowed values**, click **Add**.</span></span>
24. <span data-ttu-id="248a6-136">Írjon be egy értéket a **Fő számla** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="248a6-136">In the **MainAccount** field, type a value.</span></span> <span data-ttu-id="248a6-137">Például: 600000..699999</span><span class="sxs-lookup"><span data-stu-id="248a6-137">For example, 600000..699999</span></span>  
25. <span data-ttu-id="248a6-138">A rácson jelölje ki a szegmenst a megengedett értékek módosításához.</span><span class="sxs-lookup"><span data-stu-id="248a6-138">In the grid, select the segment to edit the allowed values.</span></span> <span data-ttu-id="248a6-139">Például: részleg.</span><span class="sxs-lookup"><span data-stu-id="248a6-139">For example, Department.</span></span>  
26. <span data-ttu-id="248a6-140">Írjon be egy értéket a Részleg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="248a6-140">In the Department field, type a value.</span></span> <span data-ttu-id="248a6-141">Például: 032.</span><span class="sxs-lookup"><span data-stu-id="248a6-141">For example, 032.</span></span>  
27. <span data-ttu-id="248a6-142">Írjon be egy értéket a Költséghely mezőbe.</span><span class="sxs-lookup"><span data-stu-id="248a6-142">In the CostCenter field, type a value.</span></span> <span data-ttu-id="248a6-143">Például: 086.</span><span class="sxs-lookup"><span data-stu-id="248a6-143">For example, 086.</span></span>  
28. <span data-ttu-id="248a6-144">A **Művelet panelen** kattintson az **Érvényesítés** elemre.</span><span class="sxs-lookup"><span data-stu-id="248a6-144">On the **Action pane**, click **Validate**.</span></span>
29. <span data-ttu-id="248a6-145">A **Művelet panelen** kattintson az **Aktiválás** elemre.</span><span class="sxs-lookup"><span data-stu-id="248a6-145">On the **Action pane**, click **Activate**.</span></span>
30. <span data-ttu-id="248a6-146">Kattintson az **Aktiválás** gombra.</span><span class="sxs-lookup"><span data-stu-id="248a6-146">Click **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]