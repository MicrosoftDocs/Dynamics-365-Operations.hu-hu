---
title: Kettős jelentéskészítés
description: Ez a témakör egy olyan példát mutat be, amely megmutatka, hogyan lehet teljesíteni a követelményeket mind a Nemzetközi pénzügyi jelentési standard (IFRS) -jelentésekben, mind a kötelező jelentésekben a tárgyi eszközlízingben.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: d6daa43178625316a40427728e7e4186691cc13c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229550"
---
# <a name="dual-reporting"></a><span data-ttu-id="f45b6-103">Kettős jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="f45b6-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f45b6-104">Ez a témakör egy olyan példát mutat be, amely megmutatka, hogyan lehet teljesíteni a követelményeket mind a Nemzetközi pénzügyi jelentési standard (IFRS) -jelentésekben, mind a kötelező jelentésekben a tárgyi eszközlízingben.</span><span class="sxs-lookup"><span data-stu-id="f45b6-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="f45b6-105">A Microsoft Dynamics 365 Finance-ben a feladási rétegek ismeretével a példa könnyebben érthető lesz.</span><span class="sxs-lookup"><span data-stu-id="f45b6-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="f45b6-106">Példa</span><span class="sxs-lookup"><span data-stu-id="f45b6-106">Example</span></span>

<span data-ttu-id="f45b6-107">A következő példa az olasz jog szerinti lízinget mutatja be, amelyben a kötelezően előírt jelentés a pénzalap módszert és az IFRS-jelentési módszereket alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="f45b6-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="f45b6-108">A vállalatnak három könyvet kell létrehoznia, hogy mind az olasz, mind az IFRS 16 követelményeit figyelembe tudja venni.</span><span class="sxs-lookup"><span data-stu-id="f45b6-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="f45b6-109">Egy könyv szükséges az IFRS 16 esetében, egy könyv szükséges a törvényi követelményekhez, és egy könyv szükséges a kötelező feladások automatikus sztornírozásához.</span><span class="sxs-lookup"><span data-stu-id="f45b6-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="f45b6-110">A könyveket a következő táblákban látható módon lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="f45b6-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="f45b6-111">**IFRS 16 könyv**</span><span class="sxs-lookup"><span data-stu-id="f45b6-111">**IFRS 16 book**</span></span>

<span data-ttu-id="f45b6-112">Az IFRS 16 könyvet úgy kell beállítani, hogy megfeleljen az IFRS 16 könyvelési szabványának.</span><span class="sxs-lookup"><span data-stu-id="f45b6-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="f45b6-113">A könyvbe feladott összes bejegyzést egy egyéni rétegre adja fel a program.</span><span class="sxs-lookup"><span data-stu-id="f45b6-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="f45b6-114">Név</span><span class="sxs-lookup"><span data-stu-id="f45b6-114">Name</span></span>                                    | <span data-ttu-id="f45b6-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="f45b6-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="f45b6-116">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-116">Book type</span></span>                               | <span data-ttu-id="f45b6-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="f45b6-117">IFRS 16</span></span>        |
| <span data-ttu-id="f45b6-118">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-118">Book description</span></span>                        | <span data-ttu-id="f45b6-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="f45b6-119">IFRS 16</span></span>        |
| <span data-ttu-id="f45b6-120">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-120">Posting Layer</span></span>                           | <span data-ttu-id="f45b6-121">1. egyéni réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-121">Custom layer 1</span></span> |
| <span data-ttu-id="f45b6-122">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="f45b6-122">Lease Type</span></span>                              | <span data-ttu-id="f45b6-123">Finance</span><span class="sxs-lookup"><span data-stu-id="f45b6-123">Finance</span></span>        |
| <span data-ttu-id="f45b6-124">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="f45b6-124">Accounting Framework</span></span>                    | <span data-ttu-id="f45b6-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="f45b6-125">IFRS 16</span></span>        |
| <span data-ttu-id="f45b6-126">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="f45b6-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="f45b6-127">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-127">0.00</span></span>           |
| <span data-ttu-id="f45b6-128">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="f45b6-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="f45b6-129">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-129">0.00</span></span>           |
| <span data-ttu-id="f45b6-130">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="f45b6-130">Short-term threshold</span></span>                    | <span data-ttu-id="f45b6-131">12</span><span class="sxs-lookup"><span data-stu-id="f45b6-131">12</span></span>             |
| <span data-ttu-id="f45b6-132">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="f45b6-132">Low Value Threshold</span></span>                     | <span data-ttu-id="f45b6-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-133">5,000.00</span></span>       |
| <span data-ttu-id="f45b6-134">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="f45b6-134">Pay to Vendor</span></span>                           | <span data-ttu-id="f45b6-135">Nincs</span><span class="sxs-lookup"><span data-stu-id="f45b6-135">No</span></span>             |

<span data-ttu-id="f45b6-136">**Kötelező könyv**</span><span class="sxs-lookup"><span data-stu-id="f45b6-136">**Statutory book**</span></span>

<span data-ttu-id="f45b6-137">A kötelező könyv egy készpénzalapú könyv, ahol a vállalat a lízingköltséget a havi fizetés összegeként adja fel, amely az egyes hónapok bérletét fedezi.</span><span class="sxs-lookup"><span data-stu-id="f45b6-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="f45b6-138">Ez a könyv nem termel használatijog-eszközt (ROU) vagy lízingkötelezettséget.</span><span class="sxs-lookup"><span data-stu-id="f45b6-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="f45b6-139">Név</span><span class="sxs-lookup"><span data-stu-id="f45b6-139">Name</span></span>                                    | <span data-ttu-id="f45b6-140">Leírás</span><span class="sxs-lookup"><span data-stu-id="f45b6-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="f45b6-141">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-141">Book type</span></span>                               | <span data-ttu-id="f45b6-142">Kötelező</span><span class="sxs-lookup"><span data-stu-id="f45b6-142">Statutory</span></span>   |
| <span data-ttu-id="f45b6-143">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-143">Book description</span></span>                        | <span data-ttu-id="f45b6-144">Helyi GAAP</span><span class="sxs-lookup"><span data-stu-id="f45b6-144">Local GAAP</span></span>  |
| <span data-ttu-id="f45b6-145">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-145">Posting Layer</span></span>                           | <span data-ttu-id="f45b6-146">Aktuális</span><span class="sxs-lookup"><span data-stu-id="f45b6-146">Current</span></span>     |
| <span data-ttu-id="f45b6-147">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="f45b6-147">Lease Type</span></span>                              | <span data-ttu-id="f45b6-148">Automatikus</span><span class="sxs-lookup"><span data-stu-id="f45b6-148">Automatic</span></span>   |
| <span data-ttu-id="f45b6-149">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="f45b6-149">Accounting Framework</span></span>                    | <span data-ttu-id="f45b6-150">Készpénzalap</span><span class="sxs-lookup"><span data-stu-id="f45b6-150">Cash basis</span></span>  |
| <span data-ttu-id="f45b6-151">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="f45b6-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="f45b6-152">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-152">0.00</span></span>        |
| <span data-ttu-id="f45b6-153">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="f45b6-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="f45b6-154">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-154">0.00</span></span>        |
| <span data-ttu-id="f45b6-155">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="f45b6-155">Short-term threshold</span></span>                    | <span data-ttu-id="f45b6-156">0</span><span class="sxs-lookup"><span data-stu-id="f45b6-156">0</span></span>           |
| <span data-ttu-id="f45b6-157">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="f45b6-157">Low Value Threshold</span></span>                     | <span data-ttu-id="f45b6-158">0</span><span class="sxs-lookup"><span data-stu-id="f45b6-158">0</span></span>           |
| <span data-ttu-id="f45b6-159">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="f45b6-159">Pay to Vendor</span></span>                           | <span data-ttu-id="f45b6-160">Nincs</span><span class="sxs-lookup"><span data-stu-id="f45b6-160">No</span></span>          |

