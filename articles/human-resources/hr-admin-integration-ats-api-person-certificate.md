---
title: Személy tanúsítványa
description: Ez a témakör a Személy tanúsítványa entitást írja le a Dynamics 365 Human Resources rendszerhez.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5cdd742d6d36ccd7136f95e416507ed6e5e5a75a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055196"
---
# <a name="person-certificate"></a><span data-ttu-id="f7d3b-103">Személy tanúsítványa</span><span class="sxs-lookup"><span data-stu-id="f7d3b-103">Person certificate</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f7d3b-104">Ez a témakör a Személy tanúsítványa entitást írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="f7d3b-105">Fizikai név: mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="f7d3b-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="f7d3b-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="f7d3b-106">Description</span></span>

<span data-ttu-id="f7d3b-107">Ez az entitás a jelölt szakmai tanúsítványait írja le.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="f7d3b-108">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="f7d3b-108">JSON representation</span></span>

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="f7d3b-109">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="f7d3b-109">Properties</span></span>

| <span data-ttu-id="f7d3b-110">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="f7d3b-110">Property</span></span><br><span data-ttu-id="f7d3b-111">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-111">**Physical name**</span></span><br><span data-ttu-id="f7d3b-112">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-112">**_Type_**</span></span> | <span data-ttu-id="f7d3b-113">Használat</span><span class="sxs-lookup"><span data-stu-id="f7d3b-113">Use</span></span> | <span data-ttu-id="f7d3b-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="f7d3b-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f7d3b-115">**Személy tanúsítványa entitás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="f7d3b-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="f7d3b-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="f7d3b-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f7d3b-117">*GUID*</span></span> | <span data-ttu-id="f7d3b-118">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="f7d3b-118">Read-only</span></span><br><span data-ttu-id="f7d3b-119">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f7d3b-119">Required</span></span> | <span data-ttu-id="f7d3b-120">A személy tanúsítványa entitásrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="f7d3b-121">**Fél száma**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-121">**Party Number**</span></span><br><span data-ttu-id="f7d3b-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="f7d3b-122">mshr_partynumber</span></span><br><span data-ttu-id="f7d3b-123">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="f7d3b-123">*String*</span></span> | <span data-ttu-id="f7d3b-124">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f7d3b-124">Read/write</span></span><br><span data-ttu-id="f7d3b-125">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f7d3b-125">Required</span></span> | <span data-ttu-id="f7d3b-126">A jelölt fél (személy) rekordjának azonosítója.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="f7d3b-127">**Személyazonosító értéke**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-127">**Person ID Value**</span></span><br><span data-ttu-id="f7d3b-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="f7d3b-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="f7d3b-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f7d3b-129">*GUID*</span></span> | <span data-ttu-id="f7d3b-130">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="f7d3b-130">Read-only</span></span><br><span data-ttu-id="f7d3b-131">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f7d3b-131">Required</span></span><br><span data-ttu-id="f7d3b-132">Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="f7d3b-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="f7d3b-133">A fél (személy) entitásrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="f7d3b-134">**Tanúsítványtípus azonosítója**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-134">**Certificate Type ID**</span></span><br><span data-ttu-id="f7d3b-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="f7d3b-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="f7d3b-136">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="f7d3b-136">*String*</span></span> | <span data-ttu-id="f7d3b-137">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f7d3b-137">Read/write</span></span><br><span data-ttu-id="f7d3b-138">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f7d3b-138">Required</span></span> |  <span data-ttu-id="f7d3b-139">A Human Resources rendszerben definiált tanúsítványtípus azonosítója.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="f7d3b-140">**Tanúsítványtípus azonosítójának értéke**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="f7d3b-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="f7d3b-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="f7d3b-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f7d3b-142">*GUID*</span></span> | <span data-ttu-id="f7d3b-143">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="f7d3b-143">Read-only</span></span><br><span data-ttu-id="f7d3b-144">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f7d3b-144">Required</span></span><br><span data-ttu-id="f7d3b-145">Idegen kulcs: mshr_hcmcertificatetypeentityid / mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="f7d3b-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="f7d3b-146">A társított entitás tanúsítványtípusának rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="f7d3b-147">**Kezdő dátum**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-147">**Start Date**</span></span><br><span data-ttu-id="f7d3b-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="f7d3b-148">mshr_startdate</span></span><br><span data-ttu-id="f7d3b-149">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="f7d3b-149">*Datetime*</span></span> | <span data-ttu-id="f7d3b-150">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f7d3b-150">Read/write</span></span><br><span data-ttu-id="f7d3b-151">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f7d3b-151">Required</span></span> | <span data-ttu-id="f7d3b-152">A tanúsítvány kibocsátásának dátuma.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="f7d3b-153">**Záró dátum**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-153">**End Date**</span></span><br><span data-ttu-id="f7d3b-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="f7d3b-154">mshr_enddate</span></span><br><span data-ttu-id="f7d3b-155">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="f7d3b-155">*Datetime*</span></span> | <span data-ttu-id="f7d3b-156">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f7d3b-156">Read/write</span></span><br><span data-ttu-id="f7d3b-157">Választható</span><span class="sxs-lookup"><span data-stu-id="f7d3b-157">Optional</span></span> | <span data-ttu-id="f7d3b-158">A tanúsítvány lejáratának dátuma.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="f7d3b-159">**Jegyzetek**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-159">**Notes**</span></span><br><span data-ttu-id="f7d3b-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="f7d3b-160">mshr_notes</span></span><br><span data-ttu-id="f7d3b-161">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="f7d3b-161">*String*</span></span> | <span data-ttu-id="f7d3b-162">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f7d3b-162">Read/write</span></span><br><span data-ttu-id="f7d3b-163">Választható</span><span class="sxs-lookup"><span data-stu-id="f7d3b-163">Optional</span></span> | <span data-ttu-id="f7d3b-164">A toborzási vagy felvételi vezetők által használható megjegyzések.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="f7d3b-165">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="f7d3b-165">**Primary Field**</span></span><br><span data-ttu-id="f7d3b-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="f7d3b-166">mshr_primaryfield</span></span><br><span data-ttu-id="f7d3b-167">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="f7d3b-167">*String*</span></span> | <span data-ttu-id="f7d3b-168">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="f7d3b-168">Read-only</span></span><br><span data-ttu-id="f7d3b-169">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f7d3b-169">Required</span></span> |  <span data-ttu-id="f7d3b-170">Az entitásrekord azonosítójaként használandó mező.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="f7d3b-171">A fél számának, a tanúsítványtípus azonosítójának és a kezdő dátumnak a kombinációja.</span><span class="sxs-lookup"><span data-stu-id="f7d3b-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f7d3b-172">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f7d3b-172">See also</span></span>

[<span data-ttu-id="f7d3b-173">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="f7d3b-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="f7d3b-174">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="f7d3b-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]