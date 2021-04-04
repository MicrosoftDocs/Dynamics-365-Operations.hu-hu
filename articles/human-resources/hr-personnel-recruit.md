---
title: Állásjelöltek toborzása
description: Ez a témakör bemutatja, hogyan lehet jelölteket toborozni a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6aca285133495dfe023dfd18bdeb050aabcafee6
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478284"
---
# <a name="recruit-job-candidates"></a><span data-ttu-id="d7e93-103">Állásjelöltek toborzása</span><span class="sxs-lookup"><span data-stu-id="d7e93-103">Recruit job candidates</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d7e93-104">A Dynamics 365 Human Resources segít a toborzási kérelmek kezelésében.</span><span class="sxs-lookup"><span data-stu-id="d7e93-104">Dynamics 365 Human Resources helps you to manage recruiting requests.</span></span> <span data-ttu-id="d7e93-105">Segít abban is, hogy zökkenőmentesen vezessen át állásjelölteket az alkalmazottak közé.</span><span class="sxs-lookup"><span data-stu-id="d7e93-105">It also helps you seamlessly transition job candidates to employees.</span></span> <span data-ttu-id="d7e93-106">Ha a szervezet külön toborzási alkalmazást használ, a toborzási folyamat a következő lépéseket foglalhatja magában:</span><span class="sxs-lookup"><span data-stu-id="d7e93-106">If your organization uses a separate recruiting application, your recruiting process might include the following steps:</span></span>

- <span data-ttu-id="d7e93-107">Adja meg toborzási kérelmét a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d7e93-107">Enter your recruiting request in Human Resources.</span></span>
- <span data-ttu-id="d7e93-108">Fogadja a toborzási kérelmeket a toborzó alkalmazásból a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d7e93-108">Receive candidate referrals in Human Resources from the recruiting application.</span></span>
- <span data-ttu-id="d7e93-109">A jelöltek jóváhagyási folyamatát végezze el a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d7e93-109">Complete the candidate approval process in Human Resources.</span></span>