<span data-ttu-id="f45b6-161">**Kötelező sztornírozási könyv**</span><span class="sxs-lookup"><span data-stu-id="f45b6-161">**Statutory reversal book**</span></span>

<span data-ttu-id="f45b6-162">A kötelező sztornírozási könyvet ugyanúgy kell beállítani, mint a kötelező könyvet.</span><span class="sxs-lookup"><span data-stu-id="f45b6-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="f45b6-163">Név</span><span class="sxs-lookup"><span data-stu-id="f45b6-163">Name</span></span>                                    | <span data-ttu-id="f45b6-164">Leírás</span><span class="sxs-lookup"><span data-stu-id="f45b6-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="f45b6-165">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-165">Book type</span></span>                               | <span data-ttu-id="f45b6-166">Kötelező – Sztornírozás</span><span class="sxs-lookup"><span data-stu-id="f45b6-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="f45b6-167">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-167">Book description</span></span>                        | <span data-ttu-id="f45b6-168">A kötelező könyv sztornírozási könyve</span><span class="sxs-lookup"><span data-stu-id="f45b6-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="f45b6-169">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-169">Posting Layer</span></span>                           | <span data-ttu-id="f45b6-170">1. egyéni réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="f45b6-171">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="f45b6-171">Lease Type</span></span>                              | <span data-ttu-id="f45b6-172">Automatikus</span><span class="sxs-lookup"><span data-stu-id="f45b6-172">Automatic</span></span>                      |
| <span data-ttu-id="f45b6-173">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="f45b6-173">Accounting Framework</span></span>                    | <span data-ttu-id="f45b6-174">Készpénzalap</span><span class="sxs-lookup"><span data-stu-id="f45b6-174">Cash basis</span></span>                     |
| <span data-ttu-id="f45b6-175">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="f45b6-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="f45b6-176">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-176">0.00</span></span>                           |
| <span data-ttu-id="f45b6-177">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="f45b6-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="f45b6-178">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-178">0.00</span></span>                           |
| <span data-ttu-id="f45b6-179">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="f45b6-179">Short-term threshold</span></span>                    | <span data-ttu-id="f45b6-180">0</span><span class="sxs-lookup"><span data-stu-id="f45b6-180">0</span></span>                              |
| <span data-ttu-id="f45b6-181">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="f45b6-181">Low Value Threshold</span></span>                     | <span data-ttu-id="f45b6-182">0</span><span class="sxs-lookup"><span data-stu-id="f45b6-182">0</span></span>                              |
| <span data-ttu-id="f45b6-183">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="f45b6-183">Pay to Vendor</span></span>                           | <span data-ttu-id="f45b6-184">Nincs</span><span class="sxs-lookup"><span data-stu-id="f45b6-184">No</span></span>                             |

<span data-ttu-id="f45b6-185">Ez a példa egy olyan lízing létrejöttét hozta létre, amelynek a következő beállításait találja az **Általános** és a **Fizetési ütemezés sorai** lapon.</span><span class="sxs-lookup"><span data-stu-id="f45b6-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="f45b6-186">**Általános fül**</span><span class="sxs-lookup"><span data-stu-id="f45b6-186">**General tab**</span></span>

| <span data-ttu-id="f45b6-187">Mező</span><span class="sxs-lookup"><span data-stu-id="f45b6-187">Field</span></span>                      | <span data-ttu-id="f45b6-188">Érték</span><span class="sxs-lookup"><span data-stu-id="f45b6-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="f45b6-189">Járulékos kamatláb</span><span class="sxs-lookup"><span data-stu-id="f45b6-189">Incremental borrowing rate</span></span> | <span data-ttu-id="f45b6-190">5%</span><span class="sxs-lookup"><span data-stu-id="f45b6-190">5%</span></span>               |
| <span data-ttu-id="f45b6-191">Kezdési dátum</span><span class="sxs-lookup"><span data-stu-id="f45b6-191">Commencement date</span></span>          | <span data-ttu-id="f45b6-192">2020.01.01.</span><span class="sxs-lookup"><span data-stu-id="f45b6-192">1/1/2020</span></span>         |
| <span data-ttu-id="f45b6-193">Lízingcsoport</span><span class="sxs-lookup"><span data-stu-id="f45b6-193">Lease group</span></span>                | <span data-ttu-id="f45b6-194">Épületek</span><span class="sxs-lookup"><span data-stu-id="f45b6-194">Buildings</span></span>        |
| <span data-ttu-id="f45b6-195">Szállító</span><span class="sxs-lookup"><span data-stu-id="f45b6-195">Vendor</span></span>                     | <span data-ttu-id="f45b6-196">1001</span><span class="sxs-lookup"><span data-stu-id="f45b6-196">1001</span></span>             |
| <span data-ttu-id="f45b6-197">Az eszköz valós értéke</span><span class="sxs-lookup"><span data-stu-id="f45b6-197">Fair value of the asset</span></span>    | <span data-ttu-id="f45b6-198">245,000</span><span class="sxs-lookup"><span data-stu-id="f45b6-198">245,000</span></span>          |
| <span data-ttu-id="f45b6-199">Eszköz hasznos élettartama</span><span class="sxs-lookup"><span data-stu-id="f45b6-199">Asset useful life</span></span>          | <span data-ttu-id="f45b6-200">120</span><span class="sxs-lookup"><span data-stu-id="f45b6-200">120</span></span>              |
| <span data-ttu-id="f45b6-201">Annuitás típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-201">Annuity type</span></span>               | <span data-ttu-id="f45b6-202">Szokásos annuitás</span><span class="sxs-lookup"><span data-stu-id="f45b6-202">Ordinary annuity</span></span> |
| <span data-ttu-id="f45b6-203">Összetételi intervallum</span><span class="sxs-lookup"><span data-stu-id="f45b6-203">Compounding interval</span></span>       | <span data-ttu-id="f45b6-204">Havi</span><span class="sxs-lookup"><span data-stu-id="f45b6-204">Monthly</span></span>          |

