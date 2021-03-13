---
title: Minősítési szint
description: Ez a témakör a Minősítési szint entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 1ad37c7a5b961bb03d37775168dac91e606d2b08
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125257"
---
# <a name="rating-level"></a><span data-ttu-id="1f26e-103">Minősítési szint</span><span class="sxs-lookup"><span data-stu-id="1f26e-103">Rating level</span></span>

<span data-ttu-id="1f26e-104">Ez a témakör a Minősítési szint entitást írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="1f26e-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="1f26e-105">Fizikai név: mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="1f26e-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="1f26e-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="1f26e-106">Description</span></span>

<span data-ttu-id="1f26e-107">Ez az entitás biztosítja a szakértelemhez rendelkezésre álló minősítési szinteket.</span><span class="sxs-lookup"><span data-stu-id="1f26e-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="1f26e-108">A minősítési szintek minden jogi személyre érvényesek.</span><span class="sxs-lookup"><span data-stu-id="1f26e-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="1f26e-109">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="1f26e-109">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="1f26e-110">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="1f26e-110">Properties</span></span>

| <span data-ttu-id="1f26e-111">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="1f26e-111">Property</span></span><br><span data-ttu-id="1f26e-112">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="1f26e-112">**Physical name**</span></span><br><span data-ttu-id="1f26e-113">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="1f26e-113">**_Type_**</span></span> | <span data-ttu-id="1f26e-114">Használat</span><span class="sxs-lookup"><span data-stu-id="1f26e-114">Use</span></span> | <span data-ttu-id="1f26e-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="1f26e-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1f26e-116">**Minősítési szint entitásazonosítója**</span><span class="sxs-lookup"><span data-stu-id="1f26e-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="1f26e-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="1f26e-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="1f26e-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1f26e-118">*GUID*</span></span> | <span data-ttu-id="1f26e-119">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="1f26e-119">Read-only</span></span><br><span data-ttu-id="1f26e-120">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1f26e-120">Required</span></span><br><span data-ttu-id="1f26e-121">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="1f26e-121">System-generated</span></span> | <span data-ttu-id="1f26e-122">A szint rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="1f26e-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="1f26e-123">**Minősítési szint azonosítója**</span><span class="sxs-lookup"><span data-stu-id="1f26e-123">**Rating Level ID**</span></span><br><span data-ttu-id="1f26e-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="1f26e-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="1f26e-125">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="1f26e-125">*String*</span></span> | <span data-ttu-id="1f26e-126">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="1f26e-126">Read/write</span></span><br><span data-ttu-id="1f26e-127">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1f26e-127">Required</span></span> | <span data-ttu-id="1f26e-128">A szint egyedi, felhasználó által olvasható azonosítója.</span><span class="sxs-lookup"><span data-stu-id="1f26e-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="1f26e-129">**Minősítési modell azonosítója**</span><span class="sxs-lookup"><span data-stu-id="1f26e-129">**Rating Model ID**</span></span><br><span data-ttu-id="1f26e-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="1f26e-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="1f26e-131">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="1f26e-131">*String*</span></span> | <span data-ttu-id="1f26e-132">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="1f26e-132">Read/write</span></span><br><span data-ttu-id="1f26e-133">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1f26e-133">Required</span></span> | <span data-ttu-id="1f26e-134">Az a minősítési modell, amelyhez a minősítési szint tartozik.</span><span class="sxs-lookup"><span data-stu-id="1f26e-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="1f26e-135">**Minősítési modell entitásazonosítója**</span><span class="sxs-lookup"><span data-stu-id="1f26e-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="1f26e-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="1f26e-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="1f26e-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1f26e-137">*GUID*</span></span> | <span data-ttu-id="1f26e-138">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="1f26e-138">Read-only</span></span><br><span data-ttu-id="1f26e-139">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1f26e-139">Required</span></span><br><span data-ttu-id="1f26e-140">Idegen kulcs: mshr_hcmratingmodelentityid / mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="1f26e-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="1f26e-141">Annak a minősítési modellnek a rendszer által generált azonosítója, amelyhez a minősítési szint tartozik.</span><span class="sxs-lookup"><span data-stu-id="1f26e-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="1f26e-142">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="1f26e-142">**Description**</span></span><br><span data-ttu-id="1f26e-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="1f26e-143">mshr_description</span></span><br><span data-ttu-id="1f26e-144">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="1f26e-144">*String*</span></span> | <span data-ttu-id="1f26e-145">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="1f26e-145">Read/write</span></span><br><span data-ttu-id="1f26e-146">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1f26e-146">Required</span></span> | <span data-ttu-id="1f26e-147">A minősítési szint leírása.</span><span class="sxs-lookup"><span data-stu-id="1f26e-147">The description of the rating level.</span></span> |
| <span data-ttu-id="1f26e-148">**Szorzó**</span><span class="sxs-lookup"><span data-stu-id="1f26e-148">**Factor**</span></span><br><span data-ttu-id="1f26e-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="1f26e-149">mshr_factor</span></span><br><span data-ttu-id="1f26e-150">*Egész*</span><span class="sxs-lookup"><span data-stu-id="1f26e-150">*Integer*</span></span> | <span data-ttu-id="1f26e-151">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="1f26e-151">Read/write</span></span><br><span data-ttu-id="1f26e-152">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1f26e-152">Required</span></span> | <span data-ttu-id="1f26e-153">A minősítési szint tényezője.</span><span class="sxs-lookup"><span data-stu-id="1f26e-153">The factor for the rating level.</span></span> <span data-ttu-id="1f26e-154">Amikor egyes elemeket különböző minősítési szintszámokkal vet össze, ezen tényező alapján normalizálhatja a pontszámokat.</span><span class="sxs-lookup"><span data-stu-id="1f26e-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="1f26e-155">Az értéknek 0 és 9 közötti egész számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="1f26e-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="1f26e-156">**Megjegyzés**</span><span class="sxs-lookup"><span data-stu-id="1f26e-156">**Note**</span></span><br><span data-ttu-id="1f26e-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="1f26e-157">mshr_note</span></span><br><span data-ttu-id="1f26e-158">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="1f26e-158">*String*</span></span> | <span data-ttu-id="1f26e-159">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="1f26e-159">Read/write</span></span><br><span data-ttu-id="1f26e-160">Választható</span><span class="sxs-lookup"><span data-stu-id="1f26e-160">Optional</span></span> | <span data-ttu-id="1f26e-161">A minősítési szinthez kapcsolódó megjegyzések.</span><span class="sxs-lookup"><span data-stu-id="1f26e-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="1f26e-162">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="1f26e-162">**Primary Field**</span></span><br><span data-ttu-id="1f26e-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="1f26e-163">mshr_primaryfield</span></span><br><span data-ttu-id="1f26e-164">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="1f26e-164">*String*</span></span> | <span data-ttu-id="1f26e-165">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="1f26e-165">Read-only</span></span><br><span data-ttu-id="1f26e-166">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1f26e-166">Required</span></span> | <span data-ttu-id="1f26e-167">Az entitásrekord azonosítójaként használandó mező.</span><span class="sxs-lookup"><span data-stu-id="1f26e-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="1f26e-168">A minősítési szint azonosítójának és az értékelési modell azonosítójának kombinációja.</span><span class="sxs-lookup"><span data-stu-id="1f26e-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1f26e-169">Lásd még</span><span class="sxs-lookup"><span data-stu-id="1f26e-169">See also</span></span>

[<span data-ttu-id="1f26e-170">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="1f26e-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="1f26e-171">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="1f26e-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

