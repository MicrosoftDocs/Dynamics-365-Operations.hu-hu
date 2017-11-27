---
title: "Áfaérték a Számítás alapja és a Számítási módszerek lapján"
description: "A témakör leírja, hogy a Számítás alapja mezőben található értékek és a Számítási módszer értékei, hogyan határozzák meg az értékesítési és beszerzési tranzakciók adó(it)."
author: twheeloc
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bf0f8f2e3f553ea181e8cc9ab5b712fce64a89d4
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a><span data-ttu-id="6445b-103">Áfaérték a Számítás alapja és a Számítási módszerek lapján</span><span class="sxs-lookup"><span data-stu-id="6445b-103">Sales tax rates based on the Marginal base and Calculation methods</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6445b-104">A témakör leírja, hogy a Számítás alapja mezőben található értékek és a Számítási módszer értékei, hogyan határozzák meg az értékesítési és beszerzési tranzakciók adó(it).</span><span class="sxs-lookup"><span data-stu-id="6445b-104">This topic explains how the values in the fields Marginal base and Calculation method determine the tax rate(s) in sales and purchase transactions.</span></span>

<span data-ttu-id="6445b-105">A számítás gyorslapon és az áfa kód lapon lévő számítás alapot az határozza meg, hogy melyik összeg használatos a megfelelő adó értékek az áfa kód értékek oldalán lévő értékekből történő kivételéhez.</span><span class="sxs-lookup"><span data-stu-id="6445b-105">The Marginal base on the Calculation FastTab on the Sales tax codes page determines which amount is used to pick the appropriate tax rate(s) from the rates in the Sales tax code values page.</span></span> <span data-ttu-id="6445b-106">A számítási mód mező módszerével kombinált számítás alapja mezőben lévő a összeg típusa határozza meg, hogy hogyan találja meg a tranzakcióhoz a megfelelő adó értéket.</span><span class="sxs-lookup"><span data-stu-id="6445b-106">The amount type in the Marginal base field in combination with the method in the Calculation method field determines the logic to find the correct tax rate(s) for a transaction.</span></span> 

<span data-ttu-id="6445b-107">A mezőértékek különféle kombinációi igen különböző áfaszámítási módokra adnak lehetőséget, ahogy az a következő példákban is látható.</span><span class="sxs-lookup"><span data-stu-id="6445b-107">Various combinations of values in these fields produce very different sales tax calculations, as shown by the following examples.</span></span> <span data-ttu-id="6445b-108">A példák ugyanazokat az áfaintervallum értékek használják, amelyek az áfa kód értékek oldalán állíthatók be minden áfakód esetében.</span><span class="sxs-lookup"><span data-stu-id="6445b-108">The examples use the same tax interval values, which are set up for each tax code in the Sales tax codes values page.</span></span> <span data-ttu-id="6445b-109">A lap megnyitásához kattintson az Áfakódra &gt; A forgalmi adó kód lap értékeire.</span><span class="sxs-lookup"><span data-stu-id="6445b-109">To open this page, click Sales tax code &gt; Values in the Sales tax codes page.</span></span>

> [!Important]                                                                                                                  
> <span data-ttu-id="6445b-110">Ha az áfakódok bármelyikének számítási alapja a sor összegétől vagy egységtől függ, akkor aszámítási módszer mezőjének értékét a sorra kell beállítani a főkönyv paramétereinek oldalán.</span><span class="sxs-lookup"><span data-stu-id="6445b-110">If the Marginal base on one or more of your sales tax codes is based on line amounts or units, the value of the Calculation method field in the General ledger parameters page must be set to Line.</span></span> |

## <a name="net-amount-per-line"></a><span data-ttu-id="6445b-111"> Soronkénti nettó összeg</span><span class="sxs-lookup"><span data-stu-id="6445b-111">Net amount per line</span></span>
<span data-ttu-id="6445b-112">Válassza ezt az opciót a számlasorok nettó összegén alapuló áfa értékek meghatározására, minden egyéb adó kizárásával.</span><span class="sxs-lookup"><span data-stu-id="6445b-112">Select this option to determine sales tax rates based on the net amount for the invoice lines, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="6445b-113">Példa</span><span class="sxs-lookup"><span data-stu-id="6445b-113">Example</span></span>

