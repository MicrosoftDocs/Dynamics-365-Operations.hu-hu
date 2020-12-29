---
title: Munkaerő optimalizálása részlegek, munkák és beosztások használatával
description: A részlegek, a munkák és a beosztások mind szervezeti elemek, melyeket az Emberi erőforrásokon belül kezelnek. Ez a cikk általános tájékoztatást ad ezeket az elemeket illetően.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources, Retail
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 826de9e1e5d70ba1ec088b44254c871726b5c38e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418833"
---
# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a><span data-ttu-id="51ff4-104">Munkaerő szervezése részlegek, feladatok és beosztások szerint</span><span class="sxs-lookup"><span data-stu-id="51ff4-104">Organize your workforce by using departments, jobs, and positions</span></span>

<span data-ttu-id="51ff4-105">A részlegek, a munkák és a beosztások mind szervezeti elemek, melyeket az Emberi erőforrásokon belül kezelnek.</span><span class="sxs-lookup"><span data-stu-id="51ff4-105">Departments, jobs, and positions are organizational elements that are maintained within Human resources.</span></span> <span data-ttu-id="51ff4-106">Ez a cikk általános tájékoztatást ad ezeket az elemeket illetően.</span><span class="sxs-lookup"><span data-stu-id="51ff4-106">This article describes conceptual information about these elements.</span></span> 

<span data-ttu-id="51ff4-107">Az alábbi példa mutatja be a jelen cikkben leírt koncepciókat.</span><span class="sxs-lookup"><span data-stu-id="51ff4-107">The following example is used to illustrate the concepts described in this article.</span></span>

|<span data-ttu-id="51ff4-108">**Részleg**</span><span class="sxs-lookup"><span data-stu-id="51ff4-108">**Department**</span></span>|<span data-ttu-id="51ff4-109">**Beosztás**</span><span class="sxs-lookup"><span data-stu-id="51ff4-109">**Position**</span></span>|<span data-ttu-id="51ff4-110">**Munka**</span><span class="sxs-lookup"><span data-stu-id="51ff4-110">**Job**</span></span>|
|---|---|---|
|<span data-ttu-id="51ff4-111">**Értékesítés**</span><span class="sxs-lookup"><span data-stu-id="51ff4-111">**Sales**</span></span>|<span data-ttu-id="51ff4-112">Értékesítési igazgató (Kelet)</span><span class="sxs-lookup"><span data-stu-id="51ff4-112">Sales manager (East)</span></span>|<span data-ttu-id="51ff4-113">Értékesítési igazgató</span><span class="sxs-lookup"><span data-stu-id="51ff4-113">Sales manager</span></span>|
|<span data-ttu-id="51ff4-114">**Értékesítések**</span><span class="sxs-lookup"><span data-stu-id="51ff4-114">**Sales**</span></span>|<span data-ttu-id="51ff4-115">Értékesítési igazgató (Nyugat)</span><span class="sxs-lookup"><span data-stu-id="51ff4-115">Sales manager (West)</span></span>|<span data-ttu-id="51ff4-116">Értékesítési igazgató</span><span class="sxs-lookup"><span data-stu-id="51ff4-116">Sales manager</span></span>|
|<span data-ttu-id="51ff4-117">**Értékesítések**</span><span class="sxs-lookup"><span data-stu-id="51ff4-117">**Sales**</span></span>|<span data-ttu-id="51ff4-118">Értékesítési igazgató (Közép)</span><span class="sxs-lookup"><span data-stu-id="51ff4-118">Sales manager (Central)</span></span>|<span data-ttu-id="51ff4-119">Értékesítési igazgató</span><span class="sxs-lookup"><span data-stu-id="51ff4-119">Sales manager</span></span>|
|<span data-ttu-id="51ff4-120">**Könyvelés**</span><span class="sxs-lookup"><span data-stu-id="51ff4-120">**Accounting**</span></span>|<span data-ttu-id="51ff4-121">Számviteli felügyelő</span><span class="sxs-lookup"><span data-stu-id="51ff4-121">Accounting supervisor</span></span>|<span data-ttu-id="51ff4-122">Főkönyvelő</span><span class="sxs-lookup"><span data-stu-id="51ff4-122">Accounting manager</span></span>|
|<span data-ttu-id="51ff4-123">**Könyvelés**</span><span class="sxs-lookup"><span data-stu-id="51ff4-123">**Accounting**</span></span>|<span data-ttu-id="51ff4-124">Könyvelés-A</span><span class="sxs-lookup"><span data-stu-id="51ff4-124">Accounting-A</span></span>|<span data-ttu-id="51ff4-125">Könyvelő</span><span class="sxs-lookup"><span data-stu-id="51ff4-125">Accountant</span></span>|
|<span data-ttu-id="51ff4-126">**Emberi erőforrások**</span><span class="sxs-lookup"><span data-stu-id="51ff4-126">**Human resources**</span></span>|<span data-ttu-id="51ff4-127">HR vezető (Kelet)</span><span class="sxs-lookup"><span data-stu-id="51ff4-127">HR manager (East)</span></span>|<span data-ttu-id="51ff4-128">HR vezető</span><span class="sxs-lookup"><span data-stu-id="51ff4-128">HR manager</span></span>|
|<span data-ttu-id="51ff4-129">**Emberi erőforrások**</span><span class="sxs-lookup"><span data-stu-id="51ff4-129">**Human resources**</span></span>|<span data-ttu-id="51ff4-130">HR vezető (Nyugat)</span><span class="sxs-lookup"><span data-stu-id="51ff4-130">HR manager (West)</span></span>|<span data-ttu-id="51ff4-131">HR vezető</span><span class="sxs-lookup"><span data-stu-id="51ff4-131">HR manager</span></span>|
|<span data-ttu-id="51ff4-132">**Emberi erőforrások**</span><span class="sxs-lookup"><span data-stu-id="51ff4-132">**Human resources**</span></span>|<span data-ttu-id="51ff4-133">HR vezető (Közép)</span><span class="sxs-lookup"><span data-stu-id="51ff4-133">HR manager (Central)</span></span>|<span data-ttu-id="51ff4-134">HR vezető</span><span class="sxs-lookup"><span data-stu-id="51ff4-134">HR manager</span></span>|


 <a name="departments"></a><span data-ttu-id="51ff4-135">Osztályok</span><span class="sxs-lookup"><span data-stu-id="51ff4-135">Departments</span></span>
