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
ms.openlocfilehash: a7d9b3ea3d4f1d48b8a7326bd5a01d3119310c62
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003181"
---
# <a name="dual-reporting"></a><span data-ttu-id="be7dd-103">Kettős jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="be7dd-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="be7dd-104">Ez a témakör egy olyan példát mutat be, amely megmutatka, hogyan lehet teljesíteni a követelményeket mind a Nemzetközi pénzügyi jelentési standard (IFRS) -jelentésekben, mind a kötelező jelentésekben a tárgyi eszközlízingben.</span><span class="sxs-lookup"><span data-stu-id="be7dd-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="be7dd-105">A Microsoft Dynamics 365 Finance-ben a feladási rétegek ismeretével a példa könnyebben érthető lesz.</span><span class="sxs-lookup"><span data-stu-id="be7dd-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="be7dd-106">Példa</span><span class="sxs-lookup"><span data-stu-id="be7dd-106">Example</span></span>

<span data-ttu-id="be7dd-107">A következő példa az olasz jog szerinti lízinget mutatja be, amelyben a kötelezően előírt jelentés a pénzalap módszert és az IFRS-jelentési módszereket alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="be7dd-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="be7dd-108">A vállalatnak három könyvet kell létrehoznia, hogy mind az olasz, mind az IFRS 16 követelményeit figyelembe tudja venni.</span><span class="sxs-lookup"><span data-stu-id="be7dd-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="be7dd-109">Egy könyv szükséges az IFRS 16 esetében, egy könyv szükséges a törvényi követelményekhez, és egy könyv szükséges a kötelező feladások automatikus sztornírozásához.</span><span class="sxs-lookup"><span data-stu-id="be7dd-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="be7dd-110">A könyveket a következő táblákban látható módon lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="be7dd-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="be7dd-111">**IFRS 16 könyv**</span><span class="sxs-lookup"><span data-stu-id="be7dd-111">**IFRS 16 book**</span></span>

<span data-ttu-id="be7dd-112">Az IFRS 16 könyvet úgy kell beállítani, hogy megfeleljen az IFRS 16 könyvelési szabványának.</span><span class="sxs-lookup"><span data-stu-id="be7dd-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="be7dd-113">A könyvbe feladott összes bejegyzést egy egyéni rétegre adja fel a program.</span><span class="sxs-lookup"><span data-stu-id="be7dd-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="be7dd-114">Név</span><span class="sxs-lookup"><span data-stu-id="be7dd-114">Name</span></span>                                    | <span data-ttu-id="be7dd-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="be7dd-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="be7dd-116">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-116">Book type</span></span>                               | <span data-ttu-id="be7dd-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="be7dd-117">IFRS 16</span></span>        |
| <span data-ttu-id="be7dd-118">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-118">Book description</span></span>                        | <span data-ttu-id="be7dd-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="be7dd-119">IFRS 16</span></span>        |
| <span data-ttu-id="be7dd-120">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-120">Posting Layer</span></span>                           | <span data-ttu-id="be7dd-121">1. egyéni réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-121">Custom layer 1</span></span> |
| <span data-ttu-id="be7dd-122">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="be7dd-122">Lease Type</span></span>                              | <span data-ttu-id="be7dd-123">Finance</span><span class="sxs-lookup"><span data-stu-id="be7dd-123">Finance</span></span>        |
| <span data-ttu-id="be7dd-124">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="be7dd-124">Accounting Framework</span></span>                    | <span data-ttu-id="be7dd-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="be7dd-125">IFRS 16</span></span>        |
| <span data-ttu-id="be7dd-126">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="be7dd-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="be7dd-127">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-127">0.00</span></span>           |
| <span data-ttu-id="be7dd-128">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="be7dd-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="be7dd-129">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-129">0.00</span></span>           |
| <span data-ttu-id="be7dd-130">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="be7dd-130">Short-term threshold</span></span>                    | <span data-ttu-id="be7dd-131">12</span><span class="sxs-lookup"><span data-stu-id="be7dd-131">12</span></span>             |
| <span data-ttu-id="be7dd-132">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="be7dd-132">Low Value Threshold</span></span>                     | <span data-ttu-id="be7dd-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-133">5,000.00</span></span>       |
| <span data-ttu-id="be7dd-134">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="be7dd-134">Pay to Vendor</span></span>                           | <span data-ttu-id="be7dd-135">Nincs</span><span class="sxs-lookup"><span data-stu-id="be7dd-135">No</span></span>             |

<span data-ttu-id="be7dd-136">**Kötelező könyv**</span><span class="sxs-lookup"><span data-stu-id="be7dd-136">**Statutory book**</span></span>

<span data-ttu-id="be7dd-137">A kötelező könyv egy készpénzalapú könyv, ahol a vállalat a lízingköltséget a havi fizetés összegeként adja fel, amely az egyes hónapok bérletét fedezi.</span><span class="sxs-lookup"><span data-stu-id="be7dd-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="be7dd-138">Ez a könyv nem termel használatijog-eszközt (ROU) vagy lízingkötelezettséget.</span><span class="sxs-lookup"><span data-stu-id="be7dd-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="be7dd-139">Név</span><span class="sxs-lookup"><span data-stu-id="be7dd-139">Name</span></span>                                    | <span data-ttu-id="be7dd-140">Leírás</span><span class="sxs-lookup"><span data-stu-id="be7dd-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="be7dd-141">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-141">Book type</span></span>                               | <span data-ttu-id="be7dd-142">Kötelező</span><span class="sxs-lookup"><span data-stu-id="be7dd-142">Statutory</span></span>   |
| <span data-ttu-id="be7dd-143">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-143">Book description</span></span>                        | <span data-ttu-id="be7dd-144">Helyi GAAP</span><span class="sxs-lookup"><span data-stu-id="be7dd-144">Local GAAP</span></span>  |
| <span data-ttu-id="be7dd-145">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-145">Posting Layer</span></span>                           | <span data-ttu-id="be7dd-146">Aktuális</span><span class="sxs-lookup"><span data-stu-id="be7dd-146">Current</span></span>     |
| <span data-ttu-id="be7dd-147">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="be7dd-147">Lease Type</span></span>                              | <span data-ttu-id="be7dd-148">Automatikus</span><span class="sxs-lookup"><span data-stu-id="be7dd-148">Automatic</span></span>   |
| <span data-ttu-id="be7dd-149">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="be7dd-149">Accounting Framework</span></span>                    | <span data-ttu-id="be7dd-150">Készpénzalap</span><span class="sxs-lookup"><span data-stu-id="be7dd-150">Cash basis</span></span>  |
| <span data-ttu-id="be7dd-151">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="be7dd-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="be7dd-152">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-152">0.00</span></span>        |
| <span data-ttu-id="be7dd-153">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="be7dd-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="be7dd-154">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-154">0.00</span></span>        |
| <span data-ttu-id="be7dd-155">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="be7dd-155">Short-term threshold</span></span>                    | <span data-ttu-id="be7dd-156">0</span><span class="sxs-lookup"><span data-stu-id="be7dd-156">0</span></span>           |
| <span data-ttu-id="be7dd-157">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="be7dd-157">Low Value Threshold</span></span>                     | <span data-ttu-id="be7dd-158">0</span><span class="sxs-lookup"><span data-stu-id="be7dd-158">0</span></span>           |
| <span data-ttu-id="be7dd-159">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="be7dd-159">Pay to Vendor</span></span>                           | <span data-ttu-id="be7dd-160">Nincs</span><span class="sxs-lookup"><span data-stu-id="be7dd-160">No</span></span>          |

