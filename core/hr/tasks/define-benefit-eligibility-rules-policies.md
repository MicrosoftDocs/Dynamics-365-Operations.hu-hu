--- 
title: "Juttatásra való jogosultsági szabályok és irányelvek meghatározása"
description: "Ez a felvétel bemutatja, hogyan hozhat létre juttatásra való jogosultsági szabályokat és irányelveket, majd miként rendelhet hozzá szabályokat a Juttatásokhoz."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 49d512c3093f97c9c6d8ab15d29119e7a3b9a455
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="define-benefit-eligibility-rules-and-policies"></a><span data-ttu-id="8cccb-103">Juttatásra való jogosultsági szabályok és irányelvek meghatározása</span><span class="sxs-lookup"><span data-stu-id="8cccb-103">Define benefit eligibility rules and policies</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8cccb-104">Ez a felvétel bemutatja, hogyan hozhat létre juttatásra való jogosultsági szabályokat és irányelveket, majd miként rendelhet hozzá szabályokat a Juttatásokhoz.</span><span class="sxs-lookup"><span data-stu-id="8cccb-104">This recording will show you how you can create benefit eligibility rules and policies and then assign rules to Benefits.</span></span>  

<span data-ttu-id="8cccb-105">A bemutató adatsor típusa, melyet a vállalat használt az útmutató készítéséhez, az USMF.</span><span class="sxs-lookup"><span data-stu-id="8cccb-105">The demo data company used to create this recording is USMF.</span></span>


## <a name="create-benefit-eligibility-policy-rule-type"></a><span data-ttu-id="8cccb-106">Juttatásra való jogosultsági irányelvszabály-típus létrehozása</span><span class="sxs-lookup"><span data-stu-id="8cccb-106">Create benefit eligibility policy rule type</span></span>
1. <span data-ttu-id="8cccb-107">Ugorjon az Emberi erőforrások > Juttatások > Jogosultság > Juttatásra való jogosultsági irányelvszabály-típusok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8cccb-107">Go to Human resources > Benefits > Eligibility > Benefit eligibility policy rule types.</span></span>
2. <span data-ttu-id="8cccb-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8cccb-108">Click New.</span></span>
3. <span data-ttu-id="8cccb-109">Írjon be egy értéket a Szabály neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8cccb-109">In the Rule name field, type a value.</span></span>
4. <span data-ttu-id="8cccb-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8cccb-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="8cccb-111">A Lekérdezés neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8cccb-111">In the Query name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="8cccb-112">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8cccb-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="8cccb-113">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8cccb-113">Click Save.</span></span>
8. <span data-ttu-id="8cccb-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8cccb-114">Close the page.</span></span>

## <a name="benefit-eligibility-policy"></a><span data-ttu-id="8cccb-115">Juttatásra való jogosultsági irányelv</span><span class="sxs-lookup"><span data-stu-id="8cccb-115">Benefit eligibility policy</span></span>
1. <span data-ttu-id="8cccb-116">Ugorjon az Emberi erőforrások > Juttatások > Jogosultság > Juttatásra való jogosultsági irányelvszabályok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8cccb-116">Go to Human resources > Benefits > Eligibility > Benefit eligibility policies.</span></span>
2. <span data-ttu-id="8cccb-117">Válasszon ki egy meglévő juttatási irányelvet.</span><span class="sxs-lookup"><span data-stu-id="8cccb-117">Select an existing benefit policy.</span></span>
3. <span data-ttu-id="8cccb-118">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8cccb-118">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8cccb-119">Bontsa ki az Irányelv szervezetei részt.</span><span class="sxs-lookup"><span data-stu-id="8cccb-119">Toggle the expansion of the Policy organizations sections.</span></span>  <span data-ttu-id="8cccb-120">Itt felveheti és eltávolíthatja a szervezeteket, amelyeket meg kíván említeni az irányelvben.</span><span class="sxs-lookup"><span data-stu-id="8cccb-120">Here you can add or remove any organizations you want to include in the policy.</span></span>
5. <span data-ttu-id="8cccb-121">Csukja be vagy bontsa ki az Irányelvszabályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8cccb-121">Expand or collapse the Policy rules section.</span></span>
6. <span data-ttu-id="8cccb-122">A listában keresse ki a korábban létrehozott irányelvszabályt.</span><span class="sxs-lookup"><span data-stu-id="8cccb-122">In the list find the policy rule previously created.</span></span>
7. <span data-ttu-id="8cccb-123">Kattintson az Irányelvszabályra.</span><span class="sxs-lookup"><span data-stu-id="8cccb-123">Click Create policy rule.</span></span>
8. <span data-ttu-id="8cccb-124">Az Érvényesség dátuma mezőben adja meg a dátumot, amikor érvénybe kívánja léptetni az irányelvet.</span><span class="sxs-lookup"><span data-stu-id="8cccb-124">In the Effective date field, enter the date in which you want the policy to become effective.</span></span>
    * <span data-ttu-id="8cccb-125">Az érvényesség kezdő és záró dátumának beállítása lehetővé teszi az irányelvszabályok későbbi módosítását, és így nincs szükség visszatérni az irányelvhez, ha szeretné érvényesíteni ezeket a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="8cccb-125">Setting effective and end dates allows you to make future changes to policy rules and removing the need to come back to the policy when you want those changes to take effect.</span></span>  