------------

<span data-ttu-id="51ff4-136">A részleg egy olyan üzemi egység, amely a szervezet egy kategóriáját vagy funkcionális területét képviseli, amely a szervezet egy specifikus területéért felel, ilyen például az értékesítés vagy a könyvelés.</span><span class="sxs-lookup"><span data-stu-id="51ff4-136">A department is an operating unit that represents a category or functional area of an organization that is responsible for a specific area of the organization, such as sales or accounting.</span></span> <span data-ttu-id="51ff4-137">A részlegekkel – amelyeknek profitjuk és veszteségi felelősségük lehet – funkcionális területekkel kapcsolatos jelentések tehetők.</span><span class="sxs-lookup"><span data-stu-id="51ff4-137">A department is used to report on functional areas and may have profit and loss responsibility.</span></span> <span data-ttu-id="51ff4-138">Emellett egy részleg költséghelyek egy csoportját is magában foglalhatja.</span><span class="sxs-lookup"><span data-stu-id="51ff4-138">Also, a department might include a group of cost centers.</span></span> <span data-ttu-id="51ff4-139">Az értékesítés, a könyvelés és a HR csak néhány példa a szervezeten belüli részlegekre.</span><span class="sxs-lookup"><span data-stu-id="51ff4-139">Sales, accounting, and human resources are some examples of departments in an organization.</span></span>

