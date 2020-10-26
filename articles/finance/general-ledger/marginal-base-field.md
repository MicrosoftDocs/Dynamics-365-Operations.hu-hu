---
title: Áfaérték a Számítás alapja és a Számítási módszerek lapján
description: A témakör leírja, hogy a Számítás alapja mezőben található értékek és a Számítási módszer értékei, hogyan határozzák meg az értékesítési és beszerzési tranzakciók adó(it).
author: ShylaThompson
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8617785ea969f9f4facaccdf81cfaf5344c30839
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975003"
---
# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a><span data-ttu-id="4d8f1-103">Áfaérték a Számítás alapja és a Számítási módszerek lapján</span><span class="sxs-lookup"><span data-stu-id="4d8f1-103">Sales tax rates based on the Marginal base and Calculation methods</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d8f1-104">A témakör leírja, hogy a Számítás alapja mezőben található értékek és a Számítási módszer értékei, hogyan határozzák meg az értékesítési és beszerzési tranzakciók adó(it).</span><span class="sxs-lookup"><span data-stu-id="4d8f1-104">This topic explains how the values in the fields Marginal base and Calculation method determine the tax rate(s) in sales and purchase transactions.</span></span>

<span data-ttu-id="4d8f1-105">A számítás gyorslapon és az áfa kód lapon lévő számítás alapot az határozza meg, hogy melyik összeg használatos a megfelelő adó értékek az áfa kód értékek oldalán lévő értékekből történő kivételéhez.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-105">The Marginal base on the Calculation FastTab on the Sales tax codes page determines which amount is used to pick the appropriate tax rate(s) from the rates in the Sales tax code values page.</span></span> <span data-ttu-id="4d8f1-106">A számítási mód mező módszerével kombinált számítás alapja mezőben lévő a összeg típusa határozza meg, hogy hogyan találja meg a tranzakcióhoz a megfelelő adó értéket.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-106">The amount type in the Marginal base field in combination with the method in the Calculation method field determines the logic to find the correct tax rate(s) for a transaction.</span></span> 

<span data-ttu-id="4d8f1-107">A mezőértékek különféle kombinációi igen különböző áfaszámítási módokra adnak lehetőséget, ahogy az a következő példákban is látható.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-107">Various combinations of values in these fields produce very different sales tax calculations, as shown by the following examples.</span></span> <span data-ttu-id="4d8f1-108">A példák ugyanazokat az áfaintervallum értékek használják, amelyek az áfa kód értékek oldalán állíthatók be minden áfakód esetében.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-108">The examples use the same tax interval values, which are set up for each tax code in the Sales tax codes values page.</span></span> <span data-ttu-id="4d8f1-109">A lap megnyitásához kattintson az Áfakódra &gt; A forgalmi adó kód lap értékeire.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-109">To open this page, click Sales tax code &gt; Values in the Sales tax codes page.</span></span>

> [!Important]                                                                                                                  
> <span data-ttu-id="4d8f1-110">Ha az áfakódok bármelyikének számítási alapja a sor összegétől vagy egységtől függ, akkor aszámítási módszer mezőjének értékét a sorra kell beállítani a főkönyv paramétereinek oldalán.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-110">If the Marginal base on one or more of your sales tax codes is based on line amounts or units, the value of the Calculation method field in the General ledger parameters page must be set to Line.</span></span> |

## <a name="net-amount-per-line"></a><span data-ttu-id="4d8f1-111"> Soronkénti nettó összeg</span><span class="sxs-lookup"><span data-stu-id="4d8f1-111">Net amount per line</span></span>
<span data-ttu-id="4d8f1-112">Válassza ezt az opciót a számlasorok nettó összegén alapuló áfa értékek meghatározására, minden egyéb adó kizárásával.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-112">Select this option to determine sales tax rates based on the net amount for the invoice lines, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="4d8f1-113">Példa</span><span class="sxs-lookup"><span data-stu-id="4d8f1-113">Example</span></span>

