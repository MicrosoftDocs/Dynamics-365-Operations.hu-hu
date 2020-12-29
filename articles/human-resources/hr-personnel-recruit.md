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
ms.openlocfilehash: 9a35abcb8a2f6aa8031c8d84a44c2a8ad93883ac
ms.sourcegitcommit: 0354ca7e566fbd2eb0aabdd40000d4ac5c44ea78
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/04/2020
ms.locfileid: "4669171"
---
# <a name="recruit-job-candidates"></a><span data-ttu-id="c25dc-103">Állásjelöltek toborzása</span><span class="sxs-lookup"><span data-stu-id="c25dc-103">Recruit job candidates</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="c25dc-104">A Dynamics 365 Human Resources segít a toborzási kérelmek kezelésében.</span><span class="sxs-lookup"><span data-stu-id="c25dc-104">Dynamics 365 Human Resources helps you to manage recruiting requests.</span></span> <span data-ttu-id="c25dc-105">Segít abban is, hogy zökkenőmentesen vezessen át állásjelölteket az alkalmazottak közé.</span><span class="sxs-lookup"><span data-stu-id="c25dc-105">It also helps you seamlessly transition job candidates to employees.</span></span> <span data-ttu-id="c25dc-106">Ha a szervezet külön toborzási alkalmazást használ, a toborzási folyamat a következő lépéseket foglalhatja magában:</span><span class="sxs-lookup"><span data-stu-id="c25dc-106">If your organization uses a separate recruiting application, your recruiting process might include the following steps:</span></span>

- <span data-ttu-id="c25dc-107">Adja meg toborzási kérelmét a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c25dc-107">Enter your recruiting request in Human Resources.</span></span>
- <span data-ttu-id="c25dc-108">Fogadja a toborzási kérelmeket a toborzó alkalmazásból a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c25dc-108">Receive candidate referrals in Human Resources from the recruiting application.</span></span>
- <span data-ttu-id="c25dc-109">A jelöltek jóváhagyási folyamatát végezze el a Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c25dc-109">Complete the candidate approval process in Human Resources.</span></span>