<span data-ttu-id="be7dd-161">**Kötelező sztornírozási könyv**</span><span class="sxs-lookup"><span data-stu-id="be7dd-161">**Statutory reversal book**</span></span>

<span data-ttu-id="be7dd-162">A kötelező sztornírozási könyvet ugyanúgy kell beállítani, mint a kötelező könyvet.</span><span class="sxs-lookup"><span data-stu-id="be7dd-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="be7dd-163">Név</span><span class="sxs-lookup"><span data-stu-id="be7dd-163">Name</span></span>                                    | <span data-ttu-id="be7dd-164">Leírás</span><span class="sxs-lookup"><span data-stu-id="be7dd-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="be7dd-165">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-165">Book type</span></span>                               | <span data-ttu-id="be7dd-166">Kötelező – Sztornírozás</span><span class="sxs-lookup"><span data-stu-id="be7dd-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="be7dd-167">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-167">Book description</span></span>                        | <span data-ttu-id="be7dd-168">A kötelező könyv sztornírozási könyve</span><span class="sxs-lookup"><span data-stu-id="be7dd-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="be7dd-169">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-169">Posting Layer</span></span>                           | <span data-ttu-id="be7dd-170">1. egyéni réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="be7dd-171">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="be7dd-171">Lease Type</span></span>                              | <span data-ttu-id="be7dd-172">Automatikus</span><span class="sxs-lookup"><span data-stu-id="be7dd-172">Automatic</span></span>                      |
| <span data-ttu-id="be7dd-173">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="be7dd-173">Accounting Framework</span></span>                    | <span data-ttu-id="be7dd-174">Készpénzalap</span><span class="sxs-lookup"><span data-stu-id="be7dd-174">Cash basis</span></span>                     |
| <span data-ttu-id="be7dd-175">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="be7dd-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="be7dd-176">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-176">0.00</span></span>                           |
| <span data-ttu-id="be7dd-177">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="be7dd-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="be7dd-178">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-178">0.00</span></span>                           |
| <span data-ttu-id="be7dd-179">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="be7dd-179">Short-term threshold</span></span>                    | <span data-ttu-id="be7dd-180">0</span><span class="sxs-lookup"><span data-stu-id="be7dd-180">0</span></span>                              |
| <span data-ttu-id="be7dd-181">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="be7dd-181">Low Value Threshold</span></span>                     | <span data-ttu-id="be7dd-182">0</span><span class="sxs-lookup"><span data-stu-id="be7dd-182">0</span></span>                              |
| <span data-ttu-id="be7dd-183">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="be7dd-183">Pay to Vendor</span></span>                           | <span data-ttu-id="be7dd-184">Nincs</span><span class="sxs-lookup"><span data-stu-id="be7dd-184">No</span></span>                             |

<span data-ttu-id="be7dd-185">Ez a példa egy olyan lízing létrejöttét hozta létre, amelynek a következő beállításait találja az **Általános** és a **Fizetési ütemezés sorai** lapon.</span><span class="sxs-lookup"><span data-stu-id="be7dd-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="be7dd-186">**Általános fül**</span><span class="sxs-lookup"><span data-stu-id="be7dd-186">**General tab**</span></span>

| <span data-ttu-id="be7dd-187">Mező</span><span class="sxs-lookup"><span data-stu-id="be7dd-187">Field</span></span>                      | <span data-ttu-id="be7dd-188">Érték</span><span class="sxs-lookup"><span data-stu-id="be7dd-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="be7dd-189">Járulékos kamatláb</span><span class="sxs-lookup"><span data-stu-id="be7dd-189">Incremental borrowing rate</span></span> | <span data-ttu-id="be7dd-190">5%</span><span class="sxs-lookup"><span data-stu-id="be7dd-190">5%</span></span>               |
| <span data-ttu-id="be7dd-191">Kezdési dátum</span><span class="sxs-lookup"><span data-stu-id="be7dd-191">Commencement date</span></span>          | <span data-ttu-id="be7dd-192">2020.01.01.</span><span class="sxs-lookup"><span data-stu-id="be7dd-192">1/1/2020</span></span>         |
| <span data-ttu-id="be7dd-193">Lízingcsoport</span><span class="sxs-lookup"><span data-stu-id="be7dd-193">Lease group</span></span>                | <span data-ttu-id="be7dd-194">Épületek</span><span class="sxs-lookup"><span data-stu-id="be7dd-194">Buildings</span></span>        |
| <span data-ttu-id="be7dd-195">Szállító</span><span class="sxs-lookup"><span data-stu-id="be7dd-195">Vendor</span></span>                     | <span data-ttu-id="be7dd-196">1001</span><span class="sxs-lookup"><span data-stu-id="be7dd-196">1001</span></span>             |
| <span data-ttu-id="be7dd-197">Az eszköz valós értéke</span><span class="sxs-lookup"><span data-stu-id="be7dd-197">Fair value of the asset</span></span>    | <span data-ttu-id="be7dd-198">245,000</span><span class="sxs-lookup"><span data-stu-id="be7dd-198">245,000</span></span>          |
| <span data-ttu-id="be7dd-199">Eszköz hasznos élettartama</span><span class="sxs-lookup"><span data-stu-id="be7dd-199">Asset useful life</span></span>          | <span data-ttu-id="be7dd-200">120</span><span class="sxs-lookup"><span data-stu-id="be7dd-200">120</span></span>              |
| <span data-ttu-id="be7dd-201">Annuitás típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-201">Annuity type</span></span>               | <span data-ttu-id="be7dd-202">Szokásos annuitás</span><span class="sxs-lookup"><span data-stu-id="be7dd-202">Ordinary annuity</span></span> |
| <span data-ttu-id="be7dd-203">Összetételi intervallum</span><span class="sxs-lookup"><span data-stu-id="be7dd-203">Compounding interval</span></span>       | <span data-ttu-id="be7dd-204">Havi</span><span class="sxs-lookup"><span data-stu-id="be7dd-204">Monthly</span></span>          |

