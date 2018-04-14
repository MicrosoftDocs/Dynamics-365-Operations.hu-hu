--- 
title: "Alkalmazotti juttatási program megvalósítása"
description: "A feladat bemutatja, hogyan hozhat létre juttatási elemeket, amelyeket az új juttatás létrehozása során használni fog."
author: kherr75
manager: AnnBe
ms.date: 12/01/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c94f731cbdd62d51a21a42e8fcc86c5711c0e965
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="deliver-an-employee-benefits-program"></a><span data-ttu-id="9eafb-103">Alkalmazotti juttatási program megvalósítása</span><span class="sxs-lookup"><span data-stu-id="9eafb-103">Deliver an employee benefits program</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9eafb-104">A feladat bemutatja, hogyan hozhat létre juttatási elemeket, amelyeket az új juttatás létrehozása során használni fog.</span><span class="sxs-lookup"><span data-stu-id="9eafb-104">This task will show you how to create benefit elements which will be used when creating a new benefit.</span></span> <span data-ttu-id="9eafb-105">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="9eafb-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="9eafb-106">A feladat a Kompenzációkért és juttatásokért felelős vezetőnek szól.</span><span class="sxs-lookup"><span data-stu-id="9eafb-106">This task is intended for a Compensation and Benefits manager.</span></span>


## <a name="create-benefit-elements"></a><span data-ttu-id="9eafb-107">Juttatás elemeinek létrehozása</span><span class="sxs-lookup"><span data-stu-id="9eafb-107">Create benefit elements</span></span>
1. <span data-ttu-id="9eafb-108">A feladat a Juttatások listája oldalon kezdődik.</span><span class="sxs-lookup"><span data-stu-id="9eafb-108">This task starts from the Benefits list page.</span></span> <span data-ttu-id="9eafb-109">Indítsa el a feladatot: nyissa meg az oldalt vagy keressen a Juttatások listája oldalon.</span><span class="sxs-lookup"><span data-stu-id="9eafb-109">Start the task by opening that page or searching the Benefits list page.</span></span>
2. <span data-ttu-id="9eafb-110">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="9eafb-110">Click New.</span></span>
3. <span data-ttu-id="9eafb-111">Írja be a most létrehozott juttatástípus nevét a Típus mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9eafb-111">In the Type field, Enter the name of the type of benefit you are creating..</span></span>
4. <span data-ttu-id="9eafb-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9eafb-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="9eafb-113">Egy lehetőség kiválasztása az Egyidejű belépés mezőben.</span><span class="sxs-lookup"><span data-stu-id="9eafb-113">In the Concurrent enrollment field, select an option.</span></span>
    * <span data-ttu-id="9eafb-114">Annak érdekében, hogy korlátozza az alkalmazottak több egészségügyi konstrukcióba való felvételét, válassza ki a Típusonként egy felvétel lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9eafb-114">To restrict employees' ability to enroll in multiple medical plans, select One enrollment per type.</span></span>  
6. <span data-ttu-id="9eafb-115">Egy lehetőség kiválasztása a Bérlista kategóriája mezőben.</span><span class="sxs-lookup"><span data-stu-id="9eafb-115">In the Payroll category field, select an option.</span></span>
7. <span data-ttu-id="9eafb-116">Kattintson a Konstrukció fülre.</span><span class="sxs-lookup"><span data-stu-id="9eafb-116">Click the Plans tab.</span></span>
8. <span data-ttu-id="9eafb-117">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="9eafb-117">Click New.</span></span>
9. <span data-ttu-id="9eafb-118">Érték beírása a Konstrukció mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9eafb-118">In the Plan field, type a value.</span></span>
10. <span data-ttu-id="9eafb-119">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9eafb-119">In the Description field, type a value.</span></span>
11. <span data-ttu-id="9eafb-120">A Típus mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9eafb-120">In the Type field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="9eafb-121">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="9eafb-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="9eafb-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9eafb-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="9eafb-123">Egy lehetőség kiválasztása a Bérlista hatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="9eafb-123">In the Payroll impact field, select an option.</span></span>
15. <span data-ttu-id="9eafb-124">Kattintson az Opciók fülre.</span><span class="sxs-lookup"><span data-stu-id="9eafb-124">Click the Options tab.</span></span>
16. <span data-ttu-id="9eafb-125">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="9eafb-125">Click New.</span></span>
17. <span data-ttu-id="9eafb-126">Érték beírása az Opció mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9eafb-126">In the Option field, type a value.</span></span>
18. <span data-ttu-id="9eafb-127">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="9eafb-127">In the Description field, type a value.</span></span>

## <a name="create-a-benefit"></a><span data-ttu-id="9eafb-128">Juttatás létrehozása</span><span class="sxs-lookup"><span data-stu-id="9eafb-128">Create a benefit</span></span>
1. <span data-ttu-id="9eafb-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9eafb-129">Close the page.</span></span>
2. <span data-ttu-id="9eafb-130">Ugorjon az Emberi erőforrások > Juttatások > Juttatások pontra.</span><span class="sxs-lookup"><span data-stu-id="9eafb-130">Go to Human resources > Benefits > Benefits.</span></span>
3. <span data-ttu-id="9eafb-131">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="9eafb-131">Click New to open the drop dialog.</span></span>
4. <span data-ttu-id="9eafb-132">A Konstrukció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9eafb-132">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="9eafb-133">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="9eafb-133">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="9eafb-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9eafb-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="9eafb-135">Az Opció mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9eafb-135">In the Option field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="9eafb-136">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="9eafb-136">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="9eafb-137">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9eafb-137">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="9eafb-138">Az Érvényesség mezőben adjon meg dátumot és időt.</span><span class="sxs-lookup"><span data-stu-id="9eafb-138">In the Effective field, enter a date and time.</span></span>
11. <span data-ttu-id="9eafb-139">Kattintson a Juttatás létrehozása hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9eafb-139">Click Create benefit.</span></span>
12. <span data-ttu-id="9eafb-140">Bontsa ki a Bérlista részletei részt.</span><span class="sxs-lookup"><span data-stu-id="9eafb-140">Toggle the expansion of the Payroll details section.</span></span>
13. <span data-ttu-id="9eafb-141">A Gyakoriság mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="9eafb-141">In the Frequency field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="9eafb-142">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="9eafb-142">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="9eafb-143">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="9eafb-143">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="9eafb-144">Egy lehetőség kiválasztása az Alap mezőben.</span><span class="sxs-lookup"><span data-stu-id="9eafb-144">In the Basis field, select an option.</span></span>
17. <span data-ttu-id="9eafb-145">Az Összeg vagy arány mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="9eafb-145">In the Amount or rate field, enter a number.</span></span>


