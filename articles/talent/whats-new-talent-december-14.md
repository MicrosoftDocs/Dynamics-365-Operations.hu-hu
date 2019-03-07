---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. december 14.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7d2866923efd7f115ad5290f35ed4fcac5e47573
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304610"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-14-2018"></a><span data-ttu-id="cc5d0-103">Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. december 14.)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-103">What's new or changed in Dynamics 365 for Talent Core HR (December 14, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cc5d0-104">**Build 8.1.2085**</span><span class="sxs-lookup"><span data-stu-id="cc5d0-104">**Build 8.1.2085**</span></span>

<span data-ttu-id="cc5d0-105">Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="cc5d0-106">Változások</span><span class="sxs-lookup"><span data-stu-id="cc5d0-106">Changes</span></span>

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a><span data-ttu-id="cc5d0-107">US – ACA (Affordable Care Act) támogatás a 2018-as adózási évre, 1095-B és 1095 C űrlapok</span><span class="sxs-lookup"><span data-stu-id="cc5d0-107">US - ACA (Affordable Care Act) support for tax year 2018 1095-B and 1095-C forms</span></span>

<span data-ttu-id="cc5d0-108">Minden évben az alkalmazandó nagy munkáltatóknak (ALE-k) minden teljes munkaidős alkalmazottnak a rendelkezésére kell bocsátaniuk egy 1095-C-t.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-108">Each year, Applicable Large Employers (ALEs) must provide each full-time employees with a 1095-C.</span></span> <span data-ttu-id="cc5d0-109">Ezenkívül, ha a munkáltató önálló biztosítási fedezetet kínál, rendelkezésre kell bocsájtania a teljes munkaidős vagy részmunkaidős alkalmazottaknak a 1095-C-t (ha ALE), és egy 1095-B-t (ha kis foglalkoztató), akikre kiterjed a munkaadó által ajánlott egészségügyi tervek egyike.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-109">In addition, if the employer provides self-insured coverage they must provide the 1095-C (if they are an ALE) and a 1095-B (if they are a small employer) to any employee, full-time or part-time, covered under one of their offered health plans.</span></span> <span data-ttu-id="cc5d0-110">Ez a funkció nyomtatható űrlapot biztosít a 1095-C és 1095-B esetében.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-110">This feature provides printable forms for both the 1095-C and 1095-B.</span></span>

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a><span data-ttu-id="cc5d0-111">Az importálás során HcmPerfJournalEntity SubmittedByPersonId mezője nem lesz figyelembe véve</span><span class="sxs-lookup"><span data-stu-id="cc5d0-111">During import SubmittedByPersonId field on HcmPerfJournalEntity is ignored</span></span>

<span data-ttu-id="cc5d0-112">A teljesítmény-naplóbejegyzések importálásakor/exportálásakor az **Elküldte** mezőt a program figyelmen kívül hagyja.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-112">When importing/exporting performance journal entries, the **Submitted by** field is ignored.</span></span> <span data-ttu-id="cc5d0-113">Ezzel a változtatással az **importált/exportált** érték azt az értéket tükrözi a táblában az exportálás során, hogy a rendszer importálását mikor frissíti a rendszer az importálási fájlban megadott értékkel.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-113">With this change, the value **imported/exported** will reflect the value in the table during the export, when importing the system will be updated with the value supplied in the import file.</span></span>

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a><span data-ttu-id="cc5d0-114">A „Szabadság és távollét” munkaterület Analitika lapja „OpenConnectionError” hibát jelenít meg a nem rendszergazdai szerepkörök esetén</span><span class="sxs-lookup"><span data-stu-id="cc5d0-114">Analytics tab on 'Leave and absence' workspace displays "OpenConnectionError" error for non-system Admin roles</span></span>

<span data-ttu-id="cc5d0-115">A frissítés telepítését követően nem jelenik meg hiba, ha megnyitják az **Analitika** lapot a **Szabadság és távollét** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-115">With this update, no errors will be issued when opening the **Analytics** tab on the **Leave and Absence** workspace.</span></span>

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="cc5d0-116">Az alkalmazotti önkiszolgáló rendszer, Beosztáshierarchia leásás a csempéről nem tudja beolvasni a szülőcsomópontot</span><span class="sxs-lookup"><span data-stu-id="cc5d0-116">Employee self-service, Position Hierarchy drill-down from tile fails to get parent node</span></span>

