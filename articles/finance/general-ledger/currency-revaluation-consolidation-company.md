---
title: Devizaátértékelés konszolidált vállalatban
description: Ez a témakör azt ismerteti, hogyan lehet átértékelni a devizát a konszolidált vállalatban.
author: roschlom
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerExchAdjHist
audience: Application User
ms.reviewer: roschlom
ms.custom: 62183
ms.assetid: 2762baaf-0c10-4ff7-8713-c506d6c29b98
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 81de31ee75b4be38256505bc7b875dc15473c75a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212229"
---
# <a name="currency-revaluation-in-a-consolidation-company"></a><span data-ttu-id="419f7-103">Devizaátértékelés konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="419f7-103">Currency revaluation in a consolidation company</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="419f7-104">Ha egy könyvelési pénznemből egy másikba konszolidál adatokat és változik az árfolyam, devizaátértékelést kell futtatnia, hogy a számlaegyenlegek átértékelése megfelelően történjen.</span><span class="sxs-lookup"><span data-stu-id="419f7-104">When you consolidate data from one accounting currency to another, you must still run currency revaluation if there is a change in exchange rates, so that your account balances  are correctly revalued.</span></span> <span data-ttu-id="419f7-105">Az adatok eredeti konszolidációja során használja a **Devizaátváltás** lapot, ahol kiválaszthatja a kezdeti árfolyamot a konszolidációs folyamat kezdeti átváltásához.</span><span class="sxs-lookup"><span data-stu-id="419f7-105">When you originally consolidate the data, use the **Currency translation** tab to select the initial exchange rates to for translation during the consolidation process.</span></span> <span data-ttu-id="419f7-106">Ha új árfolyamot ad meg (például következő hónapban), át kell értékelnie a számlaegyenlegeket.</span><span class="sxs-lookup"><span data-stu-id="419f7-106">After a new exchange rate is entered (for example, in the next month), you must revalue the account balances.</span></span> <span data-ttu-id="419f7-107">A nem realizált nyereség vagy nem realizált veszteség ezután az új árfolyamnak és dátumnak megfelelően frissül.</span><span class="sxs-lookup"><span data-stu-id="419f7-107">The unrealized gains or losses are then updated accordingly, based on the new exchange rate and date.</span></span> <span data-ttu-id="419f7-108">Az alábbi példa a könyvelés bejegyzéseket mutatja be, amelyek egy ilyen folyamat során létrejönnek.</span><span class="sxs-lookup"><span data-stu-id="419f7-108">The following example illustrates the accounting entries that are created during the process.</span></span>

## <a name="company-setup"></a><span data-ttu-id="419f7-109">Vállalat beállítása</span><span class="sxs-lookup"><span data-stu-id="419f7-109">Company setup</span></span>
-   <span data-ttu-id="419f7-110">**Forrás/működő vállalat (USMF)** – USA-dollárban (USD) van megadva a könyvelési és a jelentési pénznem.</span><span class="sxs-lookup"><span data-stu-id="419f7-110">**Source/operating company (USMF)** – US dollars (USD) are used as the accounting and reporting currency.</span></span>
-   <span data-ttu-id="419f7-111">**Konszolidált vállalat (CON)** – Euróban (EUR) van megadva a könyvelési és a jelentési pénznem.</span><span class="sxs-lookup"><span data-stu-id="419f7-111">**Consolidated company (CON)** – Euros (EUR) are used as the accounting and reporting currency.</span></span>
    -   <span data-ttu-id="419f7-112">**Realizált nyereség**– 801500 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="419f7-112">**Realized gain**– Ledger account 801500</span></span>
    -   <span data-ttu-id="419f7-113">**Realizált veszteség**– 801600 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="419f7-113">**Realized loss** – Ledger account 801600</span></span>
    -   <span data-ttu-id="419f7-114">**Nem realizált nyereség**– 801600 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="419f7-114">**Unrealized gain** – Ledger account 801600</span></span>
    -   <span data-ttu-id="419f7-115">**Nem realizált veszteség**– 801400 főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="419f7-115">**Unrealized loss** – Ledger account 801400</span></span>

## <a name="original-transactions"></a><span data-ttu-id="419f7-116">Eredeti tranzakciók</span><span class="sxs-lookup"><span data-stu-id="419f7-116">Original transactions</span></span>
### <a name="cash-receipt-transactions-in-usmf"></a><span data-ttu-id="419f7-117">Készpénz-befizetési utalvány tranzakciói USMF-ben</span><span class="sxs-lookup"><span data-stu-id="419f7-117">Cash receipt transactions in USMF</span></span>

