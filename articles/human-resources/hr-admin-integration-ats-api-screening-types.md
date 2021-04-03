---
title: Szűréstípusok
description: Ez a témakör a Szűréstípusok entitást mutatja be a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: d3a45d802ab6b574338a09e77d432357cb9df507
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465918"
---
# <a name="screening-types"></a><span data-ttu-id="ed309-103">Szűréstípusok</span><span class="sxs-lookup"><span data-stu-id="ed309-103">Screening types</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ed309-104">Ez a témakör a Szűréstípusok entitást mutatja be a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="ed309-104">This topic describes the Screening types entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="ed309-105">Fizikai név: mshr_hcmscreeningtypeentity</span><span class="sxs-lookup"><span data-stu-id="ed309-105">Physical name: mshr_hcmscreeningtypeentity</span></span>

## <a name="description"></a><span data-ttu-id="ed309-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="ed309-106">Description</span></span>

<span data-ttu-id="ed309-107">Ez az entitás leírja a vállalat által a foglalkoztatás előtti és a folyamatban lévő alkalmazotti szűrési folyamatokhoz beállított szűréstípusokat.</span><span class="sxs-lookup"><span data-stu-id="ed309-107">This entity describes the screening types set up by the company for pre-employment and ongoing employee screening processes.</span></span>

## <a name="json-representation"></a><span data-ttu-id="ed309-108">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="ed309-108">JSON representation</span></span>

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

## <a name="properties"></a><span data-ttu-id="ed309-109">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="ed309-109">Properties</span></span>

