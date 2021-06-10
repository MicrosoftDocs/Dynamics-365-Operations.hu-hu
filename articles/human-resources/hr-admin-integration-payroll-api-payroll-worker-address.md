---
title: Bérlista dolgozói címe
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti dolgozó címe entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3407128b0172f0e253d51bcfa23a894f981e21e2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052289"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="d5957-103">Bérlista dolgozói címe</span><span class="sxs-lookup"><span data-stu-id="d5957-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="d5957-104">Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti dolgozó címe entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="d5957-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="d5957-105">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="d5957-105">Properties</span></span>

| <span data-ttu-id="d5957-106">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="d5957-106">Property</span></span><br><span data-ttu-id="d5957-107">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="d5957-107">**Physical name**</span></span><br><span data-ttu-id="d5957-108">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="d5957-108">**_Type_**</span></span> | <span data-ttu-id="d5957-109">Használat</span><span class="sxs-lookup"><span data-stu-id="d5957-109">Use</span></span> | <span data-ttu-id="d5957-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="d5957-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="d5957-111">**Város**</span><span class="sxs-lookup"><span data-stu-id="d5957-111">**City**</span></span><br><span data-ttu-id="d5957-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="d5957-112">mshr_city</span></span><br><span data-ttu-id="d5957-113">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d5957-113">*String*</span></span> | <span data-ttu-id="d5957-114">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-114">Read-only</span></span><br><span data-ttu-id="d5957-115">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-115">Required</span></span> | <span data-ttu-id="d5957-116">A címhez megadott város.</span><span class="sxs-lookup"><span data-stu-id="d5957-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="d5957-117">**Személyzeti szám**</span><span class="sxs-lookup"><span data-stu-id="d5957-117">**Personnel number**</span></span><br><span data-ttu-id="d5957-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="d5957-118">mshr_personnelnumber</span></span><br><span data-ttu-id="d5957-119">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d5957-119">*String*</span></span> | <span data-ttu-id="d5957-120">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-120">Read-only</span></span><br><span data-ttu-id="d5957-121">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-121">Required</span></span> | <span data-ttu-id="d5957-122">Az alkalmazott egyedi személyzeti száma.</span><span class="sxs-lookup"><span data-stu-id="d5957-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="d5957-123">**Ország régió**</span><span class="sxs-lookup"><span data-stu-id="d5957-123">**Country region**</span></span><br><span data-ttu-id="d5957-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="d5957-124">mshr_countryregionid</span></span><br><span data-ttu-id="d5957-125">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d5957-125">*String*</span></span> | <span data-ttu-id="d5957-126">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-126">Read-only</span></span><br><span data-ttu-id="d5957-127">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-127">Required</span></span> | <span data-ttu-id="d5957-128">A címhez tartozó ország régió megadása</span><span class="sxs-lookup"><span data-stu-id="d5957-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="d5957-129">**Érvényesség kezdete**</span><span class="sxs-lookup"><span data-stu-id="d5957-129">**Valid from**</span></span><br><span data-ttu-id="d5957-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="d5957-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="d5957-131">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="d5957-131">*Date Time Offset*</span></span> | <span data-ttu-id="d5957-132">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-132">Read-only</span></span> <br><span data-ttu-id="d5957-133">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-133">Required</span></span> | <span data-ttu-id="d5957-134">A cím érvényességének kezdő dátuma</span><span class="sxs-lookup"><span data-stu-id="d5957-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="d5957-135">**A címen dolgozott**</span><span class="sxs-lookup"><span data-stu-id="d5957-135">**Worked in address**</span></span><br><span data-ttu-id="d5957-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="d5957-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="d5957-137">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-137">Read-only</span></span><br><span data-ttu-id="d5957-138">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-138">Required</span></span> | <span data-ttu-id="d5957-139">Azt jelzi, hogy a címen dolgozik-e az alkalmazott.</span><span class="sxs-lookup"><span data-stu-id="d5957-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="d5957-140">**Megye**</span><span class="sxs-lookup"><span data-stu-id="d5957-140">**County**</span></span><br><span data-ttu-id="d5957-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="d5957-141">mshr_county</span></span><br><span data-ttu-id="d5957-142">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d5957-142">*String*</span></span> | <span data-ttu-id="d5957-143">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-143">Read-only</span></span><br><span data-ttu-id="d5957-144">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-144">Required</span></span> | <span data-ttu-id="d5957-145">A címhez megadott megye.</span><span class="sxs-lookup"><span data-stu-id="d5957-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="d5957-146">**Bérlista dolgozói címe azonosítója**</span><span class="sxs-lookup"><span data-stu-id="d5957-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="d5957-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="d5957-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="d5957-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="d5957-148">*GUID*</span></span> | <span data-ttu-id="d5957-149">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-149">Required</span></span><br><span data-ttu-id="d5957-150">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="d5957-150">System generated</span></span> | <span data-ttu-id="d5957-151">A cím egyedi azonosítására szolgáló, rendszer által generált GUID-értéke.</span><span class="sxs-lookup"><span data-stu-id="d5957-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="d5957-152">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="d5957-152">**Primary field**</span></span><br><span data-ttu-id="d5957-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="d5957-153">mshr_primaryfield</span></span><br><span data-ttu-id="d5957-154">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d5957-154">*String*</span></span> | <span data-ttu-id="d5957-155">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-155">Read-only</span></span><br><span data-ttu-id="d5957-156">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-156">Required</span></span> |  |
| <span data-ttu-id="d5957-157">**Utca**</span><span class="sxs-lookup"><span data-stu-id="d5957-157">**Street**</span></span><br><span data-ttu-id="d5957-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="d5957-158">mshr_street</span></span><br><span data-ttu-id="d5957-159">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d5957-159">*String*</span></span> | <span data-ttu-id="d5957-160">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-160">Read-only</span></span><br><span data-ttu-id="d5957-161">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-161">Required</span></span> | <span data-ttu-id="d5957-162">A címhez megadott utca.</span><span class="sxs-lookup"><span data-stu-id="d5957-162">The street defined for the address.</span></span> |
| <span data-ttu-id="d5957-163">**Érvényesség vége:**</span><span class="sxs-lookup"><span data-stu-id="d5957-163">**Valid to**</span></span><br><span data-ttu-id="d5957-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="d5957-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="d5957-165">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="d5957-165">*Date Time Offset*</span></span> | <span data-ttu-id="d5957-166">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-166">Read-only</span></span> <br><span data-ttu-id="d5957-167">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-167">Required</span></span> | <span data-ttu-id="d5957-168">A cím érvényességének befejező dátuma.</span><span class="sxs-lookup"><span data-stu-id="d5957-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="d5957-169">**Helyazonosító**</span><span class="sxs-lookup"><span data-stu-id="d5957-169">**Location ID**</span></span><br><span data-ttu-id="d5957-170">mshr_locationidbr>*karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d5957-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="d5957-171">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-171">Read-only</span></span> <br><span data-ttu-id="d5957-172">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-172">Required</span></span> | <span data-ttu-id="d5957-173">A cím azonosítója.</span><span class="sxs-lookup"><span data-stu-id="d5957-173">The ID for the address.</span></span>  |
| <span data-ttu-id="d5957-174">**Irányítószám**</span><span class="sxs-lookup"><span data-stu-id="d5957-174">**Postal code**</span></span><br><span data-ttu-id="d5957-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="d5957-175">mshr_zipcode</span></span><br><span data-ttu-id="d5957-176">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d5957-176">*String*</span></span> | <span data-ttu-id="d5957-177">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-177">Read-only</span></span> <br><span data-ttu-id="d5957-178">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-178">Required</span></span> |<span data-ttu-id="d5957-179">Az alkalmazotthoz meghatározott azonosítószám.</span><span class="sxs-lookup"><span data-stu-id="d5957-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="d5957-180">**A címen lakott**</span><span class="sxs-lookup"><span data-stu-id="d5957-180">**Lived in address**</span></span><br><span data-ttu-id="d5957-181">mshr_islivedinaddressbr>*karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="d5957-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="d5957-182">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-182">Read-only</span></span><br><span data-ttu-id="d5957-183">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-183">Required</span></span> | <span data-ttu-id="d5957-184">Azt jelzi, hogy a címen lakott-e az alkalmazott.</span><span class="sxs-lookup"><span data-stu-id="d5957-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="d5957-185">**Állami**</span><span class="sxs-lookup"><span data-stu-id="d5957-185">**State**</span></span><br><span data-ttu-id="d5957-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="d5957-186">mshr_state</span></span><br><span data-ttu-id="d5957-187">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="d5957-187">*String*</span></span> | <span data-ttu-id="d5957-188">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="d5957-188">Read-only</span></span><br><span data-ttu-id="d5957-189">Szükséges</span><span class="sxs-lookup"><span data-stu-id="d5957-189">Required</span></span> | <span data-ttu-id="d5957-190">A címhez megadott állam.</span><span class="sxs-lookup"><span data-stu-id="d5957-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="d5957-191">Példa lekérdezésre</span><span class="sxs-lookup"><span data-stu-id="d5957-191">Example query</span></span>

<span data-ttu-id="d5957-192">**Kérelem**</span><span class="sxs-lookup"><span data-stu-id="d5957-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="d5957-193">**Válasz**</span><span class="sxs-lookup"><span data-stu-id="d5957-193">**Response**</span></span>

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
