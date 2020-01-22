---
title: Kérdőívek terjesztése és ütemezése.
description: A témakör leírja, hogyan terjesztheti a megtervezett kérdőíveket, hogy azok csak a kijelölt személy vagy csoportok számára legyenek elérhetők.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc392c965a0d3bc308e0396263e84ecf1e713491
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898363"
---
# <a name="distribute-and-schedule-questionnaires"></a><span data-ttu-id="37ffa-103">Kérdőívek terjesztése és ütemezése.</span><span class="sxs-lookup"><span data-stu-id="37ffa-103">Distribute and schedule questionnaires</span></span>

<span data-ttu-id="37ffa-104">A témakör leírja, hogyan terjesztheti a megtervezett kérdőíveket, hogy azok csak a kijelölt személy vagy csoportok számára legyenek elérhetők.</span><span class="sxs-lookup"><span data-stu-id="37ffa-104">This topic explains how distribute the questionnaires that you design, so that they are available to the person or group of people who will complete them.</span></span> 

<span data-ttu-id="37ffa-105">A kérdőívek terjesztésének több módja van:</span><span class="sxs-lookup"><span data-stu-id="37ffa-105">There are multiple ways to distribute a questionnaire:</span></span>

-   <span data-ttu-id="37ffa-106">Jelölje meg aktívként a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="37ffa-106">Mark the questionnaire as active.</span></span> <span data-ttu-id="37ffa-107">A kérdőív ezt követően elérhetővé válik minden alkalmazott számára, kivéve ha a kérdőív csoport úgy van beállítva, hogy a hozzáférés korlátozva van.</span><span class="sxs-lookup"><span data-stu-id="37ffa-107">The questionnaire is then available to all employees, unless a questionnaire group is set up to restrict access to it.</span></span>
-   <span data-ttu-id="37ffa-108">Rendeljen jogokat a kérdőív csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="37ffa-108">Assign rights to a questionnaire group.</span></span> <span data-ttu-id="37ffa-109">A kérdőív ezt követően a kiválasztott csoport minden tagja számára elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="37ffa-109">The questionnaire is then available to all members of the selected group.</span></span>
-   <span data-ttu-id="37ffa-110">Hozzon létre tervezett válaszmunkameneteket.</span><span class="sxs-lookup"><span data-stu-id="37ffa-110">Create planned answer sessions.</span></span> <span data-ttu-id="37ffa-111">A kérdőív ekkor csak egy bizonyos személy részére áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="37ffa-111">The questionnaire is then available only to a particular person.</span></span>
-   <span data-ttu-id="37ffa-112">Hozzon létre egy ütemezést.</span><span class="sxs-lookup"><span data-stu-id="37ffa-112">Create a schedule.</span></span> <span data-ttu-id="37ffa-113">A kérdőív ekkor több felhasználó számára is elérhető lehet.</span><span class="sxs-lookup"><span data-stu-id="37ffa-113">The questionnaire can then be available to multiple people.</span></span>

## <a name="marking-a-questionnaire-as-active"></a><span data-ttu-id="37ffa-114">Kérdőív aktívként való megjelölése</span><span class="sxs-lookup"><span data-stu-id="37ffa-114">Marking a questionnaire as active</span></span>
<span data-ttu-id="37ffa-115">Ha szeretné, hogy a kérdőívet minden alkalmazott kitölthesse, állítsa az **Aktív** mezőt **Igen** értékre a **Kérdőívek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="37ffa-115">By setting the **Active** field to **Yes** on the **Questionnaires** page, you make the questionnaire available for all employees to complete.</span></span> <span data-ttu-id="37ffa-116">A válaszadók több alkalommal is kitölthetik a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="37ffa-116">Respondents can complete the questionnaire multiple times.</span></span> <span data-ttu-id="37ffa-117">Ez a funkció akkor hasznos, ha azt szeretné, hogy egész évben folyamatosak legyenek a visszajelzések.</span><span class="sxs-lookup"><span data-stu-id="37ffa-117">This functionality is useful if you want to gather continual feedback throughout the year.</span></span> <span data-ttu-id="37ffa-118">Például létrehozhat egy kérdőívet, amelyen keresztül az alkalmazottak a menza étkezési lehetőségeivel kapcsolatban adhatnak visszajelzéseket.</span><span class="sxs-lookup"><span data-stu-id="37ffa-118">For example, you can make a questionnaire that employees use to give feedback about the lunch service in the cafeteria.</span></span>

