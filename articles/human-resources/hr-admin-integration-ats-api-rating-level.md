---
title: Minősítési szint
description: Ez a témakör a Minősítési szint entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 8bbd10bcc47a928070da7cd82e6d996f71c65698
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054836"
---
# <a name="rating-level"></a><span data-ttu-id="a3e68-103">Minősítési szint</span><span class="sxs-lookup"><span data-stu-id="a3e68-103">Rating level</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="a3e68-104">Ez a témakör a Minősítési szint entitást írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="a3e68-104">This topic describes the Rating level entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="a3e68-105">Fizikai név: mshr_hcmratinglevelentity</span><span class="sxs-lookup"><span data-stu-id="a3e68-105">Physical name: mshr_hcmratinglevelentity</span></span>

## <a name="description"></a><span data-ttu-id="a3e68-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="a3e68-106">Description</span></span>

<span data-ttu-id="a3e68-107">Ez az entitás biztosítja a szakértelemhez rendelkezésre álló minősítési szinteket.</span><span class="sxs-lookup"><span data-stu-id="a3e68-107">This entity provides the available rating levels for skills.</span></span> <span data-ttu-id="a3e68-108">A minősítési szintek minden jogi személyre érvényesek.</span><span class="sxs-lookup"><span data-stu-id="a3e68-108">Rating levels apply across all legal entities.</span></span>

## <a name="json-representation"></a><span data-ttu-id="a3e68-109">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="a3e68-109">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="a3e68-110">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="a3e68-110">Properties</span></span>

