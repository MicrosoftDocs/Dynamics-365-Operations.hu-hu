---
title: Kettős jelentéskészítés
description: Ez a témakör egy olyan példát mutat be, amely megmutatka, hogyan lehet teljesíteni a követelményeket mind a Nemzetközi pénzügyi jelentési standard (IFRS) -jelentésekben, mind a kötelező jelentésekben a tárgyi eszközlízingben.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseBookMaster
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 86f42f8db707f3b8c62b9ec4c39ad6464f080748
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881156"
---
# <a name="dual-reporting"></a><span data-ttu-id="ca424-103">Kettős jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="ca424-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ca424-104">Ez a témakör egy olyan példát mutat be, amely megmutatka, hogyan lehet teljesíteni a követelményeket mind a Nemzetközi pénzügyi jelentési standard (IFRS) -jelentésekben, mind a kötelező jelentésekben a tárgyi eszközlízingben.</span><span class="sxs-lookup"><span data-stu-id="ca424-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="ca424-105">A Microsoft Dynamics 365 Finance-ben a feladási rétegek ismeretével a példa könnyebben érthető lesz.</span><span class="sxs-lookup"><span data-stu-id="ca424-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="ca424-106">Példa</span><span class="sxs-lookup"><span data-stu-id="ca424-106">Example</span></span>

<span data-ttu-id="ca424-107">A következő példa az olasz jog szerinti lízinget mutatja be, amelyben a kötelezően előírt jelentés a pénzalap módszert és az IFRS-jelentési módszereket alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="ca424-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="ca424-108">A vállalatnak három könyvet kell létrehoznia, hogy mind az olasz, mind az IFRS 16 követelményeit figyelembe tudja venni.</span><span class="sxs-lookup"><span data-stu-id="ca424-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="ca424-109">Egy könyv szükséges az IFRS 16 esetében, egy könyv szükséges a törvényi követelményekhez, és egy könyv szükséges a kötelező feladások automatikus sztornírozásához.</span><span class="sxs-lookup"><span data-stu-id="ca424-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="ca424-110">A könyveket a következő táblákban látható módon lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="ca424-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="ca424-111">**IFRS 16 könyv**</span><span class="sxs-lookup"><span data-stu-id="ca424-111">**IFRS 16 book**</span></span>

<span data-ttu-id="ca424-112">Az IFRS 16 könyvet úgy kell beállítani, hogy megfeleljen az IFRS 16 könyvelési szabványának.</span><span class="sxs-lookup"><span data-stu-id="ca424-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="ca424-113">A könyvbe feladott összes bejegyzést egy egyéni rétegre adja fel a program.</span><span class="sxs-lookup"><span data-stu-id="ca424-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="ca424-114">Név</span><span class="sxs-lookup"><span data-stu-id="ca424-114">Name</span></span>                                    | <span data-ttu-id="ca424-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="ca424-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="ca424-116">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-116">Book type</span></span>                               | <span data-ttu-id="ca424-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="ca424-117">IFRS 16</span></span>        |
| <span data-ttu-id="ca424-118">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-118">Book description</span></span>                        | <span data-ttu-id="ca424-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="ca424-119">IFRS 16</span></span>        |
| <span data-ttu-id="ca424-120">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-120">Posting Layer</span></span>                           | <span data-ttu-id="ca424-121">1. egyéni réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-121">Custom layer 1</span></span> |
| <span data-ttu-id="ca424-122">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="ca424-122">Lease Type</span></span>                              | <span data-ttu-id="ca424-123">Finance</span><span class="sxs-lookup"><span data-stu-id="ca424-123">Finance</span></span>        |
| <span data-ttu-id="ca424-124">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="ca424-124">Accounting Framework</span></span>                    | <span data-ttu-id="ca424-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="ca424-125">IFRS 16</span></span>        |
| <span data-ttu-id="ca424-126">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="ca424-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="ca424-127">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-127">0.00</span></span>           |
| <span data-ttu-id="ca424-128">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="ca424-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="ca424-129">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-129">0.00</span></span>           |
| <span data-ttu-id="ca424-130">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="ca424-130">Short-term threshold</span></span>                    | <span data-ttu-id="ca424-131">12</span><span class="sxs-lookup"><span data-stu-id="ca424-131">12</span></span>             |
| <span data-ttu-id="ca424-132">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="ca424-132">Low Value Threshold</span></span>                     | <span data-ttu-id="ca424-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-133">5,000.00</span></span>       |
| <span data-ttu-id="ca424-134">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="ca424-134">Pay to Vendor</span></span>                           | <span data-ttu-id="ca424-135">Nincs</span><span class="sxs-lookup"><span data-stu-id="ca424-135">No</span></span>             |

<span data-ttu-id="ca424-136">**Kötelező könyv**</span><span class="sxs-lookup"><span data-stu-id="ca424-136">**Statutory book**</span></span>

<span data-ttu-id="ca424-137">A kötelező könyv egy készpénzalapú könyv, ahol a vállalat a lízingköltséget a havi fizetés összegeként adja fel, amely az egyes hónapok bérletét fedezi.</span><span class="sxs-lookup"><span data-stu-id="ca424-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="ca424-138">Ez a könyv nem termel használatijog-eszközt (ROU) vagy lízingkötelezettséget.</span><span class="sxs-lookup"><span data-stu-id="ca424-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="ca424-139">Név</span><span class="sxs-lookup"><span data-stu-id="ca424-139">Name</span></span>                                    | <span data-ttu-id="ca424-140">Leírás</span><span class="sxs-lookup"><span data-stu-id="ca424-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="ca424-141">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-141">Book type</span></span>                               | <span data-ttu-id="ca424-142">Kötelező</span><span class="sxs-lookup"><span data-stu-id="ca424-142">Statutory</span></span>   |
| <span data-ttu-id="ca424-143">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-143">Book description</span></span>                        | <span data-ttu-id="ca424-144">Helyi GAAP</span><span class="sxs-lookup"><span data-stu-id="ca424-144">Local GAAP</span></span>  |
| <span data-ttu-id="ca424-145">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-145">Posting Layer</span></span>                           | <span data-ttu-id="ca424-146">Aktuális</span><span class="sxs-lookup"><span data-stu-id="ca424-146">Current</span></span>     |
| <span data-ttu-id="ca424-147">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="ca424-147">Lease Type</span></span>                              | <span data-ttu-id="ca424-148">Automatikus</span><span class="sxs-lookup"><span data-stu-id="ca424-148">Automatic</span></span>   |
| <span data-ttu-id="ca424-149">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="ca424-149">Accounting Framework</span></span>                    | <span data-ttu-id="ca424-150">Készpénzalap</span><span class="sxs-lookup"><span data-stu-id="ca424-150">Cash basis</span></span>  |
| <span data-ttu-id="ca424-151">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="ca424-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="ca424-152">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-152">0.00</span></span>        |
| <span data-ttu-id="ca424-153">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="ca424-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="ca424-154">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-154">0.00</span></span>        |
| <span data-ttu-id="ca424-155">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="ca424-155">Short-term threshold</span></span>                    | <span data-ttu-id="ca424-156">0</span><span class="sxs-lookup"><span data-stu-id="ca424-156">0</span></span>           |
| <span data-ttu-id="ca424-157">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="ca424-157">Low Value Threshold</span></span>                     | <span data-ttu-id="ca424-158">0</span><span class="sxs-lookup"><span data-stu-id="ca424-158">0</span></span>           |
| <span data-ttu-id="ca424-159">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="ca424-159">Pay to Vendor</span></span>                           | <span data-ttu-id="ca424-160">Nincs</span><span class="sxs-lookup"><span data-stu-id="ca424-160">No</span></span>          |