<span data-ttu-id="4d8f1-114">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-114">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="4d8f1-115">Összegintervallum</span><span class="sxs-lookup"><span data-stu-id="4d8f1-115">Amount interval</span></span>    | <span data-ttu-id="4d8f1-116">Adómérték</span><span class="sxs-lookup"><span data-stu-id="4d8f1-116">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="4d8f1-117">0 - 50</span><span class="sxs-lookup"><span data-stu-id="4d8f1-117">0 - 50</span></span>             | <span data-ttu-id="4d8f1-118">30%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-118">30%</span></span>      |
| <span data-ttu-id="4d8f1-119">50 - 100</span><span class="sxs-lookup"><span data-stu-id="4d8f1-119">50 - 100</span></span>           | <span data-ttu-id="4d8f1-120">20%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-120">20%</span></span>      |
| <span data-ttu-id="4d8f1-121">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="4d8f1-121">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="4d8f1-122">10%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-122">10%</span></span>      |

> [!NOTE]                                                                                                             
> <span data-ttu-id="4d8f1-123">Az utolsó intervallumban szereplő nulla (0) felső határ azt jelenti, hogy minden olyan összeg, amely meghaladja a 100-at ebbe az intervallumba esik.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-123">The upper limit of zero (0) in the last interval means that all amounts that exceed 100 are included in the interval.</span></span>

<span data-ttu-id="4d8f1-124">Számítás alapja: **nettó összeg soronként**</span><span class="sxs-lookup"><span data-stu-id="4d8f1-124">Marginal base: **Net amount per line**</span></span> 

<span data-ttu-id="4d8f1-125">Számítási mód: **Intervallum**</span><span class="sxs-lookup"><span data-stu-id="4d8f1-125">Calculation method: **Interval**</span></span> 

<span data-ttu-id="4d8f1-126">8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-126">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="4d8f1-127">A számlasor nettó értéke 200.00.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-127">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="4d8f1-128">Az áfa számítása a következő:</span><span class="sxs-lookup"><span data-stu-id="4d8f1-128">The tax is calculated as follows:</span></span> 

<span data-ttu-id="4d8f1-129">Áfa összesen = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35,00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-129">Total sales tax = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35.00</span></span> 

<span data-ttu-id="4d8f1-130">Teljes számlaösszeg = 200,00 + 35,00 = 235,00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-130">Total invoice amount = 200.00 + 35.00 = 235.00</span></span> 

<span data-ttu-id="4d8f1-131">**Változat**</span><span class="sxs-lookup"><span data-stu-id="4d8f1-131">**Variation**</span></span> 

<span data-ttu-id="4d8f1-132">Ha a számlán két sor szerepel, amelyekben egyenként négy cikk van, akkor a soronkénti nettó összeg 100,00 euró, az áfa számítása pedig a következő:</span><span class="sxs-lookup"><span data-stu-id="4d8f1-132">If the invoice has two lines with four items on each line, the net amount on each line is 100.00 and the sales tax is calculated as follows:</span></span> 

<span data-ttu-id="4d8f1-133">1. sor áfája = 50 x 30% + 50 x 20% = 15 + 10 = 25,00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-133">Sales tax line 1 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="4d8f1-134">2. sor áfája = 50 x 30% + 50 x 20% = 15 + 10 = 25,00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-134">Sales tax line 2 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="4d8f1-135">Áfa összesen = 25,00 + 25,00 = 50,00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-135">Total sales tax = 25.00 + 25.00 = 50.00</span></span> 

<span data-ttu-id="4d8f1-136">Teljes számlaösszeg = 200,00 + 50,00 = 250,00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-136">Total invoice amount = 200.00 + 50.00 = 250.00</span></span>

## <a name="net-amount-per-unit"></a><span data-ttu-id="4d8f1-137"> Egységenkénti nettó összeg</span><span class="sxs-lookup"><span data-stu-id="4d8f1-137">Net amount per unit</span></span>
<span data-ttu-id="4d8f1-138">Válassza ezt az opciót a az egyes egységek értékein alapuló áfa értékek meghatározására, minden egyéb adó kizárásával.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-138">Select this option to determine sales tax rates based on the value of each unit, excluding any other taxes.</span></span> <span data-ttu-id="4d8f1-139">Ha egy számítás alapon alapuló egység van bejelölve, akkor is egy egységet kell megadni az áfakódhoz.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-139">When a unit based Marginal base is selected then also a Unit has to be specified for the Sales tax code.</span></span>

