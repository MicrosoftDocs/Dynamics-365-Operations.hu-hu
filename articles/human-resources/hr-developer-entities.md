---
title: Dataverse-táblák
description: A Microsoft Dynamics 365 Human Resources a Dataverse használatával biztosítja a bővíthetőségi és az integrációs eseteket.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 325bd8a9de07e3978ff6c513975a0e8db22854e0
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054356"
---
# <a name="dataverse-tables"></a><span data-ttu-id="9095a-103">Dataverse-táblák</span><span class="sxs-lookup"><span data-stu-id="9095a-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="9095a-104">A Microsoft Dynamics 365 Human Resources a Dataverse használatával biztosítja a bővíthetőségi és az integrációs eseteket.</span><span class="sxs-lookup"><span data-stu-id="9095a-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="9095a-105">A Human Resources entitások Dataverse-tábláknak felelnek meg.</span><span class="sxs-lookup"><span data-stu-id="9095a-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="9095a-106">A Dataverse (a korábbi Common Data Service) rendszer kapcsolatos további tudnivalókat és a terminológiai frissítéseket lásd: [Mi a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="9095a-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="9095a-107">A következő, Human Resources-entitásokon alapuló Dataverse-táblák érhetők el.</span><span class="sxs-lookup"><span data-stu-id="9095a-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="9095a-108">Juttatási táblák</span><span class="sxs-lookup"><span data-stu-id="9095a-108">Benefit tables</span></span>

| <span data-ttu-id="9095a-109">Név</span><span class="sxs-lookup"><span data-stu-id="9095a-109">Name</span></span> | <span data-ttu-id="9095a-110">Tábla</span><span class="sxs-lookup"><span data-stu-id="9095a-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9095a-111">Juttatás számítási gyakorisága</span><span class="sxs-lookup"><span data-stu-id="9095a-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="9095a-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="9095a-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="9095a-113">Fizetési időszak juttatásszámítási gyakorisága</span><span class="sxs-lookup"><span data-stu-id="9095a-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="9095a-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="9095a-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="9095a-115">Juttatásszámítás gyakorisága</span><span class="sxs-lookup"><span data-stu-id="9095a-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="9095a-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="9095a-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="9095a-117">Juttatás számítási mértékének részletei</span><span class="sxs-lookup"><span data-stu-id="9095a-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="9095a-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="9095a-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="9095a-119">Juttatási lehetőség</span><span class="sxs-lookup"><span data-stu-id="9095a-119">Benefit Option</span></span> | <span data-ttu-id="9095a-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="9095a-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="9095a-121">Juttatási terv</span><span class="sxs-lookup"><span data-stu-id="9095a-121">Benefit Plan</span></span> | <span data-ttu-id="9095a-122">cdm_benefitplan (egyéni mezőtámogatáshoz nem engedélyezett)</span><span class="sxs-lookup"><span data-stu-id="9095a-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="9095a-123">Juttatás típusa</span><span class="sxs-lookup"><span data-stu-id="9095a-123">Benefit Type</span></span> | <span data-ttu-id="9095a-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="9095a-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="9095a-125">Üzleti folyamat feladatok táblái</span><span class="sxs-lookup"><span data-stu-id="9095a-125">Business process tasks tables</span></span>

| <span data-ttu-id="9095a-126">Név</span><span class="sxs-lookup"><span data-stu-id="9095a-126">Name</span></span> | <span data-ttu-id="9095a-127">Tábla</span><span class="sxs-lookup"><span data-stu-id="9095a-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9095a-128">Üzletifolyamat-naptár</span><span class="sxs-lookup"><span data-stu-id="9095a-128">Business Process Calendar</span></span> | <span data-ttu-id="9095a-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="9095a-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="9095a-130">Üzletifolyamat-csoport hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="9095a-130">Business Process Group Assignment</span></span> | <span data-ttu-id="9095a-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="9095a-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="9095a-132">Üzletifolyamat-tár feladatcsoportja</span><span class="sxs-lookup"><span data-stu-id="9095a-132">Business Process Library Task Group</span></span> | <span data-ttu-id="9095a-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="9095a-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="9095a-134">Üzleti folyamat szakasza</span><span class="sxs-lookup"><span data-stu-id="9095a-134">Business Process Stage</span></span> | <span data-ttu-id="9095a-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="9095a-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="9095a-136">Ellenőrzőlista-sablon fejléce</span><span class="sxs-lookup"><span data-stu-id="9095a-136">Checklist Template Header</span></span> | <span data-ttu-id="9095a-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="9095a-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="9095a-138">Ellenőrzőlistasablon-feladat</span><span class="sxs-lookup"><span data-stu-id="9095a-138">Checklist Template Task</span></span> | <span data-ttu-id="9095a-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="9095a-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="9095a-140">Kompenzációs táblák</span><span class="sxs-lookup"><span data-stu-id="9095a-140">Compensation tables</span></span>