<span data-ttu-id="ca424-161">**Kötelező sztornírozási könyv**</span><span class="sxs-lookup"><span data-stu-id="ca424-161">**Statutory reversal book**</span></span>

<span data-ttu-id="ca424-162">A kötelező sztornírozási könyvet ugyanúgy kell beállítani, mint a kötelező könyvet.</span><span class="sxs-lookup"><span data-stu-id="ca424-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="ca424-163">Név</span><span class="sxs-lookup"><span data-stu-id="ca424-163">Name</span></span>                                    | <span data-ttu-id="ca424-164">Leírás</span><span class="sxs-lookup"><span data-stu-id="ca424-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="ca424-165">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-165">Book type</span></span>                               | <span data-ttu-id="ca424-166">Kötelező – Sztornírozás</span><span class="sxs-lookup"><span data-stu-id="ca424-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="ca424-167">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-167">Book description</span></span>                        | <span data-ttu-id="ca424-168">A kötelező könyv sztornírozási könyve</span><span class="sxs-lookup"><span data-stu-id="ca424-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="ca424-169">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-169">Posting Layer</span></span>                           | <span data-ttu-id="ca424-170">1. egyéni réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="ca424-171">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="ca424-171">Lease Type</span></span>                              | <span data-ttu-id="ca424-172">Automatikus</span><span class="sxs-lookup"><span data-stu-id="ca424-172">Automatic</span></span>                      |
| <span data-ttu-id="ca424-173">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="ca424-173">Accounting Framework</span></span>                    | <span data-ttu-id="ca424-174">Készpénzalap</span><span class="sxs-lookup"><span data-stu-id="ca424-174">Cash basis</span></span>                     |
| <span data-ttu-id="ca424-175">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="ca424-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="ca424-176">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-176">0.00</span></span>                           |
| <span data-ttu-id="ca424-177">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="ca424-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="ca424-178">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-178">0.00</span></span>                           |
| <span data-ttu-id="ca424-179">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="ca424-179">Short-term threshold</span></span>                    | <span data-ttu-id="ca424-180">0</span><span class="sxs-lookup"><span data-stu-id="ca424-180">0</span></span>                              |
| <span data-ttu-id="ca424-181">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="ca424-181">Low Value Threshold</span></span>                     | <span data-ttu-id="ca424-182">0</span><span class="sxs-lookup"><span data-stu-id="ca424-182">0</span></span>                              |
| <span data-ttu-id="ca424-183">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="ca424-183">Pay to Vendor</span></span>                           | <span data-ttu-id="ca424-184">Nincs</span><span class="sxs-lookup"><span data-stu-id="ca424-184">No</span></span>                             |

<span data-ttu-id="ca424-185">Ez a példa egy olyan lízing létrejöttét hozta létre, amelynek a következő beállításait találja az **Általános** és a **Fizetési ütemezés sorai** lapon.</span><span class="sxs-lookup"><span data-stu-id="ca424-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="ca424-186">**Általános fül**</span><span class="sxs-lookup"><span data-stu-id="ca424-186">**General tab**</span></span>

| <span data-ttu-id="ca424-187">Mező</span><span class="sxs-lookup"><span data-stu-id="ca424-187">Field</span></span>                      | <span data-ttu-id="ca424-188">Érték</span><span class="sxs-lookup"><span data-stu-id="ca424-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="ca424-189">Járulékos kamatláb</span><span class="sxs-lookup"><span data-stu-id="ca424-189">Incremental borrowing rate</span></span> | <span data-ttu-id="ca424-190">5%</span><span class="sxs-lookup"><span data-stu-id="ca424-190">5%</span></span>               |
| <span data-ttu-id="ca424-191">Kezdési dátum</span><span class="sxs-lookup"><span data-stu-id="ca424-191">Commencement date</span></span>          | <span data-ttu-id="ca424-192">2020.01.01.</span><span class="sxs-lookup"><span data-stu-id="ca424-192">1/1/2020</span></span>         |
| <span data-ttu-id="ca424-193">Lízingcsoport</span><span class="sxs-lookup"><span data-stu-id="ca424-193">Lease group</span></span>                | <span data-ttu-id="ca424-194">Épületek</span><span class="sxs-lookup"><span data-stu-id="ca424-194">Buildings</span></span>        |
| <span data-ttu-id="ca424-195">Szállító</span><span class="sxs-lookup"><span data-stu-id="ca424-195">Vendor</span></span>                     | <span data-ttu-id="ca424-196">1001</span><span class="sxs-lookup"><span data-stu-id="ca424-196">1001</span></span>             |
| <span data-ttu-id="ca424-197">Az eszköz valós értéke</span><span class="sxs-lookup"><span data-stu-id="ca424-197">Fair value of the asset</span></span>    | <span data-ttu-id="ca424-198">245,000</span><span class="sxs-lookup"><span data-stu-id="ca424-198">245,000</span></span>          |
| <span data-ttu-id="ca424-199">Eszköz hasznos élettartama</span><span class="sxs-lookup"><span data-stu-id="ca424-199">Asset useful life</span></span>          | <span data-ttu-id="ca424-200">120</span><span class="sxs-lookup"><span data-stu-id="ca424-200">120</span></span>              |
| <span data-ttu-id="ca424-201">Annuitás típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-201">Annuity type</span></span>               | <span data-ttu-id="ca424-202">Szokásos annuitás</span><span class="sxs-lookup"><span data-stu-id="ca424-202">Ordinary annuity</span></span> |
| <span data-ttu-id="ca424-203">Összetételi intervallum</span><span class="sxs-lookup"><span data-stu-id="ca424-203">Compounding interval</span></span>       | <span data-ttu-id="ca424-204">Havi</span><span class="sxs-lookup"><span data-stu-id="ca424-204">Monthly</span></span>          |

