---
title: "Forráskeresés LinkedIn Recruiter segítségével"
description: "Ez a témakör a gépi tanulásnak az állás- és állásjelölti javaslatok beszerzésére való használatával kapcsolatban tartalmaz tájékoztatást."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2fc6bf25d303d7d8de8002a923a080b90dcfbeab
ms.openlocfilehash: 106103e2c3d8f3d89aac5140174e5794da22536f
ms.contentlocale: hu-hu
ms.lasthandoff: 10/24/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a><span data-ttu-id="368b8-103">Forráskeresés LinkedIn Recruiter segítségével</span><span class="sxs-lookup"><span data-stu-id="368b8-103">Sourcing with LinkedIn Recruiter</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="368b8-104">A LinkedIn a világ legnagyobb szaktudás-adatbázisa, és gyakran az elsődleges rendszer, amelyet a toborzók jelöltek megtalálására, a velük való kommunikációra és forráskeresésre használnak az aktuális állásra.</span><span class="sxs-lookup"><span data-stu-id="368b8-104">LinkedIn is the world’s largest talent database and often the primary system that recruiters use to find, communicate with, and source candidates for the jobs that recruiters are looking to fill.</span></span> <span data-ttu-id="368b8-105">A LinkedIn Recruiter és a Dynamics 365 for Talent: Attract integrálása megkönnyíti a felhasználók számára a felvételt, valamint az adatok két rendszer közötti szinkronizálását.</span><span class="sxs-lookup"><span data-stu-id="368b8-105">LinkedIn Recruiter integration with Dynamics 365 for Talent: Attract makes it easier for users to hire, and to keep the data in sync between the two systems.</span></span>

> [!NOTE]
> <span data-ttu-id="368b8-106">Az átfogó felvételi bővítmény és LinkedIn Recruiter helyek szükségesek a LinkedIn Recruiter és az Attract integrációjának használatához.</span><span class="sxs-lookup"><span data-stu-id="368b8-106">You need the Comprehensive hiring add-on and LinkedIn Recruiter seats to be able to use LinkedIn Recruiter integration with Attract.</span></span>

## <a name="set-up-linkedin-recruiter-with-attract"></a><span data-ttu-id="368b8-107">Az Attract és a LinkedIn Recruiter beállítása</span><span class="sxs-lookup"><span data-stu-id="368b8-107">Set up LinkedIn Recruiter with Attract</span></span> 

<span data-ttu-id="368b8-108">A LinkedIn Recruiter funkciók használata előtt konfigurálnia kell szerződésszintű, vagy a vállalatiszintű hozzáférést az Attract-példánnyal.</span><span class="sxs-lookup"><span data-stu-id="368b8-108">Before you can use the LinkedIn Recruiter capabilities, you must configure contract-level or company-level access with your Attract instance.</span></span> <span data-ttu-id="368b8-109">A konfiguráció befejezéséhez a LinkedIn Recruiter szerződés rendszergazda felhasználójával kell együttműködnie.</span><span class="sxs-lookup"><span data-stu-id="368b8-109">To complete the configuration process, you must work with the user who is an Admin on your LinkedIn Recruiter contract.</span></span> <span data-ttu-id="368b8-110">A következő lépések bemutatják a LinkedIn Recruiter és az Attract beállítását.</span><span class="sxs-lookup"><span data-stu-id="368b8-110">Complete the following steps to configure LinkedIn Recruiter with Attract.</span></span>

1.  <span data-ttu-id="368b8-111">Jelentkezzen be rendszergazdaként az Attract rendszerébe, és nyissa meg: **Adminisztratív beállítások**.</span><span class="sxs-lookup"><span data-stu-id="368b8-111">Sign in to Attract as an Admin and go to **Admin Settings**.</span></span>

2.  <span data-ttu-id="368b8-112">A bal panelen kattintson a **LinkedIn integráció** lapra.</span><span class="sxs-lookup"><span data-stu-id="368b8-112">On the left pane, click the **LinkedIn Integration** tab.</span></span>