9. 
    * <span data-ttu-id="8cccb-126">Például, ha szeretné, hogy a szabály csak az Értékesítési vezetőkre vonatkozzon, akkor létrehozhatja az alábbi Where feltételt: Ahol a beosztás leírása megegyezik az Értékesítési vezető értékkel.</span><span class="sxs-lookup"><span data-stu-id="8cccb-126">For example if you wanted the rule to only apply to Sales Managers you could create the Where clause to say: Where position description equals Sales Manager.</span></span>  <span data-ttu-id="8cccb-127">A Where kimutatást És vagy Vagy művelettel szorozhatja össze a szabályban.</span><span class="sxs-lookup"><span data-stu-id="8cccb-127">You can And or Or multiple Where statements together in the rule.</span></span>  
10. <span data-ttu-id="8cccb-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8cccb-128">Click OK.</span></span>
11. <span data-ttu-id="8cccb-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8cccb-129">Close the page.</span></span>
12. <span data-ttu-id="8cccb-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8cccb-130">Close the page.</span></span>

## <a name="assign-rule-to-benefit"></a><span data-ttu-id="8cccb-131">Szabály hozzárendelése juttatáshoz</span><span class="sxs-lookup"><span data-stu-id="8cccb-131">Assign rule to benefit</span></span>
1. <span data-ttu-id="8cccb-132">Ugorjon az Emberi erőforrások > Juttatások > Juttatások pontra.</span><span class="sxs-lookup"><span data-stu-id="8cccb-132">Go to Human resources > Benefits > Benefits.</span></span>
2. <span data-ttu-id="8cccb-133">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8cccb-133">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="8cccb-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8cccb-134">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="8cccb-135">Bontsa ki vagy zárja be az Alkalmazhatósági szabályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8cccb-135">Expand or collapse the Eligibility rules section.</span></span>
5. <span data-ttu-id="8cccb-136">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8cccb-136">Click Edit.</span></span>
6. <span data-ttu-id="8cccb-137">Az Alkalmazhatóság mezőben válassza ki a Szabályalapú lehetőséget a listáról.</span><span class="sxs-lookup"><span data-stu-id="8cccb-137">In the Eligibility field, select Rule based from the list.</span></span>
7. <span data-ttu-id="8cccb-138">A Szabálytípus mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="8cccb-138">In the Rule type field, click the drop down button to open the lookup.</span></span>
8. <span data-ttu-id="8cccb-139">A listában keresse meg és válassza ki a korábban létrehozott szabályt.</span><span class="sxs-lookup"><span data-stu-id="8cccb-139">In the list find and select the rule you previously created.</span></span>
9. <span data-ttu-id="8cccb-140">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="8cccb-140">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="8cccb-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8cccb-141">Click Save.</span></span>
11. <span data-ttu-id="8cccb-142">Zárja be az űrlapot.</span><span class="sxs-lookup"><span data-stu-id="8cccb-142">Close the form.</span></span>


