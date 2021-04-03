---
title: Személy tanúsítványa
description: Ez a témakör a Személy tanúsítványa entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 4587337d8fd52828309826f3301b6f053b267819
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466520"
---
# <a name="person-certificate"></a><span data-ttu-id="d6951-103">Személy tanúsítványa</span><span class="sxs-lookup"><span data-stu-id="d6951-103">Person certificate</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d6951-104">Ez a témakör a Személy tanúsítványa entitást írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="d6951-104">This topic describes the Person certificate entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="d6951-105">Fizikai név: mshr_hcmpersoncertificateentity</span><span class="sxs-lookup"><span data-stu-id="d6951-105">Physical name: mshr_hcmpersoncertificateentity</span></span>

## <a name="description"></a><span data-ttu-id="d6951-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="d6951-106">Description</span></span>

<span data-ttu-id="d6951-107">Ez az entitás a jelölt szakmai tanúsítványait írja le.</span><span class="sxs-lookup"><span data-stu-id="d6951-107">This entity describes the professional certificates of a candidate.</span></span>

## <a name="json-representation"></a><span data-ttu-id="d6951-108">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="d6951-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="d6951-109">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="d6951-109">Properties</span></span>

| <span data-ttu-id="d6951-110">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="d6951-110">Property</span></span><br><span data-ttu-id="d6951-111">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="d6951-111">**Physical name**</span></span><br><span data-ttu-id="d6951-112">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="d6951-112">**_Type_**</span></span> | <span data-ttu-id="d6951-113">Használat</span><span class="sxs-lookup"><span data-stu-id="d6951-113">Use</span></span> | <span data-ttu-id="d6951-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="d6951-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="d6951-115">**Személy tanúsítványa entitás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="d6951-115">**Person Certificate Entity ID**</span></span><br><span data-ttu-id="d6951-116">mshr_hcmpersoncertificateentityid</span><span class="sxs-lookup"><span data-stu-id="d6951-116">mshr_hcmpersoncertificateentityid</span></span><br><span data-ttu-id="d6951-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="d6951-117">*GUID*</span></span> | <span data-ttu-id="d6951-118">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d6951-118">Read-only</span></span><br><span data-ttu-id="d6951-119">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d6951-119">Required</span></span> | <span data-ttu-id="d6951-120">A személy tanúsítványa entitásrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="d6951-120">System-generated unique identifier for the person certificate entity record.</span></span> |
| <span data-ttu-id="d6951-121">**Fél száma**</span><span class="sxs-lookup"><span data-stu-id="d6951-121">**Party Number**</span></span><br><span data-ttu-id="d6951-122">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="d6951-122">mshr_partynumber</span></span><br><span data-ttu-id="d6951-123">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d6951-123">*String*</span></span> | <span data-ttu-id="d6951-124">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="d6951-124">Read/write</span></span><br><span data-ttu-id="d6951-125">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d6951-125">Required</span></span> | <span data-ttu-id="d6951-126">A jelölt fél (személy) rekordjának azonosítója.</span><span class="sxs-lookup"><span data-stu-id="d6951-126">The party (person) ID of the candidate.</span></span> |
| <span data-ttu-id="d6951-127">**Személyazonosító értéke**</span><span class="sxs-lookup"><span data-stu-id="d6951-127">**Person ID Value**</span></span><br><span data-ttu-id="d6951-128">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="d6951-128">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="d6951-129">*GUID*</span><span class="sxs-lookup"><span data-stu-id="d6951-129">*GUID*</span></span> | <span data-ttu-id="d6951-130">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d6951-130">Read-only</span></span><br><span data-ttu-id="d6951-131">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d6951-131">Required</span></span><br><span data-ttu-id="d6951-132">Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="d6951-132">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="d6951-133">A fél (személy) entitásrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="d6951-133">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="d6951-134">**Tanúsítványtípus azonosítója**</span><span class="sxs-lookup"><span data-stu-id="d6951-134">**Certificate Type ID**</span></span><br><span data-ttu-id="d6951-135">mshr_certificatetypeid</span><span class="sxs-lookup"><span data-stu-id="d6951-135">mshr_certificatetypeid</span></span><br><span data-ttu-id="d6951-136">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d6951-136">*String*</span></span> | <span data-ttu-id="d6951-137">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="d6951-137">Read/write</span></span><br><span data-ttu-id="d6951-138">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d6951-138">Required</span></span> |  <span data-ttu-id="d6951-139">A Human Resources rendszerben definiált tanúsítványtípus azonosítója.</span><span class="sxs-lookup"><span data-stu-id="d6951-139">The identifier of the certificate type defined in Human Resources.</span></span> |
| <span data-ttu-id="d6951-140">**Tanúsítványtípus azonosítójának értéke**</span><span class="sxs-lookup"><span data-stu-id="d6951-140">**Certificate Type ID Value**</span></span><br><span data-ttu-id="d6951-141">_mshr_fk_certificatetype_id_value</span><span class="sxs-lookup"><span data-stu-id="d6951-141">_mshr_fk_certificatetype_id_value</span></span><br><span data-ttu-id="d6951-142">*GUID*</span><span class="sxs-lookup"><span data-stu-id="d6951-142">*GUID*</span></span> | <span data-ttu-id="d6951-143">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d6951-143">Read-only</span></span><br><span data-ttu-id="d6951-144">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d6951-144">Required</span></span><br><span data-ttu-id="d6951-145">Idegen kulcs: mshr_hcmcertificatetypeentityid / mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="d6951-145">Foreign key: mshr_hcmcertificatetypeentityid of mshr_hcmcertificatetypeentity</span></span> | <span data-ttu-id="d6951-146">A társított entitás tanúsítványtípusának rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="d6951-146">System-generated unique identifier of the certificate type in the associated entity.</span></span> |
| <span data-ttu-id="d6951-147">**Kezdő dátum**</span><span class="sxs-lookup"><span data-stu-id="d6951-147">**Start Date**</span></span><br><span data-ttu-id="d6951-148">mshr_startdate</span><span class="sxs-lookup"><span data-stu-id="d6951-148">mshr_startdate</span></span><br><span data-ttu-id="d6951-149">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="d6951-149">*Datetime*</span></span> | <span data-ttu-id="d6951-150">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="d6951-150">Read/write</span></span><br><span data-ttu-id="d6951-151">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d6951-151">Required</span></span> | <span data-ttu-id="d6951-152">A tanúsítvány kibocsátásának dátuma.</span><span class="sxs-lookup"><span data-stu-id="d6951-152">The date at which the certificate was issued.</span></span> |
| <span data-ttu-id="d6951-153">**Záró dátum**</span><span class="sxs-lookup"><span data-stu-id="d6951-153">**End Date**</span></span><br><span data-ttu-id="d6951-154">mshr_enddate</span><span class="sxs-lookup"><span data-stu-id="d6951-154">mshr_enddate</span></span><br><span data-ttu-id="d6951-155">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="d6951-155">*Datetime*</span></span> | <span data-ttu-id="d6951-156">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="d6951-156">Read/write</span></span><br><span data-ttu-id="d6951-157">Választható</span><span class="sxs-lookup"><span data-stu-id="d6951-157">Optional</span></span> | <span data-ttu-id="d6951-158">A tanúsítvány lejáratának dátuma.</span><span class="sxs-lookup"><span data-stu-id="d6951-158">The date at which the certificate will expire.</span></span> |
| <span data-ttu-id="d6951-159">**Jegyzetek**</span><span class="sxs-lookup"><span data-stu-id="d6951-159">**Notes**</span></span><br><span data-ttu-id="d6951-160">mshr_notes</span><span class="sxs-lookup"><span data-stu-id="d6951-160">mshr_notes</span></span><br><span data-ttu-id="d6951-161">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d6951-161">*String*</span></span> | <span data-ttu-id="d6951-162">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="d6951-162">Read/write</span></span><br><span data-ttu-id="d6951-163">Választható</span><span class="sxs-lookup"><span data-stu-id="d6951-163">Optional</span></span> | <span data-ttu-id="d6951-164">A toborzási vagy felvételi vezetők által használható megjegyzések.</span><span class="sxs-lookup"><span data-stu-id="d6951-164">Notes for use by hiring managers and recruiters.</span></span> |
| <span data-ttu-id="d6951-165">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="d6951-165">**Primary Field**</span></span><br><span data-ttu-id="d6951-166">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="d6951-166">mshr_primaryfield</span></span><br><span data-ttu-id="d6951-167">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d6951-167">*String*</span></span> | <span data-ttu-id="d6951-168">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d6951-168">Read-only</span></span><br><span data-ttu-id="d6951-169">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d6951-169">Required</span></span> |  <span data-ttu-id="d6951-170">Az entitásrekord azonosítójaként használandó mező.</span><span class="sxs-lookup"><span data-stu-id="d6951-170">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="d6951-171">A fél számának, a tanúsítványtípus azonosítójának és a kezdő dátumnak a kombinációja.</span><span class="sxs-lookup"><span data-stu-id="d6951-171">Combination of party number, certificate type ID, and start date.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d6951-172">Lásd még</span><span class="sxs-lookup"><span data-stu-id="d6951-172">See also</span></span>

[<span data-ttu-id="d6951-173">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="d6951-173">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="d6951-174">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="d6951-174">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]