| <span data-ttu-id="419f7-118">Dátum</span><span class="sxs-lookup"><span data-stu-id="419f7-118">Date</span></span>       | <span data-ttu-id="419f7-119">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="419f7-119">Ledger account</span></span>               | <span data-ttu-id="419f7-120">Pénznem</span><span class="sxs-lookup"><span data-stu-id="419f7-120">Currency</span></span> | <span data-ttu-id="419f7-121">Összeg</span><span class="sxs-lookup"><span data-stu-id="419f7-121">Amount</span></span> |
|------------|------------------------------|----------|--------|
| <span data-ttu-id="419f7-122">2015/11/10</span><span class="sxs-lookup"><span data-stu-id="419f7-122">10/11/2015</span></span> | <span data-ttu-id="419f7-123">110110 – készpénz</span><span class="sxs-lookup"><span data-stu-id="419f7-123">110110 – Cash</span></span>                | <span data-ttu-id="419f7-124">dollár</span><span class="sxs-lookup"><span data-stu-id="419f7-124">USD</span></span>      | <span data-ttu-id="419f7-125">500</span><span class="sxs-lookup"><span data-stu-id="419f7-125">500</span></span>    |
| <span data-ttu-id="419f7-126">2015/11/10</span><span class="sxs-lookup"><span data-stu-id="419f7-126">10/11/2015</span></span> | <span data-ttu-id="419f7-127">130100 – kinnlevőségek</span><span class="sxs-lookup"><span data-stu-id="419f7-127">130100 – Accounts Receivable</span></span> | <span data-ttu-id="419f7-128">dollár</span><span class="sxs-lookup"><span data-stu-id="419f7-128">USD</span></span>      | <span data-ttu-id="419f7-129">-500</span><span class="sxs-lookup"><span data-stu-id="419f7-129">-500</span></span>   |

## <a name="exchange-rates"></a><span data-ttu-id="419f7-130">Árfolyamok</span><span class="sxs-lookup"><span data-stu-id="419f7-130">Exchange rates</span></span>

| <span data-ttu-id="419f7-131">Kezdő pénznem</span><span class="sxs-lookup"><span data-stu-id="419f7-131">From currency</span></span> | <span data-ttu-id="419f7-132">Célpénznem</span><span class="sxs-lookup"><span data-stu-id="419f7-132">To currency</span></span> | <span data-ttu-id="419f7-133">Kezdő dátum</span><span class="sxs-lookup"><span data-stu-id="419f7-133">Start date</span></span> | <span data-ttu-id="419f7-134">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="419f7-134">Exchange rate</span></span> |
|---------------|-------------|------------|---------------|
| <span data-ttu-id="419f7-135">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-135">EUR</span></span>           | <span data-ttu-id="419f7-136">dollár</span><span class="sxs-lookup"><span data-stu-id="419f7-136">USD</span></span>         | <span data-ttu-id="419f7-137">2015/1/10</span><span class="sxs-lookup"><span data-stu-id="419f7-137">10/1/2015</span></span>  | <span data-ttu-id="419f7-138">200</span><span class="sxs-lookup"><span data-stu-id="419f7-138">200</span></span>           |
| <span data-ttu-id="419f7-139">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-139">EUR</span></span>           | <span data-ttu-id="419f7-140">dollár</span><span class="sxs-lookup"><span data-stu-id="419f7-140">USD</span></span>         | <span data-ttu-id="419f7-141">2015/1/11</span><span class="sxs-lookup"><span data-stu-id="419f7-141">11/1/2015</span></span>  | <span data-ttu-id="419f7-142">150</span><span class="sxs-lookup"><span data-stu-id="419f7-142">150</span></span>           |
| <span data-ttu-id="419f7-143">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-143">EUR</span></span>           | <span data-ttu-id="419f7-144">dollár</span><span class="sxs-lookup"><span data-stu-id="419f7-144">USD</span></span>         | <span data-ttu-id="419f7-145">2012/1/12</span><span class="sxs-lookup"><span data-stu-id="419f7-145">12/1/2012</span></span>  | <span data-ttu-id="419f7-146">100</span><span class="sxs-lookup"><span data-stu-id="419f7-146">100</span></span>           |

## <a name="perform-the-consolidation-for-october-2015"></a><span data-ttu-id="419f7-147">2015 októberében a konszolidáció végrehajtása megtörténik</span><span class="sxs-lookup"><span data-stu-id="419f7-147">Perform the consolidation for October 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="419f7-148">Egyenlegek a konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="419f7-148">Balances in the consolidation company</span></span>

