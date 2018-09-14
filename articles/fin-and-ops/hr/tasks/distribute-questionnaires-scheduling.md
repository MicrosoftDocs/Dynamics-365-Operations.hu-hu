--- 
title: "Kérdőívek terjesztése ütemezés segítségével"
description: "A Kérdőív-ütemezés lehetővé teszi a kérdőívek tervezését és több válaszadónak történő terjesztését."
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: b66389a7d63c51f059a39495b8c7fbd325ef41e8
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="distribute-questionnaires-using-scheduling"></a><span data-ttu-id="6a259-103">Kérdőívek terjesztése ütemezés segítségével</span><span class="sxs-lookup"><span data-stu-id="6a259-103">Distribute questionnaires using scheduling</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6a259-104">A Kérdőív-ütemezés lehetővé teszi a kérdőívek tervezését és több válaszadónak történő terjesztését.</span><span class="sxs-lookup"><span data-stu-id="6a259-104">Questionnaire scheduling allows you to plan and distribute questionnaires to multiple respondents.</span></span> <span data-ttu-id="6a259-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="6a259-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-questionnaire-schedule"></a><span data-ttu-id="6a259-106">Hozzon létre egy kérdőív-ütemezést</span><span class="sxs-lookup"><span data-stu-id="6a259-106">Create a questionnaire schedule</span></span>
1. <span data-ttu-id="6a259-107">Ugrás a Kérdőív > Elosztás > Kérdőív-ütemezések elemre.</span><span class="sxs-lookup"><span data-stu-id="6a259-107">Go to Questionnaire > Distribute > Questionnaire schedules.</span></span>
2. <span data-ttu-id="6a259-108">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6a259-108">Click New.</span></span>
3. <span data-ttu-id="6a259-109">Az Ütemezési mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6a259-109">In the Scheduling field, type a value.</span></span>
4. <span data-ttu-id="6a259-110">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6a259-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="6a259-111">Állítsa be az ütemezést névtelen értékre, ha a válaszokat a válaszhoz tartozó nevek nélkül kell rögzíteni.</span><span class="sxs-lookup"><span data-stu-id="6a259-111">Set the schedule to Anonymous if the responses should be recorded without names associated to the response.</span></span>  
    * <span data-ttu-id="6a259-112">A névtelen eredmények engedélyezését először be kell állítani a HR-paraméterek között.</span><span class="sxs-lookup"><span data-stu-id="6a259-112">Allowing anonymous results must be set up in the HR parameters first.</span></span>  
5. <span data-ttu-id="6a259-113">Válassza ki a Tervezési típust a Típus mezőben.</span><span class="sxs-lookup"><span data-stu-id="6a259-113">In the Type field, select the planning type.</span></span>  <span data-ttu-id="6a259-114">Ebben a példában az Elégedettség típust fogjuk használni.</span><span class="sxs-lookup"><span data-stu-id="6a259-114">In this example we will use the Satisfaction type.</span></span>
6. <span data-ttu-id="6a259-115">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="6a259-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="6a259-116">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="6a259-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="6a259-117">Adja meg a dátumot a Dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="6a259-117">In the Date field, enter a date.</span></span>
9. <span data-ttu-id="6a259-118">Bontsa ki az E-mail az alkalmazotti önkiszolgáló rendszernek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="6a259-118">Expand the Email for employee self service section.</span></span>
10. <span data-ttu-id="6a259-119">Írjon be egy értéket a Tárgy mezőbe.</span><span class="sxs-lookup"><span data-stu-id="6a259-119">In the Subject field, type a value.</span></span>
    * <span data-ttu-id="6a259-120">Példa: Kérdőív elérhető</span><span class="sxs-lookup"><span data-stu-id="6a259-120">Example: Questionnaire available</span></span>  
