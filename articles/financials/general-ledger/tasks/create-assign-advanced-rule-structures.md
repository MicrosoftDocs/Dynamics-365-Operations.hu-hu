--- 
title: "Speciális szabálystruktúrák létrehozása és hozzárendelése"
description: "A feladat-útmutató bemutatja a speciális szabálystruktúra létrehozását és hozzárendelését egy számlastruktúrához."
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: dd62254c20cf5d77677d03c7d7335fb793d7f5f2
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="b9242-103">Speciális szabálystruktúrák létrehozása és hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="b9242-103">Create and assign advanced rule structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b9242-104">A feladat-útmutató bemutatja a speciális szabálystruktúra létrehozását és hozzárendelését egy számlastruktúrához.</span><span class="sxs-lookup"><span data-stu-id="b9242-104">This task guide steps through creating and assigning an advanced rule structure to an account structure.</span></span> <span data-ttu-id="b9242-105">Az útmutató az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b9242-105">This guide uses the USMF demo company.</span></span>


## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="b9242-106">Speciális szabálystruktúra létrehozása</span><span class="sxs-lookup"><span data-stu-id="b9242-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="b9242-107">Ugorjon a Főkönyv > Számlatükör > Struktúrák > Speciális számlastruktúrák pontra.</span><span class="sxs-lookup"><span data-stu-id="b9242-107">Go to General ledger > Chart of accounts > Structures > Advanced rule structures.</span></span>
2. <span data-ttu-id="b9242-108">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b9242-108">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="b9242-109">A Speciális szabálystruktúra mezőbe írjon be egy nevet a szabálystruktúra leírásához.</span><span class="sxs-lookup"><span data-stu-id="b9242-109">In the Advanced rule structure field, type a name to descritbe the rule structure.</span></span>
4. <span data-ttu-id="b9242-110">A Leírás mezőben adja meg a struktúra leírásához az értéket.</span><span class="sxs-lookup"><span data-stu-id="b9242-110">In the Description field, type a value to describe the structure.</span></span>
5. <span data-ttu-id="b9242-111">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b9242-111">Click OK.</span></span>
6. <span data-ttu-id="b9242-112">Kattintson a Szegmens hozzáadása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b9242-112">Click Add segment.</span></span>
7. <span data-ttu-id="b9242-113">A szegmensek listájáról válassza ki a pénzügyi dimenziót.</span><span class="sxs-lookup"><span data-stu-id="b9242-113">In the list of segments, select a financial dimension.</span></span>
    * <span data-ttu-id="b9242-114">Például: raktár.</span><span class="sxs-lookup"><span data-stu-id="b9242-114">For example, Store.</span></span>  
8. <span data-ttu-id="b9242-115">Kattintson a Szegmens hozzáadása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b9242-115">Click Add segment.</span></span>
9. <span data-ttu-id="b9242-116">A listában kattintson a speciális szabálystruktúra hivatkozására ahhoz, hogy megtekintse.</span><span class="sxs-lookup"><span data-stu-id="b9242-116">In the list, click the link of the advanced rule structure to view it.</span></span>
10. <span data-ttu-id="b9242-117">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="b9242-117">Click Activate.</span></span>
11. <span data-ttu-id="b9242-118">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="b9242-118">Click Activate.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="b9242-119">Speciális szabály alkalmazása egy számlastruktúrához</span><span class="sxs-lookup"><span data-stu-id="b9242-119">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="b9242-120">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="b9242-120">Close the form.</span></span>
2. <span data-ttu-id="b9242-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b9242-121">Close the page.</span></span>
3. <span data-ttu-id="b9242-122">Ugorjon a Főkönyv > Számlatükör > Struktúrák > Számlastruktúrák konfigurálása pontra.</span><span class="sxs-lookup"><span data-stu-id="b9242-122">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
4. <span data-ttu-id="b9242-123">A listában keresse meg és válassza ki azt a számlastruktúrát, amelyhez a speciális szabályt alkalmazni szeretné.</span><span class="sxs-lookup"><span data-stu-id="b9242-123">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
5. <span data-ttu-id="b9242-124">Kattintson a megnyitni kívánt számlastruktúra nevére.</span><span class="sxs-lookup"><span data-stu-id="b9242-124">Click the name of the account structure to open it.</span></span>
6. <span data-ttu-id="b9242-125">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b9242-125">Click Edit.</span></span>
    * <span data-ttu-id="b9242-126">Ha a speciális szabályokra kattint, a rendszer kérni fogja a számlastruktúra vázlat módba történő helyezését.</span><span class="sxs-lookup"><span data-stu-id="b9242-126">You can also click Advanced rules and you will be prompted to put the account structure in Draft mode.</span></span>  
7. <span data-ttu-id="b9242-127">Kattintson a Speciális szabályok elemre.</span><span class="sxs-lookup"><span data-stu-id="b9242-127">Click Advanced rules.</span></span>
8. <span data-ttu-id="b9242-128">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b9242-128">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="b9242-129">Írjon be egy értéket a Speciális szabály mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b9242-129">In the Advanced rule field, type a value.</span></span>
10. <span data-ttu-id="b9242-130">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b9242-130">In the Name field, type a value.</span></span>
11. <span data-ttu-id="b9242-131">Kattintson az Új > lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b9242-131">Click Create.</span></span>
12. <span data-ttu-id="b9242-132">Kattintson az Új feltételek hozzáadása elemre.</span><span class="sxs-lookup"><span data-stu-id="b9242-132">Click Add new criteria.</span></span>
13. <span data-ttu-id="b9242-133">A Honnan mezőben válassza ki a fő számlát vagy a pénzügyi dimenziót.</span><span class="sxs-lookup"><span data-stu-id="b9242-133">In the Where field, select main account or a financial dimension.</span></span>
14. <span data-ttu-id="b9242-134">A Kezelő mezőben válasszon ki egy lehetőséget, például a „között”, vagy a „tartalmazza” elemet.</span><span class="sxs-lookup"><span data-stu-id="b9242-134">In the Operator field, select an option, such as is between and includes.</span></span>
15. <span data-ttu-id="b9242-135">Érték beírása az Érték mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b9242-135">In the Value field, type a value.</span></span>
16. <span data-ttu-id="b9242-136">Írjon be egy értéket a – mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b9242-136">In the through field, type a value.</span></span>
17. <span data-ttu-id="b9242-137">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b9242-137">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="b9242-138">A listában keresse meg azt a speciális szabálystruktúrát, amelyet akkor szeretne használni, amikor a megadott feltételek teljesülnek.</span><span class="sxs-lookup"><span data-stu-id="b9242-138">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
19. <span data-ttu-id="b9242-139">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="b9242-139">Click Add.</span></span>
20. <span data-ttu-id="b9242-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b9242-140">Close the page.</span></span>
21. <span data-ttu-id="b9242-141">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="b9242-141">Click Activate.</span></span>
22. <span data-ttu-id="b9242-142">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="b9242-142">Click Activate.</span></span>


