---
title: Kérdőívek terjesztése és ütemezése
description: A cikk leírja, hogyan terjesztheti a megtervezett kérdőíveket, hogy azok csak a kijelölt személy vagy csoportok számára legyenek elérhetők.
author: andreabichsel
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd0c519cfb8af811ef733804ea1086680990df00
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790596"
---
# <a name="distribute-and-schedule-questionnaires"></a><span data-ttu-id="a1278-103">Kérdőívek terjesztése és ütemezése</span><span class="sxs-lookup"><span data-stu-id="a1278-103">Distribute and schedule questionnaires</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a1278-104">A cikk leírja, hogyan terjesztheti a megtervezett kérdőíveket, hogy azok csak a kijelölt személy vagy csoportok számára legyenek elérhetők.</span><span class="sxs-lookup"><span data-stu-id="a1278-104">This article explains how distribute the questionnaires that you design, so that they are available to the person or group of people who will complete them.</span></span> 

<span data-ttu-id="a1278-105">A kérdőívek terjesztésének több módja van:</span><span class="sxs-lookup"><span data-stu-id="a1278-105">There are multiple ways to distribute a questionnaire:</span></span>

-   <span data-ttu-id="a1278-106">Jelölje meg aktívként a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="a1278-106">Mark the questionnaire as active.</span></span> <span data-ttu-id="a1278-107">A kérdőív ezt követően elérhetővé válik minden alkalmazott számára, kivéve ha a kérdőív csoport úgy van beállítva, hogy a hozzáférés korlátozva van.</span><span class="sxs-lookup"><span data-stu-id="a1278-107">The questionnaire is then available to all employees, unless a questionnaire group is set up to restrict access to it.</span></span>
-   <span data-ttu-id="a1278-108">Rendeljen jogokat a kérdőív csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="a1278-108">Assign rights to a questionnaire group.</span></span> <span data-ttu-id="a1278-109">A kérdőív ezt követően a kiválasztott csoport minden tagja számára elérhető lesz.</span><span class="sxs-lookup"><span data-stu-id="a1278-109">The questionnaire is then available to all members of the selected group.</span></span>
-   <span data-ttu-id="a1278-110">Hozzon létre tervezett válaszmunkameneteket.</span><span class="sxs-lookup"><span data-stu-id="a1278-110">Create planned answer sessions.</span></span> <span data-ttu-id="a1278-111">A kérdőív ekkor csak egy bizonyos személy részére áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="a1278-111">The questionnaire is then available only to a particular person.</span></span>
-   <span data-ttu-id="a1278-112">Hozzon létre egy ütemezést.</span><span class="sxs-lookup"><span data-stu-id="a1278-112">Create a schedule.</span></span> <span data-ttu-id="a1278-113">A kérdőív ekkor több felhasználó számára is elérhető lehet.</span><span class="sxs-lookup"><span data-stu-id="a1278-113">The questionnaire can then be available to multiple people.</span></span>

## <a name="marking-a-questionnaire-as-active"></a><span data-ttu-id="a1278-114">Kérdőív aktívként való megjelölése</span><span class="sxs-lookup"><span data-stu-id="a1278-114">Marking a questionnaire as active</span></span>

<span data-ttu-id="a1278-115">Ha szeretné, hogy a kérdőívet minden alkalmazott kitölthesse, állítsa az **Aktív** mezőt **Igen** értékre a **Kérdőívek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="a1278-115">By setting the **Active** field to **Yes** on the **Questionnaires** page, you make the questionnaire available for all employees to complete.</span></span> <span data-ttu-id="a1278-116">A válaszadók több alkalommal is kitölthetik a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="a1278-116">Respondents can complete the questionnaire multiple times.</span></span> <span data-ttu-id="a1278-117">Ez a funkció akkor hasznos, ha azt szeretné, hogy egész évben folyamatosak legyenek a visszajelzések.</span><span class="sxs-lookup"><span data-stu-id="a1278-117">This functionality is useful if you want to gather continual feedback throughout the year.</span></span> <span data-ttu-id="a1278-118">Például létrehozhat egy kérdőívet, amelyen keresztül az alkalmazottak a menza étkezési lehetőségeivel kapcsolatban adhatnak visszajelzéseket.</span><span class="sxs-lookup"><span data-stu-id="a1278-118">For example, you can make a questionnaire that employees use to give feedback about the lunch service in the cafeteria.</span></span>