<span data-ttu-id="cc5d0-117">Változtatás történt „A szülőcsomópont beolvasása nem sikerült” hiba kijavítására, amely akkor jelenik meg, ha egy beosztáshierarchiát testreszabtak, hogy egy meglévő munkaterületen jelenjen meg, és egy beosztást kiválasztanak a hierarchiában.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-117">A change has been made to correct the error "Getting the parent node failed" when the position hierarchy has been personalized to appear on an existing workspace and a position is selected in the hierarchy.</span></span>  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a><span data-ttu-id="cc5d0-118">A Beosztás oldal Bérlista lapjának megtekintéséhez rendszergazdának kell lenni</span><span class="sxs-lookup"><span data-stu-id="cc5d0-118">Must be System Admin to see the Payroll tab in the Position page</span></span>

<span data-ttu-id="cc5d0-119">Változtatás történt, hogy a helyes biztonsági elemek szerepeljenek a meglévő jogosultságban: „Bérlista dolgozókra és beosztásokra vonatkozó részleteinek karbantartása”.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-119">A change has been made to include the correct security elements in the existing privilege: "Maintain payroll worker and position detail".</span></span> <span data-ttu-id="cc5d0-120">Ezzel a módosítással alapértelmezés szerint a bérszámfejtő fér hozzá a Beosztás oldal Bérlista mezőihez.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-120">With this change, by default, the Payroll Administrator will have access to the Payroll fields on the Position page.</span></span>

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a><span data-ttu-id="cc5d0-121">Hiba a teljesítményáttekintés elküldésekor a vezetőnek, és a %Reviews.PerfPeriod% helyőrző van használatban a küldési utasításokban</span><span class="sxs-lookup"><span data-stu-id="cc5d0-121">Error when submitting performance review to manager and the %Reviews.PerfPeriod% placeholder is used in the Submission instructions</span></span>

<span data-ttu-id="cc5d0-122">Változtatás történt, amely javítja a „Null referencia” hibát a küldési utasításokban a %Reviews.PerfPeriod% helyőrző használatakor.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-122">A change has been made that corrects the "Null Reference" error when using the %Reviews.PerfPeriod% placeholder in the Submission instructions.</span></span>

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a><span data-ttu-id="cc5d0-123">A munkaerő Power BI jelentés hibát jelez, amikor az alkalmazott szolgálati idejének dátuma szökőnap</span><span class="sxs-lookup"><span data-stu-id="cc5d0-123">Workforce Power BI report shows error when worker seniority date is a leap day</span></span>

<span data-ttu-id="cc5d0-124">Ezt a változtatást a Power BI most már támogatja a szökőnapokat.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-124">With this change, leap days are now supported in Power BI.</span></span>

### <a name="integration-between-core-hr-and-attract"></a><span data-ttu-id="cc5d0-125">Core HR és Attract integrációja</span><span class="sxs-lookup"><span data-stu-id="cc5d0-125">Integration between Core HR and Attract</span></span>

<span data-ttu-id="cc5d0-126">Változás történt, amely frissíti a Core HR és az Attract integrációját a pályázók felvételéhez kapcsolódóan.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-126">A change has been made to update the integration between Core HR and Attract related to candidates to hire.</span></span> <span data-ttu-id="cc5d0-127">A felvételre váró pályázók láthatóvá tételéhez a **Személyzet kezelése** munkaterületen, a következő CDS for Apps (CD 2.0) entitások használatosak:</span><span class="sxs-lookup"><span data-stu-id="cc5d0-127">For candidates to hire to be visible in the **Personnel Management** workspace, the following CDS for Apps (CDS 2.0) entities are used:</span></span>

<span data-ttu-id="cc5d0-128">Álláspályázat</span><span class="sxs-lookup"><span data-stu-id="cc5d0-128">Job Application</span></span>
- <span data-ttu-id="cc5d0-129">Az állapot okát elfogadott ajánlatra kell állítani</span><span class="sxs-lookup"><span data-stu-id="cc5d0-129">Status Reason needs to be set to Offer Accepted</span></span>
-   <span data-ttu-id="cc5d0-130">A pályázókat és az álláslehetőségeket biztosítja</span><span class="sxs-lookup"><span data-stu-id="cc5d0-130">Provides Candidate and Job Opening</span></span>

