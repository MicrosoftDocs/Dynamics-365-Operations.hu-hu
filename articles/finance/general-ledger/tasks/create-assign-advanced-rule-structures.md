---
title: Speciális szabálystruktúrák létrehozása és hozzárendelése
description: Ez a témakör leírja, hogyan hozhat létre és rendelhet hozzá egy speciális szabályszerkezetet egy számlastruktúrához.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a7b9d0c20a49996b4c8d45b030d9e587818de3d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216545"
---
# <a name="create-and-assign-advanced-rule-structures"></a><span data-ttu-id="b26d4-103">Speciális szabálystruktúrák létrehozása és hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="b26d4-103">Create and assign advanced rule structures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b26d4-104">Ez a témakör leírja, hogyan hozhat létre és rendelhet hozzá egy speciális szabályszerkezetet egy számlastruktúrához.</span><span class="sxs-lookup"><span data-stu-id="b26d4-104">This topic explains how to create and assign an advanced rule structure to an account structure.</span></span> <span data-ttu-id="b26d4-105">Az útmutató az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b26d4-105">This guide uses the USMF demo company.</span></span>

## <a name="create-an-advanced-rule-structure"></a><span data-ttu-id="b26d4-106">Speciális szabálystruktúra létrehozása</span><span class="sxs-lookup"><span data-stu-id="b26d4-106">Create an advanced rule structure</span></span>
1. <span data-ttu-id="b26d4-107">Ugrás a következő útvonalra: **Navigációs ablaktábla > Modulok > Főkönyv > Számlatükör > Struktúrák > Speciális számlastruktúrák**.</span><span class="sxs-lookup"><span data-stu-id="b26d4-107">Go to **Navigation pane > Modules > General ledger > Chart of accounts > Structures > Advanced rule structures**.</span></span>
2. <span data-ttu-id="b26d4-108">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b26d4-108">Select **New** to open the drop dialog.</span></span>
3. <span data-ttu-id="b26d4-109">A **Speciális szabálystruktúra** mezőbe írjon be egy nevet a szabálystruktúra leírásához.</span><span class="sxs-lookup"><span data-stu-id="b26d4-109">In the **Advanced rule structure** field, type a name to describe the rule structure.</span></span>
4. <span data-ttu-id="b26d4-110">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b26d4-110">Select **OK**.</span></span>
5. <span data-ttu-id="b26d4-111">Válassza a **Szegmens hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b26d4-111">Select **Add segment**.</span></span>
6. <span data-ttu-id="b26d4-112">A szegmensek listájáról válassza ki a pénzügyi dimenziót.</span><span class="sxs-lookup"><span data-stu-id="b26d4-112">In the list of segments, select a financial dimension.</span></span> <span data-ttu-id="b26d4-113">Például: **Bolt**.</span><span class="sxs-lookup"><span data-stu-id="b26d4-113">For example, **Store**.</span></span>  
7. <span data-ttu-id="b26d4-114">Válassza a **Szegmens hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b26d4-114">Select **Add segment**.</span></span>
8. <span data-ttu-id="b26d4-115">Válassza az **Aktiválás** lehetõséget.</span><span class="sxs-lookup"><span data-stu-id="b26d4-115">Select **Activate**.</span></span>

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a><span data-ttu-id="b26d4-116">Speciális szabály alkalmazása egy számlastruktúrához</span><span class="sxs-lookup"><span data-stu-id="b26d4-116">Apply an advanced rule structure to an account structure</span></span>
1. <span data-ttu-id="b26d4-117">Ugrás a következő útvonalra: **navigációs ablaktábla > Modulok > Főkönyv > Számlatükör > Struktúrák > Számlastruktúrák konfigurálása**.</span><span class="sxs-lookup"><span data-stu-id="b26d4-117">Go to **navigation pane > Modules > General ledger > Chart of accounts > Structures > Configure account structures**.</span></span>
2. <span data-ttu-id="b26d4-118">A listában keresse meg és válassza ki azt a számlastruktúrát, amelyhez a speciális szabályt alkalmazni szeretné.</span><span class="sxs-lookup"><span data-stu-id="b26d4-118">In the list, find and select the account structure you want to apply the advanced rule to.</span></span>
3. <span data-ttu-id="b26d4-119">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="b26d4-119">Select **Edit**.</span></span> <span data-ttu-id="b26d4-120">Ha a **Speciális szabályokra** kattint, a rendszer kérni fogja a számlastruktúra **Vázlat módba** történő helyezését.</span><span class="sxs-lookup"><span data-stu-id="b26d4-120">You can also select **Advanced rules** and you will be prompted to put the account structure in **Draft mode**.</span></span>  
4. <span data-ttu-id="b26d4-121">Válassza a **Speciális szabályok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b26d4-121">Select **Advanced rules**.</span></span>
5. <span data-ttu-id="b26d4-122">Az **Új** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b26d4-122">Select **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="b26d4-123">Írjon be egy értéket a **Speciális szabály** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b26d4-123">In the **Advanced rule** field, type a value.</span></span>
7. <span data-ttu-id="b26d4-124">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b26d4-124">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="b26d4-125">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b26d4-125">Select **Create**.</span></span>
9. <span data-ttu-id="b26d4-126">Kattintson az **Új feltételek hozzáadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="b26d4-126">Select **Add new criteria**.</span></span>
10. <span data-ttu-id="b26d4-127">A **Honnan** mezőben válassza ki a fő számlát vagy a pénzügyi dimenziót.</span><span class="sxs-lookup"><span data-stu-id="b26d4-127">In the **Where** field, select main account or a financial dimension.</span></span>
11. <span data-ttu-id="b26d4-128">A **Kezelő** mezőben válasszon ki egy lehetőséget, például a **között**, vagy a **tartalmazza** elemet.</span><span class="sxs-lookup"><span data-stu-id="b26d4-128">In the **Operator** field, select an option, such as **is between** and **includes**.</span></span>
12. <span data-ttu-id="b26d4-129">Érték beírása az **Érték** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b26d4-129">In the **Value** field, type a value.</span></span>
13. <span data-ttu-id="b26d4-130">Írjon be egy értéket a **–** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b26d4-130">In the **through** field, type a value.</span></span>
14. <span data-ttu-id="b26d4-131">A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b26d4-131">Select **Add** to open the drop dialog.</span></span>
15. <span data-ttu-id="b26d4-132">A listában keresse meg azt a speciális szabálystruktúrát, amelyet akkor szeretne használni, amikor a megadott feltételek teljesülnek.</span><span class="sxs-lookup"><span data-stu-id="b26d4-132">In the list, find the advanced rule structure you want to use when the criteria you entered is met.</span></span>
16. <span data-ttu-id="b26d4-133">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b26d4-133">Select **Add**.</span></span>
17. <span data-ttu-id="b26d4-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b26d4-134">Close the page.</span></span>
18. <span data-ttu-id="b26d4-135">Válassza az **Aktiválás** lehetõséget.</span><span class="sxs-lookup"><span data-stu-id="b26d4-135">Select **Activate**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]