<span data-ttu-id="f45b6-205">**Kifizetési lista sorai fül**</span><span class="sxs-lookup"><span data-stu-id="f45b6-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="f45b6-206">Mező</span><span class="sxs-lookup"><span data-stu-id="f45b6-206">Field</span></span>             | <span data-ttu-id="f45b6-207">Érték</span><span class="sxs-lookup"><span data-stu-id="f45b6-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="f45b6-208">Kezdés dátuma</span><span class="sxs-lookup"><span data-stu-id="f45b6-208">Start date</span></span>        | <span data-ttu-id="f45b6-209">2020.01.01.</span><span class="sxs-lookup"><span data-stu-id="f45b6-209">1/1/2020</span></span>   |
| <span data-ttu-id="f45b6-210">Időszak intervalluma</span><span class="sxs-lookup"><span data-stu-id="f45b6-210">Period interval</span></span>   | <span data-ttu-id="f45b6-211">Hónap</span><span class="sxs-lookup"><span data-stu-id="f45b6-211">Months</span></span>     |
| <span data-ttu-id="f45b6-212">Időszakok</span><span class="sxs-lookup"><span data-stu-id="f45b6-212">Periods</span></span>           | <span data-ttu-id="f45b6-213">24</span><span class="sxs-lookup"><span data-stu-id="f45b6-213">24</span></span>         |
| <span data-ttu-id="f45b6-214">Befejezés</span><span class="sxs-lookup"><span data-stu-id="f45b6-214">End date</span></span>          | <span data-ttu-id="f45b6-215">2020.12.31.</span><span class="sxs-lookup"><span data-stu-id="f45b6-215">12/31/2020</span></span> |
| <span data-ttu-id="f45b6-216">Fizetés gyakorisága</span><span class="sxs-lookup"><span data-stu-id="f45b6-216">Payment frequency</span></span> | <span data-ttu-id="f45b6-217">Havi</span><span class="sxs-lookup"><span data-stu-id="f45b6-217">Monthly</span></span>    |
| <span data-ttu-id="f45b6-218">Fizetés összege</span><span class="sxs-lookup"><span data-stu-id="f45b6-218">Payment amount</span></span>    | <span data-ttu-id="f45b6-219">1000</span><span class="sxs-lookup"><span data-stu-id="f45b6-219">1,000</span></span>      |

