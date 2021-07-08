---
title: Képlettervező TDS-számításokhoz
description: Ez a témakör egy példát mutat arra, hogy a Forrásnál levont adót (TDS) hogyan számítják ki a tranzakcióhoz csatolt TDS-csoport minden egyes TDS-adókódjára meghatározott képlet alapján.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: d0f644da640b56761a52baec9ff01c898e895d19
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023289"
---
# <a name="formula-designer-for-tds-calculations"></a><span data-ttu-id="892f3-103">Képlettervező TDS-számításokhoz</span><span class="sxs-lookup"><span data-stu-id="892f3-103">Formula designer for TDS calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="892f3-104">Ez a témakör egy példát mutat arra, hogyan számítják ki a forrásnál levont adót (TDS) az egyes TDS-adókódokra meghatározott képlet alapján.</span><span class="sxs-lookup"><span data-stu-id="892f3-104">This topic provides an example of how Tax Deducted at Source (TDS) is calculated based on the formula defined for each TDS tax code.</span></span> <span data-ttu-id="892f3-105">A TDS adókódokat a tranzakcióhoz csatolt TDS csoport határozza meg.</span><span class="sxs-lookup"><span data-stu-id="892f3-105">TDS tax codes are defined in the TDS group that's attached to the transaction.</span></span> <span data-ttu-id="892f3-106">A TDS-képletek tervezése előtt töltse ki a TDS-hez szükséges alapbeállítást a következő lépésekben felsoroltak szerint.</span><span class="sxs-lookup"><span data-stu-id="892f3-106">Before designing TDS formulas, complete the basic setup required for TDS as listed in the following steps.</span></span> 

- <span data-ttu-id="892f3-107">Állítsa be a TDS-adóelőleg-összetevőkkel kapcsolatos csoportokat az **Adóelőleg-összetevő csoportok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="892f3-107">Set up TDS component groups using the **Withholding tax component groups** page.</span></span> 
- <span data-ttu-id="892f3-108">Állítsa be a TDS-összetevőket, és csatolja a TDS-összetevők csoportját a TDS-összetevőkhöz az **Adóelőleg-összetevők** oldal használatával.</span><span class="sxs-lookup"><span data-stu-id="892f3-108">Set up TDS components and attach TDS component group to the TDS components using the **Withholding tax components** page.</span></span> 
- <span data-ttu-id="892f3-109">Állítsa be a TDS-adókódokat, és csatolja a TDS-adókódok csoportját az adókódokhoz az **Adóelőlegkódok** oldal használatával.</span><span class="sxs-lookup"><span data-stu-id="892f3-109">Set up TDS tax codes and attach TDS components to the tax codes using the **Withholding tax codes** page.</span></span> 
- <span data-ttu-id="892f3-110">Állítsa be a TDS-adócsoportokat az **Adóelőleg csoportok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="892f3-110">Set up TDS tax groups using the **Withholding tax groups** page.</span></span> <span data-ttu-id="892f3-111">Ezután csatolja a TDS-adókódokat az adócsoporthoz, és határozza meg a képletet a **Képlettervező** oldalon.</span><span class="sxs-lookup"><span data-stu-id="892f3-111">Then attach the TDS tax codes to the tax group, and define the formula, using the **Formula designer** page.</span></span> 

<span data-ttu-id="892f3-112">**Példa képlet**</span><span class="sxs-lookup"><span data-stu-id="892f3-112">**Example formula**</span></span>

<span data-ttu-id="892f3-113">Ebben a példában a Bérleti díj nevű TDS-csoport az „A” szállító számára létrehozott beszerzési számlához van csatolva. A számla összege $100 000.</span><span class="sxs-lookup"><span data-stu-id="892f3-113">In this example, the TDS group, Rent, is attached to a purchase invoice that's created for vendor A. The invoice amount is $100,000.</span></span> <span data-ttu-id="892f3-114">A számla TDS-számításának megtekintéséhez hivatkozzon az alábbi táblázatra.</span><span class="sxs-lookup"><span data-stu-id="892f3-114">Refer to the following table to view the TDS calculation for the invoice.</span></span>

