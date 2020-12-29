---
title: Jelöltek felkutatása a LinkedIn Recruiter használatával az Attract szolgáltatásban
description: A Microsoft Dynamics 365 Talent - Attract LinkedIn integrációját használhatja a jelöltek felkutatásához a LinkedIn Recruiter megoldáson keresztül.
author: andreabichsel
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 96e4660c4958bf5f2a0910bfad770e1e713f800f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528269"
---
# <a name="source-candidates-with-linkedin-recruiter-in-attract"></a><span data-ttu-id="44da0-103">Jelöltek felkutatása a LinkedIn Recruiter használatával az Attract szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="44da0-103">Source candidates with LinkedIn Recruiter in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="44da0-104">A LinkedIn a világ legnagyobb online szakmai hálózata, amely hozzáférést biztosít a világ legjobb tehetségéhez.</span><span class="sxs-lookup"><span data-stu-id="44da0-104">LinkedIn is the world's largest online professional network, giving you access to the world's top talent.</span></span> <span data-ttu-id="44da0-105">Microsoft Dynamics 365 Talent: Attract segítségével felkutathat pályázókat közvetlenül a LinkedIn felületről.</span><span class="sxs-lookup"><span data-stu-id="44da0-105">Microsoft Dynamics 365 Talent: Attract lets you source candidates directly from LinkedIn.</span></span> <span data-ttu-id="44da0-106">Ezért könnyebb, mint valaha, megtalálnia azokat a tehetségeket, akikkel betöltheti nyitott állásait.</span><span class="sxs-lookup"><span data-stu-id="44da0-106">Therefore, it's easier than ever to find the talent that you need to fill your open positions.</span></span> <span data-ttu-id="44da0-107">Miután a LinkedIn alkalmazással beállította a kapcsolatot az Attract megoldáson keresztül, megtekintheti a beosztásokhoz tartozó esetleges LinkedIn-jelöltek adatait, és egyetlen kattintással exportálhatja azokat az Attract megoldásba.</span><span class="sxs-lookup"><span data-stu-id="44da0-107">After you set up your connection with LinkedIn through Attract, you can view potential LinkedIn candidates for your positions and export them into Attract with just one click.</span></span>

