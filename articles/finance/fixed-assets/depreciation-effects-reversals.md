---
title: A sztornírozások értékcsökkenésre gyakorolt hatására
description: Ez a cikk egy tárgyieszköz-tranzakció sztornírozásának lehetséges következményeit tárgyalja.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6973cf3f4189347e0403d3d29014a23afb03836c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826954"
---
# <a name="depreciation-effects-with-reversals"></a><span data-ttu-id="daab9-103">A sztornírozások értékcsökkenésre gyakorolt hatására</span><span class="sxs-lookup"><span data-stu-id="daab9-103">Depreciation effects with reversals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="daab9-104">Ez a cikk egy tárgyieszköz-tranzakció sztornírozásának lehetséges következményeit tárgyalja.</span><span class="sxs-lookup"><span data-stu-id="daab9-104">This article discusses potential implications of reversing a fixed asset transaction.</span></span> 

<span data-ttu-id="daab9-105">Sztornírozhatja a tárgyieszköz-tranzakciókat és a azokat a tranzakciókat, amelyek egy tárgyi eszközhöz vannak társítva.</span><span class="sxs-lookup"><span data-stu-id="daab9-105">You can reverse fixed asset transactions, and the transactions that are associated with a fixed asset.</span></span> <span data-ttu-id="daab9-106">Továbbá visszavonhatja a sztornírozott tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="daab9-106">You can also revoke a reversed transaction.</span></span> 

<span data-ttu-id="daab9-107">Sztornírozhat vagy visszavonhat egy tranzakciót, amely nem a legutóbbi feladott tranzakció a könyvben az eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="daab9-107">You can reverse or revoke a transaction that was not the most recent transaction posted to the book for the asset.</span></span> <span data-ttu-id="daab9-108">Előbb érdemes megállapítania, hogy lett-e értékcsökkenési tranzakció feladva az után a tranzakció után, amelyet sztorníroz.</span><span class="sxs-lookup"><span data-stu-id="daab9-108">You should first determine whether any depreciation transactions were posted after the transaction that you are reversing.</span></span> <span data-ttu-id="daab9-109">Ennek oka az, hogy az értékcsökkenés nem kerül kiszámításra amikor sztorníroz egy tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="daab9-109">This is because depreciation is not recalculated when you reverse a transaction.</span></span> <span data-ttu-id="daab9-110">Ezért értékcsökkenés gyakran túl nagy vagy túl alacsony, a sztornírozás után, ahogy azt a példák mutatják.</span><span class="sxs-lookup"><span data-stu-id="daab9-110">Therefore, depreciation often is overstated or understated after the reversal, as shown in the examples.</span></span> 

<span data-ttu-id="daab9-111">Hogy megbizonyosodjon, hogy az értékcsökkenés helyes, amikor sztorníroz egy tranzakciót ne folytassa a sztornírozást, ha egy olyan üzenetet kap, amelyben az áll, hogy a sztornírozás nem lesz újraszámolva.</span><span class="sxs-lookup"><span data-stu-id="daab9-111">To make sure that depreciation is correct when you reverse a transaction, do not continue with the reversal if you receive a message that states that depreciation will not be recalculated.</span></span> <span data-ttu-id="daab9-112">Ehelyett előbb sztornírozza az értékcsökkenési tranzakciót, amit az után a tranzakció után adtak föl, amit épp sztornírozni próbált, majd folytassa a sztornírozást.</span><span class="sxs-lookup"><span data-stu-id="daab9-112">Instead, first reverse the depreciation transaction that was posted after the transaction you tried to reverse, and then continue with the reversal.</span></span> <span data-ttu-id="daab9-113">Nem lesz figyelmeztetve az értékcsökkenés újraszámításáról és folytathatja a sztornírozást.</span><span class="sxs-lookup"><span data-stu-id="daab9-113">You will not be warned about depreciation recalculations, and you can continue with the reversal.</span></span> 

<span data-ttu-id="daab9-114">A következő példák bemutatják a számításokat, amelyek akkor történnek, ha folytatja a sztornírozást az üzenet után mielőtt sztornírozta volna a korábbi értékcsökkenési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="daab9-114">The following examples show the calculations that occur if you continue beyond the message without first reversing the depreciation transactions.</span></span>

## <a name="example-1-depreciation-is-overstated"></a><span data-ttu-id="daab9-115"> 1. példa: túl nagy értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="daab9-115">Example 1: Depreciation is overstated</span></span>
<span data-ttu-id="daab9-116">Az eszköznek 5 év hasznos élettartam és lineáris értékcsökkenés (60 értékcsökkenési időszak) van beállítva.</span><span class="sxs-lookup"><span data-stu-id="daab9-116">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="daab9-117">Ebben a példában túl nagy az értékcsökkenés.</span><span class="sxs-lookup"><span data-stu-id="daab9-117">In this example, depreciation is overstated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="daab9-118">Tárgyieszköz-tranzakciók előzményei</span><span class="sxs-lookup"><span data-stu-id="daab9-118">Asset transaction history</span></span>

