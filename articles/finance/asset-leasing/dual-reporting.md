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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 96e1d4d460aef2f74422d5e4bd4fc68255466455
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444164"
---
# <a name="dual-reporting"></a><span data-ttu-id="32f9a-103">Kettős jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="32f9a-103">Dual reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="32f9a-104">Ez a témakör egy olyan példát mutat be, amely megmutatka, hogyan lehet teljesíteni a követelményeket mind a Nemzetközi pénzügyi jelentési standard (IFRS) -jelentésekben, mind a kötelező jelentésekben a tárgyi eszközlízingben.</span><span class="sxs-lookup"><span data-stu-id="32f9a-104">This topic guides you through an example that shows how you can fulfill the requirements for both International Financial Reporting Standard (IFRS) reporting and statutory reporting in Asset leasing.</span></span> <span data-ttu-id="32f9a-105">A Microsoft Dynamics 365 Finance-ben a feladási rétegek ismeretével a példa könnyebben érthető lesz.</span><span class="sxs-lookup"><span data-stu-id="32f9a-105">Familiarity with posting layers in Microsoft Dynamics 365 Finance is required and will make the example easier to understand.</span></span>

## <a name="example"></a><span data-ttu-id="32f9a-106">Példa</span><span class="sxs-lookup"><span data-stu-id="32f9a-106">Example</span></span>

<span data-ttu-id="32f9a-107">A következő példa az olasz jog szerinti lízinget mutatja be, amelyben a kötelezően előírt jelentés a pénzalap módszert és az IFRS-jelentési módszereket alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="32f9a-107">The following example accounts for a lease under Italian statutory reporting by using both the cash-basis method and IFRS reporting methods.</span></span> <span data-ttu-id="32f9a-108">A vállalatnak három könyvet kell létrehoznia, hogy mind az olasz, mind az IFRS 16 követelményeit figyelembe tudja venni.</span><span class="sxs-lookup"><span data-stu-id="32f9a-108">The company must establish three books to account for both the Italian statutory requirements and the IFRS 16 requirements.</span></span> <span data-ttu-id="32f9a-109">Egy könyv szükséges az IFRS 16 esetében, egy könyv szükséges a törvényi követelményekhez, és egy könyv szükséges a kötelező feladások automatikus sztornírozásához.</span><span class="sxs-lookup"><span data-stu-id="32f9a-109">One book is required for IFRS 16, one book is required for statutory requirements, and one book is required to automatically reverse statutory postings.</span></span> <span data-ttu-id="32f9a-110">A könyveket a következő táblákban látható módon lehet beállítani.</span><span class="sxs-lookup"><span data-stu-id="32f9a-110">The books are set up as shown in the following tables.</span></span>

<span data-ttu-id="32f9a-111">**IFRS 16 könyv**</span><span class="sxs-lookup"><span data-stu-id="32f9a-111">**IFRS 16 book**</span></span>

<span data-ttu-id="32f9a-112">Az IFRS 16 könyvet úgy kell beállítani, hogy megfeleljen az IFRS 16 könyvelési szabványának.</span><span class="sxs-lookup"><span data-stu-id="32f9a-112">The IFRS 16 book is set up so that it complies with the IFRS 16 accounting standard.</span></span> <span data-ttu-id="32f9a-113">A könyvbe feladott összes bejegyzést egy egyéni rétegre adja fel a program.</span><span class="sxs-lookup"><span data-stu-id="32f9a-113">All entries that are posted in this book will be posted to a custom layer.</span></span>

| <span data-ttu-id="32f9a-114">Név</span><span class="sxs-lookup"><span data-stu-id="32f9a-114">Name</span></span>                                    | <span data-ttu-id="32f9a-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="32f9a-115">Description</span></span>    |
|-----------------------------------------|----------------|
| <span data-ttu-id="32f9a-116">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-116">Book type</span></span>                               | <span data-ttu-id="32f9a-117">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="32f9a-117">IFRS 16</span></span>        |
| <span data-ttu-id="32f9a-118">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-118">Book description</span></span>                        | <span data-ttu-id="32f9a-119">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="32f9a-119">IFRS 16</span></span>        |
| <span data-ttu-id="32f9a-120">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-120">Posting Layer</span></span>                           | <span data-ttu-id="32f9a-121">1. egyéni réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-121">Custom layer 1</span></span> |
| <span data-ttu-id="32f9a-122">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="32f9a-122">Lease Type</span></span>                              | <span data-ttu-id="32f9a-123">Finance</span><span class="sxs-lookup"><span data-stu-id="32f9a-123">Finance</span></span>        |
| <span data-ttu-id="32f9a-124">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="32f9a-124">Accounting Framework</span></span>                    | <span data-ttu-id="32f9a-125">IFRS 16</span><span class="sxs-lookup"><span data-stu-id="32f9a-125">IFRS 16</span></span>        |
| <span data-ttu-id="32f9a-126">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="32f9a-126">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="32f9a-127">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-127">0.00</span></span>           |
| <span data-ttu-id="32f9a-128">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="32f9a-128">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="32f9a-129">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-129">0.00</span></span>           |
| <span data-ttu-id="32f9a-130">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="32f9a-130">Short-term threshold</span></span>                    | <span data-ttu-id="32f9a-131">12</span><span class="sxs-lookup"><span data-stu-id="32f9a-131">12</span></span>             |
| <span data-ttu-id="32f9a-132">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="32f9a-132">Low Value Threshold</span></span>                     | <span data-ttu-id="32f9a-133">5,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-133">5,000.00</span></span>       |
| <span data-ttu-id="32f9a-134">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="32f9a-134">Pay to Vendor</span></span>                           | <span data-ttu-id="32f9a-135">Nincs</span><span class="sxs-lookup"><span data-stu-id="32f9a-135">No</span></span>             |

<span data-ttu-id="32f9a-136">**Kötelező könyv**</span><span class="sxs-lookup"><span data-stu-id="32f9a-136">**Statutory book**</span></span>

<span data-ttu-id="32f9a-137">A kötelező könyv egy készpénzalapú könyv, ahol a vállalat a lízingköltséget a havi fizetés összegeként adja fel, amely az egyes hónapok bérletét fedezi.</span><span class="sxs-lookup"><span data-stu-id="32f9a-137">The statutory book is a cash-basis book where the company will account for the lease expense as the amount of cash that is paid each month for rent.</span></span> <span data-ttu-id="32f9a-138">Ez a könyv nem termel használatijog-eszközt (ROU) vagy lízingkötelezettséget.</span><span class="sxs-lookup"><span data-stu-id="32f9a-138">This book won't produce a right-of-use (ROU) asset or lease liability.</span></span>

| <span data-ttu-id="32f9a-139">Név</span><span class="sxs-lookup"><span data-stu-id="32f9a-139">Name</span></span>                                    | <span data-ttu-id="32f9a-140">Leírás</span><span class="sxs-lookup"><span data-stu-id="32f9a-140">Description</span></span> |
|-----------------------------------------|-------------|
| <span data-ttu-id="32f9a-141">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-141">Book type</span></span>                               | <span data-ttu-id="32f9a-142">Kötelező</span><span class="sxs-lookup"><span data-stu-id="32f9a-142">Statutory</span></span>   |
| <span data-ttu-id="32f9a-143">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-143">Book description</span></span>                        | <span data-ttu-id="32f9a-144">Helyi GAAP</span><span class="sxs-lookup"><span data-stu-id="32f9a-144">Local GAAP</span></span>  |
| <span data-ttu-id="32f9a-145">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-145">Posting Layer</span></span>                           | <span data-ttu-id="32f9a-146">Aktuális</span><span class="sxs-lookup"><span data-stu-id="32f9a-146">Current</span></span>     |
| <span data-ttu-id="32f9a-147">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="32f9a-147">Lease Type</span></span>                              | <span data-ttu-id="32f9a-148">Automatikus</span><span class="sxs-lookup"><span data-stu-id="32f9a-148">Automatic</span></span>   |
| <span data-ttu-id="32f9a-149">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="32f9a-149">Accounting Framework</span></span>                    | <span data-ttu-id="32f9a-150">Készpénzalap</span><span class="sxs-lookup"><span data-stu-id="32f9a-150">Cash basis</span></span>  |
| <span data-ttu-id="32f9a-151">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="32f9a-151">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="32f9a-152">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-152">0.00</span></span>        |
| <span data-ttu-id="32f9a-153">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="32f9a-153">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="32f9a-154">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-154">0.00</span></span>        |
| <span data-ttu-id="32f9a-155">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="32f9a-155">Short-term threshold</span></span>                    | <span data-ttu-id="32f9a-156">0</span><span class="sxs-lookup"><span data-stu-id="32f9a-156">0</span></span>           |
| <span data-ttu-id="32f9a-157">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="32f9a-157">Low Value Threshold</span></span>                     | <span data-ttu-id="32f9a-158">0</span><span class="sxs-lookup"><span data-stu-id="32f9a-158">0</span></span>           |
| <span data-ttu-id="32f9a-159">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="32f9a-159">Pay to Vendor</span></span>                           | <span data-ttu-id="32f9a-160">Nincs</span><span class="sxs-lookup"><span data-stu-id="32f9a-160">No</span></span>          |