| <span data-ttu-id="9095a-141">Név</span><span class="sxs-lookup"><span data-stu-id="9095a-141">Name</span></span> | <span data-ttu-id="9095a-142">Tábla</span><span class="sxs-lookup"><span data-stu-id="9095a-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9095a-143">Kompenzációs fix terv</span><span class="sxs-lookup"><span data-stu-id="9095a-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="9095a-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="9095a-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="9095a-145">Kompenzációs rács</span><span class="sxs-lookup"><span data-stu-id="9095a-145">Compensation Grid</span></span> | <span data-ttu-id="9095a-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="9095a-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="9095a-147">Kompenzációs szint</span><span class="sxs-lookup"><span data-stu-id="9095a-147">Compensation Level</span></span> | <span data-ttu-id="9095a-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="9095a-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="9095a-149">Kompenzáció – fizetés gyakorisága</span><span class="sxs-lookup"><span data-stu-id="9095a-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="9095a-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="9095a-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="9095a-151">Kompenzációs hivatkozási pont beállítása</span><span class="sxs-lookup"><span data-stu-id="9095a-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="9095a-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="9095a-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="9095a-153">Kompenzációs hivatkozási pontok beállítási sora</span><span class="sxs-lookup"><span data-stu-id="9095a-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="9095a-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="9095a-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="9095a-155">Kompenzációs régió</span><span class="sxs-lookup"><span data-stu-id="9095a-155">Compensation Region</span></span> | <span data-ttu-id="9095a-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="9095a-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="9095a-157">Kompenzációs struktúra</span><span class="sxs-lookup"><span data-stu-id="9095a-157">Compensation Structure</span></span> | <span data-ttu-id="9095a-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="9095a-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="9095a-159">Változó kompenzációs konstrukció</span><span class="sxs-lookup"><span data-stu-id="9095a-159">Compensation Variable Plan</span></span> | <span data-ttu-id="9095a-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="9095a-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="9095a-161">Változó kompenzációs konstrukció szintje</span><span class="sxs-lookup"><span data-stu-id="9095a-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="9095a-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="9095a-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="9095a-163">Változó kompenzációs konstrukció típusa</span><span class="sxs-lookup"><span data-stu-id="9095a-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="9095a-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="9095a-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="9095a-165">Fix kompenzációs esemény</span><span class="sxs-lookup"><span data-stu-id="9095a-165">Fixed Compensation Event</span></span> | <span data-ttu-id="9095a-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="9095a-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="9095a-167">Átruházási szabály</span><span class="sxs-lookup"><span data-stu-id="9095a-167">Vesting Rule</span></span> | <span data-ttu-id="9095a-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="9095a-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="9095a-169">Dolgozói fix kompenzáció</span><span class="sxs-lookup"><span data-stu-id="9095a-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="9095a-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="9095a-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="9095a-171">Szervezeti táblák</span><span class="sxs-lookup"><span data-stu-id="9095a-171">Organization tables</span></span>

