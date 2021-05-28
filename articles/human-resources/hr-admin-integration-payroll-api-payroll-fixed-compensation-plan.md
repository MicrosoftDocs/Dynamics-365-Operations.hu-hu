---
title: Fix kompenzációs konstrukció bérlistája
description: Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista fix kompenzációs konstrukció entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.
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
ms.openlocfilehash: 85cfce6f626090adab422ea6c60fc0778fd1ac67
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021296"
---
# <a name="payroll-fixed-compensation-plan"></a><span data-ttu-id="7e72a-103">Fix kompenzációs konstrukció bérlistája</span><span class="sxs-lookup"><span data-stu-id="7e72a-103">Payroll fixed compensation plan</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7e72a-104">Ez a témakör részleteket nyújt, és példalekérdezést tartalmaz a Bérlista fix kompenzációs konstrukció entitásra vonatkozóan a Dynamics 365 Human Resources rendszerben.</span><span class="sxs-lookup"><span data-stu-id="7e72a-104">This topic provides details and an example query for the Payroll fixed compensation plan entity in Dynamics 365 Human Resources.</span></span>

## <a name="properties"></a><span data-ttu-id="7e72a-105">Tulajdonságok</span><span class="sxs-lookup"><span data-stu-id="7e72a-105">Properties</span></span>

