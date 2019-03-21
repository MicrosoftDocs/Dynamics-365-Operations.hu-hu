---
title: Attract előmeneteli webhely funkció
description: Ez a témakör áttekintést a pályázó által használt karrierwebhely funkcióiról az Attract-ban.
author: josaw1
manager: AnnBe
ms.date: 02/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-02-12
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: 087ab4034a1e601e7f3514c77d56ef54b0c5c52d
ms.sourcegitcommit: 1ee613a88edddab036d145f27f19d071a4b8ad24
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/13/2019
ms.locfileid: "389966"
---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="9a747-103">Attract előmeneteli webhely funkció</span><span class="sxs-lookup"><span data-stu-id="9a747-103">Career site functionality in Attract</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9a747-104">Ez a témakör áttekintést a pályázó által használt karrierwebhely funkcióiról a Microsoft Dynamics 365 for Talent: Attract-ban.</span><span class="sxs-lookup"><span data-stu-id="9a747-104">This topic provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="9a747-105">A funkciók beállítását is ismerteti.</span><span class="sxs-lookup"><span data-stu-id="9a747-105">It also explains how to set up this functionality.</span></span>

<span data-ttu-id="9a747-106">Az Attract egy karrierwebhelyet biztosít minden egyes környezethez a bérlőben.</span><span class="sxs-lookup"><span data-stu-id="9a747-106">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="9a747-107">Például ha egy szervezet fejlesztői környezettel és tesztkörnyezettel rendelkezik, egy karrierwebhely lesz telepítve a fejlesztői környezethez, és egy másik a tesztkörnyezethez.</span><span class="sxs-lookup"><span data-stu-id="9a747-107">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="9a747-108">Valamennyi karrierwebhely teljesen elszigetelt, és saját hitelesítési módszere van.</span><span class="sxs-lookup"><span data-stu-id="9a747-108">Each career site is completely isolated and has its own authentication mechanism.</span></span> <span data-ttu-id="9a747-109">Az állások és a jelöltprofilok nincsenek a karrierwebhelyek között megosztva.</span><span class="sxs-lookup"><span data-stu-id="9a747-109">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="9a747-110">Alapértelmezés szerint a karrierwebhely nyilvános.</span><span class="sxs-lookup"><span data-stu-id="9a747-110">By default, the career site is public.</span></span> <span data-ttu-id="9a747-111">Ezért a pályázók anélkül, hogy bejelentkeznének, megtekinthetik a külsőként megjelölt állásokat.</span><span class="sxs-lookup"><span data-stu-id="9a747-111">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="9a747-112">Minden egyéb művelethez azonban szükséges, hogy a pályázók bejelentkezzenek.</span><span class="sxs-lookup"><span data-stu-id="9a747-112">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="9a747-113">Karrierwebhely kezelése</span><span class="sxs-lookup"><span data-stu-id="9a747-113">Career site management</span></span>

<span data-ttu-id="9a747-114">Az alábbi elemek értékének beállításához jelentkezzen be az Attract rendszerébe rendszergazdaként, válassza az **Adminisztrációs központ** lehetőséget a **Beállítások** menüben (fogaskerék szimbólum), és válassza ki a **Vállalati adatok** lapot.</span><span class="sxs-lookup"><span data-stu-id="9a747-114">To set the values for the following items, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

-   <span data-ttu-id="9a747-115">**Szervezet neve:** – A szervezet neve megjelenik az előmeneteli webhely felső navigációs sávján.</span><span class="sxs-lookup"><span data-stu-id="9a747-115">**Organization name** - The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="9a747-116">A szervezet nevének kiválasztásával a jelentkezők az összes nyitott állást felsoroló lapra ugranak.</span><span class="sxs-lookup"><span data-stu-id="9a747-116">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>

-   <span data-ttu-id="9a747-117">**Szervezet emblémája** – A cég emblémájának képe a bal felső részén jelenik meg az előmeneteli webhelynek.</span><span class="sxs-lookup"><span data-stu-id="9a747-117">**Organization logo** - An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="9a747-118">Az emlémakép kiválasztásával a jelentkezők az összes nyitott állást felsoroló lapra ugranak.</span><span class="sxs-lookup"><span data-stu-id="9a747-118">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

    >   [!NOTE] 
    >   <span data-ttu-id="9a747-119">A karrierwebhelyen megjelenő emblémához 20 képpont rögzített magasság tartozik.</span><span class="sxs-lookup"><span data-stu-id="9a747-119">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="9a747-120">Az Adminisztrációs központban felvett kép át lesz méretezve, hogy elférjen.</span><span class="sxs-lookup"><span data-stu-id="9a747-120">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="9a747-121">Ezért, a képtől függően a kép szélessége megváltozhat.</span><span class="sxs-lookup"><span data-stu-id="9a747-121">Therefore, depending on the image, the width might change.</span></span>
 