| <span data-ttu-id="daab9-119">Dátum</span><span class="sxs-lookup"><span data-stu-id="daab9-119">Date</span></span>       | <span data-ttu-id="daab9-120">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="daab9-120">Transaction type</span></span>                                                          | <span data-ttu-id="daab9-121">Összeg</span><span class="sxs-lookup"><span data-stu-id="daab9-121">Amount</span></span>                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| <span data-ttu-id="daab9-122">Január 1.</span><span class="sxs-lookup"><span data-stu-id="daab9-122">January 1</span></span>  | <span data-ttu-id="daab9-123">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="daab9-123">Acquisition</span></span>                                                               | <span data-ttu-id="daab9-124">59 000,00</span><span class="sxs-lookup"><span data-stu-id="daab9-124">59,000.00</span></span>                                 |
| <span data-ttu-id="daab9-125">Január 1.</span><span class="sxs-lookup"><span data-stu-id="daab9-125">January 1</span></span>  | <span data-ttu-id="daab9-126">Beszerzés helyesbítése</span><span class="sxs-lookup"><span data-stu-id="daab9-126">Acquisition adjustment</span></span>                                                    | <span data-ttu-id="daab9-127">1000,00</span><span class="sxs-lookup"><span data-stu-id="daab9-127">1,000.00</span></span>                                  |
| <span data-ttu-id="daab9-128">Január 31.</span><span class="sxs-lookup"><span data-stu-id="daab9-128">January 31</span></span> | <span data-ttu-id="daab9-129">Értékcsökkenés (az értékcsökkenés egy időszakának javaslatával létrehozva)</span><span class="sxs-lookup"><span data-stu-id="daab9-129">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="daab9-130">1 000,00 Számítás: Könyv szerinti érték (59 000 + 1 000) / Hátra lévő értékcsökkenési időszakok száma (60)</span><span class="sxs-lookup"><span data-stu-id="daab9-130">1,000.00Calculation: Book value (59,000 + 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="daab9-131">Sztornírozási művelet</span><span class="sxs-lookup"><span data-stu-id="daab9-131">Reversal action</span></span>

| <span data-ttu-id="daab9-132">Dátum</span><span class="sxs-lookup"><span data-stu-id="daab9-132">Date</span></span>      | <span data-ttu-id="daab9-133">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="daab9-133">Transaction type</span></span>                | <span data-ttu-id="daab9-134">Összeg</span><span class="sxs-lookup"><span data-stu-id="daab9-134">Amount</span></span>    |
|-----------|---------------------------------|-----------|
| <span data-ttu-id="daab9-135">Január 1.</span><span class="sxs-lookup"><span data-stu-id="daab9-135">January 1</span></span> | <span data-ttu-id="daab9-136">Beszerzés-helyesbítési sztornírozás</span><span class="sxs-lookup"><span data-stu-id="daab9-136">Acquisition adjustment reversal</span></span> | <span data-ttu-id="daab9-137">–1000,00</span><span class="sxs-lookup"><span data-stu-id="daab9-137">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="daab9-138">Az értékcsökkenés hatása</span><span class="sxs-lookup"><span data-stu-id="daab9-138">Depreciation effect</span></span>

| <span data-ttu-id="daab9-139">Dátum</span><span class="sxs-lookup"><span data-stu-id="daab9-139">Date</span></span>        | <span data-ttu-id="daab9-140">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="daab9-140">Transaction type</span></span>        | <span data-ttu-id="daab9-141">Összeg</span><span class="sxs-lookup"><span data-stu-id="daab9-141">Amount</span></span>                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| <span data-ttu-id="daab9-142">Február 28.</span><span class="sxs-lookup"><span data-stu-id="daab9-142">February 28</span></span> | <span data-ttu-id="daab9-143">Értékcsökkenés (javaslat)</span><span class="sxs-lookup"><span data-stu-id="daab9-143">Depreciation (proposal)</span></span> | <span data-ttu-id="daab9-144">983,05 Számítás: Könyv szerinti érték (59 000 - 1 000 értékcsökkenés) / Hátralévő értékcsökkenési időszakok száma (59)</span><span class="sxs-lookup"><span data-stu-id="daab9-144">983.05Calculation: Book value (59,000 - 1,000 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="daab9-145">Az értékcsökkenés túl nagy, mértéke 16,95 (1000 - 983,05).</span><span class="sxs-lookup"><span data-stu-id="daab9-145">Depreciation is overstated by 16.95 (1,000 - 983.05).</span></span>

## <a name="example-2-depreciation-is-understated"></a><span data-ttu-id="daab9-146"> 2. példa: túl alacsony értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="daab9-146">Example 2: Depreciation is understated</span></span>
<span data-ttu-id="daab9-147">Az eszköznek 5 év hasznos élettartam és lineáris értékcsökkenés (60 értékcsökkenési időszak) van beállítva.</span><span class="sxs-lookup"><span data-stu-id="daab9-147">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="daab9-148">Ebben a példában túl alacsony az értékcsökkenés.</span><span class="sxs-lookup"><span data-stu-id="daab9-148">In this example, depreciation is understated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="daab9-149">Tárgyieszköz-tranzakciók előzményei</span><span class="sxs-lookup"><span data-stu-id="daab9-149">Asset transaction history</span></span>

| <span data-ttu-id="daab9-150">Dátum</span><span class="sxs-lookup"><span data-stu-id="daab9-150">Date</span></span>       | <span data-ttu-id="daab9-151">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="daab9-151">Transaction type</span></span>                                                          | <span data-ttu-id="daab9-152">Összeg</span><span class="sxs-lookup"><span data-stu-id="daab9-152">Amount</span></span>                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="daab9-153">Január 1.</span><span class="sxs-lookup"><span data-stu-id="daab9-153">January 1</span></span>  | <span data-ttu-id="daab9-154">Beszerzés</span><span class="sxs-lookup"><span data-stu-id="daab9-154">Acquisition</span></span>                                                               | <span data-ttu-id="daab9-155">59 000,00</span><span class="sxs-lookup"><span data-stu-id="daab9-155">59,000.00</span></span>                                   |
| <span data-ttu-id="daab9-156">Január 1.</span><span class="sxs-lookup"><span data-stu-id="daab9-156">January 1</span></span>  | <span data-ttu-id="daab9-157">Leértékelési helyesbítés</span><span class="sxs-lookup"><span data-stu-id="daab9-157">Write-down adjustment</span></span>                                                     | <span data-ttu-id="daab9-158">1000,00</span><span class="sxs-lookup"><span data-stu-id="daab9-158">1,000.00</span></span>                                    |
| <span data-ttu-id="daab9-159">Január 31.</span><span class="sxs-lookup"><span data-stu-id="daab9-159">January 31</span></span> | <span data-ttu-id="daab9-160">Értékcsökkenés (az értékcsökkenés egy időszakának javaslatával létrehozva)</span><span class="sxs-lookup"><span data-stu-id="daab9-160">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="daab9-161">966,67 Számítás: könyv szerinti érték (59 000 - 1 000) / Hátralévő értékcsökkenési időszakok száma (60)</span><span class="sxs-lookup"><span data-stu-id="daab9-161">966.67Calculation: Book value (59,000 - 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="daab9-162">Sztornírozási művelet</span><span class="sxs-lookup"><span data-stu-id="daab9-162">Reversal action</span></span>

| <span data-ttu-id="daab9-163">Dátum</span><span class="sxs-lookup"><span data-stu-id="daab9-163">Date</span></span>      | <span data-ttu-id="daab9-164">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="daab9-164">Transaction type</span></span>               | <span data-ttu-id="daab9-165">Összeg</span><span class="sxs-lookup"><span data-stu-id="daab9-165">Amount</span></span>    |
|-----------|--------------------------------|-----------|
| <span data-ttu-id="daab9-166">Január 1.</span><span class="sxs-lookup"><span data-stu-id="daab9-166">January 1</span></span> | <span data-ttu-id="daab9-167">Leértékelési helyesbítés sztornírozás</span><span class="sxs-lookup"><span data-stu-id="daab9-167">Write-down adjustment reversal</span></span> | <span data-ttu-id="daab9-168">–1000,00</span><span class="sxs-lookup"><span data-stu-id="daab9-168">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="daab9-169">Az értékcsökkenés hatása</span><span class="sxs-lookup"><span data-stu-id="daab9-169">Depreciation effect</span></span>

| <span data-ttu-id="daab9-170">Dátum</span><span class="sxs-lookup"><span data-stu-id="daab9-170">Date</span></span>        | <span data-ttu-id="daab9-171">Tranzakció típusa</span><span class="sxs-lookup"><span data-stu-id="daab9-171">Transaction type</span></span>        | <span data-ttu-id="daab9-172">Összeg</span><span class="sxs-lookup"><span data-stu-id="daab9-172">Amount</span></span>                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| <span data-ttu-id="daab9-173">Február 28.</span><span class="sxs-lookup"><span data-stu-id="daab9-173">February 28</span></span> | <span data-ttu-id="daab9-174">Értékcsökkenés (javaslat)</span><span class="sxs-lookup"><span data-stu-id="daab9-174">Depreciation (proposal)</span></span> | <span data-ttu-id="daab9-175">983,62 Számítás: könyv szerinti érték (59 000 - 966,67 értékcsökkenés) / Hátralévő értékcsökkenési időszakok száma (59)</span><span class="sxs-lookup"><span data-stu-id="daab9-175">983.62Calculation: Book value (59,000 - 966.67 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="daab9-176">Az értékcsökkenés túl alacsony, mértéke 16,95 (983,62 - 966,67).</span><span class="sxs-lookup"><span data-stu-id="daab9-176">Depreciation is understated by 16.95 (983.62 - 966.67).</span></span>



<a name="additional-resources"></a><span data-ttu-id="daab9-177">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="daab9-177">Additional resources</span></span>
--------

[<span data-ttu-id="daab9-178">Tárgyi eszközök értékcsökkenése</span><span class="sxs-lookup"><span data-stu-id="daab9-178">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]