---
title: Személy szűrési adatai
description: Ez a témakör a Személy szűrése entitást mutatja be a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: d76bb57d85ee16f4faa0bb9cfec77047feb7df5f
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125377"
---
# <a name="person-screening"></a><span data-ttu-id="9735d-103">Személy szűrési adatai</span><span class="sxs-lookup"><span data-stu-id="9735d-103">Person screening</span></span>

<span data-ttu-id="9735d-104">Ez a témakör a Személy szűrése entitást mutatja be a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="9735d-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="9735d-105">Fizikai név: mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="9735d-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="9735d-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="9735d-106">Description</span></span>

<span data-ttu-id="9735d-107">Ez az entitás olyan szűréseket ír le, amelyeken a jelölt átment vagy amelyeken át kell mennie az állás betöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="9735d-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="9735d-108">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="9735d-108">JSON representation</span></span>

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a><span data-ttu-id="9735d-109">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="9735d-109">Properties</span></span>

| <span data-ttu-id="9735d-110">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="9735d-110">Property</span></span><br><span data-ttu-id="9735d-111">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="9735d-111">**Physical name**</span></span><br><span data-ttu-id="9735d-112">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="9735d-112">**_Type_**</span></span> | <span data-ttu-id="9735d-113">Használat</span><span class="sxs-lookup"><span data-stu-id="9735d-113">Use</span></span> | <span data-ttu-id="9735d-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="9735d-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="9735d-115">**Személy szűrése entitás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="9735d-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="9735d-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="9735d-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="9735d-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="9735d-117">*GUID*</span></span> | <span data-ttu-id="9735d-118">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="9735d-118">Read-only</span></span><br><span data-ttu-id="9735d-119">Szükséges</span><span class="sxs-lookup"><span data-stu-id="9735d-119">Required</span></span><br><span data-ttu-id="9735d-120">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="9735d-120">System-generated</span></span> | <span data-ttu-id="9735d-121">A személy szűrési rekordjának egyedi elsődleges azonosítója.</span><span class="sxs-lookup"><span data-stu-id="9735d-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="9735d-122">**Fél száma**</span><span class="sxs-lookup"><span data-stu-id="9735d-122">**Party Number**</span></span><br><span data-ttu-id="9735d-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="9735d-123">mshr_partynumber</span></span><br><span data-ttu-id="9735d-124">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="9735d-124">*String*</span></span> | <span data-ttu-id="9735d-125">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="9735d-125">Read/write</span></span><br><span data-ttu-id="9735d-126">Szükséges</span><span class="sxs-lookup"><span data-stu-id="9735d-126">Required</span></span> | <span data-ttu-id="9735d-127">A jelölthöz társított fél (személy) száma.</span><span class="sxs-lookup"><span data-stu-id="9735d-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="9735d-128">**Személyazonosító értéke**</span><span class="sxs-lookup"><span data-stu-id="9735d-128">**Person ID Value**</span></span><br><span data-ttu-id="9735d-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="9735d-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="9735d-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="9735d-130">*GUID*</span></span> | <span data-ttu-id="9735d-131">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="9735d-131">Read-only</span></span><br><span data-ttu-id="9735d-132">Szükséges</span><span class="sxs-lookup"><span data-stu-id="9735d-132">Required</span></span><br><span data-ttu-id="9735d-133">Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="9735d-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="9735d-134">A fél (személy) entitásrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="9735d-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="9735d-135">**Szűréstípus azonosítója**</span><span class="sxs-lookup"><span data-stu-id="9735d-135">**Screening Type ID**</span></span><br><span data-ttu-id="9735d-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="9735d-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="9735d-137">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="9735d-137">*String*</span></span> | <span data-ttu-id="9735d-138">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="9735d-138">Read/write</span></span><br><span data-ttu-id="9735d-139">Szükséges</span><span class="sxs-lookup"><span data-stu-id="9735d-139">Required</span></span><br><span data-ttu-id="9735d-140">Idegen kulcs: ScreeningType</span><span class="sxs-lookup"><span data-stu-id="9735d-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="9735d-141">A Human Resources rendszerben definiált szűréstípus azonosítója.</span><span class="sxs-lookup"><span data-stu-id="9735d-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="9735d-142">**Szűréstípus azonosítójának értéke**</span><span class="sxs-lookup"><span data-stu-id="9735d-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="9735d-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="9735d-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="9735d-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="9735d-144">*GUID*</span></span> | <span data-ttu-id="9735d-145">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="9735d-145">Read-only</span></span><br><span data-ttu-id="9735d-146">Szükséges</span><span class="sxs-lookup"><span data-stu-id="9735d-146">Required</span></span><br><span data-ttu-id="9735d-147">Idegen kulcs: mshr_hcmscreeningtypeentityid / mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="9735d-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="9735d-148">A társított entitás szűréstípusrekordjának rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="9735d-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="9735d-149">**A következőig szükséges:**</span><span class="sxs-lookup"><span data-stu-id="9735d-149">**Required By**</span></span><br><span data-ttu-id="9735d-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="9735d-150">mshr_requiredby</span></span><br><span data-ttu-id="9735d-151">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="9735d-151">*Datetime*</span></span> | <span data-ttu-id="9735d-152">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="9735d-152">Read/write</span></span><br><span data-ttu-id="9735d-153">Választható</span><span class="sxs-lookup"><span data-stu-id="9735d-153">Optional</span></span> | <span data-ttu-id="9735d-154">Az a dátum, amikorra a szűrést el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="9735d-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="9735d-155">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="9735d-155">**Status**</span></span><br><span data-ttu-id="9735d-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="9735d-156">mshr_status</span></span><br><span data-ttu-id="9735d-157">*mshr_hcmcompletionstatus beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="9735d-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="9735d-158">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="9735d-158">Read/write</span></span><br><span data-ttu-id="9735d-159">Szükséges</span><span class="sxs-lookup"><span data-stu-id="9735d-159">Required</span></span> | <span data-ttu-id="9735d-160">Megadja a jelölt állapotát a szűréshez.</span><span class="sxs-lookup"><span data-stu-id="9735d-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="9735d-161">**Befejezés dátuma**</span><span class="sxs-lookup"><span data-stu-id="9735d-161">**Completed Date**</span></span><br><span data-ttu-id="9735d-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="9735d-162">mshr_completeddate</span></span><br><span data-ttu-id="9735d-163">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="9735d-163">*Datetime*</span></span> | <span data-ttu-id="9735d-164">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="9735d-164">Read/write</span></span><br><span data-ttu-id="9735d-165">Választható</span><span class="sxs-lookup"><span data-stu-id="9735d-165">Optional</span></span> | <span data-ttu-id="9735d-166">A szűrés befejezésének dátuma.</span><span class="sxs-lookup"><span data-stu-id="9735d-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="9735d-167">**Jegyzetek**</span><span class="sxs-lookup"><span data-stu-id="9735d-167">**Notes**</span></span><br><span data-ttu-id="9735d-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="9735d-168">mshr_note</span></span><br><span data-ttu-id="9735d-169">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="9735d-169">*String*</span></span> | <span data-ttu-id="9735d-170">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="9735d-170">Read/write</span></span><br><span data-ttu-id="9735d-171">Választható</span><span class="sxs-lookup"><span data-stu-id="9735d-171">Optional</span></span> | <span data-ttu-id="9735d-172">A toborzási vagy felvételi vezetők által használható megjegyzések.</span><span class="sxs-lookup"><span data-stu-id="9735d-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9735d-173">Lásd még</span><span class="sxs-lookup"><span data-stu-id="9735d-173">See also</span></span>

[<span data-ttu-id="9735d-174">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="9735d-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="9735d-175">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="9735d-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