<span data-ttu-id="9a747-122">Az alábbi elemek értékének beállításához jelentkezzen be az Attract rendszerébe rendszergazdaként, válassza az **Adminisztrációs központ** lehetőséget a **Beállítások** menüben, és válassza ki a **Karrieroldal kezelése** lapot.</span><span class="sxs-lookup"><span data-stu-id="9a747-122">To set the values for the following items, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu, and then select the **Career site management** tab.</span></span>

-   <span data-ttu-id="9a747-123">**Keresőmotor optimalizálása** -Ha engedélyezve van, az Attract karrierwebhelyre feladott összes nyilvános állás kereshető keresőmotorok, Bing és Google segítségével.</span><span class="sxs-lookup"><span data-stu-id="9a747-123">**Search Engine Optimization** - When enabled, all public jobs posted to Attract career site will be searchable using search engines like Bing and Google.</span></span>

    >   [!NOTE] 
    >   <span data-ttu-id="9a747-124">A beállítás bekapcsolása és a keresési eredmények megjelenése között eltelhet egy kis idő, és attól függően, hogy milyen keresőmotor használ.</span><span class="sxs-lookup"><span data-stu-id="9a747-124">There might be a delay between turning this setting on and search results appearing, depending on the search engine that you are using.</span></span>
         
## <a name="career-site-urls"></a><span data-ttu-id="9a747-125">Karrierwebhely URL-címek</span><span class="sxs-lookup"><span data-stu-id="9a747-125">Career site URLs</span></span>

<span data-ttu-id="9a747-126">Az alábbi lista a gyakran használt karrierwebhely URL-címeket és azok elérési módját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="9a747-126">The following list contains the commonly used career site URLs and how to access them.</span></span>

-   <span data-ttu-id="9a747-127">**Karrierwebhely kezdőlapjának URL-címe** – A karrierwebhely kezdőlapja URL-címének megtekintéséhez, jelentkezzen be az Attract-be rendszergazdaként, válassza a **Felügyeleti központ** lehetőséget **Beállítások** menüben, és válassza a **Karrieroldal kezelése** lapot.</span><span class="sxs-lookup"><span data-stu-id="9a747-127">**Career site home page URL** - To view the career site home page URL, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu, and then select the **Career site management** tab.</span></span>