## <a name="questionnaire-groups"></a><span data-ttu-id="37ffa-119">Kérdőívcsoportok</span><span class="sxs-lookup"><span data-stu-id="37ffa-119">Questionnaire groups</span></span>
<span data-ttu-id="37ffa-120">Létrehozhat kérdőívcsoportokat, amelyekhez beállíthatja azon lehetséges válaszadókat, akiknek a kérdőív szól.</span><span class="sxs-lookup"><span data-stu-id="37ffa-120">You can set up questionnaire groups and then include the respondents that a questionnaire should be distributed to.</span></span> 

<span data-ttu-id="37ffa-121">A következő oldalakról hozhat létre kérdőív csoportokat:</span><span class="sxs-lookup"><span data-stu-id="37ffa-121">You can create questionnaire groups from the following pages:</span></span>

-   <span data-ttu-id="37ffa-122">**Kérdőív csoportok**– Csak az egyes kérdőív csoportokban szereplő személyek tölthetik ki a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="37ffa-122">**Questionnaire groups** – Only individuals in a questionnaire group can complete a selected questionnaire.</span></span> <span data-ttu-id="37ffa-123">Például ha csak az alvállalkozókat szeretné megkérdezni, létrehozhat olyan kérdőív csoportokat, amelyekbe ezen specifikus válaszadókat vonhatja be.</span><span class="sxs-lookup"><span data-stu-id="37ffa-123">For example, your intended audience is contractors, so you create a questionnaire group that is specific to those respondents.</span></span>
-   <span data-ttu-id="37ffa-124">**Kérdőív csoportok tagjai** – Személyek adhat hozzá a kérdőív csoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="37ffa-124">**Questionnaire group members** – You can add people to the questionnaire groups.</span></span>

<span data-ttu-id="37ffa-125">Kérdőívhez kérdőívcsoport hozzárendeléséhez a **Kérdőívek** oldalon kattintson a **Felhasználói jogok** elemre.</span><span class="sxs-lookup"><span data-stu-id="37ffa-125">To assign a questionnaire group to a questionnaire, on the **Questionnaires** page, click **User rights**.</span></span> <span data-ttu-id="37ffa-126">A kérdőív aktívként történő elmentése után a kérdőívcsoport tagjai kitölthetik a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="37ffa-126">After the questionnaire is saved as active, the members of the questionnaire group can complete the questionnaire.</span></span> <span data-ttu-id="37ffa-127">Ez a funkció akkor hasznos, ha szeretné a kérdőívet tesztelni személyek egy kiválasztott csoportján, mielőtt nagyobb csoport számára közzétenné, illetve ha egy kérdőívvel egy nagyon specifikus célközönséget szeretne megcélozni.</span><span class="sxs-lookup"><span data-stu-id="37ffa-127">This functionality is helpful if you want to test a questionnaire on a select group of people before you roll it out to a larger group, or if you want to target a questionnaire to a very specific audience.</span></span>

## <a name="planned-answer-sessions-in-a-questionnaire"></a><span data-ttu-id="37ffa-128">Tervezett válaszmunkamenet egy kérdőívenben</span><span class="sxs-lookup"><span data-stu-id="37ffa-128">Planned answer sessions in a questionnaire</span></span>
<span data-ttu-id="37ffa-129">A tervezett válaszmunkamenetek olyan kérdőívek, amelyek megtervezettek és a kijelölt válaszadóknak szólnak.</span><span class="sxs-lookup"><span data-stu-id="37ffa-129">Planned answer sessions are questionnaires that you've designed and selected the respondents for.</span></span> 

> [!NOTE]
>   <span data-ttu-id="37ffa-130">Egy tervezett válaszadási munkamenet beállítása előtt meg kell terveznie a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="37ffa-130">Before you can set up planned answer sessions, you must design a questionnaire.</span></span> 

<span data-ttu-id="37ffa-131">A **Tervezett válaszmunkamenetek** képernyőn lehet létrehozni tervezett válaszmunkamenetet egy bizonyos alkalmazotthoz.</span><span class="sxs-lookup"><span data-stu-id="37ffa-131">On the **Planned answer session** page, you can create a planned answer session for an individual employee.</span></span> <span data-ttu-id="37ffa-132">A lapon megjelenő listában megjelenik minden tervezett kérdőív.</span><span class="sxs-lookup"><span data-stu-id="37ffa-132">The list on the page displays all planned questionnaires.</span></span> 