<span data-ttu-id="32f9a-161">**Kötelező sztornírozási könyv**</span><span class="sxs-lookup"><span data-stu-id="32f9a-161">**Statutory reversal book**</span></span>

<span data-ttu-id="32f9a-162">A kötelező sztornírozási könyvet ugyanúgy kell beállítani, mint a kötelező könyvet.</span><span class="sxs-lookup"><span data-stu-id="32f9a-162">The statutory reversal book is set up in the same way as the statutory book.</span></span>

| <span data-ttu-id="32f9a-163">Név</span><span class="sxs-lookup"><span data-stu-id="32f9a-163">Name</span></span>                                    | <span data-ttu-id="32f9a-164">Leírás</span><span class="sxs-lookup"><span data-stu-id="32f9a-164">Description</span></span>                    |
|-----------------------------------------|--------------------------------|
| <span data-ttu-id="32f9a-165">Könyv típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-165">Book type</span></span>                               | <span data-ttu-id="32f9a-166">Kötelező – Sztornírozás</span><span class="sxs-lookup"><span data-stu-id="32f9a-166">Statutory – Reversal</span></span>           |
| <span data-ttu-id="32f9a-167">Könyv leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-167">Book description</span></span>                        | <span data-ttu-id="32f9a-168">A kötelező könyv sztornírozási könyve</span><span class="sxs-lookup"><span data-stu-id="32f9a-168">Book to reverse statutory book</span></span> |
| <span data-ttu-id="32f9a-169">Feladási réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-169">Posting Layer</span></span>                           | <span data-ttu-id="32f9a-170">1. egyéni réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-170">Custom layer 1</span></span>                 |
| <span data-ttu-id="32f9a-171">Lízingtípus</span><span class="sxs-lookup"><span data-stu-id="32f9a-171">Lease Type</span></span>                              | <span data-ttu-id="32f9a-172">Automatikus</span><span class="sxs-lookup"><span data-stu-id="32f9a-172">Automatic</span></span>                      |
| <span data-ttu-id="32f9a-173">Könyvelési keretrendszer</span><span class="sxs-lookup"><span data-stu-id="32f9a-173">Accounting Framework</span></span>                    | <span data-ttu-id="32f9a-174">Készpénzalap</span><span class="sxs-lookup"><span data-stu-id="32f9a-174">Cash basis</span></span>                     |
| <span data-ttu-id="32f9a-175">Lízingfutamidő / hasznos élettartam beállítás</span><span class="sxs-lookup"><span data-stu-id="32f9a-175">Lease Term / Useful life Set Up</span></span>         | <span data-ttu-id="32f9a-176">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-176">0.00</span></span>                           |
| <span data-ttu-id="32f9a-177">Jelenérték / Eszköz valós értékének beállítása</span><span class="sxs-lookup"><span data-stu-id="32f9a-177">Present Value / Asset Fair Value Set Up</span></span> | <span data-ttu-id="32f9a-178">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-178">0.00</span></span>                           |
| <span data-ttu-id="32f9a-179">Rövid távú küszöb</span><span class="sxs-lookup"><span data-stu-id="32f9a-179">Short-term threshold</span></span>                    | <span data-ttu-id="32f9a-180">0</span><span class="sxs-lookup"><span data-stu-id="32f9a-180">0</span></span>                              |
| <span data-ttu-id="32f9a-181">Alacsony értékű küszöb</span><span class="sxs-lookup"><span data-stu-id="32f9a-181">Low Value Threshold</span></span>                     | <span data-ttu-id="32f9a-182">0</span><span class="sxs-lookup"><span data-stu-id="32f9a-182">0</span></span>                              |
| <span data-ttu-id="32f9a-183">Fizetés szállítónak</span><span class="sxs-lookup"><span data-stu-id="32f9a-183">Pay to Vendor</span></span>                           | <span data-ttu-id="32f9a-184">Nincs</span><span class="sxs-lookup"><span data-stu-id="32f9a-184">No</span></span>                             |

<span data-ttu-id="32f9a-185">Ez a példa egy olyan lízing létrejöttét hozta létre, amelynek a következő beállításait találja az **Általános** és a **Fizetési ütemezés sorai** lapon.</span><span class="sxs-lookup"><span data-stu-id="32f9a-185">For this example, a lease has been created that has the following settings on the **General** and **Payment schedule lines** tabs.</span></span>

<span data-ttu-id="32f9a-186">**Általános fül**</span><span class="sxs-lookup"><span data-stu-id="32f9a-186">**General tab**</span></span>

| <span data-ttu-id="32f9a-187">Mező</span><span class="sxs-lookup"><span data-stu-id="32f9a-187">Field</span></span>                      | <span data-ttu-id="32f9a-188">Érték</span><span class="sxs-lookup"><span data-stu-id="32f9a-188">Value</span></span>            |
|----------------------------|------------------|
| <span data-ttu-id="32f9a-189">Járulékos kamatláb</span><span class="sxs-lookup"><span data-stu-id="32f9a-189">Incremental borrowing rate</span></span> | <span data-ttu-id="32f9a-190">5%</span><span class="sxs-lookup"><span data-stu-id="32f9a-190">5%</span></span>               |
| <span data-ttu-id="32f9a-191">Kezdési dátum</span><span class="sxs-lookup"><span data-stu-id="32f9a-191">Commencement date</span></span>          | <span data-ttu-id="32f9a-192">2020.01.01.</span><span class="sxs-lookup"><span data-stu-id="32f9a-192">1/1/2020</span></span>         |
| <span data-ttu-id="32f9a-193">Lízingcsoport</span><span class="sxs-lookup"><span data-stu-id="32f9a-193">Lease group</span></span>                | <span data-ttu-id="32f9a-194">Épületek</span><span class="sxs-lookup"><span data-stu-id="32f9a-194">Buildings</span></span>        |
| <span data-ttu-id="32f9a-195">Szállító</span><span class="sxs-lookup"><span data-stu-id="32f9a-195">Vendor</span></span>                     | <span data-ttu-id="32f9a-196">1001</span><span class="sxs-lookup"><span data-stu-id="32f9a-196">1001</span></span>             |
| <span data-ttu-id="32f9a-197">Az eszköz valós értéke</span><span class="sxs-lookup"><span data-stu-id="32f9a-197">Fair value of the asset</span></span>    | <span data-ttu-id="32f9a-198">245,000</span><span class="sxs-lookup"><span data-stu-id="32f9a-198">245,000</span></span>          |
| <span data-ttu-id="32f9a-199">Eszköz hasznos élettartama</span><span class="sxs-lookup"><span data-stu-id="32f9a-199">Asset useful life</span></span>          | <span data-ttu-id="32f9a-200">120</span><span class="sxs-lookup"><span data-stu-id="32f9a-200">120</span></span>              |
| <span data-ttu-id="32f9a-201">Annuitás típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-201">Annuity type</span></span>               | <span data-ttu-id="32f9a-202">Szokásos annuitás</span><span class="sxs-lookup"><span data-stu-id="32f9a-202">Ordinary annuity</span></span> |
| <span data-ttu-id="32f9a-203">Összetételi intervallum</span><span class="sxs-lookup"><span data-stu-id="32f9a-203">Compounding interval</span></span>       | <span data-ttu-id="32f9a-204">Havi</span><span class="sxs-lookup"><span data-stu-id="32f9a-204">Monthly</span></span>          |

<span data-ttu-id="32f9a-205">**Kifizetési lista sorai fül**</span><span class="sxs-lookup"><span data-stu-id="32f9a-205">**Payment schedule lines tab**</span></span>

| <span data-ttu-id="32f9a-206">Mező</span><span class="sxs-lookup"><span data-stu-id="32f9a-206">Field</span></span>             | <span data-ttu-id="32f9a-207">Érték</span><span class="sxs-lookup"><span data-stu-id="32f9a-207">Value</span></span>      |
|-------------------|------------|
| <span data-ttu-id="32f9a-208">Kezdés dátuma</span><span class="sxs-lookup"><span data-stu-id="32f9a-208">Start date</span></span>        | <span data-ttu-id="32f9a-209">2020.01.01.</span><span class="sxs-lookup"><span data-stu-id="32f9a-209">1/1/2020</span></span>   |
| <span data-ttu-id="32f9a-210">Időszak intervalluma</span><span class="sxs-lookup"><span data-stu-id="32f9a-210">Period interval</span></span>   | <span data-ttu-id="32f9a-211">Hónap</span><span class="sxs-lookup"><span data-stu-id="32f9a-211">Months</span></span>     |
| <span data-ttu-id="32f9a-212">Időszakok</span><span class="sxs-lookup"><span data-stu-id="32f9a-212">Periods</span></span>           | <span data-ttu-id="32f9a-213">24</span><span class="sxs-lookup"><span data-stu-id="32f9a-213">24</span></span>         |
| <span data-ttu-id="32f9a-214">Befejezés</span><span class="sxs-lookup"><span data-stu-id="32f9a-214">End date</span></span>          | <span data-ttu-id="32f9a-215">2020.12.31.</span><span class="sxs-lookup"><span data-stu-id="32f9a-215">12/31/2020</span></span> |
| <span data-ttu-id="32f9a-216">Fizetés gyakorisága</span><span class="sxs-lookup"><span data-stu-id="32f9a-216">Payment frequency</span></span> | <span data-ttu-id="32f9a-217">Havi</span><span class="sxs-lookup"><span data-stu-id="32f9a-217">Monthly</span></span>    |
| <span data-ttu-id="32f9a-218">Fizetés összege</span><span class="sxs-lookup"><span data-stu-id="32f9a-218">Payment amount</span></span>    | <span data-ttu-id="32f9a-219">1000</span><span class="sxs-lookup"><span data-stu-id="32f9a-219">1,000</span></span>      |