## <a name="jobs-and-positions"></a><span data-ttu-id="51ff4-140"> Munkakörök és beosztások</span><span class="sxs-lookup"><span data-stu-id="51ff4-140">Jobs and positions</span></span>
<span data-ttu-id="51ff4-141">A munkakör azon feladatok és felelősségek gyűjteménye, amelyek egy adott munkát végrehajtó személytől elvárt.</span><span class="sxs-lookup"><span data-stu-id="51ff4-141">A job is a collection of tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="51ff4-142">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="51ff4-142">A position is an individual instance of a job.</span></span> <span data-ttu-id="51ff4-143">Egy adott munkakörhöz szükséges felelősségi területek, munkafeladatok, beosztások, képességek, tanulmányi adatok és tanúsítványok az adott munkához rendelt pozíciók esetén is elvárt.</span><span class="sxs-lookup"><span data-stu-id="51ff4-143">Areas of responsibility, job tasks, job functions, skills, education information, and certificates that are required for a job are also required for positions that are associated with a job.</span></span>
### <a name="job-tasks"></a><span data-ttu-id="51ff4-144">Munkaköri feladatok</span><span class="sxs-lookup"><span data-stu-id="51ff4-144">Job tasks</span></span>

<span data-ttu-id="51ff4-145">Létrehozhat olyan munkaköri feladatokat, amelyek bemutatják az adott pozíciójú dolgozótól elvárt alapvető feladatokat.</span><span class="sxs-lookup"><span data-stu-id="51ff4-145">You can create job tasks that describe the basic tasks that a worker in a position for that job must complete.</span></span> <span data-ttu-id="51ff4-146">Ugyanazon munkaköri feladatok több munkához is hozzáadhatók, valamint az adott munkához tartozó pozíciók öröklik ezen munkaköri feladatokat.</span><span class="sxs-lookup"><span data-stu-id="51ff4-146">The same job task can be added to multiple jobs, and positions for those jobs will inherit those job tasks.</span></span> <span data-ttu-id="51ff4-147">Az alábbi táblázatban látható néhány példa munkaköri feladatokra.</span><span class="sxs-lookup"><span data-stu-id="51ff4-147">Examples of job tasks are listed in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="51ff4-148">Munka</span><span class="sxs-lookup"><span data-stu-id="51ff4-148">Job</span></span></th>
<th><span data-ttu-id="51ff4-149">Munkaköri feladat</span><span class="sxs-lookup"><span data-stu-id="51ff4-149">Job task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="51ff4-150">Értékesítési igazgató</span><span class="sxs-lookup"><span data-stu-id="51ff4-150">Sales manager</span></span></td>
<td><ul>
<li><span data-ttu-id="51ff4-151"><span class="input">Teljesítményellenőrzés</span> – Az egyes értékesítők teljesítményének áttekintése.</span><span class="sxs-lookup"><span data-stu-id="51ff4-151"><span class="input">Perf-review</span> – Review each salesperson’s job performance.</span></span></li>
<li><span data-ttu-id="51ff4-152"><span class="input">Hiányzásellenőrzési</span> – Az üzletkötők távolléti kérelmeinek vagy regisztrációnak jóváhagyása vagy elutasítása.</span><span class="sxs-lookup"><span data-stu-id="51ff4-152"><span class="input">Abs-review</span> – Approve or reject each salesperson’s absence requests or registrations.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51ff4-153">Könyvelő</span><span class="sxs-lookup"><span data-stu-id="51ff4-153">Accountant</span></span></td>
<td><span data-ttu-id="51ff4-154"><span class="input">Pénzügyi jelentés</span> – Heti pénzügyi jelentések bemutatása a pénzügyi igazgatónak.</span><span class="sxs-lookup"><span data-stu-id="51ff4-154"><span class="input">FIN-Report</span> – Present weekly financial reports to chief financial officer.</span></span></td>
</tr>
</tbody>
</table>

### <a name="job-functions"></a><span data-ttu-id="51ff4-155">Beosztások</span><span class="sxs-lookup"><span data-stu-id="51ff4-155">Job functions</span></span>