<span data-ttu-id="44da0-108">Ha úgy tűnik, hogy nem rendelkezik ezzel a képességgel, forduljon a rendszergazdához. Csak akkor veheti igénybe LinkedIn Recruiter megoldást az Attract alkalmazásból ha az adminisztrátor [beállította a LinkedIn integrációt](./attract-admin-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="44da0-108">If you don't seem to have this capability, contact your admin. Before you can take advantage of LinkedIn Recruiter from Attract, your admin must [set up integration with LinkedIn](./attract-admin-linkedin.md).</span></span> <span data-ttu-id="44da0-109">Ezután beállíthatja a kapcsolatot a LinkedIn Recruiter megoldással és megkezdheti a jelöltek megtalálását.</span><span class="sxs-lookup"><span data-stu-id="44da0-109">You can then set up your connection with LinkedIn Recruiter and start finding candidates.</span></span>

>[!IMPORTANT]
><span data-ttu-id="44da0-110">2020. július 1-től a LinkedIn már nem támogatja az Internet Explorer 11-et.</span><span class="sxs-lookup"><span data-stu-id="44da0-110">As of July 1, 2020, LinkedIn no longer supports Internet Explorer 11.</span></span> <span data-ttu-id="44da0-111">A felhasználók továbbra is elérhetik a LinkedInt az Internet Explorer 11-gyel, de a rendszer kérni fogja a frissítést vagy egy másik böngésző használatát.</span><span class="sxs-lookup"><span data-stu-id="44da0-111">Users can still access LinkedIn with Internet Explorer 11, but will be prompted to upgrade or use a different browser.</span></span> <span data-ttu-id="44da0-112">További információ: [A LinkedIn által támogatott böngészők](https://www.linkedin.com/help/linkedin/answer/4135/supported-internet-browsers-for-linkedin).</span><span class="sxs-lookup"><span data-stu-id="44da0-112">For more information, see [Supported Internet Browsers for LinkedIn](https://www.linkedin.com/help/linkedin/answer/4135/supported-internet-browsers-for-linkedin).</span></span>

## <a name="set-up-your-connection-with-linkedin-recruiter"></a><span data-ttu-id="44da0-113">A kapcsolat beállítása a LinkedIn Recruiter megoldással</span><span class="sxs-lookup"><span data-stu-id="44da0-113">Set up your connection with LinkedIn Recruiter</span></span>

<span data-ttu-id="44da0-114">Mielőtt használhatná a LinkedIn Recruiter megoldást az Attract alkalmazáson keresztül be kell állítania a kapcsolatot LinkedIn Recruiter megoldással.</span><span class="sxs-lookup"><span data-stu-id="44da0-114">Before you can start working with LinkedIn Recruiter through Attract, you must set up your connection with LinkedIn Recruiter.</span></span> <span data-ttu-id="44da0-115">Ehhez a lépéshez szüksége van a LinkedIn Recruiter hitelesítő adataira.</span><span class="sxs-lookup"><span data-stu-id="44da0-115">For this step, you need your LinkedIn Recruiter credentials.</span></span>

1. <span data-ttu-id="44da0-116">Kattintson a lap jobb felső sarkában látható **Beállítások** (fogaskerék ikon) gombra.</span><span class="sxs-lookup"><span data-stu-id="44da0-116">Select the **Settings** button (gear icon) in the upper-right corner of the page.</span></span>
2. <span data-ttu-id="44da0-117">Válassza a **Felhasználói beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="44da0-117">Select **User settings**.</span></span>
3. <span data-ttu-id="44da0-118">A **Kapcsolatok** lapon jelölje be a **Csatlakozás** lehetőséget a **LinkedIn** mellett.</span><span class="sxs-lookup"><span data-stu-id="44da0-118">On the **Connections** tab, select **Connect** next to **LinkedIn**.</span></span> <span data-ttu-id="44da0-119">Kövesse a LinkedIn által biztosított utasításokat.</span><span class="sxs-lookup"><span data-stu-id="44da0-119">Follow the instructions that are provided by LinkedIn.</span></span>

    ![[<span data-ttu-id="44da0-120">Kapcsolat beállítása a LinkedIn Recruiter felé az Attracttól</span><span class="sxs-lookup"><span data-stu-id="44da0-120">Set up connection to LinkedIn Recruiter from Attract</span></span>](./media/attract-set-up-linkedin-recruiter-connection.png)](./media/attract-set-up-linkedin-recruiter-connection.png)

## <a name="view-linkedin-candidates-in-attract"></a><span data-ttu-id="44da0-121">A LinkedIn-jelöltek megtekintése az Attract megoldásban</span><span class="sxs-lookup"><span data-stu-id="44da0-121">View LinkedIn candidates in Attract</span></span>

<span data-ttu-id="44da0-122">Miután csatlakozott a LinkedIn Recruiter alkalmazáshoz, megtekintheti a jelentkezők LinkedIn-profiljait az Attract megoldásban.</span><span class="sxs-lookup"><span data-stu-id="44da0-122">After you're connected to LinkedIn Recruiter, you can view candidates' LinkedIn profiles in Attract.</span></span>

>[!NOTE]
><span data-ttu-id="44da0-123">Ha van Recruiter munkaállomás Önhöz rendelve akkor láthatja a jelöltek összes adatát.</span><span class="sxs-lookup"><span data-stu-id="44da0-123">If you have a Recruiter seat assigned to you, you can see the candidates' full information.</span></span><br><br>
><span data-ttu-id="44da0-124">Ha van egy Toborzási vezető munkaállomás van Önhöz rendelve vagy nincs munkaállomás Önhöz rendelve, ügyeljen arra, hogy kijelentkezzen a LinkedIn vagy a LinkedIn Recruiter szolgáltatásból, mielőtt egy jelölt LinkedIn lapjára navigálna az Attractban.</span><span class="sxs-lookup"><span data-stu-id="44da0-124">If you have a Hiring Manager seat or no seat assigned to you, be sure to sign out of LinkedIn or LinkedIn Recruiter before navigating to the LinkedIn tab for a candidate in Attract.</span></span> <span data-ttu-id="44da0-125">Megtekintheti a jelölt alapvető nyilvános profiladatait, például a vezeték- és keresztnevét.</span><span class="sxs-lookup"><span data-stu-id="44da0-125">You'll be able to see the candidate's basic public profile data, such as their first and last name.</span></span>

1. <span data-ttu-id="44da0-126">Az Attract megoldásban válassza a **Munkák** vagy **Tehetségállományok** lehetőséget a bal oldalon, majd válassza ki a pályázót.</span><span class="sxs-lookup"><span data-stu-id="44da0-126">In Attract, select **Jobs** or **Talent pools** on the left, and then select an applicant.</span></span>

    ![[<span data-ttu-id="44da0-127">A LinkedIn-jelöltek megtekintése az Attract megoldásban</span><span class="sxs-lookup"><span data-stu-id="44da0-127">View LinkedIn candidates in Attract</span></span>](./media/attract-view-linkedin-candidates.png)](./media/attract-view-linkedin-candidates.png)

2. <span data-ttu-id="44da0-128">A pályázó profiljában válassza a **LinkedIn** fület. A pályázó profilját az InMail előzményeivel együtt tekintheti meg.</span><span class="sxs-lookup"><span data-stu-id="44da0-128">In the candidate's profile, select the **LinkedIn** tab. You can view the candidate's profile and InMail history.</span></span>

   ![A jelölt LinkedIn-adatainak megtekintése](./media/attract-candidate-linkedin-tab.png)

<span data-ttu-id="44da0-130">A következő műveleteket végezheti el innen:</span><span class="sxs-lookup"><span data-stu-id="44da0-130">From here, you can perform the following actions:</span></span>

- <span data-ttu-id="44da0-131">A **Toborzási tevékenységek** lapon megtekintheti a következőket:</span><span class="sxs-lookup"><span data-stu-id="44da0-131">Select the **Recruiting activities** tab to view:</span></span>
   
   - <span data-ttu-id="44da0-132">Toborzó jegyzetek (nyilvános és magán is).</span><span class="sxs-lookup"><span data-stu-id="44da0-132">Recruiter notes (both public and private).</span></span> <span data-ttu-id="44da0-133">Alapértelmezés szerint a jegyzetek privátak, és csak a jegyzetek tulajdonosa számára láthatók.</span><span class="sxs-lookup"><span data-stu-id="44da0-133">By default, notes are private and only visible to the owner of the notes.</span></span>
   - <span data-ttu-id="44da0-134">InMail tevékenység (de nem InMail tartalom).</span><span class="sxs-lookup"><span data-stu-id="44da0-134">InMail activity (but not the InMail content).</span></span> <span data-ttu-id="44da0-135">Görgessen a lap aljára, hogy megtekinthesse a InMail párbeszédet a jelölttel, és megtekinthesse a szervezet más, a potenciális jelölttel interakcióba lépő felhasználóit.</span><span class="sxs-lookup"><span data-stu-id="44da0-135">Scroll to the bottom of the page to view the InMail exchange with your prospect and view other users in your organization who are interacting with your prospect.</span></span>
   - <span data-ttu-id="44da0-136">A pályázó-elutasítás tevékenysége</span><span class="sxs-lookup"><span data-stu-id="44da0-136">Candidate rejection activity</span></span>

- <span data-ttu-id="44da0-137">Válassza a **Küldés InMail-ben**, hogy anélkül küldhessem InMail-t, hogy el kellene hagynia az Attractet.</span><span class="sxs-lookup"><span data-stu-id="44da0-137">Select **Send InMail** to send InMail without having to leave Attract.</span></span>

- <span data-ttu-id="44da0-138">Válassza a **Mentés egy munkába** lehetőséget a munka mentéséhez az Attract elhagyása nélkül.</span><span class="sxs-lookup"><span data-stu-id="44da0-138">Select **Save to a job** to save the job without leaving Attract.</span></span>

> [!NOTE]
> <span data-ttu-id="44da0-139">A pályázó LinkedIn-profilja akkor jelenik meg az Attract megoldásban, ha a pályázónak Attract és LinkedIn adatai megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="44da0-139">A candidate's LinkedIn profile will display in Attract when the candidate's Attract information matches the LinkedIn information.</span></span> <span data-ttu-id="44da0-140">Itt találja a használt egyezetetési szabályokat:</span><span class="sxs-lookup"><span data-stu-id="44da0-140">Here are the matching rules that are used:</span></span>
> 
> 1. <span data-ttu-id="44da0-141">Ha az e-mail cím és a LinkedIn tagazonosító egyezik az Attract megoldásban és a LinkedIn felületen, megjelenik a pályázó profilja.</span><span class="sxs-lookup"><span data-stu-id="44da0-141">If the email address and LinkedIn member ID match in Attract and LinkedIn, the candidate's profile is shown.</span></span> <span data-ttu-id="44da0-142">A jelentkezőknek lehetősége van arra, hogy a LinkedIn profilját összekapcsolja vagy leválassza az Attract megoldásból.</span><span class="sxs-lookup"><span data-stu-id="44da0-142">Candidates still have the option to link or unlink their LinkedIn profile from Attract.</span></span>
> 2. <span data-ttu-id="44da0-143">Ha az e-mail cím vagy a LinkedIn tagazonosító nem egyezik, akkor megjelenik a lehetséges jelöltek listája.</span><span class="sxs-lookup"><span data-stu-id="44da0-143">If the email address or LinkedIn member ID doesn't match, you see a list of possible candidates.</span></span> <span data-ttu-id="44da0-144">Ezután ki lehet választani egy pályázót a listában, és csatolhatja a profilhoz.</span><span class="sxs-lookup"><span data-stu-id="44da0-144">You can then select a candidate in the list and link the profile.</span></span>
> 3. <span data-ttu-id="44da0-145">Ha nincsenek jó egyezések, akkor a program értesítést küldött, hogy nem talált egyezést.</span><span class="sxs-lookup"><span data-stu-id="44da0-145">If there are no good matches, you're notified that no match was found.</span></span>

## <a name="export-linkedin-candidates-to-attract-with-one-click"></a><span data-ttu-id="44da0-146">LinkedIn jelöltek exportálás az Attract megoldásba egyetlen kattintással</span><span class="sxs-lookup"><span data-stu-id="44da0-146">Export LinkedIn candidates to Attract with one click</span></span>

<span data-ttu-id="44da0-147">Amikor a jelentkezőket a LinkedIn Recruiter megoldásban tekinti meg, akkor őket olyan feladatokba exportálhatja, amelyek jelenleg meg vannak nyitva az Attract megoldásban.</span><span class="sxs-lookup"><span data-stu-id="44da0-147">While you're reviewing candidates in LinkedIn Recruiter, you can export them to jobs that you currently have open in Attract.</span></span> <span data-ttu-id="44da0-148">Ehhez a lépéshez Toborzó vagy Felvételi vezető engedélyek szükségesek a Vonzásban.</span><span class="sxs-lookup"><span data-stu-id="44da0-148">For this step, you need Recruiter or Hiring Manager permissions in Attract.</span></span> <span data-ttu-id="44da0-149">Az Attract szerepköreivel kapcsolatos további tudnivalókért tekintse át a [Biztonság és szerepkörkezelés az Attract alkalmazásban](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract) részt.</span><span class="sxs-lookup"><span data-stu-id="44da0-149">For more information about roles in Attract, see [Security and role management in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract).</span></span>

<span data-ttu-id="44da0-150">Arról is meg kell győződnie arról, hogy a feladatnak van Potenciális jelölt szakasza.</span><span class="sxs-lookup"><span data-stu-id="44da0-150">You must also make sure that the job has a Prospect stage.</span></span> <span data-ttu-id="44da0-151">További információ: [Potenciális jelöltekkel kapcsolatos tevékenységek](./activities-attract.md#prospect-activity).</span><span class="sxs-lookup"><span data-stu-id="44da0-151">For more information, see [Prospect activity](./activities-attract.md#prospect-activity).</span></span>

1. <span data-ttu-id="44da0-152">Az Attract megoldásban hozzon létre egy állást, végezze el a megfelelő szerepkörök hozzárendelését, és aktiválja az állást.</span><span class="sxs-lookup"><span data-stu-id="44da0-152">In Attract, create a job, assign the appropriate roles, and activate the job.</span></span>
2. <span data-ttu-id="44da0-153">A LinkedIn Recruiter alkalmazásban keressen egy jó jelentkezőt a feladatra, és nyissa meg a pályázó profilját.</span><span class="sxs-lookup"><span data-stu-id="44da0-153">In LinkedIn Recruiter, find a good candidate for the job, and go to the candidate's profile.</span></span>
3. <span data-ttu-id="44da0-154">A névjegykártya álláskeresés mezőjével keresse meg az állást az Attract rendszerében aktivált álláscím vagy állásazonosító alapján.</span><span class="sxs-lookup"><span data-stu-id="44da0-154">In the job search box in the contact card, find the job by using the title or the Job ID that was activated in Attract.</span></span> <span data-ttu-id="44da0-155">Ha nem találja az állást, kattintson az **ATS módosítása** elemre a megfelelő Attract-példány megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="44da0-155">If you can't find the job, select **Change ATS** to find the correct Attract instance.</span></span>
4. <span data-ttu-id="44da0-156">Válassza ki az állást, válassza az **Exportálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="44da0-156">Select the job, and then select **Export**.</span></span>
5. <span data-ttu-id="44da0-157">Az Attract megoldásban nyissa meg az állást.</span><span class="sxs-lookup"><span data-stu-id="44da0-157">In Attract, open the job.</span></span> <span data-ttu-id="44da0-158">Az állásnak a **Potenciális jelölt** lapján fog megjelenni az exportált pályázó.</span><span class="sxs-lookup"><span data-stu-id="44da0-158">The exported candidate will appear on the **Prospect** tab of the job.</span></span>

## <a name="view-attract-information-in-linkedin-recruiter"></a><span data-ttu-id="44da0-159">Az Attract információinak megtekintése a LinkedIn Recruiter megoldásban</span><span class="sxs-lookup"><span data-stu-id="44da0-159">View Attract information in LinkedIn Recruiter</span></span>

<span data-ttu-id="44da0-160">A LinkedIn Recruiter megoldásban nyomon követheti, hogy pályázó jelentkezett-e a szervezeténél más állásokra, megnézheti, hogy hol tart az álláspályázatok különböző szakaszaiban, és megtekintheti az Attract visszajelzéseit és megjegyzéseit.</span><span class="sxs-lookup"><span data-stu-id="44da0-160">In LinkedIn Recruiter, you can track whether a candidate applied to other jobs in your organization, see where the candidate is in the various stages for job applications, and view feedback and comments from Attract.</span></span>

1. <span data-ttu-id="44da0-161">Nyissa meg a LinkedIn Recruiter lehetőséget, és válassza ki a pályázó profilját.</span><span class="sxs-lookup"><span data-stu-id="44da0-161">Open LinkedIn Recruiter, and select a candidate profile.</span></span>
2. <span data-ttu-id="44da0-162">Vigye az egeret az **ATS-ben** elem fölé.</span><span class="sxs-lookup"><span data-stu-id="44da0-162">Hover over **In ATS**.</span></span>
3. <span data-ttu-id="44da0-163">Válassza ki a következő lehetőségek egyikét, hogy megtekintse a jelentkezők adatait, amelyek tárolva vannak az Attract megoldásban:</span><span class="sxs-lookup"><span data-stu-id="44da0-163">Select any of the following options to view the candidate information that is stored in Attract:</span></span>

    - <span data-ttu-id="44da0-164">**Állások és állapotok** – Azokat a állásokat jeleníti meg, amelyeken a pályázó része, a legfrissebb állapotot, valamint a pályázónak az egyes állásokra vonatkozó előrehaladását.</span><span class="sxs-lookup"><span data-stu-id="44da0-164">**Jobs & Statuses** – See jobs that the candidate is part of, the latest status, and how the candidate is progressing for each job.</span></span>
    - <span data-ttu-id="44da0-165">**Interjú-visszajelzés** – Az interjúbonyolítók által az Attract rendszerébe beküldött visszajelzések megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="44da0-165">**Interview Feedback** – See feedback that interviewers have submitted in Attract.</span></span>
    - <span data-ttu-id="44da0-166">**Megjegyzések** – Tekintse meg, hogy milyen megjegyzések kerültek be ehhez a pályázóhoz az Attract megoldásban.</span><span class="sxs-lookup"><span data-stu-id="44da0-166">**Notes** – See any notes that have been entered for this candidate in Attract.</span></span>

    ![[<span data-ttu-id="44da0-167">Az Attract információinak megtekintése a LinkedIn Recruiter-szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="44da0-167">View Attract information from LinkedIn Recruiter</span></span>](./media/attract-view-information-from-linkedin-recruiter.png)](./media/attract-view-information-from-linkedin-recruiter.png)

> [!NOTE]
> <span data-ttu-id="44da0-168">A pályázó- és pályázati adatok nem lesznek szinkronizálva a LinkedIn Recruiter rendszerrel, ha a jelentkező nem lépett túl a Potenciális szakaszon.</span><span class="sxs-lookup"><span data-stu-id="44da0-168">Candidate and application data won't be synced with LinkedIn Recruiter if the candidate hasn't moved past the Prospect stage.</span></span>

## <a name="view-linkedin-talent-pools"></a><span data-ttu-id="44da0-169">LinkedIn tehetségállományok megtekintése</span><span class="sxs-lookup"><span data-stu-id="44da0-169">View LinkedIn talent pools</span></span>

<span data-ttu-id="44da0-170">Ha a jelentkezők beleegyeznek abba, hogy a saját LinkedIn-profiljaikat a szervezet bármelyik felhasználója számára megosztják, egy új pályázói rekord jön létre az Attract megoldásban.</span><span class="sxs-lookup"><span data-stu-id="44da0-170">If candidates agree to share their LinkedIn profiles with any user in your organization, a new candidate record is created in Attract.</span></span> <span data-ttu-id="44da0-171">Ezek a jelöltek ezután egy rendszer által létrehozott LinkedIn tehetségállományban jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="44da0-171">These candidates then appear in a system-created LinkedIn talent pool.</span></span>

1. <span data-ttu-id="44da0-172">A Vonzásban válassza a **tehetségállomány** lehetőséget a bal oldalon.</span><span class="sxs-lookup"><span data-stu-id="44da0-172">In Attract, select **Talent pools** on the left.</span></span>
2. <span data-ttu-id="44da0-173">Válassza ki a LinkedIn tehetségállományt.</span><span class="sxs-lookup"><span data-stu-id="44da0-173">Select the LinkedIn talent pool.</span></span> <span data-ttu-id="44da0-174">Látni fogja a jelentkezők listáját és a LinkedIn-ről származó csonka profiljaikat.</span><span class="sxs-lookup"><span data-stu-id="44da0-174">You will see a list of candidates and their stub profiles from LinkedIn.</span></span> <span data-ttu-id="44da0-175">A csonka profilok tartalmazzák a pályázó kereszt- és vezetéknevét és e-mail címét, ha a pályázó úgy döntött, hogy megosztja.</span><span class="sxs-lookup"><span data-stu-id="44da0-175">Stub profiles contain the candidate's first and last names and email address, if the candidate chose to share it.</span></span>

## <a name="see-also"></a><span data-ttu-id="44da0-176">Lásd még</span><span class="sxs-lookup"><span data-stu-id="44da0-176">See also</span></span>

[<span data-ttu-id="44da0-177">Az Attact és a LinkedIn integrációjával kapcsolatos gyakori kérdések</span><span class="sxs-lookup"><span data-stu-id="44da0-177">Attract integration with LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="44da0-178">A LinkedIn integrációjának beállítása a Microsoft Dynamics 365 Talent – Attract megoldáshoz</span><span class="sxs-lookup"><span data-stu-id="44da0-178">Set up integration with LinkedIn for Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-admin-linkedin.md)

[<span data-ttu-id="44da0-179">Állás létrehozása, jóváhagyása és feladása az Attract alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="44da0-179">Create, approve, and post jobs in Attract</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="44da0-180">Állások feladása a LinkedIn felületére a Microsoft Dynamics 365 Talent – Attract szolgáltatásból</span><span class="sxs-lookup"><span data-stu-id="44da0-180">Post jobs to LinkedIn from Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-post-jobs-to-linkedin.md)

[<span data-ttu-id="44da0-181">A LinkedIn és a Microsoft Dynamics 365 Talent – Attract közötti integráció hibaelhárítása</span><span class="sxs-lookup"><span data-stu-id="44da0-181">Troubleshooting integration with LinkedIn and Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-troubleshoot-linkedin.md)
