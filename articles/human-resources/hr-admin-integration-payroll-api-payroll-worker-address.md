---
title: Bérlista dolgozói címe
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti dolgozó címe entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
author: jcart
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
ms.openlocfilehash: 964f04261ea95ee6fa2880b0905a669855f6c58a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020705"
---
# <a name="payroll-worker-address"></a><span data-ttu-id="5aa19-103">Bérlista dolgozói címe</span><span class="sxs-lookup"><span data-stu-id="5aa19-103">Payroll worker address</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="5aa19-104">Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista szerinti dolgozó címe entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="5aa19-104">This topic provides details and an example query for the Payroll worker address entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="5aa19-105">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="5aa19-105">Properties</span></span>

| <span data-ttu-id="5aa19-106">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="5aa19-106">Property</span></span><br><span data-ttu-id="5aa19-107">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="5aa19-107">**Physical name**</span></span><br><span data-ttu-id="5aa19-108">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="5aa19-108">**_Type_**</span></span> | <span data-ttu-id="5aa19-109">Használat</span><span class="sxs-lookup"><span data-stu-id="5aa19-109">Use</span></span> | <span data-ttu-id="5aa19-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="5aa19-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="5aa19-111">**Város**</span><span class="sxs-lookup"><span data-stu-id="5aa19-111">**City**</span></span><br><span data-ttu-id="5aa19-112">mshr_city</span><span class="sxs-lookup"><span data-stu-id="5aa19-112">mshr_city</span></span><br><span data-ttu-id="5aa19-113">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="5aa19-113">*String*</span></span> | <span data-ttu-id="5aa19-114">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-114">Read-only</span></span><br><span data-ttu-id="5aa19-115">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-115">Required</span></span> | <span data-ttu-id="5aa19-116">A címhez megadott város.</span><span class="sxs-lookup"><span data-stu-id="5aa19-116">The city defined for the address.</span></span>   |
| <span data-ttu-id="5aa19-117">**Személyzeti szám**</span><span class="sxs-lookup"><span data-stu-id="5aa19-117">**Personnel number**</span></span><br><span data-ttu-id="5aa19-118">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="5aa19-118">mshr_personnelnumber</span></span><br><span data-ttu-id="5aa19-119">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="5aa19-119">*String*</span></span> | <span data-ttu-id="5aa19-120">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-120">Read-only</span></span><br><span data-ttu-id="5aa19-121">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-121">Required</span></span> | <span data-ttu-id="5aa19-122">Az alkalmazott egyedi személyzeti száma.</span><span class="sxs-lookup"><span data-stu-id="5aa19-122">The employee's unique personnel number.</span></span>  |
| <span data-ttu-id="5aa19-123">**Ország régió**</span><span class="sxs-lookup"><span data-stu-id="5aa19-123">**Country region**</span></span><br><span data-ttu-id="5aa19-124">mshr_countryregionid</span><span class="sxs-lookup"><span data-stu-id="5aa19-124">mshr_countryregionid</span></span><br><span data-ttu-id="5aa19-125">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="5aa19-125">*String*</span></span> | <span data-ttu-id="5aa19-126">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-126">Read-only</span></span><br><span data-ttu-id="5aa19-127">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-127">Required</span></span> | <span data-ttu-id="5aa19-128">A címhez tartozó ország régió megadása</span><span class="sxs-lookup"><span data-stu-id="5aa19-128">The country region defined for the address</span></span>  |
| <span data-ttu-id="5aa19-129">**Érvényesség kezdete**</span><span class="sxs-lookup"><span data-stu-id="5aa19-129">**Valid from**</span></span><br><span data-ttu-id="5aa19-130">mshr_postaladdressvalidfrom</span><span class="sxs-lookup"><span data-stu-id="5aa19-130">mshr_postaladdressvalidfrom</span></span><br><span data-ttu-id="5aa19-131">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="5aa19-131">*Date Time Offset*</span></span> | <span data-ttu-id="5aa19-132">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-132">Read-only</span></span> <br><span data-ttu-id="5aa19-133">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-133">Required</span></span> | <span data-ttu-id="5aa19-134">A cím érvényességének kezdő dátuma</span><span class="sxs-lookup"><span data-stu-id="5aa19-134">The date the address is valid from.</span></span> |
| <span data-ttu-id="5aa19-135">**A címen dolgozott**</span><span class="sxs-lookup"><span data-stu-id="5aa19-135">**Worked in address**</span></span><br><span data-ttu-id="5aa19-136">mshr_isworkedinaddressbr>*Int32*</span><span class="sxs-lookup"><span data-stu-id="5aa19-136">mshr_isworkedinaddressbr>*Int32*</span></span> | <span data-ttu-id="5aa19-137">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-137">Read-only</span></span><br><span data-ttu-id="5aa19-138">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-138">Required</span></span> | <span data-ttu-id="5aa19-139">Azt jelzi, hogy a címen dolgozik-e az alkalmazott.</span><span class="sxs-lookup"><span data-stu-id="5aa19-139">Denotes if the address is where the employee works.</span></span> |
| <span data-ttu-id="5aa19-140">**Megye**</span><span class="sxs-lookup"><span data-stu-id="5aa19-140">**County**</span></span><br><span data-ttu-id="5aa19-141">mshr_county</span><span class="sxs-lookup"><span data-stu-id="5aa19-141">mshr_county</span></span><br><span data-ttu-id="5aa19-142">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="5aa19-142">*String*</span></span> | <span data-ttu-id="5aa19-143">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-143">Read-only</span></span><br><span data-ttu-id="5aa19-144">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-144">Required</span></span> | <span data-ttu-id="5aa19-145">A címhez megadott megye.</span><span class="sxs-lookup"><span data-stu-id="5aa19-145">The county defined for the address.</span></span>  |
| <span data-ttu-id="5aa19-146">**Bérlista dolgozói címe azonosítója**</span><span class="sxs-lookup"><span data-stu-id="5aa19-146">**Payroll worker address ID**</span></span><br><span data-ttu-id="5aa19-147">mshr_payrollworkeraddressentityid</span><span class="sxs-lookup"><span data-stu-id="5aa19-147">mshr_payrollworkeraddressentityid</span></span><br><span data-ttu-id="5aa19-148">*GUID*</span><span class="sxs-lookup"><span data-stu-id="5aa19-148">*GUID*</span></span> | <span data-ttu-id="5aa19-149">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-149">Required</span></span><br><span data-ttu-id="5aa19-150">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="5aa19-150">System generated</span></span> | <span data-ttu-id="5aa19-151">A cím egyedi azonosítására szolgáló, rendszer által generált GUID-értéke.</span><span class="sxs-lookup"><span data-stu-id="5aa19-151">A system-generated GUID value to uniquely identify the address.</span></span>  |
| <span data-ttu-id="5aa19-152">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="5aa19-152">**Primary field**</span></span><br><span data-ttu-id="5aa19-153">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="5aa19-153">mshr_primaryfield</span></span><br><span data-ttu-id="5aa19-154">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="5aa19-154">*String*</span></span> | <span data-ttu-id="5aa19-155">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-155">Read-only</span></span><br><span data-ttu-id="5aa19-156">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-156">Required</span></span> |  |
| <span data-ttu-id="5aa19-157">**Utca**</span><span class="sxs-lookup"><span data-stu-id="5aa19-157">**Street**</span></span><br><span data-ttu-id="5aa19-158">mshr_street</span><span class="sxs-lookup"><span data-stu-id="5aa19-158">mshr_street</span></span><br><span data-ttu-id="5aa19-159">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="5aa19-159">*String*</span></span> | <span data-ttu-id="5aa19-160">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-160">Read-only</span></span><br><span data-ttu-id="5aa19-161">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-161">Required</span></span> | <span data-ttu-id="5aa19-162">A címhez megadott utca.</span><span class="sxs-lookup"><span data-stu-id="5aa19-162">The street defined for the address.</span></span> |
| <span data-ttu-id="5aa19-163">**Érvényesség vége:**</span><span class="sxs-lookup"><span data-stu-id="5aa19-163">**Valid to**</span></span><br><span data-ttu-id="5aa19-164">mshr_postaladdressvalidto</span><span class="sxs-lookup"><span data-stu-id="5aa19-164">mshr_postaladdressvalidto</span></span><br><span data-ttu-id="5aa19-165">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="5aa19-165">*Date Time Offset*</span></span> | <span data-ttu-id="5aa19-166">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-166">Read-only</span></span> <br><span data-ttu-id="5aa19-167">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-167">Required</span></span> | <span data-ttu-id="5aa19-168">A cím érvényességének befejező dátuma.</span><span class="sxs-lookup"><span data-stu-id="5aa19-168">The date the address is valid to.</span></span>  |
| <span data-ttu-id="5aa19-169">**Helyazonosító**</span><span class="sxs-lookup"><span data-stu-id="5aa19-169">**Location ID**</span></span><br><span data-ttu-id="5aa19-170">mshr_locationidbr>*karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="5aa19-170">mshr_locationidbr>*String*</span></span> | <span data-ttu-id="5aa19-171">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-171">Read-only</span></span> <br><span data-ttu-id="5aa19-172">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-172">Required</span></span> | <span data-ttu-id="5aa19-173">A cím azonosítója.</span><span class="sxs-lookup"><span data-stu-id="5aa19-173">The ID for the address.</span></span>  |
| <span data-ttu-id="5aa19-174">**Irányítószám**</span><span class="sxs-lookup"><span data-stu-id="5aa19-174">**Postal code**</span></span><br><span data-ttu-id="5aa19-175">mshr_zipcode</span><span class="sxs-lookup"><span data-stu-id="5aa19-175">mshr_zipcode</span></span><br><span data-ttu-id="5aa19-176">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="5aa19-176">*String*</span></span> | <span data-ttu-id="5aa19-177">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-177">Read-only</span></span> <br><span data-ttu-id="5aa19-178">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-178">Required</span></span> |<span data-ttu-id="5aa19-179">Az alkalmazotthoz meghatározott azonosítószám.</span><span class="sxs-lookup"><span data-stu-id="5aa19-179">The identification number defined for the employee.</span></span>  |
| <span data-ttu-id="5aa19-180">**A címen lakott**</span><span class="sxs-lookup"><span data-stu-id="5aa19-180">**Lived in address**</span></span><br><span data-ttu-id="5aa19-181">mshr_islivedinaddressbr>*karakterlánc*</span><span class="sxs-lookup"><span data-stu-id="5aa19-181">mshr_islivedinaddressbr>*String*</span></span> | <span data-ttu-id="5aa19-182">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-182">Read-only</span></span><br><span data-ttu-id="5aa19-183">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-183">Required</span></span> | <span data-ttu-id="5aa19-184">Azt jelzi, hogy a címen lakott-e az alkalmazott.</span><span class="sxs-lookup"><span data-stu-id="5aa19-184">Denotes if the address is where the employee lives.</span></span> |
| <span data-ttu-id="5aa19-185">**Állami**</span><span class="sxs-lookup"><span data-stu-id="5aa19-185">**State**</span></span><br><span data-ttu-id="5aa19-186">mshr_state</span><span class="sxs-lookup"><span data-stu-id="5aa19-186">mshr_state</span></span><br><span data-ttu-id="5aa19-187">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="5aa19-187">*String*</span></span> | <span data-ttu-id="5aa19-188">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="5aa19-188">Read-only</span></span><br><span data-ttu-id="5aa19-189">Szükséges</span><span class="sxs-lookup"><span data-stu-id="5aa19-189">Required</span></span> | <span data-ttu-id="5aa19-190">A címhez megadott állam.</span><span class="sxs-lookup"><span data-stu-id="5aa19-190">The state defined for the address.</span></span>  |

## <a name="example-query"></a><span data-ttu-id="5aa19-191">Példa lekérdezésre</span><span class="sxs-lookup"><span data-stu-id="5aa19-191">Example query</span></span>

<span data-ttu-id="5aa19-192">**Kérelem**</span><span class="sxs-lookup"><span data-stu-id="5aa19-192">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="5aa19-193">**Válasz**</span><span class="sxs-lookup"><span data-stu-id="5aa19-193">**Response**</span></span>

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
