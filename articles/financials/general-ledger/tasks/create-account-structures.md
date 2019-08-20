---
title: Számlastruktúrák létrehozása
description: Ez az útmutató bemutatja a számlastruktúra létrehozásának folyamatát.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2183f88356fc8094781af147bf079c4e53ffb2b4
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846703"
---
# <a name="create-account-structures"></a><span data-ttu-id="a49a1-103">Számlastruktúrák létrehozása</span><span class="sxs-lookup"><span data-stu-id="a49a1-103">Create account structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a49a1-104">Ez az útmutató bemutatja a számlastruktúra létrehozásának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="a49a1-104">This task guide steps through creating an account structure.</span></span> <span data-ttu-id="a49a1-105">A lépés a USMF bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="a49a1-105">The steps use demo data company USMF.</span></span>

1. <span data-ttu-id="a49a1-106">Ugorjon a Főkönyv > Számlatükör > Struktúrák > Számlastruktúrák konfigurálása pontra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-106">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
2. <span data-ttu-id="a49a1-107">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="a49a1-107">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="a49a1-108">A Számlastruktúra mezőbe írjon be egy nevet, amely leírja a számlastruktúra célját.</span><span class="sxs-lookup"><span data-stu-id="a49a1-108">In the Account structure field, type a name to describe the purpose of the account structure.</span></span>
4. <span data-ttu-id="a49a1-109">A Leírás mezőbe írjon be egy leírást, amely megadja a számlastruktúra célját.</span><span class="sxs-lookup"><span data-stu-id="a49a1-109">In the Description field, type a description to specify the purpose of the account structure.</span></span>
5. <span data-ttu-id="a49a1-110">Kattintson az Új > lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a49a1-110">Click Create.</span></span>
6. <span data-ttu-id="a49a1-111">Kattintson a Szegmens hozzáadása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-111">Click Add segment.</span></span>
7. <span data-ttu-id="a49a1-112">A Dimenziók listájában válassza ki a számlastruktúrához adandó dimenziót.</span><span class="sxs-lookup"><span data-stu-id="a49a1-112">In the Dimensions list, select the dimension to add to the account structure.</span></span>
8. <span data-ttu-id="a49a1-113">Kattintson a Szegmens hozzáadása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-113">Click Add segment.</span></span>
9. <span data-ttu-id="a49a1-114">Kattintson a Szegmens hozzáadása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-114">Click Add segment.</span></span>
10. <span data-ttu-id="a49a1-115">A Dimenziók listájában válassza ki a számlastruktúrához adandó dimenziót.</span><span class="sxs-lookup"><span data-stu-id="a49a1-115">In the Dimensions list, select the dimension to add to the account structure.</span></span>
11. <span data-ttu-id="a49a1-116">Kattintson a Szegmens hozzáadása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-116">Click Add segment.</span></span>
12. <span data-ttu-id="a49a1-117">Kattintson a Szegmens hozzáadása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-117">Click Add segment.</span></span>
13. <span data-ttu-id="a49a1-118">A Dimenziók listájában válassza ki a számlastruktúrához adandó dimenziót.</span><span class="sxs-lookup"><span data-stu-id="a49a1-118">In the Dimensions list, select the dimension to add to the account structure.</span></span>
14. <span data-ttu-id="a49a1-119">Kattintson a Szegmens hozzáadása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-119">Click Add segment.</span></span>
15. <span data-ttu-id="a49a1-120">A rácson jelölje ki a szegmenst a megengedett értékek módosításához.</span><span class="sxs-lookup"><span data-stu-id="a49a1-120">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="a49a1-121">Kattintson például a Fő számlába.</span><span class="sxs-lookup"><span data-stu-id="a49a1-121">For example, click in Main Account.</span></span>  
16. <span data-ttu-id="a49a1-122">A Kezelő mezőben válasszon ki egy lehetőséget, például a „között”, vagy a „tartalmazza” elemet.</span><span class="sxs-lookup"><span data-stu-id="a49a1-122">In the Operator field, select an option, such as is between and includes.</span></span>
17. <span data-ttu-id="a49a1-123">Érték beírása az Érték mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a49a1-123">In the Value field, type a value.</span></span>
    * <span data-ttu-id="a49a1-124">Például 600 000.</span><span class="sxs-lookup"><span data-stu-id="a49a1-124">For example, 600000.</span></span>  
18. <span data-ttu-id="a49a1-125">Írjon be egy értéket a – mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a49a1-125">In the through field, type a value.</span></span>
    * <span data-ttu-id="a49a1-126">Például 699 999.</span><span class="sxs-lookup"><span data-stu-id="a49a1-126">For example, 699999.</span></span>  