| <span data-ttu-id="9095a-172">Név</span><span class="sxs-lookup"><span data-stu-id="9095a-172">Name</span></span> | <span data-ttu-id="9095a-173">Tábla</span><span class="sxs-lookup"><span data-stu-id="9095a-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9095a-174">Részleg</span><span class="sxs-lookup"><span data-stu-id="9095a-174">Department</span></span> | <span data-ttu-id="9095a-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="9095a-175">cdm_department</span></span> |
| <span data-ttu-id="9095a-176">Alkalmazás</span><span class="sxs-lookup"><span data-stu-id="9095a-176">Employment</span></span> | <span data-ttu-id="9095a-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="9095a-177">cdm_employment</span></span> |
| <span data-ttu-id="9095a-178">Cég</span><span class="sxs-lookup"><span data-stu-id="9095a-178">Company</span></span> | <span data-ttu-id="9095a-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="9095a-179">cdm_company</span></span> |
| <span data-ttu-id="9095a-180">Állás</span><span class="sxs-lookup"><span data-stu-id="9095a-180">Job</span></span> | <span data-ttu-id="9095a-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="9095a-181">cdm_job</span></span> |
| <span data-ttu-id="9095a-182">Beosztás funkciója</span><span class="sxs-lookup"><span data-stu-id="9095a-182">Job Function</span></span> | <span data-ttu-id="9095a-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="9095a-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="9095a-184">Beosztás</span><span class="sxs-lookup"><span data-stu-id="9095a-184">Job Position</span></span> | <span data-ttu-id="9095a-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="9095a-185">cdm_jobposition</span></span> |
| <span data-ttu-id="9095a-186">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="9095a-186">Position Type</span></span> | <span data-ttu-id="9095a-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="9095a-187">cdm_positiontype</span></span> |
| <span data-ttu-id="9095a-188">Beosztáshoz rendelt dolgozó</span><span class="sxs-lookup"><span data-stu-id="9095a-188">Position Worker Assignment</span></span> | <span data-ttu-id="9095a-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="9095a-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="9095a-190">Beosztásdimenzió</span><span class="sxs-lookup"><span data-stu-id="9095a-190">Job Position Dimension</span></span> | <span data-ttu-id="9095a-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="9095a-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="9095a-192">Állás típusa</span><span class="sxs-lookup"><span data-stu-id="9095a-192">Job Type</span></span> | <span data-ttu-id="9095a-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="9095a-193">cdm_jobtype</span></span> |
| <span data-ttu-id="9095a-194">Nyelv</span><span class="sxs-lookup"><span data-stu-id="9095a-194">Language</span></span> | <span data-ttu-id="9095a-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="9095a-195">cdm_language</span></span> |
| <span data-ttu-id="9095a-196">Megszólítás</span><span class="sxs-lookup"><span data-stu-id="9095a-196">Title</span></span> | <span data-ttu-id="9095a-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="9095a-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="9095a-198">A **Beosztás típusa**, **Beosztáshoz rendelt dolgozó** és **Foglalkoztatás** pénzügyi dimenziói egyirányú integrációt biztosítanak a Dataverse felé.</span><span class="sxs-lookup"><span data-stu-id="9095a-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="9095a-199">A pénzügyi dimenziók frissítései jelenleg nem szinkronizálnak a Dataverse szolgáltatásból Human Resources alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="9095a-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="9095a-200">Szabadság és távollét táblák</span><span class="sxs-lookup"><span data-stu-id="9095a-200">Leave and absence tables</span></span>

| <span data-ttu-id="9095a-201">Név</span><span class="sxs-lookup"><span data-stu-id="9095a-201">Name</span></span> | <span data-ttu-id="9095a-202">Tábla</span><span class="sxs-lookup"><span data-stu-id="9095a-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9095a-203">Szabadsági banki tranzakció</span><span class="sxs-lookup"><span data-stu-id="9095a-203">Leave Bank Transaction</span></span> | <span data-ttu-id="9095a-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="9095a-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="9095a-205">Szabadságbejegyzés</span><span class="sxs-lookup"><span data-stu-id="9095a-205">Leave Enrollment</span></span> | <span data-ttu-id="9095a-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="9095a-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="9095a-207">Szabadságterv</span><span class="sxs-lookup"><span data-stu-id="9095a-207">Leave Plan</span></span> | <span data-ttu-id="9095a-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="9095a-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="9095a-209">Szabadságkérelem</span><span class="sxs-lookup"><span data-stu-id="9095a-209">Leave Request</span></span> | <span data-ttu-id="9095a-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="9095a-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="9095a-211">Szabadságkérelem részletes adatai</span><span class="sxs-lookup"><span data-stu-id="9095a-211">Leave Request Detail</span></span> | <span data-ttu-id="9095a-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="9095a-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="9095a-213">Szabadság típusa</span><span class="sxs-lookup"><span data-stu-id="9095a-213">Leave Type</span></span> | <span data-ttu-id="9095a-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="9095a-214">cdm_leavetype</span></span> |
| <span data-ttu-id="9095a-215">Szabadságtípus okkódja</span><span class="sxs-lookup"><span data-stu-id="9095a-215">Leave Type Reason Code</span></span> | <span data-ttu-id="9095a-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="9095a-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="9095a-217">Bérlistatáblák</span><span class="sxs-lookup"><span data-stu-id="9095a-217">Payroll tables</span></span>

