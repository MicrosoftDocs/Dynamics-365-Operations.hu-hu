---
title: Common Data Service-entitások
description: A Microsoft Dynamics 365 Human Resources a Common Data Service használatával biztosítja a bővíthetőségi és az integrációs eseteket.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6879a45dd1fcc1ba718747aaaf0d7936c2eac49f
ms.sourcegitcommit: 3cad15f8ecc257d3a45c1bc1fada7c094ff4bcec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087346"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="e2081-103">Common Data Service-entitások</span><span class="sxs-lookup"><span data-stu-id="e2081-103">Common Data Service entities</span></span>

<span data-ttu-id="e2081-104">A Microsoft Dynamics 365 Human Resources a Common Data Service használatával biztosítja a bővíthetőségi és az integrációs eseteket.</span><span class="sxs-lookup"><span data-stu-id="e2081-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="e2081-105">A Common Data Service eltávolításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Mi a Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="e2081-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="e2081-106">A Human Resources rendszerhez a következő erőforrások állnak rendelkezésére a Common Data Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="e2081-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="e2081-107">Juttatási egységek</span><span class="sxs-lookup"><span data-stu-id="e2081-107">Benefit entities</span></span>

| <span data-ttu-id="e2081-108">Név</span><span class="sxs-lookup"><span data-stu-id="e2081-108">Name</span></span> | <span data-ttu-id="e2081-109">Entitás</span><span class="sxs-lookup"><span data-stu-id="e2081-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e2081-110">Juttatás számítási gyakorisága</span><span class="sxs-lookup"><span data-stu-id="e2081-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="e2081-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="e2081-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="e2081-112">Fizetési időszak juttatásszámítási gyakorisága</span><span class="sxs-lookup"><span data-stu-id="e2081-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="e2081-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="e2081-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="e2081-114">Juttatásszámítás gyakorisága</span><span class="sxs-lookup"><span data-stu-id="e2081-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="e2081-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="e2081-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="e2081-116">Juttatás számítási mértékének részletei</span><span class="sxs-lookup"><span data-stu-id="e2081-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="e2081-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="e2081-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="e2081-118">Juttatási lehetőség</span><span class="sxs-lookup"><span data-stu-id="e2081-118">Benefit Option</span></span> | <span data-ttu-id="e2081-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="e2081-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="e2081-120">Juttatási terv</span><span class="sxs-lookup"><span data-stu-id="e2081-120">Benefit Plan</span></span> | <span data-ttu-id="e2081-121">cdm_benefitplan (egyéni mezőtámogatáshoz nem engedélyezett)</span><span class="sxs-lookup"><span data-stu-id="e2081-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="e2081-122">Juttatás típusa</span><span class="sxs-lookup"><span data-stu-id="e2081-122">Benefit Type</span></span> | <span data-ttu-id="e2081-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="e2081-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="e2081-124">Üzleti folyamat feladatentitásai</span><span class="sxs-lookup"><span data-stu-id="e2081-124">Business process tasks entities</span></span>

| <span data-ttu-id="e2081-125">Név</span><span class="sxs-lookup"><span data-stu-id="e2081-125">Name</span></span> | <span data-ttu-id="e2081-126">Entitás</span><span class="sxs-lookup"><span data-stu-id="e2081-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e2081-127">Üzletifolyamat-naptár</span><span class="sxs-lookup"><span data-stu-id="e2081-127">Business Process Calendar</span></span> | <span data-ttu-id="e2081-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="e2081-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="e2081-129">Üzletifolyamat-csoport hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="e2081-129">Business Process Group Assignment</span></span> | <span data-ttu-id="e2081-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="e2081-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="e2081-131">Üzletifolyamat-tár feladatcsoportja</span><span class="sxs-lookup"><span data-stu-id="e2081-131">Business Process Library Task Group</span></span> | <span data-ttu-id="e2081-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="e2081-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="e2081-133">Üzleti folyamat szakasza</span><span class="sxs-lookup"><span data-stu-id="e2081-133">Business Process Stage</span></span> | <span data-ttu-id="e2081-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="e2081-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="e2081-135">Ellenőrzőlista-sablon fejléce</span><span class="sxs-lookup"><span data-stu-id="e2081-135">Checklist Template Header</span></span> | <span data-ttu-id="e2081-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="e2081-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="e2081-137">Ellenőrzőlistasablon-feladat</span><span class="sxs-lookup"><span data-stu-id="e2081-137">Checklist Template Task</span></span> | <span data-ttu-id="e2081-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="e2081-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="e2081-139">Kompenzációs entitások</span><span class="sxs-lookup"><span data-stu-id="e2081-139">Compensation entities</span></span>

