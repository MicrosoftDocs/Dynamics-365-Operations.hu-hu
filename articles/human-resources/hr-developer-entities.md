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
ms.openlocfilehash: c8e0288da16829c04a9b97c0a52caa8bd27cddf8
ms.sourcegitcommit: fde8045ea49d0cf26d5e7ac5a0da5c0d3d69d5bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/26/2020
ms.locfileid: "3166498"
---
# <a name="common-data-service-entities"></a><span data-ttu-id="a2e20-103">Common Data Service-entitások</span><span class="sxs-lookup"><span data-stu-id="a2e20-103">Common Data Service entities</span></span>

<span data-ttu-id="a2e20-104">A Microsoft Dynamics 365 Human Resources a Common Data Service használatával biztosítja a bővíthetőségi és az integrációs eseteket.</span><span class="sxs-lookup"><span data-stu-id="a2e20-104">Microsoft Dynamics 365 Human Resources uses Common Data Service to enable extensibility and integration scenarios.</span></span>

<span data-ttu-id="a2e20-105">A Common Data Service eltávolításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Mi a Common Data Service?](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="a2e20-105">For more information about Common Data Service, see [What is Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span>

<span data-ttu-id="a2e20-106">A Human Resources rendszerhez a következő erőforrások állnak rendelkezésére a Common Data Service szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="a2e20-106">The following Human Resources entities are available in Common Data Service.</span></span>

## <a name="benefit-entities"></a><span data-ttu-id="a2e20-107">Juttatási egységek</span><span class="sxs-lookup"><span data-stu-id="a2e20-107">Benefit entities</span></span>

| <span data-ttu-id="a2e20-108">Név</span><span class="sxs-lookup"><span data-stu-id="a2e20-108">Name</span></span> | <span data-ttu-id="a2e20-109">Entitás</span><span class="sxs-lookup"><span data-stu-id="a2e20-109">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="a2e20-110">Juttatás számítási gyakorisága</span><span class="sxs-lookup"><span data-stu-id="a2e20-110">Benefit Calculation Frequency</span></span> | <span data-ttu-id="a2e20-111">cdm_benefitcalculationfrequency</span><span class="sxs-lookup"><span data-stu-id="a2e20-111">cdm_benefitcalculationfrequency</span></span> |
| <span data-ttu-id="a2e20-112">Fizetési időszak juttatásszámítási gyakorisága</span><span class="sxs-lookup"><span data-stu-id="a2e20-112">Benefit Calculation Frequency Pay Period</span></span> | <span data-ttu-id="a2e20-113">cdm_benefitcalculationfrequencypayperiod</span><span class="sxs-lookup"><span data-stu-id="a2e20-113">cdm_benefitcalculationfrequencypayperiod</span></span> |
| <span data-ttu-id="a2e20-114">Juttatásszámítás gyakorisága</span><span class="sxs-lookup"><span data-stu-id="a2e20-114">Benefit Calculation Rate</span></span> | <span data-ttu-id="a2e20-115">cdm_benefitcalculationrate</span><span class="sxs-lookup"><span data-stu-id="a2e20-115">cdm_benefitcalculationrate</span></span> |
| <span data-ttu-id="a2e20-116">Juttatás számítási mértékének részletei</span><span class="sxs-lookup"><span data-stu-id="a2e20-116">Benefit Calculation Rate Detail</span></span> | <span data-ttu-id="a2e20-117">cdm_benefitcalculationratedetail</span><span class="sxs-lookup"><span data-stu-id="a2e20-117">cdm_benefitcalculationratedetail</span></span> |
| <span data-ttu-id="a2e20-118">Juttatási lehetőség</span><span class="sxs-lookup"><span data-stu-id="a2e20-118">Benefit Option</span></span> | <span data-ttu-id="a2e20-119">cdm_benefitoption</span><span class="sxs-lookup"><span data-stu-id="a2e20-119">cdm_benefitoption</span></span> |
| <span data-ttu-id="a2e20-120">Juttatási terv</span><span class="sxs-lookup"><span data-stu-id="a2e20-120">Benefit Plan</span></span> | <span data-ttu-id="a2e20-121">cdm_benefitplan (egyéni mezőtámogatáshoz nem engedélyezett)</span><span class="sxs-lookup"><span data-stu-id="a2e20-121">cdm_benefitplan (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="a2e20-122">Juttatás típusa</span><span class="sxs-lookup"><span data-stu-id="a2e20-122">Benefit Type</span></span> | <span data-ttu-id="a2e20-123">cdm_benefittype</span><span class="sxs-lookup"><span data-stu-id="a2e20-123">cdm_benefittype</span></span> |

## <a name="business-process-tasks-entities"></a><span data-ttu-id="a2e20-124">Üzleti folyamat feladatentitásai</span><span class="sxs-lookup"><span data-stu-id="a2e20-124">Business process tasks entities</span></span>

| <span data-ttu-id="a2e20-125">Név</span><span class="sxs-lookup"><span data-stu-id="a2e20-125">Name</span></span> | <span data-ttu-id="a2e20-126">Entitás</span><span class="sxs-lookup"><span data-stu-id="a2e20-126">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="a2e20-127">Üzletifolyamat-naptár</span><span class="sxs-lookup"><span data-stu-id="a2e20-127">Business Process Calendar</span></span> | <span data-ttu-id="a2e20-128">cdm_businessprocesscalendar</span><span class="sxs-lookup"><span data-stu-id="a2e20-128">cdm_businessprocesscalendar</span></span> |
| <span data-ttu-id="a2e20-129">Üzletifolyamat-csoport hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="a2e20-129">Business Process Group Assignment</span></span> | <span data-ttu-id="a2e20-130">cdm_businessprocessgroupassignment</span><span class="sxs-lookup"><span data-stu-id="a2e20-130">cdm_businessprocessgroupassignment</span></span> |
| <span data-ttu-id="a2e20-131">Üzletifolyamat-tár feladatcsoportja</span><span class="sxs-lookup"><span data-stu-id="a2e20-131">Business Process Library Task Group</span></span> | <span data-ttu-id="a2e20-132">cdm_businessprocesslibrarytaskgroup</span><span class="sxs-lookup"><span data-stu-id="a2e20-132">cdm_businessprocesslibrarytaskgroup</span></span> |
| <span data-ttu-id="a2e20-133">Üzleti folyamat szakasza</span><span class="sxs-lookup"><span data-stu-id="a2e20-133">Business Process Stage</span></span> | <span data-ttu-id="a2e20-134">cdm_businessprocessstage</span><span class="sxs-lookup"><span data-stu-id="a2e20-134">cdm_businessprocessstage</span></span> |
| <span data-ttu-id="a2e20-135">Ellenőrzőlista-sablon fejléce</span><span class="sxs-lookup"><span data-stu-id="a2e20-135">Checklist Template Header</span></span> | <span data-ttu-id="a2e20-136">cdm_businessprocesstemplateheader</span><span class="sxs-lookup"><span data-stu-id="a2e20-136">cdm_businessprocesstemplateheader</span></span> |
| <span data-ttu-id="a2e20-137">Ellenőrzőlistasablon-feladat</span><span class="sxs-lookup"><span data-stu-id="a2e20-137">Checklist Template Task</span></span> | <span data-ttu-id="a2e20-138">cdm_businessprocesstemplatetask</span><span class="sxs-lookup"><span data-stu-id="a2e20-138">cdm_businessprocesstemplatetask</span></span> |

## <a name="compensation-entities"></a><span data-ttu-id="a2e20-139">Kompenzációs entitások</span><span class="sxs-lookup"><span data-stu-id="a2e20-139">Compensation entities</span></span>

| <span data-ttu-id="a2e20-140">Név</span><span class="sxs-lookup"><span data-stu-id="a2e20-140">Name</span></span> | <span data-ttu-id="a2e20-141">Entitás</span><span class="sxs-lookup"><span data-stu-id="a2e20-141">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="a2e20-142">Fix kompenzációs konstrukció</span><span class="sxs-lookup"><span data-stu-id="a2e20-142">Compensation Fixed Plan</span></span> | <span data-ttu-id="a2e20-143">cdm_compensationfixedplan</span><span class="sxs-lookup"><span data-stu-id="a2e20-143">cdm_compensationfixedplan</span></span> |
| <span data-ttu-id="a2e20-144">Kompenzációs rács</span><span class="sxs-lookup"><span data-stu-id="a2e20-144">Compensation Grid</span></span> | <span data-ttu-id="a2e20-145">cdm_compensationgrid</span><span class="sxs-lookup"><span data-stu-id="a2e20-145">cdm_compensationgrid</span></span> |
| <span data-ttu-id="a2e20-146">Kompenzációs szint</span><span class="sxs-lookup"><span data-stu-id="a2e20-146">Compensation Level</span></span> | <span data-ttu-id="a2e20-147">cdm_compensationlevel</span><span class="sxs-lookup"><span data-stu-id="a2e20-147">cdm_compensationlevel</span></span> |
| <span data-ttu-id="a2e20-148">Kompenzáció – fizetés gyakorisága</span><span class="sxs-lookup"><span data-stu-id="a2e20-148">Compensation Pay Frequency</span></span> | <span data-ttu-id="a2e20-149">cdm_compensationpayfrequency</span><span class="sxs-lookup"><span data-stu-id="a2e20-149">cdm_compensationpayfrequency</span></span> |
| <span data-ttu-id="a2e20-150">Kompenzációs hivatkozási pont beállítása</span><span class="sxs-lookup"><span data-stu-id="a2e20-150">Compensation Reference Point Setup</span></span> | <span data-ttu-id="a2e20-151">cdm_compensationreferencepointsetup</span><span class="sxs-lookup"><span data-stu-id="a2e20-151">cdm_compensationreferencepointsetup</span></span> |
| <span data-ttu-id="a2e20-152">Kompenzációs hivatkozási pontok beállítási sora</span><span class="sxs-lookup"><span data-stu-id="a2e20-152">Compensation Reference Point Setup Line</span></span> | <span data-ttu-id="a2e20-153">cdm_compensationreferencepointsetupline</span><span class="sxs-lookup"><span data-stu-id="a2e20-153">cdm_compensationreferencepointsetupline</span></span> |
| <span data-ttu-id="a2e20-154">Kompenzációs régió</span><span class="sxs-lookup"><span data-stu-id="a2e20-154">Compensation Region</span></span> | <span data-ttu-id="a2e20-155">cdm_compensationregion</span><span class="sxs-lookup"><span data-stu-id="a2e20-155">cdm_compensationregion</span></span> |
| <span data-ttu-id="a2e20-156">Kompenzációs struktúra</span><span class="sxs-lookup"><span data-stu-id="a2e20-156">Compensation Structure</span></span> | <span data-ttu-id="a2e20-157">cdm_compensationstructure</span><span class="sxs-lookup"><span data-stu-id="a2e20-157">cdm_compensationstructure</span></span> |
| <span data-ttu-id="a2e20-158">Változó kompenzációs konstrukció</span><span class="sxs-lookup"><span data-stu-id="a2e20-158">Compensation Variable Plan</span></span> | <span data-ttu-id="a2e20-159">cdm_compensationvariableplan</span><span class="sxs-lookup"><span data-stu-id="a2e20-159">cdm_compensationvariableplan</span></span> |
| <span data-ttu-id="a2e20-160">Változó kompenzációs konstrukció szintje</span><span class="sxs-lookup"><span data-stu-id="a2e20-160">Compensation Variable Plan Level</span></span> | <span data-ttu-id="a2e20-161">cdm_compensationvariableplanlevel</span><span class="sxs-lookup"><span data-stu-id="a2e20-161">cdm_compensationvariableplanlevel</span></span> |
| <span data-ttu-id="a2e20-162">Változó kompenzációs konstrukció típusa</span><span class="sxs-lookup"><span data-stu-id="a2e20-162">Compensation Variable Plan Type</span></span> | <span data-ttu-id="a2e20-163">cdm_compensationvariableplantype</span><span class="sxs-lookup"><span data-stu-id="a2e20-163">cdm_compensationvariableplantype</span></span> |
| <span data-ttu-id="a2e20-164">Fix kompenzációs esemény</span><span class="sxs-lookup"><span data-stu-id="a2e20-164">Fixed Compensation Event</span></span> | <span data-ttu-id="a2e20-165">cdm_fixedcompensationevent</span><span class="sxs-lookup"><span data-stu-id="a2e20-165">cdm_fixedcompensationevent</span></span> |
| <span data-ttu-id="a2e20-166">Átruházási szabály</span><span class="sxs-lookup"><span data-stu-id="a2e20-166">Vesting Rule</span></span> | <span data-ttu-id="a2e20-167">cdm_vestingrule</span><span class="sxs-lookup"><span data-stu-id="a2e20-167">cdm_vestingrule</span></span> |
| <span data-ttu-id="a2e20-168">Dolgozói fix kompenzáció</span><span class="sxs-lookup"><span data-stu-id="a2e20-168">Worker Fixed Compensation</span></span> | <span data-ttu-id="a2e20-169">cdm_workerfixedcompensation</span><span class="sxs-lookup"><span data-stu-id="a2e20-169">cdm_workerfixedcompensation</span></span> |

## <a name="organization-entities"></a><span data-ttu-id="a2e20-170">Szervezeti entitások</span><span class="sxs-lookup"><span data-stu-id="a2e20-170">Organization entities</span></span>

| <span data-ttu-id="a2e20-171">Név</span><span class="sxs-lookup"><span data-stu-id="a2e20-171">Name</span></span> | <span data-ttu-id="a2e20-172">Entitás</span><span class="sxs-lookup"><span data-stu-id="a2e20-172">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="a2e20-173">Részleg </span><span class="sxs-lookup"><span data-stu-id="a2e20-173">Department</span></span> | <span data-ttu-id="a2e20-174">cdm_department</span><span class="sxs-lookup"><span data-stu-id="a2e20-174">cdm_department</span></span> |
| <span data-ttu-id="a2e20-175">Foglalkoztatás</span><span class="sxs-lookup"><span data-stu-id="a2e20-175">Employment</span></span> | <span data-ttu-id="a2e20-176">cdm_employment</span><span class="sxs-lookup"><span data-stu-id="a2e20-176">cdm_employment</span></span> |
| <span data-ttu-id="a2e20-177">Cég</span><span class="sxs-lookup"><span data-stu-id="a2e20-177">Company</span></span> | <span data-ttu-id="a2e20-178">cdm_company</span><span class="sxs-lookup"><span data-stu-id="a2e20-178">cdm_company</span></span> |
| <span data-ttu-id="a2e20-179">Állás</span><span class="sxs-lookup"><span data-stu-id="a2e20-179">Job</span></span> | <span data-ttu-id="a2e20-180">cdm_job</span><span class="sxs-lookup"><span data-stu-id="a2e20-180">cdm_job</span></span> |
| <span data-ttu-id="a2e20-181">Beosztás funkciója</span><span class="sxs-lookup"><span data-stu-id="a2e20-181">Job Function</span></span> | <span data-ttu-id="a2e20-182">cdm_jobfunction</span><span class="sxs-lookup"><span data-stu-id="a2e20-182">cdm_jobfunction</span></span> |
| <span data-ttu-id="a2e20-183">Beosztás</span><span class="sxs-lookup"><span data-stu-id="a2e20-183">Job Position</span></span> | <span data-ttu-id="a2e20-184">cdm_jobposition</span><span class="sxs-lookup"><span data-stu-id="a2e20-184">cdm_jobposition</span></span> |
| <span data-ttu-id="a2e20-185">Beosztás típusa</span><span class="sxs-lookup"><span data-stu-id="a2e20-185">Position Type</span></span> | <span data-ttu-id="a2e20-186">cdm_positiontype</span><span class="sxs-lookup"><span data-stu-id="a2e20-186">cdm_positiontype</span></span> |
| <span data-ttu-id="a2e20-187">Beosztáshoz rendelt dolgozó</span><span class="sxs-lookup"><span data-stu-id="a2e20-187">Position Worker Assignment</span></span> | <span data-ttu-id="a2e20-188">cdm_positionworkerassignmentmap</span><span class="sxs-lookup"><span data-stu-id="a2e20-188">cdm_positionworkerassignmentmap</span></span> |
| <span data-ttu-id="a2e20-189">Beosztásdimenzió</span><span class="sxs-lookup"><span data-stu-id="a2e20-189">Job Position Dimension</span></span> | <span data-ttu-id="a2e20-190">cdm_jobpositiondimension</span><span class="sxs-lookup"><span data-stu-id="a2e20-190">cdm_jobpositiondimension</span></span>|
| <span data-ttu-id="a2e20-191">Állás típusa</span><span class="sxs-lookup"><span data-stu-id="a2e20-191">Job Type</span></span> | <span data-ttu-id="a2e20-192">cdm_jobtype</span><span class="sxs-lookup"><span data-stu-id="a2e20-192">cdm_jobtype</span></span> |
| <span data-ttu-id="a2e20-193">Nyelv</span><span class="sxs-lookup"><span data-stu-id="a2e20-193">Language</span></span> | <span data-ttu-id="a2e20-194">cdm_language</span><span class="sxs-lookup"><span data-stu-id="a2e20-194">cdm_language</span></span> |
| <span data-ttu-id="a2e20-195">Megszólítás</span><span class="sxs-lookup"><span data-stu-id="a2e20-195">Title</span></span> | <span data-ttu-id="a2e20-196">cdm_title</span><span class="sxs-lookup"><span data-stu-id="a2e20-196">cdm_title</span></span> |

> [!NOTE]
> <span data-ttu-id="a2e20-197">A **Beosztás típusa**, **Beosztáshoz rendelt dolgozó** és **Foglalkoztatás** pénzügyi dimenziói egyirányú integrációt biztosítanak a Common Data Service felé.</span><span class="sxs-lookup"><span data-stu-id="a2e20-197">Financial dimensions for **Position Type**, **Position Worker Assignment**, and **Employment** provide one-direction integration to Common Data Service.</span></span> <span data-ttu-id="a2e20-198">A pénzügyi dimenziók frissítései jelenleg nem szinkronizálnak a Common Data Service szolgáltatásból Human Resources alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a2e20-198">Financial dimensions updates currently can't synchronize from Common Data Service to Human Resources.</span></span> 

## <a name="leave-and-absence-entities"></a><span data-ttu-id="a2e20-199">Szabadság- és távollétentitások</span><span class="sxs-lookup"><span data-stu-id="a2e20-199">Leave and absence entities</span></span>

| <span data-ttu-id="a2e20-200">Név</span><span class="sxs-lookup"><span data-stu-id="a2e20-200">Name</span></span> | <span data-ttu-id="a2e20-201">Entitás</span><span class="sxs-lookup"><span data-stu-id="a2e20-201">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="a2e20-202">Szabadsági banki tranzakció</span><span class="sxs-lookup"><span data-stu-id="a2e20-202">Leave Bank Transaction</span></span> | <span data-ttu-id="a2e20-203">cdm_leavebanktransaction</span><span class="sxs-lookup"><span data-stu-id="a2e20-203">cdm_leavebanktransaction</span></span> |
| <span data-ttu-id="a2e20-204">Szabadság regisztrációja</span><span class="sxs-lookup"><span data-stu-id="a2e20-204">Leave Enrollment</span></span> | <span data-ttu-id="a2e20-205">cdm_leaveenrollment</span><span class="sxs-lookup"><span data-stu-id="a2e20-205">cdm_leaveenrollment</span></span> |
| <span data-ttu-id="a2e20-206">Szabadságterv</span><span class="sxs-lookup"><span data-stu-id="a2e20-206">Leave Plan</span></span> | <span data-ttu-id="a2e20-207">cdm_leaveplan</span><span class="sxs-lookup"><span data-stu-id="a2e20-207">cdm_leaveplan</span></span> |
| <span data-ttu-id="a2e20-208">Szabadságkérelem</span><span class="sxs-lookup"><span data-stu-id="a2e20-208">Leave Request</span></span> | <span data-ttu-id="a2e20-209">cdm_leaverequest</span><span class="sxs-lookup"><span data-stu-id="a2e20-209">cdm_leaverequest</span></span> |
| <span data-ttu-id="a2e20-210">Szabadságkérelem részletes adatai</span><span class="sxs-lookup"><span data-stu-id="a2e20-210">Leave Request Detail</span></span> | <span data-ttu-id="a2e20-211">cdm_leaverequestdetail</span><span class="sxs-lookup"><span data-stu-id="a2e20-211">cdm_leaverequestdetail</span></span> |
| <span data-ttu-id="a2e20-212">Szabadság típusa</span><span class="sxs-lookup"><span data-stu-id="a2e20-212">Leave Type</span></span> | <span data-ttu-id="a2e20-213">cdm_leavetype</span><span class="sxs-lookup"><span data-stu-id="a2e20-213">cdm_leavetype</span></span> |
| <span data-ttu-id="a2e20-214">Szabadságtípus okkódja</span><span class="sxs-lookup"><span data-stu-id="a2e20-214">Leave Type Reason Code</span></span> | <span data-ttu-id="a2e20-215">cdm_leavetypereasoncode</span><span class="sxs-lookup"><span data-stu-id="a2e20-215">cdm_leavetypereasoncode</span></span> |

## <a name="payroll-entities"></a><span data-ttu-id="a2e20-216">Bérlistaentitás</span><span class="sxs-lookup"><span data-stu-id="a2e20-216">Payroll entities</span></span>

| <span data-ttu-id="a2e20-217">Név</span><span class="sxs-lookup"><span data-stu-id="a2e20-217">Name</span></span> | <span data-ttu-id="a2e20-218">Entitás</span><span class="sxs-lookup"><span data-stu-id="a2e20-218">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="a2e20-219">Fizetési ciklus</span><span class="sxs-lookup"><span data-stu-id="a2e20-219">Pay Cycle</span></span> | <span data-ttu-id="a2e20-220">cdm_paycycle</span><span class="sxs-lookup"><span data-stu-id="a2e20-220">cdm_paycycle</span></span> |
| <span data-ttu-id="a2e20-221">Fizetési időszak</span><span class="sxs-lookup"><span data-stu-id="a2e20-221">Pay Period</span></span> | <span data-ttu-id="a2e20-222">cdm_payperiod</span><span class="sxs-lookup"><span data-stu-id="a2e20-222">cdm_payperiod</span></span> |
| <span data-ttu-id="a2e20-223">Bérlista bevételkódja</span><span class="sxs-lookup"><span data-stu-id="a2e20-223">Payroll Earning Code</span></span> | <span data-ttu-id="a2e20-224">cdm_payrollearningcode</span><span class="sxs-lookup"><span data-stu-id="a2e20-224">cdm_payrollearningcode</span></span> |
| <span data-ttu-id="a2e20-225">Bankszámla kifizetései</span><span class="sxs-lookup"><span data-stu-id="a2e20-225">Bank Account Disbursement</span></span> | <span data-ttu-id="a2e20-226">cdm_bankaccountdisbursement</span><span class="sxs-lookup"><span data-stu-id="a2e20-226">cdm_bankaccountdisbursement</span></span> |
| <span data-ttu-id="a2e20-227">Adórégió</span><span class="sxs-lookup"><span data-stu-id="a2e20-227">Tax Region</span></span> | <span data-ttu-id="a2e20-228">cdm_taxregion</span><span class="sxs-lookup"><span data-stu-id="a2e20-228">cdm_taxregion</span></span> |

## <a name="worker-entities"></a><span data-ttu-id="a2e20-229">Dolgozói entitások</span><span class="sxs-lookup"><span data-stu-id="a2e20-229">Worker entities</span></span>

| <span data-ttu-id="a2e20-230">Név</span><span class="sxs-lookup"><span data-stu-id="a2e20-230">Name</span></span> | <span data-ttu-id="a2e20-231">Entitás</span><span class="sxs-lookup"><span data-stu-id="a2e20-231">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="a2e20-232">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="a2e20-232">Worker</span></span> | <span data-ttu-id="a2e20-233">cdm_worker</span><span class="sxs-lookup"><span data-stu-id="a2e20-233">cdm_worker</span></span> |
| <span data-ttu-id="a2e20-234">Dolgozó címe</span><span class="sxs-lookup"><span data-stu-id="a2e20-234">Worker Address</span></span> | <span data-ttu-id="a2e20-235">cdm_workeraddress</span><span class="sxs-lookup"><span data-stu-id="a2e20-235">cdm_workeraddress</span></span> |
| <span data-ttu-id="a2e20-236">Dolgozói személyes adat</span><span class="sxs-lookup"><span data-stu-id="a2e20-236">Worker Personal Detail</span></span> | <span data-ttu-id="a2e20-237">cdm_workerpersonaldetail</span><span class="sxs-lookup"><span data-stu-id="a2e20-237">cdm_workerpersonaldetail</span></span> |
| <span data-ttu-id="a2e20-238">Dolgozó személyazonosító száma</span><span class="sxs-lookup"><span data-stu-id="a2e20-238">Worker Person Identification Number</span></span> | <span data-ttu-id="a2e20-239">cdm_workerpersonidentificationnumber</span><span class="sxs-lookup"><span data-stu-id="a2e20-239">cdm_workerpersonidentificationnumber</span></span> |
| <span data-ttu-id="a2e20-240">Dolgozó személyazonosító típusa</span><span class="sxs-lookup"><span data-stu-id="a2e20-240">Worker Person Identification Type</span></span> | <span data-ttu-id="a2e20-241">cdm_workerpersonidentificationtype</span><span class="sxs-lookup"><span data-stu-id="a2e20-241">cdm_workerpersonidentificationtype</span></span> |
| <span data-ttu-id="a2e20-242">Munkanaptár</span><span class="sxs-lookup"><span data-stu-id="a2e20-242">Work Calendar</span></span> | <span data-ttu-id="a2e20-243">cdm_workcalendar</span><span class="sxs-lookup"><span data-stu-id="a2e20-243">cdm_workcalendar</span></span> |
| <span data-ttu-id="a2e20-244">Munkanaptár napja</span><span class="sxs-lookup"><span data-stu-id="a2e20-244">Work Calendar Day</span></span> | <span data-ttu-id="a2e20-245">cdm_workcalendarday</span><span class="sxs-lookup"><span data-stu-id="a2e20-245">cdm_workcalendarday</span></span> |
| <span data-ttu-id="a2e20-246">Munkanaptári ünnep</span><span class="sxs-lookup"><span data-stu-id="a2e20-246">Work Calendar Holiday</span></span> |<span data-ttu-id="a2e20-247">cdm_workcalendarholiday</span><span class="sxs-lookup"><span data-stu-id="a2e20-247">cdm_workcalendarholiday</span></span> |
| <span data-ttu-id="a2e20-248">Munkanaptár ünnepsora</span><span class="sxs-lookup"><span data-stu-id="a2e20-248">Work Calendar Holiday Line</span></span> | <span data-ttu-id="a2e20-249">cdm_workcalendarholidayline</span><span class="sxs-lookup"><span data-stu-id="a2e20-249">cdm_workcalendarholidayline</span></span> |
| <span data-ttu-id="a2e20-250">Munkanaptár időintervalluma</span><span class="sxs-lookup"><span data-stu-id="a2e20-250">Work Calendar Time Interval</span></span> | <span data-ttu-id="a2e20-251">cdm_workcalendartimeinterval (egyéni mezőtámogatáshoz nem engedélyezett)</span><span class="sxs-lookup"><span data-stu-id="a2e20-251">cdm_workcalendartimeinterval (Not enabled for custom field support)</span></span> |
| <span data-ttu-id="a2e20-252">Dolgozói bankszámla</span><span class="sxs-lookup"><span data-stu-id="a2e20-252">Worker Bank Account</span></span> | <span data-ttu-id="a2e20-253">cdm_workerbankaccount</span><span class="sxs-lookup"><span data-stu-id="a2e20-253">cdm_workerbankaccount</span></span> |

## <a name="worker-setup-entities"></a><span data-ttu-id="a2e20-254">Dolgozó beállítási entitásai</span><span class="sxs-lookup"><span data-stu-id="a2e20-254">Worker setup entities</span></span>

| <span data-ttu-id="a2e20-255">Név</span><span class="sxs-lookup"><span data-stu-id="a2e20-255">Name</span></span> | <span data-ttu-id="a2e20-256">Entitás</span><span class="sxs-lookup"><span data-stu-id="a2e20-256">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="a2e20-257">Veteránállapot</span><span class="sxs-lookup"><span data-stu-id="a2e20-257">Veteran Status</span></span> | <span data-ttu-id="a2e20-258">cdm_veteranstatus</span><span class="sxs-lookup"><span data-stu-id="a2e20-258">cdm_veteranstatus</span></span> |
| <span data-ttu-id="a2e20-259">Etnikum</span><span class="sxs-lookup"><span data-stu-id="a2e20-259">Ethnic Origin</span></span> | <span data-ttu-id="a2e20-260">cdm_ethnicorigin</span><span class="sxs-lookup"><span data-stu-id="a2e20-260">cdm_ethnicorigin</span></span> |
| <span data-ttu-id="a2e20-261">Okkód</span><span class="sxs-lookup"><span data-stu-id="a2e20-261">Reason Code</span></span> | <span data-ttu-id="a2e20-262">cdm_reasoncode</span><span class="sxs-lookup"><span data-stu-id="a2e20-262">cdm_reasoncode</span></span> |
| <span data-ttu-id="a2e20-263">Személyazonosító kiállító hivatala</span><span class="sxs-lookup"><span data-stu-id="a2e20-263">Person Identification Issuing Agency</span></span> | <span data-ttu-id="a2e20-264">cdm_personidentificationissuingagency</span><span class="sxs-lookup"><span data-stu-id="a2e20-264">cdm_personidentificationissuingagency</span></span> |

## <a name="competency-entities"></a><span data-ttu-id="a2e20-265">Kompetenciaentitások</span><span class="sxs-lookup"><span data-stu-id="a2e20-265">Competency entities</span></span>

| <span data-ttu-id="a2e20-266">Név</span><span class="sxs-lookup"><span data-stu-id="a2e20-266">Name</span></span> | <span data-ttu-id="a2e20-267">Entitás</span><span class="sxs-lookup"><span data-stu-id="a2e20-267">Entity</span></span> |
| --- | --- |
| <span data-ttu-id="a2e20-268">Szakértelemtípus</span><span class="sxs-lookup"><span data-stu-id="a2e20-268">Skill Type</span></span> | <span data-ttu-id="a2e20-269">cdm_skilltype</span><span class="sxs-lookup"><span data-stu-id="a2e20-269">cdm_skilltype</span></span> |

## <a name="entity-relationship-models"></a><span data-ttu-id="a2e20-270">Entitáskapcsolati modellek</span><span class="sxs-lookup"><span data-stu-id="a2e20-270">Entity relationship models</span></span>

### <a name="worker"></a><span data-ttu-id="a2e20-271">Dolgozó</span><span class="sxs-lookup"><span data-stu-id="a2e20-271">Worker</span></span>

![Dolgozó](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a><span data-ttu-id="a2e20-273">Feladat és feladat beosztása</span><span class="sxs-lookup"><span data-stu-id="a2e20-273">Job and Job Position</span></span>

![Feladat és feladat beosztása](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a><span data-ttu-id="a2e20-275">Előnyök</span><span class="sxs-lookup"><span data-stu-id="a2e20-275">Benefits</span></span>

![Előnyök](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a><span data-ttu-id="a2e20-277">Kompenzáció</span><span class="sxs-lookup"><span data-stu-id="a2e20-277">Compensation</span></span>

![Kompenzáció](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a><span data-ttu-id="a2e20-279">Kilépés</span><span class="sxs-lookup"><span data-stu-id="a2e20-279">Leave</span></span>

![Kilépés](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a><span data-ttu-id="a2e20-281">Munkanaptár</span><span class="sxs-lookup"><span data-stu-id="a2e20-281">Work Calendar</span></span>

![Munkanaptár](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a><span data-ttu-id="a2e20-283">Lásd még</span><span class="sxs-lookup"><span data-stu-id="a2e20-283">See also</span></span>

[<span data-ttu-id="a2e20-284">Válasszon ki egy adatintegrációs technológiát</span><span class="sxs-lookup"><span data-stu-id="a2e20-284">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)</br>
[<span data-ttu-id="a2e20-285">A Common Data Service-integráció konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a2e20-285">Configure Common Data Service integration</span></span>](hr-admin-integration-common-data-service.md)