<span data-ttu-id="f45b6-220">Ha ezt a lízinget két keretrendszerben szeretné elszámolni, akkor egy aktuális feladási réteget és egy egyéni feladási réteget kell használnia.</span><span class="sxs-lookup"><span data-stu-id="f45b6-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="f45b6-221">A következő táblázat egy példát mutat be az összes naplóbejegyzésről, amely szükséges az összes jelentési standard alatt lévő pénzügyek helyes megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f45b6-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="f45b6-222">Ezt követően a lízing első hónapjához tartozó valamennyi naplóbejegyzés részletes leírása jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="f45b6-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="f45b6-223">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="f45b6-224">Leírás</span><span class="sxs-lookup"><span data-stu-id="f45b6-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="f45b6-225">Kötelező könyv (jelenlegi réteg)</span><span class="sxs-lookup"><span data-stu-id="f45b6-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="f45b6-226">Aktuális réteg összesen</span><span class="sxs-lookup"><span data-stu-id="f45b6-226">Current layer total</span></span></th>
<th><span data-ttu-id="f45b6-227">Sztornírozási könyv (egyéni réteg)</span><span class="sxs-lookup"><span data-stu-id="f45b6-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="f45b6-228">IFRS 16 könyv (egyéni réteg)</span><span class="sxs-lookup"><span data-stu-id="f45b6-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="f45b6-229">Aktuális réteg + egyéni réteg összesen</span><span class="sxs-lookup"><span data-stu-id="f45b6-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="f45b6-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="f45b6-230">JE-100</span></span></th>
<th><span data-ttu-id="f45b6-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="f45b6-231">JE-110</span></span></th>
<th><span data-ttu-id="f45b6-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="f45b6-232">JE-120</span></span></th>
<th><span data-ttu-id="f45b6-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="f45b6-233">JE-130</span></span></th>
<th><span data-ttu-id="f45b6-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="f45b6-234">JE-140</span></span></th>
<th><span data-ttu-id="f45b6-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="f45b6-235">JE-150</span></span></th>
<th><span data-ttu-id="f45b6-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="f45b6-236">JE-160</span></span></th>
<th><span data-ttu-id="f45b6-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="f45b6-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="f45b6-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="f45b6-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="f45b6-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="f45b6-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="f45b6-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="f45b6-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="f45b6-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="f45b6-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f45b6-246">1</span><span class="sxs-lookup"><span data-stu-id="f45b6-246">1</span></span></td>
<td><span data-ttu-id="f45b6-247">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-247">Lease expense</span></span></td>
<td><span data-ttu-id="f45b6-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-249">1,000.00</span></span></td>
<td><span data-ttu-id="f45b6-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-251">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-252">2</span><span class="sxs-lookup"><span data-stu-id="f45b6-252">2</span></span></td>
<td><span data-ttu-id="f45b6-253">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-254">3.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-255">3.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-256">3.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-257">3</span><span class="sxs-lookup"><span data-stu-id="f45b6-257">3</span></span></td>
<td><span data-ttu-id="f45b6-258">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-259">5.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-260">5.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-261">5.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-262">4</span><span class="sxs-lookup"><span data-stu-id="f45b6-262">4</span></span></td>
<td><span data-ttu-id="f45b6-263">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="f45b6-263">Clearing account</span></span></td>
<td><span data-ttu-id="f45b6-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-264">-1,000.00</span></span></td>
<td><span data-ttu-id="f45b6-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-266">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-266">0.00</span></span></td>
<td><span data-ttu-id="f45b6-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-269">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-270">5</span><span class="sxs-lookup"><span data-stu-id="f45b6-270">5</span></span></td>
<td><span data-ttu-id="f45b6-271">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="f45b6-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-272">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-272">-1,008.00</span></span></td>
<td><span data-ttu-id="f45b6-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-273">1,008.00</span></span></td>
<td><span data-ttu-id="f45b6-274">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-275">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-276">6</span><span class="sxs-lookup"><span data-stu-id="f45b6-276">6</span></span></td>
<td><span data-ttu-id="f45b6-277">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="f45b6-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-278">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="f45b6-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-281">7</span><span class="sxs-lookup"><span data-stu-id="f45b6-281">7</span></span></td>
<td><span data-ttu-id="f45b6-282">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="f45b6-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-283">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-284">-22.794,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-284">-22,794.00</span></span></td>
<td><span data-ttu-id="f45b6-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-285">1,000.00</span></span></td>
<td><span data-ttu-id="f45b6-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="f45b6-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-287">-21.888,87</span><span class="sxs-lookup"><span data-stu-id="f45b6-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-288">8</span><span class="sxs-lookup"><span data-stu-id="f45b6-288">8</span></span></td>
<td><span data-ttu-id="f45b6-289">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-290">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-291">94.97</span><span class="sxs-lookup"><span data-stu-id="f45b6-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-292">94.97</span><span class="sxs-lookup"><span data-stu-id="f45b6-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-293">9</span><span class="sxs-lookup"><span data-stu-id="f45b6-293">9</span></span></td>
<td><span data-ttu-id="f45b6-294">Készpénz</span><span class="sxs-lookup"><span data-stu-id="f45b6-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-295">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-295">-1,008.00</span></span></td>
<td><span data-ttu-id="f45b6-296">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-297">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-298">10</span><span class="sxs-lookup"><span data-stu-id="f45b6-298">10</span></span></td>
<td><span data-ttu-id="f45b6-299">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="f45b6-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-300">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-301">949.75</span><span class="sxs-lookup"><span data-stu-id="f45b6-301">949.75</span></span></td>
<td><span data-ttu-id="f45b6-302">949.75</span><span class="sxs-lookup"><span data-stu-id="f45b6-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-303">11</span><span class="sxs-lookup"><span data-stu-id="f45b6-303">11</span></span></td>
<td><span data-ttu-id="f45b6-304">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="f45b6-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-305">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="f45b6-306">-949.75</span></span></td>
<td><span data-ttu-id="f45b6-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="f45b6-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f45b6-308">Az előző táblában látható, hogy három könyv szükséges a kötelező jelentéshez és az IFRS-jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="f45b6-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="f45b6-309">A kötelező könyv rögzíti a lízingdíjfizetés az aktuális rétegben a pénzforgalmi elszámolás szabályainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="f45b6-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="f45b6-310">A kötelező sztornírozási könyv a kötelező napló bejegyzéseit visszavonja.</span><span class="sxs-lookup"><span data-stu-id="f45b6-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="f45b6-311">Az IFRS 16 könyv létrehozza az IFRS 16 alapján szükséges naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="f45b6-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="f45b6-312">A lízinget csak egy alkalommal kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="f45b6-312">You must enter a lease only one time.</span></span> <span data-ttu-id="f45b6-313">Ezután megnyithatja a **Könyvek** lapot, amelyen megtekintheti a lízinghez társított könyveket.</span><span class="sxs-lookup"><span data-stu-id="f45b6-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="f45b6-314">Amikor létrehozza a könyveket, mindháromnak ugyanahhoz a lízingrekordhoz kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="f45b6-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="f45b6-315">Az első naplóbejegyzés a kötelező könyv szerinti lízingköltséget rögzíti.</span><span class="sxs-lookup"><span data-stu-id="f45b6-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="f45b6-316">A kifizetéseket egy kötegben is létrehozhatja, vagy kiválaszthatja a kötelező könyv szerinti kifizetési ütemezéseket.</span><span class="sxs-lookup"><span data-stu-id="f45b6-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="f45b6-317">Ebben a példában a következő naplóbejegyzés készül a kötelező könyveléshez a fizetési ütemezésből.</span><span class="sxs-lookup"><span data-stu-id="f45b6-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="f45b6-318">Lízingdíjfizetés – 2020.01.31. – JE 100</span><span class="sxs-lookup"><span data-stu-id="f45b6-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="f45b6-319">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-319">Account type</span></span> | <span data-ttu-id="f45b6-320">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-320">Account number</span></span> | <span data-ttu-id="f45b6-321">Réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-321">Layer</span></span>   | <span data-ttu-id="f45b6-322">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-322">Account description</span></span> | <span data-ttu-id="f45b6-323">Tartozik</span><span class="sxs-lookup"><span data-stu-id="f45b6-323">Debit</span></span>    | <span data-ttu-id="f45b6-324">Követel</span><span class="sxs-lookup"><span data-stu-id="f45b6-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="f45b6-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-325">Ledger</span></span>       | <span data-ttu-id="f45b6-326">1</span><span class="sxs-lookup"><span data-stu-id="f45b6-326">1</span></span>              | <span data-ttu-id="f45b6-327">Aktuális</span><span class="sxs-lookup"><span data-stu-id="f45b6-327">Current</span></span> | <span data-ttu-id="f45b6-328">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-328">Lease expense</span></span>       | <span data-ttu-id="f45b6-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-329">1,000.00</span></span> |          |
| <span data-ttu-id="f45b6-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-330">Ledger</span></span>       | <span data-ttu-id="f45b6-331">4</span><span class="sxs-lookup"><span data-stu-id="f45b6-331">4</span></span>              | <span data-ttu-id="f45b6-332">Aktuális</span><span class="sxs-lookup"><span data-stu-id="f45b6-332">Current</span></span> | <span data-ttu-id="f45b6-333">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="f45b6-333">Clearing account</span></span>    |          | <span data-ttu-id="f45b6-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-334">1,000.00</span></span> |