| <span data-ttu-id="e2081-140">Név</span><span class="sxs-lookup"><span data-stu-id="e2081-140">Name</span></span> | <span data-ttu-id="e2081-141">Entitás</span><span class="sxs-lookup"><span data-stu-id="e2081-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e2081-142">Fix kompenzációs konstrukció</span><span class="sxs-lookup"><span data-stu-id="e2081-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="e2081-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="e2081-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="e2081-144">Kompenzációs rács</span><span class="sxs-lookup"><span data-stu-id="e2081-144">Compensation Grid</span></span> | <span data-ttu-id="e2081-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="e2081-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="e2081-146">Kompenzációs szint</span><span class="sxs-lookup"><span data-stu-id="e2081-146">Compensation Level</span></span> | <span data-ttu-id="e2081-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="e2081-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="e2081-148">Kompenzáció – fizetés gyakorisága</span><span class="sxs-lookup"><span data-stu-id="e2081-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="e2081-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="e2081-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="e2081-150">Kompenzációs hivatkozási pont beállítása</span><span class="sxs-lookup"><span data-stu-id="e2081-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="e2081-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="e2081-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="e2081-152">Kompenzációs hivatkozási pontok beállítási sora</span><span class="sxs-lookup"><span data-stu-id="e2081-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="e2081-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="e2081-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="e2081-154">Kompenzációs régió</span><span class="sxs-lookup"><span data-stu-id="e2081-154">Compensation Region</span></span> | <span data-ttu-id="e2081-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="e2081-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="e2081-156">Kompenzációs struktúra</span><span class="sxs-lookup"><span data-stu-id="e2081-156">Compensation Structure</span></span> | <span data-ttu-id="e2081-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="e2081-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="e2081-158">Változó kompenzációs konstrukció</span><span class="sxs-lookup"><span data-stu-id="e2081-158">Compensation Variable Plan</span></span> | <span data-ttu-id="e2081-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="e2081-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="e2081-160">Változó kompenzációs konstrukció szintje</span><span class="sxs-lookup"><span data-stu-id="e2081-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="e2081-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="e2081-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="e2081-162">Változó kompenzációs konstrukció típusa</span><span class="sxs-lookup"><span data-stu-id="e2081-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="e2081-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="e2081-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="e2081-164">Fix kompenzációs esemény</span><span class="sxs-lookup"><span data-stu-id="e2081-164">Fixed Compensation Event</span></span> | <span data-ttu-id="e2081-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="e2081-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="e2081-166">Átruházási szabály</span><span class="sxs-lookup"><span data-stu-id="e2081-166">Vesting Rule</span></span> | <span data-ttu-id="e2081-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="e2081-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="e2081-168">Dolgozói fix kompenzáció</span><span class="sxs-lookup"><span data-stu-id="e2081-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="e2081-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="e2081-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="e2081-170">Szervezeti entitások</span><span class="sxs-lookup"><span data-stu-id="e2081-170">Organization entities</span></span>

