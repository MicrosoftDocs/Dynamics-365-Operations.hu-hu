---
title: Alkalmazotti juttatási program megvalósítása
description: A cikk bemutatja, hogyan hozhat létre juttatási elemeket, amelyeket az új juttatások létrehozása során használni fog.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmBenefitElementSetup, HcmBenefit, HcmBenefitNewBenefit, HcmBenefitPlanLookup
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: b8631e4f8cb2947ec7e09de86a7ceb075a83a453
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009346"
---
# <a name="deliver-employee-benefits-program"></a><span data-ttu-id="6c92c-103">Alkalmazotti juttatási program megvalósítása</span><span class="sxs-lookup"><span data-stu-id="6c92c-103">Deliver employee benefits program</span></span>

<span data-ttu-id="6c92c-104">A cikk bemutatja, hogyan hozhat létre juttatási elemeket, amelyeket az új juttatások létrehozása során használni fog.</span><span class="sxs-lookup"><span data-stu-id="6c92c-104">This article shows you how to create benefit elements which will be used when creating a new benefit.</span></span> <span data-ttu-id="6c92c-105">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="6c92c-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="6c92c-106">A feladat a Kompenzációkért és juttatásokért felelős vezetőnek szól.</span><span class="sxs-lookup"><span data-stu-id="6c92c-106">This task is intended for a Compensation and Benefits manager.</span></span>


## <a name="create-benefit-elements"></a><span data-ttu-id="6c92c-107">Juttatás elemeinek létrehozása</span><span class="sxs-lookup"><span data-stu-id="6c92c-107">Create benefit elements</span></span>
1. <span data-ttu-id="6c92c-108">A feladat a Juttatások listája oldalon kezdődik.</span><span class="sxs-lookup"><span data-stu-id="6c92c-108">This task starts from the Benefits list page.</span></span> <span data-ttu-id="6c92c-109">Indítsa el a feladatot: nyissa meg az oldalt vagy keressen a Juttatások listája oldalon.</span><span class="sxs-lookup"><span data-stu-id="6c92c-109">Start the task by opening that page or searching the Benefits list page.</span></span>
2. <span data-ttu-id="6c92c-110">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="6c92c-110">Click New.</span></span>
3. <span data-ttu-id="6c92c-111">Írja be a most létrehozott juttatástípus nevét a Típus mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6c92c-111">In the Type field, Enter the name of the type of benefit you are creating..</span></span>
4. <span data-ttu-id="6c92c-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6c92c-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6c92c-113">Egy lehetőség kiválasztása az Egyidejű belépés mezőben.</span><span class="sxs-lookup"><span data-stu-id="6c92c-113">In the Concurrent enrollment field, select an option.</span></span>
    * <span data-ttu-id="6c92c-114">Annak érdekében, hogy korlátozza az alkalmazottak több egészségügyi konstrukcióba való felvételét, válassza ki a Típusonként egy felvétel lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6c92c-114">To restrict employees' ability to enroll in multiple medical plans, select One enrollment per type.</span></span>  
6. <span data-ttu-id="6c92c-115">Egy lehetőség kiválasztása a Bérlista kategóriája mezőben.</span><span class="sxs-lookup"><span data-stu-id="6c92c-115">In the Payroll category field, select an option.</span></span>
7. <span data-ttu-id="6c92c-116">Kattintson a Konstrukció fülre.</span><span class="sxs-lookup"><span data-stu-id="6c92c-116">Click the Plans tab.</span></span>
8. <span data-ttu-id="6c92c-117">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="6c92c-117">Click New.</span></span>
9. <span data-ttu-id="6c92c-118">Érték beírása a Konstrukció mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6c92c-118">In the Plan field, type a value.</span></span>
10. <span data-ttu-id="6c92c-119">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6c92c-119">In the Description field, type a value.</span></span>
11. <span data-ttu-id="6c92c-120">A Típus mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6c92c-120">In the Type field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="6c92c-121">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="6c92c-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="6c92c-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6c92c-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="6c92c-123">Egy lehetőség kiválasztása a Bérlista hatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="6c92c-123">In the Payroll impact field, select an option.</span></span>
15. <span data-ttu-id="6c92c-124">Kattintson az Opciók fülre.</span><span class="sxs-lookup"><span data-stu-id="6c92c-124">Click the Options tab.</span></span>
16. <span data-ttu-id="6c92c-125">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="6c92c-125">Click New.</span></span>
17. <span data-ttu-id="6c92c-126">Érték beírása az Opció mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6c92c-126">In the Option field, type a value.</span></span>
18. <span data-ttu-id="6c92c-127">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6c92c-127">In the Description field, type a value.</span></span>

## <a name="create-a-benefit"></a><span data-ttu-id="6c92c-128">Juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="6c92c-128">Create a benefit</span></span>
1. <span data-ttu-id="6c92c-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6c92c-129">Close the page.</span></span>
2. <span data-ttu-id="6c92c-130">Ugorjon az Emberi erőforrások > Juttatások > Juttatások pontra.</span><span class="sxs-lookup"><span data-stu-id="6c92c-130">Go to Human resources > Benefits > Benefits.</span></span>
3. <span data-ttu-id="6c92c-131">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6c92c-131">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="6c92c-132">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6c92c-132">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="6c92c-133">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="6c92c-133">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="6c92c-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6c92c-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="6c92c-135">Az Opció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6c92c-135">In the Option field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="6c92c-136">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="6c92c-136">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="6c92c-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6c92c-137">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="6c92c-138">Az Érvényesség mezőben adjon meg dátumot és időt.</span><span class="sxs-lookup"><span data-stu-id="6c92c-138">In the Effective field, enter a date and time.</span></span>
11. <span data-ttu-id="6c92c-139">Kattintson a Juttatás létrehozása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6c92c-139">Click Create benefit.</span></span>
12. <span data-ttu-id="6c92c-140">Bontsa ki a Bérlista részletei részt.</span><span class="sxs-lookup"><span data-stu-id="6c92c-140">Toggle the expansion of the Payroll details section.</span></span>
13. <span data-ttu-id="6c92c-141">A Gyakoriság mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6c92c-141">In the Frequency field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="6c92c-142">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="6c92c-142">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="6c92c-143">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6c92c-143">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="6c92c-144">Egy lehetőség kiválasztása az Alap mezőben.</span><span class="sxs-lookup"><span data-stu-id="6c92c-144">In the Basis field, select an option.</span></span>
17. <span data-ttu-id="6c92c-145">Az Összeg vagy arány mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="6c92c-145">In the Amount or rate field, enter a number.</span></span>
