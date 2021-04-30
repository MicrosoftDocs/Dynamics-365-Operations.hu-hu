---
title: Bérlista dolgozói címe
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti dolgozó címe entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6d93c38b21e953446142fc32cc2a0911616ac61d
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881998"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="96334-103">Bérlista dolgozói címe</span><span class="sxs-lookup"><span data-stu-id="96334-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="96334-104">Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti dolgozó címe entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="96334-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="96334-105">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="96334-105">Properties</span></span>

| <span data-ttu-id="96334-106">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="96334-106">Property</span></span><br><span data-ttu-id="96334-107">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="96334-107">**Physical name**</span></span><br><span data-ttu-id="96334-108">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="96334-108">**_Type_**</span></span> | <span data-ttu-id="96334-109">Használat</span><span class="sxs-lookup"><span data-stu-id="96334-109">Use</span></span> | <span data-ttu-id="96334-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="96334-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="96334-111">**Város**</span><span class="sxs-lookup"><span data-stu-id="96334-111">**City**</span></span><br><span data-ttu-id="96334-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="96334-112">mshr_city</span></span><br><span data-ttu-id="96334-113">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="96334-113">*String*</span></span> | <span data-ttu-id="96334-114">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-114">Read-only</span></span><br><span data-ttu-id="96334-115">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-115">Required</span></span> | <span data-ttu-id="96334-116">A címhez megadott város.</span><span class="sxs-lookup"><span data-stu-id="96334-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="96334-117">**Személyzeti szám**</span><span class="sxs-lookup"><span data-stu-id="96334-117">**Personnel number**</span></span><br><span data-ttu-id="96334-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="96334-118">mshr_personnelnumber</span></span><br><span data-ttu-id="96334-119">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="96334-119">*String*</span></span> | <span data-ttu-id="96334-120">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-120">Read-only</span></span><br><span data-ttu-id="96334-121">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-121">Required</span></span> | <span data-ttu-id="96334-122">Az alkalmazott egyedi személyzeti száma.</span><span class="sxs-lookup"><span data-stu-id="96334-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="96334-123">**Ország régió**</span><span class="sxs-lookup"><span data-stu-id="96334-123">**Country region**</span></span><br><span data-ttu-id="96334-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="96334-124">mshr_countryregionid</span></span><br><span data-ttu-id="96334-125">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="96334-125">*String*</span></span> | <span data-ttu-id="96334-126">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-126">Read-only</span></span><br><span data-ttu-id="96334-127">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-127">Required</span></span> | <span data-ttu-id="96334-128">A címhez tartozó ország régió megadása</span><span class="sxs-lookup"><span data-stu-id="96334-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="96334-129">**Érvényesség kezdete**</span><span class="sxs-lookup"><span data-stu-id="96334-129">**Valid from**</span></span><br><span data-ttu-id="96334-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="96334-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="96334-131">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="96334-131">*Date Time Offset*</span></span> | <span data-ttu-id="96334-132">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-132">Read-only</span></span> <br><span data-ttu-id="96334-133">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-133">Required</span></span> | <span data-ttu-id="96334-134">A cím érvényességének kezdő dátuma</span><span class="sxs-lookup"><span data-stu-id="96334-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="96334-135">**A címen dolgozott**</span><span class="sxs-lookup"><span data-stu-id="96334-135">**Worked in address**</span></span><br><span data-ttu-id="96334-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="96334-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="96334-137">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-137">Read-only</span></span><br><span data-ttu-id="96334-138">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-138">Required</span></span> | <span data-ttu-id="96334-139">Azt jelzi, hogy a címen dolgozik-e az alkalmazott.</span><span class="sxs-lookup"><span data-stu-id="96334-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="96334-140">**Megye**</span><span class="sxs-lookup"><span data-stu-id="96334-140">**County**</span></span><br><span data-ttu-id="96334-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="96334-141">mshr_county</span></span><br><span data-ttu-id="96334-142">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="96334-142">*String*</span></span> | <span data-ttu-id="96334-143">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-143">Read-only</span></span><br><span data-ttu-id="96334-144">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-144">Required</span></span> | <span data-ttu-id="96334-145">A címhez megadott megye.</span><span class="sxs-lookup"><span data-stu-id="96334-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="96334-146">**Bérlista dolgozói címe azonosítója**</span><span class="sxs-lookup"><span data-stu-id="96334-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="96334-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="96334-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="96334-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="96334-148">*GUID*</span></span> | <span data-ttu-id="96334-149">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-149">Required</span></span><br><span data-ttu-id="96334-150">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="96334-150">System generated</span></span> | <span data-ttu-id="96334-151">A cím egyedi azonosítására szolgáló, rendszer által generált GUID-értéke.</span><span class="sxs-lookup"><span data-stu-id="96334-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="96334-152">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="96334-152">**Primary field**</span></span><br><span data-ttu-id="96334-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="96334-153">mshr_primaryfield</span></span><br><span data-ttu-id="96334-154">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="96334-154">*String*</span></span> | <span data-ttu-id="96334-155">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-155">Read-only</span></span><br><span data-ttu-id="96334-156">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-156">Required</span></span> |  |
| <span data-ttu-id="96334-157">**Utca**</span><span class="sxs-lookup"><span data-stu-id="96334-157">**Street**</span></span><br><span data-ttu-id="96334-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="96334-158">mshr_street</span></span><br><span data-ttu-id="96334-159">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="96334-159">*String*</span></span> | <span data-ttu-id="96334-160">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-160">Read-only</span></span><br><span data-ttu-id="96334-161">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-161">Required</span></span> | <span data-ttu-id="96334-162">A címhez megadott utca.</span><span class="sxs-lookup"><span data-stu-id="96334-162">The street defined for the address.</span></span> |
| <span data-ttu-id="96334-163">**Érvényesség vége:**</span><span class="sxs-lookup"><span data-stu-id="96334-163">**Valid to**</span></span><br><span data-ttu-id="96334-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="96334-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="96334-165">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="96334-165">*Date Time Offset*</span></span> | <span data-ttu-id="96334-166">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-166">Read-only</span></span> <br><span data-ttu-id="96334-167">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-167">Required</span></span> | <span data-ttu-id="96334-168">A cím érvényességének befejező dátuma.</span><span class="sxs-lookup"><span data-stu-id="96334-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="96334-169">**Helyazonosító**</span><span class="sxs-lookup"><span data-stu-id="96334-169">**Location ID**</span></span><br><span data-ttu-id="96334-170">mshr_locationidbr>*karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="96334-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="96334-171">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-171">Read-only</span></span> <br><span data-ttu-id="96334-172">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-172">Required</span></span> | <span data-ttu-id="96334-173">A cím azonosítója.</span><span class="sxs-lookup"><span data-stu-id="96334-173">The ID for the address.</span></span>  |
| <span data-ttu-id="96334-174">**Irányítószám**</span><span class="sxs-lookup"><span data-stu-id="96334-174">**Postal code**</span></span><br><span data-ttu-id="96334-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="96334-175">mshr_zipcode</span></span><br><span data-ttu-id="96334-176">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="96334-176">*String*</span></span> | <span data-ttu-id="96334-177">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-177">Read-only</span></span> <br><span data-ttu-id="96334-178">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-178">Required</span></span> |<span data-ttu-id="96334-179">Az alkalmazotthoz meghatározott azonosítószám.</span><span class="sxs-lookup"><span data-stu-id="96334-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="96334-180">**A címen lakott**</span><span class="sxs-lookup"><span data-stu-id="96334-180">**Lived in address**</span></span><br><span data-ttu-id="96334-181">mshr_islivedinaddressbr>*karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="96334-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="96334-182">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-182">Read-only</span></span><br><span data-ttu-id="96334-183">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-183">Required</span></span> | <span data-ttu-id="96334-184">Azt jelzi, hogy a címen lakott-e az alkalmazott.</span><span class="sxs-lookup"><span data-stu-id="96334-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="96334-185">**Állami**</span><span class="sxs-lookup"><span data-stu-id="96334-185">**State**</span></span><br><span data-ttu-id="96334-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="96334-186">mshr_state</span></span><br><span data-ttu-id="96334-187">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="96334-187">*String*</span></span> | <span data-ttu-id="96334-188">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="96334-188">Read-only</span></span><br><span data-ttu-id="96334-189">Szükséges</span><span class="sxs-lookup"><span data-stu-id="96334-189">Required</span></span> | <span data-ttu-id="96334-190">A címhez megadott állam.</span><span class="sxs-lookup"><span data-stu-id="96334-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="96334-191">Példa lekérdezésre</span><span class="sxs-lookup"><span data-stu-id="96334-191">Example query</span></span>

<span data-ttu-id="96334-192">**Kérelem**</span><span class="sxs-lookup"><span data-stu-id="96334-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="96334-193">**Válasz**</span><span class="sxs-lookup"><span data-stu-id="96334-193">**Response**</span></span>

```json
{
            "mshr_personnelnumber": "000041",
            "mshr_locationid": "000000538",
            "mshr_islivedinaddress": 200000001,
            "mshr_isworkedinaddress": 200000000,
            "mshr_countryregionid": "USA",
            "mshr_zipcode": "99025",
            "mshr_street": "6543 Cypress Ave",
            "mshr_city": "Tacoma",
            "mshr_state": "WA",
            "mshr_county": "KING",
            "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
            "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
            "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
            "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```