## <a name="questionnaire-groups"></a><span data-ttu-id="a1278-119">Kérdőívcsoportok</span><span class="sxs-lookup"><span data-stu-id="a1278-119">Questionnaire groups</span></span>

<span data-ttu-id="a1278-120">Létrehozhat kérdőívcsoportokat, amelyekhez beállíthatja azon lehetséges válaszadókat, akiknek a kérdőív szól.</span><span class="sxs-lookup"><span data-stu-id="a1278-120">You can set up questionnaire groups and then include the respondents that a questionnaire should be distributed to.</span></span> 

<span data-ttu-id="a1278-121">A következő oldalakról hozhat létre kérdőív csoportokat:</span><span class="sxs-lookup"><span data-stu-id="a1278-121">You can create questionnaire groups from the following pages:</span></span>

-   <span data-ttu-id="a1278-122">**Kérdőív csoportok**– Csak az egyes kérdőív csoportokban szereplő személyek tölthetik ki a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="a1278-122">**Questionnaire groups** – Only individuals in a questionnaire group can complete a selected questionnaire.</span></span> <span data-ttu-id="a1278-123">Például ha csak az alvállalkozókat szeretné megkérdezni, létrehozhat olyan kérdőív csoportokat, amelyekbe ezen specifikus válaszadókat vonhatja be.</span><span class="sxs-lookup"><span data-stu-id="a1278-123">For example, your intended audience is contractors, so you create a questionnaire group that is specific to those respondents.</span></span>
-   <span data-ttu-id="a1278-124">**Kérdőív csoportok tagjai** – Személyek adhat hozzá a kérdőív csoportokhoz.</span><span class="sxs-lookup"><span data-stu-id="a1278-124">**Questionnaire group members** – You can add people to the questionnaire groups.</span></span>

<span data-ttu-id="a1278-125">Kérdőívhez kérdőívcsoport hozzárendeléséhez a **Kérdőívek** oldalon kattintson a **Felhasználói jogok** elemre.</span><span class="sxs-lookup"><span data-stu-id="a1278-125">To assign a questionnaire group to a questionnaire, on the **Questionnaires** page, click **User rights**.</span></span> <span data-ttu-id="a1278-126">A kérdőív aktívként történő elmentése után a kérdőívcsoport tagjai kitölthetik a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="a1278-126">After the questionnaire is saved as active, the members of the questionnaire group can complete the questionnaire.</span></span> <span data-ttu-id="a1278-127">Ez a funkció akkor hasznos, ha szeretné a kérdőívet tesztelni személyek egy kiválasztott csoportján, mielőtt nagyobb csoport számára közzétenné, illetve ha egy kérdőívvel egy nagyon specifikus célközönséget szeretne megcélozni.</span><span class="sxs-lookup"><span data-stu-id="a1278-127">This functionality is helpful if you want to test a questionnaire on a select group of people before you roll it out to a larger group, or if you want to target a questionnaire to a very specific audience.</span></span>

## <a name="planned-answer-sessions-in-a-questionnaire"></a><span data-ttu-id="a1278-128">Tervezett válaszmunkamenet egy kérdőívenben</span><span class="sxs-lookup"><span data-stu-id="a1278-128">Planned answer sessions in a questionnaire</span></span>

<span data-ttu-id="a1278-129">A tervezett válaszmunkamenetek olyan kérdőívek, amelyek megtervezettek és a kijelölt válaszadóknak szólnak.</span><span class="sxs-lookup"><span data-stu-id="a1278-129">Planned answer sessions are questionnaires that you've designed and selected the respondents for.</span></span> 

> [!NOTE]
> <span data-ttu-id="a1278-130">Egy tervezett válaszadási munkamenet beállítása előtt meg kell terveznie a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="a1278-130">Before you can set up planned answer sessions, you must design a questionnaire.</span></span> 

