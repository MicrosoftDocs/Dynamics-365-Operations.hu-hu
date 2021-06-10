---
title: Fix kompenzációs konstrukció bérlistája
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista fix kompenzációs konstrukció entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 227082358c59abddd63f4faa4536a8df270a4d80
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059088"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="0f0e8-103">Fix kompenzációs konstrukció bérlistája</span><span class="sxs-lookup"><span data-stu-id="0f0e8-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0f0e8-104">Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista fix kompenzációs konstrukció entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="0f0e8-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="0f0e8-105">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="0f0e8-105">Properties</span></span>

| <span data-ttu-id="0f0e8-106">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="0f0e8-106">Property</span></span><br><span data-ttu-id="0f0e8-107">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-107">**Physical name**</span></span><br><span data-ttu-id="0f0e8-108">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-108">**_Type_**</span></span> | <span data-ttu-id="0f0e8-109">Használat</span><span class="sxs-lookup"><span data-stu-id="0f0e8-109">Use</span></span> | <span data-ttu-id="0f0e8-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="0f0e8-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="0f0e8-111">**Alkalmazott azonosítója**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-111">**Employee ID**</span></span><br><span data-ttu-id="0f0e8-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="0f0e8-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="0f0e8-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="0f0e8-113">*GUID*</span></span> | <span data-ttu-id="0f0e8-114">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="0f0e8-114">Read-only</span></span><br><span data-ttu-id="0f0e8-115">Szükséges</span><span class="sxs-lookup"><span data-stu-id="0f0e8-115">Required</span></span><br><span data-ttu-id="0f0e8-116">Idegen kulcs: mshr_payrollemployeeentity entitáshoz tartozó mshr_Employee_id</span><span class="sxs-lookup"><span data-stu-id="0f0e8-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="0f0e8-117">Alkalmazott azonosítója</span><span class="sxs-lookup"><span data-stu-id="0f0e8-117">Employee ID</span></span> |
| <span data-ttu-id="0f0e8-118">**Fizetési díjalap**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-118">**Pay rate**</span></span><br><span data-ttu-id="0f0e8-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="0f0e8-119">mshr_payrate</span></span><br><span data-ttu-id="0f0e8-120">*Decimális*</span><span class="sxs-lookup"><span data-stu-id="0f0e8-120">*Decimal*</span></span> | <span data-ttu-id="0f0e8-121">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="0f0e8-121">Read-only</span></span><br><span data-ttu-id="0f0e8-122">Szükséges</span><span class="sxs-lookup"><span data-stu-id="0f0e8-122">Required</span></span> | <span data-ttu-id="0f0e8-123">A fix kompenzációs konstrukcióban meghatározott fizetési díj.</span><span class="sxs-lookup"><span data-stu-id="0f0e8-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="0f0e8-124">**Tervazonosító**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-124">**Plan ID**</span></span><br><span data-ttu-id="0f0e8-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="0f0e8-125">mshr_planid</span></span><br><span data-ttu-id="0f0e8-126">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="0f0e8-126">*String*</span></span> | <span data-ttu-id="0f0e8-127">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="0f0e8-127">Read-only</span></span><br><span data-ttu-id="0f0e8-128">Szükséges</span><span class="sxs-lookup"><span data-stu-id="0f0e8-128">Required</span></span> |<span data-ttu-id="0f0e8-129">A kompenzációs konstrukciót adja meg.</span><span class="sxs-lookup"><span data-stu-id="0f0e8-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="0f0e8-130">**Érvényesség kezdete**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-130">**Valid from**</span></span><br><span data-ttu-id="0f0e8-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="0f0e8-131">mshr_validfrom</span></span><br><span data-ttu-id="0f0e8-132">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="0f0e8-132">*Date Time Offset*</span></span> |  <span data-ttu-id="0f0e8-133">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="0f0e8-133">Read-only</span></span><br><span data-ttu-id="0f0e8-134">Szükséges</span><span class="sxs-lookup"><span data-stu-id="0f0e8-134">Required</span></span> |<span data-ttu-id="0f0e8-135">Az a dátum, amelytől az alkalmazott fix kompenzációja érvényes.</span><span class="sxs-lookup"><span data-stu-id="0f0e8-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="0f0e8-136">**Fix kompenzációs konstrukció bérlistája entitás**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="0f0e8-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="0f0e8-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="0f0e8-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="0f0e8-138">*GUID*</span></span> | <span data-ttu-id="0f0e8-139">Szükséges</span><span class="sxs-lookup"><span data-stu-id="0f0e8-139">Required</span></span><br><span data-ttu-id="0f0e8-140">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="0f0e8-140">Sytem generated</span></span> | <span data-ttu-id="0f0e8-141">A kompenzációs konstrukció azonosítására szolgáló, rendszer által generált GUID-értéke.</span><span class="sxs-lookup"><span data-stu-id="0f0e8-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="0f0e8-142">**Fizetési gyakoriság**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-142">**Pay frequency**</span></span><br><span data-ttu-id="0f0e8-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="0f0e8-143">mshr_payfrequency</span></span><br><span data-ttu-id="0f0e8-144">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="0f0e8-144">*String*</span></span> | <span data-ttu-id="0f0e8-145">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="0f0e8-145">Read-only</span></span><br><span data-ttu-id="0f0e8-146">Szükséges</span><span class="sxs-lookup"><span data-stu-id="0f0e8-146">Required</span></span> |<span data-ttu-id="0f0e8-147">Az alkalmazott fizetésének gyakorisága.</span><span class="sxs-lookup"><span data-stu-id="0f0e8-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="0f0e8-148">**Érvényesség vége:**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-148">**Valid to**</span></span><br><span data-ttu-id="0f0e8-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="0f0e8-149">mshr_validto</span></span><br><span data-ttu-id="0f0e8-150">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="0f0e8-150">*Date Time Offset*</span></span> | <span data-ttu-id="0f0e8-151">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="0f0e8-151">Read-only</span></span> <br><span data-ttu-id="0f0e8-152">Szükséges</span><span class="sxs-lookup"><span data-stu-id="0f0e8-152">Required</span></span> | <span data-ttu-id="0f0e8-153">Az a dátum, amelyig az alkalmazott fix kompenzációja érvényes.</span><span class="sxs-lookup"><span data-stu-id="0f0e8-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="0f0e8-154">**Beosztásazonosító**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-154">**Position ID**</span></span><br><span data-ttu-id="0f0e8-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="0f0e8-155">mshr_positionid</span></span><br><span data-ttu-id="0f0e8-156">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="0f0e8-156">*String*</span></span> | <span data-ttu-id="0f0e8-157">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="0f0e8-157">Read-only</span></span> <br><span data-ttu-id="0f0e8-158">Szükséges</span><span class="sxs-lookup"><span data-stu-id="0f0e8-158">Required</span></span> | <span data-ttu-id="0f0e8-159">Az alkalmazotthoz és a fix kompenzációs konstrukcióba való belépéshez társított pozícióazonosító.</span><span class="sxs-lookup"><span data-stu-id="0f0e8-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="0f0e8-160">**Pénznem**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-160">**Currency**</span></span><br><span data-ttu-id="0f0e8-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="0f0e8-161">mshr_currency</span></span><br><span data-ttu-id="0f0e8-162">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="0f0e8-162">*String*</span></span> | <span data-ttu-id="0f0e8-163">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="0f0e8-163">Read-only</span></span> <br><span data-ttu-id="0f0e8-164">Szükséges</span><span class="sxs-lookup"><span data-stu-id="0f0e8-164">Required</span></span> |<span data-ttu-id="0f0e8-165">A fix kompenzációs konstrukcióhoz meghatározott pénznem</span><span class="sxs-lookup"><span data-stu-id="0f0e8-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="0f0e8-166">**Személyzeti szám**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-166">**Personnel number**</span></span><br><span data-ttu-id="0f0e8-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="0f0e8-167">mshr_personnelnumber</span></span><br><span data-ttu-id="0f0e8-168">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="0f0e8-168">*String*</span></span> | <span data-ttu-id="0f0e8-169">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="0f0e8-169">Read-only</span></span><br><span data-ttu-id="0f0e8-170">Szükséges</span><span class="sxs-lookup"><span data-stu-id="0f0e8-170">Required</span></span> |<span data-ttu-id="0f0e8-171">Az alkalmazott egyedi személyzeti száma.</span><span class="sxs-lookup"><span data-stu-id="0f0e8-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="0f0e8-172">**Lekérdezés**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-172">**Query**</span></span>

<span data-ttu-id="0f0e8-173">**Kérelem**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="0f0e8-174">**Válasz**</span><span class="sxs-lookup"><span data-stu-id="0f0e8-174">**Response**</span></span>

```json
{
            "mshr_planid": "GradeC",
            "mshr_personnelnumber": "000041",
            "mshr_payrate": 75200,
            "mshr_positionid": "000276",
            "mshr_validfrom": "2011-04-05T00:00:00Z",
            "mshr_validto": "2154-12-31T00:00:00Z",
            "mshr_payfrequency": "Annual",
            "mshr_currency": "USD",
            "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
            "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
            "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
            "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
            "_mshr_fk_payroll_id_value": null
}
```
