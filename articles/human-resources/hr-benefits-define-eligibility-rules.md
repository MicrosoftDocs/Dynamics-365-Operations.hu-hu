---
title: Juttatásra való jogosultsági szabályok és irányelvek meghatározása
description: Ez a cikk bemutatja, hogyan hozhat létre juttatásra való jogosultsági szabályokat és irányelveket, majd miként rendelhet hozzá szabályokat a juttatásokhoz.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: df517e1ab72634cb434411fab3bd92bf34c7e609
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805946"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="d63f9-103">Juttatásra való jogosultsági szabályok és irányelvek meghatározása</span><span class="sxs-lookup"><span data-stu-id="d63f9-103">Define benefit eligibility rules and policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d63f9-104">Ez a témakör bemutatja, hogyan hozhat létre juttatásra való jogosultsági szabályokat és irányelveket, majd miként rendelhet hozzá szabályokat a juttatásokhoz.</span><span class="sxs-lookup"><span data-stu-id="d63f9-104">This topic shows you how you can create benefit eligibility rules and policies and then assign rules to benefits.</span></span>  

## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="d63f9-105">Juttatásra való jogosultsági irányelvszabály-típus létrehozása</span><span class="sxs-lookup"><span data-stu-id="d63f9-105">Create benefit eligibility policy rule type</span></span>

1. <span data-ttu-id="d63f9-106">Ugorjon az **Emberi erőforrások > Juttatások > Jogosultság > Juttatásra való jogosultsági irányelvszabály-típusok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d63f9-106">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policy rule types**.</span></span>
2. <span data-ttu-id="d63f9-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d63f9-107">Select **New**.</span></span>
3. <span data-ttu-id="d63f9-108">A **Szabály neve** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d63f9-108">In the **Rule name** field, enter a value.</span></span>
4. <span data-ttu-id="d63f9-109">A **Leírás** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d63f9-109">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="d63f9-110">A **Lekérdezés neve** mezőben kattintson a legördülő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d63f9-110">In the **Query name** field, select the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="d63f9-111">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="d63f9-111">In the list, select the link in the selected row.</span></span>
7. <span data-ttu-id="d63f9-112">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d63f9-112">Select **Save**.</span></span>
8. <span data-ttu-id="d63f9-113">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d63f9-113">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="d63f9-114">Juttatásra való jogosultsági irányelv</span><span class="sxs-lookup"><span data-stu-id="d63f9-114">Benefit eligibility policy</span></span>

1. <span data-ttu-id="d63f9-115">Ugorjon az **Emberi erőforrások > Juttatások > Jogosultság > Juttatásra való jogosultsági irányelvszabályok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d63f9-115">Go to **Human resources > Benefits > Eligibility > Benefit eligibility policies**.</span></span>
2. <span data-ttu-id="d63f9-116">Válasszon ki egy meglévő juttatási irányelvet.</span><span class="sxs-lookup"><span data-stu-id="d63f9-116">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="d63f9-117">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="d63f9-117">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="d63f9-118">Bontsa ki az **Irányelv szervezetei** részt.</span><span class="sxs-lookup"><span data-stu-id="d63f9-118">Toggle the expansion of the **Policy organizations** sections.</span></span> <span data-ttu-id="d63f9-119">Felveheti és eltávolíthatja a szervezeteket, amelyeket meg kíván említeni az irányelvben.</span><span class="sxs-lookup"><span data-stu-id="d63f9-119">You can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="d63f9-120">Csukja be vagy bontsa ki az **Irányelvszabályok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d63f9-120">Expand or collapse the **Policy rules** section.</span></span>
6. <span data-ttu-id="d63f9-121">A listában keresse ki a korábban létrehozott irányelvszabályt.</span><span class="sxs-lookup"><span data-stu-id="d63f9-121">In the list, find the policy rule previously created.</span></span>
7. <span data-ttu-id="d63f9-122">Válassza ki az **Irányelvszabály létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d63f9-122">Select **Create policy rule**.</span></span>
8. <span data-ttu-id="d63f9-123">Az **Érvényesség dátuma** mezőben adja meg a dátumot, amikor érvénybe kívánja léptetni az irányelvet.</span><span class="sxs-lookup"><span data-stu-id="d63f9-123">In the **Effective date** field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="d63f9-124">Az érvényesség kezdő és záró dátumának beállítása lehetővé teszi az irányelvszabályok későbbi módosítását, és így nem kell visszatérnie az irányelvhez, ha szeretné érvényesíteni ezeket a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="d63f9-124">Setting effective end dates allows you to make future changes to policy rules so you don't need to come back to the policy when you want those changes to take effect.</span></span>  
9. <span data-ttu-id="d63f9-125">Ha szükséges, adjon hozzá egy Where feltételt a **Feltétel hozzáadása** mezőhöz.</span><span class="sxs-lookup"><span data-stu-id="d63f9-125">If needed, add a where clause to the **Add condition** field.</span></span>
    * <span data-ttu-id="d63f9-126">Például, ha szeretné, hogy a szabály csak az Értékesítési vezetőkre vonatkozzon, akkor létrehozhatja az alábbi Where feltételt: Ahol a beosztás leírása megegyezik az Értékesítési vezető értékkel.</span><span class="sxs-lookup"><span data-stu-id="d63f9-126">For example if you wanted the rule to only apply to Sales Managers you could create the where clause to say: Where position description equals Sales Manager.</span></span> <span data-ttu-id="d63f9-127">Több Where kimutatást adhat össze a szabályban.</span><span class="sxs-lookup"><span data-stu-id="d63f9-127">You can add multiple where statements together in the rule.</span></span>  
10. <span data-ttu-id="d63f9-128">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d63f9-128">Select **OK**.</span></span>
11. <span data-ttu-id="d63f9-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d63f9-129">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="d63f9-130">Szabály hozzárendelése juttatáshoz</span><span class="sxs-lookup"><span data-stu-id="d63f9-130">Assign rule to benefit</span></span>

1. <span data-ttu-id="d63f9-131">Ugorjon az **Emberi erőforrások > Juttatások > Juttatások** pontra.</span><span class="sxs-lookup"><span data-stu-id="d63f9-131">Go to **Human resources > Benefits > Benefits**.</span></span>
2. <span data-ttu-id="d63f9-132">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d63f9-132">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d63f9-133">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="d63f9-133">In the list, select the link in the selected row.</span></span>
4. <span data-ttu-id="d63f9-134">Bontsa ki vagy zárja be az **Alkalmazhatósági szabályok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d63f9-134">Expand or collapse the **Eligibility rules** section.</span></span>
5. <span data-ttu-id="d63f9-135">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="d63f9-135">Select **Edit**.</span></span>
6. <span data-ttu-id="d63f9-136">Az **Alkalmazhatóság** mezőben válassza ki a szabályt.</span><span class="sxs-lookup"><span data-stu-id="d63f9-136">In the **Eligibility** field, select the rule.</span></span>
7. <span data-ttu-id="d63f9-137">A **Szabálytípus** mezőben keresse meg és válassza ki a korábban létrehozott szabályt.</span><span class="sxs-lookup"><span data-stu-id="d63f9-137">In the **Rule type** field, select the rule you previously created.</span></span>
9. <span data-ttu-id="d63f9-138">A listában válassza ki a kiválasztott sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="d63f9-138">In the list, select the link in the selected row.</span></span>
10. <span data-ttu-id="d63f9-139">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d63f9-139">Select **Save**.</span></span>
11. <span data-ttu-id="d63f9-140">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="d63f9-140">Close the form.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]