<span data-ttu-id="51ff4-156">A beosztási funkciók hasonlók a munkaköri feladatokhoz.</span><span class="sxs-lookup"><span data-stu-id="51ff4-156">Job functions are like job tasks.</span></span> <span data-ttu-id="51ff4-157">A beosztási funkció egy munkához rendelt egy vagy több feladat, kötelezettség és feladatkör.</span><span class="sxs-lookup"><span data-stu-id="51ff4-157">A job function describes one or more tasks, duties or responsibilities that are assigned to a job.</span></span> <span data-ttu-id="51ff4-158">A beosztásokat a munkákhoz lehet hozzárendelni, és segítségükkel a kompenzációs tervekhez kapcsolódó jogosultsági szabályokat lehet beállítani és alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="51ff4-158">Job functions can be assigned to jobs and used to set up and implement eligibility rules for compensation plans.</span></span> <span data-ttu-id="51ff4-159">Az alábbi táblázatban látható néhány példa munkaköri beosztásokra.</span><span class="sxs-lookup"><span data-stu-id="51ff4-159">Examples of job functions are listed in the following table.</span></span>

| <span data-ttu-id="51ff4-160">Munka</span><span class="sxs-lookup"><span data-stu-id="51ff4-160">Job</span></span>           | <span data-ttu-id="51ff4-161">Beosztás</span><span class="sxs-lookup"><span data-stu-id="51ff4-161">Job function</span></span>                                                |
|---------------|-------------------------------------------------------------|
| <span data-ttu-id="51ff4-162">Értékesítési igazgató</span><span class="sxs-lookup"><span data-stu-id="51ff4-162">Sales manager</span></span> | <span data-ttu-id="51ff4-163">Személyek kezelése – Azon személyek kezelése, akik Önnek jelentenek.</span><span class="sxs-lookup"><span data-stu-id="51ff4-163">Mng-people – Manage people who report to you.</span></span>               |
| <span data-ttu-id="51ff4-164">Könyvelő</span><span class="sxs-lookup"><span data-stu-id="51ff4-164">Accountant</span></span>    | <span data-ttu-id="51ff4-165">Pénzügyi ellenőrzés – Pénzügyi adatok karbantartása számlák csoportjainak esetében.</span><span class="sxs-lookup"><span data-stu-id="51ff4-165">FIN-Review – Maintain financial data for a set of accounts.</span></span> |

### <a name="job-types"></a><span data-ttu-id="51ff4-166">Beosztástípusok</span><span class="sxs-lookup"><span data-stu-id="51ff4-166">Job types</span></span>

<span data-ttu-id="51ff4-167">Feladattípusok segítségével a hasonló beosztások kategóriákba sorolhatók.</span><span class="sxs-lookup"><span data-stu-id="51ff4-167">Use job types to classify similar jobs into categories.</span></span> <span data-ttu-id="51ff4-168">A feladattípusokat a beosztási funkciókhoz hasonlóan a feladatokhoz lehet hozzárendelni, és segítségükkel a kompenzációs tervekhez kapcsolódó jogosultsági szabályokat lehet beállítani és alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="51ff4-168">Job types, just like job functions, can be assigned to jobs and used to set up and implement eligibility rules for compensation plans.</span></span> <span data-ttu-id="51ff4-169">Az alábbi táblázatban látható néhány példa a feladattípusokra:</span><span class="sxs-lookup"><span data-stu-id="51ff4-169">Some examples of job types are included in the following list:</span></span>
-   <span data-ttu-id="51ff4-170">Teljes munkaidős</span><span class="sxs-lookup"><span data-stu-id="51ff4-170">Full-time</span></span>
-   <span data-ttu-id="51ff4-171">Részmunkaidős</span><span class="sxs-lookup"><span data-stu-id="51ff4-171">Part-time</span></span>
-   <span data-ttu-id="51ff4-172">Fizetés</span><span class="sxs-lookup"><span data-stu-id="51ff4-172">Salary</span></span>
-   <span data-ttu-id="51ff4-173">Órabér</span><span class="sxs-lookup"><span data-stu-id="51ff4-173">Hourly pay</span></span>

### <a name="areas-of-responsibility"></a><span data-ttu-id="51ff4-174">Hatáskörök</span><span class="sxs-lookup"><span data-stu-id="51ff4-174">Areas of responsibility</span></span>