| <span data-ttu-id="a3e68-111">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="a3e68-111">Property</span></span><br><span data-ttu-id="a3e68-112">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="a3e68-112">**Physical name**</span></span><br><span data-ttu-id="a3e68-113">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="a3e68-113">**_Type_**</span></span> | <span data-ttu-id="a3e68-114">Használat</span><span class="sxs-lookup"><span data-stu-id="a3e68-114">Use</span></span> | <span data-ttu-id="a3e68-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="a3e68-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="a3e68-116">**Minősítési szint entitásazonosítója**</span><span class="sxs-lookup"><span data-stu-id="a3e68-116">**Rating Level Entity ID**</span></span><br><span data-ttu-id="a3e68-117">mshr_hcmratinglevelentityid</span><span class="sxs-lookup"><span data-stu-id="a3e68-117">mshr_hcmratinglevelentityid</span></span><br><span data-ttu-id="a3e68-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a3e68-118">*GUID*</span></span> | <span data-ttu-id="a3e68-119">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="a3e68-119">Read-only</span></span><br><span data-ttu-id="a3e68-120">Szükséges</span><span class="sxs-lookup"><span data-stu-id="a3e68-120">Required</span></span><br><span data-ttu-id="a3e68-121">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="a3e68-121">System-generated</span></span> | <span data-ttu-id="a3e68-122">A szint rendszer által generált egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="a3e68-122">The system-generated unique identifier for the level.</span></span> |
| <span data-ttu-id="a3e68-123">**Minősítési szint azonosítója**</span><span class="sxs-lookup"><span data-stu-id="a3e68-123">**Rating Level ID**</span></span><br><span data-ttu-id="a3e68-124">mshr_ratinglevelid</span><span class="sxs-lookup"><span data-stu-id="a3e68-124">mshr_ratinglevelid</span></span><br><span data-ttu-id="a3e68-125">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="a3e68-125">*String*</span></span> | <span data-ttu-id="a3e68-126">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="a3e68-126">Read/write</span></span><br><span data-ttu-id="a3e68-127">Szükséges</span><span class="sxs-lookup"><span data-stu-id="a3e68-127">Required</span></span> | <span data-ttu-id="a3e68-128">A szint egyedi, felhasználó által olvasható azonosítója.</span><span class="sxs-lookup"><span data-stu-id="a3e68-128">User-readable unique identifier for the level.</span></span> |
| <span data-ttu-id="a3e68-129">**Minősítési modell azonosítója**</span><span class="sxs-lookup"><span data-stu-id="a3e68-129">**Rating Model ID**</span></span><br><span data-ttu-id="a3e68-130">mshr_ratingmodelid</span><span class="sxs-lookup"><span data-stu-id="a3e68-130">mshr_ratingmodelid</span></span><br><span data-ttu-id="a3e68-131">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="a3e68-131">*String*</span></span> | <span data-ttu-id="a3e68-132">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="a3e68-132">Read/write</span></span><br><span data-ttu-id="a3e68-133">Szükséges</span><span class="sxs-lookup"><span data-stu-id="a3e68-133">Required</span></span> | <span data-ttu-id="a3e68-134">Az a minősítési modell, amelyhez a minősítési szint tartozik.</span><span class="sxs-lookup"><span data-stu-id="a3e68-134">The rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="a3e68-135">**Minősítési modell entitásazonosítója**</span><span class="sxs-lookup"><span data-stu-id="a3e68-135">**Rating Model Entity ID**</span></span><br><span data-ttu-id="a3e68-136">_mshr_fk_ratingmodelentity_id_value</span><span class="sxs-lookup"><span data-stu-id="a3e68-136">_mshr_fk_ratingmodelentity_id_value</span></span><br><span data-ttu-id="a3e68-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="a3e68-137">*GUID*</span></span> | <span data-ttu-id="a3e68-138">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="a3e68-138">Read-only</span></span><br><span data-ttu-id="a3e68-139">Szükséges</span><span class="sxs-lookup"><span data-stu-id="a3e68-139">Required</span></span><br><span data-ttu-id="a3e68-140">Idegen kulcs: mshr_hcmratingmodelentityid / mshr_hcmratingmodelentity</span><span class="sxs-lookup"><span data-stu-id="a3e68-140">Foreign key: mshr_hcmratingmodelentityid of mshr_hcmratingmodelentity</span></span> | <span data-ttu-id="a3e68-141">Annak a minősítési modellnek a rendszer által generált azonosítója, amelyhez a minősítési szint tartozik.</span><span class="sxs-lookup"><span data-stu-id="a3e68-141">The system-generated identifier for the rating model to which the rating level belongs.</span></span> |
| <span data-ttu-id="a3e68-142">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="a3e68-142">**Description**</span></span><br><span data-ttu-id="a3e68-143">mshr_description</span><span class="sxs-lookup"><span data-stu-id="a3e68-143">mshr_description</span></span><br><span data-ttu-id="a3e68-144">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="a3e68-144">*String*</span></span> | <span data-ttu-id="a3e68-145">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="a3e68-145">Read/write</span></span><br><span data-ttu-id="a3e68-146">Szükséges</span><span class="sxs-lookup"><span data-stu-id="a3e68-146">Required</span></span> | <span data-ttu-id="a3e68-147">A minősítési szint leírása.</span><span class="sxs-lookup"><span data-stu-id="a3e68-147">The description of the rating level.</span></span> |
| <span data-ttu-id="a3e68-148">**Szorzó**</span><span class="sxs-lookup"><span data-stu-id="a3e68-148">**Factor**</span></span><br><span data-ttu-id="a3e68-149">mshr_factor</span><span class="sxs-lookup"><span data-stu-id="a3e68-149">mshr_factor</span></span><br><span data-ttu-id="a3e68-150">*Egész*</span><span class="sxs-lookup"><span data-stu-id="a3e68-150">*Integer*</span></span> | <span data-ttu-id="a3e68-151">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="a3e68-151">Read/write</span></span><br><span data-ttu-id="a3e68-152">Szükséges</span><span class="sxs-lookup"><span data-stu-id="a3e68-152">Required</span></span> | <span data-ttu-id="a3e68-153">A minősítési szint tényezője.</span><span class="sxs-lookup"><span data-stu-id="a3e68-153">The factor for the rating level.</span></span> <span data-ttu-id="a3e68-154">Amikor egyes elemeket különböző minősítési szintszámokkal vet össze, ezen tényező alapján normalizálhatja a pontszámokat.</span><span class="sxs-lookup"><span data-stu-id="a3e68-154">When you compare items with a different number of rating levels, the factor is used to normalize the scores.</span></span> <span data-ttu-id="a3e68-155">Az értéknek 0 és 9 közötti egész számnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a3e68-155">The value must be an integer between 0 and 9.</span></span> |
| <span data-ttu-id="a3e68-156">**Megjegyzés**</span><span class="sxs-lookup"><span data-stu-id="a3e68-156">**Note**</span></span><br><span data-ttu-id="a3e68-157">mshr_note</span><span class="sxs-lookup"><span data-stu-id="a3e68-157">mshr_note</span></span><br><span data-ttu-id="a3e68-158">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="a3e68-158">*String*</span></span> | <span data-ttu-id="a3e68-159">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="a3e68-159">Read/write</span></span><br><span data-ttu-id="a3e68-160">Választható</span><span class="sxs-lookup"><span data-stu-id="a3e68-160">Optional</span></span> | <span data-ttu-id="a3e68-161">A minősítési szinthez kapcsolódó megjegyzések.</span><span class="sxs-lookup"><span data-stu-id="a3e68-161">Any notes associated with the rating level.</span></span> |
| <span data-ttu-id="a3e68-162">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="a3e68-162">**Primary Field**</span></span><br><span data-ttu-id="a3e68-163">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="a3e68-163">mshr_primaryfield</span></span><br><span data-ttu-id="a3e68-164">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="a3e68-164">*String*</span></span> | <span data-ttu-id="a3e68-165">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="a3e68-165">Read-only</span></span><br><span data-ttu-id="a3e68-166">Szükséges</span><span class="sxs-lookup"><span data-stu-id="a3e68-166">Required</span></span> | <span data-ttu-id="a3e68-167">Az entitásrekord azonosítójaként használandó mező.</span><span class="sxs-lookup"><span data-stu-id="a3e68-167">Field to be used as an identifier of the entity record.</span></span> <span data-ttu-id="a3e68-168">A minősítési szint azonosítójának és az értékelési modell azonosítójának kombinációja.</span><span class="sxs-lookup"><span data-stu-id="a3e68-168">Combination of rating level ID and rating model ID.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a3e68-169">Lásd még</span><span class="sxs-lookup"><span data-stu-id="a3e68-169">See also</span></span>

[<span data-ttu-id="a3e68-170">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="a3e68-170">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="a3e68-171">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="a3e68-171">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]