---
title: Speciális szabálystruktúrák létrehozása és hozzárendelése
description: A feladat-útmutató bemutatja a speciális szabálystruktúra létrehozását és hozzárendelését egy számlastruktúrához.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd62254c20cf5d77677d03c7d7335fb793d7f5f2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558906"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="3e60b-103">Speciális szabálystruktúrák létrehozása és hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="3e60b-103">Create and assign advanced rule structures</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3e60b-104">A feladat-útmutató bemutatja a speciális szabálystruktúra létrehozását és hozzárendelését egy számlastruktúrához.</span><span class="sxs-lookup"><span data-stu-id="3e60b-104">This task guide steps through creating and assigning an advanced rule structure to an account structure.</span></span> <span data-ttu-id="3e60b-105">Az útmutató az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="3e60b-105">This guide uses the USMF demo company.</span></span>


## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="3e60b-106">Speciális szabálystruktúra létrehozása</span><span class="sxs-lookup"><span data-stu-id="3e60b-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="3e60b-107">Ugorjon a Főkönyv > Számlatükör > Struktúrák > Speciális számlastruktúrák pontra.</span><span class="sxs-lookup"><span data-stu-id="3e60b-107">Go to General ledger > Chart of accounts > Structures > Advanced rule structures.</span></span>
2. <span data-ttu-id="3e60b-108">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="3e60b-108">Click New to open the drop dialog.</span></span>
3. <span data-ttu-id="3e60b-109">A Speciális szabálystruktúra mezőbe írjon be egy nevet a szabálystruktúra leírásához.</span><span class="sxs-lookup"><span data-stu-id="3e60b-109">In the Advanced rule structure field, type a name to descritbe the rule structure.</span></span>
4. <span data-ttu-id="3e60b-110">A Leírás mezőben adja meg a struktúra leírásához az értéket.</span><span class="sxs-lookup"><span data-stu-id="3e60b-110">In the Description field, type a value to describe the structure.</span></span>
5. <span data-ttu-id="3e60b-111">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3e60b-111">Click OK.</span></span>
6. <span data-ttu-id="3e60b-112">Kattintson a Szegmens hozzáadása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3e60b-112">Click Add segment.</span></span>
7. <span data-ttu-id="3e60b-113">A szegmensek listájáról válassza ki a pénzügyi dimenziót.</span><span class="sxs-lookup"><span data-stu-id="3e60b-113">In the list of segments, select a financial dimension.</span></span>
    * <span data-ttu-id="3e60b-114">Például: raktár.</span><span class="sxs-lookup"><span data-stu-id="3e60b-114">For example, Store.</span></span>  
8. <span data-ttu-id="3e60b-115">Kattintson a Szegmens hozzáadása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3e60b-115">Click Add segment.</span></span>
9. <span data-ttu-id="3e60b-116">A listában kattintson a speciális szabálystruktúra hivatkozására ahhoz, hogy megtekintse.</span><span class="sxs-lookup"><span data-stu-id="3e60b-116">In the list, click the link of the advanced rule structure to view it.</span></span>
10. <span data-ttu-id="3e60b-117">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="3e60b-117">Click Activate.</span></span>
11. <span data-ttu-id="3e60b-118">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="3e60b-118">Click Activate.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="3e60b-119">Speciális szabály alkalmazása egy számlastruktúrához</span><span class="sxs-lookup"><span data-stu-id="3e60b-119">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="3e60b-120">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="3e60b-120">Close the form.</span></span>
2. <span data-ttu-id="3e60b-121">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3e60b-121">Close the page.</span></span>
3. <span data-ttu-id="3e60b-122">Ugorjon a Főkönyv > Számlatükör > Struktúrák > Számlastruktúrák konfigurálása pontra.</span><span class="sxs-lookup"><span data-stu-id="3e60b-122">Go to General ledger > Chart of accounts > Structures > Configure account structures.</span></span>
4. <span data-ttu-id="3e60b-123">A listában keresse meg és válassza ki azt a számlastruktúrát, amelyhez a speciális szabályt alkalmazni szeretné.</span><span class="sxs-lookup"><span data-stu-id="3e60b-123">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
5. <span data-ttu-id="3e60b-124">Kattintson a megnyitni kívánt számlastruktúra nevére.</span><span class="sxs-lookup"><span data-stu-id="3e60b-124">Click the name of the account structure to open it.</span></span>
6. <span data-ttu-id="3e60b-125">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3e60b-125">Click Edit.</span></span>
    * <span data-ttu-id="3e60b-126">Ha a speciális szabályokra kattint, a rendszer kérni fogja a számlastruktúra vázlat módba történő helyezését.</span><span class="sxs-lookup"><span data-stu-id="3e60b-126">You can also click Advanced rules and you will be prompted to put the account structure in Draft mode.</span></span>  
7. <span data-ttu-id="3e60b-127">Kattintson a Speciális szabályok elemre.</span><span class="sxs-lookup"><span data-stu-id="3e60b-127">Click Advanced rules.</span></span>
8. <span data-ttu-id="3e60b-128">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="3e60b-128">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="3e60b-129">Írjon be egy értéket a Speciális szabály mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3e60b-129">In the Advanced rule field, type a value.</span></span>
10. <span data-ttu-id="3e60b-130">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3e60b-130">In the Name field, type a value.</span></span>
11. <span data-ttu-id="3e60b-131">Kattintson az Új > lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3e60b-131">Click Create.</span></span>
12. <span data-ttu-id="3e60b-132">Kattintson az Új feltételek hozzáadása elemre.</span><span class="sxs-lookup"><span data-stu-id="3e60b-132">Click Add new criteria.</span></span>
13. <span data-ttu-id="3e60b-133">A Honnan mezőben válassza ki a fő számlát vagy a pénzügyi dimenziót.</span><span class="sxs-lookup"><span data-stu-id="3e60b-133">In the Where field, select main account or a financial dimension.</span></span>
14. <span data-ttu-id="3e60b-134">A Kezelő mezőben válasszon ki egy lehetőséget, például a „között”, vagy a „tartalmazza” elemet.</span><span class="sxs-lookup"><span data-stu-id="3e60b-134">In the Operator field, select an option, such as is between and includes.</span></span>
15. <span data-ttu-id="3e60b-135">Érték beírása az Érték mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3e60b-135">In the Value field, type a value.</span></span>
16. <span data-ttu-id="3e60b-136">Írjon be egy értéket a – mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3e60b-136">In the through field, type a value.</span></span>
17. <span data-ttu-id="3e60b-137">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="3e60b-137">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="3e60b-138">A listában keresse meg azt a speciális szabálystruktúrát, amelyet akkor szeretne használni, amikor a megadott feltételek teljesülnek.</span><span class="sxs-lookup"><span data-stu-id="3e60b-138">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
19. <span data-ttu-id="3e60b-139">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="3e60b-139">Click Add.</span></span>
20. <span data-ttu-id="3e60b-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3e60b-140">Close the page.</span></span>
21. <span data-ttu-id="3e60b-141">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="3e60b-141">Click Activate.</span></span>
22. <span data-ttu-id="3e60b-142">Kattintson az Aktiválás gombra.</span><span class="sxs-lookup"><span data-stu-id="3e60b-142">Click Activate.</span></span>

