---
title: Személy végzettsége
description: Ez a témakör a Személy végzettsége entitást írja le a Dynamics 365 Human Resources rendszerhez.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b3f3c5a94d7deedd70af0d031c15ecf631dce4d7
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125329"
---
# <a name="person-education"></a><span data-ttu-id="4e922-103">Személy végzettsége</span><span class="sxs-lookup"><span data-stu-id="4e922-103">Person education</span></span>

<span data-ttu-id="4e922-104">Ez a témakör a Személy végzettsége entitást írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="4e922-104">This topic describes the Person education entity for Dynamics 365 Human Resources.</span></span>


<span data-ttu-id="4e922-105">Fizikai név: mshr_hcmpersoneducationentity</span><span class="sxs-lookup"><span data-stu-id="4e922-105">Physical name: mshr_hcmpersoneducationentity</span></span>

## <a name="description"></a><span data-ttu-id="4e922-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4e922-106">Description</span></span>

<span data-ttu-id="4e922-107">Ez az entitás tartalmazza a jelölt tanulmányi előzményeit.</span><span class="sxs-lookup"><span data-stu-id="4e922-107">This entity contains the educational history of the person who is the candidate.</span></span> <span data-ttu-id="4e922-108">A végzettség ahhoz a személyrekordhoz kapcsolódik, amely lehetővé teszi, hogy a végzettség a jelölt rekordján kívül más szerepkörökhöz is társítva legyen (dolgozó, alvállalkozó stb.).</span><span class="sxs-lookup"><span data-stu-id="4e922-108">The education is linked to the person record enabling the education to be associated with any other roles created for the person in addition to the candidate record (worker, contractor, and so on).</span></span>

## <a name="json-representation"></a><span data-ttu-id="4e922-109">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="4e922-109">JSON representation</span></span>