<span data-ttu-id="be7dd-205">**Kifizetési lista sorai fül**</span><span class="sxs-lookup"><span data-stu-id="be7dd-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="be7dd-206">Mező</span><span class="sxs-lookup"><span data-stu-id="be7dd-206">Field</span></span>             | <span data-ttu-id="be7dd-207">Érték</span><span class="sxs-lookup"><span data-stu-id="be7dd-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="be7dd-208">Kezdés dátuma</span><span class="sxs-lookup"><span data-stu-id="be7dd-208">Start date</span></span>        | <span data-ttu-id="be7dd-209">2020.01.01.</span><span class="sxs-lookup"><span data-stu-id="be7dd-209">1/1/2020</span></span>   |
| <span data-ttu-id="be7dd-210">Időszak intervalluma</span><span class="sxs-lookup"><span data-stu-id="be7dd-210">Period interval</span></span>   | <span data-ttu-id="be7dd-211">Hónap</span><span class="sxs-lookup"><span data-stu-id="be7dd-211">Months</span></span>     |
| <span data-ttu-id="be7dd-212">Időszakok</span><span class="sxs-lookup"><span data-stu-id="be7dd-212">Periods</span></span>           | <span data-ttu-id="be7dd-213">24</span><span class="sxs-lookup"><span data-stu-id="be7dd-213">24</span></span>         |
| <span data-ttu-id="be7dd-214">Befejezés</span><span class="sxs-lookup"><span data-stu-id="be7dd-214">End date</span></span>          | <span data-ttu-id="be7dd-215">2020.12.31.</span><span class="sxs-lookup"><span data-stu-id="be7dd-215">12/31/2020</span></span> |
| <span data-ttu-id="be7dd-216">Fizetés gyakorisága</span><span class="sxs-lookup"><span data-stu-id="be7dd-216">Payment frequency</span></span> | <span data-ttu-id="be7dd-217">Havi</span><span class="sxs-lookup"><span data-stu-id="be7dd-217">Monthly</span></span>    |
| <span data-ttu-id="be7dd-218">Fizetés összege</span><span class="sxs-lookup"><span data-stu-id="be7dd-218">Payment amount</span></span>    | <span data-ttu-id="be7dd-219">1000</span><span class="sxs-lookup"><span data-stu-id="be7dd-219">1,000</span></span>      |