11. <span data-ttu-id="6a259-121">A Szöveg mezőbe írja be az e-mail főszövegét.</span><span class="sxs-lookup"><span data-stu-id="6a259-121">In the Text field, type the body of your email message.</span></span> <span data-ttu-id="6a259-122">Ne feledje, a változó felhasználható értékek behelyettesítésére a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="6a259-122">Note, the variable can be used to substitue values in the system.</span></span>
    * <span data-ttu-id="6a259-123">Példa: Kedves %P%! Kérjük, jelentkezzen be az Alkalmazotti önkiszolgáló rendszerbe a munkaerő-egészségügyi kérdőív kitöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="6a259-123">Example:   Dear %P%,  Please log in to Employee Self Service to complete the Workforce Health questionnaire.</span></span>  <span data-ttu-id="6a259-124">Contoso</span><span class="sxs-lookup"><span data-stu-id="6a259-124">Contoso</span></span>  
12. <span data-ttu-id="6a259-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="6a259-125">Click Save.</span></span>

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a><span data-ttu-id="6a259-126">A Beállítás részletei segítségével válassza ki a megválaszolandó kérdőívet, valamint a válaszadók kiválasztásához használt lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="6a259-126">Use the Setup details to select the questionnaire(s) to be answered as well as any queries to use to select respondents.</span></span>
1. <span data-ttu-id="6a259-127">Kattintson a Beállítás részleteire.</span><span class="sxs-lookup"><span data-stu-id="6a259-127">Click Setup details.</span></span>
2. <span data-ttu-id="6a259-128">A listában válassza ki a kérdőívhez tartozó válaszadók megkereséséhez használni kívánt lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="6a259-128">In the list, select a query to use to search the system for respondents for the questionnaire.</span></span>
    * <span data-ttu-id="6a259-129">Példa: munkavállalók</span><span class="sxs-lookup"><span data-stu-id="6a259-129">Example: Workers</span></span>  
3. <span data-ttu-id="6a259-130">Kattintson a Lekérdezés megtekintése vagy módosítására specifikus személy kiválasztához vagy a lekérdezés módosításához a megadott feltételeknek megfelelő személyek megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="6a259-130">Click View or modify query to select specific people or adjust the query to find people who match specific criteria.</span></span>
    * <span data-ttu-id="6a259-131">Vegye figyelembe, hogy az összes válaszadónak a rendszerben is felhasználónak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6a259-131">Note that all respondents must also be users in the system.</span></span>  
4. <span data-ttu-id="6a259-132">A listában jelölje meg a Személy sort</span><span class="sxs-lookup"><span data-stu-id="6a259-132">In the list, mark the row for Person</span></span>
5. <span data-ttu-id="6a259-133">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="6a259-133">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="6a259-134">Válassza ki Julia Funderburkot</span><span class="sxs-lookup"><span data-stu-id="6a259-134">Select Julia Funderburk</span></span>  
6. <span data-ttu-id="6a259-135">A listában válassza ki Julia Funderburkot</span><span class="sxs-lookup"><span data-stu-id="6a259-135">In the list, select Julia Funderburk</span></span>
7. <span data-ttu-id="6a259-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6a259-136">Click OK.</span></span>
8. <span data-ttu-id="6a259-137">Kattintson a Kérdőívek lapra.</span><span class="sxs-lookup"><span data-stu-id="6a259-137">Click the Questionnaires tab.</span></span>
9. <span data-ttu-id="6a259-138">A fastruktúrában bontsa ki az „Elégedettségi felmérés típusú kérdőív csomópontját”.</span><span class="sxs-lookup"><span data-stu-id="6a259-138">In the tree, expand 'the node for the questionnaire type Satisfaction Survey'.</span></span>
10. <span data-ttu-id="6a259-139">A fastruktúrában jelölje be a „Munkaerő-egészségügyi vizsgálat” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6a259-139">In the tree, check 'Workforce Health Assessment'.</span></span>
11. <span data-ttu-id="6a259-140">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6a259-140">Click OK.</span></span>
12. <span data-ttu-id="6a259-141">Kattintson a Tervezett válaszmunkamenetre.</span><span class="sxs-lookup"><span data-stu-id="6a259-141">Click Planned answer session.</span></span>
    * <span data-ttu-id="6a259-142">Vegye figyelembe, hogy a tervezett válaszadási munkameneteket kiválasztott/kérdezhető felhasználónként hozzák létre.</span><span class="sxs-lookup"><span data-stu-id="6a259-142">Note that Planned answer sessions have been created for each selected/queried user.</span></span>  