<span data-ttu-id="ca424-205">**Kifizetési lista sorai fül**</span><span class="sxs-lookup"><span data-stu-id="ca424-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="ca424-206">Mező</span><span class="sxs-lookup"><span data-stu-id="ca424-206">Field</span></span>             | <span data-ttu-id="ca424-207">Érték</span><span class="sxs-lookup"><span data-stu-id="ca424-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="ca424-208">Kezdés dátuma</span><span class="sxs-lookup"><span data-stu-id="ca424-208">Start date</span></span>        | <span data-ttu-id="ca424-209">2020.01.01.</span><span class="sxs-lookup"><span data-stu-id="ca424-209">1/1/2020</span></span>   |
| <span data-ttu-id="ca424-210">Időszak intervalluma</span><span class="sxs-lookup"><span data-stu-id="ca424-210">Period interval</span></span>   | <span data-ttu-id="ca424-211">Hónap</span><span class="sxs-lookup"><span data-stu-id="ca424-211">Months</span></span>     |
| <span data-ttu-id="ca424-212">Időszakok</span><span class="sxs-lookup"><span data-stu-id="ca424-212">Periods</span></span>           | <span data-ttu-id="ca424-213">24</span><span class="sxs-lookup"><span data-stu-id="ca424-213">24</span></span>         |
| <span data-ttu-id="ca424-214">Befejezés</span><span class="sxs-lookup"><span data-stu-id="ca424-214">End date</span></span>          | <span data-ttu-id="ca424-215">2020.12.31.</span><span class="sxs-lookup"><span data-stu-id="ca424-215">12/31/2020</span></span> |
| <span data-ttu-id="ca424-216">Fizetés gyakorisága</span><span class="sxs-lookup"><span data-stu-id="ca424-216">Payment frequency</span></span> | <span data-ttu-id="ca424-217">Havi</span><span class="sxs-lookup"><span data-stu-id="ca424-217">Monthly</span></span>    |
| <span data-ttu-id="ca424-218">Fizetés összege</span><span class="sxs-lookup"><span data-stu-id="ca424-218">Payment amount</span></span>    | <span data-ttu-id="ca424-219">1000</span><span class="sxs-lookup"><span data-stu-id="ca424-219">1,000</span></span>      |