<span data-ttu-id="f45b6-335">A Kötelezettségekkel kapcsolatos adminisztrátorok a standard Dynamics 365 funkciót használják egy számla létrehozásához, amely a lízing külső Eszközlízingje esetén fizetendő.</span><span class="sxs-lookup"><span data-stu-id="f45b6-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="f45b6-336">Ha viszont a **Lízingköltség** lehetőséget nem tartozási számlaként választja, akkor a Kötelezettségek adminisztrátora egy elszámolási számlát választ a következő bejegyzés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="f45b6-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="f45b6-337">AP-folyamat – 2020.01.31. – JE 110</span><span class="sxs-lookup"><span data-stu-id="f45b6-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="f45b6-338">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-338">Account type</span></span> | <span data-ttu-id="f45b6-339">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-339">Account number</span></span> | <span data-ttu-id="f45b6-340">Réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-340">Layer</span></span>   | <span data-ttu-id="f45b6-341">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-341">Account description</span></span> | <span data-ttu-id="f45b6-342">Tartozik</span><span class="sxs-lookup"><span data-stu-id="f45b6-342">Debit</span></span>    | <span data-ttu-id="f45b6-343">Követel</span><span class="sxs-lookup"><span data-stu-id="f45b6-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="f45b6-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-344">Ledger</span></span>       | <span data-ttu-id="f45b6-345">4</span><span class="sxs-lookup"><span data-stu-id="f45b6-345">4</span></span>              | <span data-ttu-id="f45b6-346">Aktuális</span><span class="sxs-lookup"><span data-stu-id="f45b6-346">Current</span></span> | <span data-ttu-id="f45b6-347">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="f45b6-347">Clearing account</span></span>    | <span data-ttu-id="f45b6-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-348">1,000.00</span></span> |          |
| <span data-ttu-id="f45b6-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-349">Ledger</span></span>       | <span data-ttu-id="f45b6-350">2</span><span class="sxs-lookup"><span data-stu-id="f45b6-350">2</span></span>              | <span data-ttu-id="f45b6-351">Aktuális</span><span class="sxs-lookup"><span data-stu-id="f45b6-351">Current</span></span> | <span data-ttu-id="f45b6-352">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-352">Bank fee</span></span>            | <span data-ttu-id="f45b6-353">3.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-353">3.00</span></span>     |          |
| <span data-ttu-id="f45b6-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-354">Ledger</span></span>       | <span data-ttu-id="f45b6-355">3</span><span class="sxs-lookup"><span data-stu-id="f45b6-355">3</span></span>              | <span data-ttu-id="f45b6-356">Aktuális</span><span class="sxs-lookup"><span data-stu-id="f45b6-356">Current</span></span> | <span data-ttu-id="f45b6-357">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-357">VAT expense</span></span>         | <span data-ttu-id="f45b6-358">5.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-358">5.00</span></span>     |          |
| <span data-ttu-id="f45b6-359">Szállító</span><span class="sxs-lookup"><span data-stu-id="f45b6-359">Vendor</span></span>       | <span data-ttu-id="f45b6-360">5</span><span class="sxs-lookup"><span data-stu-id="f45b6-360">5</span></span>              | <span data-ttu-id="f45b6-361">Aktuális</span><span class="sxs-lookup"><span data-stu-id="f45b6-361">Current</span></span> | <span data-ttu-id="f45b6-362">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="f45b6-362">Accounts payable</span></span>    |          | <span data-ttu-id="f45b6-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-363">1,008.00</span></span> |

<span data-ttu-id="f45b6-364">Amikor a kimutatást kiállítják a szállítónak, a szokásos fizetési folyamatot követik.</span><span class="sxs-lookup"><span data-stu-id="f45b6-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="f45b6-365">A folyamat során a következő naplóbejegyzés jön létre.</span><span class="sxs-lookup"><span data-stu-id="f45b6-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="f45b6-366">Készpénzes fizetés – 2020.01.31. – JE 120</span><span class="sxs-lookup"><span data-stu-id="f45b6-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="f45b6-367">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-367">Account type</span></span> | <span data-ttu-id="f45b6-368">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-368">Account number</span></span> | <span data-ttu-id="f45b6-369">Réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-369">Layer</span></span>   | <span data-ttu-id="f45b6-370">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-370">Account description</span></span> | <span data-ttu-id="f45b6-371">Tartozik</span><span class="sxs-lookup"><span data-stu-id="f45b6-371">Debit</span></span>    | <span data-ttu-id="f45b6-372">Követel</span><span class="sxs-lookup"><span data-stu-id="f45b6-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="f45b6-373">Szállító</span><span class="sxs-lookup"><span data-stu-id="f45b6-373">Vendor</span></span>       | <span data-ttu-id="f45b6-374">5</span><span class="sxs-lookup"><span data-stu-id="f45b6-374">5</span></span>              | <span data-ttu-id="f45b6-375">Aktuális</span><span class="sxs-lookup"><span data-stu-id="f45b6-375">Current</span></span> | <span data-ttu-id="f45b6-376">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="f45b6-376">Accounts Payable</span></span>    | <span data-ttu-id="f45b6-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-377">1,008.00</span></span> |          |
| <span data-ttu-id="f45b6-378">Bank</span><span class="sxs-lookup"><span data-stu-id="f45b6-378">Bank</span></span>         | <span data-ttu-id="f45b6-379">9</span><span class="sxs-lookup"><span data-stu-id="f45b6-379">9</span></span>              | <span data-ttu-id="f45b6-380">Aktuális</span><span class="sxs-lookup"><span data-stu-id="f45b6-380">Current</span></span> | <span data-ttu-id="f45b6-381">Készpénz</span><span class="sxs-lookup"><span data-stu-id="f45b6-381">Cash</span></span>                |          | <span data-ttu-id="f45b6-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-382">1,008.00</span></span> |

