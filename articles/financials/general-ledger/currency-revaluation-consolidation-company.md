---
title: "Devizaátértékelés konszolidált vállalatban"
description: "Ez a témakör azt ismerteti, hogyan lehet átértékelni a devizát a konszolidált vállalatban."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2330939ddd7ccf4555cf1eff1e264c51f779c4eb
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="e6cc9-103">Devizaátértékelés konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="e6cc9-103">Currency revaluation in a consolidation company</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="e6cc9-104">Ha egy könyvelési pénznemből egy másikba konszolidál adatokat és változik az árfolyam, devizaátértékelést kell futtatnia, hogy a számlaegyenlegek átértékelése megfelelően történjen.</span><span class="sxs-lookup"><span data-stu-id="e6cc9-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="e6cc9-105">Az adatok eredeti konszolidációja során használja a **Devizaátváltás** lapot, ahol kiválaszthatja a kezdeti árfolyamot a konszolidációs folyamat kezdeti átváltásához.</span><span class="sxs-lookup"><span data-stu-id="e6cc9-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="e6cc9-106">Ha új árfolyamot ad meg (például következő hónapban), át kell értékelnie a számlaegyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="e6cc9-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="e6cc9-107">A nem realizált nyereség vagy nem realizált veszteség ezután az új árfolyamnak és dátumnak megfelelően frissül.</span><span class="sxs-lookup"><span data-stu-id="e6cc9-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="e6cc9-108">Az alábbi példa a könyvelés bejegyzéseket mutatja be, amelyek egy ilyen folyamat során létrejönnek.</span><span class="sxs-lookup"><span data-stu-id="e6cc9-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="e6cc9-109">Vállalat beállítása</span><span class="sxs-lookup"><span data-stu-id="e6cc9-109">Company setup</span></span>
-   <span data-ttu-id="e6cc9-110">**Forrás/működő vállalat (USMF)** – USA-dollárban (USD) van megadva a könyvelési és a jelentési pénznem.</span><span class="sxs-lookup"><span data-stu-id="e6cc9-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="e6cc9-111">**Konszolidált vállalat (CON)** – Euróban (EUR) van megadva a könyvelési és a jelentési pénznem.</span><span class="sxs-lookup"><span data-stu-id="e6cc9-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="e6cc9-112">**Realizált nyereség** – 801500 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="e6cc9-112">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="e6cc9-113">**Realizált veszteség**– 801600 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="e6cc9-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="e6cc9-114">**Nem realizált nyereség**– 801600 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="e6cc9-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="e6cc9-115">**Nem realizált veszteség**– 801400 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="e6cc9-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="e6cc9-116">Eredeti tranzakciók</span><span class="sxs-lookup"><span data-stu-id="e6cc9-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="e6cc9-117">Készpénz-befizetési utalvány tranzakciói USMF-ben</span><span class="sxs-lookup"><span data-stu-id="e6cc9-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="e6cc9-118">Dátum</span><span class="sxs-lookup"><span data-stu-id="e6cc9-118">Date</span></span>       | <span data-ttu-id="e6cc9-119">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="e6cc9-119">Ledger account</span></span>               | <span data-ttu-id="e6cc9-120">Pénznem</span><span class="sxs-lookup"><span data-stu-id="e6cc9-120">Currency</span></span> | <span data-ttu-id="e6cc9-121">Összeg</span><span class="sxs-lookup"><span data-stu-id="e6cc9-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="e6cc9-122">2015/11/10</span><span class="sxs-lookup"><span data-stu-id="e6cc9-122">10/11/2015</span></span> | <span data-ttu-id="e6cc9-123">110110 – készpénz</span><span class="sxs-lookup"><span data-stu-id="e6cc9-123">110110 – Cash</span></span>                | <span data-ttu-id="e6cc9-124">dollár</span><span class="sxs-lookup"><span data-stu-id="e6cc9-124">USD</span></span>      | <span data-ttu-id="e6cc9-125">500</span><span class="sxs-lookup"><span data-stu-id="e6cc9-125">500</span></span>    |
| <span data-ttu-id="e6cc9-126">2015/11/10</span><span class="sxs-lookup"><span data-stu-id="e6cc9-126">10/11/2015</span></span> | <span data-ttu-id="e6cc9-127">130100 – kinnlevőségek</span><span class="sxs-lookup"><span data-stu-id="e6cc9-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="e6cc9-128">dollár</span><span class="sxs-lookup"><span data-stu-id="e6cc9-128">USD</span></span>      | <span data-ttu-id="e6cc9-129">-500</span><span class="sxs-lookup"><span data-stu-id="e6cc9-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="e6cc9-130">Árfolyamok</span><span class="sxs-lookup"><span data-stu-id="e6cc9-130">Exchange rates</span></span>

