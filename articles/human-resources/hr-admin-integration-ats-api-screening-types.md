---
title: Szűréstípusok
description: Ez a témakör a Szűréstípusok entitást mutatja be a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 361f8c866abb9d34eb3e2be7ea42626e98e34779
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805130"
---
# <a name="screening-types"></a><span data-ttu-id="1d196-103">Szűréstípusok</span><span class="sxs-lookup"><span data-stu-id="1d196-103">Screening types</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1d196-104">Ez a témakör a Szűréstípusok entitást mutatja be a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="1d196-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="1d196-105">Fizikai név: mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="1d196-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="1d196-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="1d196-106">Description</span></span>

<span data-ttu-id="1d196-107">Ez az entitás leírja a vállalat által a foglalkoztatás előtti és a folyamatban lévő alkalmazotti szűrési folyamatokhoz beállított szűréstípusokat.</span><span class="sxs-lookup"><span data-stu-id="1d196-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="1d196-108">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="1d196-108">JSON representation</span></span>

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="1d196-109">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="1d196-109">Properties</span></span>

| <span data-ttu-id="1d196-110">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="1d196-110">Property</span></span><br><span data-ttu-id="1d196-111">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="1d196-111">**Physical name**</span></span><br><span data-ttu-id="1d196-112">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="1d196-112">**_Type_**</span></span> | <span data-ttu-id="1d196-113">Használat</span><span class="sxs-lookup"><span data-stu-id="1d196-113">Use</span></span> | <span data-ttu-id="1d196-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="1d196-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="1d196-115">**Szűréstípus entitás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="1d196-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="1d196-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="1d196-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="1d196-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="1d196-117">*GUID*</span></span> | <span data-ttu-id="1d196-118">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="1d196-118">Read-only</span></span><br><span data-ttu-id="1d196-119">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1d196-119">Required</span></span><br><span data-ttu-id="1d196-120">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="1d196-120">System-generated</span></span> | <span data-ttu-id="1d196-121">A szűréstípus rekordjának egyedi elsődleges azonosítója.</span><span class="sxs-lookup"><span data-stu-id="1d196-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="1d196-122">**Szűréstípus azonosítója**</span><span class="sxs-lookup"><span data-stu-id="1d196-122">**Screening Type ID**</span></span><br><span data-ttu-id="1d196-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="1d196-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="1d196-124">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="1d196-124">*String*</span></span> | <span data-ttu-id="1d196-125">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="1d196-125">Read/write</span></span><br><span data-ttu-id="1d196-126">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1d196-126">Required</span></span> | <span data-ttu-id="1d196-127">A szűréstípus felhasználó által meghatározott egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="1d196-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="1d196-128">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="1d196-128">**Description**</span></span><br><span data-ttu-id="1d196-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="1d196-129">mshr_description</span></span><br><span data-ttu-id="1d196-130">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="1d196-130">*String*</span></span> | <span data-ttu-id="1d196-131">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="1d196-131">Read/write</span></span><br><span data-ttu-id="1d196-132">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1d196-132">Required</span></span> | <span data-ttu-id="1d196-133">A szűrési típus leírása.</span><span class="sxs-lookup"><span data-stu-id="1d196-133">The description of the screening type.</span></span> |
| <span data-ttu-id="1d196-134">**Gyakoriság egysége**</span><span class="sxs-lookup"><span data-stu-id="1d196-134">**Frequency Unit**</span></span><br><span data-ttu-id="1d196-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="1d196-135">mshr_frequencyunit</span></span><br><span data-ttu-id="1d196-136">*mshr_hcmfrequencyunit beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="1d196-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="1d196-137">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="1d196-137">Read/write</span></span><br><span data-ttu-id="1d196-138">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1d196-138">Required</span></span> | <span data-ttu-id="1d196-139">Leírja, hogy milyen gyakorisággal kell végrehajtani a szűrést a hozzárendelt személy esetében.</span><span class="sxs-lookup"><span data-stu-id="1d196-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="1d196-140">**Létrehozás alapja**</span><span class="sxs-lookup"><span data-stu-id="1d196-140">**Generate From**</span></span><br><span data-ttu-id="1d196-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="1d196-141">mshr_generatefrom</span></span><br><span data-ttu-id="1d196-142">*mshr_hcmfrequencygeneratefrom beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="1d196-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="1d196-143">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="1d196-143">Read-write</span></span><br><span data-ttu-id="1d196-144">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1d196-144">Required</span></span> | <span data-ttu-id="1d196-145">Ha a Gyakoriság értéke nem Csak egyszeri, akkor a GenerateFrom érték határozza meg azt a dátumot, amelytől ki kell számítani a következő szűrési eseményt.</span><span class="sxs-lookup"><span data-stu-id="1d196-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="1d196-146">**Gyakorisági intervallum**</span><span class="sxs-lookup"><span data-stu-id="1d196-146">**Frequency Interval**</span></span><br><span data-ttu-id="1d196-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="1d196-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="1d196-148">*Egész*</span><span class="sxs-lookup"><span data-stu-id="1d196-148">*Integer*</span></span> | <span data-ttu-id="1d196-149">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="1d196-149">Read-write</span></span><br><span data-ttu-id="1d196-150">Szükséges</span><span class="sxs-lookup"><span data-stu-id="1d196-150">Required</span></span> | <span data-ttu-id="1d196-151">Ha a Gyakoriság értéke nem Csak egyszeri, meg kell határoznia egy intervallumot az egyes szűrési események közötti időegységekre.</span><span class="sxs-lookup"><span data-stu-id="1d196-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1d196-152">Lásd még</span><span class="sxs-lookup"><span data-stu-id="1d196-152">See also</span></span>

[<span data-ttu-id="1d196-153">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="1d196-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="1d196-154">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="1d196-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]