<span data-ttu-id="d7e93-110">Ha nem használ külön toborzási alkalmazást, manuálisan is kezelheti a jelölteket az Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d7e93-110">If you aren't using a separate recruiting application, you can also manually manage candidates in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="d7e93-111">Ha Ön rendszergazda vagy fejlesztő, és integrálni szeretné az Human Resources alkalmazást egy külső toborzó alkalmazással, olvassa el a [Dataverse integráció konfigurálása](hr-admin-integration-common-data-service.md) és a [Dataverse virtuális táblák konfigurálása](hr-admin-integration-common-data-service-virtual-entities.md) című témakört</span><span class="sxs-lookup"><span data-stu-id="d7e93-111">If you're an admin or developer and want to integrate Human Resources with a third-party recruiting application, see [Configure Dataverse integration](hr-admin-integration-common-data-service.md) and [Configure Dataverse virtual tables](hr-admin-integration-common-data-service-virtual-entities.md)</span></span>
>
> <span data-ttu-id="d7e93-112">Integrálható toborzó alkalmazásokat találhat az [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics) felületén is.</span><span class="sxs-lookup"><span data-stu-id="d7e93-112">You can also find recruiting integration apps on [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span></span>
>
> <span data-ttu-id="d7e93-113">A LinkedIn Talent Hub szolgáltatással való integráció előzetes verziójának kipróbálásához lásd: [Integrálás a LinkedIn Talent Hub-szolgáltatással](hr-admin-integration-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="d7e93-113">To try out our preview feature for integrating with LinkedIn Talent Hub, see [Integrate with LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span></span>

## <a name="enable-recruiting-requests"></a><span data-ttu-id="d7e93-114">Toborzási kérelmek engedélyezése</span><span class="sxs-lookup"><span data-stu-id="d7e93-114">Enable recruiting requests</span></span>

<span data-ttu-id="d7e93-115">Ha toborzási kérelmeket szeretne benyújtani a Human Resources alkalmazásban, először engedélyeznie kell a funkciót a **Human Resources megosztott paraméterei** lehetőségben.</span><span class="sxs-lookup"><span data-stu-id="d7e93-115">If you want to submit recruiting requests in Human Resources, you must first enable the functionality in **Human resources shared parameters**.</span></span>

1. <span data-ttu-id="d7e93-116">A **Személyzetkezelés** munkaterületen válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-116">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="d7e93-117">A **Beállítás** alatt válassza a **Humán erőforrás megosztott paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-117">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="d7e93-118">A **Toborzás** lap **TOBORZÁS** részében állítsa a **Toborzási kérelmek engedélyezése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="d7e93-118">On the **Recruitment** tab, under **RECRUITING**, set **Enable recruiting requests** to **Yes**.</span></span>

## <a name="add-a-recruiting-request-location"></a><span data-ttu-id="d7e93-119">Toborzási kérelem helyének hozzáadása</span><span class="sxs-lookup"><span data-stu-id="d7e93-119">Add a recruiting request location</span></span>

<span data-ttu-id="d7e93-120">Ha a szervezetnek több helyszíne van, hozzáadhatja őket, így a kérelmezők kiválaszthatják azt a helyet, ahol az új belépő dolgozik majd.</span><span class="sxs-lookup"><span data-stu-id="d7e93-120">If your organization has multiple locations, you can add them so requestors can select a location where the new recruit will be working.</span></span> <span data-ttu-id="d7e93-121">A hely szerepelni fog az álláshirdetésben.</span><span class="sxs-lookup"><span data-stu-id="d7e93-121">The location will be included in the job posting.</span></span>

1. <span data-ttu-id="d7e93-122">A keresősávban adja meg a **toborzási kérelem helye** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="d7e93-122">In the search bar, enter **recruiting request location**.</span></span>

2. <span data-ttu-id="d7e93-123">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-123">Select **New**.</span></span>

3. <span data-ttu-id="d7e93-124">A **Toborzási kérelem helye** mezőben adja meg a hely nevét.</span><span class="sxs-lookup"><span data-stu-id="d7e93-124">In the **Recruiting request location** field, enter the location name.</span></span>

   ![Toborzási kérelem helyének hozzáadása](./media/hr-recruit-0a-add-location.png)

4. <span data-ttu-id="d7e93-126">A **Leírás** mezőben adja meg a hely leírását.</span><span class="sxs-lookup"><span data-stu-id="d7e93-126">In the **Description**, enter a description for the location.</span></span>

5. <span data-ttu-id="d7e93-127">A **Hely** alatt válassz a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-127">Under **Location**, select **Add**.</span></span> <span data-ttu-id="d7e93-128">Ha megjelenik az **Új cím** előugró ablak, adja meg a hely címét.</span><span class="sxs-lookup"><span data-stu-id="d7e93-128">If the **New address** popout appears, enter the address for the location.</span></span>

   ![Cím megadása](./media/hr-recruit-0b-address.png)

6. <span data-ttu-id="d7e93-130">A **Kapcsolattartási adatok** alatt adja meg a hely kapcsolattartójának adatait.</span><span class="sxs-lookup"><span data-stu-id="d7e93-130">Under **Contact information**, enter the information for the location's contact.</span></span>

7. <span data-ttu-id="d7e93-131">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-131">Select **Save**.</span></span>

## <a name="add-a-recruiting-request"></a><span data-ttu-id="d7e93-132">Toborzási kérelem hozzáadása</span><span class="sxs-lookup"><span data-stu-id="d7e93-132">Add a recruiting request</span></span>

<span data-ttu-id="d7e93-133">A vezetők toborzási kérelmeket nyújthatnak be a Human Resources alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="d7e93-133">Managers can submit recruiting requests in Human Resources.</span></span> <span data-ttu-id="d7e93-134">Ha külön toborzási alkalmazást használ, a lépések végrehajtása toborzási kérelmet küld, és elindítja a toborzási folyamatot az adott alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="d7e93-134">If you use a separate recruiting application, completing these steps will send a recruiting request and start the recruiting process in that application.</span></span> <span data-ttu-id="d7e93-135">Ellenkező esetben hajtsa végre ezt az eljárást a munkafolyamat elindításához a saját belső toborzási folyamatához.</span><span class="sxs-lookup"><span data-stu-id="d7e93-135">Otherwise, complete this procedure to begin the workflow for your own internal recruiting process.</span></span>

1. <span data-ttu-id="d7e93-136">Válassza az **Alkalmazotti önkiszolgáló rendszer** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-136">Select **Employee self service**.</span></span>

2. <span data-ttu-id="d7e93-137">Válassza ki a **Saját csapat** lapot.</span><span class="sxs-lookup"><span data-stu-id="d7e93-137">Select the **My team** tab.</span></span>

3. <span data-ttu-id="d7e93-138">Válassza a **Toborzás kérése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-138">Select  **Request to recruit**.</span></span>

   ![Toborzási kérelem indítása](./media/hr-recruit-1-request-to-recruit.png)

4. <span data-ttu-id="d7e93-140">Töltse ki a **Leírás**, **Munka** és a **Becsült kezdési dátum** mezőket.</span><span class="sxs-lookup"><span data-stu-id="d7e93-140">Complete the **Description**, **Job**, and **Estimated start date** fields.</span></span>

   ![A toborzási kérelem befejezése](./media/hr-recruit-2-request-to-recruit.png)

5. <span data-ttu-id="d7e93-142">Válassza **Folytatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="d7e93-142">Select **Continue**.</span></span> <span data-ttu-id="d7e93-143">Megjelenik a toborzási kérelem a pozíciójához.</span><span class="sxs-lookup"><span data-stu-id="d7e93-143">The recruiting request for your position appears.</span></span>

6. <span data-ttu-id="d7e93-144">Az **Általános** részben válasszon ki egy toborzót a **Toborzó** legördülő menüből, majd válasszon ki egy helyet a **Toborzási kérelem helye** legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="d7e93-144">Under **General**, select a recruiter from the **Recruiter** dropdown, and then select a location from the **Recruiting request location** dropdown.</span></span>

7. <span data-ttu-id="d7e93-145">A **Munka** részben szükség szerint módosítsa az adatokat, majd válassza a **Részletek létrehozása a munkából** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-145">Under **Job**, change any information as needed, and then select **Create details from job**.</span></span>

   ![Részletek létrehozása a feladatból](./media/hr-recruit-3-create-details-from-job.png)

   <span data-ttu-id="d7e93-147">A toborzási kérelem többi része ki lesz töltve a megadott munka alapértelmezett adataival.</span><span class="sxs-lookup"><span data-stu-id="d7e93-147">The rest of the recruiting request will populate with the default information for the job you entered.</span></span>

8. <span data-ttu-id="d7e93-148">A **Külső leírás** részben adjon meg egy a szervezeten kívülről megtekinthető leírást.</span><span class="sxs-lookup"><span data-stu-id="d7e93-148">Under **External description**, enter an external-facing job description.</span></span>

9. <span data-ttu-id="d7e93-149">A **Pozíciók** részben válassza a **Hozzáadás** lehetőséget, majd válassza ki a toborzási kérelemhez tartozó beosztást.</span><span class="sxs-lookup"><span data-stu-id="d7e93-149">Under **Positions**, select **Add**, and then select a position for this recruiting request.</span></span>

   ![Pozíció hozzáadása](./media/hr-recruit-4-select-position.png)

10. <span data-ttu-id="d7e93-151">A **Szakértelmek** részben válassza a **Hozzáadás** lehetőséget, majd válasszon ki egy szakértelmet.</span><span class="sxs-lookup"><span data-stu-id="d7e93-151">Under **Skills**, select **Add**, and then select a skill.</span></span>

11. <span data-ttu-id="d7e93-152">Az **Oktatási követelmények** csoportban válassza a **Hozzáadás** lehetőséget, majd válasszon értékeket a **Végzettség** és az **Végzettség szintje** legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="d7e93-152">Under **Educational requirements**, select **Add**, and then select values from the **Education** and **Level of education** dropdowns.</span></span>

   ![Végzettségi követelmények hozzáadása](./media/hr-recruit-5-select-educational-requirements.png)

12. <span data-ttu-id="d7e93-154">A **Megjegyzés** részben szükség szerint fűzzön hozzá megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="d7e93-154">Under **Comment**, add comments as necessary.</span></span>

13. <span data-ttu-id="d7e93-155">A **Kompenzáció** részben válasszon egy szintet a **Szint** legördülő menüből, majd szükség szerint módosítsa az **Alacsony küszöb**, az **Ellenőrzőpont** és a **Magas küszöb** értéket.</span><span class="sxs-lookup"><span data-stu-id="d7e93-155">Under **Compensation**, select a level from the **Level** dropdown, and then adjust **Low threshold**, **Control point**, and **High threshold** as necessary.</span></span>

14. <span data-ttu-id="d7e93-156">Amikor a toborzási kérelem elkészült, és készen áll a toborzási folyamat elindítására, válassza az **Aktiválás** lehetőséget a menüsorban.</span><span class="sxs-lookup"><span data-stu-id="d7e93-156">When your recruiting request is complete and you're ready to start the recruiting process, select **Activate** in the menu bar.</span></span>

   ![Toborzási kérelem aktiválása](./media/hr-recruit-6-activate-recruit-request.png)

15. <span data-ttu-id="d7e93-158">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-158">Select **Save**.</span></span>

## <a name="view-and-edit-your-recruiting-requests"></a><span data-ttu-id="d7e93-159">A toborzási kérelmek megtekintése és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="d7e93-159">View and edit your recruiting requests</span></span>

<span data-ttu-id="d7e93-160">Ha Ön vezető, és szeretné megtekinteni a saját kéréseit:</span><span class="sxs-lookup"><span data-stu-id="d7e93-160">If you're a manager and want to view your own requests:</span></span>

1. <span data-ttu-id="d7e93-161">Válassza az **Alkalmazotti önkiszolgáló rendszer** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-161">Select **Employee self service**.</span></span>

2. <span data-ttu-id="d7e93-162">Válassza ki a **Saját csapat** lapot.</span><span class="sxs-lookup"><span data-stu-id="d7e93-162">Select the **My team** tab.</span></span>

3. <span data-ttu-id="d7e93-163">A **Saját csapat adatai** területen válassza a **Toborzási kérelmek** lapot.</span><span class="sxs-lookup"><span data-stu-id="d7e93-163">Under **My team information**, select the **Recruiting requests** tab.</span></span>

   ![Toborzási kérelmek lap kiválasztása](./media/hr-recruit-7-recruiting-requests.png)

4. <span data-ttu-id="d7e93-165">A toborzási kérelem megtekintéséhez vagy szerkesztéséhez jelölje ki azt a rácsban.</span><span class="sxs-lookup"><span data-stu-id="d7e93-165">To view or edit a recruiting request, select it in the grid.</span></span>

<span data-ttu-id="d7e93-166">Ha Ön HR-szakember, és szeretné megtekinteni az összes toborzási kérelmet:</span><span class="sxs-lookup"><span data-stu-id="d7e93-166">If you're an HR pro and want to view all recruiting requests:</span></span>

1. <span data-ttu-id="d7e93-167">Válassza a **Személyzetkezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-167">Select **Personnel management**.</span></span>

2. <span data-ttu-id="d7e93-168">Válassza a **Toborzási kérelmek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-168">Select **Recruiting requests**.</span></span>

   ![Toborzási kérelmek megtekintése a Személyzetkezelésben](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. <span data-ttu-id="d7e93-170">A toborzási kérelem megtekintéséhez vagy szerkesztéséhez jelölje ki azt a rácsban.</span><span class="sxs-lookup"><span data-stu-id="d7e93-170">To view or edit a recruiting request, select it in the grid.</span></span>

## <a name="add-or-edit-a-candidate-profile"></a><span data-ttu-id="d7e93-171">Jelöltprofil hozzáadása vagy szerkesztése</span><span class="sxs-lookup"><span data-stu-id="d7e93-171">Add or edit a candidate profile</span></span>

<span data-ttu-id="d7e93-172">Ha a szervezet integrált egy másik alkalmazást a toborzási kérelmek kezeléséhez, a toborzási kérelmek továbbítva vannak az adott alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="d7e93-172">If your organization has integrated with another application to manage recruiting requests, recruiting requests are forwarded to that application.</span></span> <span data-ttu-id="d7e93-173">A toborzási alkalmazás ezután visszaküldi a pályázók adatait a Human Resourcesnak.</span><span class="sxs-lookup"><span data-stu-id="d7e93-173">The recruiting application then sends candidate information back to Human Resources.</span></span> <span data-ttu-id="d7e93-174">Máskülönben követheti a saját belső toborzási folyamatait, és manuálisan adhatja meg a jelöltadatokat.</span><span class="sxs-lookup"><span data-stu-id="d7e93-174">Otherwise, you can follow your own internal recruiting processes and enter candidate information manually.</span></span>

1. <span data-ttu-id="d7e93-175">Válassza a **Személyzetkezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-175">Select **Personnel management**.</span></span>

2. <span data-ttu-id="d7e93-176">Válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-176">Select **Links**.</span></span>

3. <span data-ttu-id="d7e93-177">A **Toborzás** csoportban válassza a **Jelöltek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-177">Under **Recruiting**, select **Candidates**.</span></span>

   ![Jelentkezők megtekintése](./media/hr-recruit-9-candidates.png)

4. <span data-ttu-id="d7e93-179">Jelölt hozzáadásához válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-179">To add a candidate, select **New**.</span></span> <span data-ttu-id="d7e93-180">Meglévő jelentkező szerkesztéséhez jelölje ki a jelentkezőt a listában, majd válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-180">To edit an existing candidate, select the candidate from the list and then select **Edit**.</span></span> <span data-ttu-id="d7e93-181">Megjelenik a jelölt profilja.</span><span class="sxs-lookup"><span data-stu-id="d7e93-181">The candidate profile appears.</span></span>

5. <span data-ttu-id="d7e93-182">A **Jelölt összegzése** részben szükség szerint adja meg vagy szerkessze a pályázó adatait.</span><span class="sxs-lookup"><span data-stu-id="d7e93-182">Under **Candidate summary**, enter or edit the candidate information as necessary.</span></span>

6. <span data-ttu-id="d7e93-183">A **Toborzási kérelem** alatt válassza ki azt a toborzási kérelmet, amelyhez a jelöltet kapcsolni szeretné.</span><span class="sxs-lookup"><span data-stu-id="d7e93-183">Under **Recruiting request**, select a recruiting request to link the candidate to.</span></span> <span data-ttu-id="d7e93-184">Ezután töltse ki a **Becsült kezdési dátum**, **Felvételi vezető**, **Beosztás** és **Leírás** mezőket igény szerint.</span><span class="sxs-lookup"><span data-stu-id="d7e93-184">Then complete the **Estimated start date**, **Hiring manager**, **Position**, and **Description fields** as appropriate.</span></span>

   ![Toborzási kérelemre mutató hivatkozás](./media/hr-recruit-10-link-to-recruiting-request.png)

7. <span data-ttu-id="d7e93-186">Töltse ki az összes információt a következő területeken, amelyeket fel szeretne venni a jelölt rekordjába:</span><span class="sxs-lookup"><span data-stu-id="d7e93-186">Complete all the information in the following areas that you want to include in the candidate's record:</span></span>
   - <span data-ttu-id="d7e93-187">**Megjegyzések**</span><span class="sxs-lookup"><span data-stu-id="d7e93-187">**Comments**</span></span>
   - <span data-ttu-id="d7e93-188">**Szakmai tapasztalat**</span><span class="sxs-lookup"><span data-stu-id="d7e93-188">**Professional experience**</span></span>
   - <span data-ttu-id="d7e93-189">**Kapcsolattartó adatai**</span><span class="sxs-lookup"><span data-stu-id="d7e93-189">**Contact information**</span></span>
   - <span data-ttu-id="d7e93-190">**Végzettség**</span><span class="sxs-lookup"><span data-stu-id="d7e93-190">**Education**</span></span>
   - <span data-ttu-id="d7e93-191">**Szakértelem**</span><span class="sxs-lookup"><span data-stu-id="d7e93-191">**Skills**</span></span>
   - <span data-ttu-id="d7e93-192">**Diplomák**</span><span class="sxs-lookup"><span data-stu-id="d7e93-192">**Certificates**</span></span>
   - <span data-ttu-id="d7e93-193">**Szűrések**</span><span class="sxs-lookup"><span data-stu-id="d7e93-193">**Screenings**</span></span>

8. <span data-ttu-id="d7e93-194">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-194">Select **Save**.</span></span>

## <a name="hire-a-candidate"></a><span data-ttu-id="d7e93-195">Jelentkező felvétele</span><span class="sxs-lookup"><span data-stu-id="d7e93-195">Hire a candidate</span></span>

<span data-ttu-id="d7e93-196">Ha készen áll egy jelölt felvételére, kövesse ezt az eljárást a jelölt alkalmazottá való átalakításához.</span><span class="sxs-lookup"><span data-stu-id="d7e93-196">When you're ready to hire a candidate, follow this procedure to transition the candidate to an employee.</span></span>

1. <span data-ttu-id="d7e93-197">A jelölt űrlapon válassza a **Felvétel** l ehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-197">On the candidate form, select **Hire**.</span></span>

   ![Jelentkező felvétele](./media/hr-recruit-11-hire.png)

2. <span data-ttu-id="d7e93-199">Az **Új dolgozó felvétele** képernyő **Részletek** csoportban töltse ki az összes mezőt.</span><span class="sxs-lookup"><span data-stu-id="d7e93-199">On the **Hire new worker** form, under **Details**, complete all the fields.</span></span>

   ![Új felvétel adatainak megadása](./media/hr-recruit-12-hire-new-worker.png)

3. <span data-ttu-id="d7e93-201">A **Pozíció részletei** részben szükség szerint ellenőrizze és módosítsa az adatokat.</span><span class="sxs-lookup"><span data-stu-id="d7e93-201">Under **Position details**, verify and change information as necessary.</span></span>

4. <span data-ttu-id="d7e93-202">Az **Előkészítési ellenőrzőlisták** alatt válassza ki az alkalmazotthoz tartozó előkészítési ellenőrzőlistákat.</span><span class="sxs-lookup"><span data-stu-id="d7e93-202">Under **Onboarding checklists**, select the relevant onboarding checklists for this employee.</span></span>

5. <span data-ttu-id="d7e93-203">Válassza a **Folytatás** lehetőséget az alkalmazotti rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="d7e93-203">Select **Continue** to create the employee record.</span></span>

   >[!NOTE]
   ><span data-ttu-id="d7e93-204">A szervezet munkafolyamataitól függően a jelölt rekordja további jóváhagyási lépéseken is átmehet, mielőtt alkalmazotti rekorddá válna.</span><span class="sxs-lookup"><span data-stu-id="d7e93-204">Depending on your organization's workflows, the candidate record may go through additional approval steps before becoming an employee record.</span></span>

## <a name="decide-not-to-hire-a-candidate"></a><span data-ttu-id="d7e93-205">Úgy dönt, hogy nem vesz fel jelöltet</span><span class="sxs-lookup"><span data-stu-id="d7e93-205">Decide not to hire a candidate</span></span>

<span data-ttu-id="d7e93-206">Ha úgy dönt, hogy nem vesz fel jelöltet, kövesse ezt az eljárást, hogy távolítsa el őket az ellenőrzési folyamatból.</span><span class="sxs-lookup"><span data-stu-id="d7e93-206">If you decide not to hire a candidate, follow this procedure to remove them from the vetting process.</span></span> 

1. <span data-ttu-id="d7e93-207">A jelölt űrlapon válassza a **Nincs felvétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-207">On the candidate form, select **Do not hire**.</span></span>

   ![Nem vesz fel jelentkezőt](./media/hr-recruit-13-do-not-hire.png)

2. <span data-ttu-id="d7e93-209">Válasszon ki egy **Okkódot**, és adja meg a megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="d7e93-209">Select a **Reason code** and include any comments.</span></span>

3. <span data-ttu-id="d7e93-210">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-210">Select **OK**.</span></span>

## <a name="dismiss-a-candidate"></a><span data-ttu-id="d7e93-211">Jelölt elvetése</span><span class="sxs-lookup"><span data-stu-id="d7e93-211">Dismiss a candidate</span></span>

<span data-ttu-id="d7e93-212">Szükség esetén a felvétel után elbocsáthat egy jelöltet.</span><span class="sxs-lookup"><span data-stu-id="d7e93-212">If needed, you can dismiss a candidate after hiring them.</span></span> <span data-ttu-id="d7e93-213">Előfordulhat például, hogy egy jelölt elutasítja az ajánlatot, vagy nem jelenik meg az első napon.</span><span class="sxs-lookup"><span data-stu-id="d7e93-213">For example, a candidate might reject your offer or not show up on their first day.</span></span>

- <span data-ttu-id="d7e93-214">A jelölt űrlapon válassza a **Jelölt elvetése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d7e93-214">On the candidate form, select **Dismiss candidate**.</span></span>

  ![Jelölt elutasítása](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a><span data-ttu-id="d7e93-216">Lásd még</span><span class="sxs-lookup"><span data-stu-id="d7e93-216">See also</span></span>

[<span data-ttu-id="d7e93-217">Dataverse virtuális táblák konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d7e93-217">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="d7e93-218">Munkaerő-szervezés</span><span class="sxs-lookup"><span data-stu-id="d7e93-218">Organize your workforce</span></span>](hr-personnel-departments-jobs-positions.md)<br>
[<span data-ttu-id="d7e93-219">Feladat összetevőinek beállítása</span><span class="sxs-lookup"><span data-stu-id="d7e93-219">Set up the components of a job</span></span>](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