| <span data-ttu-id="9095a-218">Név</span><span class="sxs-lookup"><span data-stu-id="9095a-218">Name</span></span> | <span data-ttu-id="9095a-219">Tábla</span><span class="sxs-lookup"><span data-stu-id="9095a-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9095a-220">Fizetési ciklus</span><span class="sxs-lookup"><span data-stu-id="9095a-220">Pay Cycle</span></span> | <span data-ttu-id="9095a-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="9095a-221">cdm_paycycle</span></span> |
| <span data-ttu-id="9095a-222">Fizetési időszak</span><span class="sxs-lookup"><span data-stu-id="9095a-222">Pay Period</span></span> | <span data-ttu-id="9095a-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="9095a-223">cdm_payperiod</span></span> |
| <span data-ttu-id="9095a-224">Bérlista bevételkódja</span><span class="sxs-lookup"><span data-stu-id="9095a-224">Payroll Earning Code</span></span> | <span data-ttu-id="9095a-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="9095a-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="9095a-226">Bankszámla kifizetései</span><span class="sxs-lookup"><span data-stu-id="9095a-226">Bank Account Disbursement</span></span> | <span data-ttu-id="9095a-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="9095a-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="9095a-228">Adórégió</span><span class="sxs-lookup"><span data-stu-id="9095a-228">Tax Region</span></span> | <span data-ttu-id="9095a-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="9095a-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="9095a-230">Dolgozói táblák</span><span class="sxs-lookup"><span data-stu-id="9095a-230">Worker tables</span></span>

| <span data-ttu-id="9095a-231">Név</span><span class="sxs-lookup"><span data-stu-id="9095a-231">Name</span></span> | <span data-ttu-id="9095a-232">Tábla</span><span class="sxs-lookup"><span data-stu-id="9095a-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9095a-233">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="9095a-233">Worker</span></span> | <span data-ttu-id="9095a-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="9095a-234">cdm_worker</span></span> |
| <span data-ttu-id="9095a-235">Dolgozói cím</span><span class="sxs-lookup"><span data-stu-id="9095a-235">Worker Address</span></span> | <span data-ttu-id="9095a-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="9095a-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="9095a-237">Dolgozói személyes adat</span><span class="sxs-lookup"><span data-stu-id="9095a-237">Worker Personal Detail</span></span> | <span data-ttu-id="9095a-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="9095a-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="9095a-239">Dolgozó személyazonosító száma</span><span class="sxs-lookup"><span data-stu-id="9095a-239">Worker Person Identification Number</span></span> | <span data-ttu-id="9095a-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="9095a-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="9095a-241">Dolgozó személyazonosító típusa</span><span class="sxs-lookup"><span data-stu-id="9095a-241">Worker Person Identification Type</span></span> | <span data-ttu-id="9095a-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="9095a-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="9095a-243">Munkanaptár</span><span class="sxs-lookup"><span data-stu-id="9095a-243">Work Calendar</span></span> | <span data-ttu-id="9095a-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="9095a-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="9095a-245">Munkanaptár napja</span><span class="sxs-lookup"><span data-stu-id="9095a-245">Work Calendar Day</span></span> | <span data-ttu-id="9095a-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="9095a-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="9095a-247">Munkanaptári ünnep</span><span class="sxs-lookup"><span data-stu-id="9095a-247">Work Calendar Holiday</span></span> |<span data-ttu-id="9095a-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="9095a-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="9095a-249">Munkanaptár ünnepsora</span><span class="sxs-lookup"><span data-stu-id="9095a-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="9095a-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="9095a-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="9095a-251">Munkanaptár időintervalluma</span><span class="sxs-lookup"><span data-stu-id="9095a-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="9095a-252">cdm_workcalendartimeinterval (egyéni mezőtámogatáshoz nem engedélyezett)</span><span class="sxs-lookup"><span data-stu-id="9095a-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="9095a-253">Dolgozói bankszámla</span><span class="sxs-lookup"><span data-stu-id="9095a-253">Worker Bank Account</span></span> | <span data-ttu-id="9095a-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="9095a-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="9095a-255">Dolgozóbeállítási táblák</span><span class="sxs-lookup"><span data-stu-id="9095a-255">Worker setup tables</span></span>