<span data-ttu-id="ca424-220">Ha ezt a lízinget két keretrendszerben szeretné elszámolni, akkor egy aktuális feladási réteget és egy egyéni feladási réteget kell használnia.</span><span class="sxs-lookup"><span data-stu-id="ca424-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="ca424-221">A következő táblázat egy példát mutat be az összes naplóbejegyzésről, amely szükséges az összes jelentési standard alatt lévő pénzügyek helyes megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="ca424-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="ca424-222">Ezt követően a lízing első hónapjához tartozó valamennyi naplóbejegyzés részletes leírása jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ca424-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="ca424-223">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="ca424-224">Leírás</span><span class="sxs-lookup"><span data-stu-id="ca424-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="ca424-225">Kötelező könyv (jelenlegi réteg)</span><span class="sxs-lookup"><span data-stu-id="ca424-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="ca424-226">Aktuális réteg összesen</span><span class="sxs-lookup"><span data-stu-id="ca424-226">Current layer total</span></span></th>
<th><span data-ttu-id="ca424-227">Sztornírozási könyv (egyéni réteg)</span><span class="sxs-lookup"><span data-stu-id="ca424-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="ca424-228">IFRS 16 könyv (egyéni réteg)</span><span class="sxs-lookup"><span data-stu-id="ca424-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="ca424-229">Aktuális réteg + egyéni réteg összesen</span><span class="sxs-lookup"><span data-stu-id="ca424-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ca424-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="ca424-230">JE-100</span></span></th>
<th><span data-ttu-id="ca424-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="ca424-231">JE-110</span></span></th>
<th><span data-ttu-id="ca424-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="ca424-232">JE-120</span></span></th>
<th><span data-ttu-id="ca424-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="ca424-233">JE-130</span></span></th>
<th><span data-ttu-id="ca424-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="ca424-234">JE-140</span></span></th>
<th><span data-ttu-id="ca424-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="ca424-235">JE-150</span></span></th>
<th><span data-ttu-id="ca424-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="ca424-236">JE-160</span></span></th>
<th><span data-ttu-id="ca424-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="ca424-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ca424-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ca424-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ca424-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ca424-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ca424-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ca424-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ca424-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ca424-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ca424-246">1</span><span class="sxs-lookup"><span data-stu-id="ca424-246">1</span></span></td>
<td><span data-ttu-id="ca424-247">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-247">Lease expense</span></span></td>
<td><span data-ttu-id="ca424-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-249">1,000.00</span></span></td>
<td><span data-ttu-id="ca424-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ca424-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-251">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-252">2</span><span class="sxs-lookup"><span data-stu-id="ca424-252">2</span></span></td>
<td><span data-ttu-id="ca424-253">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-254">3.00</span><span class="sxs-lookup"><span data-stu-id="ca424-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-255">3.00</span><span class="sxs-lookup"><span data-stu-id="ca424-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-256">3.00</span><span class="sxs-lookup"><span data-stu-id="ca424-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-257">3</span><span class="sxs-lookup"><span data-stu-id="ca424-257">3</span></span></td>
<td><span data-ttu-id="ca424-258">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-259">5.00</span><span class="sxs-lookup"><span data-stu-id="ca424-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-260">5.00</span><span class="sxs-lookup"><span data-stu-id="ca424-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-261">5.00</span><span class="sxs-lookup"><span data-stu-id="ca424-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-262">4</span><span class="sxs-lookup"><span data-stu-id="ca424-262">4</span></span></td>
<td><span data-ttu-id="ca424-263">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="ca424-263">Clearing account</span></span></td>
<td><span data-ttu-id="ca424-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ca424-264">-1,000.00</span></span></td>
<td><span data-ttu-id="ca424-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-266">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-266">0.00</span></span></td>
<td><span data-ttu-id="ca424-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ca424-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-269">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-270">5</span><span class="sxs-lookup"><span data-stu-id="ca424-270">5</span></span></td>
<td><span data-ttu-id="ca424-271">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="ca424-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-272">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="ca424-272">-1,008.00</span></span></td>
<td><span data-ttu-id="ca424-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="ca424-273">1,008.00</span></span></td>
<td><span data-ttu-id="ca424-274">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-275">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-276">6</span><span class="sxs-lookup"><span data-stu-id="ca424-276">6</span></span></td>
<td><span data-ttu-id="ca424-277">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="ca424-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-278">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="ca424-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="ca424-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-281">7</span><span class="sxs-lookup"><span data-stu-id="ca424-281">7</span></span></td>
<td><span data-ttu-id="ca424-282">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="ca424-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-283">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-284">-22.794,00</span><span class="sxs-lookup"><span data-stu-id="ca424-284">-22,794.00</span></span></td>
<td><span data-ttu-id="ca424-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-285">1,000.00</span></span></td>
<td><span data-ttu-id="ca424-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="ca424-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-287">-21.888,87</span><span class="sxs-lookup"><span data-stu-id="ca424-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-288">8</span><span class="sxs-lookup"><span data-stu-id="ca424-288">8</span></span></td>
<td><span data-ttu-id="ca424-289">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-290">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-291">94.97</span><span class="sxs-lookup"><span data-stu-id="ca424-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-292">94.97</span><span class="sxs-lookup"><span data-stu-id="ca424-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-293">9</span><span class="sxs-lookup"><span data-stu-id="ca424-293">9</span></span></td>
<td><span data-ttu-id="ca424-294">Készpénz</span><span class="sxs-lookup"><span data-stu-id="ca424-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-295">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="ca424-295">-1,008.00</span></span></td>
<td><span data-ttu-id="ca424-296">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="ca424-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-297">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="ca424-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-298">10</span><span class="sxs-lookup"><span data-stu-id="ca424-298">10</span></span></td>
<td><span data-ttu-id="ca424-299">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="ca424-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-300">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-301">949.75</span><span class="sxs-lookup"><span data-stu-id="ca424-301">949.75</span></span></td>
<td><span data-ttu-id="ca424-302">949.75</span><span class="sxs-lookup"><span data-stu-id="ca424-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-303">11</span><span class="sxs-lookup"><span data-stu-id="ca424-303">11</span></span></td>
<td><span data-ttu-id="ca424-304">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="ca424-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-305">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="ca424-306">-949.75</span></span></td>
<td><span data-ttu-id="ca424-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="ca424-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ca424-308">Az előző táblában látható, hogy három könyv szükséges a kötelező jelentéshez és az IFRS-jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="ca424-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="ca424-309">A kötelező könyv rögzíti a lízingdíjfizetés az aktuális rétegben a pénzforgalmi elszámolás szabályainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="ca424-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="ca424-310">A kötelező sztornírozási könyv a kötelező napló bejegyzéseit visszavonja.</span><span class="sxs-lookup"><span data-stu-id="ca424-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="ca424-311">Az IFRS 16 könyv létrehozza az IFRS 16 alapján szükséges naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="ca424-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="ca424-312">A lízinget csak egy alkalommal kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="ca424-312">You must enter a lease only one time.</span></span> <span data-ttu-id="ca424-313">Ezután megnyithatja a **Könyvek** lapot, amelyen megtekintheti a lízinghez társított könyveket.</span><span class="sxs-lookup"><span data-stu-id="ca424-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="ca424-314">Amikor létrehozza a könyveket, mindháromnak ugyanahhoz a lízingrekordhoz kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="ca424-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="ca424-315">Az első naplóbejegyzés a kötelező könyv szerinti lízingköltséget rögzíti.</span><span class="sxs-lookup"><span data-stu-id="ca424-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="ca424-316">A kifizetéseket egy kötegben is létrehozhatja, vagy kiválaszthatja a kötelező könyv szerinti kifizetési ütemezéseket.</span><span class="sxs-lookup"><span data-stu-id="ca424-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="ca424-317">Ebben a példában a következő naplóbejegyzés készül a kötelező könyveléshez a fizetési ütemezésből.</span><span class="sxs-lookup"><span data-stu-id="ca424-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="ca424-318">Lízingdíjfizetés – 2020.01.31. – JE 100</span><span class="sxs-lookup"><span data-stu-id="ca424-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="ca424-319">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-319">Account type</span></span> | <span data-ttu-id="ca424-320">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-320">Account number</span></span> | <span data-ttu-id="ca424-321">Réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-321">Layer</span></span>   | <span data-ttu-id="ca424-322">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-322">Account description</span></span> | <span data-ttu-id="ca424-323">Tartozik</span><span class="sxs-lookup"><span data-stu-id="ca424-323">Debit</span></span>    | <span data-ttu-id="ca424-324">Követel</span><span class="sxs-lookup"><span data-stu-id="ca424-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="ca424-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-325">Ledger</span></span>       | <span data-ttu-id="ca424-326">1</span><span class="sxs-lookup"><span data-stu-id="ca424-326">1</span></span>              | <span data-ttu-id="ca424-327">Aktuális</span><span class="sxs-lookup"><span data-stu-id="ca424-327">Current</span></span> | <span data-ttu-id="ca424-328">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-328">Lease expense</span></span>       | <span data-ttu-id="ca424-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-329">1,000.00</span></span> |          |
| <span data-ttu-id="ca424-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-330">Ledger</span></span>       | <span data-ttu-id="ca424-331">4</span><span class="sxs-lookup"><span data-stu-id="ca424-331">4</span></span>              | <span data-ttu-id="ca424-332">Aktuális</span><span class="sxs-lookup"><span data-stu-id="ca424-332">Current</span></span> | <span data-ttu-id="ca424-333">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="ca424-333">Clearing account</span></span>    |          | <span data-ttu-id="ca424-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-334">1,000.00</span></span> |

