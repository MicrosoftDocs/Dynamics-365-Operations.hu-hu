---
title: Tanúsítvány típusa
description: Ez a témakör a Tanúsítvány típusa entitást írja le a Dynamics 365 Human Resources rendszerhez.
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
ms.openlocfilehash: 962bccb3aaab16322d072417660ec3aac821183b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467481"
---
# <a name="certificate-type"></a><span data-ttu-id="60e3f-103">Tanúsítvány típusa</span><span class="sxs-lookup"><span data-stu-id="60e3f-103">Certificate type</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="60e3f-104">Ez a témakör a Tanúsítvány típusa entitást írja le a Dynamics 365 Human Resources rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="60e3f-104">This topic describes the Certificate type entity for Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="60e3f-105">Fizikai név: mshr_hcmcertificatetypeentity</span><span class="sxs-lookup"><span data-stu-id="60e3f-105">Physical name: mshr_hcmcertificatetypeentity</span></span>

## <a name="description"></a><span data-ttu-id="60e3f-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="60e3f-106">Description</span></span>

<span data-ttu-id="60e3f-107">Ez az entitás meghatározza a Human Resources szolgáltatásban beállított szakmai tanúsítványtípusok listáját.</span><span class="sxs-lookup"><span data-stu-id="60e3f-107">This entity defines the list of professional certificate types set up in Human Resources.</span></span> <span data-ttu-id="60e3f-108">Az entitás nem egy jogi személyhez (vállalathoz) kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="60e3f-108">The entity isn't specific to a legal entity (company).</span></span>

## <a name="json-representation"></a><span data-ttu-id="60e3f-109">JSON-ábrázolás</span><span class="sxs-lookup"><span data-stu-id="60e3f-109">JSON representation</span></span>

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a><span data-ttu-id="60e3f-110">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="60e3f-110">Properties</span></span>

| <span data-ttu-id="60e3f-111">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="60e3f-111">Property</span></span><br><span data-ttu-id="60e3f-112">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="60e3f-112">**Physical name**</span></span><br><span data-ttu-id="60e3f-113">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="60e3f-113">**_Type_**</span></span> | <span data-ttu-id="60e3f-114">Használat</span><span class="sxs-lookup"><span data-stu-id="60e3f-114">Use</span></span> | <span data-ttu-id="60e3f-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="60e3f-115">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="60e3f-116">**Tanúsítványtípus entitásazonosítója**</span><span class="sxs-lookup"><span data-stu-id="60e3f-116">**Certificate Type Entity ID**</span></span><br><span data-ttu-id="60e3f-117">mshr_hcmcertificatetypeentityid</span><span class="sxs-lookup"><span data-stu-id="60e3f-117">mshr_hcmcertificatetypeentityid</span></span><br><span data-ttu-id="60e3f-118">*GUID*</span><span class="sxs-lookup"><span data-stu-id="60e3f-118">*GUID*</span></span> | <span data-ttu-id="60e3f-119">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="60e3f-119">Read-only</span></span><br><span data-ttu-id="60e3f-120">Szükséges</span><span class="sxs-lookup"><span data-stu-id="60e3f-120">Required</span></span> 
<span data-ttu-id="60e3f-121">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="60e3f-121">System-generated</span></span> | <span data-ttu-id="60e3f-122">A tanúsítványtípus egyedi elsődleges azonosítója.</span><span class="sxs-lookup"><span data-stu-id="60e3f-122">Unique primary identifier for the certificate type.</span></span> |
| <span data-ttu-id="60e3f-123">**Tanúsítvány típusa**</span><span class="sxs-lookup"><span data-stu-id="60e3f-123">**Certificate Type**</span></span><br><span data-ttu-id="60e3f-124">mshr_certificatetype</span><span class="sxs-lookup"><span data-stu-id="60e3f-124">mshr_certificatetype</span></span><br><span data-ttu-id="60e3f-125">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="60e3f-125">*String*</span></span> | <span data-ttu-id="60e3f-126">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="60e3f-126">Read/write</span></span><br><span data-ttu-id="60e3f-127">Szükséges</span><span class="sxs-lookup"><span data-stu-id="60e3f-127">Required</span></span> | <span data-ttu-id="60e3f-128">A tanúsítványtípus egyedi, felhasználó által olvasható azonosítója.</span><span class="sxs-lookup"><span data-stu-id="60e3f-128">Unique user-readable identifier for the certificate type.</span></span> |
| <span data-ttu-id="60e3f-129">**Leírás**</span><span class="sxs-lookup"><span data-stu-id="60e3f-129">**Description**</span></span><br><span data-ttu-id="60e3f-130">mshr_description</span><span class="sxs-lookup"><span data-stu-id="60e3f-130">mshr_description</span></span><br><span data-ttu-id="60e3f-131">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="60e3f-131">*String*</span></span> | <span data-ttu-id="60e3f-132">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="60e3f-132">Read/write</span></span><br><span data-ttu-id="60e3f-133">Szükséges</span><span class="sxs-lookup"><span data-stu-id="60e3f-133">Required</span></span> | <span data-ttu-id="60e3f-134">Adja meg a tanúsítvány típusának leírását.</span><span class="sxs-lookup"><span data-stu-id="60e3f-134">Description of the certificate type.</span></span> |
| <span data-ttu-id="60e3f-135">**Megújítás szükséges**</span><span class="sxs-lookup"><span data-stu-id="60e3f-135">**Require Renewal**</span></span><br><span data-ttu-id="60e3f-136">mshr_requirerenewal</span><span class="sxs-lookup"><span data-stu-id="60e3f-136">mshr_requirerenewal</span></span><br><span data-ttu-id="60e3f-137">*mshr_noyes beállításkészlet*</span><span class="sxs-lookup"><span data-stu-id="60e3f-137">*mshr_noyes option set*</span></span> | <span data-ttu-id="60e3f-138">Olvasás/írás</span><span class="sxs-lookup"><span data-stu-id="60e3f-138">Read/write</span></span><br><span data-ttu-id="60e3f-139">Választható</span><span class="sxs-lookup"><span data-stu-id="60e3f-139">Optional</span></span> | <span data-ttu-id="60e3f-140">Azt jelzi, hogy kell-e újítást igényelni a tanúsítványhoz.</span><span class="sxs-lookup"><span data-stu-id="60e3f-140">Indicates whether renewal is required for the certificate.</span></span> |

## <a name="see-also"></a><span data-ttu-id="60e3f-141">Lásd még</span><span class="sxs-lookup"><span data-stu-id="60e3f-141">See also</span></span>

[<span data-ttu-id="60e3f-142">Pályázó követésrendszer integrációs API bevezetése</span><span class="sxs-lookup"><span data-stu-id="60e3f-142">Applicant Tracking System integration API introduction</span></span>](hr-admin-integration-ats-api-introduction.md)<br>
[<span data-ttu-id="60e3f-143">Példa lekérdezésre a Felvenni kívánt jelölt esetében</span><span class="sxs-lookup"><span data-stu-id="60e3f-143">Example query for Candidate to hire</span></span>](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]