<span data-ttu-id="a1278-131">A **Tervezett válaszmunkamenetek** képernyőn lehet létrehozni tervezett válaszmunkamenetet egy bizonyos alkalmazotthoz.</span><span class="sxs-lookup"><span data-stu-id="a1278-131">On the **Planned answer session** page, you can create a planned answer session for an individual employee.</span></span> <span data-ttu-id="a1278-132">A lapon megjelenő listában megjelenik minden tervezett kérdőív.</span><span class="sxs-lookup"><span data-stu-id="a1278-132">The list on the page displays all planned questionnaires.</span></span> 

<span data-ttu-id="a1278-133">A tervezett válaszadási munkamenetek a **Kérdőív ütemezés** oldalon is használhatók, ahol többféle személy számára alkalmas kérdőíveket lehet tervezni:</span><span class="sxs-lookup"><span data-stu-id="a1278-133">Planned answer sessions are also used on the **Questionnaire schedules** page, where you can plan questionnaires for multiple people:</span></span>

-   <span data-ttu-id="a1278-134">Alkalmazottak</span><span class="sxs-lookup"><span data-stu-id="a1278-134">Employees</span></span>
-   <span data-ttu-id="a1278-135">Tanfolyam résztvevői</span><span class="sxs-lookup"><span data-stu-id="a1278-135">Course participants</span></span>
-   <span data-ttu-id="a1278-136">Szervezeti egységek</span><span class="sxs-lookup"><span data-stu-id="a1278-136">Organizational units</span></span>

<span data-ttu-id="a1278-137">Minden egyes ember csak egyszer töltheti ki a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="a1278-137">Each person can answer the questionnaire only one time.</span></span>

## <a name="scheduling-a-questionnaire"></a><span data-ttu-id="a1278-138">Kérdőív ütemezése</span><span class="sxs-lookup"><span data-stu-id="a1278-138">Scheduling a questionnaire</span></span>

<span data-ttu-id="a1278-139">Lehetőség van több válaszadó részére is ütemezni egy kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="a1278-139">You can optionally schedule a questionnaire for multiple respondents.</span></span>

### <a name="planning-types"></a><span data-ttu-id="a1278-140">Tervezés típusai</span><span class="sxs-lookup"><span data-stu-id="a1278-140">Planning types</span></span>

<span data-ttu-id="a1278-141">A tervezési típusokra akkor van szükség, ha több válaszadó részére szeretné ütemezni a tervezett válaszadási munkameneteket.</span><span class="sxs-lookup"><span data-stu-id="a1278-141">Planning types are required if you want to schedule planned answer sessions for multiple respondents.</span></span> <span data-ttu-id="a1278-142">A tervezési típusok a kérdőív-ütemezések osztályozására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="a1278-142">Planning types are used to classify questionnaire schedules.</span></span> <span data-ttu-id="a1278-143">Például az alábbi célokból ütemezhet kérdőíveket:</span><span class="sxs-lookup"><span data-stu-id="a1278-143">For example, you can schedule questionnaires for the following purposes:</span></span>

-   <span data-ttu-id="a1278-144">Értékelés</span><span class="sxs-lookup"><span data-stu-id="a1278-144">Evaluation</span></span>
-   <span data-ttu-id="a1278-145">Felmérés</span><span class="sxs-lookup"><span data-stu-id="a1278-145">Survey</span></span>
-   <span data-ttu-id="a1278-146">Tesztelés</span><span class="sxs-lookup"><span data-stu-id="a1278-146">Testing</span></span>

<span data-ttu-id="a1278-147">A **Kérdőív-ütemezések** oldalon megadhat tervezési típusokat egy kérdőív-ütemezéshez.</span><span class="sxs-lookup"><span data-stu-id="a1278-147">You can specify planning types for a questionnaire schedule on the **Questionnaire schedules** page.</span></span>

### <a name="reference-types-for-questionnaire"></a><span data-ttu-id="a1278-148">Hivatkozástípusok kérdőívhez</span><span class="sxs-lookup"><span data-stu-id="a1278-148">Reference types for questionnaire</span></span>

<span data-ttu-id="a1278-149">Hivatkozástípusok használatával megadhat feltételeket, amelyek segítségével kijelölhet bizonyos válaszadókat a kérdőív ütemezésekor.</span><span class="sxs-lookup"><span data-stu-id="a1278-149">You can use reference types to enter criteria for the respondents that you might select when you schedule a questionnaire.</span></span> 

