---
title: "Devizaátértékelés konszolidált vállalatban"
description: 
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: hminzner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 643af8d771685fe8fd652b353d41f2679e0bef8b
ms.contentlocale: hu-hu
ms.lasthandoff: 07/18/2017

---

# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="0ddfe-102">Devizaátértékelés konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="0ddfe-102">Currency revaluation in a consolidation company</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="0ddfe-103">Ha egy könyvelési pénznemből egy másikba konszolidál adatokat és változik az árfolyam, devizaátértékelést kell futtatnia, hogy a számlaegyenlegek átértékelése megfelelően történjen.</span><span class="sxs-lookup"><span data-stu-id="0ddfe-103">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="0ddfe-104">Az adatok eredeti konszolidációja során használja a **Devizaátváltás** lapot, ahol kiválaszthatja a kezdeti árfolyamot a konszolidációs folyamat kezdeti átváltásához.</span><span class="sxs-lookup"><span data-stu-id="0ddfe-104">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="0ddfe-105">Ha új árfolyamot ad meg (például következő hónapban), át kell értékelnie a számlaegyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="0ddfe-105">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="0ddfe-106">A nem realizált nyereség vagy nem realizált veszteség ezután az új árfolyamnak és dátumnak megfelelően frissül.</span><span class="sxs-lookup"><span data-stu-id="0ddfe-106">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="0ddfe-107">Az alábbi példa a könyvelés bejegyzéseket mutatja be, amelyek egy ilyen folyamat során létrejönnek.</span><span class="sxs-lookup"><span data-stu-id="0ddfe-107">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="0ddfe-108">Vállalat beállítása</span><span class="sxs-lookup"><span data-stu-id="0ddfe-108">Company setup</span></span>
-   <span data-ttu-id="0ddfe-109">**Forrás/működő vállalat (USMF)** – USA-dollárban (USD) van megadva a könyvelési és a jelentési pénznem.</span><span class="sxs-lookup"><span data-stu-id="0ddfe-109">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="0ddfe-110">**Konszolidált vállalat (CON)** – Euróban (EUR) van megadva a könyvelési és a jelentési pénznem.</span><span class="sxs-lookup"><span data-stu-id="0ddfe-110">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="0ddfe-111">**Realizált nyereség** – 801500 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="0ddfe-111">**Realized gain **– Ledger account 801500</span></span>
    -   <span data-ttu-id="0ddfe-112">**Realizált veszteség**– 801600 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="0ddfe-112">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="0ddfe-113">**Nem realizált nyereség**– 801600 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="0ddfe-113">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="0ddfe-114">**Nem realizált veszteség**– 801400 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="0ddfe-114">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="0ddfe-115">Eredeti tranzakciók</span><span class="sxs-lookup"><span data-stu-id="0ddfe-115">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="0ddfe-116">Készpénz-befizetési utalvány tranzakciói USMF-ben</span><span class="sxs-lookup"><span data-stu-id="0ddfe-116">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="0ddfe-117">Dátum</span><span class="sxs-lookup"><span data-stu-id="0ddfe-117">Date</span></span>       | <span data-ttu-id="0ddfe-118">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="0ddfe-118">Ledger account</span></span>               | <span data-ttu-id="0ddfe-119">Pénznem</span><span class="sxs-lookup"><span data-stu-id="0ddfe-119">Currency</span></span> | <span data-ttu-id="0ddfe-120">Összeg</span><span class="sxs-lookup"><span data-stu-id="0ddfe-120">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="0ddfe-121">2015/11/10</span><span class="sxs-lookup"><span data-stu-id="0ddfe-121">10/11/2015</span></span> | <span data-ttu-id="0ddfe-122">110110 – készpénz</span><span class="sxs-lookup"><span data-stu-id="0ddfe-122">110110 – Cash</span></span>                | <span data-ttu-id="0ddfe-123">dollár</span><span class="sxs-lookup"><span data-stu-id="0ddfe-123">USD</span></span>      | <span data-ttu-id="0ddfe-124">500</span><span class="sxs-lookup"><span data-stu-id="0ddfe-124">500</span></span>    |
