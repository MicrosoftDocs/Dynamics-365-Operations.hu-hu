---
title: Analitikus jelentések használata a toborzási folyamattal kapcsolatos információk érdekében
description: Ez a témakör az Attract analitikus jelentéseiről szól
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 33ed6072a9ad99144fb96ad19389a57461324f71
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1516560"
---
# <a name="use-analytic-reports-for-hiring-process-insights"></a><span data-ttu-id="602e7-103">Analitikus jelentések használata a toborzási folyamattal kapcsolatos információk érdekében</span><span class="sxs-lookup"><span data-stu-id="602e7-103">Use analytic reports for hiring process insights</span></span>

<span data-ttu-id="602e7-104">Az Attract analitikus jelentései egy beépített (OOTB) megoldást biztosítanak a felvételi folyamat háttérinformációihoz.</span><span class="sxs-lookup"><span data-stu-id="602e7-104">Analytic reports in Attract provide an out-of-the-box (OOTB) solution for hiring process insights.</span></span> <span data-ttu-id="602e7-105">A rendelkezésre álló funkciók a következők:</span><span class="sxs-lookup"><span data-stu-id="602e7-105">Availabe features include:</span></span>

- <span data-ttu-id="602e7-106">**Álláselemzés** – Kattintson egy állás **Elemzés** lapjára, és megtekintheti az állás pályázójára vonatkozó mutatókat.</span><span class="sxs-lookup"><span data-stu-id="602e7-106">**Job analytics:** Click the **Analytics** tab within a job for metrics on the job's applicants.</span></span>
- <span data-ttu-id="602e7-107">**Elemzési központ:** Kattintson a bal oldali navigációs menüben az **Elemzés** pontra az állások összesített mutatóiért.</span><span class="sxs-lookup"><span data-stu-id="602e7-107">**Analytics hub:** Click **Analytics** on the left navigation for aggregated metrics across jobs.</span></span>
- <span data-ttu-id="602e7-108">**Felhasználói szintű biztonság:** A jelentésekhez való hozzáférést az Attract [szerepköre](security-attract.md) és az állás résztvevőjének szerepköre szabályozza.</span><span class="sxs-lookup"><span data-stu-id="602e7-108">**User-specific security:** Access to reports is controlled by Attract [role](security-attract.md) and job participant role.</span></span>
- <span data-ttu-id="602e7-109">**Keresztszűrés:** A jelentésen belül a vizuális elemekre kattintva megtekinthet további mutatókat a kijelölt adat szerint szűrve.</span><span class="sxs-lookup"><span data-stu-id="602e7-109">**Cross-filtering:** Click visuals within a report to view other metrics filtered by selected data.</span></span>

>[!NOTE] 
>- <span data-ttu-id="602e7-110">Ez a funkció jelenleg [előzetes verzióban](access-preview-feature.md) elérhető.</span><span class="sxs-lookup"><span data-stu-id="602e7-110">This feature is currently in [preview](access-preview-feature.md).</span></span> <span data-ttu-id="602e7-111">Ha ki szeretné próbálni, rendelkeznie kell az [**Átfogó felvételi bővítménnyel**](attract-comprehensive-hiring.md).</span><span class="sxs-lookup"><span data-stu-id="602e7-111">To try it, you must have the [**Comprehensive Hiring Add-On**](attract-comprehensive-hiring.md).</span></span>
>- <span data-ttu-id="602e7-112">Az összes nyilvános előzetes jelentés angolul jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="602e7-112">All public preview reports are displayed in English.</span></span>
>- <span data-ttu-id="602e7-113">A jelentések 3 óránként frissülnek.</span><span class="sxs-lookup"><span data-stu-id="602e7-113">Reports refresh every 3 hours.</span></span> <span data-ttu-id="602e7-114">A jelentés felső részén található a legutóbbi frissítési idő (a helyi időzónában).</span><span class="sxs-lookup"><span data-stu-id="602e7-114">The last refresh time (in the local timezone) is located at the top of the report.</span></span> <span data-ttu-id="602e7-115">A frissítési idők becsült értékek, és a régióban használt adatmennyiségtől és erőforrás-terheléstől is függenek.</span><span class="sxs-lookup"><span data-stu-id="602e7-115">Refresh times are an approximation and vary based on data volume and resource load in your region.</span></span>

## <a name="job-analytics"></a><span data-ttu-id="602e7-116">Állással kapcsolatos elemzések</span><span class="sxs-lookup"><span data-stu-id="602e7-116">Job Analytics</span></span>

<span data-ttu-id="602e7-117">Az Álláselemzési jelentések pillanatképet biztosítanak egy állás felvételi folyamatáról.</span><span class="sxs-lookup"><span data-stu-id="602e7-117">Job Analytics reports are a snapshot of the hiring process for a job.</span></span>  <span data-ttu-id="602e7-118">A fő mutatók a következők:</span><span class="sxs-lookup"><span data-stu-id="602e7-118">Key metrics include:</span></span>