<span data-ttu-id="ca424-335">A Kötelezettségekkel kapcsolatos adminisztrátorok a standard Dynamics 365 funkciót használják egy számla létrehozásához, amely a lízing külső Eszközlízingje esetén fizetendő.</span><span class="sxs-lookup"><span data-stu-id="ca424-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="ca424-336">Ha viszont a **Lízingköltség** lehetőséget nem tartozási számlaként választja, akkor a Kötelezettségek adminisztrátora egy elszámolási számlát választ a következő bejegyzés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="ca424-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="ca424-337">AP-folyamat – 2020.01.31. – JE 110</span><span class="sxs-lookup"><span data-stu-id="ca424-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="ca424-338">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-338">Account type</span></span> | <span data-ttu-id="ca424-339">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-339">Account number</span></span> | <span data-ttu-id="ca424-340">Réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-340">Layer</span></span>   | <span data-ttu-id="ca424-341">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-341">Account description</span></span> | <span data-ttu-id="ca424-342">Tartozik</span><span class="sxs-lookup"><span data-stu-id="ca424-342">Debit</span></span>    | <span data-ttu-id="ca424-343">Követel</span><span class="sxs-lookup"><span data-stu-id="ca424-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="ca424-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-344">Ledger</span></span>       | <span data-ttu-id="ca424-345">4</span><span class="sxs-lookup"><span data-stu-id="ca424-345">4</span></span>              | <span data-ttu-id="ca424-346">Aktuális</span><span class="sxs-lookup"><span data-stu-id="ca424-346">Current</span></span> | <span data-ttu-id="ca424-347">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="ca424-347">Clearing account</span></span>    | <span data-ttu-id="ca424-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-348">1,000.00</span></span> |          |
| <span data-ttu-id="ca424-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-349">Ledger</span></span>       | <span data-ttu-id="ca424-350">2</span><span class="sxs-lookup"><span data-stu-id="ca424-350">2</span></span>              | <span data-ttu-id="ca424-351">Aktuális</span><span class="sxs-lookup"><span data-stu-id="ca424-351">Current</span></span> | <span data-ttu-id="ca424-352">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-352">Bank fee</span></span>            | <span data-ttu-id="ca424-353">3.00</span><span class="sxs-lookup"><span data-stu-id="ca424-353">3.00</span></span>     |          |
| <span data-ttu-id="ca424-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-354">Ledger</span></span>       | <span data-ttu-id="ca424-355">3</span><span class="sxs-lookup"><span data-stu-id="ca424-355">3</span></span>              | <span data-ttu-id="ca424-356">Aktuális</span><span class="sxs-lookup"><span data-stu-id="ca424-356">Current</span></span> | <span data-ttu-id="ca424-357">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-357">VAT expense</span></span>         | <span data-ttu-id="ca424-358">5.00</span><span class="sxs-lookup"><span data-stu-id="ca424-358">5.00</span></span>     |          |
| <span data-ttu-id="ca424-359">Szállító</span><span class="sxs-lookup"><span data-stu-id="ca424-359">Vendor</span></span>       | <span data-ttu-id="ca424-360">5</span><span class="sxs-lookup"><span data-stu-id="ca424-360">5</span></span>              | <span data-ttu-id="ca424-361">Aktuális</span><span class="sxs-lookup"><span data-stu-id="ca424-361">Current</span></span> | <span data-ttu-id="ca424-362">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="ca424-362">Accounts payable</span></span>    |          | <span data-ttu-id="ca424-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="ca424-363">1,008.00</span></span> |

<span data-ttu-id="ca424-364">Amikor a kimutatást kiállítják a szállítónak, a szokásos fizetési folyamatot követik.</span><span class="sxs-lookup"><span data-stu-id="ca424-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="ca424-365">A folyamat során a következő naplóbejegyzés jön létre.</span><span class="sxs-lookup"><span data-stu-id="ca424-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="ca424-366">Készpénzes fizetés – 2020.01.31. – JE 120</span><span class="sxs-lookup"><span data-stu-id="ca424-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="ca424-367">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-367">Account type</span></span> | <span data-ttu-id="ca424-368">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-368">Account number</span></span> | <span data-ttu-id="ca424-369">Réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-369">Layer</span></span>   | <span data-ttu-id="ca424-370">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-370">Account description</span></span> | <span data-ttu-id="ca424-371">Tartozik</span><span class="sxs-lookup"><span data-stu-id="ca424-371">Debit</span></span>    | <span data-ttu-id="ca424-372">Követel</span><span class="sxs-lookup"><span data-stu-id="ca424-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="ca424-373">Szállító</span><span class="sxs-lookup"><span data-stu-id="ca424-373">Vendor</span></span>       | <span data-ttu-id="ca424-374">5</span><span class="sxs-lookup"><span data-stu-id="ca424-374">5</span></span>              | <span data-ttu-id="ca424-375">Aktuális</span><span class="sxs-lookup"><span data-stu-id="ca424-375">Current</span></span> | <span data-ttu-id="ca424-376">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="ca424-376">Accounts Payable</span></span>    | <span data-ttu-id="ca424-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="ca424-377">1,008.00</span></span> |          |
| <span data-ttu-id="ca424-378">Bank</span><span class="sxs-lookup"><span data-stu-id="ca424-378">Bank</span></span>         | <span data-ttu-id="ca424-379">9</span><span class="sxs-lookup"><span data-stu-id="ca424-379">9</span></span>              | <span data-ttu-id="ca424-380">Aktuális</span><span class="sxs-lookup"><span data-stu-id="ca424-380">Current</span></span> | <span data-ttu-id="ca424-381">Készpénz</span><span class="sxs-lookup"><span data-stu-id="ca424-381">Cash</span></span>                |          | <span data-ttu-id="ca424-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="ca424-382">1,008.00</span></span> |