<span data-ttu-id="be7dd-220">Ha ezt a lízinget két keretrendszerben szeretné elszámolni, akkor egy aktuális feladási réteget és egy egyéni feladási réteget kell használnia.</span><span class="sxs-lookup"><span data-stu-id="be7dd-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="be7dd-221">A következő táblázat egy példát mutat be az összes naplóbejegyzésről, amely szükséges az összes jelentési standard alatt lévő pénzügyek helyes megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="be7dd-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="be7dd-222">Ezt követően a lízing első hónapjához tartozó valamennyi naplóbejegyzés részletes leírása jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="be7dd-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="be7dd-223">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="be7dd-224">Leírás</span><span class="sxs-lookup"><span data-stu-id="be7dd-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="be7dd-225">Kötelező könyv (jelenlegi réteg)</span><span class="sxs-lookup"><span data-stu-id="be7dd-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="be7dd-226">Aktuális réteg összesen</span><span class="sxs-lookup"><span data-stu-id="be7dd-226">Current layer total</span></span></th>
<th><span data-ttu-id="be7dd-227">Sztornírozási könyv (egyéni réteg)</span><span class="sxs-lookup"><span data-stu-id="be7dd-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="be7dd-228">IFRS 16 könyv (egyéni réteg)</span><span class="sxs-lookup"><span data-stu-id="be7dd-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="be7dd-229">Aktuális réteg + egyéni réteg összesen</span><span class="sxs-lookup"><span data-stu-id="be7dd-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="be7dd-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="be7dd-230">JE-100</span></span></th>
<th><span data-ttu-id="be7dd-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="be7dd-231">JE-110</span></span></th>
<th><span data-ttu-id="be7dd-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="be7dd-232">JE-120</span></span></th>
<th><span data-ttu-id="be7dd-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="be7dd-233">JE-130</span></span></th>
<th><span data-ttu-id="be7dd-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="be7dd-234">JE-140</span></span></th>
<th><span data-ttu-id="be7dd-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="be7dd-235">JE-150</span></span></th>
<th><span data-ttu-id="be7dd-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="be7dd-236">JE-160</span></span></th>
<th><span data-ttu-id="be7dd-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="be7dd-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="be7dd-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="be7dd-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="be7dd-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="be7dd-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="be7dd-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="be7dd-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="be7dd-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="be7dd-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="be7dd-246">1</span><span class="sxs-lookup"><span data-stu-id="be7dd-246">1</span></span></td>
<td><span data-ttu-id="be7dd-247">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-247">Lease expense</span></span></td>
<td><span data-ttu-id="be7dd-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-249">1,000.00</span></span></td>
<td><span data-ttu-id="be7dd-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-251">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-252">2</span><span class="sxs-lookup"><span data-stu-id="be7dd-252">2</span></span></td>
<td><span data-ttu-id="be7dd-253">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-254">3.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-255">3.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-256">3.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-257">3</span><span class="sxs-lookup"><span data-stu-id="be7dd-257">3</span></span></td>
<td><span data-ttu-id="be7dd-258">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-259">5.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-260">5.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-261">5.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-262">4</span><span class="sxs-lookup"><span data-stu-id="be7dd-262">4</span></span></td>
<td><span data-ttu-id="be7dd-263">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="be7dd-263">Clearing account</span></span></td>
<td><span data-ttu-id="be7dd-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-264">-1,000.00</span></span></td>
<td><span data-ttu-id="be7dd-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-266">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-266">0.00</span></span></td>
<td><span data-ttu-id="be7dd-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-269">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-270">5</span><span class="sxs-lookup"><span data-stu-id="be7dd-270">5</span></span></td>
<td><span data-ttu-id="be7dd-271">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="be7dd-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-272">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-272">-1,008.00</span></span></td>
<td><span data-ttu-id="be7dd-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-273">1,008.00</span></span></td>
<td><span data-ttu-id="be7dd-274">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-275">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-276">6</span><span class="sxs-lookup"><span data-stu-id="be7dd-276">6</span></span></td>
<td><span data-ttu-id="be7dd-277">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="be7dd-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-278">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="be7dd-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-281">7</span><span class="sxs-lookup"><span data-stu-id="be7dd-281">7</span></span></td>
<td><span data-ttu-id="be7dd-282">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="be7dd-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-283">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-284">-22.794,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-284">-22,794.00</span></span></td>
<td><span data-ttu-id="be7dd-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-285">1,000.00</span></span></td>
<td><span data-ttu-id="be7dd-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="be7dd-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-287">-21.888,87</span><span class="sxs-lookup"><span data-stu-id="be7dd-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-288">8</span><span class="sxs-lookup"><span data-stu-id="be7dd-288">8</span></span></td>
<td><span data-ttu-id="be7dd-289">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-290">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-291">94.97</span><span class="sxs-lookup"><span data-stu-id="be7dd-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-292">94.97</span><span class="sxs-lookup"><span data-stu-id="be7dd-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-293">9</span><span class="sxs-lookup"><span data-stu-id="be7dd-293">9</span></span></td>
<td><span data-ttu-id="be7dd-294">Készpénz</span><span class="sxs-lookup"><span data-stu-id="be7dd-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-295">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-295">-1,008.00</span></span></td>
<td><span data-ttu-id="be7dd-296">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-297">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-298">10</span><span class="sxs-lookup"><span data-stu-id="be7dd-298">10</span></span></td>
<td><span data-ttu-id="be7dd-299">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="be7dd-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-300">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-301">949.75</span><span class="sxs-lookup"><span data-stu-id="be7dd-301">949.75</span></span></td>
<td><span data-ttu-id="be7dd-302">949.75</span><span class="sxs-lookup"><span data-stu-id="be7dd-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-303">11</span><span class="sxs-lookup"><span data-stu-id="be7dd-303">11</span></span></td>
<td><span data-ttu-id="be7dd-304">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="be7dd-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-305">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="be7dd-306">-949.75</span></span></td>
<td><span data-ttu-id="be7dd-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="be7dd-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="be7dd-308">Az előző táblában látható, hogy három könyv szükséges a kötelező jelentéshez és az IFRS-jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="be7dd-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="be7dd-309">A kötelező könyv rögzíti a lízingdíjfizetés az aktuális rétegben a pénzforgalmi elszámolás szabályainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="be7dd-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="be7dd-310">A kötelező sztornírozási könyv a kötelező napló bejegyzéseit visszavonja.</span><span class="sxs-lookup"><span data-stu-id="be7dd-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="be7dd-311">Az IFRS 16 könyv létrehozza az IFRS 16 alapján szükséges naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="be7dd-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="be7dd-312">A lízinget csak egy alkalommal kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="be7dd-312">You must enter a lease only one time.</span></span> <span data-ttu-id="be7dd-313">Ezután megnyithatja a **Könyvek** lapot, amelyen megtekintheti a lízinghez társított könyveket.</span><span class="sxs-lookup"><span data-stu-id="be7dd-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="be7dd-314">Amikor létrehozza a könyveket, mindháromnak ugyanahhoz a lízingrekordhoz kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="be7dd-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="be7dd-315">Az első naplóbejegyzés a kötelező könyv szerinti lízingköltséget rögzíti.</span><span class="sxs-lookup"><span data-stu-id="be7dd-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="be7dd-316">A kifizetéseket egy kötegben is létrehozhatja, vagy kiválaszthatja a kötelező könyv szerinti kifizetési ütemezéseket.</span><span class="sxs-lookup"><span data-stu-id="be7dd-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="be7dd-317">Ebben a példában a következő naplóbejegyzés készül a kötelező könyveléshez a fizetési ütemezésből.</span><span class="sxs-lookup"><span data-stu-id="be7dd-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="be7dd-318">Lízingdíjfizetés – 2020.01.31. – JE 100</span><span class="sxs-lookup"><span data-stu-id="be7dd-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="be7dd-319">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-319">Account type</span></span> | <span data-ttu-id="be7dd-320">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-320">Account number</span></span> | <span data-ttu-id="be7dd-321">Réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-321">Layer</span></span>   | <span data-ttu-id="be7dd-322">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-322">Account description</span></span> | <span data-ttu-id="be7dd-323">Tartozik</span><span class="sxs-lookup"><span data-stu-id="be7dd-323">Debit</span></span>    | <span data-ttu-id="be7dd-324">Követel</span><span class="sxs-lookup"><span data-stu-id="be7dd-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="be7dd-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-325">Ledger</span></span>       | <span data-ttu-id="be7dd-326">1</span><span class="sxs-lookup"><span data-stu-id="be7dd-326">1</span></span>              | <span data-ttu-id="be7dd-327">Aktuális</span><span class="sxs-lookup"><span data-stu-id="be7dd-327">Current</span></span> | <span data-ttu-id="be7dd-328">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-328">Lease expense</span></span>       | <span data-ttu-id="be7dd-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-329">1,000.00</span></span> |          |
| <span data-ttu-id="be7dd-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-330">Ledger</span></span>       | <span data-ttu-id="be7dd-331">4</span><span class="sxs-lookup"><span data-stu-id="be7dd-331">4</span></span>              | <span data-ttu-id="be7dd-332">Aktuális</span><span class="sxs-lookup"><span data-stu-id="be7dd-332">Current</span></span> | <span data-ttu-id="be7dd-333">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="be7dd-333">Clearing account</span></span>    |          | <span data-ttu-id="be7dd-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-334">1,000.00</span></span> |

<span data-ttu-id="be7dd-335">A Kötelezettségekkel kapcsolatos adminisztrátorok a standard Dynamics 365 funkciót használják egy számla létrehozásához, amely a lízing külső Eszközlízingje esetén fizetendő.</span><span class="sxs-lookup"><span data-stu-id="be7dd-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="be7dd-336">Ha viszont a **Lízingköltség** lehetőséget nem tartozási számlaként választja, akkor a Kötelezettségek adminisztrátora egy elszámolási számlát választ a következő bejegyzés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="be7dd-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="be7dd-337">AP-folyamat – 2020.01.31. – JE 110</span><span class="sxs-lookup"><span data-stu-id="be7dd-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="be7dd-338">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-338">Account type</span></span> | <span data-ttu-id="be7dd-339">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-339">Account number</span></span> | <span data-ttu-id="be7dd-340">Réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-340">Layer</span></span>   | <span data-ttu-id="be7dd-341">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-341">Account description</span></span> | <span data-ttu-id="be7dd-342">Tartozik</span><span class="sxs-lookup"><span data-stu-id="be7dd-342">Debit</span></span>    | <span data-ttu-id="be7dd-343">Követel</span><span class="sxs-lookup"><span data-stu-id="be7dd-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="be7dd-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-344">Ledger</span></span>       | <span data-ttu-id="be7dd-345">4</span><span class="sxs-lookup"><span data-stu-id="be7dd-345">4</span></span>              | <span data-ttu-id="be7dd-346">Aktuális</span><span class="sxs-lookup"><span data-stu-id="be7dd-346">Current</span></span> | <span data-ttu-id="be7dd-347">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="be7dd-347">Clearing account</span></span>    | <span data-ttu-id="be7dd-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-348">1,000.00</span></span> |          |
| <span data-ttu-id="be7dd-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-349">Ledger</span></span>       | <span data-ttu-id="be7dd-350">2</span><span class="sxs-lookup"><span data-stu-id="be7dd-350">2</span></span>              | <span data-ttu-id="be7dd-351">Aktuális</span><span class="sxs-lookup"><span data-stu-id="be7dd-351">Current</span></span> | <span data-ttu-id="be7dd-352">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-352">Bank fee</span></span>            | <span data-ttu-id="be7dd-353">3.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-353">3.00</span></span>     |          |
| <span data-ttu-id="be7dd-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-354">Ledger</span></span>       | <span data-ttu-id="be7dd-355">3</span><span class="sxs-lookup"><span data-stu-id="be7dd-355">3</span></span>              | <span data-ttu-id="be7dd-356">Aktuális</span><span class="sxs-lookup"><span data-stu-id="be7dd-356">Current</span></span> | <span data-ttu-id="be7dd-357">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-357">VAT expense</span></span>         | <span data-ttu-id="be7dd-358">5.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-358">5.00</span></span>     |          |
| <span data-ttu-id="be7dd-359">Szállító</span><span class="sxs-lookup"><span data-stu-id="be7dd-359">Vendor</span></span>       | <span data-ttu-id="be7dd-360">5</span><span class="sxs-lookup"><span data-stu-id="be7dd-360">5</span></span>              | <span data-ttu-id="be7dd-361">Aktuális</span><span class="sxs-lookup"><span data-stu-id="be7dd-361">Current</span></span> | <span data-ttu-id="be7dd-362">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="be7dd-362">Accounts payable</span></span>    |          | <span data-ttu-id="be7dd-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-363">1,008.00</span></span> |