<span data-ttu-id="37ffa-133">A tervezett válaszadási munkamenetek a **Kérdőív ütemezés** oldalon is használhatók, ahol többféle személy számára alkalmas kérdőíveket lehet tervezni:</span><span class="sxs-lookup"><span data-stu-id="37ffa-133">Planned answer sessions are also used on the **Questionnaire schedules** page, where you can plan questionnaires for multiple people:</span></span>

-   <span data-ttu-id="37ffa-134">Alkalmazottak</span><span class="sxs-lookup"><span data-stu-id="37ffa-134">Employees</span></span>
-   <span data-ttu-id="37ffa-135">Tanfolyam résztvevői</span><span class="sxs-lookup"><span data-stu-id="37ffa-135">Course participants</span></span>
-   <span data-ttu-id="37ffa-136">Szervezeti egységek</span><span class="sxs-lookup"><span data-stu-id="37ffa-136">Organizational units</span></span>

<span data-ttu-id="37ffa-137">Minden egyes ember csak egyszer töltheti ki a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="37ffa-137">Each person can answer the questionnaire only one time.</span></span>

## <a name="scheduling-a-questionnaire"></a><span data-ttu-id="37ffa-138">Kérdőív ütemezése</span><span class="sxs-lookup"><span data-stu-id="37ffa-138">Scheduling a questionnaire</span></span>
<span data-ttu-id="37ffa-139">Lehetőség van több válaszadó részére is ütemezni egy kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="37ffa-139">You can optionally schedule a questionnaire for multiple respondents.</span></span>

### <a name="planning-types"></a><span data-ttu-id="37ffa-140">Tervezés típusai</span><span class="sxs-lookup"><span data-stu-id="37ffa-140">Planning types</span></span>

<span data-ttu-id="37ffa-141">A tervezési típusokra akkor van szükség, ha több válaszadó részére szeretné ütemezni a tervezett válaszadási munkameneteket.</span><span class="sxs-lookup"><span data-stu-id="37ffa-141">Planning types are required if you want to schedule planned answer sessions for multiple respondents.</span></span> <span data-ttu-id="37ffa-142">A tervezési típusok a kérdőív-ütemezések osztályozására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="37ffa-142">Planning types are used to classify questionnaire schedules.</span></span> <span data-ttu-id="37ffa-143">Például az alábbi célokból ütemezhet kérdőíveket:</span><span class="sxs-lookup"><span data-stu-id="37ffa-143">For example, you can schedule questionnaires for the following purposes:</span></span>

-   <span data-ttu-id="37ffa-144">Értékelés</span><span class="sxs-lookup"><span data-stu-id="37ffa-144">Evaluation</span></span>
-   <span data-ttu-id="37ffa-145">Felmérés</span><span class="sxs-lookup"><span data-stu-id="37ffa-145">Survey</span></span>
-   <span data-ttu-id="37ffa-146">Tesztelés</span><span class="sxs-lookup"><span data-stu-id="37ffa-146">Testing</span></span>

<span data-ttu-id="37ffa-147">A **Kérdőív-ütemezések** oldalon megadhat tervezési típusokat egy kérdőív-ütemezéshez.</span><span class="sxs-lookup"><span data-stu-id="37ffa-147">You can specify planning types for a questionnaire schedule on the **Questionnaire schedules** page.</span></span>

### <a name="reference-types-for-questionnaire"></a><span data-ttu-id="37ffa-148">Hivatkozástípusok kérdőívhez</span><span class="sxs-lookup"><span data-stu-id="37ffa-148">Reference types for questionnaire</span></span>

<span data-ttu-id="37ffa-149">Hivatkozástípusok használatával megadhat feltételeket, amelyek segítségével kijelölhet bizonyos válaszadókat a kérdőív ütemezésekor.</span><span class="sxs-lookup"><span data-stu-id="37ffa-149">You can use reference types to enter criteria for the respondents that you might select when you schedule a questionnaire.</span></span> 