<span data-ttu-id="ca424-383">Ezen a ponton már teljes mértékben elszámolta ezt a lízinget a kötelező jelentési követelmények között, és a jelenlegi réteg használatával generálhat egy főkönyvi kivonatot.</span><span class="sxs-lookup"><span data-stu-id="ca424-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="ca424-384">A rendszer a következő számú főkönyvi kivonatot küld vissza.</span><span class="sxs-lookup"><span data-stu-id="ca424-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="ca424-385">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="ca424-386">Leírás</span><span class="sxs-lookup"><span data-stu-id="ca424-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="ca424-387">Kötelező könyv (jelenlegi réteg)</span><span class="sxs-lookup"><span data-stu-id="ca424-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="ca424-388">Aktuális réteg összesen</span><span class="sxs-lookup"><span data-stu-id="ca424-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ca424-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="ca424-389">JE-100</span></span></th>
<th><span data-ttu-id="ca424-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="ca424-390">JE-110</span></span></th>
<th><span data-ttu-id="ca424-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="ca424-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ca424-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ca424-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="ca424-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="ca424-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ca424-395">1</span><span class="sxs-lookup"><span data-stu-id="ca424-395">1</span></span></td>
<td><span data-ttu-id="ca424-396">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-396">Lease expense</span></span></td>
<td><span data-ttu-id="ca424-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-399">2</span><span class="sxs-lookup"><span data-stu-id="ca424-399">2</span></span></td>
<td><span data-ttu-id="ca424-400">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-401">3.00</span><span class="sxs-lookup"><span data-stu-id="ca424-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-402">3.00</span><span class="sxs-lookup"><span data-stu-id="ca424-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-403">3</span><span class="sxs-lookup"><span data-stu-id="ca424-403">3</span></span></td>
<td><span data-ttu-id="ca424-404">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-405">5.00</span><span class="sxs-lookup"><span data-stu-id="ca424-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-406">5.00</span><span class="sxs-lookup"><span data-stu-id="ca424-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-407">4</span><span class="sxs-lookup"><span data-stu-id="ca424-407">4</span></span></td>
<td><span data-ttu-id="ca424-408">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="ca424-408">Clearing account</span></span></td>
<td><span data-ttu-id="ca424-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="ca424-409">-1,000.00</span></span></td>
<td><span data-ttu-id="ca424-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-411">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-412">5</span><span class="sxs-lookup"><span data-stu-id="ca424-412">5</span></span></td>
<td><span data-ttu-id="ca424-413">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="ca424-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="ca424-414">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="ca424-414">-1,008.00</span></span></td>
<td><span data-ttu-id="ca424-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="ca424-415">1,008.00</span></span></td>
<td><span data-ttu-id="ca424-416">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-417">6</span><span class="sxs-lookup"><span data-stu-id="ca424-417">6</span></span></td>
<td><span data-ttu-id="ca424-418">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="ca424-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-419">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-420">7</span><span class="sxs-lookup"><span data-stu-id="ca424-420">7</span></span></td>
<td><span data-ttu-id="ca424-421">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="ca424-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-422">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-423">8</span><span class="sxs-lookup"><span data-stu-id="ca424-423">8</span></span></td>
<td><span data-ttu-id="ca424-424">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-425">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-426">9</span><span class="sxs-lookup"><span data-stu-id="ca424-426">9</span></span></td>
<td><span data-ttu-id="ca424-427">Készpénz</span><span class="sxs-lookup"><span data-stu-id="ca424-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-428">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="ca424-428">-1,008.00</span></span></td>
<td><span data-ttu-id="ca424-429">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="ca424-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-430">10</span><span class="sxs-lookup"><span data-stu-id="ca424-430">10</span></span></td>
<td><span data-ttu-id="ca424-431">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="ca424-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-432">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ca424-433">11</span><span class="sxs-lookup"><span data-stu-id="ca424-433">11</span></span></td>
<td><span data-ttu-id="ca424-434">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="ca424-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="ca424-435">0,00</span><span class="sxs-lookup"><span data-stu-id="ca424-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ca424-436">Ha azt szeretné, hogy az IFRS 16 számokkal ugyanaz a főkönyvi kivonat fusson, akkor a kötelező könyvelési napló bejegyzéseit sztornírozni kell, és az IFRS 16 napló bejegyzéseit fel kell adni.</span><span class="sxs-lookup"><span data-stu-id="ca424-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="ca424-437">A kötelező naplóbejegyzések sztornírozásához ez a példa olyan kötelező sztornírozási könyvet tartalmaz, amelynek ugyanaz a beállítása, mint a kötelező könyvé, de ellenkező feladási profilú.</span><span class="sxs-lookup"><span data-stu-id="ca424-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="ca424-438">Például a kötelező könyv *megterhelt* egy lízingköltség-számlát, de a sztornírozási könyv *jóváírja* ezt a számlát.</span><span class="sxs-lookup"><span data-stu-id="ca424-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="ca424-439">Ezek a kapcsolatok könnyen meghatározhatók az **Eszközlízing paraméterek** oldalon (**Eszközlízing paraméterek \> Beállítás \> Eszközlízing paraméterek**) található Eszközlízing feladási számlákban.</span><span class="sxs-lookup"><span data-stu-id="ca424-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="ca424-440">Ha a sztornírozási könyvhöz a kötelező könyvhöz használt eljárást használja, a következő naplóbejegyzés jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ca424-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="ca424-441">A különbség az, hogy a sztornírozási könyv a sztornírozási bejegyzéseket a kötelező könyvből állítja be.</span><span class="sxs-lookup"><span data-stu-id="ca424-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="ca424-442">A sztornírozási bejegyzések az egyéni rétegre is vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="ca424-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="ca424-443">Ha az aktuális rétegen fut egy főkönyvi kivonat, a sztornírozó naplóbejegyzések nem szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="ca424-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="ca424-444">Lízingdíjfizetés – 2020.01.31. – JE 130</span><span class="sxs-lookup"><span data-stu-id="ca424-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="ca424-445">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-445">Account type</span></span> | <span data-ttu-id="ca424-446">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-446">Account number</span></span> | <span data-ttu-id="ca424-447">Réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-447">Layer</span></span>  | <span data-ttu-id="ca424-448">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-448">Account description</span></span> | <span data-ttu-id="ca424-449">Tartozik</span><span class="sxs-lookup"><span data-stu-id="ca424-449">Debit</span></span>    | <span data-ttu-id="ca424-450">Követel</span><span class="sxs-lookup"><span data-stu-id="ca424-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="ca424-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-451">Ledger</span></span>       | <span data-ttu-id="ca424-452">4</span><span class="sxs-lookup"><span data-stu-id="ca424-452">4</span></span>              | <span data-ttu-id="ca424-453">Egyéni</span><span class="sxs-lookup"><span data-stu-id="ca424-453">Custom</span></span> | <span data-ttu-id="ca424-454">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="ca424-454">Clearing account</span></span>    | <span data-ttu-id="ca424-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-455">1,000.00</span></span> |          |
| <span data-ttu-id="ca424-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-456">Ledger</span></span>       | <span data-ttu-id="ca424-457">1</span><span class="sxs-lookup"><span data-stu-id="ca424-457">1</span></span>              | <span data-ttu-id="ca424-458">Egyéni</span><span class="sxs-lookup"><span data-stu-id="ca424-458">Custom</span></span> | <span data-ttu-id="ca424-459">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-459">Lease expense</span></span>       |          | <span data-ttu-id="ca424-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-460">1,000.00</span></span> |

<span data-ttu-id="ca424-461">Most, hogy megszüntette a kötelező naplóbejegyzéseket, az IFRS 16 az IFRS 16-ban lefoglalja az összes naplóbejegyzést.</span><span class="sxs-lookup"><span data-stu-id="ca424-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="ca424-462">Ezek a bejegyzések tartalmazzák a ROU-eszköz és a kötelezettség kezdeti megjelenítését, valamint a kamat- és értékcsökkenési nyilvántartást.</span><span class="sxs-lookup"><span data-stu-id="ca424-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="ca424-463">Kezdeti elszámolás – 2020.01.01. – JE 140</span><span class="sxs-lookup"><span data-stu-id="ca424-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="ca424-464">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-464">Account type</span></span> | <span data-ttu-id="ca424-465">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-465">Account number</span></span> | <span data-ttu-id="ca424-466">Réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-466">Layer</span></span>  | <span data-ttu-id="ca424-467">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-467">Account description</span></span>      | <span data-ttu-id="ca424-468">Tartozik</span><span class="sxs-lookup"><span data-stu-id="ca424-468">Debit</span></span>     | <span data-ttu-id="ca424-469">Követel</span><span class="sxs-lookup"><span data-stu-id="ca424-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="ca424-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-470">Ledger</span></span>       | <span data-ttu-id="ca424-471">6</span><span class="sxs-lookup"><span data-stu-id="ca424-471">6</span></span>              | <span data-ttu-id="ca424-472">Egyéni</span><span class="sxs-lookup"><span data-stu-id="ca424-472">Custom</span></span> | <span data-ttu-id="ca424-473">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="ca424-473">ROU Asset</span></span>                | <span data-ttu-id="ca424-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="ca424-474">22,793.90</span></span> |           |
| <span data-ttu-id="ca424-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-475">Ledger</span></span>       | <span data-ttu-id="ca424-476">7</span><span class="sxs-lookup"><span data-stu-id="ca424-476">7</span></span>              | <span data-ttu-id="ca424-477">Egyéni</span><span class="sxs-lookup"><span data-stu-id="ca424-477">Custom</span></span> | <span data-ttu-id="ca424-478">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="ca424-478">Finance lease obligation</span></span> |           | <span data-ttu-id="ca424-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="ca424-479">22,793.90</span></span> |

<span data-ttu-id="ca424-480">A lízingdíjfizetés a többi lízingdíjfizetéshez hasonlóan kerül feladása.</span><span class="sxs-lookup"><span data-stu-id="ca424-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="ca424-481">A kiegyenlítési számla használatának oka annak biztosítása, hogy a készpénz csak egyszer kerüljön jóváírásra.</span><span class="sxs-lookup"><span data-stu-id="ca424-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="ca424-482">Lízingdíjfizetés – 2020.01.31. – JE 150</span><span class="sxs-lookup"><span data-stu-id="ca424-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="ca424-483">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-483">Account type</span></span> | <span data-ttu-id="ca424-484">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-484">Account number</span></span> | <span data-ttu-id="ca424-485">Réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-485">Layer</span></span>  | <span data-ttu-id="ca424-486">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-486">Account description</span></span>      | <span data-ttu-id="ca424-487">Tartozik</span><span class="sxs-lookup"><span data-stu-id="ca424-487">Debit</span></span>    | <span data-ttu-id="ca424-488">Követel</span><span class="sxs-lookup"><span data-stu-id="ca424-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="ca424-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-489">Ledger</span></span>       | <span data-ttu-id="ca424-490">7</span><span class="sxs-lookup"><span data-stu-id="ca424-490">7</span></span>              | <span data-ttu-id="ca424-491">Egyéni</span><span class="sxs-lookup"><span data-stu-id="ca424-491">Custom</span></span> | <span data-ttu-id="ca424-492">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="ca424-492">Finance lease obligation</span></span> | <span data-ttu-id="ca424-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-493">1,000.00</span></span> |          |
| <span data-ttu-id="ca424-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-494">Ledger</span></span>       | <span data-ttu-id="ca424-495">4</span><span class="sxs-lookup"><span data-stu-id="ca424-495">4</span></span>              | <span data-ttu-id="ca424-496">Egyéni</span><span class="sxs-lookup"><span data-stu-id="ca424-496">Custom</span></span> | <span data-ttu-id="ca424-497">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="ca424-497">Clearing account</span></span>         |          | <span data-ttu-id="ca424-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="ca424-498">1,000.00</span></span> |

<span data-ttu-id="ca424-499">A kamatráfordítási naplóbejegyzés a kötelezettség amortizációs ütemezéséből jön létre.</span><span class="sxs-lookup"><span data-stu-id="ca424-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="ca424-500">Kamatköltség – 2020.01.31. – JE 160</span><span class="sxs-lookup"><span data-stu-id="ca424-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="ca424-501">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-501">Account type</span></span> | <span data-ttu-id="ca424-502">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-502">Account number</span></span> | <span data-ttu-id="ca424-503">Réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-503">Layer</span></span>  | <span data-ttu-id="ca424-504">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-504">Account description</span></span>      | <span data-ttu-id="ca424-505">Tartozik</span><span class="sxs-lookup"><span data-stu-id="ca424-505">Debit</span></span> | <span data-ttu-id="ca424-506">Követel</span><span class="sxs-lookup"><span data-stu-id="ca424-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="ca424-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-507">Ledger</span></span>       | <span data-ttu-id="ca424-508">8</span><span class="sxs-lookup"><span data-stu-id="ca424-508">8</span></span>              | <span data-ttu-id="ca424-509">Egyéni</span><span class="sxs-lookup"><span data-stu-id="ca424-509">Custom</span></span> | <span data-ttu-id="ca424-510">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-510">Interest expense</span></span>         | <span data-ttu-id="ca424-511">94.97</span><span class="sxs-lookup"><span data-stu-id="ca424-511">94.97</span></span> |        |
| <span data-ttu-id="ca424-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-512">Ledger</span></span>       | <span data-ttu-id="ca424-513">7</span><span class="sxs-lookup"><span data-stu-id="ca424-513">7</span></span>              | <span data-ttu-id="ca424-514">Egyéni</span><span class="sxs-lookup"><span data-stu-id="ca424-514">Custom</span></span> | <span data-ttu-id="ca424-515">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="ca424-515">Finance lease obligation</span></span> |       | <span data-ttu-id="ca424-516">94.97</span><span class="sxs-lookup"><span data-stu-id="ca424-516">94.97</span></span>  |

<span data-ttu-id="ca424-517">Az értékcsökkenési költség-naplóbejegyzés az eszközértékcsökkenési ütemezéséből jön létre.</span><span class="sxs-lookup"><span data-stu-id="ca424-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="ca424-518">Értékcsökkenés költsége – 2020.01.31. – JE 170</span><span class="sxs-lookup"><span data-stu-id="ca424-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="ca424-519">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="ca424-519">Account type</span></span> | <span data-ttu-id="ca424-520">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-520">Account number</span></span> | <span data-ttu-id="ca424-521">Réteg</span><span class="sxs-lookup"><span data-stu-id="ca424-521">Layer</span></span>  | <span data-ttu-id="ca424-522">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="ca424-522">Account description</span></span>      | <span data-ttu-id="ca424-523">Tartozik</span><span class="sxs-lookup"><span data-stu-id="ca424-523">Debit</span></span>  | <span data-ttu-id="ca424-524">Követel</span><span class="sxs-lookup"><span data-stu-id="ca424-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="ca424-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-525">Ledger</span></span>       | <span data-ttu-id="ca424-526">10</span><span class="sxs-lookup"><span data-stu-id="ca424-526">10</span></span>             | <span data-ttu-id="ca424-527">Egyéni</span><span class="sxs-lookup"><span data-stu-id="ca424-527">Custom</span></span> | <span data-ttu-id="ca424-528">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="ca424-528">Depreciation expense</span></span>     | <span data-ttu-id="ca424-529">949.75</span><span class="sxs-lookup"><span data-stu-id="ca424-529">949.75</span></span> |        |
| <span data-ttu-id="ca424-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="ca424-530">Ledger</span></span>       | <span data-ttu-id="ca424-531">11</span><span class="sxs-lookup"><span data-stu-id="ca424-531">11</span></span>             | <span data-ttu-id="ca424-532">Egyéni</span><span class="sxs-lookup"><span data-stu-id="ca424-532">Custom</span></span> | <span data-ttu-id="ca424-533">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="ca424-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="ca424-534">949.75</span><span class="sxs-lookup"><span data-stu-id="ca424-534">949.75</span></span> |