<span data-ttu-id="51ff4-175">Alkalmazzon hatásköröket azon a szerepkörök, folyamatok, termékek és műveletek megjelöléséhez, amelyekért a dolgozó egy adott beosztásban felelős.</span><span class="sxs-lookup"><span data-stu-id="51ff4-175">Use areas of responsibility to indicate the work roles, processes, and products that a worker in a position for that job would be responsible for.</span></span> <span data-ttu-id="51ff4-176">A „Könyvelő” nevű beosztáshoz tartozó hatáskörre példa lehet a „Pénzügyi jelentés az A termékkel kapcsolatban”.</span><span class="sxs-lookup"><span data-stu-id="51ff4-176">An example of an area of responsibility for a job titled “Accountant” might be “Financial reporting for Product A”.</span></span>

<a name="positions"></a><span data-ttu-id="51ff4-177">Beosztások</span><span class="sxs-lookup"><span data-stu-id="51ff4-177">Positions</span></span>
----------

<span data-ttu-id="51ff4-178">A beosztások szervezeti hierarchia alacsonyabb szintjének fontos részei.</span><span class="sxs-lookup"><span data-stu-id="51ff4-178">Positions are an important element of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="51ff4-179">Egy beosztás egy feladat egyedi példánya.</span><span class="sxs-lookup"><span data-stu-id="51ff4-179">A position is an individual instance of a job.</span></span> <span data-ttu-id="51ff4-180">Például az „Értékesítési igazgató (Kelet)” pozíció csak egyike azon beosztásoknak, amelyek hozzárendelhetők az „Értékesítési igazgató” munkához.</span><span class="sxs-lookup"><span data-stu-id="51ff4-180">For example, the position, “Sales manager (East),” is just one of the positions that is associated with the job, “Sales manager.”</span></span> <span data-ttu-id="51ff4-181">A pozíciók egy részlegen belül léteznek, és dolgozókhoz kerülnek hozzárendelésre.</span><span class="sxs-lookup"><span data-stu-id="51ff4-181">Positions exist in a department and are assigned to workers.</span></span>
### <a name="position-creation-and-maintenance"></a><span data-ttu-id="51ff4-182">Beosztások létrehozása és karbantartása</span><span class="sxs-lookup"><span data-stu-id="51ff4-182">Position creation and maintenance</span></span>

-   <span data-ttu-id="51ff4-183">Az egyszerű hozzáférést biztosító listaoldalon megtekintheti a pozíciókkal kapcsolatos rendszermódosítások előzményeit.</span><span class="sxs-lookup"><span data-stu-id="51ff4-183">You can view a history of position-related system changes in an easy-to-access list page.</span></span>
-   <span data-ttu-id="51ff4-184">Okkódokat is létrehozhat, amelyeket a felhasználók a pozíciók létrehozásakor vagy módosításakor választhatnak.</span><span class="sxs-lookup"><span data-stu-id="51ff4-184">You can create reason codes that your users can select when they create or modify positions.</span></span>
-   <span data-ttu-id="51ff4-185">Létrehozhat személyzeti művelet típusokat, és számsorozatokat rendelhet a személyzeti műveletekhez.</span><span class="sxs-lookup"><span data-stu-id="51ff4-185">You can create personnel action types and assign a number sequence to personnel actions.</span></span>
-   <span data-ttu-id="51ff4-186">Be lehet állítani munkafolyamat úgy, hogy a beosztásokkal kapcsolatos kiegészítésekhez és módosításokhoz jóváhagyásra is szükség legyen.</span><span class="sxs-lookup"><span data-stu-id="51ff4-186">You can set up workflow so that position additions and changes can require approval.</span></span>

### <a name="position-duration"></a><span data-ttu-id="51ff4-187">Beosztás időtartama</span><span class="sxs-lookup"><span data-stu-id="51ff4-187">Position duration</span></span>