19. <span data-ttu-id="a49a1-127">Kattintson az Alkalmaz gombra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-127">Click Apply.</span></span>
20. <span data-ttu-id="a49a1-128">A rácson jelölje ki a szegmenst a megengedett értékek módosításához.</span><span class="sxs-lookup"><span data-stu-id="a49a1-128">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="a49a1-129">Például: részleg.</span><span class="sxs-lookup"><span data-stu-id="a49a1-129">For example, Department.</span></span>  
21. <span data-ttu-id="a49a1-130">A Kezelő mezőben válasszon ki egy lehetőséget, például a „között”, vagy a „tartalmazza” elemet.</span><span class="sxs-lookup"><span data-stu-id="a49a1-130">In the Operator field, select an option, such as is between and includes.</span></span>
22. <span data-ttu-id="a49a1-131">Érték beírása az Érték mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a49a1-131">In the Value field, type a value.</span></span>
    * <span data-ttu-id="a49a1-132">Például: 022.</span><span class="sxs-lookup"><span data-stu-id="a49a1-132">For example, 022.</span></span>  
23. <span data-ttu-id="a49a1-133">Írjon be egy értéket a – mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a49a1-133">In the through field, type a value.</span></span>
    * <span data-ttu-id="a49a1-134">Például: 031.</span><span class="sxs-lookup"><span data-stu-id="a49a1-134">For example, 031.</span></span>  
24. <span data-ttu-id="a49a1-135">Kattintson az Új feltételek hozzáadása elemre.</span><span class="sxs-lookup"><span data-stu-id="a49a1-135">Click Add new criteria.</span></span>
25. <span data-ttu-id="a49a1-136">A Kezelő mezőben válasszon ki egy lehetőséget, például a „között”, vagy a „tartalmazza” elemet.</span><span class="sxs-lookup"><span data-stu-id="a49a1-136">In the Operator field, select an option, such as is between and includes.</span></span>
26. <span data-ttu-id="a49a1-137">Érték beírása az Érték mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a49a1-137">In the Value field, type a value.</span></span>
    * <span data-ttu-id="a49a1-138">Például: 033.</span><span class="sxs-lookup"><span data-stu-id="a49a1-138">For example, 033.</span></span>  
27. <span data-ttu-id="a49a1-139">Írjon be egy értéket a – mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a49a1-139">In the through field, type a value.</span></span>
    * <span data-ttu-id="a49a1-140">Például: 034.</span><span class="sxs-lookup"><span data-stu-id="a49a1-140">For example, 034.</span></span>  
28. <span data-ttu-id="a49a1-141">Kattintson az Alkalmaz gombra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-141">Click Apply.</span></span>
29. <span data-ttu-id="a49a1-142">A rácson jelölje ki a szegmenst a megengedett értékek módosításához.</span><span class="sxs-lookup"><span data-stu-id="a49a1-142">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="a49a1-143">Például: költséghely.</span><span class="sxs-lookup"><span data-stu-id="a49a1-143">For example, Cost Center.</span></span>  
30. <span data-ttu-id="a49a1-144">Írjon be egy értéket a Költséghely mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a49a1-144">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="a49a1-145">Például 007..021.</span><span class="sxs-lookup"><span data-stu-id="a49a1-145">For example, 007..021.</span></span>  
31. <span data-ttu-id="a49a1-146">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-146">Click Add.</span></span>
32. <span data-ttu-id="a49a1-147">Írjon be egy értéket a Fő számla mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a49a1-147">In the MainAccount field, type a value.</span></span>
    * <span data-ttu-id="a49a1-148">Például: 600000..699999</span><span class="sxs-lookup"><span data-stu-id="a49a1-148">For example, 600000..699999</span></span>  
33. <span data-ttu-id="a49a1-149">A rácson jelölje ki a szegmenst a megengedett értékek módosításához.</span><span class="sxs-lookup"><span data-stu-id="a49a1-149">In the grid, select the segment to edit the allowed values.</span></span>
    * <span data-ttu-id="a49a1-150">Például: részleg.</span><span class="sxs-lookup"><span data-stu-id="a49a1-150">For example, Department.</span></span>  
34. <span data-ttu-id="a49a1-151">Írjon be egy értéket a Részleg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a49a1-151">In the Department field, type a value.</span></span>
    * <span data-ttu-id="a49a1-152">Például: 032.</span><span class="sxs-lookup"><span data-stu-id="a49a1-152">For example, 032.</span></span>  
35. <span data-ttu-id="a49a1-153">Írjon be egy értéket a Költséghely mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a49a1-153">In the CostCenter field, type a value.</span></span>
    * <span data-ttu-id="a49a1-154">Például: 086.</span><span class="sxs-lookup"><span data-stu-id="a49a1-154">For example, 086.</span></span>  
36. <span data-ttu-id="a49a1-155">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-155">Click Validate.</span></span>
37. <span data-ttu-id="a49a1-156">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-156">Click Activate.</span></span>
38. <span data-ttu-id="a49a1-157">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="a49a1-157">Click Activate.</span></span>