-   <span data-ttu-id="9a747-128">**Egyéni álláshirdetés jelentkezési URL-címe** [Ha első alkalommal ad fel egy külső állást](Creating-jobs-Attract.md#postings) át lehet másolni a **Jelentkezés** hivatkozást az Attract alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="9a747-128">**Individual job post apply URL** - When you [post an external job](Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="9a747-129">A hivatkozás URL-cím formátuma a következő lesz: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)</span><span class="sxs-lookup"><span data-stu-id="9a747-129">The URL for this link will be in the following format: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>/apply](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e/apply)</span></span>

-   <span data-ttu-id="9a747-130">**Egyéni álláshirdetés URL-címe** – Az álláshirdetés URL-címe a Jelentkezés URL-cím alkarakterlánca.</span><span class="sxs-lookup"><span data-stu-id="9a747-130">**Individual job post URL** - The URL of the job post is a substring of the Apply URL.</span></span> <span data-ttu-id="9a747-131">Mindent tartalmaz a munkaszámig.</span><span class="sxs-lookup"><span data-stu-id="9a747-131">It consists of everything up through the job number.</span></span> <span data-ttu-id="9a747-132">Emiatt az előző Jelentkezés URL-címnél az álláshirdetés URL-címe: [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)</span><span class="sxs-lookup"><span data-stu-id="9a747-132">Therefore, for the preceding Apply URL, the job post URL is [https://jobs.talent.dynamics.com/jobs/\<company_name\>/\<environment_number\>/\<job_number\>](https://jobs.talent.dynamics.com/jobs/%3ccompany_name%3e/%3cenvironment_number%3e/%3cjob_number%3e)</span></span>

## <a name="authentication-options"></a><span data-ttu-id="9a747-133">Hitelesítési lehetőségek</span><span class="sxs-lookup"><span data-stu-id="9a747-133">Authentication options</span></span>

<span data-ttu-id="9a747-134">A pályázók bejelentkezési lehetőségei az Attract karrierwebhelyen a következők:</span><span class="sxs-lookup"><span data-stu-id="9a747-134">Candidates have the following sign-in options for an Attract career site:</span></span>

-   <span data-ttu-id="9a747-135">Személyes fiók:</span><span class="sxs-lookup"><span data-stu-id="9a747-135">Personal account:</span></span>

    -   <span data-ttu-id="9a747-136">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="9a747-136">LinkedIn</span></span>

    -   <span data-ttu-id="9a747-137">Microsoft</span><span class="sxs-lookup"><span data-stu-id="9a747-137">Microsoft</span></span>

    -   <span data-ttu-id="9a747-138">Google</span><span class="sxs-lookup"><span data-stu-id="9a747-138">Google</span></span>

    -   <span data-ttu-id="9a747-139">Facebook</span><span class="sxs-lookup"><span data-stu-id="9a747-139">Facebook</span></span>

-   <span data-ttu-id="9a747-140">Munkahelyi vagy iskolai fiók:</span><span class="sxs-lookup"><span data-stu-id="9a747-140">Work or school account:</span></span>

    -   <span data-ttu-id="9a747-141">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="9a747-141">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="9a747-142">Az Azure AD-bejelentkezés csak belső pályázók számára készült.</span><span class="sxs-lookup"><span data-stu-id="9a747-142">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="9a747-143">Ennek megfelelően csak a belső pályázóknál működik, akik a vállalat Azure AD hitelesítő adatait használják.</span><span class="sxs-lookup"><span data-stu-id="9a747-143">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="9a747-144">Például a pályázó jelenleg a Contoso Kft alkalmazottja, és jelentkezni szeretne egy állásra az Alpine Ski House független vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="9a747-144">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="9a747-145">Ebben az esetben a bejelentkezés sikertelen lesz, ha az alkalmazott megkísérli Contoso Kft Azure AD hitelesítő adatait használni.</span><span class="sxs-lookup"><span data-stu-id="9a747-145">In this case, the sign-in will be unsuccessful if the employee tries to use Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="9a747-146">Profil létrehozása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="9a747-146">Create and maintain a profile</span></span>

<span data-ttu-id="9a747-147">Miután a pályázók bejelentkeztek a karrierwebhelyre, kiválaszthatják a **Saját profilt** a lap felső navigációs sávján a saját profil létrehozásához és karbantartásához.</span><span class="sxs-lookup"><span data-stu-id="9a747-147">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span>
<span data-ttu-id="9a747-148">A profil tartalmaz személyes adatokat, gyakorlattal kapcsolatos információkat, tanulmányokat, dokumentumokat, hivatkozásokat, képzettséggel kapcsolatos adatokat.</span><span class="sxs-lookup"><span data-stu-id="9a747-148">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="9a747-149">A profilt a létrehozása után alkalmazni lehet a jelentkezőt érdeklő állásokra való jelentkezésre.</span><span class="sxs-lookup"><span data-stu-id="9a747-149">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="9a747-150">A profilok segítségével a megfelelő állásokra javasol jelölteket az Attrat.</span><span class="sxs-lookup"><span data-stu-id="9a747-150">Profiles also help Attract recommend the right jobs to candidates.</span></span>

>   [!NOTE]
>   <span data-ttu-id="9a747-151">Ha pályázó által használt egy e-mailes azonosítót használ a bejelentkezéshez a fenti hitelesítési szolgáltatók valamelyikének használatával, ez az e-mail-azonosító lesz a profilhoz társított alapértelmezett e-mail-azonosító.</span><span class="sxs-lookup"><span data-stu-id="9a747-151">If a candidate uses an email ID to sign in using one of the authentication providers listed above, that email ID will default to the contact email ID associated with the profile.</span></span> <span data-ttu-id="9a747-152">Azonban az utóbbi bármikor módosítható, és teljesen független az előzőtől.</span><span class="sxs-lookup"><span data-stu-id="9a747-152">However, the latter can be changed at any time and is completely independent of the former.</span></span> <span data-ttu-id="9a747-153">Az Attract mindig a kapcsolattartói e-mail-azonosítót használja, hogy társítsa profilját minden e-mail kommunikációval.</span><span class="sxs-lookup"><span data-stu-id="9a747-153">Attract will always use the contact email ID to associate with your profile for all email communications.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="9a747-154">A megfelelő állás keresése</span><span class="sxs-lookup"><span data-stu-id="9a747-154">Find the right job</span></span>

<span data-ttu-id="9a747-155">Az állás listaoldalon a pályázók kereshetnek egy bizonyos állást keresési feltételek megadásával.</span><span class="sxs-lookup"><span data-stu-id="9a747-155">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="9a747-156">A keresési funkció a beosztásokban és munkaköri leírásokban keresőszavakat keres, és a megfelelő állásokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="9a747-156">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="9a747-157">A pályázók szűrhetik az eredményeket bármikor, beosztási funkció vagy a feladat helye alapján.</span><span class="sxs-lookup"><span data-stu-id="9a747-157">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="9a747-158">A pályázók ajánlott állásokat is megtekinthetnek a karrierwebhelyen.</span><span class="sxs-lookup"><span data-stu-id="9a747-158">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="9a747-159">Az állások, amelyek a pályázóknak javasoltak, a jelölt múltbeli pályázatain, profilján és önéletrajzán alapulnak.</span><span class="sxs-lookup"><span data-stu-id="9a747-159">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

>   [!NOTE] 
>   <span data-ttu-id="9a747-160">Csak akkor jelennek meg javaslatok, ha legalább 10 állást adtak fel a karrierwebhelyen, és a jelentkező profilja kész van.</span><span class="sxs-lookup"><span data-stu-id="9a747-160">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed a profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="9a747-161">Jelentkezés állásokra</span><span class="sxs-lookup"><span data-stu-id="9a747-161">Apply for jobs</span></span>

<span data-ttu-id="9a747-162">Miután a jelölt megtalálta a megfelelő állást, jelentkezhet a **Jelentkezés** gombbal az **Állás részletei** lapon.</span><span class="sxs-lookup"><span data-stu-id="9a747-162">After candidates find the right job, they can apply by using the **Apply** button on the **Job details** page.</span></span> <span data-ttu-id="9a747-163">Ezen a ponton a pályázók új profilt hozhatnak létre, vagy áttekinthetik a meglévő profil információit.</span><span class="sxs-lookup"><span data-stu-id="9a747-163">At this point, candidates can either create a new profile or review the information in their existing profile.</span></span>
<span data-ttu-id="9a747-164">A pályázó feltölthet önéletrajzot, szükség szerint, majd küldje el a jelentkezést az állásra.</span><span class="sxs-lookup"><span data-stu-id="9a747-164">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="9a747-165">Pályázat állapotának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="9a747-165">Check application status</span></span>

<span data-ttu-id="9a747-166">Egy vagy több állásra való pályázás után a jelentkező kiválaszthatja a **Jelentkezések** lehetőséget az oldal felső navigációs sávján, hogy megtekintse a nyitott és lezárt jelentkezéseket.</span><span class="sxs-lookup"><span data-stu-id="9a747-166">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="9a747-167">Amikor a pályázó megnyit egy jelentkezést, látja a jelenlegi szakaszt és minden függőben lévő teendőt, amelyet ki kell töltenie.</span><span class="sxs-lookup"><span data-stu-id="9a747-167">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="9a747-168">Például ha egy potenciális személyes interjú dátumát kell megadni, a lapon láthatók az elérhető lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="9a747-168">For example, if a candidate must provide potential dates for an in-person interview, the page shows the available options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="9a747-169">Belső állások</span><span class="sxs-lookup"><span data-stu-id="9a747-169">Internal jobs</span></span>

<span data-ttu-id="9a747-170">Jelenleg a belsőnek megjelölt, és az Attract karrierwebhelyre feladott állások nem jelennek meg a karrierwebhelyen.</span><span class="sxs-lookup"><span data-stu-id="9a747-170">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="9a747-171">Csak a közvetlen **Jelentkezés** URL-címen hozzáférhetők, amely átmásolható az Attract alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="9a747-171">They are only accessible using the direct **Apply** URL that can be copied from the Attract application.</span></span>