| <span data-ttu-id="e2081-171">Név</span><span class="sxs-lookup"><span data-stu-id="e2081-171">Name</span></span> | <span data-ttu-id="e2081-172">Entitás</span><span class="sxs-lookup"><span data-stu-id="e2081-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e2081-173">Részleg </span><span class="sxs-lookup"><span data-stu-id="e2081-173">Department</span></span> | <span data-ttu-id="e2081-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="e2081-174">cdm_department</span></span> |
| <span data-ttu-id="e2081-175">Foglalkoztatás</span><span class="sxs-lookup"><span data-stu-id="e2081-175">Employment</span></span> | <span data-ttu-id="e2081-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="e2081-176">cdm_employment</span></span> |
| <span data-ttu-id="e2081-177">Cég</span><span class="sxs-lookup"><span data-stu-id="e2081-177">Company</span></span> | <span data-ttu-id="e2081-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="e2081-178">cdm_company</span></span> |
| <span data-ttu-id="e2081-179">Állás</span><span class="sxs-lookup"><span data-stu-id="e2081-179">Job</span></span> | <span data-ttu-id="e2081-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="e2081-180">cdm_job</span></span> |
| <span data-ttu-id="e2081-181">Beosztás funkciója</span><span class="sxs-lookup"><span data-stu-id="e2081-181">Job Function</span></span> | <span data-ttu-id="e2081-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="e2081-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="e2081-183">Beosztás</span><span class="sxs-lookup"><span data-stu-id="e2081-183">Job Position</span></span> | <span data-ttu-id="e2081-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="e2081-184">cdm_jobposition</span></span> |
| <span data-ttu-id="e2081-185">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="e2081-185">Position Type</span></span> | <span data-ttu-id="e2081-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="e2081-186">cdm_positiontype</span></span> |
| <span data-ttu-id="e2081-187">Beosztáshoz rendelt dolgozó</span><span class="sxs-lookup"><span data-stu-id="e2081-187">Position Worker Assignment</span></span> | <span data-ttu-id="e2081-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="e2081-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="e2081-189">Feladattípus</span><span class="sxs-lookup"><span data-stu-id="e2081-189">Job Type</span></span> | <span data-ttu-id="e2081-190">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="e2081-190">cdm_jobtype</span></span> |
| <span data-ttu-id="e2081-191">Nyelv</span><span class="sxs-lookup"><span data-stu-id="e2081-191">Language</span></span> | <span data-ttu-id="e2081-192">cdm_language</span><span class="sxs-lookup"><span data-stu-id="e2081-192">cdm_language</span></span> |

## <a name="leave-and-absence-entities"></a><span data-ttu-id="e2081-193">Szabadság- és távollétentitások</span><span class="sxs-lookup"><span data-stu-id="e2081-193">Leave and absence entities</span></span>

| <span data-ttu-id="e2081-194">Név</span><span class="sxs-lookup"><span data-stu-id="e2081-194">Name</span></span> | <span data-ttu-id="e2081-195">Entitás</span><span class="sxs-lookup"><span data-stu-id="e2081-195">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e2081-196">Szabadság banki tranzakciója</span><span class="sxs-lookup"><span data-stu-id="e2081-196">Leave Bank Transaction</span></span> | <span data-ttu-id="e2081-197">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="e2081-197">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="e2081-198">Szabadság regisztrációja</span><span class="sxs-lookup"><span data-stu-id="e2081-198">Leave Enrollment</span></span> | <span data-ttu-id="e2081-199">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="e2081-199">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="e2081-200">Szabadságterv</span><span class="sxs-lookup"><span data-stu-id="e2081-200">Leave Plan</span></span> | <span data-ttu-id="e2081-201">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="e2081-201">cdm_leaveplan</span></span> |
| <span data-ttu-id="e2081-202">Szabadságkérelem</span><span class="sxs-lookup"><span data-stu-id="e2081-202">Leave Request</span></span> | <span data-ttu-id="e2081-203">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="e2081-203">cdm_leaverequest</span></span> |
| <span data-ttu-id="e2081-204">Szabadságkérelem részletes adatai</span><span class="sxs-lookup"><span data-stu-id="e2081-204">Leave Request Detail</span></span> | <span data-ttu-id="e2081-205">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="e2081-205">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="e2081-206">Szabadság típusa</span><span class="sxs-lookup"><span data-stu-id="e2081-206">Leave Type</span></span> | <span data-ttu-id="e2081-207">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="e2081-207">cdm_leavetype</span></span> |
| <span data-ttu-id="e2081-208">Szabadságtípus okkódja</span><span class="sxs-lookup"><span data-stu-id="e2081-208">Leave Type Reason Code</span></span> | <span data-ttu-id="e2081-209">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="e2081-209">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="e2081-210">Bérlistaentitás</span><span class="sxs-lookup"><span data-stu-id="e2081-210">Payroll entities</span></span>