<span data-ttu-id="37ffa-150">Használja a **Hivatkozástípusok** lapot a kérdőívekhez tartozó hivatkozási típusok beállításához.</span><span class="sxs-lookup"><span data-stu-id="37ffa-150">Use the **Reference types** page to set up reference types for a questionnaire.</span></span> <span data-ttu-id="37ffa-151">Minden egyes hivatkozástípus megfelel a Microsoft Dynamics 365 Finance egy adott táblázatának.</span><span class="sxs-lookup"><span data-stu-id="37ffa-151">Each reference type corresponds to a table in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="37ffa-152">Kérdőív-ütemezések létrehozásakor meg lehet adni bizonyos rekordokat vagy tartományokat a táblázatban, amelyhez a kérdőívet társítani szeretné.</span><span class="sxs-lookup"><span data-stu-id="37ffa-152">When you create questionnaire schedules, you can specify individual records in the table or a range of records that the questionnaire will be associated with.</span></span> 

<span data-ttu-id="37ffa-153">Például ha a Tanfolyamok táblázatoz választja, megadhatja, hogy melyik tanfolyam résztvevőinek számára jelenjen meg a kérdőív.</span><span class="sxs-lookup"><span data-stu-id="37ffa-153">For example, if you select the Courses table, you can decide which specific course the questionnaire will be for.</span></span> <span data-ttu-id="37ffa-154">Miután beállított egy hivatkozást a Tanfolyamok táblázathoz, bizonyos mezők és gombok elérhetővé válnak a **Tanfolyamok** lapon.</span><span class="sxs-lookup"><span data-stu-id="37ffa-154">When you set up a reference for the Courses table, some fields and buttons on the **Courses** page become available.</span></span>

### <a name="questionnaire-schedules"></a><span data-ttu-id="37ffa-155">Kérdőív-ütemezések</span><span class="sxs-lookup"><span data-stu-id="37ffa-155">Questionnaire schedules</span></span>

<span data-ttu-id="37ffa-156">A kérdőív-ütemezések segítségével több tervezett válaszmunkamenetet is generálhat egy csoport számára, egy hivatkozástípus alapján.</span><span class="sxs-lookup"><span data-stu-id="37ffa-156">You can use questionnaire schedules to generate multiple planned answer sessions for a group of users, based on a reference type.</span></span> <span data-ttu-id="37ffa-157">Az ütemezés létrehozása a **Kérdőív-ütemezések** oldalon történik.</span><span class="sxs-lookup"><span data-stu-id="37ffa-157">Create a schedule on the **Questionnaire schedules** page.</span></span> <span data-ttu-id="37ffa-158">Válasszon ki egy tervezési típust az ütemezés kategorizálásához, valamint válassza ki azon hivatkozási típust, amellyel a meghatározott felhasználókat le szeretné kérdezni a rendszerből.</span><span class="sxs-lookup"><span data-stu-id="37ffa-158">Select the planning type to categorize the schedule, and also select the reference type that should be used to query the system for specific users.</span></span> <span data-ttu-id="37ffa-159">Például a hivatkozás típusaként a Tanfolyamok táblázatot állítja be, kiválaszthat egy adott tanfolyamot a **Hivatkozás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="37ffa-159">For example, if you set the reference type to the Courses table, you can select a specific course in the **Reference** field.</span></span> 

<span data-ttu-id="37ffa-160">Kattintson a **Beállítás részletei** lehetőségre egy kérdőív és más feltételek kijelöléséhez.</span><span class="sxs-lookup"><span data-stu-id="37ffa-160">Click **Setup details** to select the questionnaire and other criteria.</span></span> <span data-ttu-id="37ffa-161">Például megadhatja az oktató nevét feltételként, ha a kérdőív az oktató teljesítményére kíváncsi.</span><span class="sxs-lookup"><span data-stu-id="37ffa-161">For example, specify the instructor's name as a criterion if the questionnaire is an evaluation of the instructor.</span></span> <span data-ttu-id="37ffa-162">Miután befejezte a beállítások megadását, a rendszer létrehozza a tervezett válaszadási munkamenetek azon felhasználóknak, akik szerepelnek a lekérdezésben.</span><span class="sxs-lookup"><span data-stu-id="37ffa-162">After you've finished entering the setup details, the system generates planned answer sessions for the users that are included in the query.</span></span> 

