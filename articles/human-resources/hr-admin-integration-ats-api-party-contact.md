---
title: Fél kapcsolattartója
description: Ez a témakör a Fél kapcsolattartója entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 38f53d402ebe9f9f358281dd3996797a20923056
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125473"
---
# <a name="party-contact"></a><span data-ttu-id="83568-103">Fél kapcsolattartója</span><span class="sxs-lookup"><span data-stu-id="83568-103">Party contact</span></span>

<span data-ttu-id="83568-104">Ez a témakör a Fél kapcsolattartója entitást írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="83568-104">This topic describes the Party contact entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="83568-105">Fizikai név: mshr_dirpartycontactentities</span><span class="sxs-lookup"><span data-stu-id="83568-105">Physical name: mshr_dirpartycontactentities</span></span>

## <a name="description"></a><span data-ttu-id="83568-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="83568-106">Description</span></span>

<span data-ttu-id="83568-107">Ez az entitás leírja a jelölt kapcsolattartási adatait, többek között a telefonszámát és e-mail-címét, valamint a közösségimédia-fiókjait.</span><span class="sxs-lookup"><span data-stu-id="83568-107">This entity describes the candidate’s contact information, including phone, email, and social media accounts.</span></span>

## <a name="json-representation"></a><span data-ttu-id="83568-108">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="83568-108">JSON representation</span></span>

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_type": Int,
    "mshr_countryregioncode": "String",
    "mshr_locator": "String",
    "mshr_locatorextension": "String",
    "mshr_purpose": "String",
    "mshr_ismobilephone": Int,
    "mshr_isinstantmessage": Int,
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "String",
    "mshr_dirpartycontactentityid": "String"
}
```

## <a name="properties"></a><span data-ttu-id="83568-109">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="83568-109">Properties</span></span>

| <span data-ttu-id="83568-110">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="83568-110">Property</span></span><br><span data-ttu-id="83568-111">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="83568-111">**Physical name**</span></span><br><span data-ttu-id="83568-112">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="83568-112">**_Type_**</span></span> | <span data-ttu-id="83568-113">Használat</span><span class="sxs-lookup"><span data-stu-id="83568-113">Use</span></span> | <span data-ttu-id="83568-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="83568-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="83568-115">**Fél kapcsolattartójának entitásazonosítója**</span><span class="sxs-lookup"><span data-stu-id="83568-115">**Party Contact Entity ID**</span></span><br><span data-ttu-id="83568-116">mshr_dirpartycontactentityid</span><span class="sxs-lookup"><span data-stu-id="83568-116">mshr_dirpartycontactentityid</span></span><br><span data-ttu-id="83568-117">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="83568-117">*String*</span></span> | <span data-ttu-id="83568-118">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="83568-118">Read-only</span></span><br><span data-ttu-id="83568-119">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-119">Required</span></span> | <span data-ttu-id="83568-120">Az entitásrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="83568-120">System-generated unique identifier for the entity record.</span></span> |
| <span data-ttu-id="83568-121">**Fél száma**</span><span class="sxs-lookup"><span data-stu-id="83568-121">**Party Number**</span></span><br><span data-ttu-id="83568-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="83568-122">mshr_partynumber</span></span><br><span data-ttu-id="83568-123">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="83568-123">*String*</span></span> | <span data-ttu-id="83568-124">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-124">Read/write</span></span><br><span data-ttu-id="83568-125">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-125">Required</span></span> | <span data-ttu-id="83568-126">A társított fél (személy) rekordjának azonosítója.</span><span class="sxs-lookup"><span data-stu-id="83568-126">The ID of the associated party (person) record.</span></span> |
| <span data-ttu-id="83568-127">**Személyazonosító értéke**</span><span class="sxs-lookup"><span data-stu-id="83568-127">**Person ID Value**</span></span><br><span data-ttu-id="83568-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="83568-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="83568-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="83568-129">*GUID*</span></span> | <span data-ttu-id="83568-130">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="83568-130">Read-only</span></span><br><span data-ttu-id="83568-131">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-131">Required</span></span><br><span data-ttu-id="83568-132">Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="83568-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="83568-133">A fél (személy) entitásrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="83568-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="83568-134">**Helyazonosító**</span><span class="sxs-lookup"><span data-stu-id="83568-134">**Location ID**</span></span><br><span data-ttu-id="83568-135">mshr_locationid</span><span class="sxs-lookup"><span data-stu-id="83568-135">mshr_locationid</span></span><br><span data-ttu-id="83568-136">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="83568-136">*String*</span></span> | <span data-ttu-id="83568-137">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-137">Read/write</span></span><br><span data-ttu-id="83568-138">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-138">Required</span></span> | <span data-ttu-id="83568-139">A címrekord helyazonosítója.</span><span class="sxs-lookup"><span data-stu-id="83568-139">The location ID of the address record.</span></span> <span data-ttu-id="83568-140">Beállítás egy mshr_logisticspostaladdresslocationcdsentity entitásban.</span><span class="sxs-lookup"><span data-stu-id="83568-140">Set up in mshr_logisticspostaladdresslocationcdsentity entity.</span></span> |
| <span data-ttu-id="83568-141">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="83568-141">**Description**</span></span><br><span data-ttu-id="83568-142">mshr_description</span><span class="sxs-lookup"><span data-stu-id="83568-142">mshr_description</span></span><br><span data-ttu-id="83568-143">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="83568-143">*String*</span></span> | <span data-ttu-id="83568-144">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-144">Read/write</span></span><br><span data-ttu-id="83568-145">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-145">Required</span></span> | <span data-ttu-id="83568-146">A kapcsolattartó részleteinek leírása.</span><span class="sxs-lookup"><span data-stu-id="83568-146">The description of the contact details.</span></span> |
| <span data-ttu-id="83568-147">**Típus**</span><span class="sxs-lookup"><span data-stu-id="83568-147">**Type**</span></span><br><span data-ttu-id="83568-148">mshr_type</span><span class="sxs-lookup"><span data-stu-id="83568-148">mshr_type</span></span><br><span data-ttu-id="83568-149">*mshr_logisticselectronicaddressmethodtype beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="83568-149">*mshr_logisticselectronicaddressmethodtype option set*</span></span> | <span data-ttu-id="83568-150">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-150">Read/write</span></span><br><span data-ttu-id="83568-151">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-151">Required</span></span> | <span data-ttu-id="83568-152">A kapcsolattartó részleteinek típusa.</span><span class="sxs-lookup"><span data-stu-id="83568-152">The contact detail type.</span></span> |
| <span data-ttu-id="83568-153">**Ország/régió kódja**</span><span class="sxs-lookup"><span data-stu-id="83568-153">**Country Region Code**</span></span><br><span data-ttu-id="83568-154">mshr_countryregioncode</span><span class="sxs-lookup"><span data-stu-id="83568-154">mshr_countryregioncode</span></span><br><span data-ttu-id="83568-155">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="83568-155">*String*</span></span> | <span data-ttu-id="83568-156">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-156">Read/write</span></span><br><span data-ttu-id="83568-157">Választható</span><span class="sxs-lookup"><span data-stu-id="83568-157">Optional</span></span> | <span data-ttu-id="83568-158">A címhez tartozó ország vagy régió megadása</span><span class="sxs-lookup"><span data-stu-id="83568-158">The country or region of the address.</span></span> |
| <span data-ttu-id="83568-159">**Lokátor**</span><span class="sxs-lookup"><span data-stu-id="83568-159">**Locator**</span></span><br><span data-ttu-id="83568-160">mshr_locator</span><span class="sxs-lookup"><span data-stu-id="83568-160">mshr_locator</span></span><br><span data-ttu-id="83568-161">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="83568-161">*String*</span></span> | <span data-ttu-id="83568-162">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-162">Read/write</span></span><br><span data-ttu-id="83568-163">Választható</span><span class="sxs-lookup"><span data-stu-id="83568-163">Optional</span></span> | <span data-ttu-id="83568-164">A kapcsolattartó adatai.</span><span class="sxs-lookup"><span data-stu-id="83568-164">The contact details.</span></span> <span data-ttu-id="83568-165">Ha például a típus **E-mail-cím**, akkor ez a mező a jelölt e-mail-címét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="83568-165">For example, if the type is **Email address**, then this field contains the candidate’s email address.</span></span> |
| <span data-ttu-id="83568-166">**Lokátor bővítménye**</span><span class="sxs-lookup"><span data-stu-id="83568-166">**Locator Extension**</span></span><br><span data-ttu-id="83568-167">mshr_locatorextension</span><span class="sxs-lookup"><span data-stu-id="83568-167">mshr_locatorextension</span></span><br><span data-ttu-id="83568-168">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="83568-168">*String*</span></span> | <span data-ttu-id="83568-169">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-169">Read/write</span></span><br><span data-ttu-id="83568-170">Választható</span><span class="sxs-lookup"><span data-stu-id="83568-170">Optional</span></span> | <span data-ttu-id="83568-171">A lokátor bővítménye.</span><span class="sxs-lookup"><span data-stu-id="83568-171">The locator extension.</span></span> <span data-ttu-id="83568-172">Ha például a típus **Telefon**, ez a tulajdonság a telefonszámmelléket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="83568-172">For example, if the type is **Phone**, then this property would contain the phone number extension.</span></span> |
| <span data-ttu-id="83568-173">**Mobil**</span><span class="sxs-lookup"><span data-stu-id="83568-173">**Is Mobile**</span></span><br><span data-ttu-id="83568-174">mshr_ismobile</span><span class="sxs-lookup"><span data-stu-id="83568-174">mshr_ismobile</span></span><br><span data-ttu-id="83568-175">*mshr_noyes beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="83568-175">*mshr_noyes option set*</span></span> | <span data-ttu-id="83568-176">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-176">Read/write</span></span><br><span data-ttu-id="83568-177">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-177">Required</span></span> | <span data-ttu-id="83568-178">Azt adja meg, hogy a telefon mobiltelefonszám-e.</span><span class="sxs-lookup"><span data-stu-id="83568-178">Specifies whether the phone is a mobile number.</span></span> |
| <span data-ttu-id="83568-179">**Azonnali üzenet**</span><span class="sxs-lookup"><span data-stu-id="83568-179">**Is Instant Message**</span></span><br><span data-ttu-id="83568-180">mshr_isinstantmessage</span><span class="sxs-lookup"><span data-stu-id="83568-180">mshr_isinstantmessage</span></span><br><span data-ttu-id="83568-181">*mshr_noyes beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="83568-181">*mshr_noyes option set*</span></span> | <span data-ttu-id="83568-182">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-182">Read/write</span></span><br><span data-ttu-id="83568-183">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-183">Required</span></span> | <span data-ttu-id="83568-184">Megadja, hogy a telefon engedélyezve van-e azonnali üzenetküldésre.</span><span class="sxs-lookup"><span data-stu-id="83568-184">Specifies whether the phone is enabled for instant messaging.</span></span> |
| <span data-ttu-id="83568-185">**Elsődleges**</span><span class="sxs-lookup"><span data-stu-id="83568-185">**Is Primary**</span></span><br><span data-ttu-id="83568-186">mshr_isprimary</span><span class="sxs-lookup"><span data-stu-id="83568-186">mshr_isprimary</span></span><br><span data-ttu-id="83568-187">*mshr_noyes beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="83568-187">*mshr_noyes option set*</span></span> | <span data-ttu-id="83568-188">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-188">Read/write</span></span><br><span data-ttu-id="83568-189">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-189">Required</span></span> | <span data-ttu-id="83568-190">Meghatározza a kapcsolattartó típusának elsődleges kapcsolattartóját.</span><span class="sxs-lookup"><span data-stu-id="83568-190">Determines the primary contact of the contact type.</span></span> <span data-ttu-id="83568-191">Kapcsolattartó-típusonként csak egy elsődleges rekord lehet.</span><span class="sxs-lookup"><span data-stu-id="83568-191">There must be only one primary record per contact type.</span></span> |
| <span data-ttu-id="83568-192">**Magánjellegű**</span><span class="sxs-lookup"><span data-stu-id="83568-192">**Is Private**</span></span><br><span data-ttu-id="83568-193">mshr_isprivate</span><span class="sxs-lookup"><span data-stu-id="83568-193">mshr_isprivate</span></span><br><span data-ttu-id="83568-194">*mshr_noyes beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="83568-194">*mshr_noyes option set*</span></span> | <span data-ttu-id="83568-195">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-195">Read/write</span></span><br><span data-ttu-id="83568-196">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-196">Required</span></span> | <span data-ttu-id="83568-197">Azt jelzi, hogy ez a cím a személy privát címe-e.</span><span class="sxs-lookup"><span data-stu-id="83568-197">Identifies whether this address is a private address for the person.</span></span> |
| <span data-ttu-id="83568-198">**Alkalmazás célja**</span><span class="sxs-lookup"><span data-stu-id="83568-198">**Purpose**</span></span><br><span data-ttu-id="83568-199">mshr_purpose</span><span class="sxs-lookup"><span data-stu-id="83568-199">mshr_purpose</span></span><br><span data-ttu-id="83568-200">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="83568-200">*String*</span></span> | <span data-ttu-id="83568-201">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="83568-201">Read/write</span></span><br><span data-ttu-id="83568-202">Választható</span><span class="sxs-lookup"><span data-stu-id="83568-202">Optional</span></span> | <span data-ttu-id="83568-203">A kapcsolattartó céljának/szerepkörének leírása.</span><span class="sxs-lookup"><span data-stu-id="83568-203">The purpose/role of the contact details.</span></span> |
| <span data-ttu-id="83568-204">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="83568-204">**Primary Field**</span></span><br><span data-ttu-id="83568-205">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="83568-205">mshr_primaryfield</span></span><br><span data-ttu-id="83568-206">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="83568-206">*String*</span></span> | <span data-ttu-id="83568-207">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="83568-207">Read-only</span></span><br><span data-ttu-id="83568-208">Szükséges</span><span class="sxs-lookup"><span data-stu-id="83568-208">Required</span></span> | <span data-ttu-id="83568-209">Az entitásrekord elsődleges azonosítójaként használt mező.</span><span class="sxs-lookup"><span data-stu-id="83568-209">Field used as a primary identifier of the entity record.</span></span> <span data-ttu-id="83568-210">Fél számának, típusának, leírásának és lokátorának kombinációja.</span><span class="sxs-lookup"><span data-stu-id="83568-210">Combination of party number, type, description, and locator.</span></span> |

## <a name="see-also"></a><span data-ttu-id="83568-211">Lásd még</span><span class="sxs-lookup"><span data-stu-id="83568-211">See also</span></span>

[<span data-ttu-id="83568-212">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="83568-212">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="83568-213">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="83568-213">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)