<span data-ttu-id="6445b-114">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="6445b-114">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="6445b-115">Összegintervallum</span><span class="sxs-lookup"><span data-stu-id="6445b-115">Amount interval</span></span>    | <span data-ttu-id="6445b-116">Adómérték</span><span class="sxs-lookup"><span data-stu-id="6445b-116">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="6445b-117">0 - 50</span><span class="sxs-lookup"><span data-stu-id="6445b-117">0 - 50</span></span>             | <span data-ttu-id="6445b-118">30%</span><span class="sxs-lookup"><span data-stu-id="6445b-118">30%</span></span>      |
| <span data-ttu-id="6445b-119">50 - 100</span><span class="sxs-lookup"><span data-stu-id="6445b-119">50 - 100</span></span>           | <span data-ttu-id="6445b-120">20%</span><span class="sxs-lookup"><span data-stu-id="6445b-120">20%</span></span>      |
| <span data-ttu-id="6445b-121">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="6445b-121">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="6445b-122">10%</span><span class="sxs-lookup"><span data-stu-id="6445b-122">10%</span></span>      |

> [!NOTE]                                                                                                             
> <span data-ttu-id="6445b-123">Az utolsó intervallumban szereplő nulla (0) felső határ azt jelenti, hogy minden olyan összeg, amely meghaladja a 100-at ebbe az intervallumba esik.</span><span class="sxs-lookup"><span data-stu-id="6445b-123">The upper limit of zero (0) in the last interval means that all amounts that exceed 100 are included in the interval.</span></span>

<span data-ttu-id="6445b-124">Számítás alapja: **nettó összeg soronként**</span><span class="sxs-lookup"><span data-stu-id="6445b-124">Marginal base: **Net amount per line**</span></span> 

<span data-ttu-id="6445b-125">Számítási mód: **Intervallum**</span><span class="sxs-lookup"><span data-stu-id="6445b-125">Calculation method: **Interval**</span></span> 

<span data-ttu-id="6445b-126">8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek.</span><span class="sxs-lookup"><span data-stu-id="6445b-126">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="6445b-127">A számlasor nettó értéke 200.00.</span><span class="sxs-lookup"><span data-stu-id="6445b-127">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="6445b-128">Az áfa számítása a következő:</span><span class="sxs-lookup"><span data-stu-id="6445b-128">The tax is calculated as follows:</span></span> 

<span data-ttu-id="6445b-129">Áfa összesen = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35,00</span><span class="sxs-lookup"><span data-stu-id="6445b-129">Total sales tax = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35.00</span></span> 

<span data-ttu-id="6445b-130">Teljes számlaösszeg = 200,00 + 35,00 = 235,00</span><span class="sxs-lookup"><span data-stu-id="6445b-130">Total invoice amount = 200.00 + 35.00 = 235.00</span></span> 

<span data-ttu-id="6445b-131">**Változat**</span><span class="sxs-lookup"><span data-stu-id="6445b-131">**Variation**</span></span> 

<span data-ttu-id="6445b-132">Ha a számlán két sor szerepel, amelyekben egyenként négy cikk van, akkor a soronkénti nettó összeg 100,00 euró, az áfa számítása pedig a következő:</span><span class="sxs-lookup"><span data-stu-id="6445b-132">If the invoice has two lines with four items on each line, the net amount on each line is 100.00 and the sales tax is calculated as follows:</span></span> 

<span data-ttu-id="6445b-133">1. sor áfája = 50 x 30% + 50 x 20% = 15 + 10 = 25,00</span><span class="sxs-lookup"><span data-stu-id="6445b-133">Sales tax line 1 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="6445b-134">2. sor áfája = 50 x 30% + 50 x 20% = 15 + 10 = 25,00</span><span class="sxs-lookup"><span data-stu-id="6445b-134">Sales tax line 2 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="6445b-135">Áfa összesen = 25,00 + 25,00 = 50,00</span><span class="sxs-lookup"><span data-stu-id="6445b-135">Total sales tax = 25.00 + 25.00 = 50.00</span></span> 

<span data-ttu-id="6445b-136">Teljes számlaösszeg = 200,00 + 50,00 = 250,00</span><span class="sxs-lookup"><span data-stu-id="6445b-136">Total invoice amount = 200.00 + 50.00 = 250.00</span></span>

## <a name="net-amount-per-unit"></a><span data-ttu-id="6445b-137"> Egységenkénti nettó összeg</span><span class="sxs-lookup"><span data-stu-id="6445b-137">Net amount per unit</span></span>
<span data-ttu-id="6445b-138">Válassza ezt az opciót a az egyes egységek értékein alapuló áfa értékek meghatározására, minden egyéb adó kizárásával.</span><span class="sxs-lookup"><span data-stu-id="6445b-138">Select this option to determine sales tax rates based on the value of each unit, excluding any other taxes.</span></span> <span data-ttu-id="6445b-139">Ha egy számítás alapon alapuló egység van bejelölve, akkor is egy egységet kell megadni az áfakódhoz.</span><span class="sxs-lookup"><span data-stu-id="6445b-139">When a unit based Marginal base is selected then also a Unit has to be specified for the Sales tax code.</span></span>

### <a name="example"></a><span data-ttu-id="6445b-140">Példa</span><span class="sxs-lookup"><span data-stu-id="6445b-140">Example</span></span>

<span data-ttu-id="6445b-141">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="6445b-141">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="6445b-142">Összeg</span><span class="sxs-lookup"><span data-stu-id="6445b-142">Amount</span></span>             | <span data-ttu-id="6445b-143">Adómérték</span><span class="sxs-lookup"><span data-stu-id="6445b-143">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="6445b-144">0 - 50</span><span class="sxs-lookup"><span data-stu-id="6445b-144">0 - 50</span></span>             | <span data-ttu-id="6445b-145">30%</span><span class="sxs-lookup"><span data-stu-id="6445b-145">30%</span></span>      |
| <span data-ttu-id="6445b-146">50 - 100</span><span class="sxs-lookup"><span data-stu-id="6445b-146">50 - 100</span></span>           | <span data-ttu-id="6445b-147">20%</span><span class="sxs-lookup"><span data-stu-id="6445b-147">20%</span></span>      |
| <span data-ttu-id="6445b-148">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="6445b-148">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="6445b-149">10%</span><span class="sxs-lookup"><span data-stu-id="6445b-149">10%</span></span>      |

<span data-ttu-id="6445b-150">Számítás alapja: **nettó összeg egységenként**</span><span class="sxs-lookup"><span data-stu-id="6445b-150">Marginal base: **Net amount per unit**</span></span> 

<span data-ttu-id="6445b-151">Számítási mód: **Teljes összeg**</span><span class="sxs-lookup"><span data-stu-id="6445b-151">Calculation method: **Whole amount**</span></span> 

<span data-ttu-id="6445b-152">8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek.</span><span class="sxs-lookup"><span data-stu-id="6445b-152">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="6445b-153">A számlasor nettó értéke 200.00.</span><span class="sxs-lookup"><span data-stu-id="6445b-153">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="6445b-154">Az áfa számítása a következőképpen történik: Egységenkénti áfa = 25,00 x 30 % = 7.50 Összes áfa = 7,50 x 8 egység = 60.00 Teljes számlaösszeg = 200,00 + 60,00 = 260.00</span><span class="sxs-lookup"><span data-stu-id="6445b-154">The tax is calculated as follows: Sales tax per unit = 25.00 x 30% = 7.50 Total sales tax = 7.50 x 8 units = 60.00 Total invoice amount = 200.00 + 60.00 = 260.00</span></span>

## <a name="net-amount-of-invoice-balance"></a><span data-ttu-id="6445b-155"> Számlaegyenleg nettó összege</span><span class="sxs-lookup"><span data-stu-id="6445b-155">Net amount of invoice balance</span></span>

<span data-ttu-id="6445b-156">Válassza ezt az opciót a számlasorok nettó összegén alapuló áfa értékek meghatározására, minden egyéb adó kizárásával.</span><span class="sxs-lookup"><span data-stu-id="6445b-156">Select this option to determine sales tax rates based on the total value for the invoice, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="6445b-157">Példa</span><span class="sxs-lookup"><span data-stu-id="6445b-157">Example</span></span>

<span data-ttu-id="6445b-158">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="6445b-158">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="6445b-159">Összeg</span><span class="sxs-lookup"><span data-stu-id="6445b-159">Amount</span></span>            | <span data-ttu-id="6445b-160">Adómérték</span><span class="sxs-lookup"><span data-stu-id="6445b-160">Tax rate</span></span> |
|-------------------|----------|
| <span data-ttu-id="6445b-161">0 - 50</span><span class="sxs-lookup"><span data-stu-id="6445b-161">0 - 50</span></span>            | <span data-ttu-id="6445b-162">30%</span><span class="sxs-lookup"><span data-stu-id="6445b-162">30%</span></span>      |
| <span data-ttu-id="6445b-163">50 - 100</span><span class="sxs-lookup"><span data-stu-id="6445b-163">50 - 100</span></span>          | <span data-ttu-id="6445b-164">20%</span><span class="sxs-lookup"><span data-stu-id="6445b-164">20%</span></span>      |
| <span data-ttu-id="6445b-165">100 -0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="6445b-165">100 -0 (&gt; 100)</span></span> | <span data-ttu-id="6445b-166">10%</span><span class="sxs-lookup"><span data-stu-id="6445b-166">10%</span></span>      |

<span data-ttu-id="6445b-167">Számítás alapja: **Számlaegyenleg nettó összege**</span><span class="sxs-lookup"><span data-stu-id="6445b-167">Marginal base: **Net amount of invoice balance**</span></span> 

<span data-ttu-id="6445b-168">Számítási módszer: **Intervallum** Egy értékesítési számlában 2 sor szerepel mindkét sorában 4 lámpával, egyenkénti értékük 25,00.</span><span class="sxs-lookup"><span data-stu-id="6445b-168">Calculation method: **Interval** A sales invoice has 2 lines with 4 lamps on each lines for 25.00 each.</span></span> <span data-ttu-id="6445b-169">Számlaegyenleg nettó összege 4 x 25,00 + 4 x 25,00 = 200,00.</span><span class="sxs-lookup"><span data-stu-id="6445b-169">The net amount of invoice balance is 4 x 25.00 + 4 x 25.00 = 200.00.</span></span> <span data-ttu-id="6445b-170">Az áfa számítása a következőképpen történik: Összes áfa = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Teljes számlaösszeg = 200,00 + 35,00 = 235.00</span><span class="sxs-lookup"><span data-stu-id="6445b-170">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 100 x 0.10 = 15 + 10 + 10 = 35.00 Total invoice amount = 200.00 + 35.00 = 235.00</span></span>

## <a name="gross-amount-per-line"></a><span data-ttu-id="6445b-171"> Soronkénti bruttó összeg</span><span class="sxs-lookup"><span data-stu-id="6445b-171">Gross amount per line</span></span>

<span data-ttu-id="6445b-172">Válassza ezt az opciót a számlasorok értékein alapuló áfa értékek meghatározására, minden erre a sorra vonatkozó egyéb adóval együtt.</span><span class="sxs-lookup"><span data-stu-id="6445b-172">Select this option to determine sales tax rates based on the value of the line including all other taxes for that line.</span></span>

> [!NOTE]
> <span data-ttu-id="6445b-173">Egy áfacsoportban csak egy áfakód lehetséges ezzel a kiválasztással a számítási alap mezőben.</span><span class="sxs-lookup"><span data-stu-id="6445b-173">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="6445b-174">Példa</span><span class="sxs-lookup"><span data-stu-id="6445b-174">Example</span></span>

<span data-ttu-id="6445b-175">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="6445b-175">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="6445b-176">Összeg</span><span class="sxs-lookup"><span data-stu-id="6445b-176">Amount</span></span>             | <span data-ttu-id="6445b-177">Adómérték</span><span class="sxs-lookup"><span data-stu-id="6445b-177">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="6445b-178">0 - 50</span><span class="sxs-lookup"><span data-stu-id="6445b-178">0 - 50</span></span>             | <span data-ttu-id="6445b-179">30%</span><span class="sxs-lookup"><span data-stu-id="6445b-179">30%</span></span>      |
| <span data-ttu-id="6445b-180">50 - 100</span><span class="sxs-lookup"><span data-stu-id="6445b-180">50 - 100</span></span>           | <span data-ttu-id="6445b-181">20%</span><span class="sxs-lookup"><span data-stu-id="6445b-181">20%</span></span>      |
| <span data-ttu-id="6445b-182">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="6445b-182">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="6445b-183">10%</span><span class="sxs-lookup"><span data-stu-id="6445b-183">10%</span></span>      |

<span data-ttu-id="6445b-184">Számítás alapja: **Soronkénti bruttó összeg** Számítási módszer: **Intervallum** Ezen kívül van egy másik áfakód minden lámpán 5,00 speciális vám kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="6445b-184">Marginal base: **Gross amount per line** Calculation method: **Interval** Additionally there is another tax code calculated for a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="6445b-185">A vámot a nettó összeghez kell hozzáadni, még az áfa számítása előtt.</span><span class="sxs-lookup"><span data-stu-id="6445b-185">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="6445b-186">8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek.</span><span class="sxs-lookup"><span data-stu-id="6445b-186">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="6445b-187">A számlasor nettó értéke 200.00.</span><span class="sxs-lookup"><span data-stu-id="6445b-187">The net amount for the invoice line is 200.00.</span></span> <span data-ttu-id="6445b-188">A számlasor bruttó összege 8 x 25.00 + 8 x 5,00 = 240,00.</span><span class="sxs-lookup"><span data-stu-id="6445b-188">The gross amount for the invoice line is 8 x 25.00 + 8 x 5.00 = 240.00.</span></span> <span data-ttu-id="6445b-189">Az áfa számítása a következőképpen történik: Összes áfa = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 Összes vám = 5,00 x 8 = 40,00 Teljes számlaösszeg = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="6445b-189">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 20 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="6445b-190">**Változat**</span><span class="sxs-lookup"><span data-stu-id="6445b-190">**Variation**</span></span> 

<span data-ttu-id="6445b-191">Ha a számlán két számlasor szerepel, amelyekben egyenként négy cikk van, akkor a számlasoronkénti nettó összeg 100,00.</span><span class="sxs-lookup"><span data-stu-id="6445b-191">If the invoice is created by using 2 invoice lines with 4 items on each line, the net amount per invoice line is 100.00.</span></span> <span data-ttu-id="6445b-192">A számlasoronkénti bruttó összeg (4 x 5.00 vámmal együtt) 120.00 lenne, és az áfa létrehozása a következőképpen történik: Számla sor 1 áfája = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Számla sor 2 áfája = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Összes áfa = 27,00 + 27,00 = 54,00 Összes vám = 5,00 x 8 = 40,00 Teljes számlaösszeg = 200,00 + 54,00 + 40,00 = 294.00</span><span class="sxs-lookup"><span data-stu-id="6445b-192">The gross amount (including the duty of 4 x 5.00) per invoice line would be 120.00, and the sales tax is created as follows: Sales tax invoice line 1 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Sales tax invoice line 2 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Total sales tax = 27.00 + 27.00 = 54.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 54.00 + 40.00 = 294.00</span></span>

## <a name="gross-amount-per-unit"></a><span data-ttu-id="6445b-193"> Egységenkénti bruttó összeg</span><span class="sxs-lookup"><span data-stu-id="6445b-193">Gross amount per unit</span></span>

<span data-ttu-id="6445b-194">Válassza ezt az opciót az egység értékein alapuló áfa értékek meghatározására, minden egyéb adóval együtt.</span><span class="sxs-lookup"><span data-stu-id="6445b-194">Select this option to determine sales tax rates based on the value of the unit including any other taxes.</span></span>

> [!NOTE]
> <span data-ttu-id="6445b-195">Egy áfacsoportban csak egy áfakód lehetséges ezzel a kiválasztással a számítási alap mezőben.</span><span class="sxs-lookup"><span data-stu-id="6445b-195">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="6445b-196">Példa</span><span class="sxs-lookup"><span data-stu-id="6445b-196">Example</span></span>

<span data-ttu-id="6445b-197">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="6445b-197">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="6445b-198">Összeg</span><span class="sxs-lookup"><span data-stu-id="6445b-198">Amount</span></span>             | <span data-ttu-id="6445b-199">Adómérték</span><span class="sxs-lookup"><span data-stu-id="6445b-199">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="6445b-200">0 - 50</span><span class="sxs-lookup"><span data-stu-id="6445b-200">0 - 50</span></span>             | <span data-ttu-id="6445b-201">30%</span><span class="sxs-lookup"><span data-stu-id="6445b-201">30%</span></span>      |
| <span data-ttu-id="6445b-202">50 - 100</span><span class="sxs-lookup"><span data-stu-id="6445b-202">50 - 100</span></span>           | <span data-ttu-id="6445b-203">20%</span><span class="sxs-lookup"><span data-stu-id="6445b-203">20%</span></span>      |
| <span data-ttu-id="6445b-204">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="6445b-204">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="6445b-205">10%</span><span class="sxs-lookup"><span data-stu-id="6445b-205">10%</span></span>      |

<span data-ttu-id="6445b-206">Számítás alapja: **Egységenkénti bruttó összeg** Minden lámpán 5,00 speciális vám van.</span><span class="sxs-lookup"><span data-stu-id="6445b-206">Marginal base: **Gross amount per unit** There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="6445b-207">A vámot a nettó összeghez kell hozzáadni, még az áfa számítása előtt.</span><span class="sxs-lookup"><span data-stu-id="6445b-207">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="6445b-208">8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek.</span><span class="sxs-lookup"><span data-stu-id="6445b-208">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="6445b-209">Az egységenkénti bruttó érték 30,00.</span><span class="sxs-lookup"><span data-stu-id="6445b-209">The gross amount per unit is 30.00.</span></span> <span data-ttu-id="6445b-210">Az áfa számítása a következőképpen történik: Összes áfa = 30 x 30% = 9.00 Összes áfa = 9,00 x 8 = 72,00 Teljes vám= 5.00 x 8 = 40.00 Teljes számlaösszeg =200.00 + 72,00 + 40,00 = 312.00</span><span class="sxs-lookup"><span data-stu-id="6445b-210">The tax is calculated as follows: Sales tax per unit = 30 x 30% = 9.00 Total sales tax = 9.00 x 8 = 72.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 72.00 + 40.00 = 312.00</span></span>

## <a name="invoice-total-incl-other-sales-tax-amounts"></a><span data-ttu-id="6445b-211"> Egyéb áfaösszegeket tartalmazó számlaösszeg</span><span class="sxs-lookup"><span data-stu-id="6445b-211">Invoice total incl. other sales tax amounts</span></span>

