---
title: "Attract előmeneteli webhely funkció"
description: "A cikk a Microsoft Dynamics 365 for Talent - Attract jelöltek számára rendelkezésre álló karrierwebhely funkcióit ismerteti. A funkciók beállítását is ismerteti."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: hu-hu
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="7c44f-104">Attract előmeneteli webhely funkció</span><span class="sxs-lookup"><span data-stu-id="7c44f-104">Career site functionality in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7c44f-105">A cikk a Microsoft Dynamics 365 for Talent - Attract jelöltek számára rendelkezésre álló karrierwebhely funkcióit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="7c44f-105">This article provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="7c44f-106">A funkciók beállítását is ismerteti.</span><span class="sxs-lookup"><span data-stu-id="7c44f-106">It also explains how to set up this functionality.</span></span>

## <a name="overview"></a><span data-ttu-id="7c44f-107">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="7c44f-107">Overview</span></span>

<span data-ttu-id="7c44f-108">Az Attract egy előmeneteli webhelyet biztosít a bérlőnek minden egyes környezetben.</span><span class="sxs-lookup"><span data-stu-id="7c44f-108">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="7c44f-109">Például ha egy szervezet fejlesztői környezettel és tesztkörnyezettel rendelkezik, egy előmeneteli webhely lesz telepítve a fejlesztői környezethez, és egy másik a tesztkörnyezethez.</span><span class="sxs-lookup"><span data-stu-id="7c44f-109">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="7c44f-110">Valamennyi előmeneteli webhely **teljesen elszigetelt**, és saját hitelesítési módszere van.</span><span class="sxs-lookup"><span data-stu-id="7c44f-110">Each career site is **completely isolated** and has its own authentication mechanism.</span></span> <span data-ttu-id="7c44f-111">Az állások és a jelöltprofilok nincsenek az előmeneteli webhelyek között megosztva.</span><span class="sxs-lookup"><span data-stu-id="7c44f-111">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="7c44f-112">Alapértelmezés szerint az előmeneteli webhely nyilvános.</span><span class="sxs-lookup"><span data-stu-id="7c44f-112">By default, the career site is public.</span></span> <span data-ttu-id="7c44f-113">Ezért a pályázók anélkül, hogy bejelentkeznének, megtekinthetik a külsőként megjelölt állásokat.</span><span class="sxs-lookup"><span data-stu-id="7c44f-113">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="7c44f-114">Minden egyéb művelethez azonban szükséges, hogy a pályázók bejelentkezzenek.</span><span class="sxs-lookup"><span data-stu-id="7c44f-114">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="7c44f-115">Karrierwebhely kezelése</span><span class="sxs-lookup"><span data-stu-id="7c44f-115">Career site management</span></span>

<span data-ttu-id="7c44f-116">A következő elemek az előmeneteli webhelyen beállításokkal szabályozottak:</span><span class="sxs-lookup"><span data-stu-id="7c44f-116">The following items on the career site are controlled by settings:</span></span>

- <span data-ttu-id="7c44f-117">**Szervezet neve:** A szervezet neve megjelenik az előmeneteli webhely felső navigációs sávján.</span><span class="sxs-lookup"><span data-stu-id="7c44f-117">**Organization name:** The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="7c44f-118">A szervezet nevének kiválasztásával a jelentkezők az összes nyitott állást felsoroló lapra ugranak.</span><span class="sxs-lookup"><span data-stu-id="7c44f-118">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>
- <span data-ttu-id="7c44f-119">**Szervezet emblémája:** A cég emblémájának képe a bal felső részén jelenik meg az előmeneteli webhelynek.</span><span class="sxs-lookup"><span data-stu-id="7c44f-119">**Organization logo:** An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="7c44f-120">Az emlémakép kiválasztásával a jelentkezők az összes nyitott állást felsoroló lapra ugranak.</span><span class="sxs-lookup"><span data-stu-id="7c44f-120">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

<span data-ttu-id="7c44f-121">A szervezet neve és az embléma értékének beállításához jelentkezzen be az Attract rendszerébe rendszergazdaként, válassza az **Adminisztrációs központ** lehetőséget a **Beállítások** menüben (fogaskerék szimbólum), és válassza ki a **Vállalati adatok** lapot.</span><span class="sxs-lookup"><span data-stu-id="7c44f-121">To set the values for the organization name and logo, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="7c44f-122">A előmeneteli webhelyen megjelenő emblémához 20 képpont rögzített magasság tartozik.</span><span class="sxs-lookup"><span data-stu-id="7c44f-122">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="7c44f-123">Az Adminisztrációs központban felvett kép át lesz méretezve, hogy elférjen.</span><span class="sxs-lookup"><span data-stu-id="7c44f-123">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="7c44f-124">Ezért a kép szélessége megváltozhat.</span><span class="sxs-lookup"><span data-stu-id="7c44f-124">Therefore, depending on the image, the width might change.</span></span>