<span data-ttu-id="37ffa-163">Kattintson a **Tervezett válaszadási munkamenetek** lehetőségre, hogy megtekinthesse a válaszadási munkameneteket egy adott ütemezéshez.</span><span class="sxs-lookup"><span data-stu-id="37ffa-163">Click **Planned answer sessions** to view the answer sessions for the schedule.</span></span> <span data-ttu-id="37ffa-164">Ezt követően manuálisan további tervezett válaszadási munkameneteket is létrehozása, illetve kitörölheti azon tervezett válaszadási munkameneteket, amelyre még nem érkezett válasz.</span><span class="sxs-lookup"><span data-stu-id="37ffa-164">You can then manually create additional planned answer sessions or delete planned answer sessions that haven't been answered.</span></span> 

<span data-ttu-id="37ffa-165">Kattintson a **Funkciók** &gt; **Start** lehetőségre, hogy a kérdőívet elérhetővé tegye a tervezett válaszmunkamenetekhez kapcsolódó személyek számára.</span><span class="sxs-lookup"><span data-stu-id="37ffa-165">Click **Functions** &gt; **Start** to make the questionnaire available to the users in related planned answer sessions.</span></span> <span data-ttu-id="37ffa-166">Kattintson a **Válaszok** lehetőségre, hogy megtekinthesse a kitöltött kérdőíveket.</span><span class="sxs-lookup"><span data-stu-id="37ffa-166">Click **Answers** to view the completed responses to the questionnaire.</span></span> <span data-ttu-id="37ffa-167">Opcionálisan át is másolhatja egy kérdőív-ütemezés beállításait, a tervezett válaszmunkamenetek és válaszokat egy új kérdőív-ütemezésekbe.</span><span class="sxs-lookup"><span data-stu-id="37ffa-167">You can optionally copy the questionnaire schedule settings, planned answer sessions, and answers to a new questionnaire schedule.</span></span>

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a><span data-ttu-id="37ffa-168">Válaszadók értesítése a számukra elérhető kérdőívekről</span><span class="sxs-lookup"><span data-stu-id="37ffa-168">Notifying respondents about questionnaires that are available to them</span></span>
<span data-ttu-id="37ffa-169">Kérdőív terjesztésekor értesítést kell küldeni a válaszadóknak arról, hogy a kérdőív elérhető számukra.</span><span class="sxs-lookup"><span data-stu-id="37ffa-169">When you distribute a questionnaire, you must notify respondents that questionnaires are available to them.</span></span> 

### <a name="notifying-respondents-about-a-planned-answer-session"></a><span data-ttu-id="37ffa-170">Válaszadók értesítése egy tervezett válaszmunkamenetről</span><span class="sxs-lookup"><span data-stu-id="37ffa-170">Notifying respondents about a planned answer session</span></span>

<span data-ttu-id="37ffa-171">Ha tervezett válaszmunkamenetet használ, akkor közvetlenül kell értesítenie az adott személyt, például telefonon vagy e-mail üzenetben.</span><span class="sxs-lookup"><span data-stu-id="37ffa-171">If you use a planned answer session, you must notify the person directly, such as by telephone or email.</span></span>

### <a name="notifying-respondents-about-a-scheduling"></a><span data-ttu-id="37ffa-172">Válaszadók értesítése egy ütemezésről</span><span class="sxs-lookup"><span data-stu-id="37ffa-172">Notifying respondents about a scheduling</span></span>

<span data-ttu-id="37ffa-173">A **Kérdívek ütemezése** képernyőn e-mail üzenetet írhat a kérdőívhez társított válaszadóknak.</span><span class="sxs-lookup"><span data-stu-id="37ffa-173">Use the **Questionnaire schedules** page to prepare and send email to all respondents who are assigned to the questionnaire.</span></span> <span data-ttu-id="37ffa-174">Írja be az e-mail szöveget az **E-mail üzenet az alkalmazotti önkiszolgáló szolgáltatás számára** lapon. Az ütemezés elindítását követően kattintson a **Funkciók** &gt; **E-mail üzenet küldése** lehetőségre a válaszadók számára küldendő e-mail létrehozásához és elküldéséhez.</span><span class="sxs-lookup"><span data-stu-id="37ffa-174">Enter the email text on the **E-mail for employee self service** tab. After the schedule has been started, click **Functions** &gt; **Send e-mail** to generate and send the email to the respondents.</span></span> <span data-ttu-id="37ffa-175">A válaszadók ezután bejelentkezhetnek a webhelyre, és kitölthetik a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="37ffa-175">Respondents can then sign in to the website and complete the questionnaire.</span></span> 