<span data-ttu-id="f45b6-383">Ezen a ponton már teljes mértékben elszámolta ezt a lízinget a kötelező jelentési követelmények között, és a jelenlegi réteg használatával generálhat egy főkönyvi kivonatot.</span><span class="sxs-lookup"><span data-stu-id="f45b6-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="f45b6-384">A rendszer a következő számú főkönyvi kivonatot küld vissza.</span><span class="sxs-lookup"><span data-stu-id="f45b6-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="f45b6-385">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="f45b6-386">Leírás</span><span class="sxs-lookup"><span data-stu-id="f45b6-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="f45b6-387">Kötelező könyv (jelenlegi réteg)</span><span class="sxs-lookup"><span data-stu-id="f45b6-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="f45b6-388">Aktuális réteg összesen</span><span class="sxs-lookup"><span data-stu-id="f45b6-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="f45b6-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="f45b6-389">JE-100</span></span></th>
<th><span data-ttu-id="f45b6-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="f45b6-390">JE-110</span></span></th>
<th><span data-ttu-id="f45b6-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="f45b6-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="f45b6-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="f45b6-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="f45b6-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="f45b6-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f45b6-395">1</span><span class="sxs-lookup"><span data-stu-id="f45b6-395">1</span></span></td>
<td><span data-ttu-id="f45b6-396">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-396">Lease expense</span></span></td>
<td><span data-ttu-id="f45b6-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-399">2</span><span class="sxs-lookup"><span data-stu-id="f45b6-399">2</span></span></td>
<td><span data-ttu-id="f45b6-400">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-401">3.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-402">3.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-403">3</span><span class="sxs-lookup"><span data-stu-id="f45b6-403">3</span></span></td>
<td><span data-ttu-id="f45b6-404">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-405">5.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-406">5.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-407">4</span><span class="sxs-lookup"><span data-stu-id="f45b6-407">4</span></span></td>
<td><span data-ttu-id="f45b6-408">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="f45b6-408">Clearing account</span></span></td>
<td><span data-ttu-id="f45b6-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-409">-1,000.00</span></span></td>
<td><span data-ttu-id="f45b6-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-411">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-412">5</span><span class="sxs-lookup"><span data-stu-id="f45b6-412">5</span></span></td>
<td><span data-ttu-id="f45b6-413">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="f45b6-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="f45b6-414">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-414">-1,008.00</span></span></td>
<td><span data-ttu-id="f45b6-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-415">1,008.00</span></span></td>
<td><span data-ttu-id="f45b6-416">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-417">6</span><span class="sxs-lookup"><span data-stu-id="f45b6-417">6</span></span></td>
<td><span data-ttu-id="f45b6-418">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="f45b6-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-419">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-420">7</span><span class="sxs-lookup"><span data-stu-id="f45b6-420">7</span></span></td>
<td><span data-ttu-id="f45b6-421">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="f45b6-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-422">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-423">8</span><span class="sxs-lookup"><span data-stu-id="f45b6-423">8</span></span></td>
<td><span data-ttu-id="f45b6-424">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-425">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-426">9</span><span class="sxs-lookup"><span data-stu-id="f45b6-426">9</span></span></td>
<td><span data-ttu-id="f45b6-427">Készpénz</span><span class="sxs-lookup"><span data-stu-id="f45b6-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-428">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-428">-1,008.00</span></span></td>
<td><span data-ttu-id="f45b6-429">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-430">10</span><span class="sxs-lookup"><span data-stu-id="f45b6-430">10</span></span></td>
<td><span data-ttu-id="f45b6-431">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="f45b6-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-432">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="f45b6-433">11</span><span class="sxs-lookup"><span data-stu-id="f45b6-433">11</span></span></td>
<td><span data-ttu-id="f45b6-434">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="f45b6-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="f45b6-435">0,00</span><span class="sxs-lookup"><span data-stu-id="f45b6-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f45b6-436">Ha azt szeretné, hogy az IFRS 16 számokkal ugyanaz a főkönyvi kivonat fusson, akkor a kötelező könyvelési napló bejegyzéseit sztornírozni kell, és az IFRS 16 napló bejegyzéseit fel kell adni.</span><span class="sxs-lookup"><span data-stu-id="f45b6-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="f45b6-437">A kötelező naplóbejegyzések sztornírozásához ez a példa olyan kötelező sztornírozási könyvet tartalmaz, amelynek ugyanaz a beállítása, mint a kötelező könyvé, de ellenkező feladási profilú.</span><span class="sxs-lookup"><span data-stu-id="f45b6-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="f45b6-438">Például a kötelező könyv *megterhelt* egy lízingköltség-számlát, de a sztornírozási könyv *jóváírja* ezt a számlát.</span><span class="sxs-lookup"><span data-stu-id="f45b6-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="f45b6-439">Ezek a kapcsolatok könnyen meghatározhatók az **Eszközlízing paraméterek** oldalon (**Eszközlízing paraméterek \> Beállítás \> Eszközlízing paraméterek**) található Eszközlízing feladási számlákban.</span><span class="sxs-lookup"><span data-stu-id="f45b6-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="f45b6-440">Ha a sztornírozási könyvhöz a kötelező könyvhöz használt eljárást használja, a következő naplóbejegyzés jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="f45b6-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="f45b6-441">A különbség az, hogy a sztornírozási könyv a sztornírozási bejegyzéseket a kötelező könyvből állítja be.</span><span class="sxs-lookup"><span data-stu-id="f45b6-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="f45b6-442">A sztornírozási bejegyzések az egyéni rétegre is vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="f45b6-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="f45b6-443">Ha az aktuális rétegen fut egy főkönyvi kivonat, a sztornírozó naplóbejegyzések nem szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="f45b6-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="f45b6-444">Lízingdíjfizetés – 2020.01.31. – JE 130</span><span class="sxs-lookup"><span data-stu-id="f45b6-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="f45b6-445">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-445">Account type</span></span> | <span data-ttu-id="f45b6-446">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-446">Account number</span></span> | <span data-ttu-id="f45b6-447">Réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-447">Layer</span></span>  | <span data-ttu-id="f45b6-448">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-448">Account description</span></span> | <span data-ttu-id="f45b6-449">Tartozik</span><span class="sxs-lookup"><span data-stu-id="f45b6-449">Debit</span></span>    | <span data-ttu-id="f45b6-450">Követel</span><span class="sxs-lookup"><span data-stu-id="f45b6-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="f45b6-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-451">Ledger</span></span>       | <span data-ttu-id="f45b6-452">4</span><span class="sxs-lookup"><span data-stu-id="f45b6-452">4</span></span>              | <span data-ttu-id="f45b6-453">Egyéni</span><span class="sxs-lookup"><span data-stu-id="f45b6-453">Custom</span></span> | <span data-ttu-id="f45b6-454">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="f45b6-454">Clearing account</span></span>    | <span data-ttu-id="f45b6-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-455">1,000.00</span></span> |          |
| <span data-ttu-id="f45b6-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-456">Ledger</span></span>       | <span data-ttu-id="f45b6-457">1</span><span class="sxs-lookup"><span data-stu-id="f45b6-457">1</span></span>              | <span data-ttu-id="f45b6-458">Egyéni</span><span class="sxs-lookup"><span data-stu-id="f45b6-458">Custom</span></span> | <span data-ttu-id="f45b6-459">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-459">Lease expense</span></span>       |          | <span data-ttu-id="f45b6-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-460">1,000.00</span></span> |

<span data-ttu-id="f45b6-461">Most, hogy megszüntette a kötelező naplóbejegyzéseket, az IFRS 16 az IFRS 16-ban lefoglalja az összes naplóbejegyzést.</span><span class="sxs-lookup"><span data-stu-id="f45b6-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="f45b6-462">Ezek a bejegyzések tartalmazzák a ROU-eszköz és a kötelezettség kezdeti megjelenítését, valamint a kamat- és értékcsökkenési nyilvántartást.</span><span class="sxs-lookup"><span data-stu-id="f45b6-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="f45b6-463">Kezdeti elszámolás – 2020.01.01. – JE 140</span><span class="sxs-lookup"><span data-stu-id="f45b6-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="f45b6-464">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-464">Account type</span></span> | <span data-ttu-id="f45b6-465">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-465">Account number</span></span> | <span data-ttu-id="f45b6-466">Réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-466">Layer</span></span>  | <span data-ttu-id="f45b6-467">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-467">Account description</span></span>      | <span data-ttu-id="f45b6-468">Tartozik</span><span class="sxs-lookup"><span data-stu-id="f45b6-468">Debit</span></span>     | <span data-ttu-id="f45b6-469">Követel</span><span class="sxs-lookup"><span data-stu-id="f45b6-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="f45b6-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-470">Ledger</span></span>       | <span data-ttu-id="f45b6-471">6</span><span class="sxs-lookup"><span data-stu-id="f45b6-471">6</span></span>              | <span data-ttu-id="f45b6-472">Egyéni</span><span class="sxs-lookup"><span data-stu-id="f45b6-472">Custom</span></span> | <span data-ttu-id="f45b6-473">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="f45b6-473">ROU Asset</span></span>                | <span data-ttu-id="f45b6-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="f45b6-474">22,793.90</span></span> |           |
| <span data-ttu-id="f45b6-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-475">Ledger</span></span>       | <span data-ttu-id="f45b6-476">7</span><span class="sxs-lookup"><span data-stu-id="f45b6-476">7</span></span>              | <span data-ttu-id="f45b6-477">Egyéni</span><span class="sxs-lookup"><span data-stu-id="f45b6-477">Custom</span></span> | <span data-ttu-id="f45b6-478">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="f45b6-478">Finance lease obligation</span></span> |           | <span data-ttu-id="f45b6-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="f45b6-479">22,793.90</span></span> |

