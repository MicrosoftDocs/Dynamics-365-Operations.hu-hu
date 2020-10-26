---
title: Járulékos költség számítása
description: Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 923e6e38a664e17ec3349d839c4b77ec903c5dc2
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976475"
---
# <a name="overhead-calculation"></a><span data-ttu-id="d853f-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="d853f-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d853f-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="d853f-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="d853f-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="d853f-105">Term definition</span></span>
---------------

<span data-ttu-id="d853f-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="d853f-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="d853f-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="d853f-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="d853f-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="d853f-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="d853f-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="d853f-109">Rent</span></span>
-   <span data-ttu-id="d853f-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-110">Electricity</span></span>
-   <span data-ttu-id="d853f-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="d853f-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="d853f-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="d853f-112">Overhead calculation overview</span></span>
<span data-ttu-id="d853f-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="d853f-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="d853f-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="d853f-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="d853f-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="d853f-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="d853f-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="d853f-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="d853f-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="d853f-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="d853f-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="d853f-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="d853f-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="d853f-119">Version type</span></span>
-   <span data-ttu-id="d853f-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="d853f-120">Date and time</span></span>
-   <span data-ttu-id="d853f-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="d853f-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="d853f-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="d853f-122">Fiscal year</span></span>
-   <span data-ttu-id="d853f-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-123">Fiscal period</span></span>

<span data-ttu-id="d853f-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="d853f-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="d853f-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="d853f-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="d853f-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="d853f-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="d853f-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="d853f-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="d853f-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="d853f-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="d853f-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="d853f-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="d853f-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="d853f-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="d853f-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="d853f-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="d853f-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="d853f-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="d853f-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="d853f-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="d853f-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="d853f-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="d853f-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="d853f-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="d853f-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="d853f-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="d853f-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="d853f-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d853f-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="d853f-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="d853f-140">Main account</span></span></th>
<th><span data-ttu-id="d853f-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="d853f-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="d853f-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="d853f-143">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-143">CC099</span></span></td>
<td><span data-ttu-id="d853f-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-144">Default cost center</span></span></td>
<td><span data-ttu-id="d853f-145">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-145">10001</span></span></td>
<td><span data-ttu-id="d853f-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-146">Electricity</span></span></td>
<td><span data-ttu-id="d853f-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="d853f-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="d853f-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="d853f-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="d853f-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="d853f-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="d853f-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost** .</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="d853f-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="d853f-151">Define the cost behavior rule</span></span>