<span data-ttu-id="a1278-150">Használja a **Hivatkozástípusok** lapot a kérdőívekhez tartozó hivatkozási típusok beállításához.</span><span class="sxs-lookup"><span data-stu-id="a1278-150">Use the **Reference types** page to set up reference types for a questionnaire.</span></span> <span data-ttu-id="a1278-151">Minden egyes hivatkozástípus megfelel a Microsoft Dynamics 365 Finance egy adott táblázatának.</span><span class="sxs-lookup"><span data-stu-id="a1278-151">Each reference type corresponds to a table in Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="a1278-152">Kérdőív-ütemezések létrehozásakor meg lehet adni bizonyos rekordokat vagy tartományokat a táblázatban, amelyhez a kérdőívet társítani szeretné.</span><span class="sxs-lookup"><span data-stu-id="a1278-152">When you create questionnaire schedules, you can specify individual records in the table or a range of records that the questionnaire will be associated with.</span></span> 

<span data-ttu-id="a1278-153">Például ha a Tanfolyamok táblázatoz választja, megadhatja, hogy melyik tanfolyam résztvevőinek számára jelenjen meg a kérdőív.</span><span class="sxs-lookup"><span data-stu-id="a1278-153">For example, if you select the Courses table, you can decide which specific course the questionnaire will be for.</span></span> <span data-ttu-id="a1278-154">Miután beállított egy hivatkozást a Tanfolyamok táblázathoz, bizonyos mezők és gombok elérhetővé válnak a **Tanfolyamok** lapon.</span><span class="sxs-lookup"><span data-stu-id="a1278-154">When you set up a reference for the Courses table, some fields and buttons on the **Courses** page become available.</span></span>

### <a name="questionnaire-schedules"></a><span data-ttu-id="a1278-155">Kérdőív-ütemezések</span><span class="sxs-lookup"><span data-stu-id="a1278-155">Questionnaire schedules</span></span>

<span data-ttu-id="a1278-156">A kérdőív-ütemezések segítségével több tervezett válaszmunkamenetet is generálhat egy csoport számára, egy hivatkozástípus alapján.</span><span class="sxs-lookup"><span data-stu-id="a1278-156">You can use questionnaire schedules to generate multiple planned answer sessions for a group of users, based on a reference type.</span></span> <span data-ttu-id="a1278-157">Az ütemezés létrehozása a **Kérdőív-ütemezések** oldalon történik.</span><span class="sxs-lookup"><span data-stu-id="a1278-157">Create a schedule on the **Questionnaire schedules** page.</span></span> <span data-ttu-id="a1278-158">Válasszon ki egy tervezési típust az ütemezés kategorizálásához, valamint válassza ki azon hivatkozási típust, amellyel a meghatározott felhasználókat le szeretné kérdezni a rendszerből.</span><span class="sxs-lookup"><span data-stu-id="a1278-158">Select the planning type to categorize the schedule, and also select the reference type that should be used to query the system for specific users.</span></span> <span data-ttu-id="a1278-159">Például a hivatkozás típusaként a Tanfolyamok táblázatot állítja be, kiválaszthat egy adott tanfolyamot a **Hivatkozás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a1278-159">For example, if you set the reference type to the Courses table, you can select a specific course in the **Reference** field.</span></span> 

<span data-ttu-id="a1278-160">Kattintson a **Beállítás részletei** lehetőségre egy kérdőív és más feltételek kijelöléséhez.</span><span class="sxs-lookup"><span data-stu-id="a1278-160">Click **Setup details** to select the questionnaire and other criteria.</span></span> <span data-ttu-id="a1278-161">Például megadhatja az oktató nevét feltételként, ha a kérdőív az oktató teljesítményére kíváncsi.</span><span class="sxs-lookup"><span data-stu-id="a1278-161">For example, specify the instructor's name as a criterion if the questionnaire is an evaluation of the instructor.</span></span> <span data-ttu-id="a1278-162">Miután befejezte a beállítások megadását, a rendszer létrehozza a tervezett válaszadási munkamenetek azon felhasználóknak, akik szerepelnek a lekérdezésben.</span><span class="sxs-lookup"><span data-stu-id="a1278-162">After you've finished entering the setup details, the system generates planned answer sessions for the users that are included in the query.</span></span> 