| <span data-ttu-id="e2081-211">Név</span><span class="sxs-lookup"><span data-stu-id="e2081-211">Name</span></span> | <span data-ttu-id="e2081-212">Entitás</span><span class="sxs-lookup"><span data-stu-id="e2081-212">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e2081-213">Fizetési ciklus</span><span class="sxs-lookup"><span data-stu-id="e2081-213">Pay Cycle</span></span> | <span data-ttu-id="e2081-214">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="e2081-214">cdm_paycycle</span></span> |
| <span data-ttu-id="e2081-215">Fizetési időszak</span><span class="sxs-lookup"><span data-stu-id="e2081-215">Pay Period</span></span> | <span data-ttu-id="e2081-216">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="e2081-216">cdm_payperiod</span></span> |
| <span data-ttu-id="e2081-217">Bérlista bevételkódja</span><span class="sxs-lookup"><span data-stu-id="e2081-217">Payroll Earning Code</span></span> | <span data-ttu-id="e2081-218">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="e2081-218">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="e2081-219">Bankszámla kifizetései</span><span class="sxs-lookup"><span data-stu-id="e2081-219">Bank Account Disbursement</span></span> | <span data-ttu-id="e2081-220">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="e2081-220">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="e2081-221">Adórégió</span><span class="sxs-lookup"><span data-stu-id="e2081-221">Tax Region</span></span> | <span data-ttu-id="e2081-222">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="e2081-222">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="e2081-223">Dolgozói entitások</span><span class="sxs-lookup"><span data-stu-id="e2081-223">Worker entities</span></span>

| <span data-ttu-id="e2081-224">Név</span><span class="sxs-lookup"><span data-stu-id="e2081-224">Name</span></span> | <span data-ttu-id="e2081-225">Entitás</span><span class="sxs-lookup"><span data-stu-id="e2081-225">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e2081-226">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="e2081-226">Worker</span></span> | <span data-ttu-id="e2081-227">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="e2081-227">cdm_worker</span></span> |
| <span data-ttu-id="e2081-228">Dolgozó címe</span><span class="sxs-lookup"><span data-stu-id="e2081-228">Worker Address</span></span> | <span data-ttu-id="e2081-229">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="e2081-229">cdm_workeraddress</span></span> |
| <span data-ttu-id="e2081-230">Dolgozói személyes adat</span><span class="sxs-lookup"><span data-stu-id="e2081-230">Worker Personal Detail</span></span> | <span data-ttu-id="e2081-231">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="e2081-231">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="e2081-232">Dolgozó személyazonosító száma</span><span class="sxs-lookup"><span data-stu-id="e2081-232">Worker Person Identification Number</span></span> | <span data-ttu-id="e2081-233">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="e2081-233">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="e2081-234">Dolgozó személyazonosító típusa</span><span class="sxs-lookup"><span data-stu-id="e2081-234">Worker Person Identification Type</span></span> | <span data-ttu-id="e2081-235">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="e2081-235">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="e2081-236">Munkanaptár</span><span class="sxs-lookup"><span data-stu-id="e2081-236">Work Calendar</span></span> | <span data-ttu-id="e2081-237">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="e2081-237">cdm_workcalendar</span></span> |
| <span data-ttu-id="e2081-238">Munkanaptár napja</span><span class="sxs-lookup"><span data-stu-id="e2081-238">Work Calendar Day</span></span> | <span data-ttu-id="e2081-239">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="e2081-239">cdm_workcalendarday</span></span> |
| <span data-ttu-id="e2081-240">Munkanaptári ünnep</span><span class="sxs-lookup"><span data-stu-id="e2081-240">Work Calendar Holiday</span></span> |<span data-ttu-id="e2081-241">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="e2081-241">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="e2081-242">Munkanaptár ünnepsora</span><span class="sxs-lookup"><span data-stu-id="e2081-242">Work Calendar Holiday Line</span></span> | <span data-ttu-id="e2081-243">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="e2081-243">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="e2081-244">Munkanaptár időintervalluma</span><span class="sxs-lookup"><span data-stu-id="e2081-244">Work Calendar Time Interval</span></span> | <span data-ttu-id="e2081-245">cdm_workcalendartimeinterval (egyéni mezőtámogatáshoz nem engedélyezett)</span><span class="sxs-lookup"><span data-stu-id="e2081-245">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="e2081-246">Dolgozói bankszámla</span><span class="sxs-lookup"><span data-stu-id="e2081-246">Worker Bank Account</span></span> | <span data-ttu-id="e2081-247">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="e2081-247">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="e2081-248">Dolgozó beállítási entitásai</span><span class="sxs-lookup"><span data-stu-id="e2081-248">Worker setup entities</span></span>