<span data-ttu-id="d853f-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="d853f-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="d853f-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="d853f-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="d853f-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="d853f-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="d853f-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="d853f-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="d853f-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="d853f-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="d853f-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="d853f-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="d853f-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="d853f-159">Napló</span><span class="sxs-lookup"><span data-stu-id="d853f-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d853f-160">Napló</span><span class="sxs-lookup"><span data-stu-id="d853f-160">Journal</span></span></th>
<th><span data-ttu-id="d853f-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="d853f-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d853f-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d853f-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="d853f-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-164">00001</span><span class="sxs-lookup"><span data-stu-id="d853f-164">00001</span></span></td>
<td><span data-ttu-id="d853f-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="d853f-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="d853f-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="d853f-166">Fiscal</span></span></td>
<td><span data-ttu-id="d853f-167">2017</span><span class="sxs-lookup"><span data-stu-id="d853f-167">2017</span></span></td>
<td><span data-ttu-id="d853f-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-168">Period 1</span></span></td>
<td><span data-ttu-id="d853f-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d853f-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="d853f-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d853f-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="d853f-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="d853f-173">Cost element</span></span></th>
<th><span data-ttu-id="d853f-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-174">Cost behavior</span></span></th>
<th><span data-ttu-id="d853f-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="d853f-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="d853f-177">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-177">CC099</span></span></td>
<td><span data-ttu-id="d853f-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-178">Default cost center</span></span></td>
<td><span data-ttu-id="d853f-179">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-179">10001</span></span></td>
<td><span data-ttu-id="d853f-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-180">Electricity</span></span></td>
<td><span data-ttu-id="d853f-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="d853f-181">Unclassified</span></span></td>
<td><span data-ttu-id="d853f-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d853f-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="d853f-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="d853f-185">Cost element</span></span></th>
<th><span data-ttu-id="d853f-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-186">Cost behavior</span></span></th>
<th><span data-ttu-id="d853f-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-187">Amount</span></span></th>
<th><span data-ttu-id="d853f-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="d853f-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-189">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-189">CC099</span></span></td>
<td><span data-ttu-id="d853f-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-190">Default cost center</span></span></td>
<td><span data-ttu-id="d853f-191">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-191">10001</span></span></td>
<td><span data-ttu-id="d853f-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-192">Electricity</span></span></td>
<td><span data-ttu-id="d853f-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="d853f-193">Unclassified</span></span></td>
<td><span data-ttu-id="d853f-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-194">10,000.00</span></span></td>
<td><span data-ttu-id="d853f-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="d853f-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-196">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-196">CC099</span></span></td>
<td><span data-ttu-id="d853f-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-197">Default cost center</span></span></td>
<td><span data-ttu-id="d853f-198">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-198">10001</span></span></td>
<td><span data-ttu-id="d853f-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-199">Electricity</span></span></td>
<td><span data-ttu-id="d853f-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="d853f-200">Unclassified</span></span></td>
<td><span data-ttu-id="d853f-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-201">-10,000.00</span></span></td>
<td><span data-ttu-id="d853f-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-203">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-203">CC099</span></span></td>
<td><span data-ttu-id="d853f-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-204">Default cost center</span></span></td>
<td><span data-ttu-id="d853f-205">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-205">10001</span></span></td>
<td><span data-ttu-id="d853f-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-206">Electricity</span></span></td>
<td><span data-ttu-id="d853f-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-207">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="d853f-208">1,000.00</span></span></td>
<td><span data-ttu-id="d853f-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-210">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-210">CC099</span></span></td>
<td><span data-ttu-id="d853f-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-211">Default cost center</span></span></td>
<td><span data-ttu-id="d853f-212">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-212">10001</span></span></td>
<td><span data-ttu-id="d853f-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-213">Electricity</span></span></td>
<td><span data-ttu-id="d853f-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-214">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-215">9,000.00</span></span></td>
<td><span data-ttu-id="d853f-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-217">További információért lásd: [Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="d853f-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="d853f-218">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="d853f-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="d853f-219">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="d853f-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="d853f-220">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="d853f-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="d853f-221">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="d853f-221">Define the cost distribution rule</span></span>

<span data-ttu-id="d853f-222">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="d853f-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="d853f-223">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="d853f-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="d853f-224">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="d853f-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="d853f-225">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="d853f-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="d853f-226">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="d853f-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="d853f-227">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="d853f-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-228">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-228">Cost object</span></span></th>
<th><span data-ttu-id="d853f-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="d853f-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-230">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-230">CC001</span></span></td>
<td><span data-ttu-id="d853f-231">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-231">HR</span></span></td>
<td><span data-ttu-id="d853f-232">1000</span><span class="sxs-lookup"><span data-stu-id="d853f-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-233">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-233">CC002</span></span></td>
<td><span data-ttu-id="d853f-234">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-234">Finance</span></span></td>
<td><span data-ttu-id="d853f-235">6,000</span><span class="sxs-lookup"><span data-stu-id="d853f-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-236">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-236">CC003</span></span></td>
<td><span data-ttu-id="d853f-237">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-237">Assembly</span></span></td>
<td><span data-ttu-id="d853f-238">0</span><span class="sxs-lookup"><span data-stu-id="d853f-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-239">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="d853f-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-240">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-240">Cost object</span></span></th>
<th><span data-ttu-id="d853f-241">Nagyság</span><span class="sxs-lookup"><span data-stu-id="d853f-241">Magnitude</span></span></th>
<th><span data-ttu-id="d853f-242">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="d853f-242">Allocation factor</span></span></th>
<th><span data-ttu-id="d853f-243">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-244">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-244">CC001</span></span></td>
<td><span data-ttu-id="d853f-245">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-245">HR</span></span></td>
<td><span data-ttu-id="d853f-246">1000</span><span class="sxs-lookup"><span data-stu-id="d853f-246">1,000</span></span></td>
<td><span data-ttu-id="d853f-247">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d853f-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="d853f-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-249">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-249">CC002</span></span></td>
<td><span data-ttu-id="d853f-250">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-250">Finance</span></span></td>
<td><span data-ttu-id="d853f-251">6,000</span><span class="sxs-lookup"><span data-stu-id="d853f-251">6,000</span></span></td>
<td><span data-ttu-id="d853f-252">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d853f-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="d853f-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-254">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-254">CC003</span></span></td>
<td><span data-ttu-id="d853f-255">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-255">Assembly</span></span></td>
<td><span data-ttu-id="d853f-256">0</span><span class="sxs-lookup"><span data-stu-id="d853f-256">0</span></span></td>
<td><span data-ttu-id="d853f-257">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="d853f-258">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-259">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="d853f-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="d853f-260">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: (Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="d853f-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-261">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-261">Cost object</span></span></th>
<th><span data-ttu-id="d853f-262">Receptúra</span><span class="sxs-lookup"><span data-stu-id="d853f-262">Formula</span></span></th>
<th><span data-ttu-id="d853f-263">Nagyság</span><span class="sxs-lookup"><span data-stu-id="d853f-263">Magnitude</span></span></th>
<th><span data-ttu-id="d853f-264">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="d853f-264">Allocation factor</span></span></th>
<th><span data-ttu-id="d853f-265">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-266">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-266">CC001</span></span></td>
<td><span data-ttu-id="d853f-267">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-267">HR</span></span></td>
<td><span data-ttu-id="d853f-268">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="d853f-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d853f-269">1</span><span class="sxs-lookup"><span data-stu-id="d853f-269">1</span></span></td>
<td><span data-ttu-id="d853f-270">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d853f-271">500.00</span><span class="sxs-lookup"><span data-stu-id="d853f-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-272">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-272">CC002</span></span></td>
<td><span data-ttu-id="d853f-273">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-273">Finance</span></span></td>
<td><span data-ttu-id="d853f-274">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="d853f-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d853f-275">1</span><span class="sxs-lookup"><span data-stu-id="d853f-275">1</span></span></td>
<td><span data-ttu-id="d853f-276">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d853f-277">500.00</span><span class="sxs-lookup"><span data-stu-id="d853f-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-278">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-278">CC003</span></span></td>
<td><span data-ttu-id="d853f-279">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-279">Assembly</span></span></td>
<td><span data-ttu-id="d853f-280">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="d853f-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="d853f-281">0</span><span class="sxs-lookup"><span data-stu-id="d853f-281">0</span></span></td>
<td><span data-ttu-id="d853f-282">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="d853f-283">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="d853f-284">Napló</span><span class="sxs-lookup"><span data-stu-id="d853f-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d853f-285">Napló</span><span class="sxs-lookup"><span data-stu-id="d853f-285">Journal</span></span></th>
<th><span data-ttu-id="d853f-286">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="d853f-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d853f-287">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d853f-288">Verzió</span><span class="sxs-lookup"><span data-stu-id="d853f-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-289">00002</span><span class="sxs-lookup"><span data-stu-id="d853f-289">00002</span></span></td>
<td><span data-ttu-id="d853f-290">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="d853f-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="d853f-291">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="d853f-291">Fiscal</span></span></td>
<td><span data-ttu-id="d853f-292">2017</span><span class="sxs-lookup"><span data-stu-id="d853f-292">2017</span></span></td>
<td><span data-ttu-id="d853f-293">1. időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-293">Period 1</span></span></td>
<td><span data-ttu-id="d853f-294">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d853f-295">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="d853f-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d853f-296">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="d853f-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-297">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-298">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="d853f-298">Cost element</span></span></th>
<th><span data-ttu-id="d853f-299">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-299">Cost behavior</span></span></th>
<th><span data-ttu-id="d853f-300">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-301">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-302">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-302">CC099</span></span></td>
<td><span data-ttu-id="d853f-303">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-303">Default cost center</span></span></td>
<td><span data-ttu-id="d853f-304">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-304">10001</span></span></td>
<td><span data-ttu-id="d853f-305">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-305">Electricity</span></span></td>
<td><span data-ttu-id="d853f-306">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-306">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="d853f-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-308">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-309">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-309">CC099</span></span></td>
<td><span data-ttu-id="d853f-310">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-310">Default cost center</span></span></td>
<td><span data-ttu-id="d853f-311">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-311">10001</span></span></td>
<td><span data-ttu-id="d853f-312">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-312">Electricity</span></span></td>
<td><span data-ttu-id="d853f-313">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-313">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d853f-315">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="d853f-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-316">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-317">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="d853f-317">Cost element</span></span></th>
<th><span data-ttu-id="d853f-318">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-318">Cost behavior</span></span></th>
<th><span data-ttu-id="d853f-319">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-319">Amount</span></span></th>
<th><span data-ttu-id="d853f-320">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="d853f-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-321">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-321">CC099</span></span></td>
<td><span data-ttu-id="d853f-322">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-322">Default cost center</span></span></td>
<td><span data-ttu-id="d853f-323">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-323">10001</span></span></td>
<td><span data-ttu-id="d853f-324">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-324">Electricity</span></span></td>
<td><span data-ttu-id="d853f-325">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-325">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="d853f-326">-1,000.00</span></span></td>
<td><span data-ttu-id="d853f-327">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-328">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-328">CC001</span></span></td>
<td><span data-ttu-id="d853f-329">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-329">HR</span></span></td>
<td><span data-ttu-id="d853f-330">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-330">10001</span></span></td>
<td><span data-ttu-id="d853f-331">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-331">Electricity</span></span></td>
<td><span data-ttu-id="d853f-332">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-332">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-333">500.00</span><span class="sxs-lookup"><span data-stu-id="d853f-333">500.00</span></span></td>
<td><span data-ttu-id="d853f-334">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-335">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-335">CC002</span></span></td>
<td><span data-ttu-id="d853f-336">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-336">Finance</span></span></td>
<td><span data-ttu-id="d853f-337">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-337">10001</span></span></td>
<td><span data-ttu-id="d853f-338">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-338">Electricity</span></span></td>
<td><span data-ttu-id="d853f-339">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-339">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-340">500.00</span><span class="sxs-lookup"><span data-stu-id="d853f-340">500.00</span></span></td>
<td><span data-ttu-id="d853f-341">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-342">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-342">CC099</span></span></td>
<td><span data-ttu-id="d853f-343">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="d853f-343">Default cost center</span></span></td>
<td><span data-ttu-id="d853f-344">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-344">10001</span></span></td>
<td><span data-ttu-id="d853f-345">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-345">Electricity</span></span></td>
<td><span data-ttu-id="d853f-346">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-346">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-347">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="d853f-347">-9,000.00</span></span></td>
<td><span data-ttu-id="d853f-348">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-349">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-349">CC001</span></span></td>
<td><span data-ttu-id="d853f-350">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-350">HR</span></span></td>
<td><span data-ttu-id="d853f-351">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-351">10001</span></span></td>
<td><span data-ttu-id="d853f-352">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-352">Electricity</span></span></td>
<td><span data-ttu-id="d853f-353">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-353">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="d853f-354">1,285.71</span></span></td>
<td><span data-ttu-id="d853f-355">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-356">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-356">CC002</span></span></td>
<td><span data-ttu-id="d853f-357">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-357">Finance</span></span></td>
<td><span data-ttu-id="d853f-358">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-358">10001</span></span></td>
<td><span data-ttu-id="d853f-359">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-359">Electricity</span></span></td>
<td><span data-ttu-id="d853f-360">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-360">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="d853f-361">7,714.29</span></span></td>
<td><span data-ttu-id="d853f-362">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-363">További információért lásd: [Költségelosztási irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="d853f-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="d853f-364">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="d853f-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="d853f-365">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="d853f-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="d853f-366">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="d853f-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="d853f-367">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="d853f-367">Define the overhead rate</span></span>

<span data-ttu-id="d853f-368">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="d853f-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="d853f-369">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="d853f-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-370">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-370">Cost object</span></span></th>
<th><span data-ttu-id="d853f-371">óra</span><span class="sxs-lookup"><span data-stu-id="d853f-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d853f-372">Proj 1</span></span></td>
<td><span data-ttu-id="d853f-373">1. projekt</span><span class="sxs-lookup"><span data-stu-id="d853f-373">Project 1</span></span></td>
<td><span data-ttu-id="d853f-374">3</span><span class="sxs-lookup"><span data-stu-id="d853f-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d853f-375">Proj 2</span></span></td>
<td><span data-ttu-id="d853f-376">2. projekt</span><span class="sxs-lookup"><span data-stu-id="d853f-376">Project 2</span></span></td>
<td><span data-ttu-id="d853f-377">1</span><span class="sxs-lookup"><span data-stu-id="d853f-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-378">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="d853f-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-379">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-379">Cost object</span></span></th>
<th><span data-ttu-id="d853f-380">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="d853f-380">Cost element</span></span></th>
<th><span data-ttu-id="d853f-381">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-381">Cost behavior</span></span></th>
<th><span data-ttu-id="d853f-382">Egységek</span><span class="sxs-lookup"><span data-stu-id="d853f-382">Units</span></span></th>
<th><span data-ttu-id="d853f-383">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="d853f-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-384">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-384">CC001</span></span></td>
<td><span data-ttu-id="d853f-385">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-385">HR</span></span></td>
<td><span data-ttu-id="d853f-386">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-386">10001</span></span></td>
<td><span data-ttu-id="d853f-387">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-387">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-388">1</span><span class="sxs-lookup"><span data-stu-id="d853f-388">1</span></span></td>
<td><span data-ttu-id="d853f-389">10</span><span class="sxs-lookup"><span data-stu-id="d853f-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-390">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="d853f-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-391">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-391">Cost object</span></span></th>
<th><span data-ttu-id="d853f-392">Nagyság</span><span class="sxs-lookup"><span data-stu-id="d853f-392">Magnitude</span></span></th>
<th><span data-ttu-id="d853f-393">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="d853f-393">Cost element</span></span></th>
<th><span data-ttu-id="d853f-394">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="d853f-394">Allocation factor</span></span></th>
<th><span data-ttu-id="d853f-395">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d853f-396">Proj 1</span></span></td>
<td><span data-ttu-id="d853f-397">1. projekt</span><span class="sxs-lookup"><span data-stu-id="d853f-397">Project 1</span></span></td>
<td><span data-ttu-id="d853f-398">3</span><span class="sxs-lookup"><span data-stu-id="d853f-398">3</span></span></td>
<td><span data-ttu-id="d853f-399">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-399">10001</span></span></td>
<td><span data-ttu-id="d853f-400">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="d853f-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="d853f-401">30.00</span><span class="sxs-lookup"><span data-stu-id="d853f-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d853f-402">Proj 2</span></span></td>
<td><span data-ttu-id="d853f-403">2. projekt</span><span class="sxs-lookup"><span data-stu-id="d853f-403">Project 2</span></span></td>
<td><span data-ttu-id="d853f-404">1</span><span class="sxs-lookup"><span data-stu-id="d853f-404">1</span></span></td>
<td><span data-ttu-id="d853f-405">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-405">10001</span></span></td>
<td><span data-ttu-id="d853f-406">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="d853f-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="d853f-407">10.00</span><span class="sxs-lookup"><span data-stu-id="d853f-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="d853f-408">Napló</span><span class="sxs-lookup"><span data-stu-id="d853f-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d853f-409">Napló</span><span class="sxs-lookup"><span data-stu-id="d853f-409">Journal</span></span></th>
<th><span data-ttu-id="d853f-410">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="d853f-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d853f-411">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d853f-412">Verzió</span><span class="sxs-lookup"><span data-stu-id="d853f-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-413">00003</span><span class="sxs-lookup"><span data-stu-id="d853f-413">00003</span></span></td>
<td><span data-ttu-id="d853f-414">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="d853f-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="d853f-415">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="d853f-415">Fiscal</span></span></td>
<td><span data-ttu-id="d853f-416">2017</span><span class="sxs-lookup"><span data-stu-id="d853f-416">2017</span></span></td>
<td><span data-ttu-id="d853f-417">1. időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-417">Period 1</span></span></td>
<td><span data-ttu-id="d853f-418">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="d853f-419">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="d853f-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d853f-420">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="d853f-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-421">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-421">Cost object</span></span></th>
<th><span data-ttu-id="d853f-422">Nagyság</span><span class="sxs-lookup"><span data-stu-id="d853f-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-423">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d853f-424">Proj 1</span></span></td>
<td><span data-ttu-id="d853f-425">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="d853f-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="d853f-426">3,00</span><span class="sxs-lookup"><span data-stu-id="d853f-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-427">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d853f-428">Proj 2</span></span></td>
<td><span data-ttu-id="d853f-429">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="d853f-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="d853f-430">1.00</span><span class="sxs-lookup"><span data-stu-id="d853f-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d853f-431">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="d853f-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-432">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-433">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="d853f-433">Cost element</span></span></th>
<th><span data-ttu-id="d853f-434">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-434">Cost behavior</span></span></th>
<th><span data-ttu-id="d853f-435">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-435">Amount</span></span></th>
<th><span data-ttu-id="d853f-436">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="d853f-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="d853f-437">CC0001</span></span></td>
<td><span data-ttu-id="d853f-438">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-438">HR</span></span></td>
<td><span data-ttu-id="d853f-439">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-439">10001</span></span></td>
<td><span data-ttu-id="d853f-440">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-440">Electricity</span></span></td>
<td><span data-ttu-id="d853f-441">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-441">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-442">-30.00</span><span class="sxs-lookup"><span data-stu-id="d853f-442">-30.00</span></span></td>
<td><span data-ttu-id="d853f-443">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d853f-444">Proj 1</span></span></td>
<td><span data-ttu-id="d853f-445">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="d853f-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="d853f-446">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-446">10001</span></span></td>
<td><span data-ttu-id="d853f-447">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-447">Electricity</span></span></td>
<td><span data-ttu-id="d853f-448">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-448">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-449">30.00</span><span class="sxs-lookup"><span data-stu-id="d853f-449">30.00</span></span></td>
<td><span data-ttu-id="d853f-450">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-451">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-451">CC001</span></span></td>
<td><span data-ttu-id="d853f-452">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-452">HR</span></span></td>
<td><span data-ttu-id="d853f-453">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-453">10001</span></span></td>
<td><span data-ttu-id="d853f-454">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-454">Electricity</span></span></td>
<td><span data-ttu-id="d853f-455">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-455">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="d853f-456">-10.00</span></span></td>
<td><span data-ttu-id="d853f-457">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d853f-458">Proj 2</span></span></td>
<td><span data-ttu-id="d853f-459">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="d853f-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="d853f-460">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-460">10001</span></span></td>
<td><span data-ttu-id="d853f-461">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-461">Electricity</span></span></td>
<td><span data-ttu-id="d853f-462">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-462">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-463">10,00</span><span class="sxs-lookup"><span data-stu-id="d853f-463">10.00</span></span></td>
<td><span data-ttu-id="d853f-464">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-465">További információ: [Járulékosköltség-számítás végrehajtása](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="d853f-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="d853f-466">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="d853f-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="d853f-467">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="d853f-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="d853f-468">A Finance a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="d853f-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="d853f-469">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="d853f-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="d853f-470">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="d853f-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="d853f-471">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="d853f-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="d853f-472">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="d853f-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="d853f-473">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="d853f-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="d853f-474">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="d853f-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="d853f-475">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="d853f-475">Define the cost allocation</span></span>

<span data-ttu-id="d853f-476">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="d853f-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="d853f-477">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="d853f-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="d853f-478">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="d853f-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-479">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-479">Cost object</span></span></th>
<th><span data-ttu-id="d853f-480">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="d853f-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-481">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-481">CC002</span></span></td>
<td><span data-ttu-id="d853f-482">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-482">Finance</span></span></td>
<td><span data-ttu-id="d853f-483">35</span><span class="sxs-lookup"><span data-stu-id="d853f-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-484">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-484">CC003</span></span></td>
<td><span data-ttu-id="d853f-485">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-485">Assembly</span></span></td>
<td><span data-ttu-id="d853f-486">55</span><span class="sxs-lookup"><span data-stu-id="d853f-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-487">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-487">CC004</span></span></td>
<td><span data-ttu-id="d853f-488">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-488">Packaging</span></span></td>
<td><span data-ttu-id="d853f-489">10</span><span class="sxs-lookup"><span data-stu-id="d853f-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-490">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="d853f-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="d853f-491">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="d853f-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-492">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-492">Cost object</span></span></th>
<th><span data-ttu-id="d853f-493">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="d853f-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-494">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-494">CC003</span></span></td>
<td><span data-ttu-id="d853f-495">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-495">Assembly</span></span></td>
<td><span data-ttu-id="d853f-496">65</span><span class="sxs-lookup"><span data-stu-id="d853f-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-497">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-497">CC004</span></span></td>
<td><span data-ttu-id="d853f-498">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-498">Packaging</span></span></td>
<td><span data-ttu-id="d853f-499">35</span><span class="sxs-lookup"><span data-stu-id="d853f-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-500">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="d853f-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="d853f-501">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="d853f-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-502">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-502">Cost object</span></span></th>
<th><span data-ttu-id="d853f-503">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="d853f-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-504">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-504">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-505">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-505">Product 1</span></span></td>
<td><span data-ttu-id="d853f-506">60</span><span class="sxs-lookup"><span data-stu-id="d853f-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-507">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-507">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-508">2. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-508">Product 2</span></span></td>
<td><span data-ttu-id="d853f-509">20</span><span class="sxs-lookup"><span data-stu-id="d853f-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-510">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="d853f-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="d853f-511">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="d853f-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-512">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-512">Cost object</span></span></th>
<th><span data-ttu-id="d853f-513">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="d853f-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-514">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-514">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-515">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-515">Product 1</span></span></td>
<td><span data-ttu-id="d853f-516">80</span><span class="sxs-lookup"><span data-stu-id="d853f-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-517">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-517">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-518">2. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-518">Product 2</span></span></td>
<td><span data-ttu-id="d853f-519">15</span><span class="sxs-lookup"><span data-stu-id="d853f-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="d853f-520">A statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="d853f-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="d853f-521">További információk: [Statisztikaimérték-szolgáltató sablon](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="d853f-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="d853f-522">Az alábbi táblázat azt az eredményt mutatja, amikor a HR szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="d853f-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-523">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-523">Cost object</span></span></th>
<th><span data-ttu-id="d853f-524">Nagyság</span><span class="sxs-lookup"><span data-stu-id="d853f-524">Magnitude</span></span></th>
<th><span data-ttu-id="d853f-525">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="d853f-525">Allocation factor</span></span></th>
<th><span data-ttu-id="d853f-526">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-526">Amount</span></span></th>
<th><span data-ttu-id="d853f-527">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-528">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-528">CC002</span></span></td>
<td><span data-ttu-id="d853f-529">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-529">Finance</span></span></td>
<td><span data-ttu-id="d853f-530">35</span><span class="sxs-lookup"><span data-stu-id="d853f-530">35</span></span></td>
<td><span data-ttu-id="d853f-531">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="d853f-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d853f-532">175.00</span><span class="sxs-lookup"><span data-stu-id="d853f-532">175.00</span></span></td>
<td><span data-ttu-id="d853f-533">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-534">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-534">CC003</span></span></td>
<td><span data-ttu-id="d853f-535">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-535">Assembly</span></span></td>
<td><span data-ttu-id="d853f-536">55</span><span class="sxs-lookup"><span data-stu-id="d853f-536">55</span></span></td>
<td><span data-ttu-id="d853f-537">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="d853f-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d853f-538">275.00</span><span class="sxs-lookup"><span data-stu-id="d853f-538">275.00</span></span></td>
<td><span data-ttu-id="d853f-539">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-540">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-540">CC004</span></span></td>
<td><span data-ttu-id="d853f-541">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-541">Packaging</span></span></td>
<td><span data-ttu-id="d853f-542">10</span><span class="sxs-lookup"><span data-stu-id="d853f-542">10</span></span></td>
<td><span data-ttu-id="d853f-543">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="d853f-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="d853f-544">50,00</span><span class="sxs-lookup"><span data-stu-id="d853f-544">50.00</span></span></td>
<td><span data-ttu-id="d853f-545">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-546">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-546">CC002</span></span></td>
<td><span data-ttu-id="d853f-547">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-547">Finance</span></span></td>
<td><span data-ttu-id="d853f-548">35</span><span class="sxs-lookup"><span data-stu-id="d853f-548">35</span></span></td>
<td><span data-ttu-id="d853f-549">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="d853f-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d853f-550">436.00</span><span class="sxs-lookup"><span data-stu-id="d853f-550">436.00</span></span></td>
<td><span data-ttu-id="d853f-551">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-552">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-552">CC003</span></span></td>
<td><span data-ttu-id="d853f-553">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-553">Assembly</span></span></td>
<td><span data-ttu-id="d853f-554">55</span><span class="sxs-lookup"><span data-stu-id="d853f-554">55</span></span></td>
<td><span data-ttu-id="d853f-555">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="d853f-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d853f-556">685.14</span><span class="sxs-lookup"><span data-stu-id="d853f-556">685.14</span></span></td>
<td><span data-ttu-id="d853f-557">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-558">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-558">CC004</span></span></td>
<td><span data-ttu-id="d853f-559">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-559">Packaging</span></span></td>
<td><span data-ttu-id="d853f-560">10</span><span class="sxs-lookup"><span data-stu-id="d853f-560">10</span></span></td>
<td><span data-ttu-id="d853f-561">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="d853f-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="d853f-562">124.57</span><span class="sxs-lookup"><span data-stu-id="d853f-562">124.57</span></span></td>
<td><span data-ttu-id="d853f-563">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-564">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="d853f-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-565">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-565">Cost object</span></span></th>
<th><span data-ttu-id="d853f-566">Nagyság</span><span class="sxs-lookup"><span data-stu-id="d853f-566">Magnitude</span></span></th>
<th><span data-ttu-id="d853f-567">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="d853f-567">Allocation factor</span></span></th>
<th><span data-ttu-id="d853f-568">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-568">Amount</span></span></th>
<th><span data-ttu-id="d853f-569">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-570">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-570">CC003</span></span></td>
<td><span data-ttu-id="d853f-571">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-571">Assembly</span></span></td>
<td><span data-ttu-id="d853f-572">65</span><span class="sxs-lookup"><span data-stu-id="d853f-572">65</span></span></td>
<td><span data-ttu-id="d853f-573">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="d853f-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="d853f-574">438.75</span><span class="sxs-lookup"><span data-stu-id="d853f-574">438.75</span></span></td>
<td><span data-ttu-id="d853f-575">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-576">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-576">CC004</span></span></td>
<td><span data-ttu-id="d853f-577">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-577">Packaging</span></span></td>
<td><span data-ttu-id="d853f-578">35</span><span class="sxs-lookup"><span data-stu-id="d853f-578">35</span></span></td>
<td><span data-ttu-id="d853f-579">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="d853f-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="d853f-580">236.25</span><span class="sxs-lookup"><span data-stu-id="d853f-580">236.25</span></span></td>
<td><span data-ttu-id="d853f-581">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-582">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-582">CC003</span></span></td>
<td><span data-ttu-id="d853f-583">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-583">Assembly</span></span></td>
<td><span data-ttu-id="d853f-584">65</span><span class="sxs-lookup"><span data-stu-id="d853f-584">65</span></span></td>
<td><span data-ttu-id="d853f-585">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="d853f-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="d853f-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="d853f-586">5,297.69</span></span></td>
<td><span data-ttu-id="d853f-587">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-588">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-588">CC004</span></span></td>
<td><span data-ttu-id="d853f-589">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-589">Packaging</span></span></td>
<td><span data-ttu-id="d853f-590">35</span><span class="sxs-lookup"><span data-stu-id="d853f-590">35</span></span></td>
<td><span data-ttu-id="d853f-591">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="d853f-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="d853f-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="d853f-592">2,852.60</span></span></td>
<td><span data-ttu-id="d853f-593">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-594">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="d853f-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-595">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-595">Cost object</span></span></th>
<th><span data-ttu-id="d853f-596">Nagyság</span><span class="sxs-lookup"><span data-stu-id="d853f-596">Magnitude</span></span></th>
<th><span data-ttu-id="d853f-597">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="d853f-597">Allocation factor</span></span></th>
<th><span data-ttu-id="d853f-598">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-598">Amount</span></span></th>
<th><span data-ttu-id="d853f-599">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-600">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-600">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-601">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-601">Product 1</span></span></td>
<td><span data-ttu-id="d853f-602">60</span><span class="sxs-lookup"><span data-stu-id="d853f-602">60</span></span></td>
<td><span data-ttu-id="d853f-603">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="d853f-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="d853f-604">535.31</span><span class="sxs-lookup"><span data-stu-id="d853f-604">535.31</span></span></td>
<td><span data-ttu-id="d853f-605">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-606">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-606">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-607">2. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-607">Product 2</span></span></td>
<td><span data-ttu-id="d853f-608">20</span><span class="sxs-lookup"><span data-stu-id="d853f-608">20</span></span></td>
<td><span data-ttu-id="d853f-609">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="d853f-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="d853f-610">178.44</span><span class="sxs-lookup"><span data-stu-id="d853f-610">178.44</span></span></td>
<td><span data-ttu-id="d853f-611">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-612">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-612">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-613">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-613">Product 1</span></span></td>
<td><span data-ttu-id="d853f-614">60</span><span class="sxs-lookup"><span data-stu-id="d853f-614">60</span></span></td>
<td><span data-ttu-id="d853f-615">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="d853f-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="d853f-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="d853f-616">4,487.12</span></span></td>
<td><span data-ttu-id="d853f-617">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-618">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-618">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-619">2. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-619">Product 2</span></span></td>
<td><span data-ttu-id="d853f-620">20</span><span class="sxs-lookup"><span data-stu-id="d853f-620">20</span></span></td>
<td><span data-ttu-id="d853f-621">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="d853f-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="d853f-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="d853f-622">1,495.71</span></span></td>
<td><span data-ttu-id="d853f-623">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d853f-624">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="d853f-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-625">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-625">Cost object</span></span></th>
<th><span data-ttu-id="d853f-626">Nagyság</span><span class="sxs-lookup"><span data-stu-id="d853f-626">Magnitude</span></span></th>
<th><span data-ttu-id="d853f-627">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="d853f-627">Allocation factor</span></span></th>
<th><span data-ttu-id="d853f-628">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-628">Amount</span></span></th>
<th><span data-ttu-id="d853f-629">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-630">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-630">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-631">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-631">Product 1</span></span></td>
<td><span data-ttu-id="d853f-632">80</span><span class="sxs-lookup"><span data-stu-id="d853f-632">80</span></span></td>
<td><span data-ttu-id="d853f-633">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="d853f-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="d853f-634">241.05</span><span class="sxs-lookup"><span data-stu-id="d853f-634">241.05</span></span></td>
<td><span data-ttu-id="d853f-635">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-636">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-636">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-637">2. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-637">Product 2</span></span></td>
<td><span data-ttu-id="d853f-638">15.</span><span class="sxs-lookup"><span data-stu-id="d853f-638">15</span></span></td>
<td><span data-ttu-id="d853f-639">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="d853f-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="d853f-640">45.20</span><span class="sxs-lookup"><span data-stu-id="d853f-640">45.20</span></span></td>
<td><span data-ttu-id="d853f-641">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-642">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-642">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-643">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-643">Product 1</span></span></td>
<td><span data-ttu-id="d853f-644">80</span><span class="sxs-lookup"><span data-stu-id="d853f-644">80</span></span></td>
<td><span data-ttu-id="d853f-645">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="d853f-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="d853f-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="d853f-646">2,507.09</span></span></td>
<td><span data-ttu-id="d853f-647">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-648">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-648">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-649">2. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-649">Product 2</span></span></td>
<td><span data-ttu-id="d853f-650">15.</span><span class="sxs-lookup"><span data-stu-id="d853f-650">15</span></span></td>
<td><span data-ttu-id="d853f-651">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="d853f-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="d853f-652">470.08</span><span class="sxs-lookup"><span data-stu-id="d853f-652">470.08</span></span></td>
<td><span data-ttu-id="d853f-653">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="d853f-654">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="d853f-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d853f-655">Napló</span><span class="sxs-lookup"><span data-stu-id="d853f-655">Journal</span></span></th>
<th><span data-ttu-id="d853f-656">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="d853f-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="d853f-657">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="d853f-658">Verzió</span><span class="sxs-lookup"><span data-stu-id="d853f-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-659">00004</span><span class="sxs-lookup"><span data-stu-id="d853f-659">00004</span></span></td>
<td><span data-ttu-id="d853f-660">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="d853f-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="d853f-661">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="d853f-661">Fiscal</span></span></td>
<td><span data-ttu-id="d853f-662">2017</span><span class="sxs-lookup"><span data-stu-id="d853f-662">2017</span></span></td>
<td><span data-ttu-id="d853f-663">1. időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-663">Period 1</span></span></td>
<td><span data-ttu-id="d853f-664">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="d853f-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="d853f-665">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="d853f-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d853f-666">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="d853f-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-667">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-668">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="d853f-668">Cost element</span></span></th>
<th><span data-ttu-id="d853f-669">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-669">Cost behavior</span></span></th>
<th><span data-ttu-id="d853f-670">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-671">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-672">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-672">CC001</span></span></td>
<td><span data-ttu-id="d853f-673">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-673">HR</span></span></td>
<td><span data-ttu-id="d853f-674">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-674">10001</span></span></td>
<td><span data-ttu-id="d853f-675">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-675">Electricity</span></span></td>
<td><span data-ttu-id="d853f-676">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-676">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-677">500.00</span><span class="sxs-lookup"><span data-stu-id="d853f-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-678">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-679">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-679">CC001</span></span></td>
<td><span data-ttu-id="d853f-680">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-680">HR</span></span></td>
<td><span data-ttu-id="d853f-681">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-681">10001</span></span></td>
<td><span data-ttu-id="d853f-682">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-682">Electricity</span></span></td>
<td><span data-ttu-id="d853f-683">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-683">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="d853f-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-685">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-686">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-686">CC002</span></span></td>
<td><span data-ttu-id="d853f-687">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-687">Finance</span></span></td>
<td><span data-ttu-id="d853f-688">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-688">10001</span></span></td>
<td><span data-ttu-id="d853f-689">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-689">Electricity</span></span></td>
<td><span data-ttu-id="d853f-690">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-690">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-691">675.00</span><span class="sxs-lookup"><span data-stu-id="d853f-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-692">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-693">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-693">CC002</span></span></td>
<td><span data-ttu-id="d853f-694">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-694">Finance</span></span></td>
<td><span data-ttu-id="d853f-695">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-695">10001</span></span></td>
<td><span data-ttu-id="d853f-696">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-696">Electricity</span></span></td>
<td><span data-ttu-id="d853f-697">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-697">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="d853f-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-699">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-700">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-700">CC003</span></span></td>
<td><span data-ttu-id="d853f-701">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-701">Assembly</span></span></td>
<td><span data-ttu-id="d853f-702">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-702">10001</span></span></td>
<td><span data-ttu-id="d853f-703">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-703">Electricity</span></span></td>
<td><span data-ttu-id="d853f-704">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-704">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-705">713.75</span><span class="sxs-lookup"><span data-stu-id="d853f-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-706">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-707">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-707">CC003</span></span></td>
<td><span data-ttu-id="d853f-708">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-708">Assembly</span></span></td>
<td><span data-ttu-id="d853f-709">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-709">10001</span></span></td>
<td><span data-ttu-id="d853f-710">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-710">Electricity</span></span></td>
<td><span data-ttu-id="d853f-711">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-711">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="d853f-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-713">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-714">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-714">CC003</span></span></td>
<td><span data-ttu-id="d853f-715">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-715">Packaging</span></span></td>
<td><span data-ttu-id="d853f-716">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-716">10001</span></span></td>
<td><span data-ttu-id="d853f-717">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-717">Electricity</span></span></td>
<td><span data-ttu-id="d853f-718">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-718">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-719">286.25</span><span class="sxs-lookup"><span data-stu-id="d853f-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-720">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-721">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-721">CC003</span></span></td>
<td><span data-ttu-id="d853f-722">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-722">Packaging</span></span></td>
<td><span data-ttu-id="d853f-723">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-723">10001</span></span></td>
<td><span data-ttu-id="d853f-724">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-724">Electricity</span></span></td>
<td><span data-ttu-id="d853f-725">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-725">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="d853f-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-727">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-728">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-728">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-729">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-729">Product 1</span></span></td>
<td><span data-ttu-id="d853f-730">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-730">10001</span></span></td>
<td><span data-ttu-id="d853f-731">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-731">Electricity</span></span></td>
<td><span data-ttu-id="d853f-732">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-732">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-733">776.36</span><span class="sxs-lookup"><span data-stu-id="d853f-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-734">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-735">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-735">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-736">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-736">Product 1</span></span></td>
<td><span data-ttu-id="d853f-737">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-737">10001</span></span></td>
<td><span data-ttu-id="d853f-738">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-738">Electricity</span></span></td>
<td><span data-ttu-id="d853f-739">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-739">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="d853f-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-741">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-742">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-742">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-743">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-743">Product 1</span></span></td>
<td><span data-ttu-id="d853f-744">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-744">10001</span></span></td>
<td><span data-ttu-id="d853f-745">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-745">Electricity</span></span></td>
<td><span data-ttu-id="d853f-746">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-746">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-747">223.64</span><span class="sxs-lookup"><span data-stu-id="d853f-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-748">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="d853f-749">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-749">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-750">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-750">Product 1</span></span></td>
<td><span data-ttu-id="d853f-751">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-751">10001</span></span></td>
<td><span data-ttu-id="d853f-752">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-752">Electricity</span></span></td>
<td><span data-ttu-id="d853f-753">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-753">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="d853f-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="d853f-755">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="d853f-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="d853f-756">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="d853f-757">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="d853f-757">Cost element</span></span></th>
<th><span data-ttu-id="d853f-758">Költség működése</span><span class="sxs-lookup"><span data-stu-id="d853f-758">Cost behavior</span></span></th>
<th><span data-ttu-id="d853f-759">Összeg</span><span class="sxs-lookup"><span data-stu-id="d853f-759">Amount</span></span></th>
<th><span data-ttu-id="d853f-760">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="d853f-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d853f-761">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-761">CC001</span></span></td>
<td><span data-ttu-id="d853f-762">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-762">HR</span></span></td>
<td><span data-ttu-id="d853f-763">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-763">10001</span></span></td>
<td><span data-ttu-id="d853f-764">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-764">Electricity</span></span></td>
<td><span data-ttu-id="d853f-765">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-765">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="d853f-766">-500.00</span></span></td>
<td><span data-ttu-id="d853f-767">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-768">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-768">CC002</span></span></td>
<td><span data-ttu-id="d853f-769">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-769">Finance</span></span></td>
<td><span data-ttu-id="d853f-770">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-770">10001</span></span></td>
<td><span data-ttu-id="d853f-771">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-771">Electricity</span></span></td>
<td><span data-ttu-id="d853f-772">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-772">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-773">175.00</span><span class="sxs-lookup"><span data-stu-id="d853f-773">175.00</span></span></td>
<td><span data-ttu-id="d853f-774">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-775">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-775">CC003</span></span></td>
<td><span data-ttu-id="d853f-776">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-776">Assembly</span></span></td>
<td><span data-ttu-id="d853f-777">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-777">10001</span></span></td>
<td><span data-ttu-id="d853f-778">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-778">Electricity</span></span></td>
<td><span data-ttu-id="d853f-779">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-779">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-780">275.00</span><span class="sxs-lookup"><span data-stu-id="d853f-780">275.00</span></span></td>
<td><span data-ttu-id="d853f-781">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-782">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-782">CC004</span></span></td>
<td><span data-ttu-id="d853f-783">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-783">Packaging</span></span></td>
<td><span data-ttu-id="d853f-784">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-784">10001</span></span></td>
<td><span data-ttu-id="d853f-785">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-785">Electricity</span></span></td>
<td><span data-ttu-id="d853f-786">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-786">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-787">50,00</span><span class="sxs-lookup"><span data-stu-id="d853f-787">50,00</span></span></td>
<td><span data-ttu-id="d853f-788">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-789">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-789">CC001</span></span></td>
<td><span data-ttu-id="d853f-790">HR</span><span class="sxs-lookup"><span data-stu-id="d853f-790">HR</span></span></td>
<td><span data-ttu-id="d853f-791">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-791">10001</span></span></td>
<td><span data-ttu-id="d853f-792">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-792">Electricity</span></span></td>
<td><span data-ttu-id="d853f-793">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-793">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-794">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="d853f-794">-1,245.71</span></span></td>
<td><span data-ttu-id="d853f-795">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-796">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-796">CC002</span></span></td>
<td><span data-ttu-id="d853f-797">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-797">Finance</span></span></td>
<td><span data-ttu-id="d853f-798">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-798">10001</span></span></td>
<td><span data-ttu-id="d853f-799">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-799">Electricity</span></span></td>
<td><span data-ttu-id="d853f-800">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-800">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-801">436.00</span><span class="sxs-lookup"><span data-stu-id="d853f-801">436.00</span></span></td>
<td><span data-ttu-id="d853f-802">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-803">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-803">CC003</span></span></td>
<td><span data-ttu-id="d853f-804">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-804">Assembly</span></span></td>
<td><span data-ttu-id="d853f-805">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-805">10001</span></span></td>
<td><span data-ttu-id="d853f-806">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-806">Electricity</span></span></td>
<td><span data-ttu-id="d853f-807">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-807">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-808">685.14</span><span class="sxs-lookup"><span data-stu-id="d853f-808">685.14</span></span></td>
<td><span data-ttu-id="d853f-809">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-810">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-810">CC004</span></span></td>
<td><span data-ttu-id="d853f-811">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-811">Packaging</span></span></td>
<td><span data-ttu-id="d853f-812">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-812">10001</span></span></td>
<td><span data-ttu-id="d853f-813">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-813">Electricity</span></span></td>
<td><span data-ttu-id="d853f-814">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-814">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-815">124.57</span><span class="sxs-lookup"><span data-stu-id="d853f-815">124.57</span></span></td>
<td><span data-ttu-id="d853f-816">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-817">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-817">CC002</span></span></td>
<td><span data-ttu-id="d853f-818">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-818">Finance</span></span></td>
<td><span data-ttu-id="d853f-819">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-819">10001</span></span></td>
<td><span data-ttu-id="d853f-820">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-820">Electricity</span></span></td>
<td><span data-ttu-id="d853f-821">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-821">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-822">-675.00</span><span class="sxs-lookup"><span data-stu-id="d853f-822">-675.00</span></span></td>
<td><span data-ttu-id="d853f-823">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-824">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-824">CC003</span></span></td>
<td><span data-ttu-id="d853f-825">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-825">Assembly</span></span></td>
<td><span data-ttu-id="d853f-826">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-826">10001</span></span></td>
<td><span data-ttu-id="d853f-827">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-827">Electricity</span></span></td>
<td><span data-ttu-id="d853f-828">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-828">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-829">438.75</span><span class="sxs-lookup"><span data-stu-id="d853f-829">438.75</span></span></td>
<td><span data-ttu-id="d853f-830">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-831">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-831">CC004</span></span></td>
<td><span data-ttu-id="d853f-832">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-832">Packaging</span></span></td>
<td><span data-ttu-id="d853f-833">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-833">10001</span></span></td>
<td><span data-ttu-id="d853f-834">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-834">Electricity</span></span></td>
<td><span data-ttu-id="d853f-835">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-835">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-836">236.25</span><span class="sxs-lookup"><span data-stu-id="d853f-836">236.25</span></span></td>
<td><span data-ttu-id="d853f-837">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-838">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-838">CC002</span></span></td>
<td><span data-ttu-id="d853f-839">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="d853f-839">Finance</span></span></td>
<td><span data-ttu-id="d853f-840">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-840">10001</span></span></td>
<td><span data-ttu-id="d853f-841">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-841">Electricity</span></span></td>
<td><span data-ttu-id="d853f-842">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-842">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-843">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="d853f-843">-8,150.29</span></span></td>
<td><span data-ttu-id="d853f-844">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-845">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-845">CC003</span></span></td>
<td><span data-ttu-id="d853f-846">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-846">Assembly</span></span></td>
<td><span data-ttu-id="d853f-847">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-847">10001</span></span></td>
<td><span data-ttu-id="d853f-848">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-848">Electricity</span></span></td>
<td><span data-ttu-id="d853f-849">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-849">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="d853f-850">5,297.69</span></span></td>
<td><span data-ttu-id="d853f-851">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-852">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-852">CC004</span></span></td>
<td><span data-ttu-id="d853f-853">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="d853f-853">Packaging</span></span></td>
<td><span data-ttu-id="d853f-854">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-854">10001</span></span></td>
<td><span data-ttu-id="d853f-855">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-855">Electricity</span></span></td>
<td><span data-ttu-id="d853f-856">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-856">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="d853f-857">2,852.60</span></span></td>
<td><span data-ttu-id="d853f-858">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-859">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-859">CC003</span></span></td>
<td><span data-ttu-id="d853f-860">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-860">Assembly</span></span></td>
<td><span data-ttu-id="d853f-861">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-861">10001</span></span></td>
<td><span data-ttu-id="d853f-862">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-862">Electricity</span></span></td>
<td><span data-ttu-id="d853f-863">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-863">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-864">-713.75</span><span class="sxs-lookup"><span data-stu-id="d853f-864">-713.75</span></span></td>
<td><span data-ttu-id="d853f-865">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-866">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-866">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-867">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-867">Product 1</span></span></td>
<td><span data-ttu-id="d853f-868">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-868">10001</span></span></td>
<td><span data-ttu-id="d853f-869">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-869">Electricity</span></span></td>
<td><span data-ttu-id="d853f-870">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-870">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-871">535.31</span><span class="sxs-lookup"><span data-stu-id="d853f-871">535.31</span></span></td>
<td><span data-ttu-id="d853f-872">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-873">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-873">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-874">2. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-874">Product 2</span></span></td>
<td><span data-ttu-id="d853f-875">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-875">10001</span></span></td>
<td><span data-ttu-id="d853f-876">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-876">Electricity</span></span></td>
<td><span data-ttu-id="d853f-877">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-877">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-878">178.44</span><span class="sxs-lookup"><span data-stu-id="d853f-878">178.44</span></span></td>
<td><span data-ttu-id="d853f-879">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-880">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-880">CC003</span></span></td>
<td><span data-ttu-id="d853f-881">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-881">Assembly</span></span></td>
<td><span data-ttu-id="d853f-882">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-882">10001</span></span></td>
<td><span data-ttu-id="d853f-883">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-883">Electricity</span></span></td>
<td><span data-ttu-id="d853f-884">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-884">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-885">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="d853f-885">-5,982.83</span></span></td>
<td><span data-ttu-id="d853f-886">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-887">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-887">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-888">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-888">Product 1</span></span></td>
<td><span data-ttu-id="d853f-889">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-889">10001</span></span></td>
<td><span data-ttu-id="d853f-890">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-890">Electricity</span></span></td>
<td><span data-ttu-id="d853f-891">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-891">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="d853f-892">4,487.12</span></span></td>
<td><span data-ttu-id="d853f-893">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-894">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-894">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-895">2. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-895">Product 2</span></span></td>
<td><span data-ttu-id="d853f-896">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-896">10001</span></span></td>
<td><span data-ttu-id="d853f-897">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-897">Electricity</span></span></td>
<td><span data-ttu-id="d853f-898">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-898">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="d853f-899">1,495.71</span></span></td>
<td><span data-ttu-id="d853f-900">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-901">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-901">CC003</span></span></td>
<td><span data-ttu-id="d853f-902">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-902">Assembly</span></span></td>
<td><span data-ttu-id="d853f-903">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-903">10001</span></span></td>
<td><span data-ttu-id="d853f-904">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-904">Electricity</span></span></td>
<td><span data-ttu-id="d853f-905">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-905">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-906">-286.25</span><span class="sxs-lookup"><span data-stu-id="d853f-906">-286.25</span></span></td>
<td><span data-ttu-id="d853f-907">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-908">Term 1</span><span class="sxs-lookup"><span data-stu-id="d853f-908">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-909">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-909">Product 1</span></span></td>
<td><span data-ttu-id="d853f-910">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-910">10001</span></span></td>
<td><span data-ttu-id="d853f-911">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-911">Electricity</span></span></td>
<td><span data-ttu-id="d853f-912">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-912">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-913">241.05</span><span class="sxs-lookup"><span data-stu-id="d853f-913">241.05</span></span></td>
<td><span data-ttu-id="d853f-914">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-915">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-915">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-916">2. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-916">Product 2</span></span></td>
<td><span data-ttu-id="d853f-917">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-917">10001</span></span></td>
<td><span data-ttu-id="d853f-918">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-918">Electricity</span></span></td>
<td><span data-ttu-id="d853f-919">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-919">Fixed cost</span></span></td>
<td><span data-ttu-id="d853f-920">45.20</span><span class="sxs-lookup"><span data-stu-id="d853f-920">45.20</span></span></td>
<td><span data-ttu-id="d853f-921">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-922">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-922">CC003</span></span></td>
<td><span data-ttu-id="d853f-923">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="d853f-923">Assembly</span></span></td>
<td><span data-ttu-id="d853f-924">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-924">10001</span></span></td>
<td><span data-ttu-id="d853f-925">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-925">Electricity</span></span></td>
<td><span data-ttu-id="d853f-926">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-926">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-927">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="d853f-927">-2,977.17</span></span></td>
<td><span data-ttu-id="d853f-928">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-929">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-929">Prod 1</span></span></td>
<td><span data-ttu-id="d853f-930">1. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-930">Product 1</span></span></td>
<td><span data-ttu-id="d853f-931">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-931">10001</span></span></td>
<td><span data-ttu-id="d853f-932">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-932">Electricity</span></span></td>
<td><span data-ttu-id="d853f-933">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-933">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="d853f-934">2,507.09</span></span></td>
<td><span data-ttu-id="d853f-935">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d853f-936">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-936">Prod 2</span></span></td>
<td><span data-ttu-id="d853f-937">2. termék</span><span class="sxs-lookup"><span data-stu-id="d853f-937">Product 2</span></span></td>
<td><span data-ttu-id="d853f-938">10001</span><span class="sxs-lookup"><span data-stu-id="d853f-938">10001</span></span></td>
<td><span data-ttu-id="d853f-939">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-939">Electricity</span></span></td>
<td><span data-ttu-id="d853f-940">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-940">Variable cost</span></span></td>
<td><span data-ttu-id="d853f-941">470.08</span><span class="sxs-lookup"><span data-stu-id="d853f-941">470.08</span></span></td>
<td><span data-ttu-id="d853f-942">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="d853f-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="d853f-943">Következtetés</span><span class="sxs-lookup"><span data-stu-id="d853f-943">Conclusion</span></span>
<span data-ttu-id="d853f-944">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="d853f-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="d853f-945">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="d853f-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="d853f-946">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="d853f-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="d853f-947">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="d853f-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="d853f-948">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="d853f-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="d853f-949">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="d853f-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="d853f-950">Összesen</span><span class="sxs-lookup"><span data-stu-id="d853f-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="d853f-951">CC099</span><span class="sxs-lookup"><span data-stu-id="d853f-951">CC099</span></span></th>
<th><span data-ttu-id="d853f-952">CC001</span><span class="sxs-lookup"><span data-stu-id="d853f-952">CC001</span></span></th>
<th><span data-ttu-id="d853f-953">CC002</span><span class="sxs-lookup"><span data-stu-id="d853f-953">CC002</span></span></th>
<th><span data-ttu-id="d853f-954">CC003</span><span class="sxs-lookup"><span data-stu-id="d853f-954">CC003</span></span></th>
<th><span data-ttu-id="d853f-955">CC004</span><span class="sxs-lookup"><span data-stu-id="d853f-955">CC004</span></span></th>
<th><span data-ttu-id="d853f-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="d853f-956">Proj 1</span></span></th>
<th><span data-ttu-id="d853f-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="d853f-957">Proj 2</span></span></th>
<th><span data-ttu-id="d853f-958">Term. 1</span><span class="sxs-lookup"><span data-stu-id="d853f-958">Prod 1</span></span></th>
<th><span data-ttu-id="d853f-959">Term. 2</span><span class="sxs-lookup"><span data-stu-id="d853f-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="d853f-960">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="d853f-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="d853f-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="d853f-970">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="d853f-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-971">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="d853f-972">Fix költség</span><span class="sxs-lookup"><span data-stu-id="d853f-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-973">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-974">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-975">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-976">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-977">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="d853f-978">776.36</span><span class="sxs-lookup"><span data-stu-id="d853f-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-979">223.64</span><span class="sxs-lookup"><span data-stu-id="d853f-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="d853f-981">Változó költség</span><span class="sxs-lookup"><span data-stu-id="d853f-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-982">000</span><span class="sxs-lookup"><span data-stu-id="d853f-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-983">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-984">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-985">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-986">0,00</span><span class="sxs-lookup"><span data-stu-id="d853f-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-987">30.00</span><span class="sxs-lookup"><span data-stu-id="d853f-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-988">1000</span><span class="sxs-lookup"><span data-stu-id="d853f-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="d853f-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="d853f-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="d853f-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="d853f-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="d853f-992">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="d853f-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="d853f-993">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="d853f-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="d853f-994">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="d853f-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="d853f-995">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="d853f-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="d853f-996">A további tudnivalókat lásd: [Költségösszesítéssel kapcsolatos irányelv és járulékos költség számítása](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="d853f-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