| <span data-ttu-id="ed309-110">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="ed309-110">Property</span></span><br><span data-ttu-id="ed309-111">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="ed309-111">**Physical name**</span></span><br><span data-ttu-id="ed309-112">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="ed309-112">**_Type_**</span></span> | <span data-ttu-id="ed309-113">Használat</span><span class="sxs-lookup"><span data-stu-id="ed309-113">Use</span></span> | <span data-ttu-id="ed309-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="ed309-114">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="ed309-115">**Szűréstípus entitás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="ed309-115">**Screening Type Entity ID**</span></span><br><span data-ttu-id="ed309-116">mshr_hcmscreeningtypeentityid</span><span class="sxs-lookup"><span data-stu-id="ed309-116">mshr_hcmscreeningtypeentityid</span></span><br><span data-ttu-id="ed309-117">*GUID*</span><span class="sxs-lookup"><span data-stu-id="ed309-117">*GUID*</span></span> | <span data-ttu-id="ed309-118">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="ed309-118">Read-only</span></span><br><span data-ttu-id="ed309-119">Szükséges</span><span class="sxs-lookup"><span data-stu-id="ed309-119">Required</span></span><br><span data-ttu-id="ed309-120">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="ed309-120">System-generated</span></span> | <span data-ttu-id="ed309-121">A szűréstípus rekordjának egyedi elsődleges azonosítója.</span><span class="sxs-lookup"><span data-stu-id="ed309-121">Unique primary identifier for the screening type record.</span></span> |
| <span data-ttu-id="ed309-122">**Szűréstípus azonosítója**</span><span class="sxs-lookup"><span data-stu-id="ed309-122">**Screening Type ID**</span></span><br><span data-ttu-id="ed309-123">mshr_screeningtypeid</span><span class="sxs-lookup"><span data-stu-id="ed309-123">mshr_screeningtypeid</span></span><br><span data-ttu-id="ed309-124">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="ed309-124">*String*</span></span> | <span data-ttu-id="ed309-125">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="ed309-125">Read/write</span></span><br><span data-ttu-id="ed309-126">Szükséges</span><span class="sxs-lookup"><span data-stu-id="ed309-126">Required</span></span> | <span data-ttu-id="ed309-127">A szűréstípus felhasználó által meghatározott egyedi azonosítója.</span><span class="sxs-lookup"><span data-stu-id="ed309-127">User-defined unique identifier for the screening type.</span></span> |
| <span data-ttu-id="ed309-128">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="ed309-128">**Description**</span></span><br><span data-ttu-id="ed309-129">mshr_description</span><span class="sxs-lookup"><span data-stu-id="ed309-129">mshr_description</span></span><br><span data-ttu-id="ed309-130">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="ed309-130">*String*</span></span> | <span data-ttu-id="ed309-131">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="ed309-131">Read/write</span></span><br><span data-ttu-id="ed309-132">Szükséges</span><span class="sxs-lookup"><span data-stu-id="ed309-132">Required</span></span> | <span data-ttu-id="ed309-133">A szűrési típus leírása.</span><span class="sxs-lookup"><span data-stu-id="ed309-133">The description of the screening type.</span></span> |
| <span data-ttu-id="ed309-134">**Gyakoriság egysége**</span><span class="sxs-lookup"><span data-stu-id="ed309-134">**Frequency Unit**</span></span><br><span data-ttu-id="ed309-135">mshr_frequencyunit</span><span class="sxs-lookup"><span data-stu-id="ed309-135">mshr_frequencyunit</span></span><br><span data-ttu-id="ed309-136">*mshr_hcmfrequencyunit beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="ed309-136">*mshr_hcmfrequencyunit option set*</span></span> | <span data-ttu-id="ed309-137">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="ed309-137">Read/write</span></span><br><span data-ttu-id="ed309-138">Szükséges</span><span class="sxs-lookup"><span data-stu-id="ed309-138">Required</span></span> | <span data-ttu-id="ed309-139">Leírja, hogy milyen gyakorisággal kell végrehajtani a szűrést a hozzárendelt személy esetében.</span><span class="sxs-lookup"><span data-stu-id="ed309-139">Describes the frequency with which the screening must be completed for the assigned person.</span></span> |
| <span data-ttu-id="ed309-140">**Létrehozás alapja**</span><span class="sxs-lookup"><span data-stu-id="ed309-140">**Generate From**</span></span><br><span data-ttu-id="ed309-141">mshr_generatefrom</span><span class="sxs-lookup"><span data-stu-id="ed309-141">mshr_generatefrom</span></span><br><span data-ttu-id="ed309-142">*mshr_hcmfrequencygeneratefrom beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="ed309-142">*mshr_hcmfrequencygeneratefrom option set*</span></span> | <span data-ttu-id="ed309-143">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="ed309-143">Read-write</span></span><br><span data-ttu-id="ed309-144">Szükséges</span><span class="sxs-lookup"><span data-stu-id="ed309-144">Required</span></span> | <span data-ttu-id="ed309-145">Ha a Gyakoriság értéke nem Csak egyszeri, akkor a GenerateFrom érték határozza meg azt a dátumot, amelytől ki kell számítani a következő szűrési eseményt.</span><span class="sxs-lookup"><span data-stu-id="ed309-145">If the Frequency value is any value other than “One-time only”, the GenerateFrom value determines the date from which to calculate the next screening event.</span></span> |
| <span data-ttu-id="ed309-146">**Gyakorisági intervallum**</span><span class="sxs-lookup"><span data-stu-id="ed309-146">**Frequency Interval**</span></span><br><span data-ttu-id="ed309-147">mshr_frequencyinterval</span><span class="sxs-lookup"><span data-stu-id="ed309-147">mshr_frequencyinterval</span></span><br><span data-ttu-id="ed309-148">*Egész*</span><span class="sxs-lookup"><span data-stu-id="ed309-148">*Integer*</span></span> | <span data-ttu-id="ed309-149">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="ed309-149">Read-write</span></span><br><span data-ttu-id="ed309-150">Szükséges</span><span class="sxs-lookup"><span data-stu-id="ed309-150">Required</span></span> | <span data-ttu-id="ed309-151">Ha a Gyakoriság értéke nem Csak egyszeri, meg kell határoznia egy intervallumot az egyes szűrési események közötti időegységekre.</span><span class="sxs-lookup"><span data-stu-id="ed309-151">If the Frequency value is any value other than “One-time only”, you must define an interval for the units of time between each screening event.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ed309-152">Lásd még</span><span class="sxs-lookup"><span data-stu-id="ed309-152">See also</span></span>

[<span data-ttu-id="ed309-153">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="ed309-153">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="ed309-154">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="ed309-154">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]