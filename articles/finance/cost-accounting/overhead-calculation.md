---
title: Járulékos költség számítása
description: Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.
author: AndersGirke
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 8dc312e66dc666ac6c23bac6b705ffc7893fd06b
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187997"
---
# <a name="overhead-calculation"></a><span data-ttu-id="c12a3-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="c12a3-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c12a3-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="c12a3-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

## <a name="term-definition"></a><span data-ttu-id="c12a3-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="c12a3-105">Term definition</span></span>

<span data-ttu-id="c12a3-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="c12a3-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="c12a3-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="c12a3-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="c12a3-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="c12a3-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="c12a3-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="c12a3-109">Rent</span></span>
-   <span data-ttu-id="c12a3-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-110">Electricity</span></span>
-   <span data-ttu-id="c12a3-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="c12a3-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="c12a3-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="c12a3-112">Overhead calculation overview</span></span>
<span data-ttu-id="c12a3-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="c12a3-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="c12a3-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="c12a3-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="c12a3-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="c12a3-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="c12a3-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="c12a3-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="c12a3-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="c12a3-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="c12a3-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="c12a3-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="c12a3-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="c12a3-119">Version type</span></span>
-   <span data-ttu-id="c12a3-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="c12a3-120">Date and time</span></span>
-   <span data-ttu-id="c12a3-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="c12a3-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="c12a3-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="c12a3-122">Fiscal year</span></span>
-   <span data-ttu-id="c12a3-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-123">Fiscal period</span></span>

<span data-ttu-id="c12a3-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="c12a3-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="c12a3-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="c12a3-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="c12a3-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="c12a3-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="c12a3-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="c12a3-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="c12a3-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="c12a3-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="c12a3-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="c12a3-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="c12a3-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="c12a3-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="c12a3-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="c12a3-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="c12a3-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="c12a3-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="c12a3-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="c12a3-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="c12a3-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="c12a3-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="c12a3-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="c12a3-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="c12a3-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="c12a3-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="c12a3-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="c12a3-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c12a3-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c12a3-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="c12a3-140">Main account</span></span></th>
<th><span data-ttu-id="c12a3-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="c12a3-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="c12a3-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="c12a3-143">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-143">CC099</span></span></td>
<td><span data-ttu-id="c12a3-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-144">Default cost center</span></span></td>
<td><span data-ttu-id="c12a3-145">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-145">10001</span></span></td>
<td><span data-ttu-id="c12a3-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-146">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="c12a3-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="c12a3-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="c12a3-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="c12a3-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="c12a3-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="c12a3-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="c12a3-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="c12a3-151">Define the cost behavior rule</span></span>