| <span data-ttu-id="0ddfe-125">2015/11/10</span><span class="sxs-lookup"><span data-stu-id="0ddfe-125">10/11/2015</span></span> | <span data-ttu-id="0ddfe-126">130100 – kinnlevőségek</span><span class="sxs-lookup"><span data-stu-id="0ddfe-126">130100 – Accounts Receivable</span></span> | <span data-ttu-id="0ddfe-127">dollár</span><span class="sxs-lookup"><span data-stu-id="0ddfe-127">USD</span></span>      | <span data-ttu-id="0ddfe-128">-500</span><span class="sxs-lookup"><span data-stu-id="0ddfe-128">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="0ddfe-129">Árfolyamok</span><span class="sxs-lookup"><span data-stu-id="0ddfe-129">Exchange rates</span></span>
| <span data-ttu-id="0ddfe-130">Kezdő pénznem</span><span class="sxs-lookup"><span data-stu-id="0ddfe-130">From currency</span></span> | <span data-ttu-id="0ddfe-131">Célpénznem</span><span class="sxs-lookup"><span data-stu-id="0ddfe-131">To currency</span></span> | <span data-ttu-id="0ddfe-132">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="0ddfe-132">Start date</span></span> | <span data-ttu-id="0ddfe-133">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="0ddfe-133">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="0ddfe-134">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-134">EUR</span></span>           | <span data-ttu-id="0ddfe-135">dollár</span><span class="sxs-lookup"><span data-stu-id="0ddfe-135">USD</span></span>         | <span data-ttu-id="0ddfe-136">2015/1/10</span><span class="sxs-lookup"><span data-stu-id="0ddfe-136">10/1/2015</span></span>  | <span data-ttu-id="0ddfe-137">200</span><span class="sxs-lookup"><span data-stu-id="0ddfe-137">200</span></span>           |
| <span data-ttu-id="0ddfe-138">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-138">EUR</span></span>           | <span data-ttu-id="0ddfe-139">dollár</span><span class="sxs-lookup"><span data-stu-id="0ddfe-139">USD</span></span>         | <span data-ttu-id="0ddfe-140">2015/1/11</span><span class="sxs-lookup"><span data-stu-id="0ddfe-140">11/1/2015</span></span>  | <span data-ttu-id="0ddfe-141">150</span><span class="sxs-lookup"><span data-stu-id="0ddfe-141">150</span></span>           |
| <span data-ttu-id="0ddfe-142">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-142">EUR</span></span>           | <span data-ttu-id="0ddfe-143">dollár</span><span class="sxs-lookup"><span data-stu-id="0ddfe-143">USD</span></span>         | <span data-ttu-id="0ddfe-144">2012/1/12</span><span class="sxs-lookup"><span data-stu-id="0ddfe-144">12/1/2012</span></span>  | <span data-ttu-id="0ddfe-145">100</span><span class="sxs-lookup"><span data-stu-id="0ddfe-145">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="0ddfe-146">2015 októberében a konszolidáció végrehajtása megtörténik</span><span class="sxs-lookup"><span data-stu-id="0ddfe-146">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="0ddfe-147">Egyenlegek a konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="0ddfe-147">Balances in the consolidation company</span></span>

| <span data-ttu-id="0ddfe-148">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="0ddfe-148">Ledger account</span></span> | <span data-ttu-id="0ddfe-149">Pénznem</span><span class="sxs-lookup"><span data-stu-id="0ddfe-149">Currency</span></span> | <span data-ttu-id="0ddfe-150">Összeg</span><span class="sxs-lookup"><span data-stu-id="0ddfe-150">Amount</span></span> | <span data-ttu-id="0ddfe-151">Számítás</span><span class="sxs-lookup"><span data-stu-id="0ddfe-151">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="0ddfe-152">110110</span><span class="sxs-lookup"><span data-stu-id="0ddfe-152">110110</span></span>         | <span data-ttu-id="0ddfe-153">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-153">EUR</span></span>      | <span data-ttu-id="0ddfe-154">250</span><span class="sxs-lookup"><span data-stu-id="0ddfe-154">250</span></span>    | <span data-ttu-id="0ddfe-155">500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="0ddfe-155">500 USD × 50%</span></span>  |
| <span data-ttu-id="0ddfe-156">130100</span><span class="sxs-lookup"><span data-stu-id="0ddfe-156">130100</span></span>         | <span data-ttu-id="0ddfe-157">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-157">EUR</span></span>      | <span data-ttu-id="0ddfe-158">-250</span><span class="sxs-lookup"><span data-stu-id="0ddfe-158">-250</span></span>   | <span data-ttu-id="0ddfe-159">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="0ddfe-159">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="0ddfe-160">Devizaátértékelés végrehajtása 2015. október 1. és 2015. november 30. közötti számlákra</span><span class="sxs-lookup"><span data-stu-id="0ddfe-160">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="0ddfe-161">Egyenlegek a konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="0ddfe-161">Balances in the consolidation company</span></span>