<span data-ttu-id="51ff4-188">Minden pozícióhoz tartozik egy időtartam, amely a beosztás érvényességi idejét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="51ff4-188">Every position has a length of time that the position is effective.</span></span> <span data-ttu-id="51ff4-189">Ezen intervallumot időtartamnak nevezik.</span><span class="sxs-lookup"><span data-stu-id="51ff4-189">This length of time is referred to as duration.</span></span> <span data-ttu-id="51ff4-190">Például a nyári beosztások időtartam lehet: 2015. május 1-től 2015. augusztus 31-ig.</span><span class="sxs-lookup"><span data-stu-id="51ff4-190">For example, summer positions might have duration of May 1, 2015 until August 31, 2015.</span></span>

### <a name="worker-assignments"></a><span data-ttu-id="51ff4-191">Dolgozó-hozzárendelések</span><span class="sxs-lookup"><span data-stu-id="51ff4-191">Worker assignments</span></span>

<span data-ttu-id="51ff4-192">Ha hozzárendel egy dolgozót egy beosztáshoz, akkor betölti a pozíciót.</span><span class="sxs-lookup"><span data-stu-id="51ff4-192">When you assign a worker to a position, you fill that position.</span></span> <span data-ttu-id="51ff4-193">Egy dolgozót több beosztáshoz is hozzárendelhet, de egy beosztáshoz egyszerre csak egy dolgozót lehet hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="51ff4-193">You can assign workers to multiple positions, but only one worker can be assigned to a position at the same time.</span></span>

### <a name="reporting-relationships"></a><span data-ttu-id="51ff4-194">Jelentési kapcsolatok</span><span class="sxs-lookup"><span data-stu-id="51ff4-194">Reporting relationships</span></span>

<span data-ttu-id="51ff4-195">A beosztások a szervezeti hierarchia alacsonyabb szintjének fontos részei.</span><span class="sxs-lookup"><span data-stu-id="51ff4-195">Positions are important elements of the lower level of an organization hierarchy.</span></span> <span data-ttu-id="51ff4-196">A Beosztás képernyőn megadhatja azon beosztást, amely felé az adott beosztottnak jelentenie kell.</span><span class="sxs-lookup"><span data-stu-id="51ff4-196">In the Position form, you can specify the position that a position reports to.</span></span> <span data-ttu-id="51ff4-197">Ha hozzárendel egy dolgozót egy olyan pozícióhoz, amely egy másik pozíció számára jelent, akkor jelentési kapcsolatot hoz létre a két beosztáshoz hozzárendelt dolgozók között.</span><span class="sxs-lookup"><span data-stu-id="51ff4-197">When you assign a worker to a position that reports to another position, you create a reporting relationship between the workers who are assigned to the two positions.</span></span> <span data-ttu-id="51ff4-198">Például a „Könyvelő-A” pozíció a „Számviteli felügyelő” számára tesz jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="51ff4-198">For example, position “Accountant-A” reports to position “Accounting Supervisor”.</span></span> <span data-ttu-id="51ff4-199">A „Számviteli felügyelő” pozícióhoz Kim Akers, a „Könyvelő-A” pozícióhoz Sanjay Patel kerül hozzárendelésre.</span><span class="sxs-lookup"><span data-stu-id="51ff4-199">Kim Akers is assigned to position “Accounting Supervisor” and Sanjay Patel is assigned to position “Accountant-A”.</span></span> <span data-ttu-id="51ff4-200">Ez azt jelenti, hogy Sanjay Patel Kim Akers felé jelent.</span><span class="sxs-lookup"><span data-stu-id="51ff4-200">This means that Sanjay Patel reports to Kim Akers.</span></span> 