<span data-ttu-id="a1278-163">Kattintson a **Tervezett válaszadási munkamenetek** lehetőségre, hogy megtekinthesse a válaszadási munkameneteket egy adott ütemezéshez.</span><span class="sxs-lookup"><span data-stu-id="a1278-163">Click **Planned answer sessions** to view the answer sessions for the schedule.</span></span> <span data-ttu-id="a1278-164">Ezt követően manuálisan további tervezett válaszadási munkameneteket is létrehozása, illetve kitörölheti azon tervezett válaszadási munkameneteket, amelyre még nem érkezett válasz.</span><span class="sxs-lookup"><span data-stu-id="a1278-164">You can then manually create additional planned answer sessions or delete planned answer sessions that haven't been answered.</span></span> 

<span data-ttu-id="a1278-165">Kattintson a **Funkciók** &gt; **Start** lehetőségre, hogy a kérdőívet elérhetővé tegye a tervezett válaszmunkamenetekhez kapcsolódó személyek számára.</span><span class="sxs-lookup"><span data-stu-id="a1278-165">Click **Functions** &gt; **Start** to make the questionnaire available to the users in related planned answer sessions.</span></span> <span data-ttu-id="a1278-166">Kattintson a **Válaszok** lehetőségre, hogy megtekinthesse a kitöltött kérdőíveket.</span><span class="sxs-lookup"><span data-stu-id="a1278-166">Click **Answers** to view the completed responses to the questionnaire.</span></span> <span data-ttu-id="a1278-167">Opcionálisan át is másolhatja egy kérdőív-ütemezés beállításait, a tervezett válaszmunkamenetek és válaszokat egy új kérdőív-ütemezésekbe.</span><span class="sxs-lookup"><span data-stu-id="a1278-167">You can optionally copy the questionnaire schedule settings, planned answer sessions, and answers to a new questionnaire schedule.</span></span>

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a><span data-ttu-id="a1278-168">Válaszadók értesítése a számukra elérhető kérdőívekről</span><span class="sxs-lookup"><span data-stu-id="a1278-168">Notifying respondents about questionnaires that are available to them</span></span>
<span data-ttu-id="a1278-169">Kérdőív terjesztésekor értesítést kell küldeni a válaszadóknak arról, hogy a kérdőív elérhető számukra.</span><span class="sxs-lookup"><span data-stu-id="a1278-169">When you distribute a questionnaire, you must notify respondents that questionnaires are available to them.</span></span> 

### <a name="notifying-respondents-about-a-planned-answer-session"></a><span data-ttu-id="a1278-170">Válaszadók értesítése egy tervezett válaszmunkamenetről</span><span class="sxs-lookup"><span data-stu-id="a1278-170">Notifying respondents about a planned answer session</span></span>

<span data-ttu-id="a1278-171">Ha tervezett válaszmunkamenetet használ, akkor közvetlenül kell értesítenie az adott személyt, például telefonon vagy e-mail üzenetben.</span><span class="sxs-lookup"><span data-stu-id="a1278-171">If you use a planned answer session, you must notify the person directly, such as by telephone or email.</span></span>

### <a name="notifying-respondents-about-a-scheduling"></a><span data-ttu-id="a1278-172">Válaszadók értesítése egy ütemezésről</span><span class="sxs-lookup"><span data-stu-id="a1278-172">Notifying respondents about a scheduling</span></span>

<span data-ttu-id="a1278-173">A **Kérdívek ütemezése** képernyőn e-mail üzenetet írhat a kérdőívhez társított válaszadóknak.</span><span class="sxs-lookup"><span data-stu-id="a1278-173">Use the **Questionnaire schedules** page to prepare and send email to all respondents who are assigned to the questionnaire.</span></span> <span data-ttu-id="a1278-174">Írja be az e-mail szöveget az **E-mail üzenet az alkalmazotti önkiszolgáló szolgáltatás számára** lapon. Az ütemezés elindítását követően kattintson a **Funkciók** &gt; **E-mail üzenet küldése** lehetőségre a válaszadók számára küldendő e-mail létrehozásához és elküldéséhez.</span><span class="sxs-lookup"><span data-stu-id="a1278-174">Enter the email text on the **E-mail for employee self service** tab. After the schedule has been started, click **Functions** &gt; **Send e-mail** to generate and send the email to the respondents.</span></span> <span data-ttu-id="a1278-175">A válaszadók ezután bejelentkezhetnek a webhelyre, és kitölthetik a kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="a1278-175">Respondents can then sign in to the website and complete the questionnaire.</span></span> 

