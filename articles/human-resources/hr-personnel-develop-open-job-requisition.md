---
title: Beosztásigénylés kialakítása és megnyitása
description: A toborzási projektek segítenek a toborzási folyamat kezelésében.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMRecruitingTable, HcmWorkerLookUp, HcmJobLookup, HRMRecruitingMedia, HRMRecruitingJobAd, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3207d61536422255b574fd126f16075fcddc2c93
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418786"
---
# <a name="develop-and-open-job-requisition"></a><span data-ttu-id="86cfc-103">Beosztásigénylés kialakítása és megnyitása</span><span class="sxs-lookup"><span data-stu-id="86cfc-103">Develop and open job requisition</span></span>



<span data-ttu-id="86cfc-104">A toborzási projektek segítenek a toborzási folyamat kezelésében.</span><span class="sxs-lookup"><span data-stu-id="86cfc-104">Recruitment projects help manage the recruiting process.</span></span> <span data-ttu-id="86cfc-105">Minden toborzási projekthez beállíthatja az adatokat, például a feladatot, amelyhez a toborzás történik, a toborzó nevét, a projekt és a részleg státuszát, ahol a feladatot végezni fogják.</span><span class="sxs-lookup"><span data-stu-id="86cfc-105">For each recruitment project, you can set up information, such as the job that recruiting is for, the name of the recruiter, the status of the project and the department that the job will be located in.</span></span> <span data-ttu-id="86cfc-106">Miután létrehozta a toborzási projektet, megírhatja a projekthez tartozó álláshirdetést, közzéteheti az Alkalmazotti önkiszolgáló rendszer oldalain, hozzárendelheti a projekthez az álláspályázatokat és nyomon követheti a projekthez tartozó tevékenységeket.</span><span class="sxs-lookup"><span data-stu-id="86cfc-106">After creating a recruitment project, you can write a job advertisement for the project, publish the ad on Employee self-service pages, associate applications for employment with the project, and track activities for that project.</span></span> <span data-ttu-id="86cfc-107">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="86cfc-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="86cfc-108">Az eljárás megkezdéséhez lépjen az Emberi erőforrások > a Toborzás > a Toborzási projektek > a Toborzási projektek menüpontokra</span><span class="sxs-lookup"><span data-stu-id="86cfc-108">To begin the procedure, go to Human resources > Recruitment > Recruitment projects > Recruitment projects</span></span>

1. <span data-ttu-id="86cfc-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="86cfc-109">Click New.</span></span>
2. <span data-ttu-id="86cfc-110">A Toborzási projekt mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="86cfc-110">In the Recruitment project field, type a value.</span></span>
3. <span data-ttu-id="86cfc-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="86cfc-111">In the Description field, type a value.</span></span>
4. <span data-ttu-id="86cfc-112">A Toborzási mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="86cfc-112">In the Recruiter field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="86cfc-113">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="86cfc-113">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="86cfc-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="86cfc-115">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="86cfc-115">Click Select.</span></span>
8. <span data-ttu-id="86cfc-116">A Részleg mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="86cfc-116">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="86cfc-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-117">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="86cfc-118">Az Állás mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="86cfc-118">In the Job field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="86cfc-119">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="86cfc-119">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="86cfc-120">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-120">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="86cfc-121">Adjon meg egy számot a Pályázható álláshelyek száma mezőben.</span><span class="sxs-lookup"><span data-stu-id="86cfc-121">In the Number of openings field, enter a number.</span></span>
14. <span data-ttu-id="86cfc-122">A Felvételi vezető mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="86cfc-122">In the Hiring manager field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="86cfc-123">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="86cfc-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="86cfc-124">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="86cfc-125">Kattintson a Kiválasztás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="86cfc-125">Click Select.</span></span>
18. <span data-ttu-id="86cfc-126">Írjon be egy dátumot a Pályázati határidő mezőbe.</span><span class="sxs-lookup"><span data-stu-id="86cfc-126">In the Application deadline field, enter a date.</span></span>
19. <span data-ttu-id="86cfc-127">Kattintson a Média parancsra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-127">Click Media.</span></span>
    * <span data-ttu-id="86cfc-128">A Toborzási projektekben meg lehet adni azokat a médiaorgánumokat, amelyeket a nyitott pozíciók hirdetésére kíván használni.</span><span class="sxs-lookup"><span data-stu-id="86cfc-128">Recruitment projects include the option to specify media outlets to use to advertise open positions.</span></span>  
20. <span data-ttu-id="86cfc-129">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="86cfc-129">Click New.</span></span>
21. <span data-ttu-id="86cfc-130">A Média mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="86cfc-130">In the Media field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="86cfc-131">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-131">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="86cfc-132">Adja meg a dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="86cfc-132">In the Start date field, enter a date.</span></span>
24. <span data-ttu-id="86cfc-133">Adja meg a dátumot a Záró dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="86cfc-133">In the End date field, enter a date.</span></span>
25. <span data-ttu-id="86cfc-134">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-134">Click Save.</span></span>
26. <span data-ttu-id="86cfc-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="86cfc-135">Close the page.</span></span>
27. <span data-ttu-id="86cfc-136">Kattintson az Álláshirdetések parancsra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-136">Click Job ads.</span></span>
28. <span data-ttu-id="86cfc-137">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-137">Click Save.</span></span>
29. <span data-ttu-id="86cfc-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="86cfc-138">Close the page.</span></span>
30. <span data-ttu-id="86cfc-139">Jelölje be a Megjelenítés az alkalmazotti önkiszolgáló rendszerben jelölőnégyzetet vagy vegye ki belőle a jelölést.</span><span class="sxs-lookup"><span data-stu-id="86cfc-139">Check or uncheck the Display on employee self service checkbox.</span></span>
    * <span data-ttu-id="86cfc-140">Válassza ki a Megjelenítés az alkalmazotti önkiszolgáló rendszerben jelölőnégyzetet, ha szeretné, hogy a toborzási projekt látható legyen az alkalmazottak számára az Alkalmazotti önkiszolgáló rendszer lapjain.</span><span class="sxs-lookup"><span data-stu-id="86cfc-140">Select the Display on employee self service check box to make the recruitment project visible to employees on their Employee self-service pages.</span></span>  
31. <span data-ttu-id="86cfc-141">Kattintson Toborzási projekt állapota parancsra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-141">Click Recruitment project status.</span></span>
32. <span data-ttu-id="86cfc-142">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="86cfc-142">Click Start.</span></span>
    * <span data-ttu-id="86cfc-143">Az Elindítva állapot azt jelenti, hogy a projekt készen áll pályázatok fogadására.</span><span class="sxs-lookup"><span data-stu-id="86cfc-143">The Started status means that the project is ready to receive applications.</span></span>  
33. <span data-ttu-id="86cfc-144">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="86cfc-144">Click OK.</span></span>