### <a name="example"></a><span data-ttu-id="4d8f1-140">Példa</span><span class="sxs-lookup"><span data-stu-id="4d8f1-140">Example</span></span>

<span data-ttu-id="4d8f1-141">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-141">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="4d8f1-142">Összeg</span><span class="sxs-lookup"><span data-stu-id="4d8f1-142">Amount</span></span>             | <span data-ttu-id="4d8f1-143">Adómérték</span><span class="sxs-lookup"><span data-stu-id="4d8f1-143">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="4d8f1-144">0 - 50</span><span class="sxs-lookup"><span data-stu-id="4d8f1-144">0 - 50</span></span>             | <span data-ttu-id="4d8f1-145">30%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-145">30%</span></span>      |
| <span data-ttu-id="4d8f1-146">50 - 100</span><span class="sxs-lookup"><span data-stu-id="4d8f1-146">50 - 100</span></span>           | <span data-ttu-id="4d8f1-147">20%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-147">20%</span></span>      |
| <span data-ttu-id="4d8f1-148">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="4d8f1-148">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="4d8f1-149">10%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-149">10%</span></span>      |

<span data-ttu-id="4d8f1-150">Számítás alapja: **nettó összeg egységenként**</span><span class="sxs-lookup"><span data-stu-id="4d8f1-150">Marginal base: **Net amount per unit**</span></span> 

<span data-ttu-id="4d8f1-151">Számítási mód: **Teljes összeg**</span><span class="sxs-lookup"><span data-stu-id="4d8f1-151">Calculation method: **Whole amount**</span></span> 

<span data-ttu-id="4d8f1-152">8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-152">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="4d8f1-153">A számlasor nettó értéke 200.00.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-153">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="4d8f1-154">Az áfa számítása a következőképpen történik: Egységenkénti áfa = 25,00 x 30 % = 7.50 Összes áfa = 7,50 x 8 egység = 60.00 Teljes számlaösszeg = 200,00 + 60,00 = 260.00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-154">The tax is calculated as follows: Sales tax per unit = 25.00 x 30% = 7.50 Total sales tax = 7.50 x 8 units = 60.00 Total invoice amount = 200.00 + 60.00 = 260.00</span></span>

## <a name="net-amount-of-invoice-balance"></a><span data-ttu-id="4d8f1-155"> Számlaegyenleg nettó összege</span><span class="sxs-lookup"><span data-stu-id="4d8f1-155">Net amount of invoice balance</span></span>

<span data-ttu-id="4d8f1-156">Válassza ezt az opciót a számlasorok nettó összegén alapuló áfa értékek meghatározására, minden egyéb adó kizárásával.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-156">Select this option to determine sales tax rates based on the total value for the invoice, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="4d8f1-157">Példa</span><span class="sxs-lookup"><span data-stu-id="4d8f1-157">Example</span></span>

<span data-ttu-id="4d8f1-158">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-158">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="4d8f1-159">Összeg</span><span class="sxs-lookup"><span data-stu-id="4d8f1-159">Amount</span></span>            | <span data-ttu-id="4d8f1-160">Adómérték</span><span class="sxs-lookup"><span data-stu-id="4d8f1-160">Tax rate</span></span> |
|-------------------|----------|
| <span data-ttu-id="4d8f1-161">0 - 50</span><span class="sxs-lookup"><span data-stu-id="4d8f1-161">0 - 50</span></span>            | <span data-ttu-id="4d8f1-162">30%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-162">30%</span></span>      |
| <span data-ttu-id="4d8f1-163">50 - 100</span><span class="sxs-lookup"><span data-stu-id="4d8f1-163">50 - 100</span></span>          | <span data-ttu-id="4d8f1-164">20%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-164">20%</span></span>      |
| <span data-ttu-id="4d8f1-165">100 -0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="4d8f1-165">100 -0 (&gt; 100)</span></span> | <span data-ttu-id="4d8f1-166">10%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-166">10%</span></span>      |