| <span data-ttu-id="0ddfe-162">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="0ddfe-162">Ledger account</span></span> | <span data-ttu-id="0ddfe-163">Pénznem</span><span class="sxs-lookup"><span data-stu-id="0ddfe-163">Currency</span></span> | <span data-ttu-id="0ddfe-164">Összeg</span><span class="sxs-lookup"><span data-stu-id="0ddfe-164">Amount</span></span>  | <span data-ttu-id="0ddfe-165">Számítás</span><span class="sxs-lookup"><span data-stu-id="0ddfe-165">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="0ddfe-166">110110</span><span class="sxs-lookup"><span data-stu-id="0ddfe-166">110110</span></span>         | <span data-ttu-id="0ddfe-167">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-167">EUR</span></span>      | <span data-ttu-id="0ddfe-168">333,33</span><span class="sxs-lookup"><span data-stu-id="0ddfe-168">333.33</span></span>  | <span data-ttu-id="0ddfe-169">Eredeti összeg 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="0ddfe-169">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="0ddfe-170">130100</span><span class="sxs-lookup"><span data-stu-id="0ddfe-170">130100</span></span>         | <span data-ttu-id="0ddfe-171">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-171">EUR</span></span>      | <span data-ttu-id="0ddfe-172">-333,33</span><span class="sxs-lookup"><span data-stu-id="0ddfe-172">-333.33</span></span> | <span data-ttu-id="0ddfe-173">Eredeti összeg -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="0ddfe-173">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="0ddfe-174">801400</span><span class="sxs-lookup"><span data-stu-id="0ddfe-174">801400</span></span>         | <span data-ttu-id="0ddfe-175">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-175">EUR</span></span>      | <span data-ttu-id="0ddfe-176">83,33</span><span class="sxs-lookup"><span data-stu-id="0ddfe-176">83.33</span></span>   | <span data-ttu-id="0ddfe-177">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="0ddfe-177">333.33 – 250</span></span>                       |
| <span data-ttu-id="0ddfe-178">801600</span><span class="sxs-lookup"><span data-stu-id="0ddfe-178">801600</span></span>         | <span data-ttu-id="0ddfe-179">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-179">EUR</span></span>      | <span data-ttu-id="0ddfe-180">-83,33</span><span class="sxs-lookup"><span data-stu-id="0ddfe-180">-83.33</span></span>  | <span data-ttu-id="0ddfe-181">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="0ddfe-181">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="0ddfe-182">A jelentési pénznem összegeihez további tranzakciók történnek.</span><span class="sxs-lookup"><span data-stu-id="0ddfe-182">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="0ddfe-183">Devizaátértékelés végrehajtása 2015. október 1. és 2015. december 31. közötti számlákra</span><span class="sxs-lookup"><span data-stu-id="0ddfe-183">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="0ddfe-184">Egyenlegek a konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="0ddfe-184">Balances in the consolidation company</span></span>

| <span data-ttu-id="0ddfe-185">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="0ddfe-185">Ledger account</span></span> | <span data-ttu-id="0ddfe-186">Pénznem</span><span class="sxs-lookup"><span data-stu-id="0ddfe-186">Currency</span></span> | <span data-ttu-id="0ddfe-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="0ddfe-187">Amount</span></span>  | <span data-ttu-id="0ddfe-188">Számítás</span><span class="sxs-lookup"><span data-stu-id="0ddfe-188">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="0ddfe-189">110110</span><span class="sxs-lookup"><span data-stu-id="0ddfe-189">110110</span></span>         | <span data-ttu-id="0ddfe-190">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-190">EUR</span></span>      | <span data-ttu-id="0ddfe-191">500,00</span><span class="sxs-lookup"><span data-stu-id="0ddfe-191">500.00</span></span>  | <span data-ttu-id="0ddfe-192">Eredeti összeg 500 × 1</span><span class="sxs-lookup"><span data-stu-id="0ddfe-192">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="0ddfe-193">130100</span><span class="sxs-lookup"><span data-stu-id="0ddfe-193">130100</span></span>         | <span data-ttu-id="0ddfe-194">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-194">EUR</span></span>      | <span data-ttu-id="0ddfe-195">-500,00</span><span class="sxs-lookup"><span data-stu-id="0ddfe-195">-500.00</span></span> | <span data-ttu-id="0ddfe-196">Eredeti összeg -500 × 1</span><span class="sxs-lookup"><span data-stu-id="0ddfe-196">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="0ddfe-197">801400</span><span class="sxs-lookup"><span data-stu-id="0ddfe-197">801400</span></span>         | <span data-ttu-id="0ddfe-198">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-198">EUR</span></span>      | <span data-ttu-id="0ddfe-199">250</span><span class="sxs-lookup"><span data-stu-id="0ddfe-199">250</span></span>     | <span data-ttu-id="0ddfe-200">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="0ddfe-200">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="0ddfe-201">801600</span><span class="sxs-lookup"><span data-stu-id="0ddfe-201">801600</span></span>         | <span data-ttu-id="0ddfe-202">HUF</span><span class="sxs-lookup"><span data-stu-id="0ddfe-202">EUR</span></span>      | <span data-ttu-id="0ddfe-203">-250</span><span class="sxs-lookup"><span data-stu-id="0ddfe-203">-250</span></span>    | <span data-ttu-id="0ddfe-204">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="0ddfe-204">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |






