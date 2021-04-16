---
title: Személy szűrési adatai
description: Ez a témakör a Személy szűrése entitást mutatja be a Dynamics 365 Human Resources rendszerben.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4bc32eb948f4a4966a927b0907b8d499486e43dc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798033"
---
# <a name="person-screening"></a><span data-ttu-id="f6584-103">Személy szűrési adatai</span><span class="sxs-lookup"><span data-stu-id="f6584-103">Person screening</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f6584-104">Ez a témakör a Személy szűrése entitást mutatja be a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="f6584-104">This topic describes the Person screening entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="f6584-105">Fizikai név: mshr_hcmpersonscreeningentity</span><span class="sxs-lookup"><span data-stu-id="f6584-105">Physical name: mshr_hcmpersonscreeningentity</span></span>

## <a name="description"></a><span data-ttu-id="f6584-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="f6584-106">Description</span></span>

<span data-ttu-id="f6584-107">Ez az entitás olyan szűréseket ír le, amelyeken a jelölt átment vagy amelyeken át kell mennie az állás betöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="f6584-107">This entity describes screenings a candidate has passed or must pass for employment.</span></span>

## <a name="json-representation"></a><span data-ttu-id="f6584-108">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="f6584-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="f6584-109">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="f6584-109">Properties</span></span>