<span data-ttu-id="cc5d0-131">Pályázó</span><span class="sxs-lookup"><span data-stu-id="cc5d0-131">Candidate</span></span>
-   <span data-ttu-id="cc5d0-132">Jelölt adatokat biztosítja</span><span class="sxs-lookup"><span data-stu-id="cc5d0-132">Provides Candidate information</span></span>

<span data-ttu-id="cc5d0-133">Álláslehetőség</span><span class="sxs-lookup"><span data-stu-id="cc5d0-133">Job Opening</span></span>
-   <span data-ttu-id="cc5d0-134">Az álláslehetőség-azonosítót és az álláslehetőség-résztvevőket biztosítja</span><span class="sxs-lookup"><span data-stu-id="cc5d0-134">Provides Job Opening ID and Job Opening Participants</span></span>

<span data-ttu-id="cc5d0-135">Álláslehetőség-résztvevők</span><span class="sxs-lookup"><span data-stu-id="cc5d0-135">Job Opening Participants</span></span>
-   <span data-ttu-id="cc5d0-136">A munkaerő-felvételi vezetőt biztosítja</span><span class="sxs-lookup"><span data-stu-id="cc5d0-136">Provides Hiring Manager</span></span>

<span data-ttu-id="cc5d0-137">Egy jelöltnek a személyzet kezelésébe való felvétele után a jelöltet most már egy, a jelöltkártyán rendelkezésre álló új opcióval is ki lehet zárni.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-137">When a candidate is added to Personnel Management, the candidate can now also be dismissed using a new option available on the candidate card.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="cc5d0-138">Hamarosan</span><span class="sxs-lookup"><span data-stu-id="cc5d0-138">Coming soon</span></span>

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a><span data-ttu-id="cc5d0-139">Szabadság és távollét: jövőbeli szabadság és távolléti egyenlegek előrejelzése</span><span class="sxs-lookup"><span data-stu-id="cc5d0-139">Leave and absence: Future leave and forecasting leave balances</span></span>

<span data-ttu-id="cc5d0-140">Azzal a változással, amely lehetővé teszi az alkalmazottak számára a szabadságok előrejelzését és a jövőbeli szabdságkérelmek benyújtását anélkül, hogy ez befolyásolná a jelenlegi szabadságegyenlegeiket, a szabadságegyenlegek megjelenési módja is változik.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-140">With the changes being made to allow for employees to forecast time off and request future time off requests without impacting their current time off balances, the way the time off balances are displayed is also changing.</span></span> 

<span data-ttu-id="cc5d0-141">A rendelkezésre álló egyenleg jelenleg megjeleníti a szabadságkérésre rendelkezésre álló időt, beleértve a könyveléseket a mai dátumig, és az összes jóváhagyott távollétkérelmet az idők végezetéig.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-141">The available balance currently displayed is the amount of time off available for requests including accruals through today and all approved leave requests to the end of time.</span></span> 

<span data-ttu-id="cc5d0-142">Az előrejelzési képesség kiadásával a megjelenített egyenleg megváltozik: az aktuális szabadságegyenleg lesz, beleértve a könyveléseket a mai dátumig, és a kéréseket a mai dátumig.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-142">When the ability to forecast is released, the balance displayed changes to  be the current balance of time off including accruals through today and requests through today.</span></span> <span data-ttu-id="cc5d0-143">Az alkalmazottak és vezetők számára a frissített egyenlegek az alkalmazotti és a vezetői önkiszolgáló felületen jelennek meg a **Szabadság** kártyán és a **Szabadságegyenlegek** ablakban.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-143">Employees and managers will see these updated balances in employee and manager self-service on the **Time off** card and in the **Time off balances** window.</span></span> <span data-ttu-id="cc5d0-144">A HR-vezetők a frissített egyenlegeket a **Személyek** munkaterületen és az alkalmazott **Alkalmazotthoz rendelt szabadságtervek** ablakában láthatják.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-144">HR managers will see these updated balances in the **People** workspace and in the employee’s **Assigned leave plans** window.</span></span>

## <a name="known-issue"></a><span data-ttu-id="cc5d0-145">Ismert probléma</span><span class="sxs-lookup"><span data-stu-id="cc5d0-145">Known issue</span></span>

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a><span data-ttu-id="cc5d0-146">A Finance and Operations integráció hibáinek leképezése</span><span class="sxs-lookup"><span data-stu-id="cc5d0-146">Mapping errors in the integration with Finance and Operations</span></span>