<span data-ttu-id="be7dd-364">Amikor a kimutatást kiállítják a szállítónak, a szokásos fizetési folyamatot követik.</span><span class="sxs-lookup"><span data-stu-id="be7dd-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="be7dd-365">A folyamat során a következő naplóbejegyzés jön létre.</span><span class="sxs-lookup"><span data-stu-id="be7dd-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="be7dd-366">Készpénzes fizetés – 2020.01.31. – JE 120</span><span class="sxs-lookup"><span data-stu-id="be7dd-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="be7dd-367">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-367">Account type</span></span> | <span data-ttu-id="be7dd-368">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-368">Account number</span></span> | <span data-ttu-id="be7dd-369">Réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-369">Layer</span></span>   | <span data-ttu-id="be7dd-370">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-370">Account description</span></span> | <span data-ttu-id="be7dd-371">Tartozik</span><span class="sxs-lookup"><span data-stu-id="be7dd-371">Debit</span></span>    | <span data-ttu-id="be7dd-372">Követel</span><span class="sxs-lookup"><span data-stu-id="be7dd-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="be7dd-373">Szállító</span><span class="sxs-lookup"><span data-stu-id="be7dd-373">Vendor</span></span>       | <span data-ttu-id="be7dd-374">5</span><span class="sxs-lookup"><span data-stu-id="be7dd-374">5</span></span>              | <span data-ttu-id="be7dd-375">Aktuális</span><span class="sxs-lookup"><span data-stu-id="be7dd-375">Current</span></span> | <span data-ttu-id="be7dd-376">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="be7dd-376">Accounts Payable</span></span>    | <span data-ttu-id="be7dd-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-377">1,008.00</span></span> |          |
| <span data-ttu-id="be7dd-378">Bank</span><span class="sxs-lookup"><span data-stu-id="be7dd-378">Bank</span></span>         | <span data-ttu-id="be7dd-379">9</span><span class="sxs-lookup"><span data-stu-id="be7dd-379">9</span></span>              | <span data-ttu-id="be7dd-380">Aktuális</span><span class="sxs-lookup"><span data-stu-id="be7dd-380">Current</span></span> | <span data-ttu-id="be7dd-381">Készpénz</span><span class="sxs-lookup"><span data-stu-id="be7dd-381">Cash</span></span>                |          | <span data-ttu-id="be7dd-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-382">1,008.00</span></span> |

