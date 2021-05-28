---
title: Bérlista beosztásokra vonatkozó részletei
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérszámfejtési részletek a beosztáshoz entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 7b23ac5d11b18c77109be21afe1570755dccba20
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019322"
---
# <a name="payroll-position"></a><span data-ttu-id="3e240-103">Bérlista szerinti beosztás</span><span class="sxs-lookup"><span data-stu-id="3e240-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="3e240-104">Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérszámfejtési részletek a beosztáshoz entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="3e240-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="3e240-105">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="3e240-105">Properties</span></span>

| <span data-ttu-id="3e240-106">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="3e240-106">Property</span></span><br><span data-ttu-id="3e240-107">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="3e240-107">**Physical name**</span></span><br><span data-ttu-id="3e240-108">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="3e240-108">**_Type_**</span></span> | <span data-ttu-id="3e240-109">Használat</span><span class="sxs-lookup"><span data-stu-id="3e240-109">Use</span></span> | <span data-ttu-id="3e240-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="3e240-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="3e240-111">**Éves rendes munkaidő**</span><span class="sxs-lookup"><span data-stu-id="3e240-111">**Annual regular hours**</span></span><br><span data-ttu-id="3e240-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="3e240-112">annualregularhours</span></span><br><span data-ttu-id="3e240-113">*Decimális*</span><span class="sxs-lookup"><span data-stu-id="3e240-113">*Decimal*</span></span> | <span data-ttu-id="3e240-114">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="3e240-114">Read-only</span></span><br><span data-ttu-id="3e240-115">Szükséges</span><span class="sxs-lookup"><span data-stu-id="3e240-115">Required</span></span> | <span data-ttu-id="3e240-116">A beosztáshoz meghatározott éves rendszeres munkaidő.</span><span class="sxs-lookup"><span data-stu-id="3e240-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="3e240-117">**Bérlista szerinti beosztás részletei entitás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="3e240-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="3e240-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="3e240-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="3e240-119">*Guid*</span><span class="sxs-lookup"><span data-stu-id="3e240-119">*Guid*</span></span> | <span data-ttu-id="3e240-120">Szükséges</span><span class="sxs-lookup"><span data-stu-id="3e240-120">Required</span></span><br><span data-ttu-id="3e240-121">Rendszer által előállított.</span><span class="sxs-lookup"><span data-stu-id="3e240-121">System generated.</span></span> | <span data-ttu-id="3e240-122">A pozíció egyedi azonosítására szolgáló, rendszer által generált GUID-értéke.</span><span class="sxs-lookup"><span data-stu-id="3e240-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="3e240-123">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="3e240-123">**Primary field**</span></span><br><span data-ttu-id="3e240-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="3e240-124">mshr_primaryfield</span></span><br><span data-ttu-id="3e240-125">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="3e240-125">*String*</span></span> | <span data-ttu-id="3e240-126">Szükséges</span><span class="sxs-lookup"><span data-stu-id="3e240-126">Required</span></span><br><span data-ttu-id="3e240-127">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="3e240-127">System generated</span></span> |  |
| <span data-ttu-id="3e240-128">**Beosztáshoz tartozó feladat azonosítójának értéke**</span><span class="sxs-lookup"><span data-stu-id="3e240-128">**Position job ID value**</span></span><br><span data-ttu-id="3e240-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="3e240-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="3e240-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="3e240-130">*GUID*</span></span> | <span data-ttu-id="3e240-131">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="3e240-131">Read-only</span></span><br><span data-ttu-id="3e240-132">Szükséges</span><span class="sxs-lookup"><span data-stu-id="3e240-132">Required</span></span><br><span data-ttu-id="3e240-133">Idegen kulcs:mshr_PayrollPositionJobEntity ehhez: mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="3e240-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="3e240-134">A pozícióhoz társított beosztás azonosítója.</span><span class="sxs-lookup"><span data-stu-id="3e240-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="3e240-135">**Fix kompenzációs konstrukció azonosítójának értéke**</span><span class="sxs-lookup"><span data-stu-id="3e240-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="3e240-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="3e240-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="3e240-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="3e240-137">*GUID*</span></span> | <span data-ttu-id="3e240-138">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="3e240-138">Read-only</span></span><br><span data-ttu-id="3e240-139">Szükséges</span><span class="sxs-lookup"><span data-stu-id="3e240-139">Required</span></span><br><span data-ttu-id="3e240-140">Idegen kulcs: mshr_payrollfixedcompensationplanentity entitáshoz tartozó mshr_FixedCompPlan_id</span><span class="sxs-lookup"><span data-stu-id="3e240-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="3e240-141">A pozícióhoz társított fix kompenzációs konstrukció azonosítója.</span><span class="sxs-lookup"><span data-stu-id="3e240-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="3e240-142">**Fizetési ciklus azonsítója**</span><span class="sxs-lookup"><span data-stu-id="3e240-142">**Pay cycle ID**</span></span><br><span data-ttu-id="3e240-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="3e240-143">mshr_primaryfield</span></span><br><span data-ttu-id="3e240-144">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="3e240-144">*String*</span></span> | <span data-ttu-id="3e240-145">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="3e240-145">Read-only</span></span><br><span data-ttu-id="3e240-146">Szükséges</span><span class="sxs-lookup"><span data-stu-id="3e240-146">Required</span></span> | <span data-ttu-id="3e240-147">A beosztáshoz meghatározott fizetési ciklus.</span><span class="sxs-lookup"><span data-stu-id="3e240-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="3e240-148">**Jogi személy által fizetett**</span><span class="sxs-lookup"><span data-stu-id="3e240-148">**Paid by legal entity**</span></span><br><span data-ttu-id="3e240-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="3e240-149">paidbylegalentity</span></span><br><span data-ttu-id="3e240-150">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="3e240-150">*String*</span></span> | <span data-ttu-id="3e240-151">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="3e240-151">Read-only</span></span><br><span data-ttu-id="3e240-152">Szükséges</span><span class="sxs-lookup"><span data-stu-id="3e240-152">Required</span></span> | <span data-ttu-id="3e240-153">A fizetés kiadásáért felelős beosztáshoz meghatározott jogi személy.</span><span class="sxs-lookup"><span data-stu-id="3e240-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="3e240-154">**Beosztásazonosító**</span><span class="sxs-lookup"><span data-stu-id="3e240-154">**Position ID**</span></span><br><span data-ttu-id="3e240-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="3e240-155">mshr_positionid</span></span><br><span data-ttu-id="3e240-156">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="3e240-156">*String*</span></span> | <span data-ttu-id="3e240-157">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="3e240-157">Read-only</span></span><br><span data-ttu-id="3e240-158">Szükséges</span><span class="sxs-lookup"><span data-stu-id="3e240-158">Required</span></span> | <span data-ttu-id="3e240-159">A pozíció azonosítója.</span><span class="sxs-lookup"><span data-stu-id="3e240-159">The ID of the position.</span></span> |
| <span data-ttu-id="3e240-160">**Érvényesség vége:**</span><span class="sxs-lookup"><span data-stu-id="3e240-160">**Valid to**</span></span><br><span data-ttu-id="3e240-161">validto</span><span class="sxs-lookup"><span data-stu-id="3e240-161">validto</span></span><br><span data-ttu-id="3e240-162">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="3e240-162">*Date Time Offset*</span></span> | <span data-ttu-id="3e240-163">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="3e240-163">Read-only</span></span><br><span data-ttu-id="3e240-164">Szükséges</span><span class="sxs-lookup"><span data-stu-id="3e240-164">Required</span></span> |<span data-ttu-id="3e240-165">Az a dátum, amelytől a beosztás adatai érvényesek.</span><span class="sxs-lookup"><span data-stu-id="3e240-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="3e240-166">**Érvényesség kezdete**</span><span class="sxs-lookup"><span data-stu-id="3e240-166">**Valid from**</span></span><br><span data-ttu-id="3e240-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="3e240-167">validfrom</span></span><br><span data-ttu-id="3e240-168">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="3e240-168">*Date Time Offset*</span></span> | <span data-ttu-id="3e240-169">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="3e240-169">Read-only</span></span><br><span data-ttu-id="3e240-170">Szükséges</span><span class="sxs-lookup"><span data-stu-id="3e240-170">Required</span></span> |<span data-ttu-id="3e240-171">Az a dátum, ameddig a beosztás adatai érvényesek.</span><span class="sxs-lookup"><span data-stu-id="3e240-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="3e240-172">**Lekérdezés**</span><span class="sxs-lookup"><span data-stu-id="3e240-172">**Query**</span></span>

<span data-ttu-id="3e240-173">**Kérelem**</span><span class="sxs-lookup"><span data-stu-id="3e240-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="3e240-174">**Válasz**</span><span class="sxs-lookup"><span data-stu-id="3e240-174">**Response**</span></span>

```json
{
            "mshr_positionid": "000276",
            "mshr_paycycleid": "w",
            "mshr_annualregularhours": 3000,
            "mshr_paidbylegalentity": "USMF",
            "mshr_validfrom": "2021-03-14T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_primaryfield": "000276 | 3/14/2021",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
            "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```