<span data-ttu-id="cc5d0-147">A következő problémákat azonosítottuk a Talent és a Dynamics 365 for Finance and Operations integrációjának aktuális sablonjában.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-147">The following issues have been identified in the current template for integrating Talent with Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="cc5d0-148">Hamarosan új sablont teszünk közzé, amely minden létrehozott új integrációs projektekre alkalmazva lesz.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-148">A new template will be published soon and will be applied to all new integration projects that are created.</span></span> <span data-ttu-id="cc5d0-149">A meglévő integrációs projektek esetén a feladat-hozzárendelésekhez lehet frissíteni.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-149">For existing integration projects, the task mappings can be updated.</span></span> <span data-ttu-id="cc5d0-150">A frissített leképezésekért tekintse át a következő táblázatot.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-150">Refer to the following table for updated mappings.</span></span> 

>[!NOTE]
> <span data-ttu-id="cc5d0-151">A Munkabeosztások a szülő munka-hozzárendelésbe feadat nem integrálja az adatokat.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-151">The Job Positions to Positions Parent Job Assignment task does not integrate data.</span></span> <span data-ttu-id="cc5d0-152">Ezt a hibát jelenleg vizsgáljuk.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-152">This is an issue that is currently being researched.</span></span> <span data-ttu-id="cc5d0-153">Az aktuális leképezésben nincs megkerülő megoldás.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-153">There is no workaround in the current mapping.</span></span> 

<span data-ttu-id="cc5d0-154">A részlegek az üzemi egységbe feladat esetében frissíteni kell a következő hozzárendeléseket.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-154">The Departments to Operating unit task needs the following mappings updated.</span></span>

| <span data-ttu-id="cc5d0-155">Meglévő forrásmező</span><span class="sxs-lookup"><span data-stu-id="cc5d0-155">Existing source field</span></span>          | <span data-ttu-id="cc5d0-156">Új forrásmező</span><span class="sxs-lookup"><span data-stu-id="cc5d0-156">New source field</span></span> |
| -------------------------------|------------------|
| <span data-ttu-id="cc5d0-157">cdm_description (leírás)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-157">cdm_description (Description)</span></span>  | <span data-ttu-id="cc5d0-158">cdm_name (név)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-158">cdm_name (Name)</span></span>  |

<span data-ttu-id="cc5d0-159">Egy további leképezést is kell megadni.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-159">An additional mapping also needs to be added.</span></span> <span data-ttu-id="cc5d0-160">Válassza ki az utolsó **Nincs** mezőt a következő leképezések hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-160">Select the last **None** field to add the following mapping.</span></span>

| <span data-ttu-id="cc5d0-161">Forrásmező</span><span class="sxs-lookup"><span data-stu-id="cc5d0-161">Source field</span></span>                   | <span data-ttu-id="cc5d0-162">Célmező</span><span class="sxs-lookup"><span data-stu-id="cc5d0-162">Destination field</span></span>    |
| -------------------------------|----------------------|
| <span data-ttu-id="cc5d0-163">cdm_description (leírás)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-163">cdm_description (Description)</span></span>  | <span data-ttu-id="cc5d0-164">NAMEALIAS (NAMEALIAS)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-164">NAMEALIAS (NAMEALIAS)</span></span>|

<span data-ttu-id="cc5d0-165">A frissített leképezéseknek a következő kép szerint kell kinézniük.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-165">The updated mappings should look like the following image.</span></span>

![Részlegek az üzemi egységbe feladat](./media/DepartmentMapping.png)


<span data-ttu-id="cc5d0-167">A feladatok a feladat részleteibe feladat esetében frissíteni kell a következő hozzárendeléseket.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-167">The Jobs to Job Detail task needs the following mappings updated.</span></span>

| <span data-ttu-id="cc5d0-168">Meglévő forrásmező</span><span class="sxs-lookup"><span data-stu-id="cc5d0-168">Existing source field</span></span>          | <span data-ttu-id="cc5d0-169">Új forrásmező</span><span class="sxs-lookup"><span data-stu-id="cc5d0-169">New source field</span></span>                   |
| -------------------------------|------------------------------------|
| <span data-ttu-id="cc5d0-170">cdm_name (név)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-170">cdm_name (Name)</span></span>                | <span data-ttu-id="cc5d0-171">cdm_description (leírás)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-171">cdm_description (Description)</span></span>      |
| <span data-ttu-id="cc5d0-172">cdm_name (leírás)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-172">cdm_name (Description)</span></span>         | <span data-ttu-id="cc5d0-173">cdm_jobdescription(munkaköri leírás)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-173">cdm_jobdescription(Job Description)</span></span>|


