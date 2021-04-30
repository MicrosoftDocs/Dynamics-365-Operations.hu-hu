---
title: Bérlista beosztásokra vonatkozó részletei
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérszámfejtési részletek a beosztáshoz entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: f6c4bb0e2f4521e8c870f6c4fb645e2ce506138c
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881996"
---
# <a name="payroll-position"></a><span data-ttu-id="fa922-103">Bérlista szerinti beosztás</span><span class="sxs-lookup"><span data-stu-id="fa922-103">Payroll position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="fa922-104">Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérszámfejtési részletek a beosztáshoz entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="fa922-104">This topic provides details and an example query for the Payroll details for the Positions entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="fa922-105">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="fa922-105">Properties</span></span>

| <span data-ttu-id="fa922-106">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="fa922-106">Property</span></span><br><span data-ttu-id="fa922-107">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="fa922-107">**Physical name**</span></span><br><span data-ttu-id="fa922-108">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="fa922-108">**_Type_**</span></span> | <span data-ttu-id="fa922-109">Használat</span><span class="sxs-lookup"><span data-stu-id="fa922-109">Use</span></span> | <span data-ttu-id="fa922-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="fa922-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="fa922-111">**Éves rendes munkaidő**</span><span class="sxs-lookup"><span data-stu-id="fa922-111">**Annual regular hours**</span></span><br><span data-ttu-id="fa922-112">annualregularhours</span><span class="sxs-lookup"><span data-stu-id="fa922-112">annualregularhours</span></span><br><span data-ttu-id="fa922-113">*Decimális*</span><span class="sxs-lookup"><span data-stu-id="fa922-113">*Decimal*</span></span> | <span data-ttu-id="fa922-114">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="fa922-114">Read-only</span></span><br><span data-ttu-id="fa922-115">Szükséges</span><span class="sxs-lookup"><span data-stu-id="fa922-115">Required</span></span> | <span data-ttu-id="fa922-116">A beosztáshoz meghatározott éves rendszeres munkaidő.</span><span class="sxs-lookup"><span data-stu-id="fa922-116">Annual regular hours defined on the position.</span></span>  |
| <span data-ttu-id="fa922-117">**Bérlista szerinti beosztás részletei entitás azonosítója**</span><span class="sxs-lookup"><span data-stu-id="fa922-117">**Payroll position details entity ID**</span></span><br><span data-ttu-id="fa922-118">payrollpositiondetailsentityid</span><span class="sxs-lookup"><span data-stu-id="fa922-118">payrollpositiondetailsentityid</span></span><br><span data-ttu-id="fa922-119">*Guid*</span><span class="sxs-lookup"><span data-stu-id="fa922-119">*Guid*</span></span> | <span data-ttu-id="fa922-120">Szükséges</span><span class="sxs-lookup"><span data-stu-id="fa922-120">Required</span></span><br><span data-ttu-id="fa922-121">Rendszer által előállított.</span><span class="sxs-lookup"><span data-stu-id="fa922-121">System generated.</span></span> | <span data-ttu-id="fa922-122">A pozíció egyedi azonosítására szolgáló, rendszer által generált GUID-értéke.</span><span class="sxs-lookup"><span data-stu-id="fa922-122">A system-generated GUID value to uniquely identify the position.</span></span>  |
| <span data-ttu-id="fa922-123">**Elsődleges mező**</span><span class="sxs-lookup"><span data-stu-id="fa922-123">**Primary field**</span></span><br><span data-ttu-id="fa922-124">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="fa922-124">mshr_primaryfield</span></span><br><span data-ttu-id="fa922-125">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="fa922-125">*String*</span></span> | <span data-ttu-id="fa922-126">Szükséges</span><span class="sxs-lookup"><span data-stu-id="fa922-126">Required</span></span><br><span data-ttu-id="fa922-127">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="fa922-127">System generated</span></span> |  |
| <span data-ttu-id="fa922-128">**Beosztáshoz tartozó feladat azonosítójának értéke**</span><span class="sxs-lookup"><span data-stu-id="fa922-128">**Position job ID value**</span></span><br><span data-ttu-id="fa922-129">_mshr_fk_positionjob_id_value</span><span class="sxs-lookup"><span data-stu-id="fa922-129">_mshr_fk_positionjob_id_value</span></span><br><span data-ttu-id="fa922-130">*GUID*</span><span class="sxs-lookup"><span data-stu-id="fa922-130">*GUID*</span></span> | <span data-ttu-id="fa922-131">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="fa922-131">Read-only</span></span><br><span data-ttu-id="fa922-132">Szükséges</span><span class="sxs-lookup"><span data-stu-id="fa922-132">Required</span></span><br><span data-ttu-id="fa922-133">Idegen kulcs:mshr_PayrollPositionJobEntity ehhez: mshr_payrollpositionjobentity</span><span class="sxs-lookup"><span data-stu-id="fa922-133">Foreign key:mshr_PayrollPositionJobEntity of the mshr_payrollpositionjobentity</span></span> |<span data-ttu-id="fa922-134">A pozícióhoz társított beosztás azonosítója.</span><span class="sxs-lookup"><span data-stu-id="fa922-134">The ID of the job associated with the position.</span></span>|
| <span data-ttu-id="fa922-135">**Fix kompenzációs konstrukció azonosítójának értéke**</span><span class="sxs-lookup"><span data-stu-id="fa922-135">**Fixed compensation plan ID value**</span></span><br><span data-ttu-id="fa922-136">_mshr_fk_fixedcompplan_id_value</span><span class="sxs-lookup"><span data-stu-id="fa922-136">_mshr_fk_fixedcompplan_id_value</span></span><br><span data-ttu-id="fa922-137">*GUID*</span><span class="sxs-lookup"><span data-stu-id="fa922-137">*GUID*</span></span> | <span data-ttu-id="fa922-138">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="fa922-138">Read-only</span></span><br><span data-ttu-id="fa922-139">Szükséges</span><span class="sxs-lookup"><span data-stu-id="fa922-139">Required</span></span><br><span data-ttu-id="fa922-140">Idegen kulcs: mshr_payrollfixedcompensationplanentity entitáshoz tartozó mshr_FixedCompPlan_id</span><span class="sxs-lookup"><span data-stu-id="fa922-140">Foreign key: mshr_FixedCompPlan_id of mshr_payrollfixedcompensationplanentity</span></span>  | <span data-ttu-id="fa922-141">A pozícióhoz társított fix kompenzációs konstrukció azonosítója.</span><span class="sxs-lookup"><span data-stu-id="fa922-141">The ID of the fixed compensation plan associated with the position.</span></span> |
| <span data-ttu-id="fa922-142">**Fizetési ciklus azonsítója**</span><span class="sxs-lookup"><span data-stu-id="fa922-142">**Pay cycle ID**</span></span><br><span data-ttu-id="fa922-143">mshr_primaryfield</span><span class="sxs-lookup"><span data-stu-id="fa922-143">mshr_primaryfield</span></span><br><span data-ttu-id="fa922-144">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="fa922-144">*String*</span></span> | <span data-ttu-id="fa922-145">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="fa922-145">Read-only</span></span><br><span data-ttu-id="fa922-146">Szükséges</span><span class="sxs-lookup"><span data-stu-id="fa922-146">Required</span></span> | <span data-ttu-id="fa922-147">A beosztáshoz meghatározott fizetési ciklus.</span><span class="sxs-lookup"><span data-stu-id="fa922-147">The pay cycle defined on the position.</span></span> |
| <span data-ttu-id="fa922-148">**Jogi személy által fizetett**</span><span class="sxs-lookup"><span data-stu-id="fa922-148">**Paid by legal entity**</span></span><br><span data-ttu-id="fa922-149">paidbylegalentity</span><span class="sxs-lookup"><span data-stu-id="fa922-149">paidbylegalentity</span></span><br><span data-ttu-id="fa922-150">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="fa922-150">*String*</span></span> | <span data-ttu-id="fa922-151">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="fa922-151">Read-only</span></span><br><span data-ttu-id="fa922-152">Szükséges</span><span class="sxs-lookup"><span data-stu-id="fa922-152">Required</span></span> | <span data-ttu-id="fa922-153">A fizetés kiadásáért felelős beosztáshoz meghatározott jogi személy.</span><span class="sxs-lookup"><span data-stu-id="fa922-153">The legal entity defined on the positoin responsible for issuing payment.</span></span> |
| <span data-ttu-id="fa922-154">**Beosztásazonosító**</span><span class="sxs-lookup"><span data-stu-id="fa922-154">**Position ID**</span></span><br><span data-ttu-id="fa922-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="fa922-155">mshr_positionid</span></span><br><span data-ttu-id="fa922-156">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="fa922-156">*String*</span></span> | <span data-ttu-id="fa922-157">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="fa922-157">Read-only</span></span><br><span data-ttu-id="fa922-158">Szükséges</span><span class="sxs-lookup"><span data-stu-id="fa922-158">Required</span></span> | <span data-ttu-id="fa922-159">A pozíció azonosítója.</span><span class="sxs-lookup"><span data-stu-id="fa922-159">The ID of the position.</span></span> |
| <span data-ttu-id="fa922-160">**Érvényesség vége:**</span><span class="sxs-lookup"><span data-stu-id="fa922-160">**Valid to**</span></span><br><span data-ttu-id="fa922-161">validto</span><span class="sxs-lookup"><span data-stu-id="fa922-161">validto</span></span><br><span data-ttu-id="fa922-162">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="fa922-162">*Date Time Offset*</span></span> | <span data-ttu-id="fa922-163">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="fa922-163">Read-only</span></span><br><span data-ttu-id="fa922-164">Szükséges</span><span class="sxs-lookup"><span data-stu-id="fa922-164">Required</span></span> |<span data-ttu-id="fa922-165">Az a dátum, amelytől a beosztás adatai érvényesek.</span><span class="sxs-lookup"><span data-stu-id="fa922-165">The date the position details are valid from.</span></span>  |
| <span data-ttu-id="fa922-166">**Érvényesség kezdete**</span><span class="sxs-lookup"><span data-stu-id="fa922-166">**Valid from**</span></span><br><span data-ttu-id="fa922-167">validfrom</span><span class="sxs-lookup"><span data-stu-id="fa922-167">validfrom</span></span><br><span data-ttu-id="fa922-168">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="fa922-168">*Date Time Offset*</span></span> | <span data-ttu-id="fa922-169">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="fa922-169">Read-only</span></span><br><span data-ttu-id="fa922-170">Szükséges</span><span class="sxs-lookup"><span data-stu-id="fa922-170">Required</span></span> |<span data-ttu-id="fa922-171">Az a dátum, ameddig a beosztás adatai érvényesek.</span><span class="sxs-lookup"><span data-stu-id="fa922-171">The date the position details are valid to.</span></span>  |

<span data-ttu-id="fa922-172">**Lekérdezés**</span><span class="sxs-lookup"><span data-stu-id="fa922-172">**Query**</span></span>

<span data-ttu-id="fa922-173">**Kérelem**</span><span class="sxs-lookup"><span data-stu-id="fa922-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

<span data-ttu-id="fa922-174">**Válasz**</span><span class="sxs-lookup"><span data-stu-id="fa922-174">**Response**</span></span>

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