> [!NOTE]
> <span data-ttu-id="a1278-176">Az e-mail funkció használata előtt a rendszergazdának meg kell adnia az e-mail-beállításokat az **E-mail-paraméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="a1278-176">Before you can use the email functionality, your IT administrator must enter the email settings on the **E-mail parameters** page.</span></span>

## <a name="ending-a-scheduled-questionnaire"></a><span data-ttu-id="a1278-177">Ütemezett kérdőív lezárása</span><span class="sxs-lookup"><span data-stu-id="a1278-177">Ending a scheduled questionnaire</span></span>

<span data-ttu-id="a1278-178">Ha az összes válaszadó befejezte a kiadott válaszmunkamenetet, akkor be lehet fejezni az ütemezett kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="a1278-178">You can end a scheduled questionnaire after all respondents have completed their assigned answer sessions.</span></span> <span data-ttu-id="a1278-179">Az ütemezett kérdőív befejezése után annak beállításait már nem lehet az új ütemezésekbe másolni.</span><span class="sxs-lookup"><span data-stu-id="a1278-179">After a scheduled questionnaire is ended, you can't copy its settings to a new schedule.</span></span> 

> [!NOTE]
>   <span data-ttu-id="a1278-180">Ha annak ellenére szeretné befejezni az ütemezést, hogy egy vagy több válaszadó még nem töltötte ki a kérdőívet, először törölje a szóban forgó válaszadókat a **Tervezett válaszmunkamenet** képernyő listájáról.</span><span class="sxs-lookup"><span data-stu-id="a1278-180">If one or more respondents haven't completed the questionnaire, but you still want to end the scheduling, you must first delete those respondents from the list on the **Planned answer session** page.</span></span> <span data-ttu-id="a1278-181">Ezután befejezhető az ütemezés.</span><span class="sxs-lookup"><span data-stu-id="a1278-181">You can then end the schedule.</span></span>

## <a name="completing-questionnaires"></a><span data-ttu-id="a1278-182">Kérdőív kitöltése</span><span class="sxs-lookup"><span data-stu-id="a1278-182">Completing questionnaires</span></span>

<span data-ttu-id="a1278-183">Miután megtervezte és kiosztotta a kérdőívet, az csak a kijelölt válaszadók számára lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="a1278-183">After you've designed and distributed a questionnaire, the questionnaire can be completed by selected respondents.</span></span> <span data-ttu-id="a1278-184">A rendelkezésre álló kérdőíveket két helyen töltheti ki:</span><span class="sxs-lookup"><span data-stu-id="a1278-184">You can complete the questionnaires that are available to you from two locations:</span></span>

-   <span data-ttu-id="a1278-185">Kattintson a navigációs ablak **Kérdőívek** &gt; **Terjesztés** &gt; **Kérdőív kitöltése** lehetőségére.</span><span class="sxs-lookup"><span data-stu-id="a1278-185">In the navigation pane, click **Questionnaires** &gt; **Distribute** &gt; **Complete a questionnaire**.</span></span>
-   <span data-ttu-id="a1278-186">Kattintson az Alkalmazotti önkiszolgáló rendszer **Kitöltendő kérdőívek** lehetőségére.</span><span class="sxs-lookup"><span data-stu-id="a1278-186">In Employee self-service, click **Questionnaires to complete**.</span></span>

<span data-ttu-id="a1278-187">A kérdőívek közzétehetők csak adott felhasználók vagy felhasználócsoportok számára is, illetve a hálózat minden tagja számára.</span><span class="sxs-lookup"><span data-stu-id="a1278-187">Questionnaires can made be available to specific users or groups of users, or to all users in a network.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]