<span data-ttu-id="32f9a-220">Ha ezt a lízinget két keretrendszerben szeretné elszámolni, akkor egy aktuális feladási réteget és egy egyéni feladási réteget kell használnia.</span><span class="sxs-lookup"><span data-stu-id="32f9a-220">To account for this lease under two frameworks, you use a current posting layer and a custom posting layer.</span></span> <span data-ttu-id="32f9a-221">A következő táblázat egy példát mutat be az összes naplóbejegyzésről, amely szükséges az összes jelentési standard alatt lévő pénzügyek helyes megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="32f9a-221">The following table shows an example of every journal entry that required to fairly represent the financials under each reporting standard.</span></span> <span data-ttu-id="32f9a-222">Ezt követően a lízing első hónapjához tartozó valamennyi naplóbejegyzés részletes leírása jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="32f9a-222">A detailed description of each journal entry for the first month of the lease is provided afterward.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="32f9a-223">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-223">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="32f9a-224">Leírás</span><span class="sxs-lookup"><span data-stu-id="32f9a-224">Description</span></span></th>
<th colspan='3'><span data-ttu-id="32f9a-225">Kötelező könyv (jelenlegi réteg)</span><span class="sxs-lookup"><span data-stu-id="32f9a-225">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="32f9a-226">Aktuális réteg összesen</span><span class="sxs-lookup"><span data-stu-id="32f9a-226">Current layer total</span></span></th>
<th><span data-ttu-id="32f9a-227">Sztornírozási könyv (egyéni réteg)</span><span class="sxs-lookup"><span data-stu-id="32f9a-227">Reversal book (custom layer)</span></span></th>
<th colspan='4'><span data-ttu-id="32f9a-228">IFRS 16 könyv (egyéni réteg)</span><span class="sxs-lookup"><span data-stu-id="32f9a-228">IFRS 16 book (custom layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="32f9a-229">Aktuális réteg + egyéni réteg összesen</span><span class="sxs-lookup"><span data-stu-id="32f9a-229">Current layer + custom layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="32f9a-230">JE-100</span><span class="sxs-lookup"><span data-stu-id="32f9a-230">JE-100</span></span></th>
<th><span data-ttu-id="32f9a-231">JE-110</span><span class="sxs-lookup"><span data-stu-id="32f9a-231">JE-110</span></span></th>
<th><span data-ttu-id="32f9a-232">JE-120</span><span class="sxs-lookup"><span data-stu-id="32f9a-232">JE-120</span></span></th>
<th><span data-ttu-id="32f9a-233">JE-130</span><span class="sxs-lookup"><span data-stu-id="32f9a-233">JE-130</span></span></th>
<th><span data-ttu-id="32f9a-234">JE-140</span><span class="sxs-lookup"><span data-stu-id="32f9a-234">JE-140</span></span></th>
<th><span data-ttu-id="32f9a-235">JE-150</span><span class="sxs-lookup"><span data-stu-id="32f9a-235">JE-150</span></span></th>
<th><span data-ttu-id="32f9a-236">JE-160</span><span class="sxs-lookup"><span data-stu-id="32f9a-236">JE-160</span></span></th>
<th><span data-ttu-id="32f9a-237">JE-170</span><span class="sxs-lookup"><span data-stu-id="32f9a-237">JE-170</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="32f9a-238">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-238">Dr (Cr)</span></span></th>
<th><span data-ttu-id="32f9a-239">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-239">Dr (Cr)</span></span></th>
<th><span data-ttu-id="32f9a-240">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-240">Dr (Cr)</span></span></th>
<th><span data-ttu-id="32f9a-241">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-241">Dr (Cr)</span></span></th>
<th><span data-ttu-id="32f9a-242">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-242">Dr (Cr)</span></span></th>
<th><span data-ttu-id="32f9a-243">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-243">Dr (Cr)</span></span></th>
<th><span data-ttu-id="32f9a-244">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-244">Dr (Cr)</span></span></th>
<th><span data-ttu-id="32f9a-245">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-245">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="32f9a-246">1</span><span class="sxs-lookup"><span data-stu-id="32f9a-246">1</span></span></td>
<td><span data-ttu-id="32f9a-247">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-247">Lease expense</span></span></td>
<td><span data-ttu-id="32f9a-248">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-248">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-249">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-249">1,000.00</span></span></td>
<td><span data-ttu-id="32f9a-250">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-250">-1,000.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-251">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-251">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-252">2</span><span class="sxs-lookup"><span data-stu-id="32f9a-252">2</span></span></td>
<td><span data-ttu-id="32f9a-253">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-253">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-254">3.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-254">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-255">3.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-255">3.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-256">3.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-256">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-257">3</span><span class="sxs-lookup"><span data-stu-id="32f9a-257">3</span></span></td>
<td><span data-ttu-id="32f9a-258">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-258">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-259">5.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-259">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-260">5.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-260">5.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-261">5.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-261">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-262">4</span><span class="sxs-lookup"><span data-stu-id="32f9a-262">4</span></span></td>
<td><span data-ttu-id="32f9a-263">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="32f9a-263">Clearing account</span></span></td>
<td><span data-ttu-id="32f9a-264">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-264">-1,000.00</span></span></td>
<td><span data-ttu-id="32f9a-265">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-265">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-266">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-266">0.00</span></span></td>
<td><span data-ttu-id="32f9a-267">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-267">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-268">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-268">-1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-269">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-269">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-270">5</span><span class="sxs-lookup"><span data-stu-id="32f9a-270">5</span></span></td>
<td><span data-ttu-id="32f9a-271">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="32f9a-271">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-272">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-272">-1,008.00</span></span></td>
<td><span data-ttu-id="32f9a-273">1,008.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-273">1,008.00</span></span></td>
<td><span data-ttu-id="32f9a-274">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-274">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-275">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-275">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-276">6</span><span class="sxs-lookup"><span data-stu-id="32f9a-276">6</span></span></td>
<td><span data-ttu-id="32f9a-277">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="32f9a-277">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-278">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-278">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-279">22,794.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-279">22,794.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-280">22,793.90</span><span class="sxs-lookup"><span data-stu-id="32f9a-280">22,793.90</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-281">7</span><span class="sxs-lookup"><span data-stu-id="32f9a-281">7</span></span></td>
<td><span data-ttu-id="32f9a-282">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="32f9a-282">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-283">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-283">0.00</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-284">-22.794,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-284">-22,794.00</span></span></td>
<td><span data-ttu-id="32f9a-285">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-285">1,000.00</span></span></td>
<td><span data-ttu-id="32f9a-286">-94,97</span><span class="sxs-lookup"><span data-stu-id="32f9a-286">-94.97</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-287">-21.888,87</span><span class="sxs-lookup"><span data-stu-id="32f9a-287">-21,888.87</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-288">8</span><span class="sxs-lookup"><span data-stu-id="32f9a-288">8</span></span></td>
<td><span data-ttu-id="32f9a-289">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-289">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-290">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-290">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-291">94.97</span><span class="sxs-lookup"><span data-stu-id="32f9a-291">94.97</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-292">94.97</span><span class="sxs-lookup"><span data-stu-id="32f9a-292">94.97</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-293">9</span><span class="sxs-lookup"><span data-stu-id="32f9a-293">9</span></span></td>
<td><span data-ttu-id="32f9a-294">Készpénz</span><span class="sxs-lookup"><span data-stu-id="32f9a-294">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-295">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-295">-1,008.00</span></span></td>
<td><span data-ttu-id="32f9a-296">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-296">-1,008.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-297">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-297">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-298">10</span><span class="sxs-lookup"><span data-stu-id="32f9a-298">10</span></span></td>
<td><span data-ttu-id="32f9a-299">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="32f9a-299">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-300">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-300">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-301">949.75</span><span class="sxs-lookup"><span data-stu-id="32f9a-301">949.75</span></span></td>
<td><span data-ttu-id="32f9a-302">949.75</span><span class="sxs-lookup"><span data-stu-id="32f9a-302">949.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-303">11</span><span class="sxs-lookup"><span data-stu-id="32f9a-303">11</span></span></td>
<td><span data-ttu-id="32f9a-304">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="32f9a-304">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-305">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-305">0.00</span></span></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-306">-949,75</span><span class="sxs-lookup"><span data-stu-id="32f9a-306">-949.75</span></span></td>
<td><span data-ttu-id="32f9a-307">-949,75</span><span class="sxs-lookup"><span data-stu-id="32f9a-307">-949.75</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="32f9a-308">Az előző táblában látható, hogy három könyv szükséges a kötelező jelentéshez és az IFRS-jelentéshez.</span><span class="sxs-lookup"><span data-stu-id="32f9a-308">As the preceding table shows, three books are required to report under both statutory reporting and IFRS reporting.</span></span>

- <span data-ttu-id="32f9a-309">A kötelező könyv rögzíti a lízingdíjfizetés az aktuális rétegben a pénzforgalmi elszámolás szabályainak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="32f9a-309">The statutory book records the lease payment according to the rules for cash-basis accounting under the current layer.</span></span>
- <span data-ttu-id="32f9a-310">A kötelező sztornírozási könyv a kötelező napló bejegyzéseit visszavonja.</span><span class="sxs-lookup"><span data-stu-id="32f9a-310">The statutory reversal book reverses the statutory journal entries.</span></span>
- <span data-ttu-id="32f9a-311">Az IFRS 16 könyv létrehozza az IFRS 16 alapján szükséges naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="32f9a-311">The IFRS 16 book creates the journal entries that are required under IFRS 16.</span></span>

<span data-ttu-id="32f9a-312">A lízinget csak egy alkalommal kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="32f9a-312">You must enter a lease only one time.</span></span> <span data-ttu-id="32f9a-313">Ezután megnyithatja a **Könyvek** lapot, amelyen megtekintheti a lízinghez társított könyveket.</span><span class="sxs-lookup"><span data-stu-id="32f9a-313">You can then open the **Books** page to see all the books that are associated with the lease.</span></span>

> [!NOTE]
> <span data-ttu-id="32f9a-314">Amikor létrehozza a könyveket, mindháromnak ugyanahhoz a lízingrekordhoz kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="32f9a-314">When you create the books, all three of them must be associated with the same lease record.</span></span>

<span data-ttu-id="32f9a-315">Az első naplóbejegyzés a kötelező könyv szerinti lízingköltséget rögzíti.</span><span class="sxs-lookup"><span data-stu-id="32f9a-315">The first journal entry records the lease expense under the statutory book.</span></span> <span data-ttu-id="32f9a-316">A kifizetéseket egy kötegben is létrehozhatja, vagy kiválaszthatja a kötelező könyv szerinti kifizetési ütemezéseket.</span><span class="sxs-lookup"><span data-stu-id="32f9a-316">You can create the payments either in a batch or by selecting the payment schedule in the statutory book.</span></span>

<span data-ttu-id="32f9a-317">Ebben a példában a következő naplóbejegyzés készül a kötelező könyveléshez a fizetési ütemezésből.</span><span class="sxs-lookup"><span data-stu-id="32f9a-317">For this example, the following journal entry is produced for the statutory book from the payment schedule.</span></span>

### <a name="lease-payment--1312020--je-100"></a><span data-ttu-id="32f9a-318">Lízingdíjfizetés – 2020.01.31. – JE 100</span><span class="sxs-lookup"><span data-stu-id="32f9a-318">Lease payment – 1/31/2020 – JE 100</span></span>

| <span data-ttu-id="32f9a-319">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-319">Account type</span></span> | <span data-ttu-id="32f9a-320">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-320">Account number</span></span> | <span data-ttu-id="32f9a-321">Réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-321">Layer</span></span>   | <span data-ttu-id="32f9a-322">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-322">Account description</span></span> | <span data-ttu-id="32f9a-323">Tartozik</span><span class="sxs-lookup"><span data-stu-id="32f9a-323">Debit</span></span>    | <span data-ttu-id="32f9a-324">Követel</span><span class="sxs-lookup"><span data-stu-id="32f9a-324">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="32f9a-325">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-325">Ledger</span></span>       | <span data-ttu-id="32f9a-326">1</span><span class="sxs-lookup"><span data-stu-id="32f9a-326">1</span></span>              | <span data-ttu-id="32f9a-327">Aktuális</span><span class="sxs-lookup"><span data-stu-id="32f9a-327">Current</span></span> | <span data-ttu-id="32f9a-328">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-328">Lease expense</span></span>       | <span data-ttu-id="32f9a-329">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-329">1,000.00</span></span> |          |
| <span data-ttu-id="32f9a-330">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-330">Ledger</span></span>       | <span data-ttu-id="32f9a-331">4</span><span class="sxs-lookup"><span data-stu-id="32f9a-331">4</span></span>              | <span data-ttu-id="32f9a-332">Aktuális</span><span class="sxs-lookup"><span data-stu-id="32f9a-332">Current</span></span> | <span data-ttu-id="32f9a-333">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="32f9a-333">Clearing account</span></span>    |          | <span data-ttu-id="32f9a-334">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-334">1,000.00</span></span> |

<span data-ttu-id="32f9a-335">A Kötelezettségekkel kapcsolatos adminisztrátorok a standard Dynamics 365 funkciót használják egy számla létrehozásához, amely a lízing külső Eszközlízingje esetén fizetendő.</span><span class="sxs-lookup"><span data-stu-id="32f9a-335">An Accounts payable clerk uses standard Dynamics 365 functionality to create an invoice to pay for the lease outside Asset leasing.</span></span> <span data-ttu-id="32f9a-336">Ha viszont a **Lízingköltség** lehetőséget nem tartozási számlaként választja, akkor a Kötelezettségek adminisztrátora egy elszámolási számlát választ a következő bejegyzés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="32f9a-336">However, instead of selecting **Lease expense** as the debit account, the Accounts payable clerk selects a clearing account to generate the following entry.</span></span>

### <a name="ap-process--1312020--je-110"></a><span data-ttu-id="32f9a-337">AP-folyamat – 2020.01.31. – JE 110</span><span class="sxs-lookup"><span data-stu-id="32f9a-337">AP process – 1/31/2020 – JE 110</span></span>

| <span data-ttu-id="32f9a-338">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-338">Account type</span></span> | <span data-ttu-id="32f9a-339">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-339">Account number</span></span> | <span data-ttu-id="32f9a-340">Réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-340">Layer</span></span>   | <span data-ttu-id="32f9a-341">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-341">Account description</span></span> | <span data-ttu-id="32f9a-342">Tartozik</span><span class="sxs-lookup"><span data-stu-id="32f9a-342">Debit</span></span>    | <span data-ttu-id="32f9a-343">Követel</span><span class="sxs-lookup"><span data-stu-id="32f9a-343">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="32f9a-344">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-344">Ledger</span></span>       | <span data-ttu-id="32f9a-345">4</span><span class="sxs-lookup"><span data-stu-id="32f9a-345">4</span></span>              | <span data-ttu-id="32f9a-346">Aktuális</span><span class="sxs-lookup"><span data-stu-id="32f9a-346">Current</span></span> | <span data-ttu-id="32f9a-347">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="32f9a-347">Clearing account</span></span>    | <span data-ttu-id="32f9a-348">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-348">1,000.00</span></span> |          |
| <span data-ttu-id="32f9a-349">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-349">Ledger</span></span>       | <span data-ttu-id="32f9a-350">2</span><span class="sxs-lookup"><span data-stu-id="32f9a-350">2</span></span>              | <span data-ttu-id="32f9a-351">Aktuális</span><span class="sxs-lookup"><span data-stu-id="32f9a-351">Current</span></span> | <span data-ttu-id="32f9a-352">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-352">Bank fee</span></span>            | <span data-ttu-id="32f9a-353">3.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-353">3.00</span></span>     |          |
| <span data-ttu-id="32f9a-354">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-354">Ledger</span></span>       | <span data-ttu-id="32f9a-355">3</span><span class="sxs-lookup"><span data-stu-id="32f9a-355">3</span></span>              | <span data-ttu-id="32f9a-356">Aktuális</span><span class="sxs-lookup"><span data-stu-id="32f9a-356">Current</span></span> | <span data-ttu-id="32f9a-357">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-357">VAT expense</span></span>         | <span data-ttu-id="32f9a-358">5.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-358">5.00</span></span>     |          |
| <span data-ttu-id="32f9a-359">Szállító</span><span class="sxs-lookup"><span data-stu-id="32f9a-359">Vendor</span></span>       | <span data-ttu-id="32f9a-360">5</span><span class="sxs-lookup"><span data-stu-id="32f9a-360">5</span></span>              | <span data-ttu-id="32f9a-361">Aktuális</span><span class="sxs-lookup"><span data-stu-id="32f9a-361">Current</span></span> | <span data-ttu-id="32f9a-362">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="32f9a-362">Accounts payable</span></span>    |          | <span data-ttu-id="32f9a-363">1,008.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-363">1,008.00</span></span> |

<span data-ttu-id="32f9a-364">Amikor a kimutatást kiállítják a szállítónak, a szokásos fizetési folyamatot követik.</span><span class="sxs-lookup"><span data-stu-id="32f9a-364">When the statement is issued to the vendor, you follow the regular payment process.</span></span> <span data-ttu-id="32f9a-365">A folyamat során a következő naplóbejegyzés jön létre.</span><span class="sxs-lookup"><span data-stu-id="32f9a-365">During this process, the following journal entry is generated.</span></span>

### <a name="cash-payment--1312020--je-120"></a><span data-ttu-id="32f9a-366">Készpénzes fizetés – 2020.01.31. – JE 120</span><span class="sxs-lookup"><span data-stu-id="32f9a-366">Cash payment – 1/31/2020 – JE 120</span></span>

| <span data-ttu-id="32f9a-367">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-367">Account type</span></span> | <span data-ttu-id="32f9a-368">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-368">Account number</span></span> | <span data-ttu-id="32f9a-369">Réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-369">Layer</span></span>   | <span data-ttu-id="32f9a-370">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-370">Account description</span></span> | <span data-ttu-id="32f9a-371">Tartozik</span><span class="sxs-lookup"><span data-stu-id="32f9a-371">Debit</span></span>    | <span data-ttu-id="32f9a-372">Követel</span><span class="sxs-lookup"><span data-stu-id="32f9a-372">Credit</span></span>   |
|--------------|----------------|---------|---------------------|----------|----------|
| <span data-ttu-id="32f9a-373">Szállító</span><span class="sxs-lookup"><span data-stu-id="32f9a-373">Vendor</span></span>       | <span data-ttu-id="32f9a-374">5</span><span class="sxs-lookup"><span data-stu-id="32f9a-374">5</span></span>              | <span data-ttu-id="32f9a-375">Aktuális</span><span class="sxs-lookup"><span data-stu-id="32f9a-375">Current</span></span> | <span data-ttu-id="32f9a-376">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="32f9a-376">Accounts Payable</span></span>    | <span data-ttu-id="32f9a-377">1,008.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-377">1,008.00</span></span> |          |
| <span data-ttu-id="32f9a-378">Bank</span><span class="sxs-lookup"><span data-stu-id="32f9a-378">Bank</span></span>         | <span data-ttu-id="32f9a-379">9</span><span class="sxs-lookup"><span data-stu-id="32f9a-379">9</span></span>              | <span data-ttu-id="32f9a-380">Aktuális</span><span class="sxs-lookup"><span data-stu-id="32f9a-380">Current</span></span> | <span data-ttu-id="32f9a-381">Készpénz</span><span class="sxs-lookup"><span data-stu-id="32f9a-381">Cash</span></span>                |          | <span data-ttu-id="32f9a-382">1,008.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-382">1,008.00</span></span> |

<span data-ttu-id="32f9a-383">Ezen a ponton már teljes mértékben elszámolta ezt a lízinget a kötelező jelentési követelmények között, és a jelenlegi réteg használatával generálhat egy főkönyvi kivonatot.</span><span class="sxs-lookup"><span data-stu-id="32f9a-383">At this point, you've fully accounted for this lease under statutory reporting requirements and can generate a trial balance by using the current layer.</span></span> <span data-ttu-id="32f9a-384">A rendszer a következő számú főkönyvi kivonatot küld vissza.</span><span class="sxs-lookup"><span data-stu-id="32f9a-384">The system returns a trial balance that has the following figures.</span></span>

<table>
<thead>
<tr>
<th rowspan='3'><span data-ttu-id="32f9a-385">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-385">Account number</span></span></th>
<th rowspan='3'><span data-ttu-id="32f9a-386">Leírás</span><span class="sxs-lookup"><span data-stu-id="32f9a-386">Description</span></span></th>
<th colspan='3'><span data-ttu-id="32f9a-387">Kötelező könyv (jelenlegi réteg)</span><span class="sxs-lookup"><span data-stu-id="32f9a-387">Statutory book (current layer)</span></span></th>
<th rowspan='3'><span data-ttu-id="32f9a-388">Aktuális réteg összesen</span><span class="sxs-lookup"><span data-stu-id="32f9a-388">Current layer total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="32f9a-389">JE-100</span><span class="sxs-lookup"><span data-stu-id="32f9a-389">JE-100</span></span></th>
<th><span data-ttu-id="32f9a-390">JE-110</span><span class="sxs-lookup"><span data-stu-id="32f9a-390">JE-110</span></span></th>
<th><span data-ttu-id="32f9a-391">JE-120</span><span class="sxs-lookup"><span data-stu-id="32f9a-391">JE-120</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="32f9a-392">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-392">Dr (Cr)</span></span></th>
<th><span data-ttu-id="32f9a-393">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-393">Dr (Cr)</span></span></th>
<th><span data-ttu-id="32f9a-394">Dr (Cr)</span><span class="sxs-lookup"><span data-stu-id="32f9a-394">Dr (Cr)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="32f9a-395">1</span><span class="sxs-lookup"><span data-stu-id="32f9a-395">1</span></span></td>
<td><span data-ttu-id="32f9a-396">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-396">Lease expense</span></span></td>
<td><span data-ttu-id="32f9a-397">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-397">1,000.00</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-398">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-398">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-399">2</span><span class="sxs-lookup"><span data-stu-id="32f9a-399">2</span></span></td>
<td><span data-ttu-id="32f9a-400">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-400">Bank fee</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-401">3.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-401">3.00</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-402">3.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-402">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-403">3</span><span class="sxs-lookup"><span data-stu-id="32f9a-403">3</span></span></td>
<td><span data-ttu-id="32f9a-404">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-404">VAT expense</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-405">5.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-405">5.00</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-406">5.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-406">5.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-407">4</span><span class="sxs-lookup"><span data-stu-id="32f9a-407">4</span></span></td>
<td><span data-ttu-id="32f9a-408">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="32f9a-408">Clearing account</span></span></td>
<td><span data-ttu-id="32f9a-409">-1 000,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-409">-1,000.00</span></span></td>
<td><span data-ttu-id="32f9a-410">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-410">1,000.00</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-411">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-411">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-412">5</span><span class="sxs-lookup"><span data-stu-id="32f9a-412">5</span></span></td>
<td><span data-ttu-id="32f9a-413">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="32f9a-413">Accounts payable</span></span></td>
<td></td>
<td><span data-ttu-id="32f9a-414">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-414">-1,008.00</span></span></td>
<td><span data-ttu-id="32f9a-415">1,008.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-415">1,008.00</span></span></td>
<td><span data-ttu-id="32f9a-416">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-416">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-417">6</span><span class="sxs-lookup"><span data-stu-id="32f9a-417">6</span></span></td>
<td><span data-ttu-id="32f9a-418">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="32f9a-418">ROU asset</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-419">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-419">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-420">7</span><span class="sxs-lookup"><span data-stu-id="32f9a-420">7</span></span></td>
<td><span data-ttu-id="32f9a-421">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="32f9a-421">Finance lease obligation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-422">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-422">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-423">8</span><span class="sxs-lookup"><span data-stu-id="32f9a-423">8</span></span></td>
<td><span data-ttu-id="32f9a-424">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-424">Interest expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-425">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-425">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-426">9</span><span class="sxs-lookup"><span data-stu-id="32f9a-426">9</span></span></td>
<td><span data-ttu-id="32f9a-427">Készpénz</span><span class="sxs-lookup"><span data-stu-id="32f9a-427">Cash</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-428">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-428">-1,008.00</span></span></td>
<td><span data-ttu-id="32f9a-429">-1.008,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-429">-1,008.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-430">10</span><span class="sxs-lookup"><span data-stu-id="32f9a-430">10</span></span></td>
<td><span data-ttu-id="32f9a-431">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="32f9a-431">Depreciation expense</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-432">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-432">0.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32f9a-433">11</span><span class="sxs-lookup"><span data-stu-id="32f9a-433">11</span></span></td>
<td><span data-ttu-id="32f9a-434">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="32f9a-434">Accumulated depreciation</span></span></td>
<td></td>
<td></td>
<td></td>
<td><span data-ttu-id="32f9a-435">0,00</span><span class="sxs-lookup"><span data-stu-id="32f9a-435">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="32f9a-436">Ha azt szeretné, hogy az IFRS 16 számokkal ugyanaz a főkönyvi kivonat fusson, akkor a kötelező könyvelési napló bejegyzéseit sztornírozni kell, és az IFRS 16 napló bejegyzéseit fel kell adni.</span><span class="sxs-lookup"><span data-stu-id="32f9a-436">If you want to use the IFRS 16 figures to run the same trial balance, the statutory accounting journal entries must be reversed, and the IFRS 16 journal entries must be posted.</span></span> <span data-ttu-id="32f9a-437">A kötelező naplóbejegyzések sztornírozásához ez a példa olyan kötelező sztornírozási könyvet tartalmaz, amelynek ugyanaz a beállítása, mint a kötelező könyvé, de ellenkező feladási profilú.</span><span class="sxs-lookup"><span data-stu-id="32f9a-437">To reverse the statutory journal entries, this example includes a statutory reversal book that has the same setup as the statutory book but an opposite posting profile.</span></span> <span data-ttu-id="32f9a-438">Például a kötelező könyv *megterhelt* egy lízingköltség-számlát, de a sztornírozási könyv *jóváírja* ezt a számlát.</span><span class="sxs-lookup"><span data-stu-id="32f9a-438">For example, the statutory book *debited* a lease expense account, but the reversal book will *credit* this account.</span></span> <span data-ttu-id="32f9a-439">Ezek a kapcsolatok könnyen meghatározhatók az **Eszközlízing paraméterek** oldalon (**Eszközlízing paraméterek \> Beállítás \> Eszközlízing paraméterek**) található Eszközlízing feladási számlákban.</span><span class="sxs-lookup"><span data-stu-id="32f9a-439">These relationships are easily defined in the Asset leasing posting accounts on the **Asset leasing parameters** page (**Asset leasing \> Setup \> Asset leasing parameters**).</span></span>

<span data-ttu-id="32f9a-440">Ha a sztornírozási könyvhöz a kötelező könyvhöz használt eljárást használja, a következő naplóbejegyzés jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="32f9a-440">When the same process that was used for the statutory book is used for the reversal book, the following journal entry is produced.</span></span> <span data-ttu-id="32f9a-441">A különbség az, hogy a sztornírozási könyv a sztornírozási bejegyzéseket a kötelező könyvből állítja be.</span><span class="sxs-lookup"><span data-stu-id="32f9a-441">The difference is that the reversal book books the reversing entries from the statutory book.</span></span> <span data-ttu-id="32f9a-442">A sztornírozási bejegyzések az egyéni rétegre is vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="32f9a-442">The reversing entries are also made to the custom layer.</span></span> <span data-ttu-id="32f9a-443">Ha az aktuális rétegen fut egy főkönyvi kivonat, a sztornírozó naplóbejegyzések nem szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="32f9a-443">When a trial balance is run at the current layer, the reversing journal entries aren't included.</span></span>

### <a name="lease-payment--1312020--je-130"></a><span data-ttu-id="32f9a-444">Lízingdíjfizetés – 2020.01.31. – JE 130</span><span class="sxs-lookup"><span data-stu-id="32f9a-444">Lease payment – 1/31/2020 – JE 130</span></span>

| <span data-ttu-id="32f9a-445">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-445">Account type</span></span> | <span data-ttu-id="32f9a-446">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-446">Account number</span></span> | <span data-ttu-id="32f9a-447">Réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-447">Layer</span></span>  | <span data-ttu-id="32f9a-448">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-448">Account description</span></span> | <span data-ttu-id="32f9a-449">Tartozik</span><span class="sxs-lookup"><span data-stu-id="32f9a-449">Debit</span></span>    | <span data-ttu-id="32f9a-450">Követel</span><span class="sxs-lookup"><span data-stu-id="32f9a-450">Credit</span></span>   |
|--------------|----------------|--------|---------------------|----------|----------|
| <span data-ttu-id="32f9a-451">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-451">Ledger</span></span>       | <span data-ttu-id="32f9a-452">4</span><span class="sxs-lookup"><span data-stu-id="32f9a-452">4</span></span>              | <span data-ttu-id="32f9a-453">Egyéni</span><span class="sxs-lookup"><span data-stu-id="32f9a-453">Custom</span></span> | <span data-ttu-id="32f9a-454">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="32f9a-454">Clearing account</span></span>    | <span data-ttu-id="32f9a-455">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-455">1,000.00</span></span> |          |
| <span data-ttu-id="32f9a-456">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-456">Ledger</span></span>       | <span data-ttu-id="32f9a-457">1</span><span class="sxs-lookup"><span data-stu-id="32f9a-457">1</span></span>              | <span data-ttu-id="32f9a-458">Egyéni</span><span class="sxs-lookup"><span data-stu-id="32f9a-458">Custom</span></span> | <span data-ttu-id="32f9a-459">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-459">Lease expense</span></span>       |          | <span data-ttu-id="32f9a-460">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-460">1,000.00</span></span> |

<span data-ttu-id="32f9a-461">Most, hogy megszüntette a kötelező naplóbejegyzéseket, az IFRS 16 az IFRS 16-ban lefoglalja az összes naplóbejegyzést.</span><span class="sxs-lookup"><span data-stu-id="32f9a-461">Now that you've eliminated the statutory journal entries, you will book all the journal entries that IFRS 16 requires in the IFRS 16 book.</span></span> <span data-ttu-id="32f9a-462">Ezek a bejegyzések tartalmazzák a ROU-eszköz és a kötelezettség kezdeti megjelenítését, valamint a kamat- és értékcsökkenési nyilvántartást.</span><span class="sxs-lookup"><span data-stu-id="32f9a-462">These entries include the initial recognition of the ROU asset and the liability, and the record of interest and depreciation.</span></span>

### <a name="initial-recognition--112020--je-140"></a><span data-ttu-id="32f9a-463">Kezdeti elszámolás – 2020.01.01. – JE 140</span><span class="sxs-lookup"><span data-stu-id="32f9a-463">Initial recognition – 1/1/2020 – JE 140</span></span>

| <span data-ttu-id="32f9a-464">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-464">Account type</span></span> | <span data-ttu-id="32f9a-465">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-465">Account number</span></span> | <span data-ttu-id="32f9a-466">Réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-466">Layer</span></span>  | <span data-ttu-id="32f9a-467">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-467">Account description</span></span>      | <span data-ttu-id="32f9a-468">Tartozik</span><span class="sxs-lookup"><span data-stu-id="32f9a-468">Debit</span></span>     | <span data-ttu-id="32f9a-469">Követel</span><span class="sxs-lookup"><span data-stu-id="32f9a-469">Credit</span></span>    |
|--------------|----------------|--------|--------------------------|-----------|-----------|
| <span data-ttu-id="32f9a-470">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-470">Ledger</span></span>       | <span data-ttu-id="32f9a-471">6</span><span class="sxs-lookup"><span data-stu-id="32f9a-471">6</span></span>              | <span data-ttu-id="32f9a-472">Egyéni</span><span class="sxs-lookup"><span data-stu-id="32f9a-472">Custom</span></span> | <span data-ttu-id="32f9a-473">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="32f9a-473">ROU Asset</span></span>                | <span data-ttu-id="32f9a-474">22,793.90</span><span class="sxs-lookup"><span data-stu-id="32f9a-474">22,793.90</span></span> |           |
| <span data-ttu-id="32f9a-475">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-475">Ledger</span></span>       | <span data-ttu-id="32f9a-476">7</span><span class="sxs-lookup"><span data-stu-id="32f9a-476">7</span></span>              | <span data-ttu-id="32f9a-477">Egyéni</span><span class="sxs-lookup"><span data-stu-id="32f9a-477">Custom</span></span> | <span data-ttu-id="32f9a-478">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="32f9a-478">Finance lease obligation</span></span> |           | <span data-ttu-id="32f9a-479">22,793.90</span><span class="sxs-lookup"><span data-stu-id="32f9a-479">22,793.90</span></span> |

<span data-ttu-id="32f9a-480">A lízingdíjfizetés a többi lízingdíjfizetéshez hasonlóan kerül feladása.</span><span class="sxs-lookup"><span data-stu-id="32f9a-480">The lease payment is posted like the other lease payments.</span></span> <span data-ttu-id="32f9a-481">A kiegyenlítési számla használatának oka annak biztosítása, hogy a készpénz csak egyszer kerüljön jóváírásra.</span><span class="sxs-lookup"><span data-stu-id="32f9a-481">The reason for using the clearing account is to ensure that cash is credited only one time.</span></span>

### <a name="lease-payment--1312020--je-150"></a><span data-ttu-id="32f9a-482">Lízingdíjfizetés – 2020.01.31. – JE 150</span><span class="sxs-lookup"><span data-stu-id="32f9a-482">Lease payment – 1/31/2020 – JE 150</span></span>

| <span data-ttu-id="32f9a-483">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-483">Account type</span></span> | <span data-ttu-id="32f9a-484">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-484">Account number</span></span> | <span data-ttu-id="32f9a-485">Réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-485">Layer</span></span>  | <span data-ttu-id="32f9a-486">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-486">Account description</span></span>      | <span data-ttu-id="32f9a-487">Tartozik</span><span class="sxs-lookup"><span data-stu-id="32f9a-487">Debit</span></span>    | <span data-ttu-id="32f9a-488">Követel</span><span class="sxs-lookup"><span data-stu-id="32f9a-488">Credit</span></span>   |
|--------------|----------------|--------|--------------------------|----------|----------|
| <span data-ttu-id="32f9a-489">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-489">Ledger</span></span>       | <span data-ttu-id="32f9a-490">7</span><span class="sxs-lookup"><span data-stu-id="32f9a-490">7</span></span>              | <span data-ttu-id="32f9a-491">Egyéni</span><span class="sxs-lookup"><span data-stu-id="32f9a-491">Custom</span></span> | <span data-ttu-id="32f9a-492">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="32f9a-492">Finance lease obligation</span></span> | <span data-ttu-id="32f9a-493">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-493">1,000.00</span></span> |          |
| <span data-ttu-id="32f9a-494">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-494">Ledger</span></span>       | <span data-ttu-id="32f9a-495">4</span><span class="sxs-lookup"><span data-stu-id="32f9a-495">4</span></span>              | <span data-ttu-id="32f9a-496">Egyéni</span><span class="sxs-lookup"><span data-stu-id="32f9a-496">Custom</span></span> | <span data-ttu-id="32f9a-497">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="32f9a-497">Clearing account</span></span>         |          | <span data-ttu-id="32f9a-498">1,000.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-498">1,000.00</span></span> |

<span data-ttu-id="32f9a-499">A kamatráfordítási naplóbejegyzés a kötelezettség amortizációs ütemezéséből jön létre.</span><span class="sxs-lookup"><span data-stu-id="32f9a-499">The interest expense journal entry is generated from the liability amortization schedule.</span></span>

### <a name="interest-expense--1312020--je-160"></a><span data-ttu-id="32f9a-500">Kamatköltség – 2020.01.31. – JE 160</span><span class="sxs-lookup"><span data-stu-id="32f9a-500">Interest expense – 1/31/2020 – JE 160</span></span>

| <span data-ttu-id="32f9a-501">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-501">Account type</span></span> | <span data-ttu-id="32f9a-502">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-502">Account number</span></span> | <span data-ttu-id="32f9a-503">Réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-503">Layer</span></span>  | <span data-ttu-id="32f9a-504">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-504">Account description</span></span>      | <span data-ttu-id="32f9a-505">Tartozik</span><span class="sxs-lookup"><span data-stu-id="32f9a-505">Debit</span></span> | <span data-ttu-id="32f9a-506">Követel</span><span class="sxs-lookup"><span data-stu-id="32f9a-506">Credit</span></span> |
|--------------|----------------|--------|--------------------------|-------|--------|
| <span data-ttu-id="32f9a-507">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-507">Ledger</span></span>       | <span data-ttu-id="32f9a-508">8</span><span class="sxs-lookup"><span data-stu-id="32f9a-508">8</span></span>              | <span data-ttu-id="32f9a-509">Egyéni</span><span class="sxs-lookup"><span data-stu-id="32f9a-509">Custom</span></span> | <span data-ttu-id="32f9a-510">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-510">Interest expense</span></span>         | <span data-ttu-id="32f9a-511">94.97</span><span class="sxs-lookup"><span data-stu-id="32f9a-511">94.97</span></span> |        |
| <span data-ttu-id="32f9a-512">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-512">Ledger</span></span>       | <span data-ttu-id="32f9a-513">7</span><span class="sxs-lookup"><span data-stu-id="32f9a-513">7</span></span>              | <span data-ttu-id="32f9a-514">Egyéni</span><span class="sxs-lookup"><span data-stu-id="32f9a-514">Custom</span></span> | <span data-ttu-id="32f9a-515">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="32f9a-515">Finance lease obligation</span></span> |       | <span data-ttu-id="32f9a-516">94.97</span><span class="sxs-lookup"><span data-stu-id="32f9a-516">94.97</span></span>  |

<span data-ttu-id="32f9a-517">Az értékcsökkenési költség-naplóbejegyzés az eszközértékcsökkenési ütemezéséből jön létre.</span><span class="sxs-lookup"><span data-stu-id="32f9a-517">The depreciation expense journal entry is generated from the asset depreciation schedule.</span></span>

### <a name="depreciation-expense--1312020--je-170"></a><span data-ttu-id="32f9a-518">Értékcsökkenés költsége – 2020.01.31. – JE 170</span><span class="sxs-lookup"><span data-stu-id="32f9a-518">Depreciation expense – 1/31/2020 – JE 170</span></span>

| <span data-ttu-id="32f9a-519">Számla típusa</span><span class="sxs-lookup"><span data-stu-id="32f9a-519">Account type</span></span> | <span data-ttu-id="32f9a-520">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-520">Account number</span></span> | <span data-ttu-id="32f9a-521">Réteg</span><span class="sxs-lookup"><span data-stu-id="32f9a-521">Layer</span></span>  | <span data-ttu-id="32f9a-522">Számla leírása</span><span class="sxs-lookup"><span data-stu-id="32f9a-522">Account description</span></span>      | <span data-ttu-id="32f9a-523">Tartozik</span><span class="sxs-lookup"><span data-stu-id="32f9a-523">Debit</span></span>  | <span data-ttu-id="32f9a-524">Követel</span><span class="sxs-lookup"><span data-stu-id="32f9a-524">Credit</span></span> |
|--------------|----------------|--------|--------------------------|--------|--------|
| <span data-ttu-id="32f9a-525">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-525">Ledger</span></span>       | <span data-ttu-id="32f9a-526">10</span><span class="sxs-lookup"><span data-stu-id="32f9a-526">10</span></span>             | <span data-ttu-id="32f9a-527">Egyéni</span><span class="sxs-lookup"><span data-stu-id="32f9a-527">Custom</span></span> | <span data-ttu-id="32f9a-528">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="32f9a-528">Depreciation expense</span></span>     | <span data-ttu-id="32f9a-529">949.75</span><span class="sxs-lookup"><span data-stu-id="32f9a-529">949.75</span></span> |        |
| <span data-ttu-id="32f9a-530">Ledger</span><span class="sxs-lookup"><span data-stu-id="32f9a-530">Ledger</span></span>       | <span data-ttu-id="32f9a-531">11</span><span class="sxs-lookup"><span data-stu-id="32f9a-531">11</span></span>             | <span data-ttu-id="32f9a-532">Egyéni</span><span class="sxs-lookup"><span data-stu-id="32f9a-532">Custom</span></span> | <span data-ttu-id="32f9a-533">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="32f9a-533">Accumulated depreciation</span></span> |        | <span data-ttu-id="32f9a-534">949.75</span><span class="sxs-lookup"><span data-stu-id="32f9a-534">949.75</span></span> |

<span data-ttu-id="32f9a-535">Miután az összes naplóbejegyzést létrehozta és feladta, akkor a következő „1. egyéni réteg” értékeket fogja látni.</span><span class="sxs-lookup"><span data-stu-id="32f9a-535">After all these journal entries are created and posted, you will see the following "custom layer 1" values.</span></span> <span data-ttu-id="32f9a-536">Ne feledje, hogy az utolsó oszlop tartalmazza a banki díjat, az áfaköltséget (ÁFA) és az előző rétegből származó készpénz csökkentését, de nem tartalmazza a kötelező jelentési naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="32f9a-536">Note that the last column includes the bank fee, the value-added tax (VAT) expense, and the reduction of cash from the previous layer, but it doesn't include the statutory reporting journal entries.</span></span> <span data-ttu-id="32f9a-537">Ezért valódi kettős jelentéskészítési képességeket érhet el.</span><span class="sxs-lookup"><span data-stu-id="32f9a-537">Therefore, you achieve true dual-reporting capabilities.</span></span> <span data-ttu-id="32f9a-538">Ezen a ponton a vállalatnak csak futtatnia kell a főkönyvi kivonatot, és kombinálnia kell az aktuális réteget és az egyéni réteget az IFRS főkönyvi kivonat létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="32f9a-538">At this point, the company just has to run its trial balance, and combine the current layer and the custom layer to create an IFRS trial balance.</span></span>

| <span data-ttu-id="32f9a-539">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="32f9a-539">Account No</span></span> | <span data-ttu-id="32f9a-540">Leírás</span><span class="sxs-lookup"><span data-stu-id="32f9a-540">Description</span></span>              | <span data-ttu-id="32f9a-541">Kötelező könyv\-Aktuális réteg\-JE\-100\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="32f9a-541">Statutory Book\-Current Layer\-JE\-100\-Dr \(Cr\)</span></span> | <span data-ttu-id="32f9a-542">Kötelező könyv\-Aktuális réteg\-JE\-110\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="32f9a-542">Statutory Book\-Current Layer\-JE\-110\-Dr \(Cr\)</span></span> | <span data-ttu-id="32f9a-543">Kötelező könyv\-Aktuális réteg\-JE\-120\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="32f9a-543">Statutory Book\-Current Layer\-JE\-120\-Dr \(Cr\)</span></span> | <span data-ttu-id="32f9a-544">Aktuális réteg \- Összesen</span><span class="sxs-lookup"><span data-stu-id="32f9a-544">Current Layer \- Totals</span></span> | - | <span data-ttu-id="32f9a-545">Sztornírozási könyv\-Egyéni réteg\-JE\-130\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="32f9a-545">Reversal Book\-Custom layer\-JE\-130\-Dr \(Cr\)</span></span> | <span data-ttu-id="32f9a-546">IFRS 16 könyv\-Egyéni réteg\-JE\-140\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="32f9a-546">IFRS 16 Book\-Custom layer\-JE\-140\-Dr \(Cr\)</span></span> | <span data-ttu-id="32f9a-547">IFRS 16 könyv\-Egyéni réteg\-JE\-150\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="32f9a-547">IFRS 16 Book\-Custom layer\-JE\-150\-Dr \(Cr\)</span></span> | <span data-ttu-id="32f9a-548">IFRS 16 könyv\-Egyéni réteg\-JE\-160\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="32f9a-548">IFRS 16 Book\-Custom layer\-JE\-160\-Dr \(Cr\)</span></span> | <span data-ttu-id="32f9a-549">IFRS 16 könyv\-Egyéni réteg\-JE\-170\-Dr \(Cr\)</span><span class="sxs-lookup"><span data-stu-id="32f9a-549">IFRS 16 Book\-Custom layer\-JE\-170\-Dr \(Cr\)</span></span> | <span data-ttu-id="32f9a-550">Egyéni réteg \+ Egyéni réteg \- Összesen</span><span class="sxs-lookup"><span data-stu-id="32f9a-550">Custom Layer \+ Current Layer \- Totals</span></span> |
|------------|--------------------------|---------------------------------------------------|---------------------------------------------------|---------------------------------------------------|-------------------------|---|-------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------|
| <span data-ttu-id="32f9a-551">1</span><span class="sxs-lookup"><span data-stu-id="32f9a-551">1</span></span>          | <span data-ttu-id="32f9a-552">Lízingköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-552">Lease expense</span></span>            | <span data-ttu-id="32f9a-553">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-553">1,000\.00</span></span>                                         |                                                   |                                                   | <span data-ttu-id="32f9a-554">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-554">1,000\.00</span></span>               |   | <span data-ttu-id="32f9a-555">\-1.000.</span><span class="sxs-lookup"><span data-stu-id="32f9a-555">\-1,000</span></span>                                         |                                                |                                                |                                                |                                                | <span data-ttu-id="32f9a-556">0\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-556">0\.00</span></span>                                   |
| <span data-ttu-id="32f9a-557">2</span><span class="sxs-lookup"><span data-stu-id="32f9a-557">2</span></span>          | <span data-ttu-id="32f9a-558">Bankköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-558">Bank fee</span></span>                 |                                                   | <span data-ttu-id="32f9a-559">3\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-559">3\.00</span></span>                                             |                                                   | <span data-ttu-id="32f9a-560">3\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-560">3\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="32f9a-561">3\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-561">3\.00</span></span>                                   |
| <span data-ttu-id="32f9a-562">3</span><span class="sxs-lookup"><span data-stu-id="32f9a-562">3</span></span>          | <span data-ttu-id="32f9a-563">Áfaköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-563">VAT expense</span></span>              |                                                   | <span data-ttu-id="32f9a-564">5\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-564">5\.00</span></span>                                             |                                                   | <span data-ttu-id="32f9a-565">5\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-565">5\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="32f9a-566">5\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-566">5\.00</span></span>                                   |
| <span data-ttu-id="32f9a-567">4</span><span class="sxs-lookup"><span data-stu-id="32f9a-567">4</span></span>          | <span data-ttu-id="32f9a-568">Elszámolási számla</span><span class="sxs-lookup"><span data-stu-id="32f9a-568">Clearing account</span></span>         | <span data-ttu-id="32f9a-569">\-1.000\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-569">\-1,000\.00</span></span>                                       | <span data-ttu-id="32f9a-570">1,000\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-570">1,000\.00</span></span>                                         |                                                   | <span data-ttu-id="32f9a-571">0\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-571">0\.00</span></span>                   |   | <span data-ttu-id="32f9a-572">1000</span><span class="sxs-lookup"><span data-stu-id="32f9a-572">1,000</span></span>                                           |                                                | <span data-ttu-id="32f9a-573">\-1.000.</span><span class="sxs-lookup"><span data-stu-id="32f9a-573">\-1,000</span></span>                                        |                                                |                                                | <span data-ttu-id="32f9a-574">0\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-574">0\.00</span></span>                                   |
| <span data-ttu-id="32f9a-575">5</span><span class="sxs-lookup"><span data-stu-id="32f9a-575">5</span></span>          | <span data-ttu-id="32f9a-576">Kötelezettségek</span><span class="sxs-lookup"><span data-stu-id="32f9a-576">Accounts payable</span></span>         |                                                   | <span data-ttu-id="32f9a-577">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-577">\-1,008\.00</span></span>                                       | <span data-ttu-id="32f9a-578">1,008\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-578">1,008\.00</span></span>                                         | <span data-ttu-id="32f9a-579">0\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-579">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="32f9a-580">0\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-580">0\.00</span></span>                                   |
| <span data-ttu-id="32f9a-581">6</span><span class="sxs-lookup"><span data-stu-id="32f9a-581">6</span></span>          | <span data-ttu-id="32f9a-582">ROU-eszköz</span><span class="sxs-lookup"><span data-stu-id="32f9a-582">ROU asset</span></span>                |                                                   |                                                   |                                                   | <span data-ttu-id="32f9a-583">0\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-583">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="32f9a-584">22,794</span><span class="sxs-lookup"><span data-stu-id="32f9a-584">22,794</span></span>                                         |                                                |                                                |                                                | <span data-ttu-id="32f9a-585">22,793\.90</span><span class="sxs-lookup"><span data-stu-id="32f9a-585">22,793\.90</span></span>                              |
| <span data-ttu-id="32f9a-586">7</span><span class="sxs-lookup"><span data-stu-id="32f9a-586">7</span></span>          | <span data-ttu-id="32f9a-587">Pénzügyi lízingkötelezettség</span><span class="sxs-lookup"><span data-stu-id="32f9a-587">Finance lease obligation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="32f9a-588">0\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-588">0\.00</span></span>                   |   |                                                 | <span data-ttu-id="32f9a-589">\-22.794.</span><span class="sxs-lookup"><span data-stu-id="32f9a-589">\-22,794</span></span>                                       | <span data-ttu-id="32f9a-590">1000</span><span class="sxs-lookup"><span data-stu-id="32f9a-590">1,000</span></span>                                          | <span data-ttu-id="32f9a-591">\-94\.97</span><span class="sxs-lookup"><span data-stu-id="32f9a-591">\-94\.97</span></span>                                       |                                                | <span data-ttu-id="32f9a-592">\-21.888\.87</span><span class="sxs-lookup"><span data-stu-id="32f9a-592">\-21,888\.87</span></span>                            |
| <span data-ttu-id="32f9a-593">8</span><span class="sxs-lookup"><span data-stu-id="32f9a-593">8</span></span>          | <span data-ttu-id="32f9a-594">Kamatköltség</span><span class="sxs-lookup"><span data-stu-id="32f9a-594">Interest expense</span></span>         |                                                   |                                                   |                                                   | <span data-ttu-id="32f9a-595">0\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-595">0\.00</span></span>                   |   |                                                 |                                                |                                                | <span data-ttu-id="32f9a-596">94\.97</span><span class="sxs-lookup"><span data-stu-id="32f9a-596">94\.97</span></span>                                         |                                                | <span data-ttu-id="32f9a-597">94\.97</span><span class="sxs-lookup"><span data-stu-id="32f9a-597">94\.97</span></span>                                  |
| <span data-ttu-id="32f9a-598">9</span><span class="sxs-lookup"><span data-stu-id="32f9a-598">9</span></span>          | <span data-ttu-id="32f9a-599">Készpénz</span><span class="sxs-lookup"><span data-stu-id="32f9a-599">Cash</span></span>                     |                                                   |                                                   | <span data-ttu-id="32f9a-600">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-600">\-1,008\.00</span></span>                                       | <span data-ttu-id="32f9a-601">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-601">\-1,008\.00</span></span>             |   |                                                 |                                                |                                                |                                                |                                                | <span data-ttu-id="32f9a-602">\-1.008\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-602">\-1,008\.00</span></span>                             |
| <span data-ttu-id="32f9a-603">10</span><span class="sxs-lookup"><span data-stu-id="32f9a-603">10</span></span>         | <span data-ttu-id="32f9a-604">Értékcsökkenés költsége</span><span class="sxs-lookup"><span data-stu-id="32f9a-604">Depreciation expense</span></span>     |                                                   |                                                   |                                                   | <span data-ttu-id="32f9a-605">0\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-605">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="32f9a-606">949\.75</span><span class="sxs-lookup"><span data-stu-id="32f9a-606">949\.75</span></span>                                        | <span data-ttu-id="32f9a-607">949\.75</span><span class="sxs-lookup"><span data-stu-id="32f9a-607">949\.75</span></span>                                 |
| <span data-ttu-id="32f9a-608">11</span><span class="sxs-lookup"><span data-stu-id="32f9a-608">11</span></span>         | <span data-ttu-id="32f9a-609">Halmozott értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="32f9a-609">Accumulated depreciation</span></span> |                                                   |                                                   |                                                   | <span data-ttu-id="32f9a-610">0\.00</span><span class="sxs-lookup"><span data-stu-id="32f9a-610">0\.00</span></span>                   |   |                                                 |                                                |                                                |                                                | <span data-ttu-id="32f9a-611">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="32f9a-611">\-949\.75</span></span>                                      | <span data-ttu-id="32f9a-612">\-949\.75</span><span class="sxs-lookup"><span data-stu-id="32f9a-612">\-949\.75</span></span>                               |