<span data-ttu-id="51ff4-201">Ha szervezete mátrix hierarchiát vagy egyéb egyéni hierarchiát alkalmaz, beállíthat pozíció hierarchia típusokat, majd hozzáadhat jelentési kapcsolatokat minden egyes beállított hierarchia típushoz.</span><span class="sxs-lookup"><span data-stu-id="51ff4-201">If your organization uses a matrix hierarchy or another custom hierarchy, you can set up position hierarchy types and then add reporting relationships to positions for each hierarchy type that you set up.</span></span> <span data-ttu-id="51ff4-202">Például Lori Penor az Adventure Works általános igazgatója, így hozzá van rendelve az „Általános igazgató” beosztáshoz.</span><span class="sxs-lookup"><span data-stu-id="51ff4-202">For example, Lori Penor is a general manager at Adventure Works and is assigned to the “General Manager” position.</span></span> <span data-ttu-id="51ff4-203">Lori kezeli a fejlesztését egy olyan terméknek, amely különböző eszközök tisztítására szolgál.</span><span class="sxs-lookup"><span data-stu-id="51ff4-203">Lori manages the development of a product that is used to clean widgets.</span></span> <span data-ttu-id="51ff4-204">Lorinak szüksége van egy könyvelőre, aki segít neki a termékfejlesztéssel kapcsolatos pénzügyek kezelésében.</span><span class="sxs-lookup"><span data-stu-id="51ff4-204">Lori requires an accountant to help her with the finances for developing the product.</span></span> <span data-ttu-id="51ff4-205">Ezért felvette Sanjay Patelt könyvelőnek.</span><span class="sxs-lookup"><span data-stu-id="51ff4-205">Therefore, she has recruited Sanjay Patel to be her accountant.</span></span> <span data-ttu-id="51ff4-206">Sanjay közvetlenül Kim Akers felé jelent, ugyanakkor együtt dolgozik Lori Penorral is, aki szintén az eszköztisztító fejlesztésével kapcsolatos pénzügyek kezelésében vesz részt.</span><span class="sxs-lookup"><span data-stu-id="51ff4-206">Sanjay reports directly to Kim Akers, but also works with Lori Penor on his work related to the finances for developing the widget cleaner.</span></span> 

<span data-ttu-id="51ff4-207">Az előző példához a következő feladatokat kellene végrehajtani Sanjay Patel és Anna Penor munkakapcsolatának beállításához:</span><span class="sxs-lookup"><span data-stu-id="51ff4-207">For the previous example, you would complete the following tasks to set up the working relationship between Sanjay Patel and Lori Penor:</span></span>
1.  <span data-ttu-id="51ff4-208">Egyéni pozícióhierarchia létrehozása „Eszköz” néven az eszköztisztító termék fejlesztéséért felelős beosztásokat magában foglaló hierarchia létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="51ff4-208">Create a custom position hierarchy type called “Widget” to create a hierarchy that includes positions responsible for working on the widget cleaner product.</span></span>
2.  <span data-ttu-id="51ff4-209">Az Általános igazgatói pozíció hozzárendelése a Könyvelő-A pozícióhoz úgy, hogy utóbbi jelentsen az előző számára.</span><span class="sxs-lookup"><span data-stu-id="51ff4-209">Assign the General Manager position to be the position that the Accountant-A position reports to in the Widget hierarchy.</span></span>

<span data-ttu-id="51ff4-210">A beosztáshierarchia a pozíciók jelentési szerkezetének megtekintésére használható.</span><span class="sxs-lookup"><span data-stu-id="51ff4-210">Use the position hierarchy to view the reporting structure of positions.</span></span> <span data-ttu-id="51ff4-211">Ha több beosztáshierarchiával rendelkezik, a beosztáshierarchia minden egyes hierarchiatípusához kapcsolódóan megtekintheti a hierarchiákat.</span><span class="sxs-lookup"><span data-stu-id="51ff4-211">If you have multiple position hierarchies, you can view the hierarchy for each hierarchy type in the position hierarchy.</span></span> <span data-ttu-id="51ff4-212">Emellett a pozícióazonosító vagy a beosztáshoz hozzárendelt dolgozó neve alapján is megkereshet egy pozíciót.</span><span class="sxs-lookup"><span data-stu-id="51ff4-212">Also, you can search for a position by position ID or by the name of the worker who is assigned to the position.</span></span> <span data-ttu-id="51ff4-213">A beosztáshierarchia egy szervezeti hierarchia.</span><span class="sxs-lookup"><span data-stu-id="51ff4-213">The position hierarchy is an organizational hierarchy.</span></span>