<span data-ttu-id="368b8-113">[![Attract adminisztrátori nézet a LinkedIn Recruiter integráció indításához](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span><span class="sxs-lookup"><span data-stu-id="368b8-113">[![Attract Admin view to start LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span></span>

3.  <span data-ttu-id="368b8-114">Kattintson a **Csatlakozás** elemre a telepítő elindításához, és csinálja végig a LinkedIn bejelentkezési folyamatát.</span><span class="sxs-lookup"><span data-stu-id="368b8-114">Click **Connect** to start the setup and be guided through the LinkedIn sign-in process.</span></span>

4.  <span data-ttu-id="368b8-115">Ha több LinkedIn szerződésben vannak helyei, válassza ki a szerződést, amelyet az Attract rendszerhez szeretne csatolni.</span><span class="sxs-lookup"><span data-stu-id="368b8-115">If you have seats on multiple LinkedIn contracts, select the contract that you would like to connect to the Attract system.</span></span> <span data-ttu-id="368b8-116">Ha csak egy LinkedIn szerződési helye van, ez a lépés nem szükséges.</span><span class="sxs-lookup"><span data-stu-id="368b8-116">If you have a seat on only one LinkedIn contract, this step will not be needed.</span></span>

5.  <span data-ttu-id="368b8-117">A LinkedIn widget most betölti a rendszergazdai beállításokat integrációk megjelenített listájával.</span><span class="sxs-lookup"><span data-stu-id="368b8-117">The LinkedIn widget will now load in your Admin settings with the list of integrations shown.</span></span> <span data-ttu-id="368b8-118">A **Recruiter rendszer csatlakozás** alatt kattintson a **Kérés** elemre.</span><span class="sxs-lookup"><span data-stu-id="368b8-118">Under **Recruiter System connect**, click **Request**.</span></span>

<span data-ttu-id="368b8-119">[![Attract adminisztrátori nézet, a LinkedIn Recruiter integráció kérése](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span><span class="sxs-lookup"><span data-stu-id="368b8-119">[![Attract Admin view to Request LinkedIn Recruiter integration](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span></span>

6.  <span data-ttu-id="368b8-120">Az integráció kérelmezése után az Attract rendszertől, megjelenik a **Partner kész** módon, és már be lehet kapcsolni a **Recruiter adminisztratív beállítások** helyről.</span><span class="sxs-lookup"><span data-stu-id="368b8-120">After the integration is requested from Attract, it will show as **Partner ready** and is ready to be turned on from **Recruiter Admin settings**.</span></span> <span data-ttu-id="368b8-121">Ha a **Partner értesítése** megjelenik ezen az oldalon, várjon néhány másodpercet, kattintson a **Partner értesítése** elemre, majd frissítse a lapot.</span><span class="sxs-lookup"><span data-stu-id="368b8-121">If you see **Notify partner** on this page, wait a few seconds, click **Notify partner**, and then refresh the page.</span></span> <span data-ttu-id="368b8-122">Most meg kell jelennie a **Partner kész** állapotban.</span><span class="sxs-lookup"><span data-stu-id="368b8-122">It should now show as **Partner ready**.</span></span>

<span data-ttu-id="368b8-123">[![Attract adminisztrátori nézet, az Attract oldaláról érkező kérelmet teljesítették](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span><span class="sxs-lookup"><span data-stu-id="368b8-123">[![Attract Admin view to indicate Attract side of requests have been completed](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span></span>

<span data-ttu-id="368b8-124">A következő lépésre teljesítéséhez rendszergazdai jogosultság szükséges a LinkedIn Recruiter szerződésen.</span><span class="sxs-lookup"><span data-stu-id="368b8-124">To complete the next step, you need to have an Admin privilege on your LinkedIn Recruiter Contract.</span></span>

7.  <span data-ttu-id="368b8-125">A LinkedIn rendszerébe a rendszergazda fiók használatával jelentkezzen be, és nyissa meg a jobb felső sarokban LinkedIn Recruiter elemet.</span><span class="sxs-lookup"><span data-stu-id="368b8-125">Sign in to LinkedIn using the Admin account and go to LinkedIn Recruiter on the top right.</span></span> 

8. <span data-ttu-id="368b8-126">A **További** menüben a képernyő tetején kattintson az **Adminisztratív beállítások** elemre, majd kattintson az **ATS** lapra.</span><span class="sxs-lookup"><span data-stu-id="368b8-126">On the **More** menu at the top of the screen, click **Admin Settings**, and then click the **ATS** Tab.</span></span>

<span data-ttu-id="368b8-127">Az Attract rendszer jelenik meg a néhány beállítással, amelyek bekapcsolhatók.</span><span class="sxs-lookup"><span data-stu-id="368b8-127">The Attract system will be listed with a couple of options that can be turned on.</span></span>

9. <span data-ttu-id="368b8-128">Ha csak az 1 kattintásos exportálást szeretné engedélyezni at **In-ATS jelzőhöz** és az **In-ATS profil widgethez**, jelölje be a **Vállalati szintű hozzáférést**.</span><span class="sxs-lookup"><span data-stu-id="368b8-128">If you want to enable only 1-Click export for the **In-ATS indicator** and the **In-ATS Profile Widget**, select **Company-level access**.</span></span> <span data-ttu-id="368b8-129">Ha engedélyezni szeretné az összes vállalati szintű hozzáférési funkciót plusz az InMail előzményeket, a Megjegyzések előzményeit és az InMail csonka profil hozzáférést, jelölje be a **Szerződés szintű hozzáférés** elemet.</span><span class="sxs-lookup"><span data-stu-id="368b8-129">If you want to enable all of Company-level access features plus InMail history, Notes history, and the InMail stub profile access, select **Contract-level access**.</span></span>

10. <span data-ttu-id="368b8-130">Kapcsolja be a kívánt hozzáférési szintet a LinkedIn Recruiter **Admin-ATS** beállításaiban.</span><span class="sxs-lookup"><span data-stu-id="368b8-130">Turn on the desired access level from your LinkedIn Recruiter **Admin-ATS** settings.</span></span>

<span data-ttu-id="368b8-131">[![LinkedIn Recruiter adminisztrátori nézet, Attract integráció bekapcsolása](./media/EnableRSC.png)](./media/EnableRSC.png)</span><span class="sxs-lookup"><span data-stu-id="368b8-131">[![Turn on Attract integration from LinkedIn Recruiter Admin view](./media/EnableRSC.png)](./media/EnableRSC.png)</span></span>

12. <span data-ttu-id="368b8-132">Térjen vissza az Attract adminisztratív beállításokhoz AttractAdminként, és válassza ki a **LinkedIn integráció** lapot. Azt kell látnia, hogy a LinkedIn widget be van töltődve **Engedélyezett** állapottal, a kijelölt hozzáférési szint pedig be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="368b8-132">Go back to Attract Admin Settings as an AttractAdmin and select the **LinkedIn integration** tab. You should now see the LinkedIn widget load showing **Enabled** with the selected access level turned on.</span></span>

<span data-ttu-id="368b8-133">[![LinkedIn Recruiter-integráció kész](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span><span class="sxs-lookup"><span data-stu-id="368b8-133">[![LinkedIn Recruiter integration complete](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span></span>

## <a name="using-linkedin-recruiter-capabilities"></a><span data-ttu-id="368b8-134">A LinkedIn Recruiter lehetőségeinek használata</span><span class="sxs-lookup"><span data-stu-id="368b8-134">Using LinkedIn Recruiter capabilities</span></span>

<span data-ttu-id="368b8-135">Miután LinkedIn Recruiter lehetőségeket az Attract rendszergazda engedélyezte, elérhető a felvételi vezetők és a toborzók számára.</span><span class="sxs-lookup"><span data-stu-id="368b8-135">After LinkedIn Recruiter capabilities has been enabled by the Attract Admin it is available for hiring managers and recruiters to access.</span></span> <span data-ttu-id="368b8-136">A funkciók használatához csatlakoztassa LinkedIn-fiókját itt: **Felhasználói beállítások**.</span><span class="sxs-lookup"><span data-stu-id="368b8-136">To use these capabilities, connect your LinkedIn account under **User Settings**.</span></span> <span data-ttu-id="368b8-137">Több képesség lesz elérhető az adminisztrációs és felhasználói beállítások csatlakoztatása után.</span><span class="sxs-lookup"><span data-stu-id="368b8-137">Several capabilities will be available after both the Admin and User settings have been connected.</span></span>

### <a name="in-ats-profile-widget"></a><span data-ttu-id="368b8-138">In-ATS profil widget</span><span class="sxs-lookup"><span data-stu-id="368b8-138">In-ATS profile widget</span></span>

<span data-ttu-id="368b8-139">A jelölt LinkedIn profilját megtekintheti az Attract rendszerében.</span><span class="sxs-lookup"><span data-stu-id="368b8-139">You can view the candidate’s LinkedIn profile in Attract.</span></span> <span data-ttu-id="368b8-140">A LinkedIn widget megjeleníti a pályázó profilját, amikor az ATS adatok megfelelnek a felhasználók LinkedIn adatainak.</span><span class="sxs-lookup"><span data-stu-id="368b8-140">The LinkedIn widget will display the candidate profile when the ATS information matches the LinkedIn information of its users.</span></span>

<span data-ttu-id="368b8-141">Profil megtekintéséhez menjen a jelentkező profiljához az állásból vagy a szaktudáskészletből elindulva.</span><span class="sxs-lookup"><span data-stu-id="368b8-141">To view a profile, go the candidate profile either from a job or talent pool.</span></span> <span data-ttu-id="368b8-142">A pályázói profilnál válassz a **LinkedIn** lapot, és betöltődik a profilwidget.</span><span class="sxs-lookup"><span data-stu-id="368b8-142">In the candidate profile, select the **LinkedIn** tab and the profile widget will load.</span></span> <span data-ttu-id="368b8-143">A profilwidget használatával jelzze, ha ez a megfelelő egyezés-e.</span><span class="sxs-lookup"><span data-stu-id="368b8-143">Using the profile widget, indicate if this is the correct match.</span></span> <span data-ttu-id="368b8-144">Ha nem, keresse meg a megfelelő személyt.</span><span class="sxs-lookup"><span data-stu-id="368b8-144">If it is not, find the correct person.</span></span> <span data-ttu-id="368b8-145">A pályázót mentheti is erről a lapról LinkedIn Recruiter projektjeibe.</span><span class="sxs-lookup"><span data-stu-id="368b8-145">You can also save the candidate to your LinkedIn Recruiter projects from this page.</span></span>

### <a name="1-click-export"></a><span data-ttu-id="368b8-146">1 kattintásos exportálás</span><span class="sxs-lookup"><span data-stu-id="368b8-146">1-click export</span></span> 

<span data-ttu-id="368b8-147">A LinkedIn rendszerében pályázók keresésekor 1 kattintással exportálhatja a pályázókat az éppen nyitott állásokhoz.</span><span class="sxs-lookup"><span data-stu-id="368b8-147">While sourcing candidates in LinkedIn, you can 1-click export the candidate to the jobs that you currently have open.</span></span> <span data-ttu-id="368b8-148">Hajtsa végre a következő lépéseket az 1 kattintásos exportáláshoz.</span><span class="sxs-lookup"><span data-stu-id="368b8-148">Complete the following steps for a 1-click export.</span></span> <span data-ttu-id="368b8-149">A lépések lezárása előtt ellenőrizze, hogy a hozzárendelt szerepe felvételi vezető vagy toborzó az állás esetében, és hogy az állás a **Jelölt** szakaszban legyen.</span><span class="sxs-lookup"><span data-stu-id="368b8-149">Before you complete these steps, verify that you are a assigned the role of Hiring manager or Recruiter for the job and that the job has a **Prospect** stage.</span></span>

1.  <span data-ttu-id="368b8-150">Végezze el az állás létrehozását, a megfelelő szerepkörök hozzárendelését, és aktiválja az állást.</span><span class="sxs-lookup"><span data-stu-id="368b8-150">Create the job, assign the appropriate roles, and activate the job.</span></span>

2.  <span data-ttu-id="368b8-151">Az állás aktiválása után menjen ide: LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="368b8-151">When the job is activated, navigate to LinkedIn Recruiter.</span></span>

3.  <span data-ttu-id="368b8-152">Keresse meg a keresett jelöltet, és ugorjon a profiljához.</span><span class="sxs-lookup"><span data-stu-id="368b8-152">Find the candidate that you are looking for and go to their profile.</span></span>

4.  <span data-ttu-id="368b8-153">A névjegykártya álláskeresés mezőjével keresse meg az állást az Attract rendszerében aktivált álláscím vagy állásazonosító alapján.</span><span class="sxs-lookup"><span data-stu-id="368b8-153">Using the job search box in the contact card, find the job using the title or the Job ID that was activated in Attract.</span></span> <span data-ttu-id="368b8-154">Ha nem találja az állást, kattintson az **ATS módosítása** elemre a megfelelő Attract-példány megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="368b8-154">If you don’t find the job, click **Change ATS** to find the correct Attract instance.</span></span>

5. <span data-ttu-id="368b8-155">Miután kiválasztotta az állást, kattintson az **Exportálás** elemre.</span><span class="sxs-lookup"><span data-stu-id="368b8-155">After the job is selected, click **Export**.</span></span> <span data-ttu-id="368b8-156">A pályázót az Attract most beolvassa.</span><span class="sxs-lookup"><span data-stu-id="368b8-156">The candidate is now fetched by Attract.</span></span>

6.  <span data-ttu-id="368b8-157">Menjen az Attract rendszerébe, és nyissa meg a megfelelő állást.</span><span class="sxs-lookup"><span data-stu-id="368b8-157">Go to Attract and open the respective job.</span></span> <span data-ttu-id="368b8-158">Az imént exportált jelöltet megtalálja az állás **Jelölt** állapotában.</span><span class="sxs-lookup"><span data-stu-id="368b8-158">You will find the candidate that you just exported in the **Prospect** stage of the job.</span></span>

### <a name="in-ats-indicator"></a><span data-ttu-id="368b8-159">In-ATS jelölő</span><span class="sxs-lookup"><span data-stu-id="368b8-159">In-ATS indicator</span></span> 

<span data-ttu-id="368b8-160">LinkedIn Recruiter használatával nyomon követheti, hogy pályázó jelentkezett-e a szervezeténél más állásokra, megnézheti, hogy hol tart az álláspályázatok különböző szakaszaiban, és LinkedIn Recruiter rendszerében megtekintheti az Attract visszajelzéseit és megjegyzéseit.</span><span class="sxs-lookup"><span data-stu-id="368b8-160">Using LinkedIn recruiter, you can track whether a candidate has applied to other jobs in your organization, look at where they are in different stages of job applications, and view the feedback and comments from Attract in LinkedIn Recruiter.</span></span>

1.  <span data-ttu-id="368b8-161">Nyissa meg a LinkedIn Recruiter rendszert, és keresse meg a kívánt pályázói profilt.</span><span class="sxs-lookup"><span data-stu-id="368b8-161">Open LinkedIn Recruiter and locate the candidate profile that you are looking for.</span></span>

2.  <span data-ttu-id="368b8-162">Görgetés lefelé az **In-ATS** szakaszhoz a jelölt profiljában.</span><span class="sxs-lookup"><span data-stu-id="368b8-162">Scroll down to view the **In-ATS** section on the candidate’s profile.</span></span>

3.  <span data-ttu-id="368b8-163">A widget segítségével minden olyan jelöltadat megtekinthető a LinkedIn Recruiter nézetben, amely megtalálható az Attract rendszerében.</span><span class="sxs-lookup"><span data-stu-id="368b8-163">You can use this widget to view all of the information about the candidate that’s present in Attract from within the LinkedIn Recruiter view.</span></span>

4.  <span data-ttu-id="368b8-164">Válassza ki az **Állások és állapotok** lapot az állások megtekintéséhez, amelyeknek a részesei, a legutóbbi állapot megtekintéséhez, és hogy hogyan mozogtak az egyes állások esetében.</span><span class="sxs-lookup"><span data-stu-id="368b8-164">Select the **Jobs & Statuses** tab to see jobs they are part of, the latest status, and how they have been moving against each job.</span></span>

5.  <span data-ttu-id="368b8-165">Válassza ki az **Interjú-visszajelzés** fület az interjúbonyolítók által az Attract rendszerébe beküldött visszajelzések megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="368b8-165">Select the **Interview Feedback** tab to see feedback that the interviewers have submitted in Attract.</span></span>

6.  <span data-ttu-id="368b8-166">Válassza ki a **Megjegyzések** lapot a pályázóhoz az Attractban rögzített megjegyzések megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="368b8-166">Select the **Notes** tab to see notes that have been captured for this applicant in Attract.</span></span>

### <a name="inmail-history"></a><span data-ttu-id="368b8-167">InMail előzmények</span><span class="sxs-lookup"><span data-stu-id="368b8-167">InMail history</span></span>

<span data-ttu-id="368b8-168">Szerződés szintű hozzáféréssel elérhetők a LinkedIn InMail előzményei a LinkedIn Recruiterben.</span><span class="sxs-lookup"><span data-stu-id="368b8-168">The LinkedIn InMail history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="368b8-169">Ha engedélyezve van, a pályázó teljes InMail előzményei megjeleníthetők.</span><span class="sxs-lookup"><span data-stu-id="368b8-169">When it is enabled, you can view your entire InMail history with the candidate.</span></span> <span data-ttu-id="368b8-170">Megtekintheti, hogy a szervezetből ki váltott InMail üzeneteket a pályázóval, az üzeneteket azonban nem lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="368b8-170">You can also see who else from your organization has exchanged InMail with the candidate, however you can't view the messages between them.</span></span>

<span data-ttu-id="368b8-171">Az InMail-előzmények megtekintéséhez ugorjon a jelentkező profiljára, menjen a **LinkedIn** lapra, és görgessen az előzmények megtekintéséhez a lap aljára.</span><span class="sxs-lookup"><span data-stu-id="368b8-171">To view InMail history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="368b8-172">Csak akkor tekintheti meg az InMail előzményeket, ha a pályázó válaszolt a kérésére, és a LinkedIn rendszerében megosztotta Önnel a profilját.</span><span class="sxs-lookup"><span data-stu-id="368b8-172">You can view the InMail history only if the candidate has responded to your request and chosen to share their profile with you in LinkedIn.</span></span> <span data-ttu-id="368b8-173">Az InMail üzenetei az Attract rendszerével néhány óránként szinkronizálódnak.</span><span class="sxs-lookup"><span data-stu-id="368b8-173">The messages from InMail sync with Attract every couple of hours.</span></span>

### <a name="notes-history"></a><span data-ttu-id="368b8-174">Megjegyzések előzményei</span><span class="sxs-lookup"><span data-stu-id="368b8-174">Notes history</span></span> 

<span data-ttu-id="368b8-175">Szerződés szintű hozzáféréssel elérhetők a LinkedIn megjegyzések előzményei a LinkedIn Recruiterben.</span><span class="sxs-lookup"><span data-stu-id="368b8-175">The LinkedIn notes history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="368b8-176">Ha engedélyezve van, megtekintheti a szervezet különböző toborzói által a jelölttel kapcsolatosan rögzített megjegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="368b8-176">When it is enabled, you can view the notes that have been captured about the candidate by different recruiters from your organization.</span></span>

<span data-ttu-id="368b8-177">A megjegyzéselőzmények megtekintéséhez ugorjon a jelentkező profiljára, menjen a **LinkedIn** lapra, és görgessen az előzmények megtekintéséhez a lap aljára.</span><span class="sxs-lookup"><span data-stu-id="368b8-177">To view Notes history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="368b8-178">A pályázóval kapcsolatosan rögzített összes megjegyzést megtekintheti a LinkedIn Recruiterből.</span><span class="sxs-lookup"><span data-stu-id="368b8-178">You can view all the notes about the candidate from LinkedIn Recruiter.</span></span>

### <a name="inmail-stub-profile"></a><span data-ttu-id="368b8-179">InMail csonka profil</span><span class="sxs-lookup"><span data-stu-id="368b8-179">InMail stub profile</span></span>

<span data-ttu-id="368b8-180">Szerződés szintű hozzáféréssel elérhetők a LinkedIn InMail csonka profilok a LinkedIn Recruiterben.</span><span class="sxs-lookup"><span data-stu-id="368b8-180">The InMail stub profile is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="368b8-181">Ha a pályázó elfogadja a LinkedIn-profilja megosztása a szervezet egy felhasználójával, nyomon követheti a jelölteket az Attract rendszerében, és minden egyes jelölthöz létrejön egy új jelentkezőrekord.</span><span class="sxs-lookup"><span data-stu-id="368b8-181">If candidates agree to share their LinkedIn profiles with any user in your organization, you can track the candidates in Attract and a new candidate record will be created for each candidate.</span></span>

<span data-ttu-id="368b8-182">A pályázók listájának megtekintéséhez menjen a **Szaktudásgyűjtők** elemhez a rendszer által létrehozott LinkedIn szaktudásgyűjtők ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="368b8-182">To view the list of candidates, go to **Talent pools** to see a system-created LinkedIn talent pool.</span></span> <span data-ttu-id="368b8-183">A szaktudásgyűjtő a LinkedIntől kapott jelöltlistákat és a jelöltek csonka profiljait tartalmazza, a jelölt keresztnevét és vezetéknevét mutatva.</span><span class="sxs-lookup"><span data-stu-id="368b8-183">This talent pool contains the list candidates and their stub profiles as received from LinkedIn, showing the candidate's first name and last name.</span></span> <span data-ttu-id="368b8-184">A pályázó e-mail-azonosítója fog megjelenni, ha a pályázó az e-mail-címe megosztását választotta.</span><span class="sxs-lookup"><span data-stu-id="368b8-184">The candidate’s email ID will be displayed if the candidate had chosen to share their email address.</span></span>