<span data-ttu-id="ca424-535">Miután az összes naplóbejegyzést létrehozta és feladta, akkor a következő „1. egyéni réteg” értékeket fogja látni.</span><span class="sxs-lookup"><span data-stu-id="ca424-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="ca424-536">Ne feledje, hogy az utolsó oszlop tartalmazza a banki díjat, az áfaköltséget (ÁFA) és az előző rétegből származó készpénz csökkentését, de nem tartalmazza a kötelező jelentési naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="ca424-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="ca424-537">Ezért valódi kettős jelentéskészítési képességeket érhet el.</span><span class="sxs-lookup"><span data-stu-id="ca424-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="ca424-538">Ezen a ponton a vállalatnak csak futtatnia kell a főkönyvi kivonatot, és kombinálnia kell az aktuális réteget és az egyéni réteget az IFRS főkönyvi kivonat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="ca424-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="ca424-539">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="ca424-539">Account No</span></span> | <span data-ttu-id="ca424-540">Leírás</span><span class="sxs-lookup"><span data-stu-id="ca424-540">Description</span></span>              | <span data-ttu-id="ca424-541">Kötelező könyv\-Aktuális réteg\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ca424-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="ca424-542">Kötelező könyv\-Aktuális réteg\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ca424-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="ca424-543">Kötelező könyv\-Aktuális réteg\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ca424-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="ca424-544">Aktuális réteg \- Összesen</span><span class="sxs-lookup"><span data-stu-id="ca424-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="ca424-545">Sztornírozási könyv\-Egyéni réteg\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ca424-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="ca424-546">IFRS 16 könyv\-Egyéni réteg\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ca424-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="ca424-547">IFRS 16 könyv\-Egyéni réteg\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ca424-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="ca424-548">IFRS 16 könyv\-Egyéni réteg\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ca424-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="ca424-549">IFRS 16 könyv\-Egyéni réteg\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="ca424-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="ca424-550">Egyéni réteg \+ Egyéni réteg \- Összesen</span><span class="sxs-lookup"><span data-stu-id="ca424-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="ca424-551">1</span><span class="sxs-lookup"><span data-stu-id="ca424-551">1</span></span>          | <span data-ttu-id="ca424-552">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-552">Lease expense</span></span>            | <span data-ttu-id="ca424-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="ca424-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-554">1,000\.00</span></span>               |   | <span data-ttu-id="ca424-555">\-1.000.</span><span class="sxs-lookup"><span data-stu-id="ca424-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="ca424-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-556">0\.00</span></span>                                   |
| <span data-ttu-id="ca424-557">2</span><span class="sxs-lookup"><span data-stu-id="ca424-557">2</span></span>          | <span data-ttu-id="ca424-558">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="ca424-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="ca424-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="ca424-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-561">3\.00</span></span>                                   |
| <span data-ttu-id="ca424-562">3</span><span class="sxs-lookup"><span data-stu-id="ca424-562">3</span></span>          | <span data-ttu-id="ca424-563">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="ca424-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="ca424-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="ca424-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-566">5\.00</span></span>                                   |
| <span data-ttu-id="ca424-567">4</span><span class="sxs-lookup"><span data-stu-id="ca424-567">4</span></span>          | <span data-ttu-id="ca424-568">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="ca424-568">Clearing account</span></span>         | <span data-ttu-id="ca424-569">\-1.000\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="ca424-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="ca424-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-571">0\.00</span></span>                   |   | <span data-ttu-id="ca424-572">1000</span><span class="sxs-lookup"><span data-stu-id="ca424-572">1,000</span></span>                                           |                                                | <span data-ttu-id="ca424-573">\-1.000.</span><span class="sxs-lookup"><span data-stu-id="ca424-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="ca424-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-574">0\.00</span></span>                                   |
| <span data-ttu-id="ca424-575">5</span><span class="sxs-lookup"><span data-stu-id="ca424-575">5</span></span>          | <span data-ttu-id="ca424-576">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="ca424-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="ca424-577">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="ca424-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-578">1,008\.00</span></span>                                         | <span data-ttu-id="ca424-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="ca424-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-580">0\.00</span></span>                                   |
| <span data-ttu-id="ca424-581">6</span><span class="sxs-lookup"><span data-stu-id="ca424-581">6</span></span>          | <span data-ttu-id="ca424-582">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="ca424-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="ca424-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="ca424-584">22,794</span><span class="sxs-lookup"><span data-stu-id="ca424-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="ca424-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="ca424-585">22,793\.90</span></span>                              |
| <span data-ttu-id="ca424-586">7</span><span class="sxs-lookup"><span data-stu-id="ca424-586">7</span></span>          | <span data-ttu-id="ca424-587">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="ca424-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="ca424-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="ca424-589">\-22.794.</span><span class="sxs-lookup"><span data-stu-id="ca424-589">\-22,794</span></span>                                       | <span data-ttu-id="ca424-590">1000</span><span class="sxs-lookup"><span data-stu-id="ca424-590">1,000</span></span>                                          | <span data-ttu-id="ca424-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="ca424-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="ca424-592">\-21.888\.87</span><span class="sxs-lookup"><span data-stu-id="ca424-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="ca424-593">8</span><span class="sxs-lookup"><span data-stu-id="ca424-593">8</span></span>          | <span data-ttu-id="ca424-594">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="ca424-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="ca424-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="ca424-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="ca424-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="ca424-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="ca424-597">94\.97</span></span>                                  |
| <span data-ttu-id="ca424-598">9</span><span class="sxs-lookup"><span data-stu-id="ca424-598">9</span></span>          | <span data-ttu-id="ca424-599">Készpénz</span><span class="sxs-lookup"><span data-stu-id="ca424-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="ca424-600">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="ca424-601">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="ca424-602">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="ca424-603">10</span><span class="sxs-lookup"><span data-stu-id="ca424-603">10</span></span>         | <span data-ttu-id="ca424-604">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="ca424-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="ca424-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="ca424-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="ca424-606">949\.75</span></span>                                        | <span data-ttu-id="ca424-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="ca424-607">949\.75</span></span>                                 |
| <span data-ttu-id="ca424-608">11</span><span class="sxs-lookup"><span data-stu-id="ca424-608">11</span></span>         | <span data-ttu-id="ca424-609">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="ca424-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="ca424-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="ca424-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="ca424-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="ca424-611">\-949\.75</span></span>                                      | <span data-ttu-id="ca424-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="ca424-612">\-949\.75</span></span>                               |




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