<span data-ttu-id="c12a3-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="c12a3-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="c12a3-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="c12a3-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="c12a3-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="c12a3-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="c12a3-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="c12a3-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="c12a3-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="c12a3-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="c12a3-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="c12a3-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="c12a3-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="c12a3-159">Napló</span><span class="sxs-lookup"><span data-stu-id="c12a3-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c12a3-160">Napló</span><span class="sxs-lookup"><span data-stu-id="c12a3-160">Journal</span></span></th>
<th><span data-ttu-id="c12a3-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="c12a3-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c12a3-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c12a3-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="c12a3-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-164">00001</span><span class="sxs-lookup"><span data-stu-id="c12a3-164">00001</span></span></td>
<td><span data-ttu-id="c12a3-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="c12a3-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="c12a3-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="c12a3-166">Fiscal</span></span></td>
<td><span data-ttu-id="c12a3-167">2017</span><span class="sxs-lookup"><span data-stu-id="c12a3-167">2017</span></span></td>
<td><span data-ttu-id="c12a3-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-168">Period 1</span></span></td>
<td><span data-ttu-id="c12a3-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c12a3-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="c12a3-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c12a3-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c12a3-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c12a3-173">Cost element</span></span></th>
<th><span data-ttu-id="c12a3-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-174">Cost behavior</span></span></th>
<th><span data-ttu-id="c12a3-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="c12a3-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="c12a3-177">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-177">CC099</span></span></td>
<td><span data-ttu-id="c12a3-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-178">Default cost center</span></span></td>
<td><span data-ttu-id="c12a3-179">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-179">10001</span></span></td>
<td><span data-ttu-id="c12a3-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-180">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="c12a3-181">Unclassified</span></span></td>
<td><span data-ttu-id="c12a3-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c12a3-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="c12a3-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c12a3-185">Cost element</span></span></th>
<th><span data-ttu-id="c12a3-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-186">Cost behavior</span></span></th>
<th><span data-ttu-id="c12a3-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-187">Amount</span></span></th>
<th><span data-ttu-id="c12a3-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c12a3-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-189">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-189">CC099</span></span></td>
<td><span data-ttu-id="c12a3-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-190">Default cost center</span></span></td>
<td><span data-ttu-id="c12a3-191">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-191">10001</span></span></td>
<td><span data-ttu-id="c12a3-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-192">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="c12a3-193">Unclassified</span></span></td>
<td><span data-ttu-id="c12a3-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-194">10,000.00</span></span></td>
<td><span data-ttu-id="c12a3-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="c12a3-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-196">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-196">CC099</span></span></td>
<td><span data-ttu-id="c12a3-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-197">Default cost center</span></span></td>
<td><span data-ttu-id="c12a3-198">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-198">10001</span></span></td>
<td><span data-ttu-id="c12a3-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-199">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="c12a3-200">Unclassified</span></span></td>
<td><span data-ttu-id="c12a3-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-201">-10,000.00</span></span></td>
<td><span data-ttu-id="c12a3-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-203">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-203">CC099</span></span></td>
<td><span data-ttu-id="c12a3-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-204">Default cost center</span></span></td>
<td><span data-ttu-id="c12a3-205">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-205">10001</span></span></td>
<td><span data-ttu-id="c12a3-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-206">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-207">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-208">1,000.00</span></span></td>
<td><span data-ttu-id="c12a3-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-210">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-210">CC099</span></span></td>
<td><span data-ttu-id="c12a3-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-211">Default cost center</span></span></td>
<td><span data-ttu-id="c12a3-212">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-212">10001</span></span></td>
<td><span data-ttu-id="c12a3-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-213">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-214">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-215">9,000.00</span></span></td>
<td><span data-ttu-id="c12a3-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-217">További információért lásd: [Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="c12a3-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="c12a3-218">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="c12a3-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="c12a3-219">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="c12a3-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="c12a3-220">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="c12a3-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="c12a3-221">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="c12a3-221">Define the cost distribution rule</span></span>

<span data-ttu-id="c12a3-222">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="c12a3-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="c12a3-223">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="c12a3-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="c12a3-224">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="c12a3-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="c12a3-225">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="c12a3-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="c12a3-226">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="c12a3-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="c12a3-227">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="c12a3-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-228">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-228">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="c12a3-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-230">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-230">CC001</span></span></td>
<td><span data-ttu-id="c12a3-231">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-231">HR</span></span></td>
<td><span data-ttu-id="c12a3-232">1000</span><span class="sxs-lookup"><span data-stu-id="c12a3-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-233">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-233">CC002</span></span></td>
<td><span data-ttu-id="c12a3-234">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-234">Finance</span></span></td>
<td><span data-ttu-id="c12a3-235">6,000</span><span class="sxs-lookup"><span data-stu-id="c12a3-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-236">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-236">CC003</span></span></td>
<td><span data-ttu-id="c12a3-237">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-237">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-238">0</span><span class="sxs-lookup"><span data-stu-id="c12a3-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-239">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c12a3-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-240">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-240">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-241">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c12a3-241">Magnitude</span></span></th>
<th><span data-ttu-id="c12a3-242">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c12a3-242">Allocation factor</span></span></th>
<th><span data-ttu-id="c12a3-243">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-244">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-244">CC001</span></span></td>
<td><span data-ttu-id="c12a3-245">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-245">HR</span></span></td>
<td><span data-ttu-id="c12a3-246">1000</span><span class="sxs-lookup"><span data-stu-id="c12a3-246">1,000</span></span></td>
<td><span data-ttu-id="c12a3-247">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c12a3-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c12a3-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-249">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-249">CC002</span></span></td>
<td><span data-ttu-id="c12a3-250">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-250">Finance</span></span></td>
<td><span data-ttu-id="c12a3-251">6,000</span><span class="sxs-lookup"><span data-stu-id="c12a3-251">6,000</span></span></td>
<td><span data-ttu-id="c12a3-252">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c12a3-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c12a3-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-254">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-254">CC003</span></span></td>
<td><span data-ttu-id="c12a3-255">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-255">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-256">0</span><span class="sxs-lookup"><span data-stu-id="c12a3-256">0</span></span></td>
<td><span data-ttu-id="c12a3-257">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c12a3-258">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-259">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="c12a3-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="c12a3-260">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: (Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c12a3-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-261">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-261">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-262">Receptúra</span><span class="sxs-lookup"><span data-stu-id="c12a3-262">Formula</span></span></th>
<th><span data-ttu-id="c12a3-263">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c12a3-263">Magnitude</span></span></th>
<th><span data-ttu-id="c12a3-264">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c12a3-264">Allocation factor</span></span></th>
<th><span data-ttu-id="c12a3-265">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-266">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-266">CC001</span></span></td>
<td><span data-ttu-id="c12a3-267">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-267">HR</span></span></td>
<td><span data-ttu-id="c12a3-268">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="c12a3-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c12a3-269">1</span><span class="sxs-lookup"><span data-stu-id="c12a3-269">1</span></span></td>
<td><span data-ttu-id="c12a3-270">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c12a3-271">500.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-272">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-272">CC002</span></span></td>
<td><span data-ttu-id="c12a3-273">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-273">Finance</span></span></td>
<td><span data-ttu-id="c12a3-274">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="c12a3-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c12a3-275">1</span><span class="sxs-lookup"><span data-stu-id="c12a3-275">1</span></span></td>
<td><span data-ttu-id="c12a3-276">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c12a3-277">500.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-278">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-278">CC003</span></span></td>
<td><span data-ttu-id="c12a3-279">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-279">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-280">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="c12a3-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c12a3-281">0</span><span class="sxs-lookup"><span data-stu-id="c12a3-281">0</span></span></td>
<td><span data-ttu-id="c12a3-282">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c12a3-283">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c12a3-284">Napló</span><span class="sxs-lookup"><span data-stu-id="c12a3-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c12a3-285">Napló</span><span class="sxs-lookup"><span data-stu-id="c12a3-285">Journal</span></span></th>
<th><span data-ttu-id="c12a3-286">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="c12a3-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c12a3-287">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c12a3-288">Verzió</span><span class="sxs-lookup"><span data-stu-id="c12a3-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-289">00002</span><span class="sxs-lookup"><span data-stu-id="c12a3-289">00002</span></span></td>
<td><span data-ttu-id="c12a3-290">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="c12a3-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="c12a3-291">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="c12a3-291">Fiscal</span></span></td>
<td><span data-ttu-id="c12a3-292">2017</span><span class="sxs-lookup"><span data-stu-id="c12a3-292">2017</span></span></td>
<td><span data-ttu-id="c12a3-293">1. időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-293">Period 1</span></span></td>
<td><span data-ttu-id="c12a3-294">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c12a3-295">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="c12a3-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c12a3-296">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c12a3-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-297">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-298">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c12a3-298">Cost element</span></span></th>
<th><span data-ttu-id="c12a3-299">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-299">Cost behavior</span></span></th>
<th><span data-ttu-id="c12a3-300">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-301">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-302">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-302">CC099</span></span></td>
<td><span data-ttu-id="c12a3-303">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-303">Default cost center</span></span></td>
<td><span data-ttu-id="c12a3-304">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-304">10001</span></span></td>
<td><span data-ttu-id="c12a3-305">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-305">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-306">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-306">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-308">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-309">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-309">CC099</span></span></td>
<td><span data-ttu-id="c12a3-310">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-310">Default cost center</span></span></td>
<td><span data-ttu-id="c12a3-311">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-311">10001</span></span></td>
<td><span data-ttu-id="c12a3-312">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-312">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-313">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-313">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c12a3-315">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="c12a3-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-316">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-317">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c12a3-317">Cost element</span></span></th>
<th><span data-ttu-id="c12a3-318">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-318">Cost behavior</span></span></th>
<th><span data-ttu-id="c12a3-319">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-319">Amount</span></span></th>
<th><span data-ttu-id="c12a3-320">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c12a3-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-321">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-321">CC099</span></span></td>
<td><span data-ttu-id="c12a3-322">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-322">Default cost center</span></span></td>
<td><span data-ttu-id="c12a3-323">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-323">10001</span></span></td>
<td><span data-ttu-id="c12a3-324">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-324">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-325">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-325">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-326">-1,000.00</span></span></td>
<td><span data-ttu-id="c12a3-327">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-328">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-328">CC001</span></span></td>
<td><span data-ttu-id="c12a3-329">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-329">HR</span></span></td>
<td><span data-ttu-id="c12a3-330">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-330">10001</span></span></td>
<td><span data-ttu-id="c12a3-331">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-331">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-332">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-332">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-333">500.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-333">500.00</span></span></td>
<td><span data-ttu-id="c12a3-334">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-335">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-335">CC002</span></span></td>
<td><span data-ttu-id="c12a3-336">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-336">Finance</span></span></td>
<td><span data-ttu-id="c12a3-337">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-337">10001</span></span></td>
<td><span data-ttu-id="c12a3-338">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-338">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-339">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-339">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-340">500.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-340">500.00</span></span></td>
<td><span data-ttu-id="c12a3-341">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-342">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-342">CC099</span></span></td>
<td><span data-ttu-id="c12a3-343">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c12a3-343">Default cost center</span></span></td>
<td><span data-ttu-id="c12a3-344">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-344">10001</span></span></td>
<td><span data-ttu-id="c12a3-345">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-345">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-346">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-346">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-347">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-347">-9,000.00</span></span></td>
<td><span data-ttu-id="c12a3-348">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-349">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-349">CC001</span></span></td>
<td><span data-ttu-id="c12a3-350">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-350">HR</span></span></td>
<td><span data-ttu-id="c12a3-351">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-351">10001</span></span></td>
<td><span data-ttu-id="c12a3-352">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-352">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-353">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-353">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c12a3-354">1,285.71</span></span></td>
<td><span data-ttu-id="c12a3-355">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-356">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-356">CC002</span></span></td>
<td><span data-ttu-id="c12a3-357">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-357">Finance</span></span></td>
<td><span data-ttu-id="c12a3-358">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-358">10001</span></span></td>
<td><span data-ttu-id="c12a3-359">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-359">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-360">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-360">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c12a3-361">7,714.29</span></span></td>
<td><span data-ttu-id="c12a3-362">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-363">További információért lásd: [Költségelosztási irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="c12a3-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="c12a3-364">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="c12a3-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="c12a3-365">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="c12a3-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="c12a3-366">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="c12a3-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="c12a3-367">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="c12a3-367">Define the overhead rate</span></span>

<span data-ttu-id="c12a3-368">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="c12a3-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="c12a3-369">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="c12a3-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-370">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-370">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-371">óra</span><span class="sxs-lookup"><span data-stu-id="c12a3-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-372">Proj 1</span></span></td>
<td><span data-ttu-id="c12a3-373">1. projekt</span><span class="sxs-lookup"><span data-stu-id="c12a3-373">Project 1</span></span></td>
<td><span data-ttu-id="c12a3-374">3</span><span class="sxs-lookup"><span data-stu-id="c12a3-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-375">Proj 2</span></span></td>
<td><span data-ttu-id="c12a3-376">2. projekt</span><span class="sxs-lookup"><span data-stu-id="c12a3-376">Project 2</span></span></td>
<td><span data-ttu-id="c12a3-377">1</span><span class="sxs-lookup"><span data-stu-id="c12a3-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-378">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="c12a3-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-379">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-379">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-380">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c12a3-380">Cost element</span></span></th>
<th><span data-ttu-id="c12a3-381">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-381">Cost behavior</span></span></th>
<th><span data-ttu-id="c12a3-382">Egységek</span><span class="sxs-lookup"><span data-stu-id="c12a3-382">Units</span></span></th>
<th><span data-ttu-id="c12a3-383">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="c12a3-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-384">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-384">CC001</span></span></td>
<td><span data-ttu-id="c12a3-385">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-385">HR</span></span></td>
<td><span data-ttu-id="c12a3-386">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-386">10001</span></span></td>
<td><span data-ttu-id="c12a3-387">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-387">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-388">1</span><span class="sxs-lookup"><span data-stu-id="c12a3-388">1</span></span></td>
<td><span data-ttu-id="c12a3-389">10</span><span class="sxs-lookup"><span data-stu-id="c12a3-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-390">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c12a3-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-391">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-391">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-392">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c12a3-392">Magnitude</span></span></th>
<th><span data-ttu-id="c12a3-393">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c12a3-393">Cost element</span></span></th>
<th><span data-ttu-id="c12a3-394">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c12a3-394">Allocation factor</span></span></th>
<th><span data-ttu-id="c12a3-395">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-396">Proj 1</span></span></td>
<td><span data-ttu-id="c12a3-397">1. projekt</span><span class="sxs-lookup"><span data-stu-id="c12a3-397">Project 1</span></span></td>
<td><span data-ttu-id="c12a3-398">3</span><span class="sxs-lookup"><span data-stu-id="c12a3-398">3</span></span></td>
<td><span data-ttu-id="c12a3-399">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-399">10001</span></span></td>
<td><span data-ttu-id="c12a3-400">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c12a3-401">30.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-402">Proj 2</span></span></td>
<td><span data-ttu-id="c12a3-403">2. projekt</span><span class="sxs-lookup"><span data-stu-id="c12a3-403">Project 2</span></span></td>
<td><span data-ttu-id="c12a3-404">1</span><span class="sxs-lookup"><span data-stu-id="c12a3-404">1</span></span></td>
<td><span data-ttu-id="c12a3-405">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-405">10001</span></span></td>
<td><span data-ttu-id="c12a3-406">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c12a3-407">10.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c12a3-408">Napló</span><span class="sxs-lookup"><span data-stu-id="c12a3-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c12a3-409">Napló</span><span class="sxs-lookup"><span data-stu-id="c12a3-409">Journal</span></span></th>
<th><span data-ttu-id="c12a3-410">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="c12a3-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c12a3-411">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c12a3-412">Verzió</span><span class="sxs-lookup"><span data-stu-id="c12a3-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-413">00003</span><span class="sxs-lookup"><span data-stu-id="c12a3-413">00003</span></span></td>
<td><span data-ttu-id="c12a3-414">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="c12a3-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="c12a3-415">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="c12a3-415">Fiscal</span></span></td>
<td><span data-ttu-id="c12a3-416">2017</span><span class="sxs-lookup"><span data-stu-id="c12a3-416">2017</span></span></td>
<td><span data-ttu-id="c12a3-417">1. időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-417">Period 1</span></span></td>
<td><span data-ttu-id="c12a3-418">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="c12a3-419">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="c12a3-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c12a3-420">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c12a3-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-421">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-421">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-422">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c12a3-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-423">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-424">Proj 1</span></span></td>
<td><span data-ttu-id="c12a3-425">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c12a3-426">3,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-427">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-428">Proj 2</span></span></td>
<td><span data-ttu-id="c12a3-429">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c12a3-430">1.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c12a3-431">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="c12a3-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-432">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-433">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c12a3-433">Cost element</span></span></th>
<th><span data-ttu-id="c12a3-434">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-434">Cost behavior</span></span></th>
<th><span data-ttu-id="c12a3-435">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-435">Amount</span></span></th>
<th><span data-ttu-id="c12a3-436">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c12a3-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="c12a3-437">CC0001</span></span></td>
<td><span data-ttu-id="c12a3-438">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-438">HR</span></span></td>
<td><span data-ttu-id="c12a3-439">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-439">10001</span></span></td>
<td><span data-ttu-id="c12a3-440">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-440">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-441">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-441">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-442">-30.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-442">-30.00</span></span></td>
<td><span data-ttu-id="c12a3-443">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-444">Proj 1</span></span></td>
<td><span data-ttu-id="c12a3-445">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c12a3-446">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-446">10001</span></span></td>
<td><span data-ttu-id="c12a3-447">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-447">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-448">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-448">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-449">30.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-449">30.00</span></span></td>
<td><span data-ttu-id="c12a3-450">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-451">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-451">CC001</span></span></td>
<td><span data-ttu-id="c12a3-452">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-452">HR</span></span></td>
<td><span data-ttu-id="c12a3-453">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-453">10001</span></span></td>
<td><span data-ttu-id="c12a3-454">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-454">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-455">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-455">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-456">-10.00</span></span></td>
<td><span data-ttu-id="c12a3-457">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-458">Proj 2</span></span></td>
<td><span data-ttu-id="c12a3-459">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c12a3-460">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-460">10001</span></span></td>
<td><span data-ttu-id="c12a3-461">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-461">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-462">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-462">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-463">10,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-463">10.00</span></span></td>
<td><span data-ttu-id="c12a3-464">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-465">További információ: [Járulékosköltség-számítás végrehajtása](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="c12a3-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="c12a3-466">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="c12a3-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="c12a3-467">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="c12a3-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="c12a3-468">A Finance a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="c12a3-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="c12a3-469">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="c12a3-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="c12a3-470">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="c12a3-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="c12a3-471">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="c12a3-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="c12a3-472">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="c12a3-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="c12a3-473">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="c12a3-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="c12a3-474">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="c12a3-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="c12a3-475">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="c12a3-475">Define the cost allocation</span></span>

<span data-ttu-id="c12a3-476">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="c12a3-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="c12a3-477">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="c12a3-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="c12a3-478">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="c12a3-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-479">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-479">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-480">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="c12a3-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-481">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-481">CC002</span></span></td>
<td><span data-ttu-id="c12a3-482">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-482">Finance</span></span></td>
<td><span data-ttu-id="c12a3-483">35</span><span class="sxs-lookup"><span data-stu-id="c12a3-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-484">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-484">CC003</span></span></td>
<td><span data-ttu-id="c12a3-485">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-485">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-486">55</span><span class="sxs-lookup"><span data-stu-id="c12a3-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-487">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-487">CC004</span></span></td>
<td><span data-ttu-id="c12a3-488">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-488">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-489">10</span><span class="sxs-lookup"><span data-stu-id="c12a3-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-490">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="c12a3-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="c12a3-491">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="c12a3-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-492">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-492">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-493">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="c12a3-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-494">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-494">CC003</span></span></td>
<td><span data-ttu-id="c12a3-495">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-495">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-496">65</span><span class="sxs-lookup"><span data-stu-id="c12a3-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-497">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-497">CC004</span></span></td>
<td><span data-ttu-id="c12a3-498">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-498">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-499">35</span><span class="sxs-lookup"><span data-stu-id="c12a3-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-500">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="c12a3-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="c12a3-501">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="c12a3-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-502">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-502">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-503">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="c12a3-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-504">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-504">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-505">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-505">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-506">60</span><span class="sxs-lookup"><span data-stu-id="c12a3-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-507">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-507">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-508">2. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-508">Product 2</span></span></td>
<td><span data-ttu-id="c12a3-509">20</span><span class="sxs-lookup"><span data-stu-id="c12a3-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-510">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="c12a3-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="c12a3-511">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="c12a3-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-512">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-512">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-513">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="c12a3-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-514">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-514">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-515">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-515">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-516">80</span><span class="sxs-lookup"><span data-stu-id="c12a3-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-517">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-517">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-518">2. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-518">Product 2</span></span></td>
<td><span data-ttu-id="c12a3-519">15</span><span class="sxs-lookup"><span data-stu-id="c12a3-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c12a3-520">A statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="c12a3-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="c12a3-521">További információk: [Statisztikaimérték-szolgáltató sablon](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="c12a3-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="c12a3-522">Az alábbi táblázat azt az eredményt mutatja, amikor a HR szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c12a3-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-523">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-523">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-524">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c12a3-524">Magnitude</span></span></th>
<th><span data-ttu-id="c12a3-525">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c12a3-525">Allocation factor</span></span></th>
<th><span data-ttu-id="c12a3-526">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-526">Amount</span></span></th>
<th><span data-ttu-id="c12a3-527">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-528">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-528">CC002</span></span></td>
<td><span data-ttu-id="c12a3-529">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-529">Finance</span></span></td>
<td><span data-ttu-id="c12a3-530">35</span><span class="sxs-lookup"><span data-stu-id="c12a3-530">35</span></span></td>
<td><span data-ttu-id="c12a3-531">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c12a3-532">175.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-532">175.00</span></span></td>
<td><span data-ttu-id="c12a3-533">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-534">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-534">CC003</span></span></td>
<td><span data-ttu-id="c12a3-535">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-535">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-536">55</span><span class="sxs-lookup"><span data-stu-id="c12a3-536">55</span></span></td>
<td><span data-ttu-id="c12a3-537">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c12a3-538">275.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-538">275.00</span></span></td>
<td><span data-ttu-id="c12a3-539">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-540">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-540">CC004</span></span></td>
<td><span data-ttu-id="c12a3-541">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-541">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-542">10</span><span class="sxs-lookup"><span data-stu-id="c12a3-542">10</span></span></td>
<td><span data-ttu-id="c12a3-543">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c12a3-544">50,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-544">50.00</span></span></td>
<td><span data-ttu-id="c12a3-545">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-546">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-546">CC002</span></span></td>
<td><span data-ttu-id="c12a3-547">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-547">Finance</span></span></td>
<td><span data-ttu-id="c12a3-548">35</span><span class="sxs-lookup"><span data-stu-id="c12a3-548">35</span></span></td>
<td><span data-ttu-id="c12a3-549">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="c12a3-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c12a3-550">436.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-550">436.00</span></span></td>
<td><span data-ttu-id="c12a3-551">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-552">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-552">CC003</span></span></td>
<td><span data-ttu-id="c12a3-553">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-553">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-554">55</span><span class="sxs-lookup"><span data-stu-id="c12a3-554">55</span></span></td>
<td><span data-ttu-id="c12a3-555">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="c12a3-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c12a3-556">685.14</span><span class="sxs-lookup"><span data-stu-id="c12a3-556">685.14</span></span></td>
<td><span data-ttu-id="c12a3-557">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-558">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-558">CC004</span></span></td>
<td><span data-ttu-id="c12a3-559">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-559">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-560">10</span><span class="sxs-lookup"><span data-stu-id="c12a3-560">10</span></span></td>
<td><span data-ttu-id="c12a3-561">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="c12a3-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c12a3-562">124.57</span><span class="sxs-lookup"><span data-stu-id="c12a3-562">124.57</span></span></td>
<td><span data-ttu-id="c12a3-563">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-564">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c12a3-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-565">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-565">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-566">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c12a3-566">Magnitude</span></span></th>
<th><span data-ttu-id="c12a3-567">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c12a3-567">Allocation factor</span></span></th>
<th><span data-ttu-id="c12a3-568">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-568">Amount</span></span></th>
<th><span data-ttu-id="c12a3-569">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-570">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-570">CC003</span></span></td>
<td><span data-ttu-id="c12a3-571">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-571">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-572">65</span><span class="sxs-lookup"><span data-stu-id="c12a3-572">65</span></span></td>
<td><span data-ttu-id="c12a3-573">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="c12a3-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c12a3-574">438.75</span><span class="sxs-lookup"><span data-stu-id="c12a3-574">438.75</span></span></td>
<td><span data-ttu-id="c12a3-575">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-576">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-576">CC004</span></span></td>
<td><span data-ttu-id="c12a3-577">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-577">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-578">35</span><span class="sxs-lookup"><span data-stu-id="c12a3-578">35</span></span></td>
<td><span data-ttu-id="c12a3-579">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="c12a3-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c12a3-580">236.25</span><span class="sxs-lookup"><span data-stu-id="c12a3-580">236.25</span></span></td>
<td><span data-ttu-id="c12a3-581">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-582">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-582">CC003</span></span></td>
<td><span data-ttu-id="c12a3-583">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-583">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-584">65</span><span class="sxs-lookup"><span data-stu-id="c12a3-584">65</span></span></td>
<td><span data-ttu-id="c12a3-585">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="c12a3-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c12a3-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c12a3-586">5,297.69</span></span></td>
<td><span data-ttu-id="c12a3-587">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-588">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-588">CC004</span></span></td>
<td><span data-ttu-id="c12a3-589">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-589">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-590">35</span><span class="sxs-lookup"><span data-stu-id="c12a3-590">35</span></span></td>
<td><span data-ttu-id="c12a3-591">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="c12a3-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c12a3-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c12a3-592">2,852.60</span></span></td>
<td><span data-ttu-id="c12a3-593">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-594">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c12a3-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-595">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-595">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-596">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c12a3-596">Magnitude</span></span></th>
<th><span data-ttu-id="c12a3-597">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c12a3-597">Allocation factor</span></span></th>
<th><span data-ttu-id="c12a3-598">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-598">Amount</span></span></th>
<th><span data-ttu-id="c12a3-599">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-600">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-600">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-601">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-601">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-602">60</span><span class="sxs-lookup"><span data-stu-id="c12a3-602">60</span></span></td>
<td><span data-ttu-id="c12a3-603">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="c12a3-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c12a3-604">535.31</span><span class="sxs-lookup"><span data-stu-id="c12a3-604">535.31</span></span></td>
<td><span data-ttu-id="c12a3-605">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-606">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-606">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-607">2. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-607">Product 2</span></span></td>
<td><span data-ttu-id="c12a3-608">20</span><span class="sxs-lookup"><span data-stu-id="c12a3-608">20</span></span></td>
<td><span data-ttu-id="c12a3-609">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="c12a3-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c12a3-610">178.44</span><span class="sxs-lookup"><span data-stu-id="c12a3-610">178.44</span></span></td>
<td><span data-ttu-id="c12a3-611">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-612">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-612">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-613">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-613">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-614">60</span><span class="sxs-lookup"><span data-stu-id="c12a3-614">60</span></span></td>
<td><span data-ttu-id="c12a3-615">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="c12a3-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c12a3-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c12a3-616">4,487.12</span></span></td>
<td><span data-ttu-id="c12a3-617">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-618">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-618">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-619">2. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-619">Product 2</span></span></td>
<td><span data-ttu-id="c12a3-620">20</span><span class="sxs-lookup"><span data-stu-id="c12a3-620">20</span></span></td>
<td><span data-ttu-id="c12a3-621">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="c12a3-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c12a3-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c12a3-622">1,495.71</span></span></td>
<td><span data-ttu-id="c12a3-623">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c12a3-624">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c12a3-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-625">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-625">Cost object</span></span></th>
<th><span data-ttu-id="c12a3-626">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c12a3-626">Magnitude</span></span></th>
<th><span data-ttu-id="c12a3-627">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c12a3-627">Allocation factor</span></span></th>
<th><span data-ttu-id="c12a3-628">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-628">Amount</span></span></th>
<th><span data-ttu-id="c12a3-629">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-630">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-630">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-631">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-631">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-632">80</span><span class="sxs-lookup"><span data-stu-id="c12a3-632">80</span></span></td>
<td><span data-ttu-id="c12a3-633">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="c12a3-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c12a3-634">241.05</span><span class="sxs-lookup"><span data-stu-id="c12a3-634">241.05</span></span></td>
<td><span data-ttu-id="c12a3-635">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-636">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-636">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-637">2. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-637">Product 2</span></span></td>
<td><span data-ttu-id="c12a3-638">15.</span><span class="sxs-lookup"><span data-stu-id="c12a3-638">15</span></span></td>
<td><span data-ttu-id="c12a3-639">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="c12a3-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c12a3-640">45.20</span><span class="sxs-lookup"><span data-stu-id="c12a3-640">45.20</span></span></td>
<td><span data-ttu-id="c12a3-641">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-642">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-642">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-643">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-643">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-644">80</span><span class="sxs-lookup"><span data-stu-id="c12a3-644">80</span></span></td>
<td><span data-ttu-id="c12a3-645">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="c12a3-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c12a3-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c12a3-646">2,507.09</span></span></td>
<td><span data-ttu-id="c12a3-647">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-648">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-648">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-649">2. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-649">Product 2</span></span></td>
<td><span data-ttu-id="c12a3-650">15.</span><span class="sxs-lookup"><span data-stu-id="c12a3-650">15</span></span></td>
<td><span data-ttu-id="c12a3-651">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="c12a3-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c12a3-652">470.08</span><span class="sxs-lookup"><span data-stu-id="c12a3-652">470.08</span></span></td>
<td><span data-ttu-id="c12a3-653">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c12a3-654">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="c12a3-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c12a3-655">Napló</span><span class="sxs-lookup"><span data-stu-id="c12a3-655">Journal</span></span></th>
<th><span data-ttu-id="c12a3-656">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="c12a3-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c12a3-657">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c12a3-658">Verzió</span><span class="sxs-lookup"><span data-stu-id="c12a3-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-659">00004</span><span class="sxs-lookup"><span data-stu-id="c12a3-659">00004</span></span></td>
<td><span data-ttu-id="c12a3-660">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="c12a3-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="c12a3-661">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="c12a3-661">Fiscal</span></span></td>
<td><span data-ttu-id="c12a3-662">2017</span><span class="sxs-lookup"><span data-stu-id="c12a3-662">2017</span></span></td>
<td><span data-ttu-id="c12a3-663">1. időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-663">Period 1</span></span></td>
<td><span data-ttu-id="c12a3-664">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="c12a3-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="c12a3-665">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="c12a3-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c12a3-666">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c12a3-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-667">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-668">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c12a3-668">Cost element</span></span></th>
<th><span data-ttu-id="c12a3-669">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-669">Cost behavior</span></span></th>
<th><span data-ttu-id="c12a3-670">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-671">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-672">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-672">CC001</span></span></td>
<td><span data-ttu-id="c12a3-673">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-673">HR</span></span></td>
<td><span data-ttu-id="c12a3-674">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-674">10001</span></span></td>
<td><span data-ttu-id="c12a3-675">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-675">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-676">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-676">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-677">500.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-678">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-679">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-679">CC001</span></span></td>
<td><span data-ttu-id="c12a3-680">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-680">HR</span></span></td>
<td><span data-ttu-id="c12a3-681">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-681">10001</span></span></td>
<td><span data-ttu-id="c12a3-682">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-682">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-683">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-683">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="c12a3-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-685">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-686">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-686">CC002</span></span></td>
<td><span data-ttu-id="c12a3-687">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-687">Finance</span></span></td>
<td><span data-ttu-id="c12a3-688">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-688">10001</span></span></td>
<td><span data-ttu-id="c12a3-689">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-689">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-690">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-690">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-691">675.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-692">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-693">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-693">CC002</span></span></td>
<td><span data-ttu-id="c12a3-694">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-694">Finance</span></span></td>
<td><span data-ttu-id="c12a3-695">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-695">10001</span></span></td>
<td><span data-ttu-id="c12a3-696">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-696">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-697">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-697">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="c12a3-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-699">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-700">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-700">CC003</span></span></td>
<td><span data-ttu-id="c12a3-701">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-701">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-702">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-702">10001</span></span></td>
<td><span data-ttu-id="c12a3-703">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-703">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-704">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-704">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-705">713.75</span><span class="sxs-lookup"><span data-stu-id="c12a3-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-706">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-707">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-707">CC003</span></span></td>
<td><span data-ttu-id="c12a3-708">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-708">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-709">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-709">10001</span></span></td>
<td><span data-ttu-id="c12a3-710">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-710">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-711">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-711">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="c12a3-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-713">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-714">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-714">CC003</span></span></td>
<td><span data-ttu-id="c12a3-715">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-715">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-716">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-716">10001</span></span></td>
<td><span data-ttu-id="c12a3-717">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-717">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-718">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-718">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-719">286.25</span><span class="sxs-lookup"><span data-stu-id="c12a3-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-720">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-721">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-721">CC003</span></span></td>
<td><span data-ttu-id="c12a3-722">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-722">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-723">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-723">10001</span></span></td>
<td><span data-ttu-id="c12a3-724">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-724">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-725">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-725">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="c12a3-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-727">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-728">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-728">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-729">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-729">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-730">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-730">10001</span></span></td>
<td><span data-ttu-id="c12a3-731">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-731">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-732">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-732">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-733">776.36</span><span class="sxs-lookup"><span data-stu-id="c12a3-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-734">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-735">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-735">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-736">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-736">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-737">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-737">10001</span></span></td>
<td><span data-ttu-id="c12a3-738">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-738">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-739">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-739">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c12a3-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-741">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-742">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-742">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-743">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-743">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-744">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-744">10001</span></span></td>
<td><span data-ttu-id="c12a3-745">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-745">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-746">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-746">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-747">223.64</span><span class="sxs-lookup"><span data-stu-id="c12a3-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-748">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="c12a3-749">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-749">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-750">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-750">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-751">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-751">10001</span></span></td>
<td><span data-ttu-id="c12a3-752">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-752">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-753">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-753">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c12a3-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c12a3-755">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="c12a3-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c12a3-756">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c12a3-757">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c12a3-757">Cost element</span></span></th>
<th><span data-ttu-id="c12a3-758">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c12a3-758">Cost behavior</span></span></th>
<th><span data-ttu-id="c12a3-759">Összeg</span><span class="sxs-lookup"><span data-stu-id="c12a3-759">Amount</span></span></th>
<th><span data-ttu-id="c12a3-760">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c12a3-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c12a3-761">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-761">CC001</span></span></td>
<td><span data-ttu-id="c12a3-762">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-762">HR</span></span></td>
<td><span data-ttu-id="c12a3-763">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-763">10001</span></span></td>
<td><span data-ttu-id="c12a3-764">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-764">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-765">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-765">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-766">-500.00</span></span></td>
<td><span data-ttu-id="c12a3-767">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-768">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-768">CC002</span></span></td>
<td><span data-ttu-id="c12a3-769">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-769">Finance</span></span></td>
<td><span data-ttu-id="c12a3-770">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-770">10001</span></span></td>
<td><span data-ttu-id="c12a3-771">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-771">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-772">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-772">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-773">175.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-773">175.00</span></span></td>
<td><span data-ttu-id="c12a3-774">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-775">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-775">CC003</span></span></td>
<td><span data-ttu-id="c12a3-776">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-776">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-777">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-777">10001</span></span></td>
<td><span data-ttu-id="c12a3-778">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-778">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-779">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-779">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-780">275.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-780">275.00</span></span></td>
<td><span data-ttu-id="c12a3-781">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-782">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-782">CC004</span></span></td>
<td><span data-ttu-id="c12a3-783">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-783">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-784">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-784">10001</span></span></td>
<td><span data-ttu-id="c12a3-785">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-785">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-786">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-786">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-787">50,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-787">50,00</span></span></td>
<td><span data-ttu-id="c12a3-788">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-789">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-789">CC001</span></span></td>
<td><span data-ttu-id="c12a3-790">HR</span><span class="sxs-lookup"><span data-stu-id="c12a3-790">HR</span></span></td>
<td><span data-ttu-id="c12a3-791">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-791">10001</span></span></td>
<td><span data-ttu-id="c12a3-792">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-792">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-793">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-793">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-794">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="c12a3-794">-1,245.71</span></span></td>
<td><span data-ttu-id="c12a3-795">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-796">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-796">CC002</span></span></td>
<td><span data-ttu-id="c12a3-797">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-797">Finance</span></span></td>
<td><span data-ttu-id="c12a3-798">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-798">10001</span></span></td>
<td><span data-ttu-id="c12a3-799">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-799">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-800">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-800">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-801">436.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-801">436.00</span></span></td>
<td><span data-ttu-id="c12a3-802">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-803">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-803">CC003</span></span></td>
<td><span data-ttu-id="c12a3-804">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-804">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-805">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-805">10001</span></span></td>
<td><span data-ttu-id="c12a3-806">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-806">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-807">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-807">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-808">685.14</span><span class="sxs-lookup"><span data-stu-id="c12a3-808">685.14</span></span></td>
<td><span data-ttu-id="c12a3-809">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-810">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-810">CC004</span></span></td>
<td><span data-ttu-id="c12a3-811">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-811">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-812">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-812">10001</span></span></td>
<td><span data-ttu-id="c12a3-813">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-813">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-814">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-814">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-815">124.57</span><span class="sxs-lookup"><span data-stu-id="c12a3-815">124.57</span></span></td>
<td><span data-ttu-id="c12a3-816">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-817">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-817">CC002</span></span></td>
<td><span data-ttu-id="c12a3-818">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-818">Finance</span></span></td>
<td><span data-ttu-id="c12a3-819">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-819">10001</span></span></td>
<td><span data-ttu-id="c12a3-820">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-820">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-821">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-821">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-822">-675.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-822">-675.00</span></span></td>
<td><span data-ttu-id="c12a3-823">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-824">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-824">CC003</span></span></td>
<td><span data-ttu-id="c12a3-825">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-825">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-826">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-826">10001</span></span></td>
<td><span data-ttu-id="c12a3-827">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-827">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-828">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-828">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-829">438.75</span><span class="sxs-lookup"><span data-stu-id="c12a3-829">438.75</span></span></td>
<td><span data-ttu-id="c12a3-830">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-831">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-831">CC004</span></span></td>
<td><span data-ttu-id="c12a3-832">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-832">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-833">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-833">10001</span></span></td>
<td><span data-ttu-id="c12a3-834">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-834">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-835">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-835">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-836">236.25</span><span class="sxs-lookup"><span data-stu-id="c12a3-836">236.25</span></span></td>
<td><span data-ttu-id="c12a3-837">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-838">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-838">CC002</span></span></td>
<td><span data-ttu-id="c12a3-839">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c12a3-839">Finance</span></span></td>
<td><span data-ttu-id="c12a3-840">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-840">10001</span></span></td>
<td><span data-ttu-id="c12a3-841">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-841">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-842">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-842">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-843">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="c12a3-843">-8,150.29</span></span></td>
<td><span data-ttu-id="c12a3-844">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-845">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-845">CC003</span></span></td>
<td><span data-ttu-id="c12a3-846">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-846">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-847">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-847">10001</span></span></td>
<td><span data-ttu-id="c12a3-848">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-848">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-849">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-849">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c12a3-850">5,297.69</span></span></td>
<td><span data-ttu-id="c12a3-851">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-852">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-852">CC004</span></span></td>
<td><span data-ttu-id="c12a3-853">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c12a3-853">Packaging</span></span></td>
<td><span data-ttu-id="c12a3-854">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-854">10001</span></span></td>
<td><span data-ttu-id="c12a3-855">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-855">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-856">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-856">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c12a3-857">2,852.60</span></span></td>
<td><span data-ttu-id="c12a3-858">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-859">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-859">CC003</span></span></td>
<td><span data-ttu-id="c12a3-860">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-860">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-861">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-861">10001</span></span></td>
<td><span data-ttu-id="c12a3-862">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-862">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-863">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-863">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-864">-713.75</span><span class="sxs-lookup"><span data-stu-id="c12a3-864">-713.75</span></span></td>
<td><span data-ttu-id="c12a3-865">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-866">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-866">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-867">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-867">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-868">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-868">10001</span></span></td>
<td><span data-ttu-id="c12a3-869">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-869">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-870">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-870">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-871">535.31</span><span class="sxs-lookup"><span data-stu-id="c12a3-871">535.31</span></span></td>
<td><span data-ttu-id="c12a3-872">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-873">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-873">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-874">2. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-874">Product 2</span></span></td>
<td><span data-ttu-id="c12a3-875">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-875">10001</span></span></td>
<td><span data-ttu-id="c12a3-876">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-876">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-877">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-877">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-878">178.44</span><span class="sxs-lookup"><span data-stu-id="c12a3-878">178.44</span></span></td>
<td><span data-ttu-id="c12a3-879">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-880">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-880">CC003</span></span></td>
<td><span data-ttu-id="c12a3-881">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-881">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-882">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-882">10001</span></span></td>
<td><span data-ttu-id="c12a3-883">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-883">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-884">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-884">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-885">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="c12a3-885">-5,982.83</span></span></td>
<td><span data-ttu-id="c12a3-886">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-887">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-887">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-888">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-888">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-889">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-889">10001</span></span></td>
<td><span data-ttu-id="c12a3-890">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-890">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-891">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-891">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c12a3-892">4,487.12</span></span></td>
<td><span data-ttu-id="c12a3-893">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-894">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-894">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-895">2. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-895">Product 2</span></span></td>
<td><span data-ttu-id="c12a3-896">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-896">10001</span></span></td>
<td><span data-ttu-id="c12a3-897">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-897">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-898">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-898">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c12a3-899">1,495.71</span></span></td>
<td><span data-ttu-id="c12a3-900">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-901">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-901">CC003</span></span></td>
<td><span data-ttu-id="c12a3-902">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-902">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-903">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-903">10001</span></span></td>
<td><span data-ttu-id="c12a3-904">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-904">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-905">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-905">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-906">-286.25</span><span class="sxs-lookup"><span data-stu-id="c12a3-906">-286.25</span></span></td>
<td><span data-ttu-id="c12a3-907">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-908">Term 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-908">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-909">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-909">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-910">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-910">10001</span></span></td>
<td><span data-ttu-id="c12a3-911">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-911">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-912">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-912">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-913">241.05</span><span class="sxs-lookup"><span data-stu-id="c12a3-913">241.05</span></span></td>
<td><span data-ttu-id="c12a3-914">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-915">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-915">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-916">2. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-916">Product 2</span></span></td>
<td><span data-ttu-id="c12a3-917">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-917">10001</span></span></td>
<td><span data-ttu-id="c12a3-918">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-918">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-919">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-919">Fixed cost</span></span></td>
<td><span data-ttu-id="c12a3-920">45.20</span><span class="sxs-lookup"><span data-stu-id="c12a3-920">45.20</span></span></td>
<td><span data-ttu-id="c12a3-921">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-922">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-922">CC003</span></span></td>
<td><span data-ttu-id="c12a3-923">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c12a3-923">Assembly</span></span></td>
<td><span data-ttu-id="c12a3-924">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-924">10001</span></span></td>
<td><span data-ttu-id="c12a3-925">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-925">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-926">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-926">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-927">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="c12a3-927">-2,977.17</span></span></td>
<td><span data-ttu-id="c12a3-928">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-929">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-929">Prod 1</span></span></td>
<td><span data-ttu-id="c12a3-930">1. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-930">Product 1</span></span></td>
<td><span data-ttu-id="c12a3-931">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-931">10001</span></span></td>
<td><span data-ttu-id="c12a3-932">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-932">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-933">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-933">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c12a3-934">2,507.09</span></span></td>
<td><span data-ttu-id="c12a3-935">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c12a3-936">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-936">Prod 2</span></span></td>
<td><span data-ttu-id="c12a3-937">2. termék</span><span class="sxs-lookup"><span data-stu-id="c12a3-937">Product 2</span></span></td>
<td><span data-ttu-id="c12a3-938">10001</span><span class="sxs-lookup"><span data-stu-id="c12a3-938">10001</span></span></td>
<td><span data-ttu-id="c12a3-939">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-939">Electricity</span></span></td>
<td><span data-ttu-id="c12a3-940">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-940">Variable cost</span></span></td>
<td><span data-ttu-id="c12a3-941">470.08</span><span class="sxs-lookup"><span data-stu-id="c12a3-941">470.08</span></span></td>
<td><span data-ttu-id="c12a3-942">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c12a3-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="c12a3-943">Következtetés</span><span class="sxs-lookup"><span data-stu-id="c12a3-943">Conclusion</span></span>
<span data-ttu-id="c12a3-944">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="c12a3-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="c12a3-945">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="c12a3-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="c12a3-946">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="c12a3-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="c12a3-947">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="c12a3-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="c12a3-948">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c12a3-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="c12a3-949">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c12a3-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="c12a3-950">Összesen</span><span class="sxs-lookup"><span data-stu-id="c12a3-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c12a3-951">CC099</span><span class="sxs-lookup"><span data-stu-id="c12a3-951">CC099</span></span></th>
<th><span data-ttu-id="c12a3-952">CC001</span><span class="sxs-lookup"><span data-stu-id="c12a3-952">CC001</span></span></th>
<th><span data-ttu-id="c12a3-953">CC002</span><span class="sxs-lookup"><span data-stu-id="c12a3-953">CC002</span></span></th>
<th><span data-ttu-id="c12a3-954">CC003</span><span class="sxs-lookup"><span data-stu-id="c12a3-954">CC003</span></span></th>
<th><span data-ttu-id="c12a3-955">CC004</span><span class="sxs-lookup"><span data-stu-id="c12a3-955">CC004</span></span></th>
<th><span data-ttu-id="c12a3-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-956">Proj 1</span></span></th>
<th><span data-ttu-id="c12a3-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-957">Proj 2</span></span></th>
<th><span data-ttu-id="c12a3-958">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c12a3-958">Prod 1</span></span></th>
<th><span data-ttu-id="c12a3-959">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c12a3-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="c12a3-960">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c12a3-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="c12a3-970">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="c12a3-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-971">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-971">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="c12a3-972">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-973">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-974">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-975">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-976">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-977">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-978">776.36</span><span class="sxs-lookup"><span data-stu-id="c12a3-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-979">223.64</span><span class="sxs-lookup"><span data-stu-id="c12a3-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="c12a3-981">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c12a3-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-982">000</span><span class="sxs-lookup"><span data-stu-id="c12a3-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-983">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-984">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-985">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-986">0,00</span><span class="sxs-lookup"><span data-stu-id="c12a3-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-987">30.00</span><span class="sxs-lookup"><span data-stu-id="c12a3-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-988">1000</span><span class="sxs-lookup"><span data-stu-id="c12a3-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c12a3-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c12a3-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c12a3-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="c12a3-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c12a3-992">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="c12a3-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="c12a3-993">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="c12a3-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="c12a3-994">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="c12a3-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="c12a3-995">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="c12a3-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="c12a3-996">A további tudnivalókat lásd: [Költségösszesítéssel kapcsolatos irányelv és járulékos költség számítása](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="c12a3-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]