```json
{
    "mshr_creditbasis": Int,
    "mshr_creditscompleted": Decimal,
    "mshr_creditsearned": Decimal,
    "mshr_creditsneeded": Decimal,
    "mshr_description": "String",
    "mshr_duration": Decimal,
    "mshr_durationunit": Int,
    "mshr_educationdisciplineid": "String",
    "mshr_educationinstitutionid": "String",
    "mshr_educationlevelid": "String",
    "mshr_enddate": "Date",
    "mshr_gradepointaverage": Decimal,
    "mshr_gradescale": "String",
    "mshr_notes": "String",
    "mshr_secondaryemphasis": "String",
    "mshr_startdate": "Date",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_educationinstitution_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmpersoneducationentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="4e922-110">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="4e922-110">Properties</span></span>

| <span data-ttu-id="4e922-111">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="4e922-111">Property</span></span><br><span data-ttu-id="4e922-112">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="4e922-112">**Physical name**</span></span><br><span data-ttu-id="4e922-113">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="4e922-113">**_Type_**</span></span> | <span data-ttu-id="4e922-114">Használat</span><span class="sxs-lookup"><span data-stu-id="4e922-114">Use</span></span> | <span data-ttu-id="4e922-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="4e922-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4e922-116">**Személy végzettsége entitás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="4e922-116">**Person Education Entity ID**</span></span><br><span data-ttu-id="4e922-117">mshr_hcmpersoneducationentityid</span><span class="sxs-lookup"><span data-stu-id="4e922-117">mshr_hcmpersoneducationentityid</span></span><br><span data-ttu-id="4e922-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4e922-118">*GUID*</span></span> | <span data-ttu-id="4e922-119">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="4e922-119">Read-only</span></span><br><span data-ttu-id="4e922-120">Szükséges</span><span class="sxs-lookup"><span data-stu-id="4e922-120">Required</span></span> | <span data-ttu-id="4e922-121">A személy végzettsége entitásrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="4e922-121">System-generated unique identifier of the person education entity record.</span></span> |
| <span data-ttu-id="4e922-122">**Fél száma**</span><span class="sxs-lookup"><span data-stu-id="4e922-122">**Party Number**</span></span><br><span data-ttu-id="4e922-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="4e922-123">mshr_partynumber</span></span><br><span data-ttu-id="4e922-124">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="4e922-124">*String*</span></span> | <span data-ttu-id="4e922-125">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-125">Read/write</span></span><br><span data-ttu-id="4e922-126">Szükséges</span><span class="sxs-lookup"><span data-stu-id="4e922-126">Required</span></span> | <span data-ttu-id="4e922-127">A jelölt fél (személy) rekordjának egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="4e922-127">The unique identifier of the party (person) record for the candidate.</span></span> |
| <span data-ttu-id="4e922-128">**Személyazonosító értéke**</span><span class="sxs-lookup"><span data-stu-id="4e922-128">**Person ID Value**</span></span><br><span data-ttu-id="4e922-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="4e922-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="4e922-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4e922-130">*GUID*</span></span> | <span data-ttu-id="4e922-131">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="4e922-131">Read-only</span></span><br><span data-ttu-id="4e922-132">Szükséges</span><span class="sxs-lookup"><span data-stu-id="4e922-132">Required</span></span><br><span data-ttu-id="4e922-133">Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="4e922-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="4e922-134">A jelölt személyi rekordjának rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="4e922-134">The system-generated unique identifier of the candidate’s person record.</span></span> |
| <span data-ttu-id="4e922-135">**Tanulmányi pontszám alapja**</span><span class="sxs-lookup"><span data-stu-id="4e922-135">**Credit Basis**</span></span><br><span data-ttu-id="4e922-136">mshr_creditbasis</span><span class="sxs-lookup"><span data-stu-id="4e922-136">mshr_creditbasis</span></span><br><span data-ttu-id="4e922-137">*mshr_hcmeducationcreditbasis beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="4e922-137">*mshr_hcmeducationcreditbasis option set*</span></span> | <span data-ttu-id="4e922-138">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-138">Read/write</span></span><br><span data-ttu-id="4e922-139">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-139">Optional</span></span> | <span data-ttu-id="4e922-140">A fokozat tanulmányi pontszámának alapja.</span><span class="sxs-lookup"><span data-stu-id="4e922-140">The credit basis of the educational degree.</span></span> |
| <span data-ttu-id="4e922-141">**Teljesített tanulmányi egységek**</span><span class="sxs-lookup"><span data-stu-id="4e922-141">**Credits Completed**</span></span><br><span data-ttu-id="4e922-142">mshr_creditscompleted</span><span class="sxs-lookup"><span data-stu-id="4e922-142">mshr_creditscompleted</span></span><br><span data-ttu-id="4e922-143">*Decimális*</span><span class="sxs-lookup"><span data-stu-id="4e922-143">*Decimal*</span></span> | <span data-ttu-id="4e922-144">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-144">Read/write</span></span><br><span data-ttu-id="4e922-145">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-145">Optional</span></span> | <span data-ttu-id="4e922-146">A végzettség során teljesített tanulmányi egységek száma.</span><span class="sxs-lookup"><span data-stu-id="4e922-146">The number of credits completed for the education.</span></span> |
| <span data-ttu-id="4e922-147">**Megszerzett tanulmányi pontszám**</span><span class="sxs-lookup"><span data-stu-id="4e922-147">**Credits Earned**</span></span><br><span data-ttu-id="4e922-148">mshr_creditsearned</span><span class="sxs-lookup"><span data-stu-id="4e922-148">mshr_creditsearned</span></span><br><span data-ttu-id="4e922-149">*Decimális*</span><span class="sxs-lookup"><span data-stu-id="4e922-149">*Decimal*</span></span> | <span data-ttu-id="4e922-150">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-150">Read/write</span></span><br><span data-ttu-id="4e922-151">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-151">Optional</span></span> | <span data-ttu-id="4e922-152">A folyamatban lévő fokozat végzettségrekordjában megszerzett tanulmányi pontszám.</span><span class="sxs-lookup"><span data-stu-id="4e922-152">The number of credits earned for the education record for a degree in progress.</span></span> |
| <span data-ttu-id="4e922-153">**Szükséges pontszám**</span><span class="sxs-lookup"><span data-stu-id="4e922-153">**Credits Needed**</span></span><br><span data-ttu-id="4e922-154">mshr_creditsneeded</span><span class="sxs-lookup"><span data-stu-id="4e922-154">mshr_creditsneeded</span></span><br><span data-ttu-id="4e922-155">*Decimális*</span><span class="sxs-lookup"><span data-stu-id="4e922-155">*Decimal*</span></span> | <span data-ttu-id="4e922-156">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-156">Read/write</span></span><br><span data-ttu-id="4e922-157">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-157">Optional</span></span> | <span data-ttu-id="4e922-158">A folyamatban lévő fokozathoz szükséges pontszám.</span><span class="sxs-lookup"><span data-stu-id="4e922-158">The number of credits required for a degree in progress.</span></span> |
| <span data-ttu-id="4e922-159">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="4e922-159">**Description**</span></span><br><span data-ttu-id="4e922-160">mshr_description</span><span class="sxs-lookup"><span data-stu-id="4e922-160">mshr_description</span></span><br><span data-ttu-id="4e922-161">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="4e922-161">*String*</span></span> | <span data-ttu-id="4e922-162">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-162">Read/write</span></span><br><span data-ttu-id="4e922-163">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-163">Optional</span></span> | <span data-ttu-id="4e922-164">A jelölt fokozatának leírása.</span><span class="sxs-lookup"><span data-stu-id="4e922-164">A description of the candidate’s degree.</span></span> |
| <span data-ttu-id="4e922-165">**Végzettségi szint azonosítója**</span><span class="sxs-lookup"><span data-stu-id="4e922-165">**Education Level ID**</span></span><br><span data-ttu-id="4e922-166">mshr_educationlevelid</span><span class="sxs-lookup"><span data-stu-id="4e922-166">mshr_educationlevelid</span></span><br><span data-ttu-id="4e922-167">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="4e922-167">*String*</span></span> | <span data-ttu-id="4e922-168">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-168">Read/write</span></span><br><span data-ttu-id="4e922-169">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-169">Optional</span></span> | <span data-ttu-id="4e922-170">A végzettségi szint azonosítója.</span><span class="sxs-lookup"><span data-stu-id="4e922-170">The ID of the education level.</span></span> | 
| <span data-ttu-id="4e922-171">**Végzettségi szint értéke**</span><span class="sxs-lookup"><span data-stu-id="4e922-171">**Education Level ID Value**</span></span><br><span data-ttu-id="4e922-172">_mshr_fk_educationlevel_id_value</span><span class="sxs-lookup"><span data-stu-id="4e922-172">_mshr_fk_educationlevel_id_value</span></span><br><span data-ttu-id="4e922-173">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4e922-173">*GUID*</span></span> | <span data-ttu-id="4e922-174">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="4e922-174">Read-only</span></span><br><span data-ttu-id="4e922-175">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-175">Optional</span></span><br><span data-ttu-id="4e922-176">Idegen kulcs: mshr_hcmeducationdegreeentityid / mshr_hcmeducationdegreeentity entitás</span><span class="sxs-lookup"><span data-stu-id="4e922-176">Foreign key: mshr_hcmeducationdegreeentityid of mshr_hcmeducationdegreeentity entity</span></span> | <span data-ttu-id="4e922-177">A végzettségrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="4e922-177">System-generated identifier for the education degree record.</span></span> <span data-ttu-id="4e922-178">Ez az azonosító biztosítja a szervezethez meghatározott fokozatokat és végzettségi szinteket.</span><span class="sxs-lookup"><span data-stu-id="4e922-178">This identifier provides the degrees and education levels defined for the organization.</span></span> |
| <span data-ttu-id="4e922-179">**Végzettség tantárgyazonosítója**</span><span class="sxs-lookup"><span data-stu-id="4e922-179">**Education Discipline ID**</span></span><br><span data-ttu-id="4e922-180">mshr_educationdisciplineid</span><span class="sxs-lookup"><span data-stu-id="4e922-180">mshr_educationdisciplineid</span></span><br><span data-ttu-id="4e922-181">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="4e922-181">*String*</span></span> | <span data-ttu-id="4e922-182">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-182">Read/write</span></span><br><span data-ttu-id="4e922-183">Szükséges</span><span class="sxs-lookup"><span data-stu-id="4e922-183">Required</span></span><br><span data-ttu-id="4e922-184">Idegen kulcs: EducationDiscipline</span><span class="sxs-lookup"><span data-stu-id="4e922-184">Foreign key: EducationDiscipline</span></span> | <span data-ttu-id="4e922-185">A végzettség tantárgyazonosítója.</span><span class="sxs-lookup"><span data-stu-id="4e922-185">The ID of the education discipline.</span></span> |
| <span data-ttu-id="4e922-186">**Végzettség tantárgyazonosítójának értéke**</span><span class="sxs-lookup"><span data-stu-id="4e922-186">**Education Discipline ID Value**</span></span><br><span data-ttu-id="4e922-187">_mshr_fk_educationdiscipline_id_value</span><span class="sxs-lookup"><span data-stu-id="4e922-187">_mshr_fk_educationdiscipline_id_value</span></span><br><span data-ttu-id="4e922-188">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4e922-188">*GUID*</span></span> | <span data-ttu-id="4e922-189">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="4e922-189">Read-only</span></span><br><span data-ttu-id="4e922-190">Szükséges</span><span class="sxs-lookup"><span data-stu-id="4e922-190">Required</span></span><br><span data-ttu-id="4e922-191">Idegen kulcs: mshr_hcmeducationdisciplineentityid / mshr_hcmeducationdisciplineentity</span><span class="sxs-lookup"><span data-stu-id="4e922-191">Foreign key: mshr_hcmeducationdisciplineentityid of mshr_hcmeducationdisciplineentity</span></span> | <span data-ttu-id="4e922-192">A végzettség tantárgyhoz tartozó végzettségrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="4e922-192">The system-generated unique identifier of the education discipline of the education record.</span></span> |
| <span data-ttu-id="4e922-193">**Másodlagos hangsúly**</span><span class="sxs-lookup"><span data-stu-id="4e922-193">**Secondary Emphasis**</span></span><br><span data-ttu-id="4e922-194">mshr_secondaryemphasis</span><span class="sxs-lookup"><span data-stu-id="4e922-194">mshr_secondaryemphasis</span></span><br><span data-ttu-id="4e922-195">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="4e922-195">*String*</span></span> | <span data-ttu-id="4e922-196">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-196">Read/write</span></span><br><span data-ttu-id="4e922-197">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-197">Optional</span></span> | <span data-ttu-id="4e922-198">A megszerzett fokozat másodlagos hangsúlya.</span><span class="sxs-lookup"><span data-stu-id="4e922-198">The secondary emphasis of the earned degree.</span></span> |
| <span data-ttu-id="4e922-199">**Oktatási intézmény azonosítója**</span><span class="sxs-lookup"><span data-stu-id="4e922-199">**Education Institution ID**</span></span><br><span data-ttu-id="4e922-200">mshr_educationinstitutionid</span><span class="sxs-lookup"><span data-stu-id="4e922-200">mshr_educationinstitutionid</span></span><br><span data-ttu-id="4e922-201">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="4e922-201">*String*</span></span> | <span data-ttu-id="4e922-202">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-202">Read/write</span></span><br><span data-ttu-id="4e922-203">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-203">Optional</span></span> | <span data-ttu-id="4e922-204">Az oktatási intézmény azonosítója.</span><span class="sxs-lookup"><span data-stu-id="4e922-204">The ID of the attended educational institution.</span></span> |
| <span data-ttu-id="4e922-205">**Oktatási intézmény azonosítójának értéke**</span><span class="sxs-lookup"><span data-stu-id="4e922-205">**Education Institution ID Value**</span></span><br><span data-ttu-id="4e922-206">_mshr_fk_educationinstitution_id_value</span><span class="sxs-lookup"><span data-stu-id="4e922-206">_mshr_fk_educationinstitution_id_value</span></span><br><span data-ttu-id="4e922-207">*GUID*</span><span class="sxs-lookup"><span data-stu-id="4e922-207">*GUID*</span></span> | <span data-ttu-id="4e922-208">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="4e922-208">Read-only</span></span><br><span data-ttu-id="4e922-209">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-209">Optional</span></span><br><span data-ttu-id="4e922-210">Idegen kulcs: mshr_hcmeducationinstitutionentityid / mshr_hcmeducationinstitutionentity</span><span class="sxs-lookup"><span data-stu-id="4e922-210">Foreign key: mshr_hcmeducationinstitutionentityid of mshr_hcmeducationinstitutionentity</span></span> | <span data-ttu-id="4e922-211">Az oktatási intézmény rendszer által generált azonosítója.</span><span class="sxs-lookup"><span data-stu-id="4e922-211">System-generated identifier of the educational institution.</span></span> |
| <span data-ttu-id="4e922-212">**Kezdő dátum**</span><span class="sxs-lookup"><span data-stu-id="4e922-212">**Start Date**</span></span><br><span data-ttu-id="4e922-213">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="4e922-213">mshr_startdate</span></span><br><span data-ttu-id="4e922-214">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="4e922-214">*Datetime*</span></span> | <span data-ttu-id="4e922-215">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-215">Read/write</span></span><br><span data-ttu-id="4e922-216">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-216">Optional</span></span> | <span data-ttu-id="4e922-217">A megszerzett fokozat oktatásának kezdő dátuma.</span><span class="sxs-lookup"><span data-stu-id="4e922-217">The start date of the education for the earned degree.</span></span> |
| <span data-ttu-id="4e922-218">**Záró dátum**</span><span class="sxs-lookup"><span data-stu-id="4e922-218">**End Date**</span></span><br><span data-ttu-id="4e922-219">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="4e922-219">mshr_enddate</span></span><br><span data-ttu-id="4e922-220">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="4e922-220">*Datetime*</span></span> | <span data-ttu-id="4e922-221">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-221">Read/write</span></span><br><span data-ttu-id="4e922-222">Szükséges</span><span class="sxs-lookup"><span data-stu-id="4e922-222">Required</span></span> | <span data-ttu-id="4e922-223">A fokozat kibocsátásának dátuma.</span><span class="sxs-lookup"><span data-stu-id="4e922-223">The date the credential was issued.</span></span> |
| <span data-ttu-id="4e922-224">**Időtartam**</span><span class="sxs-lookup"><span data-stu-id="4e922-224">**Duration**</span></span><br><span data-ttu-id="4e922-225">mshr_duration</span><span class="sxs-lookup"><span data-stu-id="4e922-225">mshr_duration</span></span><br><span data-ttu-id="4e922-226">*Decimális*</span><span class="sxs-lookup"><span data-stu-id="4e922-226">*Decimal*</span></span> | <span data-ttu-id="4e922-227">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-227">Read/write</span></span><br><span data-ttu-id="4e922-228">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-228">Optional</span></span> | <span data-ttu-id="4e922-229">A végzettségrekord időtartama.</span><span class="sxs-lookup"><span data-stu-id="4e922-229">The duration of time of the education record.</span></span> |
| <span data-ttu-id="4e922-230">**Időtartam egysége**</span><span class="sxs-lookup"><span data-stu-id="4e922-230">**Duration Unit**</span></span><br><span data-ttu-id="4e922-231">mshr_durationunit</span><span class="sxs-lookup"><span data-stu-id="4e922-231">mshr_durationunit</span></span><br><span data-ttu-id="4e922-232">*mshr_periodunit beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="4e922-232">*mshr_periodunit option set*</span></span> | <span data-ttu-id="4e922-233">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-233">Read/write</span></span><br><span data-ttu-id="4e922-234">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-234">Optional</span></span> | <span data-ttu-id="4e922-235">A végzettségrekord időtartamához kapcsolódó időegység.</span><span class="sxs-lookup"><span data-stu-id="4e922-235">The unit of time associated with the duration of the education record.</span></span> |
| <span data-ttu-id="4e922-236">**Osztályzatok átlaga**</span><span class="sxs-lookup"><span data-stu-id="4e922-236">**Grade Point Average**</span></span><br><span data-ttu-id="4e922-237">mshr_gradepointaverage</span><span class="sxs-lookup"><span data-stu-id="4e922-237">mshr_gradepointaverage</span></span><br><span data-ttu-id="4e922-238">*Decimális*</span><span class="sxs-lookup"><span data-stu-id="4e922-238">*Decimal*</span></span> | <span data-ttu-id="4e922-239">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-239">Read/write</span></span><br><span data-ttu-id="4e922-240">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-240">Optional</span></span> | <span data-ttu-id="4e922-241">A fokozathoz megszerzett osztályzatok átlaga.</span><span class="sxs-lookup"><span data-stu-id="4e922-241">The earned grade point average for the degree.</span></span> |
| <span data-ttu-id="4e922-242">**Osztályzatok skálája**</span><span class="sxs-lookup"><span data-stu-id="4e922-242">**Grade Scale**</span></span><br><span data-ttu-id="4e922-243">mshr_gradescale</span><span class="sxs-lookup"><span data-stu-id="4e922-243">mshr_gradescale</span></span><br><span data-ttu-id="4e922-244">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="4e922-244">*String*</span></span> | <span data-ttu-id="4e922-245">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-245">Read/write</span></span><br><span data-ttu-id="4e922-246">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-246">Optional</span></span> | <span data-ttu-id="4e922-247">Az osztályzatok átlagához használt skála.</span><span class="sxs-lookup"><span data-stu-id="4e922-247">The scale used for the grade point average.</span></span> |
| <span data-ttu-id="4e922-248">**Jegyzetek**</span><span class="sxs-lookup"><span data-stu-id="4e922-248">**Notes**</span></span><br><span data-ttu-id="4e922-249">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="4e922-249">mshr_notes</span></span><br><span data-ttu-id="4e922-250">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="4e922-250">*String*</span></span> | <span data-ttu-id="4e922-251">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="4e922-251">Read/write</span></span><br><span data-ttu-id="4e922-252">Választható</span><span class="sxs-lookup"><span data-stu-id="4e922-252">Optional</span></span> | <span data-ttu-id="4e922-253">A toborzási vagy felvételi vezető által használható megjegyzések.</span><span class="sxs-lookup"><span data-stu-id="4e922-253">Notes for use by the recruiter or hiring manager.</span></span> |
| <span data-ttu-id="4e922-254">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="4e922-254">**Primary Field**</span></span><br><span data-ttu-id="4e922-255">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="4e922-255">mshr_primaryfield</span></span><br><span data-ttu-id="4e922-256">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="4e922-256">*String*</span></span> | <span data-ttu-id="4e922-257">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="4e922-257">Read-only</span></span><br><span data-ttu-id="4e922-258">Szükséges</span><span class="sxs-lookup"><span data-stu-id="4e922-258">Required</span></span> | <span data-ttu-id="4e922-259">Az entitásrekord egy másik elsődleges azonosítójaként használt mező.</span><span class="sxs-lookup"><span data-stu-id="4e922-259">Field used as another primary identifier of the entity record.</span></span> <span data-ttu-id="4e922-260">A fél számának, a tantárgyazonosítónak, az oktatási intézmény azonosítójának és a végzettségi szintnek a kombinációja.</span><span class="sxs-lookup"><span data-stu-id="4e922-260">Combination of party number, education discipline ID, education institution ID, and education level ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4e922-261">Lásd még</span><span class="sxs-lookup"><span data-stu-id="4e922-261">See also</span></span>

[<span data-ttu-id="4e922-262">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="4e922-262">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="4e922-263">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="4e922-263">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