<span data-ttu-id="be7dd-383">Ezen a ponton már teljes mértékben elszámolta ezt a lízinget a kötelező jelentési követelmények között, és a jelenlegi réteg használatával generálhat egy főkönyvi kivonatot.</span><span class="sxs-lookup"><span data-stu-id="be7dd-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="be7dd-384">A rendszer a következő számú főkönyvi kivonatot küld vissza.</span><span class="sxs-lookup"><span data-stu-id="be7dd-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="be7dd-385">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="be7dd-386">Leírás</span><span class="sxs-lookup"><span data-stu-id="be7dd-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="be7dd-387">Kötelező könyv (jelenlegi réteg)</span><span class="sxs-lookup"><span data-stu-id="be7dd-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="be7dd-388">Aktuális réteg összesen</span><span class="sxs-lookup"><span data-stu-id="be7dd-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="be7dd-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="be7dd-389">JE-100</span></span></th>
<th><span data-ttu-id="be7dd-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="be7dd-390">JE-110</span></span></th>
<th><span data-ttu-id="be7dd-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="be7dd-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="be7dd-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="be7dd-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="be7dd-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="be7dd-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="be7dd-395">1</span><span class="sxs-lookup"><span data-stu-id="be7dd-395">1</span></span></td>
<td><span data-ttu-id="be7dd-396">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-396">Lease expense</span></span></td>
<td><span data-ttu-id="be7dd-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-399">2</span><span class="sxs-lookup"><span data-stu-id="be7dd-399">2</span></span></td>
<td><span data-ttu-id="be7dd-400">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-401">3.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-402">3.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-403">3</span><span class="sxs-lookup"><span data-stu-id="be7dd-403">3</span></span></td>
<td><span data-ttu-id="be7dd-404">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-405">5.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-406">5.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-407">4</span><span class="sxs-lookup"><span data-stu-id="be7dd-407">4</span></span></td>
<td><span data-ttu-id="be7dd-408">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="be7dd-408">Clearing account</span></span></td>
<td><span data-ttu-id="be7dd-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-409">-1,000.00</span></span></td>
<td><span data-ttu-id="be7dd-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-411">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-412">5</span><span class="sxs-lookup"><span data-stu-id="be7dd-412">5</span></span></td>
<td><span data-ttu-id="be7dd-413">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="be7dd-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="be7dd-414">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-414">-1,008.00</span></span></td>
<td><span data-ttu-id="be7dd-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-415">1,008.00</span></span></td>
<td><span data-ttu-id="be7dd-416">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-417">6</span><span class="sxs-lookup"><span data-stu-id="be7dd-417">6</span></span></td>
<td><span data-ttu-id="be7dd-418">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="be7dd-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-419">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-420">7</span><span class="sxs-lookup"><span data-stu-id="be7dd-420">7</span></span></td>
<td><span data-ttu-id="be7dd-421">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="be7dd-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-422">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-423">8</span><span class="sxs-lookup"><span data-stu-id="be7dd-423">8</span></span></td>
<td><span data-ttu-id="be7dd-424">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-425">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-426">9</span><span class="sxs-lookup"><span data-stu-id="be7dd-426">9</span></span></td>
<td><span data-ttu-id="be7dd-427">Készpénz</span><span class="sxs-lookup"><span data-stu-id="be7dd-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-428">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-428">-1,008.00</span></span></td>
<td><span data-ttu-id="be7dd-429">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-430">10</span><span class="sxs-lookup"><span data-stu-id="be7dd-430">10</span></span></td>
<td><span data-ttu-id="be7dd-431">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="be7dd-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-432">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="be7dd-433">11</span><span class="sxs-lookup"><span data-stu-id="be7dd-433">11</span></span></td>
<td><span data-ttu-id="be7dd-434">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="be7dd-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="be7dd-435">0,00</span><span class="sxs-lookup"><span data-stu-id="be7dd-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="be7dd-436">Ha azt szeretné, hogy az IFRS 16 számokkal ugyanaz a főkönyvi kivonat fusson, akkor a kötelező könyvelési napló bejegyzéseit sztornírozni kell, és az IFRS 16 napló bejegyzéseit fel kell adni.</span><span class="sxs-lookup"><span data-stu-id="be7dd-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="be7dd-437">A kötelező naplóbejegyzések sztornírozásához ez a példa olyan kötelező sztornírozási könyvet tartalmaz, amelynek ugyanaz a beállítása, mint a kötelező könyvé, de ellenkező feladási profilú.</span><span class="sxs-lookup"><span data-stu-id="be7dd-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="be7dd-438">Például a kötelező könyv *megterhelt* egy lízingköltség-számlát, de a sztornírozási könyv *jóváírja* ezt a számlát.</span><span class="sxs-lookup"><span data-stu-id="be7dd-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="be7dd-439">Ezek a kapcsolatok könnyen meghatározhatók az **Eszközlízing paraméterek** oldalon (**Eszközlízing paraméterek \> Beállítás \> Eszközlízing paraméterek**) található Eszközlízing feladási számlákban.</span><span class="sxs-lookup"><span data-stu-id="be7dd-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="be7dd-440">Ha a sztornírozási könyvhöz a kötelező könyvhöz használt eljárást használja, a következő naplóbejegyzés jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="be7dd-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="be7dd-441">A különbség az, hogy a sztornírozási könyv a sztornírozási bejegyzéseket a kötelező könyvből állítja be.</span><span class="sxs-lookup"><span data-stu-id="be7dd-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="be7dd-442">A sztornírozási bejegyzések az egyéni rétegre is vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="be7dd-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="be7dd-443">Ha az aktuális rétegen fut egy főkönyvi kivonat, a sztornírozó naplóbejegyzések nem szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="be7dd-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="be7dd-444">Lízingdíjfizetés – 2020.01.31. – JE 130</span><span class="sxs-lookup"><span data-stu-id="be7dd-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="be7dd-445">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-445">Account type</span></span> | <span data-ttu-id="be7dd-446">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-446">Account number</span></span> | <span data-ttu-id="be7dd-447">Réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-447">Layer</span></span>  | <span data-ttu-id="be7dd-448">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-448">Account description</span></span> | <span data-ttu-id="be7dd-449">Tartozik</span><span class="sxs-lookup"><span data-stu-id="be7dd-449">Debit</span></span>    | <span data-ttu-id="be7dd-450">Követel</span><span class="sxs-lookup"><span data-stu-id="be7dd-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="be7dd-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-451">Ledger</span></span>       | <span data-ttu-id="be7dd-452">4</span><span class="sxs-lookup"><span data-stu-id="be7dd-452">4</span></span>              | <span data-ttu-id="be7dd-453">Egyéni</span><span class="sxs-lookup"><span data-stu-id="be7dd-453">Custom</span></span> | <span data-ttu-id="be7dd-454">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="be7dd-454">Clearing account</span></span>    | <span data-ttu-id="be7dd-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-455">1,000.00</span></span> |          |
| <span data-ttu-id="be7dd-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-456">Ledger</span></span>       | <span data-ttu-id="be7dd-457">1</span><span class="sxs-lookup"><span data-stu-id="be7dd-457">1</span></span>              | <span data-ttu-id="be7dd-458">Egyéni</span><span class="sxs-lookup"><span data-stu-id="be7dd-458">Custom</span></span> | <span data-ttu-id="be7dd-459">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-459">Lease expense</span></span>       |          | <span data-ttu-id="be7dd-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-460">1,000.00</span></span> |

<span data-ttu-id="be7dd-461">Most, hogy megszüntette a kötelező naplóbejegyzéseket, az IFRS 16 az IFRS 16-ban lefoglalja az összes naplóbejegyzést.</span><span class="sxs-lookup"><span data-stu-id="be7dd-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="be7dd-462">Ezek a bejegyzések tartalmazzák a ROU-eszköz és a kötelezettség kezdeti megjelenítését, valamint a kamat- és értékcsökkenési nyilvántartást.</span><span class="sxs-lookup"><span data-stu-id="be7dd-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="be7dd-463">Kezdeti elszámolás – 2020.01.01. – JE 140</span><span class="sxs-lookup"><span data-stu-id="be7dd-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="be7dd-464">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-464">Account type</span></span> | <span data-ttu-id="be7dd-465">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-465">Account number</span></span> | <span data-ttu-id="be7dd-466">Réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-466">Layer</span></span>  | <span data-ttu-id="be7dd-467">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-467">Account description</span></span>      | <span data-ttu-id="be7dd-468">Tartozik</span><span class="sxs-lookup"><span data-stu-id="be7dd-468">Debit</span></span>     | <span data-ttu-id="be7dd-469">Követel</span><span class="sxs-lookup"><span data-stu-id="be7dd-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="be7dd-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-470">Ledger</span></span>       | <span data-ttu-id="be7dd-471">6</span><span class="sxs-lookup"><span data-stu-id="be7dd-471">6</span></span>              | <span data-ttu-id="be7dd-472">Egyéni</span><span class="sxs-lookup"><span data-stu-id="be7dd-472">Custom</span></span> | <span data-ttu-id="be7dd-473">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="be7dd-473">ROU Asset</span></span>                | <span data-ttu-id="be7dd-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="be7dd-474">22,793.90</span></span> |           |
| <span data-ttu-id="be7dd-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-475">Ledger</span></span>       | <span data-ttu-id="be7dd-476">7</span><span class="sxs-lookup"><span data-stu-id="be7dd-476">7</span></span>              | <span data-ttu-id="be7dd-477">Egyéni</span><span class="sxs-lookup"><span data-stu-id="be7dd-477">Custom</span></span> | <span data-ttu-id="be7dd-478">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="be7dd-478">Finance lease obligation</span></span> |           | <span data-ttu-id="be7dd-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="be7dd-479">22,793.90</span></span> |