## <a name="career-site-url"></a><span data-ttu-id="7c44f-125">Karrierwebhely URL-címe</span><span class="sxs-lookup"><span data-stu-id="7c44f-125">Career site URL</span></span>

<span data-ttu-id="7c44f-126">Ha első alkalommal [ad fel egy külső állást](./Creating-jobs-Attract.md#postings) át lehet másolni a **Jelentkezés** hivatkozást az Attract alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="7c44f-126">When you [post an external job](./Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="7c44f-127">A hivatkozás URL-cím formátuma a következő lesz: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span><span class="sxs-lookup"><span data-stu-id="7c44f-127">The URL for this link will be in the following format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span></span>

<span data-ttu-id="7c44f-128">Az URL-címe az előmeneteli webhelynek egy részét az **Jelentkezés** URL-címnek.</span><span class="sxs-lookup"><span data-stu-id="7c44f-128">The URL of the career site is a substring of the **Apply** URL.</span></span> <span data-ttu-id="7c44f-129">Mindent tartalmaz a vállalat nevéig.</span><span class="sxs-lookup"><span data-stu-id="7c44f-129">It consists of everything up through the company name.</span></span> <span data-ttu-id="7c44f-130">Emiatt az előző **Jelentkezés** URL-címnél az előmeneteli webhely URL-címe: `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span><span class="sxs-lookup"><span data-stu-id="7c44f-130">Therefore, for the preceding **Apply** URL, the career site URL is `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span></span>

## <a name="authentication-options"></a><span data-ttu-id="7c44f-131">Hitelesítési lehetőségek</span><span class="sxs-lookup"><span data-stu-id="7c44f-131">Authentication options</span></span>

<span data-ttu-id="7c44f-132">A pályázók bejelentkezési lehetőségei az Attract előmeneteli webhelyen a következők:</span><span class="sxs-lookup"><span data-stu-id="7c44f-132">Candidates have the following sign-in options for an Attract career site:</span></span>

- <span data-ttu-id="7c44f-133">Személyes fiók:</span><span class="sxs-lookup"><span data-stu-id="7c44f-133">Personal account:</span></span>

    - <span data-ttu-id="7c44f-134">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7c44f-134">LinkedIn</span></span>
    - <span data-ttu-id="7c44f-135">Microsoft</span><span class="sxs-lookup"><span data-stu-id="7c44f-135">Microsoft</span></span>
    - <span data-ttu-id="7c44f-136">Google</span><span class="sxs-lookup"><span data-stu-id="7c44f-136">Google</span></span>
    - <span data-ttu-id="7c44f-137">Facebook</span><span class="sxs-lookup"><span data-stu-id="7c44f-137">Facebook</span></span>

- <span data-ttu-id="7c44f-138">Munkahelyi vagy iskolai fiók:</span><span class="sxs-lookup"><span data-stu-id="7c44f-138">Work or school account:</span></span>

    - <span data-ttu-id="7c44f-139">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="7c44f-139">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="7c44f-140">Az Azure Active Directory-bejelentkezés csak belső pályázók számára készült.</span><span class="sxs-lookup"><span data-stu-id="7c44f-140">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="7c44f-141">Ennek megfelelően csak a belső pályázóknál működik, akik a vállalat Azure Active Directory hitelesítő adatait használják.</span><span class="sxs-lookup"><span data-stu-id="7c44f-141">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="7c44f-142">Például a pályázó jelenleg a Contoso Kft alkalmazottja, és jelentkezni szeretne egy állásra az Alpine Ski House független vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="7c44f-142">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="7c44f-143">Ebben az esetben a bejelentkezés sikertelen lesz, ha az alkalmazott megkísérli Contoso Kft-s Azure Active Directory hitelesítő adatait használni.</span><span class="sxs-lookup"><span data-stu-id="7c44f-143">In this case, the sign-in will be unsuccessful if the employee tries to use his or her Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="7c44f-144">Profil létrehozása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="7c44f-144">Create and maintain a profile</span></span>

<span data-ttu-id="7c44f-145">Miután a pályázók bejelentkeztek az előmeneteli webhelyre, kiválaszthatják a **Saját profilt** a lap felső navigációs sávján a saját profil létrehozásához és karbantartásához.</span><span class="sxs-lookup"><span data-stu-id="7c44f-145">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span> <span data-ttu-id="7c44f-146">A profil tartalmaz személyes adatokat, gyakorlattal kapcsolatos információkat, tanulmányokat, dokumentumokat, hivatkozásokat, képzettséggel kapcsolatos adatokat.</span><span class="sxs-lookup"><span data-stu-id="7c44f-146">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="7c44f-147">A profilt a létrehozása után alkalmazni lehet a jelentkezőt érdeklő állásokra való jelentkezésre.</span><span class="sxs-lookup"><span data-stu-id="7c44f-147">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="7c44f-148">A profilok segítségével a megfelelő állásokra javasol jelölteket az Attrat.</span><span class="sxs-lookup"><span data-stu-id="7c44f-148">Profiles also help Attract recommend the right jobs to candidates.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="7c44f-149">A megfelelő állás keresése</span><span class="sxs-lookup"><span data-stu-id="7c44f-149">Find the right job</span></span>

<span data-ttu-id="7c44f-150">Az állás listaoldalon a pályázók kereshetnek egy bizonyos állást keresési feltételek megadásával.</span><span class="sxs-lookup"><span data-stu-id="7c44f-150">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="7c44f-151">A keresési funkció a beosztásokban és munkakörökben keresőszavakat keres, és a megfelelő állásokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="7c44f-151">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="7c44f-152">A pályázók szűrhetik az eredményeket bármikor, beosztási funkció vagy a feladat helye alapján.</span><span class="sxs-lookup"><span data-stu-id="7c44f-152">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="7c44f-153">A pályázók ajánlott állásokat is megtekinthetnek az előmeneteli webhelyen.</span><span class="sxs-lookup"><span data-stu-id="7c44f-153">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="7c44f-154">Az állások, amelyek a pályázóknak javasoltak, a jelölt múltbeli pályázatain, profilján és önéletrajzán alapulnak.</span><span class="sxs-lookup"><span data-stu-id="7c44f-154">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

> [!NOTE]
> <span data-ttu-id="7c44f-155">Csak akkor jelennek meg javaslatok, ha legalább 10 állást adtak fel az előmeneteli webhelyen, és a jelentkező profilja kész van.</span><span class="sxs-lookup"><span data-stu-id="7c44f-155">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed his or her profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="7c44f-156">Pályázat állásokra</span><span class="sxs-lookup"><span data-stu-id="7c44f-156">Apply for jobs</span></span>

<span data-ttu-id="7c44f-157">Miután a jelölt megtalálta a megfelelő állást, jelentkezhet a **Jelentkezés** gombbal az állás részletes adatai lapon.</span><span class="sxs-lookup"><span data-stu-id="7c44f-157">After candidates find the right job, they can apply by using the **Apply** button on the job details page.</span></span> <span data-ttu-id="7c44f-158">Ezen a ponton a pályázók vadonatúj profilt hozhatnak létre, vagy áttekinthetik a meglévő profil információit.</span><span class="sxs-lookup"><span data-stu-id="7c44f-158">At this point, candidates can either create a brand-new profile or review the information in their existing profile.</span></span> <span data-ttu-id="7c44f-159">A pályázó feltölthet önéletrajzot, szükség szerint, majd küldje el a jelentkezést az állásra.</span><span class="sxs-lookup"><span data-stu-id="7c44f-159">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="7c44f-160">Pályázat állapotának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="7c44f-160">Check application status</span></span>

<span data-ttu-id="7c44f-161">Egy vagy több állára való pályázás után a jelentkező kiválaszthatja a **Jelentkezések** lehetőséget az oldal felső navigációs sávján, hogy megtekintse a nyitott és lezárt jelentkezéseket.</span><span class="sxs-lookup"><span data-stu-id="7c44f-161">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="7c44f-162">Pályázók nyissa meg egy jelentkezést, látják a jelenlegi szakaszt és minden függőben lévő teendők, amelyet ki kell tölteniük.</span><span class="sxs-lookup"><span data-stu-id="7c44f-162">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="7c44f-163">Például ha egy potenciális személyes interjú dátumát kell megadni, a lapon láthatók a lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="7c44f-163">For example, if a candidate must provide potential dates for an in-person interview, the page shows his or her options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="7c44f-164">Belső állások</span><span class="sxs-lookup"><span data-stu-id="7c44f-164">Internal jobs</span></span>

<span data-ttu-id="7c44f-165">Jelenleg a belső, és az Attract előmeneteli webhelyre feladott állások nem jelennek meg az előmeneteli webhelyen.</span><span class="sxs-lookup"><span data-stu-id="7c44f-165">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="7c44f-166">Csak a közvetlen **Jelentkezés** URL-címen keresztül hozzáférhetők, amely átmásolható az Attract alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="7c44f-166">They are accessible only via the direct **Apply** URL that can be copied from the Attract application.</span></span>