| <span data-ttu-id="e2081-249">Név</span><span class="sxs-lookup"><span data-stu-id="e2081-249">Name</span></span> | <span data-ttu-id="e2081-250">Entitás</span><span class="sxs-lookup"><span data-stu-id="e2081-250">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e2081-251">Veteránállapot</span><span class="sxs-lookup"><span data-stu-id="e2081-251">Veteran Status</span></span> | <span data-ttu-id="e2081-252">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="e2081-252">cdm_veteranstatus</span></span> |
| <span data-ttu-id="e2081-253">Etnikum</span><span class="sxs-lookup"><span data-stu-id="e2081-253">Ethnic Origin</span></span> | <span data-ttu-id="e2081-254">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="e2081-254">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="e2081-255">Okkód</span><span class="sxs-lookup"><span data-stu-id="e2081-255">Reason Code</span></span> | <span data-ttu-id="e2081-256">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="e2081-256">cdm_reasoncode</span></span> |
| <span data-ttu-id="e2081-257">Személyazonosító kiállító hivatala</span><span class="sxs-lookup"><span data-stu-id="e2081-257">Person Identification Issuing Agency</span></span> | <span data-ttu-id="e2081-258">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="e2081-258">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="e2081-259">Kompetenciaentitások</span><span class="sxs-lookup"><span data-stu-id="e2081-259">Competency entities</span></span>

| <span data-ttu-id="e2081-260">Név</span><span class="sxs-lookup"><span data-stu-id="e2081-260">Name</span></span> | <span data-ttu-id="e2081-261">Entitás</span><span class="sxs-lookup"><span data-stu-id="e2081-261">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="e2081-262">Szakértelemtípus</span><span class="sxs-lookup"><span data-stu-id="e2081-262">Skill Type</span></span> | <span data-ttu-id="e2081-263">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="e2081-263">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="e2081-264">Entitáskapcsolati modellek</span><span class="sxs-lookup"><span data-stu-id="e2081-264">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="e2081-265">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="e2081-265">Worker</span></span>

![Dolgozó](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="e2081-267">Feladat és feladat beosztása</span><span class="sxs-lookup"><span data-stu-id="e2081-267">Job and Job Position</span></span>

![Feladat és feladat beosztása](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="e2081-269">Előnyök</span><span class="sxs-lookup"><span data-stu-id="e2081-269">Benefits</span></span>

![Előnyök](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="e2081-271">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="e2081-271">Compensation</span></span>

![Kompenzáció](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="e2081-273">Kilépés</span><span class="sxs-lookup"><span data-stu-id="e2081-273">Leave</span></span>

![Kilépés](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="e2081-275">Munkanaptár</span><span class="sxs-lookup"><span data-stu-id="e2081-275">Work Calendar</span></span>

![Munkanaptár](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="e2081-277">Lásd még</span><span class="sxs-lookup"><span data-stu-id="e2081-277">See also</span></span>

[<span data-ttu-id="e2081-278">Válasszon ki egy adatintegrációs technológiát</span><span class="sxs-lookup"><span data-stu-id="e2081-278">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="e2081-279">A Common Data Service-integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e2081-279">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)