13. <span data-ttu-id="6a259-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6a259-143">Close the page.</span></span>

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a><span data-ttu-id="6a259-144">Annak érdekében, hogy a kérdőív a teljesítéshez szükséges válaszadók számára elérhető legyen, indítsa el a kérdőív-ütemezést.</span><span class="sxs-lookup"><span data-stu-id="6a259-144">Start the questionnaire schedule in order to make the questionnaire available for respondents to complete.</span></span>
1. <span data-ttu-id="6a259-145">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="6a259-145">Click Functions.</span></span>
2. <span data-ttu-id="6a259-146">Kattintson a Start elemre.</span><span class="sxs-lookup"><span data-stu-id="6a259-146">Click Start.</span></span>
3. <span data-ttu-id="6a259-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6a259-147">Click OK.</span></span>

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a><span data-ttu-id="6a259-148">Küldje el az e-mailt az elérhető kérdőívek válaszadóinak tájékoztatására.</span><span class="sxs-lookup"><span data-stu-id="6a259-148">Send the email to inform respondents of the available questionnaire.</span></span>
1. <span data-ttu-id="6a259-149">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="6a259-149">Click Functions.</span></span>
2. <span data-ttu-id="6a259-150">Kattintson az E-mail küldése elemre.</span><span class="sxs-lookup"><span data-stu-id="6a259-150">Click Send email.</span></span>
3. <span data-ttu-id="6a259-151">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="6a259-151">Click Cancel.</span></span>

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a><span data-ttu-id="6a259-152">Használjon Tervezett válaszmunkameneteket annak megfigyelésére, hogy kinek kell kitöltenie a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="6a259-152">Use Planned answer sessions to monitor who needs to complete the questionnaire.</span></span>
1. <span data-ttu-id="6a259-153">Kattintson a Tervezett válaszmunkamenetre.</span><span class="sxs-lookup"><span data-stu-id="6a259-153">Click Planned answer session.</span></span>
    * <span data-ttu-id="6a259-154">Törölje a fennmaradó tervezett munkamenet bármelyikét, amikor készen áll az ütemezett munka befejezésére.</span><span class="sxs-lookup"><span data-stu-id="6a259-154">Delete any remaining planned answer session when you're ready to end the scheduled session.</span></span>  
2. <span data-ttu-id="6a259-155">Kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="6a259-155">Click Delete.</span></span>
3. <span data-ttu-id="6a259-156">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="6a259-156">Click Yes.</span></span>
4. <span data-ttu-id="6a259-157">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="6a259-157">Close the page.</span></span>

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a><span data-ttu-id="6a259-158">Ha az összes válaszadó kitöltötte a kérdőívet és/vagy az összes fennmaradó Tervezett válaszmunkamenet törlésre került, zárja le az ütemezést.</span><span class="sxs-lookup"><span data-stu-id="6a259-158">End the schedule when all respondents have completed the questionnaire and/or all remaining Planned answer sessions have been deleted.</span></span>
1. <span data-ttu-id="6a259-159">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="6a259-159">Click Functions.</span></span>
2. <span data-ttu-id="6a259-160">Kattintson a Vége gombra.</span><span class="sxs-lookup"><span data-stu-id="6a259-160">Click End.</span></span>
3. <span data-ttu-id="6a259-161">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="6a259-161">Click OK.</span></span>