> [!NOTE]
>   <span data-ttu-id="37ffa-176">Az e-mail funkció használata előtt a rendszergazdának meg kell adnia az e-mail-beállításokat az **E-mail-paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="37ffa-176">Before you can use the email functionality, your IT administrator must enter the email settings on the **E-mail parameters** page.</span></span>

## <a name="ending-a-scheduled-questionnaire"></a><span data-ttu-id="37ffa-177">Ütemezett kérdőív lezárása</span><span class="sxs-lookup"><span data-stu-id="37ffa-177">Ending a scheduled questionnaire</span></span>
<span data-ttu-id="37ffa-178">Ha az összes válaszadó befejezte a kiadott válaszmunkamenetet, akkor be lehet fejezni az ütemezett kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="37ffa-178">You can end a scheduled questionnaire after all respondents have completed their assigned answer sessions.</span></span> <span data-ttu-id="37ffa-179">Az ütemezett kérdőív befejezése után annak beállításait már nem lehet az új ütemezésekbe másolni.</span><span class="sxs-lookup"><span data-stu-id="37ffa-179">After a scheduled questionnaire is ended, you can't copy its settings to a new schedule.</span></span> 

> [!NOTE]
>   <span data-ttu-id="37ffa-180">Ha annak ellenére szeretné befejezni az ütemezést, hogy egy vagy több válaszadó még nem töltötte ki a kérdőívet, először törölje a szóban forgó válaszadókat a **Tervezett válaszmunkamenet** képernyő listájáról.</span><span class="sxs-lookup"><span data-stu-id="37ffa-180">If one or more respondents haven't completed the questionnaire, but you still want to end the scheduling, you must first delete those respondents from the list on the **Planned answer session** page.</span></span> <span data-ttu-id="37ffa-181">Ezután befejezhető az ütemezés.</span><span class="sxs-lookup"><span data-stu-id="37ffa-181">You can then end the schedule.</span></span>

## <a name="completing-questionnaires"></a><span data-ttu-id="37ffa-182">Kérdőív kitöltése</span><span class="sxs-lookup"><span data-stu-id="37ffa-182">Completing questionnaires</span></span>
<span data-ttu-id="37ffa-183">Miután megtervezte és kiosztotta a kérdőívet, az csak a kijelölt válaszadók számára lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="37ffa-183">After you've designed and distributed a questionnaire, the questionnaire can be completed by selected respondents.</span></span> <span data-ttu-id="37ffa-184">A rendelkezésre álló kérdőíveket két helyen töltheti ki:</span><span class="sxs-lookup"><span data-stu-id="37ffa-184">You can complete the questionnaires that are available to you from two locations:</span></span>

-   <span data-ttu-id="37ffa-185">Kattintson a navigációs ablak **Kérdőívek** &gt; **Terjesztés** &gt; **Kérdőív kitöltése** lehetőségére.</span><span class="sxs-lookup"><span data-stu-id="37ffa-185">In the navigation pane, click **Questionnaires** &gt; **Distribute** &gt; **Complete a questionnaire**.</span></span>
-   <span data-ttu-id="37ffa-186">Kattintson az Alkalmazotti önkiszolgáló rendszer **Kitöltendő kérdőívek** lehetőségére.</span><span class="sxs-lookup"><span data-stu-id="37ffa-186">In Employee self-service, click **Questionnaires to complete**.</span></span>

<span data-ttu-id="37ffa-187">A kérdőívek közzétehetők csak adott felhasználók vagy felhasználócsoportok számára is, illetve a hálózat minden tagja számára.</span><span class="sxs-lookup"><span data-stu-id="37ffa-187">Questionnaires can made be available to specific users or groups of users, or to all users in a network.</span></span>

<a name="additional-resources"></a><span data-ttu-id="37ffa-188">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="37ffa-188">Additional resources</span></span>
--------

[<span data-ttu-id="37ffa-189">Kérdőívek tervezése</span><span class="sxs-lookup"><span data-stu-id="37ffa-189">Design questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="37ffa-190">Kérdőívek</span><span class="sxs-lookup"><span data-stu-id="37ffa-190">Questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="37ffa-191">A kérdőívek eredményeinek megtekintése és kiértékelése</span><span class="sxs-lookup"><span data-stu-id="37ffa-191">View and evaluate the results of questionnaires</span></span>](evaluate-questionnaire-results.md)