<span data-ttu-id="be7dd-480">A lízingdíjfizetés a többi lízingdíjfizetéshez hasonlóan kerül feladása.</span><span class="sxs-lookup"><span data-stu-id="be7dd-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="be7dd-481">A kiegyenlítési számla használatának oka annak biztosítása, hogy a készpénz csak egyszer kerüljön jóváírásra.</span><span class="sxs-lookup"><span data-stu-id="be7dd-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="be7dd-482">Lízingdíjfizetés – 2020.01.31. – JE 150</span><span class="sxs-lookup"><span data-stu-id="be7dd-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="be7dd-483">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-483">Account type</span></span> | <span data-ttu-id="be7dd-484">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-484">Account number</span></span> | <span data-ttu-id="be7dd-485">Réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-485">Layer</span></span>  | <span data-ttu-id="be7dd-486">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-486">Account description</span></span>      | <span data-ttu-id="be7dd-487">Tartozik</span><span class="sxs-lookup"><span data-stu-id="be7dd-487">Debit</span></span>    | <span data-ttu-id="be7dd-488">Követel</span><span class="sxs-lookup"><span data-stu-id="be7dd-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="be7dd-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-489">Ledger</span></span>       | <span data-ttu-id="be7dd-490">7</span><span class="sxs-lookup"><span data-stu-id="be7dd-490">7</span></span>              | <span data-ttu-id="be7dd-491">Egyéni</span><span class="sxs-lookup"><span data-stu-id="be7dd-491">Custom</span></span> | <span data-ttu-id="be7dd-492">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="be7dd-492">Finance lease obligation</span></span> | <span data-ttu-id="be7dd-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-493">1,000.00</span></span> |          |
| <span data-ttu-id="be7dd-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-494">Ledger</span></span>       | <span data-ttu-id="be7dd-495">4</span><span class="sxs-lookup"><span data-stu-id="be7dd-495">4</span></span>              | <span data-ttu-id="be7dd-496">Egyéni</span><span class="sxs-lookup"><span data-stu-id="be7dd-496">Custom</span></span> | <span data-ttu-id="be7dd-497">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="be7dd-497">Clearing account</span></span>         |          | <span data-ttu-id="be7dd-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-498">1,000.00</span></span> |

<span data-ttu-id="be7dd-499">A kamatráfordítási naplóbejegyzés a kötelezettség amortizációs ütemezéséből jön létre.</span><span class="sxs-lookup"><span data-stu-id="be7dd-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="be7dd-500">Kamatköltség – 2020.01.31. – JE 160</span><span class="sxs-lookup"><span data-stu-id="be7dd-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="be7dd-501">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-501">Account type</span></span> | <span data-ttu-id="be7dd-502">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-502">Account number</span></span> | <span data-ttu-id="be7dd-503">Réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-503">Layer</span></span>  | <span data-ttu-id="be7dd-504">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-504">Account description</span></span>      | <span data-ttu-id="be7dd-505">Tartozik</span><span class="sxs-lookup"><span data-stu-id="be7dd-505">Debit</span></span> | <span data-ttu-id="be7dd-506">Követel</span><span class="sxs-lookup"><span data-stu-id="be7dd-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="be7dd-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-507">Ledger</span></span>       | <span data-ttu-id="be7dd-508">8</span><span class="sxs-lookup"><span data-stu-id="be7dd-508">8</span></span>              | <span data-ttu-id="be7dd-509">Egyéni</span><span class="sxs-lookup"><span data-stu-id="be7dd-509">Custom</span></span> | <span data-ttu-id="be7dd-510">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-510">Interest expense</span></span>         | <span data-ttu-id="be7dd-511">94.97</span><span class="sxs-lookup"><span data-stu-id="be7dd-511">94.97</span></span> |        |
| <span data-ttu-id="be7dd-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-512">Ledger</span></span>       | <span data-ttu-id="be7dd-513">7</span><span class="sxs-lookup"><span data-stu-id="be7dd-513">7</span></span>              | <span data-ttu-id="be7dd-514">Egyéni</span><span class="sxs-lookup"><span data-stu-id="be7dd-514">Custom</span></span> | <span data-ttu-id="be7dd-515">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="be7dd-515">Finance lease obligation</span></span> |       | <span data-ttu-id="be7dd-516">94.97</span><span class="sxs-lookup"><span data-stu-id="be7dd-516">94.97</span></span>  |

<span data-ttu-id="be7dd-517">Az értékcsökkenési költség-naplóbejegyzés az eszközértékcsökkenési ütemezéséből jön létre.</span><span class="sxs-lookup"><span data-stu-id="be7dd-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="be7dd-518">Értékcsökkenés költsége – 2020.01.31. – JE 170</span><span class="sxs-lookup"><span data-stu-id="be7dd-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="be7dd-519">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="be7dd-519">Account type</span></span> | <span data-ttu-id="be7dd-520">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-520">Account number</span></span> | <span data-ttu-id="be7dd-521">Réteg</span><span class="sxs-lookup"><span data-stu-id="be7dd-521">Layer</span></span>  | <span data-ttu-id="be7dd-522">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="be7dd-522">Account description</span></span>      | <span data-ttu-id="be7dd-523">Tartozik</span><span class="sxs-lookup"><span data-stu-id="be7dd-523">Debit</span></span>  | <span data-ttu-id="be7dd-524">Követel</span><span class="sxs-lookup"><span data-stu-id="be7dd-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="be7dd-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-525">Ledger</span></span>       | <span data-ttu-id="be7dd-526">10</span><span class="sxs-lookup"><span data-stu-id="be7dd-526">10</span></span>             | <span data-ttu-id="be7dd-527">Egyéni</span><span class="sxs-lookup"><span data-stu-id="be7dd-527">Custom</span></span> | <span data-ttu-id="be7dd-528">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="be7dd-528">Depreciation expense</span></span>     | <span data-ttu-id="be7dd-529">949.75</span><span class="sxs-lookup"><span data-stu-id="be7dd-529">949.75</span></span> |        |
| <span data-ttu-id="be7dd-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="be7dd-530">Ledger</span></span>       | <span data-ttu-id="be7dd-531">11</span><span class="sxs-lookup"><span data-stu-id="be7dd-531">11</span></span>             | <span data-ttu-id="be7dd-532">Egyéni</span><span class="sxs-lookup"><span data-stu-id="be7dd-532">Custom</span></span> | <span data-ttu-id="be7dd-533">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="be7dd-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="be7dd-534">949.75</span><span class="sxs-lookup"><span data-stu-id="be7dd-534">949.75</span></span> |