| <span data-ttu-id="419f7-149">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="419f7-149">Ledger account</span></span> | <span data-ttu-id="419f7-150">Pénznem</span><span class="sxs-lookup"><span data-stu-id="419f7-150">Currency</span></span> | <span data-ttu-id="419f7-151">Összeg</span><span class="sxs-lookup"><span data-stu-id="419f7-151">Amount</span></span> | <span data-ttu-id="419f7-152">Számítás</span><span class="sxs-lookup"><span data-stu-id="419f7-152">Calculation</span></span>    |
|----------------|----------|--------|----------------|
| <span data-ttu-id="419f7-153">110110</span><span class="sxs-lookup"><span data-stu-id="419f7-153">110110</span></span>         | <span data-ttu-id="419f7-154">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-154">EUR</span></span>      | <span data-ttu-id="419f7-155">250</span><span class="sxs-lookup"><span data-stu-id="419f7-155">250</span></span>    | <span data-ttu-id="419f7-156">500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="419f7-156">500 USD × 50%</span></span>  |
| <span data-ttu-id="419f7-157">130100</span><span class="sxs-lookup"><span data-stu-id="419f7-157">130100</span></span>         | <span data-ttu-id="419f7-158">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-158">EUR</span></span>      | <span data-ttu-id="419f7-159">-250</span><span class="sxs-lookup"><span data-stu-id="419f7-159">-250</span></span>   | <span data-ttu-id="419f7-160">-500 USD × 50%</span><span class="sxs-lookup"><span data-stu-id="419f7-160">-500 USD × 50%</span></span> |

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-november-30-2015"></a><span data-ttu-id="419f7-161">Devizaátértékelés végrehajtása 2015. október 1. és 2015. november 30. közötti számlákra</span><span class="sxs-lookup"><span data-stu-id="419f7-161">Perform currency revaluation for the accounts from October 1, 2015, through November 30, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="419f7-162">Egyenlegek a konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="419f7-162">Balances in the consolidation company</span></span>

| <span data-ttu-id="419f7-163">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="419f7-163">Ledger account</span></span> | <span data-ttu-id="419f7-164">Pénznem</span><span class="sxs-lookup"><span data-stu-id="419f7-164">Currency</span></span> | <span data-ttu-id="419f7-165">Összeg</span><span class="sxs-lookup"><span data-stu-id="419f7-165">Amount</span></span>  | <span data-ttu-id="419f7-166">Számítás</span><span class="sxs-lookup"><span data-stu-id="419f7-166">Calculation</span></span>                        |
|----------------|----------|---------|------------------------------------|
| <span data-ttu-id="419f7-167">110110</span><span class="sxs-lookup"><span data-stu-id="419f7-167">110110</span></span>         | <span data-ttu-id="419f7-168">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-168">EUR</span></span>      | <span data-ttu-id="419f7-169">333,33</span><span class="sxs-lookup"><span data-stu-id="419f7-169">333.33</span></span>  | <span data-ttu-id="419f7-170">Eredeti összeg 500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="419f7-170">Original amount of 500 × 66.6667%</span></span>  |
| <span data-ttu-id="419f7-171">130100</span><span class="sxs-lookup"><span data-stu-id="419f7-171">130100</span></span>         | <span data-ttu-id="419f7-172">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-172">EUR</span></span>      | <span data-ttu-id="419f7-173">-333,33</span><span class="sxs-lookup"><span data-stu-id="419f7-173">-333.33</span></span> | <span data-ttu-id="419f7-174">Eredeti összeg -500 × 66,6667%</span><span class="sxs-lookup"><span data-stu-id="419f7-174">Original amount of -500 × 66.6667%</span></span> |
| <span data-ttu-id="419f7-175">801400</span><span class="sxs-lookup"><span data-stu-id="419f7-175">801400</span></span>         | <span data-ttu-id="419f7-176">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-176">EUR</span></span>      | <span data-ttu-id="419f7-177">83,33</span><span class="sxs-lookup"><span data-stu-id="419f7-177">83.33</span></span>   | <span data-ttu-id="419f7-178">333,33 – 250</span><span class="sxs-lookup"><span data-stu-id="419f7-178">333.33 – 250</span></span>                       |
| <span data-ttu-id="419f7-179">801600</span><span class="sxs-lookup"><span data-stu-id="419f7-179">801600</span></span>         | <span data-ttu-id="419f7-180">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-180">EUR</span></span>      | <span data-ttu-id="419f7-181">-83,33</span><span class="sxs-lookup"><span data-stu-id="419f7-181">-83.33</span></span>  | <span data-ttu-id="419f7-182">-333,33 – (-250)</span><span class="sxs-lookup"><span data-stu-id="419f7-182">-333.33 – (-250)</span></span>                   |