<span data-ttu-id="c25dc-110">Ha nem használ külön toborzási alkalmazást, manuálisan is kezelheti a jelölteket az Human Resources alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c25dc-110">If you aren't using a separate recruiting application, you can also manually manage candidates in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="c25dc-111">Ha Ön rendszergazda vagy fejlesztő, és integrálni szeretné az Human Resources alkalmazást egy külső toborzó alkalmazással, olvassa el a [Common Data Service integráció konfigurálása](hr-admin-integration-common-data-service.md) és a [Common Data Service virtuális entitások konfigurálása](hr-admin-integration-common-data-service-virtual-entities.md) című témakört</span><span class="sxs-lookup"><span data-stu-id="c25dc-111">If you're an admin or developer and want to integrate Human Resources with a third-party recruiting application, see [Configure Common Data Service integration](hr-admin-integration-common-data-service.md) and [Configure Common Data Service virtual entities](hr-admin-integration-common-data-service-virtual-entities.md)</span></span>
>
> <span data-ttu-id="c25dc-112">Integrálható toborzó alkalmazásokat találhat az [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics) felületén is.</span><span class="sxs-lookup"><span data-stu-id="c25dc-112">You can also find recruiting integration apps on [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span></span>
>
> <span data-ttu-id="c25dc-113">A LinkedIn Talent Hub szolgáltatással való integráció előzetes verziójának kipróbálásához lásd: [Integrálás a LinkedIn Talent Hub-szolgáltatással](hr-admin-integration-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="c25dc-113">To try out our preview feature for integrating with LinkedIn Talent Hub, see [Integrate with LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span></span>

## <a name="enable-recruiting-requests"></a><span data-ttu-id="c25dc-114">Toborzási kérelmek engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c25dc-114">Enable recruiting requests</span></span>

<span data-ttu-id="c25dc-115">Ha toborzási kérelmeket szeretne benyújtani a Human Resources alkalmazásban szolgáltatásban, először engedélyeznie kell a funkciót az **Human Resources paramétereiben**.</span><span class="sxs-lookup"><span data-stu-id="c25dc-115">If you want to submit recruiting requests in Human Resources, you must first enable the functionality in **Human resources parameters**.</span></span>

1. <span data-ttu-id="c25dc-116">A **Személyzetkezelés** munkaterületen válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-116">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="c25dc-117">A **Beállítás** alatt válassza az **Emberierőforrás-paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-117">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="c25dc-118">Az **Általános** lap **TOBORZÁS** részében állítsa a **Toborzási kérelmek engedélyezése** beállítás **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="c25dc-118">On the **General** tab, under **RECRUITING**, set **Enable recruiting requests** to **Yes**.</span></span>

   ![Toborzási kérelmek engedélyezése](./media/hr-recruit-0-enable-requests.png)

## <a name="add-a-recruiting-request-location"></a><span data-ttu-id="c25dc-120">Toborzási kérelem helyének hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c25dc-120">Add a recruiting request location</span></span>

<span data-ttu-id="c25dc-121">Ha a szervezetnek több helyszíne van, hozzáadhatja őket, így a kérelmezők kiválaszthatják azt a helyet, ahol az új belépő dolgozik majd.</span><span class="sxs-lookup"><span data-stu-id="c25dc-121">If your organization has multiple locations, you can add them so requestors can select a location where the new recruit will be working.</span></span> <span data-ttu-id="c25dc-122">A hely szerepelni fog az álláshirdetésben.</span><span class="sxs-lookup"><span data-stu-id="c25dc-122">The location will be included in the job posting.</span></span>

1. <span data-ttu-id="c25dc-123">A keresősávban adja meg a **toborzási kérelem helye** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="c25dc-123">In the search bar, enter **recruiting request location**.</span></span>

2. <span data-ttu-id="c25dc-124">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-124">Select **New**.</span></span>

3. <span data-ttu-id="c25dc-125">A **Toborzási kérelem helye** mezőben adja meg a hely nevét.</span><span class="sxs-lookup"><span data-stu-id="c25dc-125">In the **Recruiting request location** field, enter the location name.</span></span>

   ![Toborzási kérelem helyének hozzáadása](./media/hr-recruit-0a-add-location.png)

4. <span data-ttu-id="c25dc-127">A **Leírás** mezőben adja meg a hely leírását.</span><span class="sxs-lookup"><span data-stu-id="c25dc-127">In the **Description**, enter a description for the location.</span></span>

5. <span data-ttu-id="c25dc-128">A **Hely** alatt válassz a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-128">Under **Location**, select **Add**.</span></span> <span data-ttu-id="c25dc-129">Ha megjelenik az **Új cím** előugró ablak, adja meg a hely címét.</span><span class="sxs-lookup"><span data-stu-id="c25dc-129">If the **New address** popout appears, enter the address for the location.</span></span>

   ![Cím megadása](./media/hr-recruit-0b-address.png)

6. <span data-ttu-id="c25dc-131">A **Kapcsolattartási adatok** alatt adja meg a hely kapcsolattartójának adatait.</span><span class="sxs-lookup"><span data-stu-id="c25dc-131">Under **Contact information**, enter the information for the location's contact.</span></span>

7. <span data-ttu-id="c25dc-132">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-132">Select **Save**.</span></span>

## <a name="add-a-recruiting-request"></a><span data-ttu-id="c25dc-133">Toborzási kérelem hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c25dc-133">Add a recruiting request</span></span>

<span data-ttu-id="c25dc-134">A vezetők toborzási kérelmeket nyújthatnak be a Human Resources alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="c25dc-134">Managers can submit recruiting requests in Human Resources.</span></span> <span data-ttu-id="c25dc-135">Ha külön toborzási alkalmazást használ, a lépések végrehajtása toborzási kérelmet küld, és elindítja a toborzási folyamatot az adott alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c25dc-135">If you use a separate recruiting application, completing these steps will send a recruiting request and start the recruiting process in that application.</span></span> <span data-ttu-id="c25dc-136">Ellenkező esetben hajtsa végre ezt az eljárást a munkafolyamat elindításához a saját belső toborzási folyamatához.</span><span class="sxs-lookup"><span data-stu-id="c25dc-136">Otherwise, complete this procedure to begin the workflow for your own internal recruiting process.</span></span>

1. <span data-ttu-id="c25dc-137">Válassza az **Alkalmazotti önkiszolgáló rendszer** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-137">Select **Employee self service**.</span></span>

2. <span data-ttu-id="c25dc-138">Válassza ki a **Saját csapat** lapot.</span><span class="sxs-lookup"><span data-stu-id="c25dc-138">Select the **My team** tab.</span></span>

3. <span data-ttu-id="c25dc-139">Válassza a **Toborzás kérése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-139">Select  **Request to recruit**.</span></span>

   ![Toborzási kérelem indítása](./media/hr-recruit-1-request-to-recruit.png)

4. <span data-ttu-id="c25dc-141">Töltse ki a **Leírás**, **Munka** és a **Becsült kezdési dátum** mezőket.</span><span class="sxs-lookup"><span data-stu-id="c25dc-141">Complete the **Description**, **Job**, and **Estimated start date** fields.</span></span>

   ![A toborzási kérelem befejezése](./media/hr-recruit-2-request-to-recruit.png)

5. <span data-ttu-id="c25dc-143">Válassza **Folytatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="c25dc-143">Select **Continue**.</span></span> <span data-ttu-id="c25dc-144">Megjelenik a toborzási kérelem a pozíciójához.</span><span class="sxs-lookup"><span data-stu-id="c25dc-144">The recruiting request for your position appears.</span></span>

6. <span data-ttu-id="c25dc-145">Az **Általános** részben válasszon ki egy toborzót a **Toborzó** legördülő menüből, majd válasszon ki egy helyet a **Toborzási kérelem helye** legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="c25dc-145">Under **General**, select a recruiter from the **Recruiter** dropdown, and then select a location from the **Recruiting request location** dropdown.</span></span>

7. <span data-ttu-id="c25dc-146">A **Munka** részben szükség szerint módosítsa az adatokat, majd válassza a **Részletek létrehozása a munkából** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-146">Under **Job**, change any information as needed, and then select **Create details from job**.</span></span>

   ![Részletek létrehozása a feladatból](./media/hr-recruit-3-create-details-from-job.png)

   <span data-ttu-id="c25dc-148">A toborzási kérelem többi része ki lesz töltve a megadott munka alapértelmezett adataival.</span><span class="sxs-lookup"><span data-stu-id="c25dc-148">The rest of the recruiting request will populate with the default information for the job you entered.</span></span>

8. <span data-ttu-id="c25dc-149">A **Külső leírás** részben adjon meg egy a szervezeten kívülről megtekinthető leírást.</span><span class="sxs-lookup"><span data-stu-id="c25dc-149">Under **External description**, enter an external-facing job description.</span></span>

9. <span data-ttu-id="c25dc-150">A **Pozíciók** részben válassza a **Hozzáadás** lehetőséget, majd válassza ki a toborzási kérelemhez tartozó beosztást.</span><span class="sxs-lookup"><span data-stu-id="c25dc-150">Under **Positions**, select **Add**, and then select a position for this recruiting request.</span></span>

   ![Pozíció hozzáadása](./media/hr-recruit-4-select-position.png)

10. <span data-ttu-id="c25dc-152">A **Szakértelmek** részben válassza a **Hozzáadás** lehetőséget, majd válasszon ki egy szakértelmet.</span><span class="sxs-lookup"><span data-stu-id="c25dc-152">Under **Skills**, select **Add**, and then select a skill.</span></span>

11. <span data-ttu-id="c25dc-153">Az **Oktatási követelmények** csoportban válassza a **Hozzáadás** lehetőséget, majd válasszon értékeket a **Végzettség** és az **Végzettség szintje** legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="c25dc-153">Under **Educational requirements**, select **Add**, and then select values from the **Education** and **Level of education** dropdowns.</span></span>

   ![Végzettségi követelmények hozzáadása](./media/hr-recruit-5-select-educational-requirements.png)

12. <span data-ttu-id="c25dc-155">A **Megjegyzés** részben szükség szerint fűzzön hozzá megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="c25dc-155">Under **Comment**, add comments as necessary.</span></span>

13. <span data-ttu-id="c25dc-156">A **Kompenzáció** részben válasszon egy szintet a **Szint** legördülő menüből, majd szükség szerint módosítsa az **Alacsony küszöb**, az **Ellenőrzőpont** és a **Magas küszöb** értéket.</span><span class="sxs-lookup"><span data-stu-id="c25dc-156">Under **Compensation**, select a level from the **Level** dropdown, and then adjust **Low threshold**, **Control point**, and **High threshold** as necessary.</span></span>

14. <span data-ttu-id="c25dc-157">Amikor a toborzási kérelem elkészült, és készen áll a toborzási folyamat elindítására, válassza az **Aktiválás** lehetőséget a menüsorban.</span><span class="sxs-lookup"><span data-stu-id="c25dc-157">When your recruiting request is complete and you're ready to start the recruiting process, select **Activate** in the menu bar.</span></span>

   ![Toborzási kérelem aktiválása](./media/hr-recruit-6-activate-recruit-request.png)

15. <span data-ttu-id="c25dc-159">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-159">Select **Save**.</span></span>

## <a name="view-and-edit-your-recruiting-requests"></a><span data-ttu-id="c25dc-160">A toborzási kérelmek megtekintése és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="c25dc-160">View and edit your recruiting requests</span></span>

<span data-ttu-id="c25dc-161">Ha Ön vezető, és szeretné megtekinteni a saját kéréseit:</span><span class="sxs-lookup"><span data-stu-id="c25dc-161">If you're a manager and want to view your own requests:</span></span>

1. <span data-ttu-id="c25dc-162">Válassza az **Alkalmazotti önkiszolgáló rendszer** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-162">Select **Employee self service**.</span></span>

2. <span data-ttu-id="c25dc-163">Válassza ki a **Saját csapat** lapot.</span><span class="sxs-lookup"><span data-stu-id="c25dc-163">Select the **My team** tab.</span></span>

3. <span data-ttu-id="c25dc-164">A **Saját csapat adatai** területen válassza a **Toborzási kérelmek** lapot.</span><span class="sxs-lookup"><span data-stu-id="c25dc-164">Under **My team information**, select the **Recruiting requests** tab.</span></span>

   ![Toborzási kérelmek lap kiválasztása](./media/hr-recruit-7-recruiting-requests.png)

4. <span data-ttu-id="c25dc-166">A toborzási kérelem megtekintéséhez vagy szerkesztéséhez jelölje ki azt a rácsban.</span><span class="sxs-lookup"><span data-stu-id="c25dc-166">To view or edit a recruiting request, select it in the grid.</span></span>

<span data-ttu-id="c25dc-167">Ha Ön HR-szakember, és szeretné megtekinteni az összes toborzási kérelmet:</span><span class="sxs-lookup"><span data-stu-id="c25dc-167">If you're an HR pro and want to view all recruiting requests:</span></span>

1. <span data-ttu-id="c25dc-168">Válassza a **Személyzetkezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-168">Select **Personnel management**.</span></span>

2. <span data-ttu-id="c25dc-169">Válassza a **Toborzási kérelmek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-169">Select **Recruiting requests**.</span></span>

   ![Toborzási kérelmek megtekintése a Személyzetkezelésben](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. <span data-ttu-id="c25dc-171">A toborzási kérelem megtekintéséhez vagy szerkesztéséhez jelölje ki azt a rácsban.</span><span class="sxs-lookup"><span data-stu-id="c25dc-171">To view or edit a recruiting request, select it in the grid.</span></span>

## <a name="add-or-edit-a-candidate-profile"></a><span data-ttu-id="c25dc-172">Jelöltprofil hozzáadása vagy szerkesztése</span><span class="sxs-lookup"><span data-stu-id="c25dc-172">Add or edit a candidate profile</span></span>

<span data-ttu-id="c25dc-173">Ha a szervezet integrált egy másik alkalmazást a toborzási kérelmek kezeléséhez, a toborzási kérelmek továbbítva vannak az adott alkalmazáshoz.</span><span class="sxs-lookup"><span data-stu-id="c25dc-173">If your organization has integrated with another application to manage recruiting requests, recruiting requests are forwarded to that application.</span></span> <span data-ttu-id="c25dc-174">A toborzási alkalmazás ezután visszaküldi a pályázók adatait a Human Resourcesnak.</span><span class="sxs-lookup"><span data-stu-id="c25dc-174">The recruiting application then sends candidate information back to Human Resources.</span></span> <span data-ttu-id="c25dc-175">Máskülönben követheti a saját belső toborzási folyamatait, és manuálisan adhatja meg a jelöltadatokat.</span><span class="sxs-lookup"><span data-stu-id="c25dc-175">Otherwise, you can follow your own internal recruiting processes and enter candidate information manually.</span></span>

1. <span data-ttu-id="c25dc-176">Válassza a **Személyzetkezelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-176">Select **Personnel management**.</span></span>

2. <span data-ttu-id="c25dc-177">Válassza a **Hivatkozások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-177">Select **Links**.</span></span>

3. <span data-ttu-id="c25dc-178">A **Toborzás** csoportban válassza a **Jelöltek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-178">Under **Recruiting**, select **Candidates**.</span></span>

   ![Jelentkezők megtekintése](./media/hr-recruit-9-candidates.png)

4. <span data-ttu-id="c25dc-180">Jelölt hozzáadásához válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-180">To add a candidate, select **New**.</span></span> <span data-ttu-id="c25dc-181">Meglévő jelentkező szerkesztéséhez jelölje ki a jelentkezőt a listában, majd válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-181">To edit an existing candidate, select the candidate from the list and then select **Edit**.</span></span> <span data-ttu-id="c25dc-182">Megjelenik a jelölt profilja.</span><span class="sxs-lookup"><span data-stu-id="c25dc-182">The candidate profile appears.</span></span>

5. <span data-ttu-id="c25dc-183">A **Jelölt összegzése** részben szükség szerint adja meg vagy szerkessze a pályázó adatait.</span><span class="sxs-lookup"><span data-stu-id="c25dc-183">Under **Candidate summary**, enter or edit the candidate information as necessary.</span></span>

6. <span data-ttu-id="c25dc-184">A **Toborzási kérelem** alatt válassza ki azt a toborzási kérelmet, amelyhez a jelöltet kapcsolni szeretné.</span><span class="sxs-lookup"><span data-stu-id="c25dc-184">Under **Recruiting request**, select a recruiting request to link the candidate to.</span></span> <span data-ttu-id="c25dc-185">Ezután töltse ki a **Becsült kezdési dátum**, **Felvételi vezető**, **Beosztás** és **Leírás** mezőket igény szerint.</span><span class="sxs-lookup"><span data-stu-id="c25dc-185">Then complete the **Estimated start date**, **Hiring manager**, **Position**, and **Description fields** as appropriate.</span></span>

   ![Toborzási kérelemre mutató hivatkozás](./media/hr-recruit-10-link-to-recruiting-request.png)

7. <span data-ttu-id="c25dc-187">Töltse ki az összes információt a következő területeken, amelyeket fel szeretne venni a jelölt rekordjába:</span><span class="sxs-lookup"><span data-stu-id="c25dc-187">Complete all the information in the following areas that you want to include in the candidate's record:</span></span>
   - <span data-ttu-id="c25dc-188">**Megjegyzések**</span><span class="sxs-lookup"><span data-stu-id="c25dc-188">**Comments**</span></span>
   - <span data-ttu-id="c25dc-189">**Szakmai tapasztalat**</span><span class="sxs-lookup"><span data-stu-id="c25dc-189">**Professional experience**</span></span>
   - <span data-ttu-id="c25dc-190">**Kapcsolattartó adatai**</span><span class="sxs-lookup"><span data-stu-id="c25dc-190">**Contact information**</span></span>
   - <span data-ttu-id="c25dc-191">**Végzettség**</span><span class="sxs-lookup"><span data-stu-id="c25dc-191">**Education**</span></span>
   - <span data-ttu-id="c25dc-192">**Szakértelem**</span><span class="sxs-lookup"><span data-stu-id="c25dc-192">**Skills**</span></span>
   - <span data-ttu-id="c25dc-193">**Diplomák**</span><span class="sxs-lookup"><span data-stu-id="c25dc-193">**Certificates**</span></span>
   - <span data-ttu-id="c25dc-194">**Szűrések**</span><span class="sxs-lookup"><span data-stu-id="c25dc-194">**Screenings**</span></span>

8. <span data-ttu-id="c25dc-195">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-195">Select **Save**.</span></span>

## <a name="hire-a-candidate"></a><span data-ttu-id="c25dc-196">Jelentkező felvétele</span><span class="sxs-lookup"><span data-stu-id="c25dc-196">Hire a candidate</span></span>

<span data-ttu-id="c25dc-197">Ha készen áll egy jelölt felvételére, kövesse ezt az eljárást a jelölt alkalmazottá való átalakításához.</span><span class="sxs-lookup"><span data-stu-id="c25dc-197">When you're ready to hire a candidate, follow this procedure to transition the candidate to an employee.</span></span>

1. <span data-ttu-id="c25dc-198">A jelölt űrlapon válassza a **Felvétel** l ehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-198">On the candidate form, select **Hire**.</span></span>

   ![Jelentkező felvétele](./media/hr-recruit-11-hire.png)

2. <span data-ttu-id="c25dc-200">Az **Új dolgozó felvétele** képernyő **Részletek** csoportban töltse ki az összes mezőt.</span><span class="sxs-lookup"><span data-stu-id="c25dc-200">On the **Hire new worker** form, under **Details**, complete all the fields.</span></span>

   ![Új felvétel adatainak megadása](./media/hr-recruit-12-hire-new-worker.png)

3. <span data-ttu-id="c25dc-202">A **Pozíció részletei** részben szükség szerint ellenőrizze és módosítsa az adatokat.</span><span class="sxs-lookup"><span data-stu-id="c25dc-202">Under **Position details**, verify and change information as necessary.</span></span>

4. <span data-ttu-id="c25dc-203">Az **Előkészítési ellenőrzőlisták** alatt válassza ki az alkalmazotthoz tartozó előkészítési ellenőrzőlistákat.</span><span class="sxs-lookup"><span data-stu-id="c25dc-203">Under **Onboarding checklists**, select the relevant onboarding checklists for this employee.</span></span>

5. <span data-ttu-id="c25dc-204">Válassza a **Folytatás** lehetőséget az alkalmazotti rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c25dc-204">Select **Continue** to create the employee record.</span></span>

   >[!NOTE]
   ><span data-ttu-id="c25dc-205">A szervezet munkafolyamataitól függően a jelölt rekordja további jóváhagyási lépéseken is átmehet, mielőtt alkalmazotti rekorddá válna.</span><span class="sxs-lookup"><span data-stu-id="c25dc-205">Depending on your organization's workflows, the candidate record may go through additional approval steps before becoming an employee record.</span></span>

## <a name="decide-not-to-hire-a-candidate"></a><span data-ttu-id="c25dc-206">Úgy dönt, hogy nem vesz fel jelöltet</span><span class="sxs-lookup"><span data-stu-id="c25dc-206">Decide not to hire a candidate</span></span>

<span data-ttu-id="c25dc-207">Ha úgy dönt, hogy nem vesz fel jelöltet, kövesse ezt az eljárást, hogy távolítsa el őket az ellenőrzési folyamatból.</span><span class="sxs-lookup"><span data-stu-id="c25dc-207">If you decide not to hire a candidate, follow this procedure to remove them from the vetting process.</span></span> 

1. <span data-ttu-id="c25dc-208">A jelölt űrlapon válassza a **Nincs felvétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-208">On the candidate form, select **Do not hire**.</span></span>

   ![Nem vesz fel jelentkezőt](./media/hr-recruit-13-do-not-hire.png)

2. <span data-ttu-id="c25dc-210">Válasszon ki egy **Okkódot**, és adja meg a megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="c25dc-210">Select a **Reason code** and include any comments.</span></span>

3. <span data-ttu-id="c25dc-211">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-211">Select **OK**.</span></span>

## <a name="dismiss-a-candidate"></a><span data-ttu-id="c25dc-212">Jelölt elvetése</span><span class="sxs-lookup"><span data-stu-id="c25dc-212">Dismiss a candidate</span></span>

<span data-ttu-id="c25dc-213">Szükség esetén a felvétel után elbocsáthat egy jelöltet.</span><span class="sxs-lookup"><span data-stu-id="c25dc-213">If needed, you can dismiss a candidate after hiring them.</span></span> <span data-ttu-id="c25dc-214">Előfordulhat például, hogy egy jelölt elutasítja az ajánlatot, vagy nem jelenik meg az első napon.</span><span class="sxs-lookup"><span data-stu-id="c25dc-214">For example, a candidate might reject your offer or not show up on their first day.</span></span>

- <span data-ttu-id="c25dc-215">A jelölt űrlapon válassza a **Jelölt elvetése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c25dc-215">On the candidate form, select **Dismiss candidate**.</span></span>

  ![Jelölt elutasítása](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a><span data-ttu-id="c25dc-217">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c25dc-217">See also</span></span>

[<span data-ttu-id="c25dc-218">Common Data Service-virtuális entitások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c25dc-218">Configure Common Data Service virtual entities</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="c25dc-219">Munkaerő-szervezés</span><span class="sxs-lookup"><span data-stu-id="c25dc-219">Organize your workforce</span></span>](hr-personnel-departments-jobs-positions.md)<br>
[<span data-ttu-id="c25dc-220">Feladat összetevőinek beállítása</span><span class="sxs-lookup"><span data-stu-id="c25dc-220">Set up the components of a job</span></span>](hr-personnel-jobs.md)