- <span data-ttu-id="602e7-119">Aktív pályázók fokozat szerint</span><span class="sxs-lookup"><span data-stu-id="602e7-119">Active applicants by stage</span></span>
- <span data-ttu-id="602e7-120">Pályázó forrása</span><span class="sxs-lookup"><span data-stu-id="602e7-120">Applicant source</span></span>
- <span data-ttu-id="602e7-121">Pályázó típusa (belső vagy külső)</span><span class="sxs-lookup"><span data-stu-id="602e7-121">Applicant type (internal or external)</span></span>

## <a name="analytics-hub"></a><span data-ttu-id="602e7-122">Elemzési központ</span><span class="sxs-lookup"><span data-stu-id="602e7-122">Analytics Hub</span></span>

<span data-ttu-id="602e7-123">Az Elemzési központ jelentések aggregálják az állások adatait, és így kimutatják a felvételi folyamat trendjeit.</span><span class="sxs-lookup"><span data-stu-id="602e7-123">Analytics Hub reports aggregate data across jobs to surface trends in the hiring process.</span></span> <span data-ttu-id="602e7-124">A program két beépített jelentést tartalmaz: a prognózis összegzése és a tölcsérelemzés.</span><span class="sxs-lookup"><span data-stu-id="602e7-124">Attract includes two OOTB reports: Pipeline Summary and Funnel Analysis.</span></span>

### <a name="pipeline-summary"></a><span data-ttu-id="602e7-125">Értékesítési prognózis összegzése</span><span class="sxs-lookup"><span data-stu-id="602e7-125">Pipeline Summary</span></span>

<span data-ttu-id="602e7-126">A prognózisösszesítő jelentés összesíti a nyitott állások adatait.</span><span class="sxs-lookup"><span data-stu-id="602e7-126">The Pipeline Summary report aggregates data for open jobs.</span></span> <span data-ttu-id="602e7-127">A fő mutatók a következők:</span><span class="sxs-lookup"><span data-stu-id="602e7-127">Key metrics include:</span></span>

- <span data-ttu-id="602e7-128">Bármely állás pályázói fokozat szerint</span><span class="sxs-lookup"><span data-stu-id="602e7-128">Applicants across all jobs by stage</span></span>
- <span data-ttu-id="602e7-129">Pályázó forrása</span><span class="sxs-lookup"><span data-stu-id="602e7-129">Applicant source</span></span>
- <span data-ttu-id="602e7-130">Nyitott állások a szolgálati idő szintje szerint</span><span class="sxs-lookup"><span data-stu-id="602e7-130">Open jobs by seniority level</span></span>

### <a name="funnel-analysis"></a><span data-ttu-id="602e7-131">Tölcsérelemzés</span><span class="sxs-lookup"><span data-stu-id="602e7-131">Funnel Analysis</span></span>

<span data-ttu-id="602e7-132">A tölcsérelemzési jelentés összesíti a betöltöttként lezárt állások adatait.</span><span class="sxs-lookup"><span data-stu-id="602e7-132">The Funnel Analysis report aggregates data for jobs that have been closed as filled.</span></span> <span data-ttu-id="602e7-133">A fő mutatók a következők:</span><span class="sxs-lookup"><span data-stu-id="602e7-133">Key metrics include:</span></span>

- <span data-ttu-id="602e7-134">Felvétel időpontja</span><span class="sxs-lookup"><span data-stu-id="602e7-134">Time to hire</span></span>
- <span data-ttu-id="602e7-135">Konverziós mutatók (rámutatáskor)</span><span class="sxs-lookup"><span data-stu-id="602e7-135">Conversion metrics (on hover)</span></span>
- <span data-ttu-id="602e7-136">Ajánlat elfogadási rátája</span><span class="sxs-lookup"><span data-stu-id="602e7-136">Offer acceptance rate</span></span>

<span data-ttu-id="602e7-137">Megjegyzés: A felvételi jelentés legpontosabb időpontjának érdekében javasoljuk, hogy használja az [Ajánlatkezelés](offer-setup.md) funkciót, amely az Átfogó felvételi bővítmény részeként elérhető.</span><span class="sxs-lookup"><span data-stu-id="602e7-137">Note: For the most accurate time to hire reporting, it is recommended that you use [Offer management](offer-setup.md), a feature available as part of the Comprehensive Hiring Add-On.</span></span>

>[!TIP] 
><span data-ttu-id="602e7-138">További információért vigye az egérmutatót a vizuális elemek fölé.</span><span class="sxs-lookup"><span data-stu-id="602e7-138">Try hovering over visuals for additional information.</span></span> <span data-ttu-id="602e7-139">Például ha egérre rámutat az **Aktív pályázók** elemre, a vizuális elemek megmutatják a fokozaton töltött napok átlagos számát.</span><span class="sxs-lookup"><span data-stu-id="602e7-139">For example, hovering over **Active applicants** visuals will display the average days in stage.</span></span> <span data-ttu-id="602e7-140">Ezen információk elemzése kritikus fontosságú információkat nyújthat a felvétel idejének lecsökkentéséhez, és lehetővé teszi, hogy a toborzók olyan módszerekre koncentráljanak, amelyek lecsökkentik az egyes fokozatokon töltött időt.</span><span class="sxs-lookup"><span data-stu-id="602e7-140">Analyzing this information can provide insights critical to reducing time to hire and enable recruiters to focus on ways to reduce the time spent in each stage.</span></span>

