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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ddb74a2f0b6265c5be3c13a009211455ea862da
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893400"
---
# <a name="dataverse-tables"></a><span data-ttu-id="02985-103">Dataverse-táblák</span><span class="sxs-lookup"><span data-stu-id="02985-103">Dataverse tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="02985-104">A Microsoft Dynamics 365 Human Resources a Dataverse használatával biztosítja a bővíthetőségi és az integrációs eseteket.</span><span class="sxs-lookup"><span data-stu-id="02985-104">Microsoft Dynamics 365 Human Resources uses Dataverse to enable extensibility and integration scenarios.</span></span>

> [!NOTE]
> <span data-ttu-id="02985-105">A Human Resources entitások Dataverse-tábláknak felelnek meg.</span><span class="sxs-lookup"><span data-stu-id="02985-105">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="02985-106">A Dataverse (a korábbi Common Data Service) rendszer kapcsolatos további tudnivalókat és a terminológiai frissítéseket lásd: [Mi a Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="02985-106">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="02985-107">A következő, Human Resources-entitásokon alapuló Dataverse-táblák érhetők el.</span><span class="sxs-lookup"><span data-stu-id="02985-107">The following Dataverse tables are available based on Human Resources entities.</span></span>

## <a name="benefit-tables"></a><span data-ttu-id="02985-108">Juttatási táblák</span><span class="sxs-lookup"><span data-stu-id="02985-108">Benefit tables</span></span>

| <span data-ttu-id="02985-109">Név</span><span class="sxs-lookup"><span data-stu-id="02985-109">Name</span></span> | <span data-ttu-id="02985-110">Tábla</span><span class="sxs-lookup"><span data-stu-id="02985-110">Table</span></span> |
| --- | --- |
| <span data-ttu-id="02985-111">Juttatás számítási gyakorisága</span><span class="sxs-lookup"><span data-stu-id="02985-111">Benefit Calculation Frequency</span></span> | <span data-ttu-id="02985-112">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="02985-112">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="02985-113">Fizetési időszak juttatásszámítási gyakorisága</span><span class="sxs-lookup"><span data-stu-id="02985-113">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="02985-114">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="02985-114">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="02985-115">Juttatásszámítás gyakorisága</span><span class="sxs-lookup"><span data-stu-id="02985-115">Benefit Calculation Rate</span></span> | <span data-ttu-id="02985-116">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="02985-116">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="02985-117">Juttatás számítási mértékének részletei</span><span class="sxs-lookup"><span data-stu-id="02985-117">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="02985-118">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="02985-118">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="02985-119">Juttatási lehetőség</span><span class="sxs-lookup"><span data-stu-id="02985-119">Benefit Option</span></span> | <span data-ttu-id="02985-120">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="02985-120">cdm_benefitoption</span></span> |
| <span data-ttu-id="02985-121">Juttatási terv</span><span class="sxs-lookup"><span data-stu-id="02985-121">Benefit Plan</span></span> | <span data-ttu-id="02985-122">cdm_benefitplan (egyéni mezőtámogatáshoz nem engedélyezett)</span><span class="sxs-lookup"><span data-stu-id="02985-122">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="02985-123">Juttatás típusa</span><span class="sxs-lookup"><span data-stu-id="02985-123">Benefit Type</span></span> | <span data-ttu-id="02985-124">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="02985-124">cdm_benefittype</span></span> |

## <a name="business-process-tasks-tables"></a><span data-ttu-id="02985-125">Üzleti folyamat feladatok táblái</span><span class="sxs-lookup"><span data-stu-id="02985-125">Business process tasks tables</span></span>

| <span data-ttu-id="02985-126">Név</span><span class="sxs-lookup"><span data-stu-id="02985-126">Name</span></span> | <span data-ttu-id="02985-127">Tábla</span><span class="sxs-lookup"><span data-stu-id="02985-127">Table</span></span> |
| --- | --- |
| <span data-ttu-id="02985-128">Üzletifolyamat-naptár</span><span class="sxs-lookup"><span data-stu-id="02985-128">Business Process Calendar</span></span> | <span data-ttu-id="02985-129">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="02985-129">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="02985-130">Üzletifolyamat-csoport hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="02985-130">Business Process Group Assignment</span></span> | <span data-ttu-id="02985-131">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="02985-131">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="02985-132">Üzletifolyamat-tár feladatcsoportja</span><span class="sxs-lookup"><span data-stu-id="02985-132">Business Process Library Task Group</span></span> | <span data-ttu-id="02985-133">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="02985-133">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="02985-134">Üzleti folyamat szakasza</span><span class="sxs-lookup"><span data-stu-id="02985-134">Business Process Stage</span></span> | <span data-ttu-id="02985-135">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="02985-135">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="02985-136">Ellenőrzőlista-sablon fejléce</span><span class="sxs-lookup"><span data-stu-id="02985-136">Checklist Template Header</span></span> | <span data-ttu-id="02985-137">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="02985-137">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="02985-138">Ellenőrzőlistasablon-feladat</span><span class="sxs-lookup"><span data-stu-id="02985-138">Checklist Template Task</span></span> | <span data-ttu-id="02985-139">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="02985-139">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-tables"></a><span data-ttu-id="02985-140">Kompenzációs táblák</span><span class="sxs-lookup"><span data-stu-id="02985-140">Compensation tables</span></span>

| <span data-ttu-id="02985-141">Név</span><span class="sxs-lookup"><span data-stu-id="02985-141">Name</span></span> | <span data-ttu-id="02985-142">Tábla</span><span class="sxs-lookup"><span data-stu-id="02985-142">Table</span></span> |
| --- | --- |
| <span data-ttu-id="02985-143">Kompenzációs fix terv</span><span class="sxs-lookup"><span data-stu-id="02985-143">Compensation Fixed Plan</span></span> | <span data-ttu-id="02985-144">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="02985-144">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="02985-145">Kompenzációs rács</span><span class="sxs-lookup"><span data-stu-id="02985-145">Compensation Grid</span></span> | <span data-ttu-id="02985-146">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="02985-146">cdm_compensationgrid</span></span> |
| <span data-ttu-id="02985-147">Kompenzációs szint</span><span class="sxs-lookup"><span data-stu-id="02985-147">Compensation Level</span></span> | <span data-ttu-id="02985-148">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="02985-148">cdm_compensationlevel</span></span> |
| <span data-ttu-id="02985-149">Kompenzáció – fizetés gyakorisága</span><span class="sxs-lookup"><span data-stu-id="02985-149">Compensation Pay Frequency</span></span> | <span data-ttu-id="02985-150">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="02985-150">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="02985-151">Kompenzációs hivatkozási pont beállítása</span><span class="sxs-lookup"><span data-stu-id="02985-151">Compensation Reference Point Setup</span></span> | <span data-ttu-id="02985-152">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="02985-152">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="02985-153">Kompenzációs hivatkozási pontok beállítási sora</span><span class="sxs-lookup"><span data-stu-id="02985-153">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="02985-154">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="02985-154">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="02985-155">Kompenzációs régió</span><span class="sxs-lookup"><span data-stu-id="02985-155">Compensation Region</span></span> | <span data-ttu-id="02985-156">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="02985-156">cdm_compensationregion</span></span> |
| <span data-ttu-id="02985-157">Kompenzációs struktúra</span><span class="sxs-lookup"><span data-stu-id="02985-157">Compensation Structure</span></span> | <span data-ttu-id="02985-158">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="02985-158">cdm_compensationstructure</span></span> |
| <span data-ttu-id="02985-159">Változó kompenzációs konstrukció</span><span class="sxs-lookup"><span data-stu-id="02985-159">Compensation Variable Plan</span></span> | <span data-ttu-id="02985-160">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="02985-160">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="02985-161">Változó kompenzációs konstrukció szintje</span><span class="sxs-lookup"><span data-stu-id="02985-161">Compensation Variable Plan Level</span></span> | <span data-ttu-id="02985-162">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="02985-162">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="02985-163">Változó kompenzációs konstrukció típusa</span><span class="sxs-lookup"><span data-stu-id="02985-163">Compensation Variable Plan Type</span></span> | <span data-ttu-id="02985-164">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="02985-164">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="02985-165">Fix kompenzációs esemény</span><span class="sxs-lookup"><span data-stu-id="02985-165">Fixed Compensation Event</span></span> | <span data-ttu-id="02985-166">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="02985-166">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="02985-167">Átruházási szabály</span><span class="sxs-lookup"><span data-stu-id="02985-167">Vesting Rule</span></span> | <span data-ttu-id="02985-168">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="02985-168">cdm_vestingrule</span></span> |
| <span data-ttu-id="02985-169">Dolgozói fix kompenzáció</span><span class="sxs-lookup"><span data-stu-id="02985-169">Worker Fixed Compensation</span></span> | <span data-ttu-id="02985-170">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="02985-170">cdm_workerfixedcompensation</span></span> |

## <a name="organization-tables"></a><span data-ttu-id="02985-171">Szervezeti táblák</span><span class="sxs-lookup"><span data-stu-id="02985-171">Organization tables</span></span>

| <span data-ttu-id="02985-172">Név</span><span class="sxs-lookup"><span data-stu-id="02985-172">Name</span></span> | <span data-ttu-id="02985-173">Tábla</span><span class="sxs-lookup"><span data-stu-id="02985-173">Table</span></span> |
| --- | --- |
| <span data-ttu-id="02985-174">Részleg</span><span class="sxs-lookup"><span data-stu-id="02985-174">Department</span></span> | <span data-ttu-id="02985-175">cdm_department</span><span class="sxs-lookup"><span data-stu-id="02985-175">cdm_department</span></span> |
| <span data-ttu-id="02985-176">Alkalmazás</span><span class="sxs-lookup"><span data-stu-id="02985-176">Employment</span></span> | <span data-ttu-id="02985-177">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="02985-177">cdm_employment</span></span> |
| <span data-ttu-id="02985-178">Cég</span><span class="sxs-lookup"><span data-stu-id="02985-178">Company</span></span> | <span data-ttu-id="02985-179">cdm_company</span><span class="sxs-lookup"><span data-stu-id="02985-179">cdm_company</span></span> |
| <span data-ttu-id="02985-180">Állás</span><span class="sxs-lookup"><span data-stu-id="02985-180">Job</span></span> | <span data-ttu-id="02985-181">cdm_job</span><span class="sxs-lookup"><span data-stu-id="02985-181">cdm_job</span></span> |
| <span data-ttu-id="02985-182">Beosztás funkciója</span><span class="sxs-lookup"><span data-stu-id="02985-182">Job Function</span></span> | <span data-ttu-id="02985-183">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="02985-183">cdm_jobfunction</span></span> |
| <span data-ttu-id="02985-184">Beosztás</span><span class="sxs-lookup"><span data-stu-id="02985-184">Job Position</span></span> | <span data-ttu-id="02985-185">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="02985-185">cdm_jobposition</span></span> |
| <span data-ttu-id="02985-186">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="02985-186">Position Type</span></span> | <span data-ttu-id="02985-187">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="02985-187">cdm_positiontype</span></span> |
| <span data-ttu-id="02985-188">Beosztáshoz rendelt dolgozó</span><span class="sxs-lookup"><span data-stu-id="02985-188">Position Worker Assignment</span></span> | <span data-ttu-id="02985-189">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="02985-189">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="02985-190">Beosztásdimenzió</span><span class="sxs-lookup"><span data-stu-id="02985-190">Job Position Dimension</span></span> | <span data-ttu-id="02985-191">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="02985-191">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="02985-192">Állás típusa</span><span class="sxs-lookup"><span data-stu-id="02985-192">Job Type</span></span> | <span data-ttu-id="02985-193">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="02985-193">cdm_jobtype</span></span> |
| <span data-ttu-id="02985-194">Nyelv</span><span class="sxs-lookup"><span data-stu-id="02985-194">Language</span></span> | <span data-ttu-id="02985-195">cdm_language</span><span class="sxs-lookup"><span data-stu-id="02985-195">cdm_language</span></span> |
| <span data-ttu-id="02985-196">Megszólítás</span><span class="sxs-lookup"><span data-stu-id="02985-196">Title</span></span> | <span data-ttu-id="02985-197">cdm_title</span><span class="sxs-lookup"><span data-stu-id="02985-197">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="02985-198">A **Beosztás típusa**, **Beosztáshoz rendelt dolgozó** és **Foglalkoztatás** pénzügyi dimenziói egyirányú integrációt biztosítanak a Dataverse felé.</span><span class="sxs-lookup"><span data-stu-id="02985-198">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Dataverse.</span></span> <span data-ttu-id="02985-199">A pénzügyi dimenziók frissítései jelenleg nem szinkronizálnak a Dataverse szolgáltatásból Human Resources alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="02985-199">Financial dimensions updates currently can't synchronize from Dataverse to Human Resources.</span></span> 

## <a name="leave-and-absence-tables"></a><span data-ttu-id="02985-200">Szabadság és távollét táblák</span><span class="sxs-lookup"><span data-stu-id="02985-200">Leave and absence tables</span></span>

| <span data-ttu-id="02985-201">Név</span><span class="sxs-lookup"><span data-stu-id="02985-201">Name</span></span> | <span data-ttu-id="02985-202">Tábla</span><span class="sxs-lookup"><span data-stu-id="02985-202">Table</span></span> |
| --- | --- |
| <span data-ttu-id="02985-203">Szabadsági banki tranzakció</span><span class="sxs-lookup"><span data-stu-id="02985-203">Leave Bank Transaction</span></span> | <span data-ttu-id="02985-204">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="02985-204">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="02985-205">Szabadságbejegyzés</span><span class="sxs-lookup"><span data-stu-id="02985-205">Leave Enrollment</span></span> | <span data-ttu-id="02985-206">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="02985-206">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="02985-207">Szabadságterv</span><span class="sxs-lookup"><span data-stu-id="02985-207">Leave Plan</span></span> | <span data-ttu-id="02985-208">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="02985-208">cdm_leaveplan</span></span> |
| <span data-ttu-id="02985-209">Szabadságkérelem</span><span class="sxs-lookup"><span data-stu-id="02985-209">Leave Request</span></span> | <span data-ttu-id="02985-210">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="02985-210">cdm_leaverequest</span></span> |
| <span data-ttu-id="02985-211">Szabadságkérelem részletes adatai</span><span class="sxs-lookup"><span data-stu-id="02985-211">Leave Request Detail</span></span> | <span data-ttu-id="02985-212">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="02985-212">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="02985-213">Szabadság típusa</span><span class="sxs-lookup"><span data-stu-id="02985-213">Leave Type</span></span> | <span data-ttu-id="02985-214">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="02985-214">cdm_leavetype</span></span> |
| <span data-ttu-id="02985-215">Szabadságtípus okkódja</span><span class="sxs-lookup"><span data-stu-id="02985-215">Leave Type Reason Code</span></span> | <span data-ttu-id="02985-216">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="02985-216">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-tables"></a><span data-ttu-id="02985-217">Bérlistatáblák</span><span class="sxs-lookup"><span data-stu-id="02985-217">Payroll tables</span></span>

| <span data-ttu-id="02985-218">Név</span><span class="sxs-lookup"><span data-stu-id="02985-218">Name</span></span> | <span data-ttu-id="02985-219">Tábla</span><span class="sxs-lookup"><span data-stu-id="02985-219">Table</span></span> |
| --- | --- |
| <span data-ttu-id="02985-220">Fizetési ciklus</span><span class="sxs-lookup"><span data-stu-id="02985-220">Pay Cycle</span></span> | <span data-ttu-id="02985-221">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="02985-221">cdm_paycycle</span></span> |
| <span data-ttu-id="02985-222">Fizetési időszak</span><span class="sxs-lookup"><span data-stu-id="02985-222">Pay Period</span></span> | <span data-ttu-id="02985-223">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="02985-223">cdm_payperiod</span></span> |
| <span data-ttu-id="02985-224">Bérlista bevételkódja</span><span class="sxs-lookup"><span data-stu-id="02985-224">Payroll Earning Code</span></span> | <span data-ttu-id="02985-225">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="02985-225">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="02985-226">Bankszámla kifizetései</span><span class="sxs-lookup"><span data-stu-id="02985-226">Bank Account Disbursement</span></span> | <span data-ttu-id="02985-227">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="02985-227">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="02985-228">Adórégió</span><span class="sxs-lookup"><span data-stu-id="02985-228">Tax Region</span></span> | <span data-ttu-id="02985-229">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="02985-229">cdm_taxregion</span></span> |

## <a name="worker-tables"></a><span data-ttu-id="02985-230">Dolgozói táblák</span><span class="sxs-lookup"><span data-stu-id="02985-230">Worker tables</span></span>

| <span data-ttu-id="02985-231">Név</span><span class="sxs-lookup"><span data-stu-id="02985-231">Name</span></span> | <span data-ttu-id="02985-232">Tábla</span><span class="sxs-lookup"><span data-stu-id="02985-232">Table</span></span> |
| --- | --- |
| <span data-ttu-id="02985-233">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="02985-233">Worker</span></span> | <span data-ttu-id="02985-234">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="02985-234">cdm_worker</span></span> |
| <span data-ttu-id="02985-235">Dolgozói cím</span><span class="sxs-lookup"><span data-stu-id="02985-235">Worker Address</span></span> | <span data-ttu-id="02985-236">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="02985-236">cdm_workeraddress</span></span> |
| <span data-ttu-id="02985-237">Dolgozói személyes adat</span><span class="sxs-lookup"><span data-stu-id="02985-237">Worker Personal Detail</span></span> | <span data-ttu-id="02985-238">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="02985-238">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="02985-239">Dolgozó személyazonosító száma</span><span class="sxs-lookup"><span data-stu-id="02985-239">Worker Person Identification Number</span></span> | <span data-ttu-id="02985-240">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="02985-240">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="02985-241">Dolgozó személyazonosító típusa</span><span class="sxs-lookup"><span data-stu-id="02985-241">Worker Person Identification Type</span></span> | <span data-ttu-id="02985-242">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="02985-242">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="02985-243">Munkanaptár</span><span class="sxs-lookup"><span data-stu-id="02985-243">Work Calendar</span></span> | <span data-ttu-id="02985-244">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="02985-244">cdm_workcalendar</span></span> |
| <span data-ttu-id="02985-245">Munkanaptár napja</span><span class="sxs-lookup"><span data-stu-id="02985-245">Work Calendar Day</span></span> | <span data-ttu-id="02985-246">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="02985-246">cdm_workcalendarday</span></span> |
| <span data-ttu-id="02985-247">Munkanaptári ünnep</span><span class="sxs-lookup"><span data-stu-id="02985-247">Work Calendar Holiday</span></span> |<span data-ttu-id="02985-248">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="02985-248">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="02985-249">Munkanaptár ünnepsora</span><span class="sxs-lookup"><span data-stu-id="02985-249">Work Calendar Holiday Line</span></span> | <span data-ttu-id="02985-250">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="02985-250">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="02985-251">Munkanaptár időintervalluma</span><span class="sxs-lookup"><span data-stu-id="02985-251">Work Calendar Time Interval</span></span> | <span data-ttu-id="02985-252">cdm_workcalendartimeinterval (egyéni mezőtámogatáshoz nem engedélyezett)</span><span class="sxs-lookup"><span data-stu-id="02985-252">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="02985-253">Dolgozói bankszámla</span><span class="sxs-lookup"><span data-stu-id="02985-253">Worker Bank Account</span></span> | <span data-ttu-id="02985-254">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="02985-254">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-tables"></a><span data-ttu-id="02985-255">Dolgozóbeállítási táblák</span><span class="sxs-lookup"><span data-stu-id="02985-255">Worker setup tables</span></span>

| <span data-ttu-id="02985-256">Név</span><span class="sxs-lookup"><span data-stu-id="02985-256">Name</span></span> | <span data-ttu-id="02985-257">Tábla</span><span class="sxs-lookup"><span data-stu-id="02985-257">Table</span></span> |
| --- | --- |
| <span data-ttu-id="02985-258">Veteránállapot</span><span class="sxs-lookup"><span data-stu-id="02985-258">Veteran Status</span></span> | <span data-ttu-id="02985-259">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="02985-259">cdm_veteranstatus</span></span> |
| <span data-ttu-id="02985-260">Etnikum</span><span class="sxs-lookup"><span data-stu-id="02985-260">Ethnic Origin</span></span> | <span data-ttu-id="02985-261">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="02985-261">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="02985-262">Okkód</span><span class="sxs-lookup"><span data-stu-id="02985-262">Reason Code</span></span> | <span data-ttu-id="02985-263">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="02985-263">cdm_reasoncode</span></span> |
| <span data-ttu-id="02985-264">Személyazonosító-kibocsátó hivatal</span><span class="sxs-lookup"><span data-stu-id="02985-264">Person Identification Issuing Agency</span></span> | <span data-ttu-id="02985-265">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="02985-265">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-tables"></a><span data-ttu-id="02985-266">Kompetenciatáblák</span><span class="sxs-lookup"><span data-stu-id="02985-266">Competency tables</span></span>

| <span data-ttu-id="02985-267">Név</span><span class="sxs-lookup"><span data-stu-id="02985-267">Name</span></span> | <span data-ttu-id="02985-268">Tábla</span><span class="sxs-lookup"><span data-stu-id="02985-268">Table</span></span> |
| --- | --- |
| <span data-ttu-id="02985-269">Szakértelemtípus</span><span class="sxs-lookup"><span data-stu-id="02985-269">Skill Type</span></span> | <span data-ttu-id="02985-270">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="02985-270">cdm_skilltype</span></span> |

## <a name="table-relationship-models"></a><span data-ttu-id="02985-271">Táblakapcsolati modellek</span><span class="sxs-lookup"><span data-stu-id="02985-271">Table relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="02985-272">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="02985-272">Worker</span></span>

![Dolgozó](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="02985-274">Feladat és feladat beosztása</span><span class="sxs-lookup"><span data-stu-id="02985-274">Job and Job Position</span></span>

![Feladat és feladat beosztása](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="02985-276">Előnyök</span><span class="sxs-lookup"><span data-stu-id="02985-276">Benefits</span></span>

![Előnyök](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="02985-278">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="02985-278">Compensation</span></span>

![Kompenzáció](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="02985-280">Kilépés</span><span class="sxs-lookup"><span data-stu-id="02985-280">Leave</span></span>

![Kilépés](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="02985-282">Munkanaptár</span><span class="sxs-lookup"><span data-stu-id="02985-282">Work Calendar</span></span>

![Munkanaptár](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="02985-284">Lásd még</span><span class="sxs-lookup"><span data-stu-id="02985-284">See also</span></span>

[<span data-ttu-id="02985-285">Adatintegrációs technológia kiválasztása</span><span class="sxs-lookup"><span data-stu-id="02985-285">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)<br>
[<span data-ttu-id="02985-286">A Dataverse-integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="02985-286">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)<br>
[<span data-ttu-id="02985-287">Dataverse virtuális táblák konfigurálása</span><span class="sxs-lookup"><span data-stu-id="02985-287">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="02985-288">A Human Resources számára elérhető virtuális táblák – GYIK</span><span class="sxs-lookup"><span data-stu-id="02985-288">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="02985-289">Mi az a Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="02985-289">What is Microsoft Dataverse?</span></span>](/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="02985-290">Terminológia frissítései</span><span class="sxs-lookup"><span data-stu-id="02985-290">Terminology updates</span></span>](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]