<span data-ttu-id="6445b-212">Válassza ezt az opciót a számla összes értékén alapuló áfa értékek meghatározására, minden egyéb adóval együtt.</span><span class="sxs-lookup"><span data-stu-id="6445b-212">Select this option to determine sales tax rates based on the total value for the invoice including any other taxes.</span></span>
> [!NOTE]
> <span data-ttu-id="6445b-213">Egy áfacsoportban csak egy áfakód lehetséges ezzel a kiválasztással a Számítási alap mezőben</span><span class="sxs-lookup"><span data-stu-id="6445b-213">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field</span></span>

### <a name="example"></a><span data-ttu-id="6445b-214">Példa</span><span class="sxs-lookup"><span data-stu-id="6445b-214">Example</span></span>

<span data-ttu-id="6445b-215">Az áfakulcsok a következő intervallumokra vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="6445b-215">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="6445b-216">Összeg</span><span class="sxs-lookup"><span data-stu-id="6445b-216">Amount</span></span>             | <span data-ttu-id="6445b-217">Adómérték</span><span class="sxs-lookup"><span data-stu-id="6445b-217">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="6445b-218">0 - 50</span><span class="sxs-lookup"><span data-stu-id="6445b-218">0 - 50</span></span>             | <span data-ttu-id="6445b-219">30%</span><span class="sxs-lookup"><span data-stu-id="6445b-219">30%</span></span>      |
| <span data-ttu-id="6445b-220">50 - 100</span><span class="sxs-lookup"><span data-stu-id="6445b-220">50 - 100</span></span>           | <span data-ttu-id="6445b-221">20%</span><span class="sxs-lookup"><span data-stu-id="6445b-221">20%</span></span>      |
| <span data-ttu-id="6445b-222">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="6445b-222">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="6445b-223">10%</span><span class="sxs-lookup"><span data-stu-id="6445b-223">10%</span></span>      |

<span data-ttu-id="6445b-224">Számítás alapja: **Egyéb áfaösszegeket tartalmazó számlaösszeg** Számítási módszer: **Intervallum** </span><span class="sxs-lookup"><span data-stu-id="6445b-224">Marginal base: **Invoice total incl. other sales tax amounts** Calculation method: **Interval** </span></span>  
<span data-ttu-id="6445b-225">Minden lámpán 5,00 értékű speciális vám van.</span><span class="sxs-lookup"><span data-stu-id="6445b-225">There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="6445b-226">A vámot a nettó összeghez kell hozzáadni, még az áfa számítása előtt.</span><span class="sxs-lookup"><span data-stu-id="6445b-226">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="6445b-227">8 darab lámpát vásárol, amelyek egyenként 25.00 kerülnek.</span><span class="sxs-lookup"><span data-stu-id="6445b-227">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="6445b-228">A számlasor nettó értéke 200.00.</span><span class="sxs-lookup"><span data-stu-id="6445b-228">The net amount for the invoice is 200.00.</span></span> <span data-ttu-id="6445b-229">A számla bruttó összege 200.00 + (8 x 5,00) = 240,00.</span><span class="sxs-lookup"><span data-stu-id="6445b-229">The gross amount for the invoice is 200.00 + (8 x 5.00) = 240.00.</span></span> <span data-ttu-id="6445b-230">Az áfa számítása a következőképpen történik: Összes áfa = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Összes vám = 5,00 x 8 = 40,00 Teljes számlaösszeg = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="6445b-230">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 10 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="6445b-231">További tájékoztatás: [Teljes összeg és az Intervallum számítási beállítások az áfakódokhoz](whole-amount-interval-options-sales-tax-codes.md) [Áfaszámítási módszerek az Eredet mezőben](sales-tax-calculation-methods-origin-field.md)</span><span class="sxs-lookup"><span data-stu-id="6445b-231">For more information, see [Whole amount and Interval calculation options for sales tax codes](whole-amount-interval-options-sales-tax-codes.md) and [Sales tax calculation methods in the Origin field](sales-tax-calculation-methods-origin-field.md).</span></span>