## <a name="user-specific-security"></a><span data-ttu-id="602e7-141">Felhasználóspecifikus biztonság</span><span class="sxs-lookup"><span data-stu-id="602e7-141">User-specific security</span></span>

<span data-ttu-id="602e7-142">Az Attract-jelentések Rendszergazda, Minden olvasása, Toborzó és Felvételi vezető [szerepkörrel](security-attract.md) rendelkezők számára hozzáférhetők.</span><span class="sxs-lookup"><span data-stu-id="602e7-142">Attract reports are accessible for Admin, Read All, Recruiter, and Hiring Manager [roles](security-attract.md).</span></span> <span data-ttu-id="602e7-143">A nem hozzárendelt felhasználók nem férhetnek hozzá a elemzési jelentés oldalaihoz (az Állás elemzése és az Elemzési központ oldalakhoz).</span><span class="sxs-lookup"><span data-stu-id="602e7-143">Unassigned users do not have access to either of the analytic report pages (Job Analytics or Analytics Hub).</span></span>

<span data-ttu-id="602e7-144">Az Álláselemzés jelentések a kiválasztott állás adatait jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="602e7-144">Job Analytics reports display data for the selected job.</span></span> <span data-ttu-id="602e7-145">Az Elemzési központ a felhasználó által megtekinthető összes állásra vonatkozóan összesítve jelenti az adatokat.</span><span class="sxs-lookup"><span data-stu-id="602e7-145">Analytics Hub reports aggregate data across all jobs a user can view.</span></span> <span data-ttu-id="602e7-146">A felhasználók, akik az Állások oldalon megtekinthetik a Saját állások és az Összes állás lapot, ugyanazt látják az Elemzési központban.</span><span class="sxs-lookup"><span data-stu-id="602e7-146">Users that can view both My jobs and All jobs on the Jobs page have the same views available in the Analytics Hub.</span></span>

## <a name="cross-filter"></a><span data-ttu-id="602e7-147">Keresztszűrés</span><span class="sxs-lookup"><span data-stu-id="602e7-147">Cross-filter</span></span>

<span data-ttu-id="602e7-148">A Power BI egyik nagyszerű funkciója az a mód, ahogy a jelentés oldalának összes vizuális eleme összeköttetésben van.</span><span class="sxs-lookup"><span data-stu-id="602e7-148">One of the great features of Power BI is the way all visuals on a report page are interconnected.</span></span> <span data-ttu-id="602e7-149">Ha kijelöl egy adatpontot az egyik vizális elemen, az oldalon található összes másik vizuális elem módosul, amely tartalmazza az adatot, a kiválasztás alapján.</span><span class="sxs-lookup"><span data-stu-id="602e7-149">If you select a data point on one of the visuals, all the other visuals on the page that contain that data change, based on that selection.</span></span> <span data-ttu-id="602e7-150">További információt és példát a [Hogyan végeznek a vizuális elemek keresztszűrést egy Power BI-jelentésben](https://docs.microsoft.com/en-us/power-bi/consumer/end-user-interactions) részben talál.</span><span class="sxs-lookup"><span data-stu-id="602e7-150">Find out more and see an example in [How visuals cross-filter each other in a Power BI report](https://docs.microsoft.com/en-us/power-bi/consumer/end-user-interactions).</span></span>

## <a name="export-to-excel"></a><span data-ttu-id="602e7-151">Exportálás az Excel programba</span><span class="sxs-lookup"><span data-stu-id="602e7-151">Export to Excel</span></span>

<span data-ttu-id="602e7-152">Ha meg szeretné tekinteni a jelentések adatait az Excel programban, kattintson a vizuális elem beállítások menüpontjára (három pont), és válassza a **Háttéradatok exportálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="602e7-152">To view report data in Excel, you can click the options menu (three dots) on a visual and select **Export underlying data**.</span></span> <span data-ttu-id="602e7-153">Az exportált adatok szűrve kerülnek exportálásra, az Attract szolgáltatásban érvényes felhasználói engedélyek figyelembe vételével.</span><span class="sxs-lookup"><span data-stu-id="602e7-153">Exported data will export as filtered, respecting user permissions in Attract.</span></span> <span data-ttu-id="602e7-154">A további információkért lásd: [Adatok exportálása vizualizációból](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-export-data).</span><span class="sxs-lookup"><span data-stu-id="602e7-154">For more information, see [Export data from visualizations](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-export-data).</span></span>