<span data-ttu-id="cc5d0-174">A frissített leképezéseknek az alábbi kép szerint kell kinézniük.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-174">The updated mappings should look like the image below.</span></span>

![Feladatok a feladat részleteibe feladat](./media/JobMapping.png)

<span data-ttu-id="cc5d0-176">A dolgozók a munkához feladat esetében frissíteni kell a következő hozzárendeléseket.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-176">The Workers to Work task needs the following mappings updated.</span></span>

| <span data-ttu-id="cc5d0-177">Meglévő forrásmező</span><span class="sxs-lookup"><span data-stu-id="cc5d0-177">Existing source field</span></span>                 | <span data-ttu-id="cc5d0-178">Új forrásmező</span><span class="sxs-lookup"><span data-stu-id="cc5d0-178">New source field</span></span>                               |
| --------------------------------------|------------------------------------------------|
| <span data-ttu-id="cc5d0-179">cdm_emailaddress1 (1. e-mail-cím)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-179">cdm_emailaddress1 (Email Address 1)</span></span>   | <span data-ttu-id="cc5d0-180">cdm_primaryemailaddress (elsődleges e-mail-cím)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-180">cdm_primaryemailaddress (Primary Email Address</span></span> |
| <span data-ttu-id="cc5d0-181">cdm_telephone1 (1. telefon)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-181">cdm_telephone1 (Telephone 1)</span></span>          | <span data-ttu-id="cc5d0-182">cdm_primarytelephone (elsődleges telefonszám)</span><span class="sxs-lookup"><span data-stu-id="cc5d0-182">cdm_primarytelephone (Primary Telephone)</span></span>       |

<span data-ttu-id="cc5d0-183">A Nem mezőtranszformációt is frissíteni kell.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-183">The Gender field transform also needs to be updated.</span></span> <span data-ttu-id="cc5d0-184">Válassza ki a **fn** (függvény) leképezéstípust a nemhez, és frissítse a következő értékleképezéseket.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-184">Select the **fn** (function) map type for Gender and update the following value mappings.</span></span>

| <span data-ttu-id="cc5d0-185">CDS-érték</span><span class="sxs-lookup"><span data-stu-id="cc5d0-185">CDS value</span></span>                   | <span data-ttu-id="cc5d0-186">Finance and Operations érték</span><span class="sxs-lookup"><span data-stu-id="cc5d0-186">Finance and Operations value</span></span>                     |
| ----------------------------|--------------------------------------------------|
| <span data-ttu-id="cc5d0-187">75440000</span><span class="sxs-lookup"><span data-stu-id="cc5d0-187">75440000</span></span>                    | <span data-ttu-id="cc5d0-188">Férfi</span><span class="sxs-lookup"><span data-stu-id="cc5d0-188">Male</span></span>                                             |
| <span data-ttu-id="cc5d0-189">75440001</span><span class="sxs-lookup"><span data-stu-id="cc5d0-189">75440001</span></span>                    | <span data-ttu-id="cc5d0-190">Nő</span><span class="sxs-lookup"><span data-stu-id="cc5d0-190">Female</span></span>                                           |
| <span data-ttu-id="cc5d0-191">75440002</span><span class="sxs-lookup"><span data-stu-id="cc5d0-191">75440002</span></span>                    | <span data-ttu-id="cc5d0-192">Egyik sem</span><span class="sxs-lookup"><span data-stu-id="cc5d0-192">None</span></span>                                             | 
| <span data-ttu-id="cc5d0-193">75440003</span><span class="sxs-lookup"><span data-stu-id="cc5d0-193">75440003</span></span>                    | <span data-ttu-id="cc5d0-194">Nem meghatározott</span><span class="sxs-lookup"><span data-stu-id="cc5d0-194">NonSpecific</span></span>                                      |

<span data-ttu-id="cc5d0-195">A frissített leképezéseknek a következő képek szerint kell kinézniük.</span><span class="sxs-lookup"><span data-stu-id="cc5d0-195">The updated mappings should look like the following images.</span></span>

![Dolgozók a munkához feladat](./media/WorkerMapping.png)

![Nem mezőtranszformáció](./media/WorkerTransform.png)