<span data-ttu-id="4d8f1-167">Számítás alapja: **Számlaegyenleg nettó összege**</span><span class="sxs-lookup"><span data-stu-id="4d8f1-167">Marginal base: **Net amount of invoice balance**</span></span> 

<span data-ttu-id="4d8f1-168">Számítási módszer: **Intervallum** Egy értékesítési számlában 2 sor szerepel mindkét sorában 4 lámpával, egyenkénti értékük 25,00.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-168">Calculation method: **Interval** A sales invoice has 2 lines with 4 lamps on each lines for 25.00 each.</span></span> <span data-ttu-id="4d8f1-169">Számlaegyenleg nettó összege 4 x 25,00 + 4 x 25,00 = 200,00.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-169">The net amount of invoice balance is 4 x 25.00 + 4 x 25.00 = 200.00.</span></span> <span data-ttu-id="4d8f1-170">Az áfa számítása a következőképpen történik: Összes áfa = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Teljes számlaösszeg = 200,00 + 35,00 = 235.00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-170">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 100 x 0.10 = 15 + 10 + 10 = 35.00 Total invoice amount = 200.00 + 35.00 = 235.00</span></span>

## <a name="gross-amount-per-line"></a><span data-ttu-id="4d8f1-171"> Soronkénti bruttó összeg</span><span class="sxs-lookup"><span data-stu-id="4d8f1-171">Gross amount per line</span></span>

<span data-ttu-id="4d8f1-172">Válassza ezt az opciót a számlasorok értékein alapuló áfa értékek meghatározására, minden erre a sorra vonatkozó egyéb adóval együtt.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-172">Select this option to determine sales tax rates based on the value of the line including all other taxes for that line.</span></span>

> [!NOTE]
> <span data-ttu-id="4d8f1-173">Egy áfacsoportban csak egy áfakód lehetséges ezzel a kiválasztással a számítási alap mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-173">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="4d8f1-174">Példa</span><span class="sxs-lookup"><span data-stu-id="4d8f1-174">Example</span></span>

<span data-ttu-id="4d8f1-175">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-175">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="4d8f1-176">Összeg</span><span class="sxs-lookup"><span data-stu-id="4d8f1-176">Amount</span></span>             | <span data-ttu-id="4d8f1-177">Adómérték</span><span class="sxs-lookup"><span data-stu-id="4d8f1-177">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="4d8f1-178">0 - 50</span><span class="sxs-lookup"><span data-stu-id="4d8f1-178">0 - 50</span></span>             | <span data-ttu-id="4d8f1-179">30%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-179">30%</span></span>      |
| <span data-ttu-id="4d8f1-180">50 - 100</span><span class="sxs-lookup"><span data-stu-id="4d8f1-180">50 - 100</span></span>           | <span data-ttu-id="4d8f1-181">20%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-181">20%</span></span>      |
| <span data-ttu-id="4d8f1-182">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="4d8f1-182">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="4d8f1-183">10%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-183">10%</span></span>      |

<span data-ttu-id="4d8f1-184">Számítás alapja: **Soronkénti bruttó összeg** Számítási módszer: **Intervallum** Ezen kívül van egy másik áfakód minden lámpán 5,00 speciális vám kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-184">Marginal base: **Gross amount per line** Calculation method: **Interval** Additionally there is another tax code calculated for a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="4d8f1-185">A vámot a nettó összeghez kell hozzáadni, még az áfa számítása előtt.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-185">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="4d8f1-186">8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-186">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="4d8f1-187">A számlasor nettó értéke 200.00.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-187">The net amount for the invoice line is 200.00.</span></span> <span data-ttu-id="4d8f1-188">A számlasor bruttó összege 8 x 25.00 + 8 x 5,00 = 240,00.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-188">The gross amount for the invoice line is 8 x 25.00 + 8 x 5.00 = 240.00.</span></span> <span data-ttu-id="4d8f1-189">Az áfa számítása a következőképpen történik: Összes áfa = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 Összes vám = 5,00 x 8 = 40,00 Teljes számlaösszeg = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-189">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 20 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="4d8f1-190">**Változat**</span><span class="sxs-lookup"><span data-stu-id="4d8f1-190">**Variation**</span></span> 