<span data-ttu-id="f45b6-480">A lízingdíjfizetés a többi lízingdíjfizetéshez hasonlóan kerül feladása.</span><span class="sxs-lookup"><span data-stu-id="f45b6-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="f45b6-481">A kiegyenlítési számla használatának oka annak biztosítása, hogy a készpénz csak egyszer kerüljön jóváírásra.</span><span class="sxs-lookup"><span data-stu-id="f45b6-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="f45b6-482">Lízingdíjfizetés – 2020.01.31. – JE 150</span><span class="sxs-lookup"><span data-stu-id="f45b6-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="f45b6-483">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-483">Account type</span></span> | <span data-ttu-id="f45b6-484">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-484">Account number</span></span> | <span data-ttu-id="f45b6-485">Réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-485">Layer</span></span>  | <span data-ttu-id="f45b6-486">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-486">Account description</span></span>      | <span data-ttu-id="f45b6-487">Tartozik</span><span class="sxs-lookup"><span data-stu-id="f45b6-487">Debit</span></span>    | <span data-ttu-id="f45b6-488">Követel</span><span class="sxs-lookup"><span data-stu-id="f45b6-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="f45b6-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-489">Ledger</span></span>       | <span data-ttu-id="f45b6-490">7</span><span class="sxs-lookup"><span data-stu-id="f45b6-490">7</span></span>              | <span data-ttu-id="f45b6-491">Egyéni</span><span class="sxs-lookup"><span data-stu-id="f45b6-491">Custom</span></span> | <span data-ttu-id="f45b6-492">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="f45b6-492">Finance lease obligation</span></span> | <span data-ttu-id="f45b6-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-493">1,000.00</span></span> |          |
| <span data-ttu-id="f45b6-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-494">Ledger</span></span>       | <span data-ttu-id="f45b6-495">4</span><span class="sxs-lookup"><span data-stu-id="f45b6-495">4</span></span>              | <span data-ttu-id="f45b6-496">Egyéni</span><span class="sxs-lookup"><span data-stu-id="f45b6-496">Custom</span></span> | <span data-ttu-id="f45b6-497">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="f45b6-497">Clearing account</span></span>         |          | <span data-ttu-id="f45b6-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-498">1,000.00</span></span> |

<span data-ttu-id="f45b6-499">A kamatráfordítási naplóbejegyzés a kötelezettség amortizációs ütemezéséből jön létre.</span><span class="sxs-lookup"><span data-stu-id="f45b6-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="f45b6-500">Kamatköltség – 2020.01.31. – JE 160</span><span class="sxs-lookup"><span data-stu-id="f45b6-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="f45b6-501">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-501">Account type</span></span> | <span data-ttu-id="f45b6-502">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-502">Account number</span></span> | <span data-ttu-id="f45b6-503">Réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-503">Layer</span></span>  | <span data-ttu-id="f45b6-504">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-504">Account description</span></span>      | <span data-ttu-id="f45b6-505">Tartozik</span><span class="sxs-lookup"><span data-stu-id="f45b6-505">Debit</span></span> | <span data-ttu-id="f45b6-506">Követel</span><span class="sxs-lookup"><span data-stu-id="f45b6-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="f45b6-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-507">Ledger</span></span>       | <span data-ttu-id="f45b6-508">8</span><span class="sxs-lookup"><span data-stu-id="f45b6-508">8</span></span>              | <span data-ttu-id="f45b6-509">Egyéni</span><span class="sxs-lookup"><span data-stu-id="f45b6-509">Custom</span></span> | <span data-ttu-id="f45b6-510">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-510">Interest expense</span></span>         | <span data-ttu-id="f45b6-511">94.97</span><span class="sxs-lookup"><span data-stu-id="f45b6-511">94.97</span></span> |        |
| <span data-ttu-id="f45b6-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-512">Ledger</span></span>       | <span data-ttu-id="f45b6-513">7</span><span class="sxs-lookup"><span data-stu-id="f45b6-513">7</span></span>              | <span data-ttu-id="f45b6-514">Egyéni</span><span class="sxs-lookup"><span data-stu-id="f45b6-514">Custom</span></span> | <span data-ttu-id="f45b6-515">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="f45b6-515">Finance lease obligation</span></span> |       | <span data-ttu-id="f45b6-516">94.97</span><span class="sxs-lookup"><span data-stu-id="f45b6-516">94.97</span></span>  |

<span data-ttu-id="f45b6-517">Az értékcsökkenési költség-naplóbejegyzés az eszközértékcsökkenési ütemezéséből jön létre.</span><span class="sxs-lookup"><span data-stu-id="f45b6-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="f45b6-518">Értékcsökkenés költsége – 2020.01.31. – JE 170</span><span class="sxs-lookup"><span data-stu-id="f45b6-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="f45b6-519">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="f45b6-519">Account type</span></span> | <span data-ttu-id="f45b6-520">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-520">Account number</span></span> | <span data-ttu-id="f45b6-521">Réteg</span><span class="sxs-lookup"><span data-stu-id="f45b6-521">Layer</span></span>  | <span data-ttu-id="f45b6-522">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="f45b6-522">Account description</span></span>      | <span data-ttu-id="f45b6-523">Tartozik</span><span class="sxs-lookup"><span data-stu-id="f45b6-523">Debit</span></span>  | <span data-ttu-id="f45b6-524">Követel</span><span class="sxs-lookup"><span data-stu-id="f45b6-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="f45b6-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-525">Ledger</span></span>       | <span data-ttu-id="f45b6-526">10</span><span class="sxs-lookup"><span data-stu-id="f45b6-526">10</span></span>             | <span data-ttu-id="f45b6-527">Egyéni</span><span class="sxs-lookup"><span data-stu-id="f45b6-527">Custom</span></span> | <span data-ttu-id="f45b6-528">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="f45b6-528">Depreciation expense</span></span>     | <span data-ttu-id="f45b6-529">949.75</span><span class="sxs-lookup"><span data-stu-id="f45b6-529">949.75</span></span> |        |
| <span data-ttu-id="f45b6-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="f45b6-530">Ledger</span></span>       | <span data-ttu-id="f45b6-531">11</span><span class="sxs-lookup"><span data-stu-id="f45b6-531">11</span></span>             | <span data-ttu-id="f45b6-532">Egyéni</span><span class="sxs-lookup"><span data-stu-id="f45b6-532">Custom</span></span> | <span data-ttu-id="f45b6-533">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="f45b6-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="f45b6-534">949.75</span><span class="sxs-lookup"><span data-stu-id="f45b6-534">949.75</span></span> |