<span data-ttu-id="419f7-183">A jelentési pénznem összegeihez további tranzakciók történnek.</span><span class="sxs-lookup"><span data-stu-id="419f7-183">You will see additional transactions for the reporting currency amounts.</span></span>

## <a name="perform-currency-revaluation-for-the-accounts-from-october-1-2015-through-december-31-2015"></a><span data-ttu-id="419f7-184">Devizaátértékelés végrehajtása 2015. október 1. és 2015. december 31. közötti számlákra</span><span class="sxs-lookup"><span data-stu-id="419f7-184">Perform currency revaluation for the accounts from October 1, 2015, through December 31, 2015</span></span>
### <a name="balances-in-the-consolidation-company"></a><span data-ttu-id="419f7-185">Egyenlegek a konszolidált vállalatban</span><span class="sxs-lookup"><span data-stu-id="419f7-185">Balances in the consolidation company</span></span>

| <span data-ttu-id="419f7-186">Főkönyvi számla</span><span class="sxs-lookup"><span data-stu-id="419f7-186">Ledger account</span></span> | <span data-ttu-id="419f7-187">Pénznem</span><span class="sxs-lookup"><span data-stu-id="419f7-187">Currency</span></span> | <span data-ttu-id="419f7-188">Összeg</span><span class="sxs-lookup"><span data-stu-id="419f7-188">Amount</span></span>  | <span data-ttu-id="419f7-189">Számítás</span><span class="sxs-lookup"><span data-stu-id="419f7-189">Calculation</span></span>                                          |
|----------------|----------|---------|------------------------------------------------------|
| <span data-ttu-id="419f7-190">110110</span><span class="sxs-lookup"><span data-stu-id="419f7-190">110110</span></span>         | <span data-ttu-id="419f7-191">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-191">EUR</span></span>      | <span data-ttu-id="419f7-192">500,00</span><span class="sxs-lookup"><span data-stu-id="419f7-192">500.00</span></span>  | <span data-ttu-id="419f7-193">Eredeti összeg 500 × 1</span><span class="sxs-lookup"><span data-stu-id="419f7-193">Original amount of 500 × 1</span></span>                           |
| <span data-ttu-id="419f7-194">130100</span><span class="sxs-lookup"><span data-stu-id="419f7-194">130100</span></span>         | <span data-ttu-id="419f7-195">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-195">EUR</span></span>      | <span data-ttu-id="419f7-196">-500,00</span><span class="sxs-lookup"><span data-stu-id="419f7-196">-500.00</span></span> | <span data-ttu-id="419f7-197">Eredeti összeg -500 × 1</span><span class="sxs-lookup"><span data-stu-id="419f7-197">Original amount of -500 × 1</span></span>                          |
| <span data-ttu-id="419f7-198">801400</span><span class="sxs-lookup"><span data-stu-id="419f7-198">801400</span></span>         | <span data-ttu-id="419f7-199">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-199">EUR</span></span>      | <span data-ttu-id="419f7-200">250</span><span class="sxs-lookup"><span data-stu-id="419f7-200">250</span></span>     | <span data-ttu-id="419f7-201">500 – 333,33 = 166,67 166,67 + 83,33 = 250</span><span class="sxs-lookup"><span data-stu-id="419f7-201">500 – 333.33 = 166.67 166.67 + 83.33 = 250</span></span>           |
| <span data-ttu-id="419f7-202">801600</span><span class="sxs-lookup"><span data-stu-id="419f7-202">801600</span></span>         | <span data-ttu-id="419f7-203">HUF</span><span class="sxs-lookup"><span data-stu-id="419f7-203">EUR</span></span>      | <span data-ttu-id="419f7-204">-250</span><span class="sxs-lookup"><span data-stu-id="419f7-204">-250</span></span>    | <span data-ttu-id="419f7-205">-500 – (-333,33) = -166,67 -166,67 + (-83,33) = -250</span><span class="sxs-lookup"><span data-stu-id="419f7-205">-500 – (-333.33) = -166.67 -166.67 + (-83.33) = -250</span></span> |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]