| <span data-ttu-id="892f3-115">TDS-csoport</span><span class="sxs-lookup"><span data-stu-id="892f3-115">TDS  group</span></span>                                                   | <span data-ttu-id="892f3-116">A TDS-csoporthoz csatolt TDS-adókódok</span><span class="sxs-lookup"><span data-stu-id="892f3-116">TDS tax codes attached to the TDS group</span></span> | <span data-ttu-id="892f3-117">Érték</span><span class="sxs-lookup"><span data-stu-id="892f3-117">Value</span></span>              | <span data-ttu-id="892f3-118">Adóalap (Képlettervező)</span><span class="sxs-lookup"><span data-stu-id="892f3-118">Taxable basis  (Formula designer)</span></span> | <span data-ttu-id="892f3-119">Számítási kifejezés (Képlettervező)</span><span class="sxs-lookup"><span data-stu-id="892f3-119">Calculation expression  (Formula designer)</span></span> | <span data-ttu-id="892f3-120">Alapösszeg</span><span class="sxs-lookup"><span data-stu-id="892f3-120">Base amount</span></span> | <span data-ttu-id="892f3-121">Számított TDS összege</span><span class="sxs-lookup"><span data-stu-id="892f3-121">Calculated TDS amount</span></span> |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| <span data-ttu-id="892f3-122">Bérlet</span><span class="sxs-lookup"><span data-stu-id="892f3-122">Rent</span></span>                                                         | <span data-ttu-id="892f3-123">TDS (TDS-összetevő - TDS)</span><span class="sxs-lookup"><span data-stu-id="892f3-123">TDS  (TDS component-TDS)</span></span>                | <span data-ttu-id="892f3-124">10%</span><span class="sxs-lookup"><span data-stu-id="892f3-124">10%</span></span>                | <span data-ttu-id="892f3-125">Bruttó összeg</span><span class="sxs-lookup"><span data-stu-id="892f3-125">Gross amount</span></span>                      |                                            | <span data-ttu-id="892f3-126">100,000</span><span class="sxs-lookup"><span data-stu-id="892f3-126">100,000</span></span>      | <span data-ttu-id="892f3-127">10,000</span><span class="sxs-lookup"><span data-stu-id="892f3-127">10,000</span></span>                 |
| <span data-ttu-id="892f3-128">Felár (TDS-összetevő - Felár)</span><span class="sxs-lookup"><span data-stu-id="892f3-128">Surcharge  (TDS component-Surcharge)</span></span>                         | <span data-ttu-id="892f3-129">10%</span><span class="sxs-lookup"><span data-stu-id="892f3-129">10%</span></span>                                     | <span data-ttu-id="892f3-130">Kiz. bruttó összeg</span><span class="sxs-lookup"><span data-stu-id="892f3-130">Excl. gross amount</span></span> | <span data-ttu-id="892f3-131">+TDS</span><span class="sxs-lookup"><span data-stu-id="892f3-131">+TDS</span></span>                              |                   <span data-ttu-id="892f3-132">10000</span><span class="sxs-lookup"><span data-stu-id="892f3-132">10000</span></span>                    | <span data-ttu-id="892f3-133">1000</span><span class="sxs-lookup"><span data-stu-id="892f3-133">1,000</span></span>        |                       |
| <span data-ttu-id="892f3-134">PE-Cess (TDS-összetevő - PE-Cess)</span><span class="sxs-lookup"><span data-stu-id="892f3-134">PE-Cess  (TDS component- PE-Cess)</span></span>                            | <span data-ttu-id="892f3-135">2%</span><span class="sxs-lookup"><span data-stu-id="892f3-135">2%</span></span>                                      | <span data-ttu-id="892f3-136">Kiz. bruttó összeg</span><span class="sxs-lookup"><span data-stu-id="892f3-136">Excl. gross amount</span></span> | <span data-ttu-id="892f3-137">+TDS+Pótdíj</span><span class="sxs-lookup"><span data-stu-id="892f3-137">+TDS+Surcharge</span></span>                    |                   <span data-ttu-id="892f3-138">11000</span><span class="sxs-lookup"><span data-stu-id="892f3-138">11000</span></span>                    | <span data-ttu-id="892f3-139">220</span><span class="sxs-lookup"><span data-stu-id="892f3-139">220</span></span>         |                       |
| <span data-ttu-id="892f3-140">SHE Cess (TDS-összetevő - SHE Cess)</span><span class="sxs-lookup"><span data-stu-id="892f3-140">SHE Cess  (TDS component- SHE Cess)</span></span>                          | <span data-ttu-id="892f3-141">1%</span><span class="sxs-lookup"><span data-stu-id="892f3-141">1%</span></span>                                      | <span data-ttu-id="892f3-142">Kiz. bruttó összeg</span><span class="sxs-lookup"><span data-stu-id="892f3-142">Excl. gross amount</span></span> | <span data-ttu-id="892f3-143">+TDS+Pótdíj</span><span class="sxs-lookup"><span data-stu-id="892f3-143">+TDS+Surcharge</span></span>                    |                   <span data-ttu-id="892f3-144">11000</span><span class="sxs-lookup"><span data-stu-id="892f3-144">11000</span></span>                    | <span data-ttu-id="892f3-145">110</span><span class="sxs-lookup"><span data-stu-id="892f3-145">110</span></span>         |                       |
| <span data-ttu-id="892f3-146">**A** **számlára** **számított** **összes** **TDS**</span><span class="sxs-lookup"><span data-stu-id="892f3-146">**Total** **TDS**  **calculated** **for** **the** **invoice**</span></span> | <span data-ttu-id="892f3-147">**11,330**</span><span class="sxs-lookup"><span data-stu-id="892f3-147">**11,330**</span></span>                               |                    |                                   |                                            |             |                       |

<span data-ttu-id="892f3-148">A bizonylatbejegyzések az alábbiak szerint jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="892f3-148">The voucher entries are created as follows.</span></span>

| <span data-ttu-id="892f3-149">Könyvelési számla</span><span class="sxs-lookup"><span data-stu-id="892f3-149">Account</span></span>           | <span data-ttu-id="892f3-150">Tartozik</span><span class="sxs-lookup"><span data-stu-id="892f3-150">Debit</span></span>  | <span data-ttu-id="892f3-151">Követel</span><span class="sxs-lookup"><span data-stu-id="892f3-151">Credit</span></span> |
| ----------------- | ------ | ------ |
| <span data-ttu-id="892f3-152">Bérlet</span><span class="sxs-lookup"><span data-stu-id="892f3-152">Rent</span></span>              | <span data-ttu-id="892f3-153">100,000</span><span class="sxs-lookup"><span data-stu-id="892f3-153">100,000</span></span> |        |
| <span data-ttu-id="892f3-154">Szállító A</span><span class="sxs-lookup"><span data-stu-id="892f3-154">Vendor A</span></span>          |        | <span data-ttu-id="892f3-155">100,000</span><span class="sxs-lookup"><span data-stu-id="892f3-155">100,000</span></span> |
| <span data-ttu-id="892f3-156">Szállító A</span><span class="sxs-lookup"><span data-stu-id="892f3-156">Vendor A</span></span>          | <span data-ttu-id="892f3-157">11,330</span><span class="sxs-lookup"><span data-stu-id="892f3-157">11,330</span></span>  |        |
| <span data-ttu-id="892f3-158">TDS-fizetendő</span><span class="sxs-lookup"><span data-stu-id="892f3-158">TDS payable</span></span>       |        | <span data-ttu-id="892f3-159">10,000</span><span class="sxs-lookup"><span data-stu-id="892f3-159">10,000</span></span>  |
| <span data-ttu-id="892f3-160">Fizetendő pótdíj</span><span class="sxs-lookup"><span data-stu-id="892f3-160">Surcharge payable</span></span> |        | <span data-ttu-id="892f3-161">1000</span><span class="sxs-lookup"><span data-stu-id="892f3-161">1,000</span></span>   |
| <span data-ttu-id="892f3-162">PE-Cess fizetendő</span><span class="sxs-lookup"><span data-stu-id="892f3-162">PE-Cess payable</span></span>   |        | <span data-ttu-id="892f3-163">220</span><span class="sxs-lookup"><span data-stu-id="892f3-163">220</span></span>    |
| <span data-ttu-id="892f3-164">SHE Cess fizetendő</span><span class="sxs-lookup"><span data-stu-id="892f3-164">SHE Cess payable</span></span>  |        | <span data-ttu-id="892f3-165">110</span><span class="sxs-lookup"><span data-stu-id="892f3-165">110</span></span>    |