<span data-ttu-id="f45b6-535">Miután az összes naplóbejegyzést létrehozta és feladta, akkor a következő „1. egyéni réteg” értékeket fogja látni.</span><span class="sxs-lookup"><span data-stu-id="f45b6-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="f45b6-536">Ne feledje, hogy az utolsó oszlop tartalmazza a banki díjat, az áfaköltséget (ÁFA) és az előző rétegből származó készpénz csökkentését, de nem tartalmazza a kötelező jelentési naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="f45b6-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="f45b6-537">Ezért valódi kettős jelentéskészítési képességeket érhet el.</span><span class="sxs-lookup"><span data-stu-id="f45b6-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="f45b6-538">Ezen a ponton a vállalatnak csak futtatnia kell a főkönyvi kivonatot, és kombinálnia kell az aktuális réteget és az egyéni réteget az IFRS főkönyvi kivonat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="f45b6-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="f45b6-539">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="f45b6-539">Account No</span></span> | <span data-ttu-id="f45b6-540">Leírás</span><span class="sxs-lookup"><span data-stu-id="f45b6-540">Description</span></span>              | <span data-ttu-id="f45b6-541">Kötelező könyv\-Aktuális réteg\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="f45b6-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="f45b6-542">Kötelező könyv\-Aktuális réteg\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="f45b6-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="f45b6-543">Kötelező könyv\-Aktuális réteg\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="f45b6-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="f45b6-544">Aktuális réteg \- Összesen</span><span class="sxs-lookup"><span data-stu-id="f45b6-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="f45b6-545">Sztornírozási könyv\-Egyéni réteg\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="f45b6-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="f45b6-546">IFRS 16 könyv\-Egyéni réteg\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="f45b6-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="f45b6-547">IFRS 16 könyv\-Egyéni réteg\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="f45b6-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="f45b6-548">IFRS 16 könyv\-Egyéni réteg\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="f45b6-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="f45b6-549">IFRS 16 könyv\-Egyéni réteg\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="f45b6-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="f45b6-550">Egyéni réteg \+ Egyéni réteg \- Összesen</span><span class="sxs-lookup"><span data-stu-id="f45b6-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="f45b6-551">1</span><span class="sxs-lookup"><span data-stu-id="f45b6-551">1</span></span>          | <span data-ttu-id="f45b6-552">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-552">Lease expense</span></span>            | <span data-ttu-id="f45b6-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="f45b6-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-554">1,000\.00</span></span>               |   | <span data-ttu-id="f45b6-555">\-1.000.</span><span class="sxs-lookup"><span data-stu-id="f45b6-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="f45b6-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-556">0\.00</span></span>                                   |
| <span data-ttu-id="f45b6-557">2</span><span class="sxs-lookup"><span data-stu-id="f45b6-557">2</span></span>          | <span data-ttu-id="f45b6-558">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="f45b6-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="f45b6-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="f45b6-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-561">3\.00</span></span>                                   |
| <span data-ttu-id="f45b6-562">3</span><span class="sxs-lookup"><span data-stu-id="f45b6-562">3</span></span>          | <span data-ttu-id="f45b6-563">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="f45b6-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="f45b6-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="f45b6-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-566">5\.00</span></span>                                   |
| <span data-ttu-id="f45b6-567">4</span><span class="sxs-lookup"><span data-stu-id="f45b6-567">4</span></span>          | <span data-ttu-id="f45b6-568">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="f45b6-568">Clearing account</span></span>         | <span data-ttu-id="f45b6-569">\-1.000\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="f45b6-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="f45b6-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-571">0\.00</span></span>                   |   | <span data-ttu-id="f45b6-572">1000</span><span class="sxs-lookup"><span data-stu-id="f45b6-572">1,000</span></span>                                           |                                                | <span data-ttu-id="f45b6-573">\-1.000.</span><span class="sxs-lookup"><span data-stu-id="f45b6-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="f45b6-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-574">0\.00</span></span>                                   |
| <span data-ttu-id="f45b6-575">5</span><span class="sxs-lookup"><span data-stu-id="f45b6-575">5</span></span>          | <span data-ttu-id="f45b6-576">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="f45b6-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="f45b6-577">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="f45b6-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-578">1,008\.00</span></span>                                         | <span data-ttu-id="f45b6-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="f45b6-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-580">0\.00</span></span>                                   |
| <span data-ttu-id="f45b6-581">6</span><span class="sxs-lookup"><span data-stu-id="f45b6-581">6</span></span>          | <span data-ttu-id="f45b6-582">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="f45b6-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="f45b6-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="f45b6-584">22,794</span><span class="sxs-lookup"><span data-stu-id="f45b6-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="f45b6-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="f45b6-585">22,793\.90</span></span>                              |
| <span data-ttu-id="f45b6-586">7</span><span class="sxs-lookup"><span data-stu-id="f45b6-586">7</span></span>          | <span data-ttu-id="f45b6-587">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="f45b6-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="f45b6-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="f45b6-589">\-22.794.</span><span class="sxs-lookup"><span data-stu-id="f45b6-589">\-22,794</span></span>                                       | <span data-ttu-id="f45b6-590">1000</span><span class="sxs-lookup"><span data-stu-id="f45b6-590">1,000</span></span>                                          | <span data-ttu-id="f45b6-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="f45b6-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="f45b6-592">\-21.888\.87</span><span class="sxs-lookup"><span data-stu-id="f45b6-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="f45b6-593">8</span><span class="sxs-lookup"><span data-stu-id="f45b6-593">8</span></span>          | <span data-ttu-id="f45b6-594">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="f45b6-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="f45b6-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="f45b6-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="f45b6-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="f45b6-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="f45b6-597">94\.97</span></span>                                  |
| <span data-ttu-id="f45b6-598">9</span><span class="sxs-lookup"><span data-stu-id="f45b6-598">9</span></span>          | <span data-ttu-id="f45b6-599">Készpénz</span><span class="sxs-lookup"><span data-stu-id="f45b6-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="f45b6-600">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="f45b6-601">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="f45b6-602">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="f45b6-603">10</span><span class="sxs-lookup"><span data-stu-id="f45b6-603">10</span></span>         | <span data-ttu-id="f45b6-604">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="f45b6-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="f45b6-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="f45b6-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="f45b6-606">949\.75</span></span>                                        | <span data-ttu-id="f45b6-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="f45b6-607">949\.75</span></span>                                 |
| <span data-ttu-id="f45b6-608">11</span><span class="sxs-lookup"><span data-stu-id="f45b6-608">11</span></span>         | <span data-ttu-id="f45b6-609">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="f45b6-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="f45b6-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="f45b6-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="f45b6-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="f45b6-611">\-949\.75</span></span>                                      | <span data-ttu-id="f45b6-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="f45b6-612">\-949\.75</span></span>                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]