| <span data-ttu-id="7e72a-106">Tulajdonság</span><span class="sxs-lookup"><span data-stu-id="7e72a-106">Property</span></span><br><span data-ttu-id="7e72a-107">**Fizikai név**</span><span class="sxs-lookup"><span data-stu-id="7e72a-107">**Physical name**</span></span><br><span data-ttu-id="7e72a-108">**_Típus_**</span><span class="sxs-lookup"><span data-stu-id="7e72a-108">**_Type_**</span></span> | <span data-ttu-id="7e72a-109">Használat</span><span class="sxs-lookup"><span data-stu-id="7e72a-109">Use</span></span> | <span data-ttu-id="7e72a-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="7e72a-110">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="7e72a-111">**Alkalmazott azonosítója**</span><span class="sxs-lookup"><span data-stu-id="7e72a-111">**Employee ID**</span></span><br><span data-ttu-id="7e72a-112">mshr_fk_employee_id_value</span><span class="sxs-lookup"><span data-stu-id="7e72a-112">mshr_fk_employee_id_value</span></span><br><span data-ttu-id="7e72a-113">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7e72a-113">*GUID*</span></span> | <span data-ttu-id="7e72a-114">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="7e72a-114">Read-only</span></span><br><span data-ttu-id="7e72a-115">Szükséges</span><span class="sxs-lookup"><span data-stu-id="7e72a-115">Required</span></span><br><span data-ttu-id="7e72a-116">Idegen kulcs: mshr_payrollemployeeentity entitáshoz tartozó mshr_Employee_id</span><span class="sxs-lookup"><span data-stu-id="7e72a-116">Foreign key:mshr_Employee_id of mshr_payrollemployeeentity entity</span></span>  | <span data-ttu-id="7e72a-117">Alkalmazott azonosítója</span><span class="sxs-lookup"><span data-stu-id="7e72a-117">Employee ID</span></span> |
| <span data-ttu-id="7e72a-118">**Fizetési díjalap**</span><span class="sxs-lookup"><span data-stu-id="7e72a-118">**Pay rate**</span></span><br><span data-ttu-id="7e72a-119">mshr_payrate</span><span class="sxs-lookup"><span data-stu-id="7e72a-119">mshr_payrate</span></span><br><span data-ttu-id="7e72a-120">*Decimális*</span><span class="sxs-lookup"><span data-stu-id="7e72a-120">*Decimal*</span></span> | <span data-ttu-id="7e72a-121">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="7e72a-121">Read-only</span></span><br><span data-ttu-id="7e72a-122">Szükséges</span><span class="sxs-lookup"><span data-stu-id="7e72a-122">Required</span></span> | <span data-ttu-id="7e72a-123">A fix kompenzációs konstrukcióban meghatározott fizetési díj.</span><span class="sxs-lookup"><span data-stu-id="7e72a-123">Pay rate defined in fixed compensation plan.</span></span> |
| <span data-ttu-id="7e72a-124">**Tervazonosító**</span><span class="sxs-lookup"><span data-stu-id="7e72a-124">**Plan ID**</span></span><br><span data-ttu-id="7e72a-125">mshr_planid</span><span class="sxs-lookup"><span data-stu-id="7e72a-125">mshr_planid</span></span><br><span data-ttu-id="7e72a-126">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="7e72a-126">*String*</span></span> | <span data-ttu-id="7e72a-127">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="7e72a-127">Read-only</span></span><br><span data-ttu-id="7e72a-128">Szükséges</span><span class="sxs-lookup"><span data-stu-id="7e72a-128">Required</span></span> |<span data-ttu-id="7e72a-129">A kompenzációs konstrukciót adja meg.</span><span class="sxs-lookup"><span data-stu-id="7e72a-129">Specifies the compensation plan.</span></span>  |
| <span data-ttu-id="7e72a-130">**Érvényesség kezdete**</span><span class="sxs-lookup"><span data-stu-id="7e72a-130">**Valid from**</span></span><br><span data-ttu-id="7e72a-131">mshr_validfrom</span><span class="sxs-lookup"><span data-stu-id="7e72a-131">mshr_validfrom</span></span><br><span data-ttu-id="7e72a-132">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="7e72a-132">*Date Time Offset*</span></span> |  <span data-ttu-id="7e72a-133">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="7e72a-133">Read-only</span></span><br><span data-ttu-id="7e72a-134">Szükséges</span><span class="sxs-lookup"><span data-stu-id="7e72a-134">Required</span></span> |<span data-ttu-id="7e72a-135">Az a dátum, amelytől az alkalmazott fix kompenzációja érvényes.</span><span class="sxs-lookup"><span data-stu-id="7e72a-135">Date the employee fixed compensation is valid from.</span></span>  |
| <span data-ttu-id="7e72a-136">**Fix kompenzációs konstrukció bérlistája entitás**</span><span class="sxs-lookup"><span data-stu-id="7e72a-136">**Payroll Fixed Compensation Plan entity**</span></span><br><span data-ttu-id="7e72a-137">mshr_payrollfixedcompensationplanentityid</span><span class="sxs-lookup"><span data-stu-id="7e72a-137">mshr_payrollfixedcompensationplanentityid</span></span><br><span data-ttu-id="7e72a-138">*GUID*</span><span class="sxs-lookup"><span data-stu-id="7e72a-138">*GUID*</span></span> | <span data-ttu-id="7e72a-139">Szükséges</span><span class="sxs-lookup"><span data-stu-id="7e72a-139">Required</span></span><br><span data-ttu-id="7e72a-140">Rendszer által előállított</span><span class="sxs-lookup"><span data-stu-id="7e72a-140">Sytem generated</span></span> | <span data-ttu-id="7e72a-141">A kompenzációs konstrukció azonosítására szolgáló, rendszer által generált GUID-értéke.</span><span class="sxs-lookup"><span data-stu-id="7e72a-141">A system-generated GUID value to uniquely identify the compensation plan.</span></span> |
| <span data-ttu-id="7e72a-142">**Fizetési gyakoriság**</span><span class="sxs-lookup"><span data-stu-id="7e72a-142">**Pay frequency**</span></span><br><span data-ttu-id="7e72a-143">mshr_payfrequency</span><span class="sxs-lookup"><span data-stu-id="7e72a-143">mshr_payfrequency</span></span><br><span data-ttu-id="7e72a-144">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="7e72a-144">*String*</span></span> | <span data-ttu-id="7e72a-145">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="7e72a-145">Read-only</span></span><br><span data-ttu-id="7e72a-146">Szükséges</span><span class="sxs-lookup"><span data-stu-id="7e72a-146">Required</span></span> |<span data-ttu-id="7e72a-147">Az alkalmazott fizetésének gyakorisága.</span><span class="sxs-lookup"><span data-stu-id="7e72a-147">The frequency the employee will be paid.</span></span>  |
| <span data-ttu-id="7e72a-148">**Érvényesség vége:**</span><span class="sxs-lookup"><span data-stu-id="7e72a-148">**Valid to**</span></span><br><span data-ttu-id="7e72a-149">mshr_validto</span><span class="sxs-lookup"><span data-stu-id="7e72a-149">mshr_validto</span></span><br><span data-ttu-id="7e72a-150">*Dátum és idő eltolása*</span><span class="sxs-lookup"><span data-stu-id="7e72a-150">*Date Time Offset*</span></span> | <span data-ttu-id="7e72a-151">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="7e72a-151">Read-only</span></span> <br><span data-ttu-id="7e72a-152">Szükséges</span><span class="sxs-lookup"><span data-stu-id="7e72a-152">Required</span></span> | <span data-ttu-id="7e72a-153">Az a dátum, amelyig az alkalmazott fix kompenzációja érvényes.</span><span class="sxs-lookup"><span data-stu-id="7e72a-153">Date the employee fixed compensation is valid to.</span></span> |
| <span data-ttu-id="7e72a-154">**Beosztásazonosító**</span><span class="sxs-lookup"><span data-stu-id="7e72a-154">**Position ID**</span></span><br><span data-ttu-id="7e72a-155">mshr_positionid</span><span class="sxs-lookup"><span data-stu-id="7e72a-155">mshr_positionid</span></span><br><span data-ttu-id="7e72a-156">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="7e72a-156">*String*</span></span> | <span data-ttu-id="7e72a-157">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="7e72a-157">Read-only</span></span> <br><span data-ttu-id="7e72a-158">Szükséges</span><span class="sxs-lookup"><span data-stu-id="7e72a-158">Required</span></span> | <span data-ttu-id="7e72a-159">Az alkalmazotthoz és a fix kompenzációs konstrukcióba való belépéshez társított pozícióazonosító.</span><span class="sxs-lookup"><span data-stu-id="7e72a-159">Postion ID associated with the employee and fixed compensation plan enrollment.</span></span> |
| <span data-ttu-id="7e72a-160">**Pénznem**</span><span class="sxs-lookup"><span data-stu-id="7e72a-160">**Currency**</span></span><br><span data-ttu-id="7e72a-161">mshr_currency</span><span class="sxs-lookup"><span data-stu-id="7e72a-161">mshr_currency</span></span><br><span data-ttu-id="7e72a-162">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="7e72a-162">*String*</span></span> | <span data-ttu-id="7e72a-163">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="7e72a-163">Read-only</span></span> <br><span data-ttu-id="7e72a-164">Szükséges</span><span class="sxs-lookup"><span data-stu-id="7e72a-164">Required</span></span> |<span data-ttu-id="7e72a-165">A fix kompenzációs konstrukcióhoz meghatározott pénznem</span><span class="sxs-lookup"><span data-stu-id="7e72a-165">The currency defined for the fixed compensation plan</span></span>   |
| <span data-ttu-id="7e72a-166">**Személyzeti szám**</span><span class="sxs-lookup"><span data-stu-id="7e72a-166">**Personnel number**</span></span><br><span data-ttu-id="7e72a-167">mshr_personnelnumber</span><span class="sxs-lookup"><span data-stu-id="7e72a-167">mshr_personnelnumber</span></span><br><span data-ttu-id="7e72a-168">*Sztring*</span><span class="sxs-lookup"><span data-stu-id="7e72a-168">*String*</span></span> | <span data-ttu-id="7e72a-169">Írásvédett</span><span class="sxs-lookup"><span data-stu-id="7e72a-169">Read-only</span></span><br><span data-ttu-id="7e72a-170">Szükséges</span><span class="sxs-lookup"><span data-stu-id="7e72a-170">Required</span></span> |<span data-ttu-id="7e72a-171">Az alkalmazott egyedi személyzeti száma.</span><span class="sxs-lookup"><span data-stu-id="7e72a-171">The employee's unique personnel number.</span></span>  |

<span data-ttu-id="7e72a-172">**Lekérdezés**</span><span class="sxs-lookup"><span data-stu-id="7e72a-172">**Query**</span></span>

<span data-ttu-id="7e72a-173">**Kérelem**</span><span class="sxs-lookup"><span data-stu-id="7e72a-173">**Request**</span></span>

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

<span data-ttu-id="7e72a-174">**Válasz**</span><span class="sxs-lookup"><span data-stu-id="7e72a-174">**Response**</span></span>

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