<span data-ttu-id="be7dd-535">Miután az összes naplóbejegyzést létrehozta és feladta, akkor a következő „1. egyéni réteg” értékeket fogja látni.</span><span class="sxs-lookup"><span data-stu-id="be7dd-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="be7dd-536">Ne feledje, hogy az utolsó oszlop tartalmazza a banki díjat, az áfaköltséget (ÁFA) és az előző rétegből származó készpénz csökkentését, de nem tartalmazza a kötelező jelentési naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="be7dd-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="be7dd-537">Ezért valódi kettős jelentéskészítési képességeket érhet el.</span><span class="sxs-lookup"><span data-stu-id="be7dd-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="be7dd-538">Ezen a ponton a vállalatnak csak futtatnia kell a főkönyvi kivonatot, és kombinálnia kell az aktuális réteget és az egyéni réteget az IFRS főkönyvi kivonat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="be7dd-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="be7dd-539">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="be7dd-539">Account No</span></span> | <span data-ttu-id="be7dd-540">Leírás</span><span class="sxs-lookup"><span data-stu-id="be7dd-540">Description</span></span>              | <span data-ttu-id="be7dd-541">Kötelező könyv\-Aktuális réteg\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="be7dd-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="be7dd-542">Kötelező könyv\-Aktuális réteg\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="be7dd-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="be7dd-543">Kötelező könyv\-Aktuális réteg\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="be7dd-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="be7dd-544">Aktuális réteg \- Összesen</span><span class="sxs-lookup"><span data-stu-id="be7dd-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="be7dd-545">Sztornírozási könyv\-Egyéni réteg\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="be7dd-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="be7dd-546">IFRS 16 könyv\-Egyéni réteg\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="be7dd-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="be7dd-547">IFRS 16 könyv\-Egyéni réteg\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="be7dd-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="be7dd-548">IFRS 16 könyv\-Egyéni réteg\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="be7dd-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="be7dd-549">IFRS 16 könyv\-Egyéni réteg\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="be7dd-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="be7dd-550">Egyéni réteg \+ Egyéni réteg \- Összesen</span><span class="sxs-lookup"><span data-stu-id="be7dd-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="be7dd-551">1</span><span class="sxs-lookup"><span data-stu-id="be7dd-551">1</span></span>          | <span data-ttu-id="be7dd-552">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-552">Lease expense</span></span>            | <span data-ttu-id="be7dd-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="be7dd-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-554">1,000\.00</span></span>               |   | <span data-ttu-id="be7dd-555">\-1.000.</span><span class="sxs-lookup"><span data-stu-id="be7dd-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="be7dd-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-556">0\.00</span></span>                                   |
| <span data-ttu-id="be7dd-557">2</span><span class="sxs-lookup"><span data-stu-id="be7dd-557">2</span></span>          | <span data-ttu-id="be7dd-558">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="be7dd-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="be7dd-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="be7dd-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-561">3\.00</span></span>                                   |
| <span data-ttu-id="be7dd-562">3</span><span class="sxs-lookup"><span data-stu-id="be7dd-562">3</span></span>          | <span data-ttu-id="be7dd-563">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="be7dd-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="be7dd-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="be7dd-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-566">5\.00</span></span>                                   |
| <span data-ttu-id="be7dd-567">4</span><span class="sxs-lookup"><span data-stu-id="be7dd-567">4</span></span>          | <span data-ttu-id="be7dd-568">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="be7dd-568">Clearing account</span></span>         | <span data-ttu-id="be7dd-569">\-1.000\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="be7dd-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="be7dd-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-571">0\.00</span></span>                   |   | <span data-ttu-id="be7dd-572">1000</span><span class="sxs-lookup"><span data-stu-id="be7dd-572">1,000</span></span>                                           |                                                | <span data-ttu-id="be7dd-573">\-1.000.</span><span class="sxs-lookup"><span data-stu-id="be7dd-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="be7dd-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-574">0\.00</span></span>                                   |
| <span data-ttu-id="be7dd-575">5</span><span class="sxs-lookup"><span data-stu-id="be7dd-575">5</span></span>          | <span data-ttu-id="be7dd-576">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="be7dd-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="be7dd-577">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="be7dd-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-578">1,008\.00</span></span>                                         | <span data-ttu-id="be7dd-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="be7dd-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-580">0\.00</span></span>                                   |
| <span data-ttu-id="be7dd-581">6</span><span class="sxs-lookup"><span data-stu-id="be7dd-581">6</span></span>          | <span data-ttu-id="be7dd-582">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="be7dd-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="be7dd-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="be7dd-584">22,794</span><span class="sxs-lookup"><span data-stu-id="be7dd-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="be7dd-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="be7dd-585">22,793\.90</span></span>                              |
| <span data-ttu-id="be7dd-586">7</span><span class="sxs-lookup"><span data-stu-id="be7dd-586">7</span></span>          | <span data-ttu-id="be7dd-587">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="be7dd-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="be7dd-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="be7dd-589">\-22.794.</span><span class="sxs-lookup"><span data-stu-id="be7dd-589">\-22,794</span></span>                                       | <span data-ttu-id="be7dd-590">1000</span><span class="sxs-lookup"><span data-stu-id="be7dd-590">1,000</span></span>                                          | <span data-ttu-id="be7dd-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="be7dd-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="be7dd-592">\-21.888\.87</span><span class="sxs-lookup"><span data-stu-id="be7dd-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="be7dd-593">8</span><span class="sxs-lookup"><span data-stu-id="be7dd-593">8</span></span>          | <span data-ttu-id="be7dd-594">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="be7dd-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="be7dd-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="be7dd-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="be7dd-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="be7dd-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="be7dd-597">94\.97</span></span>                                  |
| <span data-ttu-id="be7dd-598">9</span><span class="sxs-lookup"><span data-stu-id="be7dd-598">9</span></span>          | <span data-ttu-id="be7dd-599">Készpénz</span><span class="sxs-lookup"><span data-stu-id="be7dd-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="be7dd-600">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="be7dd-601">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="be7dd-602">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="be7dd-603">10</span><span class="sxs-lookup"><span data-stu-id="be7dd-603">10</span></span>         | <span data-ttu-id="be7dd-604">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="be7dd-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="be7dd-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="be7dd-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="be7dd-606">949\.75</span></span>                                        | <span data-ttu-id="be7dd-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="be7dd-607">949\.75</span></span>                                 |
| <span data-ttu-id="be7dd-608">11</span><span class="sxs-lookup"><span data-stu-id="be7dd-608">11</span></span>         | <span data-ttu-id="be7dd-609">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="be7dd-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="be7dd-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="be7dd-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="be7dd-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="be7dd-611">\-949\.75</span></span>                                      | <span data-ttu-id="be7dd-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="be7dd-612">\-949\.75</span></span>                               |