| <span data-ttu-id="f6584-110">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="f6584-110">Property</span></span><br><span data-ttu-id="f6584-111">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="f6584-111">**Physical name**</span></span><br><span data-ttu-id="f6584-112">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="f6584-112">**_Type_**</span></span> | <span data-ttu-id="f6584-113">Használat</span><span class="sxs-lookup"><span data-stu-id="f6584-113">Use</span></span> | <span data-ttu-id="f6584-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="f6584-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f6584-115">**Személy szűrése entitás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="f6584-115">**Person Screening Entity ID**</span></span><br><span data-ttu-id="f6584-116">mshr_hcmpersonscreeningentityid</span><span class="sxs-lookup"><span data-stu-id="f6584-116">mshr_hcmpersonscreeningentityid</span></span><br><span data-ttu-id="f6584-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f6584-117">*GUID*</span></span> | <span data-ttu-id="f6584-118">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="f6584-118">Read-only</span></span><br><span data-ttu-id="f6584-119">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f6584-119">Required</span></span><br><span data-ttu-id="f6584-120">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="f6584-120">System-generated</span></span> | <span data-ttu-id="f6584-121">A személy szűrési rekordjának egyedi elsődleges azonosítója.</span><span class="sxs-lookup"><span data-stu-id="f6584-121">Unique primary identifier for the person screening record.</span></span> |
| <span data-ttu-id="f6584-122">**Fél száma**</span><span class="sxs-lookup"><span data-stu-id="f6584-122">**Party Number**</span></span><br><span data-ttu-id="f6584-123">mshr_partynumber</span><span class="sxs-lookup"><span data-stu-id="f6584-123">mshr_partynumber</span></span><br><span data-ttu-id="f6584-124">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="f6584-124">*String*</span></span> | <span data-ttu-id="f6584-125">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f6584-125">Read/write</span></span><br><span data-ttu-id="f6584-126">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f6584-126">Required</span></span> | <span data-ttu-id="f6584-127">A jelölthöz társított fél (személy) száma.</span><span class="sxs-lookup"><span data-stu-id="f6584-127">The party (person) number associated with the candidate.</span></span> |
| <span data-ttu-id="f6584-128">**Személyazonosító értéke**</span><span class="sxs-lookup"><span data-stu-id="f6584-128">**Person ID Value**</span></span><br><span data-ttu-id="f6584-129">_mshr_fk_person_id_value</span><span class="sxs-lookup"><span data-stu-id="f6584-129">_mshr_fk_person_id_value</span></span><br><span data-ttu-id="f6584-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f6584-130">*GUID*</span></span> | <span data-ttu-id="f6584-131">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="f6584-131">Read-only</span></span><br><span data-ttu-id="f6584-132">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f6584-132">Required</span></span><br><span data-ttu-id="f6584-133">Idegen kulcs: mshr_dirpersonentityid / mshr_dirpersonentity</span><span class="sxs-lookup"><span data-stu-id="f6584-133">Foreign key: mshr_dirpersonentityid of mshr_dirpersonentity</span></span> | <span data-ttu-id="f6584-134">A fél (személy) entitásrekord rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="f6584-134">The system-generated identifier of the party (person) entity record.</span></span> |
| <span data-ttu-id="f6584-135">**Szűréstípus azonosítója**</span><span class="sxs-lookup"><span data-stu-id="f6584-135">**Screening Type ID**</span></span><br><span data-ttu-id="f6584-136">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="f6584-136">mshr_screeningtypeid</span></span><br><span data-ttu-id="f6584-137">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="f6584-137">*String*</span></span> | <span data-ttu-id="f6584-138">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f6584-138">Read/write</span></span><br><span data-ttu-id="f6584-139">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f6584-139">Required</span></span><br><span data-ttu-id="f6584-140">Idegen kulcs: ScreeningType</span><span class="sxs-lookup"><span data-stu-id="f6584-140">Foreign key: ScreeningType</span></span> | <span data-ttu-id="f6584-141">A Human Resources rendszerben definiált szűréstípus azonosítója.</span><span class="sxs-lookup"><span data-stu-id="f6584-141">The identifier of the screening type defined in Human Resources.</span></span> |
| <span data-ttu-id="f6584-142">**Szűréstípus azonosítójának értéke**</span><span class="sxs-lookup"><span data-stu-id="f6584-142">**Screening Type ID Value**</span></span><br><span data-ttu-id="f6584-143">_mshr_fk_screeningtype_id_value</span><span class="sxs-lookup"><span data-stu-id="f6584-143">_mshr_fk_screeningtype_id_value</span></span><br><span data-ttu-id="f6584-144">*GUID*</span><span class="sxs-lookup"><span data-stu-id="f6584-144">*GUID*</span></span> | <span data-ttu-id="f6584-145">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="f6584-145">Read-only</span></span><br><span data-ttu-id="f6584-146">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f6584-146">Required</span></span><br><span data-ttu-id="f6584-147">Idegen kulcs: mshr_hcmscreeningtypeentityid / mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="f6584-147">Foreign key: mshr_hcmscreeningtypeentityid of mshr_hcmscreeningtypeentity</span></span> | <span data-ttu-id="f6584-148">A társított entitás szűréstípusrekordjának rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="f6584-148">System-generated identifier for the screening type record in the associated entity.</span></span> |
| <span data-ttu-id="f6584-149">**A következőig szükséges:**</span><span class="sxs-lookup"><span data-stu-id="f6584-149">**Required By**</span></span><br><span data-ttu-id="f6584-150">mshr_requiredby</span><span class="sxs-lookup"><span data-stu-id="f6584-150">mshr_requiredby</span></span><br><span data-ttu-id="f6584-151">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="f6584-151">*Datetime*</span></span> | <span data-ttu-id="f6584-152">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f6584-152">Read/write</span></span><br><span data-ttu-id="f6584-153">Választható</span><span class="sxs-lookup"><span data-stu-id="f6584-153">Optional</span></span> | <span data-ttu-id="f6584-154">Az a dátum, amikorra a szűrést el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="f6584-154">The date by which the screening is required to be completed.</span></span> |
| <span data-ttu-id="f6584-155">**Állapot**</span><span class="sxs-lookup"><span data-stu-id="f6584-155">**Status**</span></span><br><span data-ttu-id="f6584-156">mshr_status</span><span class="sxs-lookup"><span data-stu-id="f6584-156">mshr_status</span></span><br><span data-ttu-id="f6584-157">*mshr_hcmcompletionstatus beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="f6584-157">*mshr_hcmcompletionstatus option set*</span></span><br><span data-ttu-id="f6584-158">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f6584-158">Read/write</span></span><br><span data-ttu-id="f6584-159">Szükséges</span><span class="sxs-lookup"><span data-stu-id="f6584-159">Required</span></span> | <span data-ttu-id="f6584-160">Megadja a jelölt állapotát a szűréshez.</span><span class="sxs-lookup"><span data-stu-id="f6584-160">Provides the candidate’s status for the screening.</span></span> |
| <span data-ttu-id="f6584-161">**Befejezés dátuma**</span><span class="sxs-lookup"><span data-stu-id="f6584-161">**Completed Date**</span></span><br><span data-ttu-id="f6584-162">mshr_completeddate</span><span class="sxs-lookup"><span data-stu-id="f6584-162">mshr_completeddate</span></span><br><span data-ttu-id="f6584-163">*Datetime*</span><span class="sxs-lookup"><span data-stu-id="f6584-163">*Datetime*</span></span> | <span data-ttu-id="f6584-164">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f6584-164">Read/write</span></span><br><span data-ttu-id="f6584-165">Választható</span><span class="sxs-lookup"><span data-stu-id="f6584-165">Optional</span></span> | <span data-ttu-id="f6584-166">A szűrés befejezésének dátuma.</span><span class="sxs-lookup"><span data-stu-id="f6584-166">The date the screening was completed.</span></span> |
| <span data-ttu-id="f6584-167">**Jegyzetek**</span><span class="sxs-lookup"><span data-stu-id="f6584-167">**Notes**</span></span><br><span data-ttu-id="f6584-168">mshr_note</span><span class="sxs-lookup"><span data-stu-id="f6584-168">mshr_note</span></span><br><span data-ttu-id="f6584-169">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="f6584-169">*String*</span></span> | <span data-ttu-id="f6584-170">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="f6584-170">Read/write</span></span><br><span data-ttu-id="f6584-171">Választható</span><span class="sxs-lookup"><span data-stu-id="f6584-171">Optional</span></span> | <span data-ttu-id="f6584-172">A toborzási vagy felvételi vezetők által használható megjegyzések.</span><span class="sxs-lookup"><span data-stu-id="f6584-172">Notes for use by hiring managers and recruiters.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f6584-173">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f6584-173">See also</span></span>

[<span data-ttu-id="f6584-174">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="f6584-174">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="f6584-175">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="f6584-175">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]