## <a name="date-effective-records"></a><span data-ttu-id="51ff4-214">Érvényességidátum-rekordok</span><span class="sxs-lookup"><span data-stu-id="51ff4-214">Date effective records</span></span>
<span data-ttu-id="51ff4-215">Bizonyos rekordok esetében jövőbeni módosításokat is be lehet állítani a rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="51ff4-215">For some records, you can specify future changes to the record.</span></span> <span data-ttu-id="51ff4-216">A következő adatok érvényességi dátumhoz kötöttek.</span><span class="sxs-lookup"><span data-stu-id="51ff4-216">The following information is date effective.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="51ff4-217">Rekordok</span><span class="sxs-lookup"><span data-stu-id="51ff4-217">Records</span></span></th>
<th><span data-ttu-id="51ff4-218">Hatályba lépési dátumhoz kötött adat</span><span class="sxs-lookup"><span data-stu-id="51ff4-218">Date effective information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="51ff4-219">Feladatok</span><span class="sxs-lookup"><span data-stu-id="51ff4-219">Jobs</span></span></td>
<td><ul>
<li><span data-ttu-id="51ff4-220">Részletes információk a munkával kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="51ff4-220">Some detailed job information</span></span></li>
<li><span data-ttu-id="51ff4-221">Beosztási kategória adatai</span><span class="sxs-lookup"><span data-stu-id="51ff4-221">Job classification information</span></span></li>
<li><span data-ttu-id="51ff4-222">Kompenzációs adatok</span><span class="sxs-lookup"><span data-stu-id="51ff4-222">Compensation information</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="51ff4-223">Pozíciók</span><span class="sxs-lookup"><span data-stu-id="51ff4-223">Positions</span></span></td>
<td><ul>
<li><span data-ttu-id="51ff4-224">Részletes információk a pozícióval kapcsolatban</span><span class="sxs-lookup"><span data-stu-id="51ff4-224">Some detailed position information</span></span></li>
<li><span data-ttu-id="51ff4-225">Dolgozó-hozzárendelések</span><span class="sxs-lookup"><span data-stu-id="51ff4-225">Worker assignments</span></span></li>
<li><span data-ttu-id="51ff4-226">Beosztások időtartamai</span><span class="sxs-lookup"><span data-stu-id="51ff4-226">Position durations</span></span></li>
<li><span data-ttu-id="51ff4-227">Beosztáshierarchiák</span><span class="sxs-lookup"><span data-stu-id="51ff4-227">Position hierarchies</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="51ff4-228">Módosíthatja az előző táblázatban említett, az egyes beosztásokhoz és feladatokhoz tartozó adatokat, és megadhat egy dátumot, amikor a beosztáshoz vagy feladathoz kapcsolódó módosításoknak érvénybe kell lépniük.</span><span class="sxs-lookup"><span data-stu-id="51ff4-228">You can modify the information mentioned in the previous table for a position or a job and specify a date when the modifications to the position or job should take effect.</span></span> <span data-ttu-id="51ff4-229">Például egy beosztás csak egy dolgozóhoz rendelhető hozzá, de Sanjay Patel, aki a Könyvelő-A beosztáshoz van rendelve, két hét múlva távozik.</span><span class="sxs-lookup"><span data-stu-id="51ff4-229">For example, a position can only be assigned to one worker, but Sanjay Patel, who is assigned to the position Accountant-A, will be leaving in two weeks.</span></span> <span data-ttu-id="51ff4-230">Sanjay Patel távozását követően Joe Healey veszi át a pozíciót.</span><span class="sxs-lookup"><span data-stu-id="51ff4-230">Joe Healy will replace Sanjay Patel when he leaves.</span></span> <span data-ttu-id="51ff4-231">Annak ellenére, hogy Sanjay továbbra is hozzá van rendelve a beosztáshoz, Joe Healy is hozzárendelhető ugyanehhez a pozícióhoz úgy, hogy a hozzárendelés ténylegesen csak Sanjay utolsó napját követően lépjen hatályba.</span><span class="sxs-lookup"><span data-stu-id="51ff4-231">Even though Sanjay is still assigned to his position, you can assign Joe Healy to the same position so that the assignment is effective only after Sanjay’s last day.</span></span>