| <span data-ttu-id="e6cc9-131">Kezdő pénznem</span><span class="sxs-lookup"><span data-stu-id="e6cc9-131">From currency</span></span> | <span data-ttu-id="e6cc9-132">Célpénznem</span><span class="sxs-lookup"><span data-stu-id="e6cc9-132">To currency</span></span> | <span data-ttu-id="e6cc9-133">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="e6cc9-133">Start date</span></span> | <span data-ttu-id="e6cc9-134">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="e6cc9-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="e6cc9-135">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-135">EUR</span></span>           | <span data-ttu-id="e6cc9-136">dollár</span><span class="sxs-lookup"><span data-stu-id="e6cc9-136">USD</span></span>         | <span data-ttu-id="e6cc9-137">2015/1/10</span><span class="sxs-lookup"><span data-stu-id="e6cc9-137">10/1/2015</span></span>  | <span data-ttu-id="e6cc9-138">200</span><span class="sxs-lookup"><span data-stu-id="e6cc9-138">200</span></span>           |
| <span data-ttu-id="e6cc9-139">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-139">EUR</span></span>           | <span data-ttu-id="e6cc9-140">dollár</span><span class="sxs-lookup"><span data-stu-id="e6cc9-140">USD</span></span>         | <span data-ttu-id="e6cc9-141">2015/1/11</span><span class="sxs-lookup"><span data-stu-id="e6cc9-141">11/1/2015</span></span>  | <span data-ttu-id="e6cc9-142">150</span><span class="sxs-lookup"><span data-stu-id="e6cc9-142">150</span></span>           |
| <span data-ttu-id="e6cc9-143">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-143">EUR</span></span>           | <span data-ttu-id="e6cc9-144">dollár</span><span class="sxs-lookup"><span data-stu-id="e6cc9-144">USD</span></span>         | <span data-ttu-id="e6cc9-145">2012/1/12</span><span class="sxs-lookup"><span data-stu-id="e6cc9-145">12/1/2012</span></span>  | <span data-ttu-id="e6cc9-146">100</span><span class="sxs-lookup"><span data-stu-id="e6cc9-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="e6cc9-147">2015 októberében a konszolidáció végrehajtása megtörténik</span><span class="sxs-lookup"><span data-stu-id="e6cc9-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="e6cc9-148">Egyenlegek a konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="e6cc9-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="e6cc9-149">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="e6cc9-149">Ledger account</span></span> | <span data-ttu-id="e6cc9-150">Pénznem</span><span class="sxs-lookup"><span data-stu-id="e6cc9-150">Currency</span></span> | <span data-ttu-id="e6cc9-151">Összeg</span><span class="sxs-lookup"><span data-stu-id="e6cc9-151">Amount</span></span> | <span data-ttu-id="e6cc9-152">Számítás</span><span class="sxs-lookup"><span data-stu-id="e6cc9-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="e6cc9-153">110110</span><span class="sxs-lookup"><span data-stu-id="e6cc9-153">110110</span></span>         | <span data-ttu-id="e6cc9-154">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-154">EUR</span></span>      | <span data-ttu-id="e6cc9-155">250</span><span class="sxs-lookup"><span data-stu-id="e6cc9-155">250</span></span>    | <span data-ttu-id="e6cc9-156">500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="e6cc9-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="e6cc9-157">130100</span><span class="sxs-lookup"><span data-stu-id="e6cc9-157">130100</span></span>         | <span data-ttu-id="e6cc9-158">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-158">EUR</span></span>      | <span data-ttu-id="e6cc9-159">-250</span><span class="sxs-lookup"><span data-stu-id="e6cc9-159">-250</span></span>   | <span data-ttu-id="e6cc9-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="e6cc9-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="e6cc9-161">Devizaátértékelés végrehajtása 2015. október 1. és 2015. november 30. közötti számlákra</span><span class="sxs-lookup"><span data-stu-id="e6cc9-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="e6cc9-162">Egyenlegek a konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="e6cc9-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="e6cc9-163">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="e6cc9-163">Ledger account</span></span> | <span data-ttu-id="e6cc9-164">Pénznem</span><span class="sxs-lookup"><span data-stu-id="e6cc9-164">Currency</span></span> | <span data-ttu-id="e6cc9-165">Összeg</span><span class="sxs-lookup"><span data-stu-id="e6cc9-165">Amount</span></span>  | <span data-ttu-id="e6cc9-166">Számítás</span><span class="sxs-lookup"><span data-stu-id="e6cc9-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="e6cc9-167">110110</span><span class="sxs-lookup"><span data-stu-id="e6cc9-167">110110</span></span>         | <span data-ttu-id="e6cc9-168">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-168">EUR</span></span>      | <span data-ttu-id="e6cc9-169">333,33</span><span class="sxs-lookup"><span data-stu-id="e6cc9-169">333.33</span></span>  | <span data-ttu-id="e6cc9-170">Eredeti összeg 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="e6cc9-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="e6cc9-171">130100</span><span class="sxs-lookup"><span data-stu-id="e6cc9-171">130100</span></span>         | <span data-ttu-id="e6cc9-172">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-172">EUR</span></span>      | <span data-ttu-id="e6cc9-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="e6cc9-173">-333.33</span></span> | <span data-ttu-id="e6cc9-174">Eredeti összeg -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="e6cc9-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="e6cc9-175">801400</span><span class="sxs-lookup"><span data-stu-id="e6cc9-175">801400</span></span>         | <span data-ttu-id="e6cc9-176">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-176">EUR</span></span>      | <span data-ttu-id="e6cc9-177">83,33</span><span class="sxs-lookup"><span data-stu-id="e6cc9-177">83.33</span></span>   | <span data-ttu-id="e6cc9-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="e6cc9-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="e6cc9-179">801600</span><span class="sxs-lookup"><span data-stu-id="e6cc9-179">801600</span></span>         | <span data-ttu-id="e6cc9-180">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-180">EUR</span></span>      | <span data-ttu-id="e6cc9-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="e6cc9-181">-83.33</span></span>  | <span data-ttu-id="e6cc9-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="e6cc9-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="e6cc9-183">A jelentési pénznem összegeihez további tranzakciók történnek.</span><span class="sxs-lookup"><span data-stu-id="e6cc9-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="e6cc9-184">Devizaátértékelés végrehajtása 2015. október 1. és 2015. december 31. közötti számlákra</span><span class="sxs-lookup"><span data-stu-id="e6cc9-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="e6cc9-185">Egyenlegek a konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="e6cc9-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="e6cc9-186">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="e6cc9-186">Ledger account</span></span> | <span data-ttu-id="e6cc9-187">Pénznem</span><span class="sxs-lookup"><span data-stu-id="e6cc9-187">Currency</span></span> | <span data-ttu-id="e6cc9-188">Összeg</span><span class="sxs-lookup"><span data-stu-id="e6cc9-188">Amount</span></span>  | <span data-ttu-id="e6cc9-189">Számítás</span><span class="sxs-lookup"><span data-stu-id="e6cc9-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="e6cc9-190">110110</span><span class="sxs-lookup"><span data-stu-id="e6cc9-190">110110</span></span>         | <span data-ttu-id="e6cc9-191">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-191">EUR</span></span>      | <span data-ttu-id="e6cc9-192">500,00</span><span class="sxs-lookup"><span data-stu-id="e6cc9-192">500.00</span></span>  | <span data-ttu-id="e6cc9-193">Eredeti összeg 500 × 1</span><span class="sxs-lookup"><span data-stu-id="e6cc9-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="e6cc9-194">130100</span><span class="sxs-lookup"><span data-stu-id="e6cc9-194">130100</span></span>         | <span data-ttu-id="e6cc9-195">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-195">EUR</span></span>      | <span data-ttu-id="e6cc9-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="e6cc9-196">-500.00</span></span> | <span data-ttu-id="e6cc9-197">Eredeti összeg -500 × 1</span><span class="sxs-lookup"><span data-stu-id="e6cc9-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="e6cc9-198">801400</span><span class="sxs-lookup"><span data-stu-id="e6cc9-198">801400</span></span>         | <span data-ttu-id="e6cc9-199">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-199">EUR</span></span>      | <span data-ttu-id="e6cc9-200">250</span><span class="sxs-lookup"><span data-stu-id="e6cc9-200">250</span></span>     | <span data-ttu-id="e6cc9-201">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="e6cc9-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="e6cc9-202">801600</span><span class="sxs-lookup"><span data-stu-id="e6cc9-202">801600</span></span>         | <span data-ttu-id="e6cc9-203">HUF</span><span class="sxs-lookup"><span data-stu-id="e6cc9-203">EUR</span></span>      | <span data-ttu-id="e6cc9-204">-250</span><span class="sxs-lookup"><span data-stu-id="e6cc9-204">-250</span></span>    | <span data-ttu-id="e6cc9-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="e6cc9-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