<span data-ttu-id="4d8f1-191">Ha a számlán két számlasor szerepel, amelyekben egyenként négy cikk van, akkor a számlasoronkénti nettó összeg 100,00.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-191">If the invoice is created by using 2 invoice lines with 4 items on each line, the net amount per invoice line is 100.00.</span></span> <span data-ttu-id="4d8f1-192">A számlasoronkénti bruttó összeg (4 x 5.00 vámmal együtt) 120.00 lenne, és az áfa létrehozása a következőképpen történik: Számla sor 1 áfája = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Számla sor 2 áfája = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Összes áfa = 27,00 + 27,00 = 54,00 Összes vám = 5,00 x 8 = 40,00 Teljes számlaösszeg = 200,00 + 54,00 + 40,00 = 294.00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-192">The gross amount (including the duty of 4 x 5.00) per invoice line would be 120.00, and the sales tax is created as follows: Sales tax invoice line 1 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Sales tax invoice line 2 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Total sales tax = 27.00 + 27.00 = 54.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 54.00 + 40.00 = 294.00</span></span>

## <a name="gross-amount-per-unit"></a><span data-ttu-id="4d8f1-193"> Egységenkénti bruttó összeg</span><span class="sxs-lookup"><span data-stu-id="4d8f1-193">Gross amount per unit</span></span>

<span data-ttu-id="4d8f1-194">Válassza ezt az opciót az egység értékein alapuló áfa értékek meghatározására, minden egyéb adóval együtt.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-194">Select this option to determine sales tax rates based on the value of the unit including any other taxes.</span></span>

> [!NOTE]
> <span data-ttu-id="4d8f1-195">Egy áfacsoportban csak egy áfakód lehetséges ezzel a kiválasztással a számítási alap mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-195">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="4d8f1-196">Példa</span><span class="sxs-lookup"><span data-stu-id="4d8f1-196">Example</span></span>

<span data-ttu-id="4d8f1-197">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-197">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="4d8f1-198">Összeg</span><span class="sxs-lookup"><span data-stu-id="4d8f1-198">Amount</span></span>             | <span data-ttu-id="4d8f1-199">Adómérték</span><span class="sxs-lookup"><span data-stu-id="4d8f1-199">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="4d8f1-200">0 - 50</span><span class="sxs-lookup"><span data-stu-id="4d8f1-200">0 - 50</span></span>             | <span data-ttu-id="4d8f1-201">30%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-201">30%</span></span>      |
| <span data-ttu-id="4d8f1-202">50 - 100</span><span class="sxs-lookup"><span data-stu-id="4d8f1-202">50 - 100</span></span>           | <span data-ttu-id="4d8f1-203">20%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-203">20%</span></span>      |
| <span data-ttu-id="4d8f1-204">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="4d8f1-204">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="4d8f1-205">10%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-205">10%</span></span>      |

<span data-ttu-id="4d8f1-206">Számítás alapja: **Egységenkénti bruttó összeg** Minden lámpán 5,00 speciális vám van.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-206">Marginal base: **Gross amount per unit** There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="4d8f1-207">A vámot a nettó összeghez kell hozzáadni, még az áfa számítása előtt.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-207">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="4d8f1-208">8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-208">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="4d8f1-209">Az egységenkénti bruttó érték 30,00.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-209">The gross amount per unit is 30.00.</span></span> <span data-ttu-id="4d8f1-210">Az áfa számítása a következőképpen történik: Összes áfa = 30 x 30% = 9.00 Összes áfa = 9,00 x 8 = 72,00 Teljes vám= 5.00 x 8 = 40.00 Teljes számlaösszeg =200.00 + 72,00 + 40,00 = 312.00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-210">The tax is calculated as follows: Sales tax per unit = 30 x 30% = 9.00 Total sales tax = 9.00 x 8 = 72.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 72.00 + 40.00 = 312.00</span></span>