| <span data-ttu-id="9095a-256">Név</span><span class="sxs-lookup"><span data-stu-id="9095a-256">Name</span></span> | <span data-ttu-id="9095a-257">Tábla</span><span class="sxs-lookup"><span data-stu-id="9095a-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9095a-258">Veteránállapot</span><span class="sxs-lookup"><span data-stu-id="9095a-258">Veteran Status</span></span> | <span data-ttu-id="9095a-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="9095a-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="9095a-260">Etnikum</span><span class="sxs-lookup"><span data-stu-id="9095a-260">Ethnic Origin</span></span> | <span data-ttu-id="9095a-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="9095a-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="9095a-262">Okkód</span><span class="sxs-lookup"><span data-stu-id="9095a-262">Reason Code</span></span> | <span data-ttu-id="9095a-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="9095a-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="9095a-264">Személyazonosító-kibocsátó hivatal</span><span class="sxs-lookup"><span data-stu-id="9095a-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="9095a-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="9095a-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="9095a-266">Kompetenciatáblák</span><span class="sxs-lookup"><span data-stu-id="9095a-266">Competency tables</span></span>

| <span data-ttu-id="9095a-267">Név</span><span class="sxs-lookup"><span data-stu-id="9095a-267">Name</span></span> | <span data-ttu-id="9095a-268">Tábla</span><span class="sxs-lookup"><span data-stu-id="9095a-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="9095a-269">Szakértelemtípus</span><span class="sxs-lookup"><span data-stu-id="9095a-269">Skill Type</span></span> | <span data-ttu-id="9095a-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="9095a-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="9095a-271">Táblakapcsolati modellek</span><span class="sxs-lookup"><span data-stu-id="9095a-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="9095a-272">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="9095a-272">Worker</span></span>

![Dolgozó](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="9095a-274">Feladat és feladat beosztása</span><span class="sxs-lookup"><span data-stu-id="9095a-274">Job and Job Position</span></span>

![Feladat és feladat beosztása](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="9095a-276">Előnyök</span><span class="sxs-lookup"><span data-stu-id="9095a-276">Benefits</span></span>

![Előnyök](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="9095a-278">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="9095a-278">Compensation</span></span>

![Kompenzáció](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="9095a-280">Kilépés</span><span class="sxs-lookup"><span data-stu-id="9095a-280">Leave</span></span>

![Kilépés](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="9095a-282">Munkanaptár</span><span class="sxs-lookup"><span data-stu-id="9095a-282">Work Calendar</span></span>

![Munkanaptár](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="9095a-284">Lásd még</span><span class="sxs-lookup"><span data-stu-id="9095a-284">See also</span></span>

[<span data-ttu-id="9095a-285">Adatintegrációs technológia kiválasztása</span><span class="sxs-lookup"><span data-stu-id="9095a-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="9095a-286">A Dataverse-integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9095a-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="9095a-287">Dataverse virtuális táblák konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9095a-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="9095a-288">A Human Resources számára elérhető virtuális táblák – GYIK</span><span class="sxs-lookup"><span data-stu-id="9095a-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="9095a-289">Mi az a Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="9095a-289">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="9095a-290">Terminológia frissítései</span><span class="sxs-lookup"><span data-stu-id="9095a-290">Terminology updates</span></span>](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]