## <a name="invoice-total-incl-other-sales-tax-amounts"></a><span data-ttu-id="4d8f1-211"> Egyéb áfaösszegeket tartalmazó számlaösszeg</span><span class="sxs-lookup"><span data-stu-id="4d8f1-211">Invoice total incl. other sales tax amounts</span></span>

<span data-ttu-id="4d8f1-212">Válassza ezt az opciót a számla összes értékén alapuló áfa értékek meghatározására, minden egyéb adóval együtt.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-212">Select this option to determine sales tax rates based on the total value for the invoice including any other taxes.</span></span>
> [!NOTE]
> <span data-ttu-id="4d8f1-213">Egy áfacsoportban csak egy áfakód lehetséges ezzel a kiválasztással a Számítási alap mezőben</span><span class="sxs-lookup"><span data-stu-id="4d8f1-213">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field</span></span>

### <a name="example"></a><span data-ttu-id="4d8f1-214">Példa</span><span class="sxs-lookup"><span data-stu-id="4d8f1-214">Example</span></span>

<span data-ttu-id="4d8f1-215">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-215">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="4d8f1-216">Összeg</span><span class="sxs-lookup"><span data-stu-id="4d8f1-216">Amount</span></span>             | <span data-ttu-id="4d8f1-217">Adómérték</span><span class="sxs-lookup"><span data-stu-id="4d8f1-217">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="4d8f1-218">0 - 50</span><span class="sxs-lookup"><span data-stu-id="4d8f1-218">0 - 50</span></span>             | <span data-ttu-id="4d8f1-219">30%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-219">30%</span></span>      |
| <span data-ttu-id="4d8f1-220">50 - 100</span><span class="sxs-lookup"><span data-stu-id="4d8f1-220">50 - 100</span></span>           | <span data-ttu-id="4d8f1-221">20%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-221">20%</span></span>      |
| <span data-ttu-id="4d8f1-222">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="4d8f1-222">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="4d8f1-223">10%</span><span class="sxs-lookup"><span data-stu-id="4d8f1-223">10%</span></span>      |

<span data-ttu-id="4d8f1-224">Számítás alapja: **Egyéb áfaösszegeket tartalmazó számlaösszeg** Számítási módszer: **Intervallum** </span><span class="sxs-lookup"><span data-stu-id="4d8f1-224">Marginal base: **Invoice total incl. other sales tax amounts** Calculation method: **Interval** </span></span>  
<span data-ttu-id="4d8f1-225">Minden lámpán 5,00 értékű speciális vám van.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-225">There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="4d8f1-226">A vámot a nettó összeghez kell hozzáadni, még az áfa számítása előtt.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-226">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="4d8f1-227">8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-227">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="4d8f1-228">A számlasor nettó értéke 200.00.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-228">The net amount for the invoice is 200.00.</span></span> <span data-ttu-id="4d8f1-229">A számla bruttó összege 200.00 + (8 x 5,00) = 240,00.</span><span class="sxs-lookup"><span data-stu-id="4d8f1-229">The gross amount for the invoice is 200.00 + (8 x 5.00) = 240.00.</span></span> <span data-ttu-id="4d8f1-230">Az áfa számítása a következőképpen történik: Összes áfa = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Összes vám = 5,00 x 8 = 40,00 Teljes számlaösszeg = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="4d8f1-230">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 10 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="4d8f1-231">További tájékoztatás: [Teljes összeg és az Intervallum számítási beállítások az áfakódokhoz](whole-amount-interval-options-sales-tax-codes.md) [Áfaszámítási módszerek az Eredet mezőben](sales-tax-calculation-methods-origin-field.md)</span><span class="sxs-lookup"><span data-stu-id="4d8f1-231">For more information, see [Whole amount and Interval calculation options for sales tax codes](whole-amount-interval-options-sales-tax-codes.md) and [Sales tax calculation methods in the Origin field](sales-tax-calculation-methods-origin-field.md).</span></span>



