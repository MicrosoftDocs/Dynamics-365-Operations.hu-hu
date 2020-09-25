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
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: cc6ad48ef80aa01739129b59cc1133d0a1930f24
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759472"
---
# <a name="overhead-calculation"></a><span data-ttu-id="2873e-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="2873e-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2873e-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="2873e-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="2873e-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="2873e-105">Term definition</span></span>
---------------

<span data-ttu-id="2873e-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="2873e-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="2873e-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="2873e-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="2873e-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="2873e-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="2873e-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="2873e-109">Rent</span></span>
-   <span data-ttu-id="2873e-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-110">Electricity</span></span>
-   <span data-ttu-id="2873e-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="2873e-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="2873e-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="2873e-112">Overhead calculation overview</span></span>
<span data-ttu-id="2873e-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="2873e-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="2873e-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="2873e-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="2873e-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="2873e-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="2873e-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="2873e-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="2873e-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="2873e-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="2873e-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="2873e-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="2873e-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="2873e-119">Version type</span></span>
-   <span data-ttu-id="2873e-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="2873e-120">Date and time</span></span>
-   <span data-ttu-id="2873e-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="2873e-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="2873e-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="2873e-122">Fiscal year</span></span>
-   <span data-ttu-id="2873e-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-123">Fiscal period</span></span>

<span data-ttu-id="2873e-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="2873e-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="2873e-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="2873e-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="2873e-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="2873e-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="2873e-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="2873e-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="2873e-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="2873e-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="2873e-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="2873e-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="2873e-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="2873e-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="2873e-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="2873e-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="2873e-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="2873e-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="2873e-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="2873e-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="2873e-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="2873e-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="2873e-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="2873e-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="2873e-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="2873e-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="2873e-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="2873e-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2873e-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="2873e-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="2873e-140">Main account</span></span></th>
<th><span data-ttu-id="2873e-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="2873e-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="2873e-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="2873e-143">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-143">CC099</span></span></td>
<td><span data-ttu-id="2873e-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-144">Default cost center</span></span></td>
<td><span data-ttu-id="2873e-145">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-145">10001</span></span></td>
<td><span data-ttu-id="2873e-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-146">Electricity</span></span></td>
<td><span data-ttu-id="2873e-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="2873e-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="2873e-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="2873e-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="2873e-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="2873e-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="2873e-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="2873e-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="2873e-151">Define the cost behavior rule</span></span>

<span data-ttu-id="2873e-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="2873e-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="2873e-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="2873e-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="2873e-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="2873e-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="2873e-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="2873e-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="2873e-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="2873e-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="2873e-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="2873e-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="2873e-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="2873e-159">Napló</span><span class="sxs-lookup"><span data-stu-id="2873e-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2873e-160">Napló</span><span class="sxs-lookup"><span data-stu-id="2873e-160">Journal</span></span></th>
<th><span data-ttu-id="2873e-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="2873e-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2873e-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2873e-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="2873e-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-164">00001</span><span class="sxs-lookup"><span data-stu-id="2873e-164">00001</span></span></td>
<td><span data-ttu-id="2873e-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="2873e-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="2873e-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="2873e-166">Fiscal</span></span></td>
<td><span data-ttu-id="2873e-167">2017</span><span class="sxs-lookup"><span data-stu-id="2873e-167">2017</span></span></td>
<td><span data-ttu-id="2873e-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-168">Period 1</span></span></td>
<td><span data-ttu-id="2873e-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2873e-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="2873e-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2873e-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="2873e-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="2873e-173">Cost element</span></span></th>
<th><span data-ttu-id="2873e-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-174">Cost behavior</span></span></th>
<th><span data-ttu-id="2873e-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="2873e-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="2873e-177">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-177">CC099</span></span></td>
<td><span data-ttu-id="2873e-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-178">Default cost center</span></span></td>
<td><span data-ttu-id="2873e-179">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-179">10001</span></span></td>
<td><span data-ttu-id="2873e-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-180">Electricity</span></span></td>
<td><span data-ttu-id="2873e-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="2873e-181">Unclassified</span></span></td>
<td><span data-ttu-id="2873e-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2873e-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="2873e-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="2873e-185">Cost element</span></span></th>
<th><span data-ttu-id="2873e-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-186">Cost behavior</span></span></th>
<th><span data-ttu-id="2873e-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-187">Amount</span></span></th>
<th><span data-ttu-id="2873e-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="2873e-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-189">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-189">CC099</span></span></td>
<td><span data-ttu-id="2873e-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-190">Default cost center</span></span></td>
<td><span data-ttu-id="2873e-191">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-191">10001</span></span></td>
<td><span data-ttu-id="2873e-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-192">Electricity</span></span></td>
<td><span data-ttu-id="2873e-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="2873e-193">Unclassified</span></span></td>
<td><span data-ttu-id="2873e-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-194">10,000.00</span></span></td>
<td><span data-ttu-id="2873e-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="2873e-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-196">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-196">CC099</span></span></td>
<td><span data-ttu-id="2873e-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-197">Default cost center</span></span></td>
<td><span data-ttu-id="2873e-198">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-198">10001</span></span></td>
<td><span data-ttu-id="2873e-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-199">Electricity</span></span></td>
<td><span data-ttu-id="2873e-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="2873e-200">Unclassified</span></span></td>
<td><span data-ttu-id="2873e-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-201">-10,000.00</span></span></td>
<td><span data-ttu-id="2873e-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-203">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-203">CC099</span></span></td>
<td><span data-ttu-id="2873e-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-204">Default cost center</span></span></td>
<td><span data-ttu-id="2873e-205">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-205">10001</span></span></td>
<td><span data-ttu-id="2873e-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-206">Electricity</span></span></td>
<td><span data-ttu-id="2873e-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-207">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="2873e-208">1,000.00</span></span></td>
<td><span data-ttu-id="2873e-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-210">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-210">CC099</span></span></td>
<td><span data-ttu-id="2873e-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-211">Default cost center</span></span></td>
<td><span data-ttu-id="2873e-212">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-212">10001</span></span></td>
<td><span data-ttu-id="2873e-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-213">Electricity</span></span></td>
<td><span data-ttu-id="2873e-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-214">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-215">9,000.00</span></span></td>
<td><span data-ttu-id="2873e-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-217">További információért lásd: [Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="2873e-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="2873e-218">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="2873e-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="2873e-219">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="2873e-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="2873e-220">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="2873e-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="2873e-221">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="2873e-221">Define the cost distribution rule</span></span>

<span data-ttu-id="2873e-222">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="2873e-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="2873e-223">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="2873e-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="2873e-224">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="2873e-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="2873e-225">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="2873e-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="2873e-226">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="2873e-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="2873e-227">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="2873e-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-228">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-228">Cost object</span></span></th>
<th><span data-ttu-id="2873e-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="2873e-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-230">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-230">CC001</span></span></td>
<td><span data-ttu-id="2873e-231">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-231">HR</span></span></td>
<td><span data-ttu-id="2873e-232">1000</span><span class="sxs-lookup"><span data-stu-id="2873e-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-233">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-233">CC002</span></span></td>
<td><span data-ttu-id="2873e-234">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-234">Finance</span></span></td>
<td><span data-ttu-id="2873e-235">6,000</span><span class="sxs-lookup"><span data-stu-id="2873e-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-236">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-236">CC003</span></span></td>
<td><span data-ttu-id="2873e-237">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-237">Assembly</span></span></td>
<td><span data-ttu-id="2873e-238">0</span><span class="sxs-lookup"><span data-stu-id="2873e-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-239">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="2873e-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-240">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-240">Cost object</span></span></th>
<th><span data-ttu-id="2873e-241">Nagyság</span><span class="sxs-lookup"><span data-stu-id="2873e-241">Magnitude</span></span></th>
<th><span data-ttu-id="2873e-242">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="2873e-242">Allocation factor</span></span></th>
<th><span data-ttu-id="2873e-243">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-244">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-244">CC001</span></span></td>
<td><span data-ttu-id="2873e-245">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-245">HR</span></span></td>
<td><span data-ttu-id="2873e-246">1000</span><span class="sxs-lookup"><span data-stu-id="2873e-246">1,000</span></span></td>
<td><span data-ttu-id="2873e-247">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2873e-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="2873e-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-249">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-249">CC002</span></span></td>
<td><span data-ttu-id="2873e-250">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-250">Finance</span></span></td>
<td><span data-ttu-id="2873e-251">6,000</span><span class="sxs-lookup"><span data-stu-id="2873e-251">6,000</span></span></td>
<td><span data-ttu-id="2873e-252">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2873e-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="2873e-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-254">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-254">CC003</span></span></td>
<td><span data-ttu-id="2873e-255">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-255">Assembly</span></span></td>
<td><span data-ttu-id="2873e-256">0</span><span class="sxs-lookup"><span data-stu-id="2873e-256">0</span></span></td>
<td><span data-ttu-id="2873e-257">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="2873e-258">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-259">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="2873e-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="2873e-260">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: (Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="2873e-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-261">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-261">Cost object</span></span></th>
<th><span data-ttu-id="2873e-262">Receptúra</span><span class="sxs-lookup"><span data-stu-id="2873e-262">Formula</span></span></th>
<th><span data-ttu-id="2873e-263">Nagyság</span><span class="sxs-lookup"><span data-stu-id="2873e-263">Magnitude</span></span></th>
<th><span data-ttu-id="2873e-264">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="2873e-264">Allocation factor</span></span></th>
<th><span data-ttu-id="2873e-265">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-266">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-266">CC001</span></span></td>
<td><span data-ttu-id="2873e-267">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-267">HR</span></span></td>
<td><span data-ttu-id="2873e-268">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="2873e-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2873e-269">1</span><span class="sxs-lookup"><span data-stu-id="2873e-269">1</span></span></td>
<td><span data-ttu-id="2873e-270">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2873e-271">500.00</span><span class="sxs-lookup"><span data-stu-id="2873e-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-272">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-272">CC002</span></span></td>
<td><span data-ttu-id="2873e-273">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-273">Finance</span></span></td>
<td><span data-ttu-id="2873e-274">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="2873e-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2873e-275">1</span><span class="sxs-lookup"><span data-stu-id="2873e-275">1</span></span></td>
<td><span data-ttu-id="2873e-276">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2873e-277">500.00</span><span class="sxs-lookup"><span data-stu-id="2873e-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-278">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-278">CC003</span></span></td>
<td><span data-ttu-id="2873e-279">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-279">Assembly</span></span></td>
<td><span data-ttu-id="2873e-280">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="2873e-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="2873e-281">0</span><span class="sxs-lookup"><span data-stu-id="2873e-281">0</span></span></td>
<td><span data-ttu-id="2873e-282">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="2873e-283">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="2873e-284">Napló</span><span class="sxs-lookup"><span data-stu-id="2873e-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2873e-285">Napló</span><span class="sxs-lookup"><span data-stu-id="2873e-285">Journal</span></span></th>
<th><span data-ttu-id="2873e-286">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="2873e-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2873e-287">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2873e-288">Verzió</span><span class="sxs-lookup"><span data-stu-id="2873e-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-289">00002</span><span class="sxs-lookup"><span data-stu-id="2873e-289">00002</span></span></td>
<td><span data-ttu-id="2873e-290">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="2873e-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="2873e-291">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="2873e-291">Fiscal</span></span></td>
<td><span data-ttu-id="2873e-292">2017</span><span class="sxs-lookup"><span data-stu-id="2873e-292">2017</span></span></td>
<td><span data-ttu-id="2873e-293">1. időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-293">Period 1</span></span></td>
<td><span data-ttu-id="2873e-294">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2873e-295">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="2873e-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2873e-296">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="2873e-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-297">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-298">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="2873e-298">Cost element</span></span></th>
<th><span data-ttu-id="2873e-299">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-299">Cost behavior</span></span></th>
<th><span data-ttu-id="2873e-300">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-301">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-302">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-302">CC099</span></span></td>
<td><span data-ttu-id="2873e-303">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-303">Default cost center</span></span></td>
<td><span data-ttu-id="2873e-304">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-304">10001</span></span></td>
<td><span data-ttu-id="2873e-305">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-305">Electricity</span></span></td>
<td><span data-ttu-id="2873e-306">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-306">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="2873e-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-308">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-309">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-309">CC099</span></span></td>
<td><span data-ttu-id="2873e-310">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-310">Default cost center</span></span></td>
<td><span data-ttu-id="2873e-311">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-311">10001</span></span></td>
<td><span data-ttu-id="2873e-312">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-312">Electricity</span></span></td>
<td><span data-ttu-id="2873e-313">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-313">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2873e-315">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="2873e-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-316">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-317">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="2873e-317">Cost element</span></span></th>
<th><span data-ttu-id="2873e-318">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-318">Cost behavior</span></span></th>
<th><span data-ttu-id="2873e-319">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-319">Amount</span></span></th>
<th><span data-ttu-id="2873e-320">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="2873e-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-321">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-321">CC099</span></span></td>
<td><span data-ttu-id="2873e-322">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-322">Default cost center</span></span></td>
<td><span data-ttu-id="2873e-323">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-323">10001</span></span></td>
<td><span data-ttu-id="2873e-324">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-324">Electricity</span></span></td>
<td><span data-ttu-id="2873e-325">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-325">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="2873e-326">-1,000.00</span></span></td>
<td><span data-ttu-id="2873e-327">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-328">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-328">CC001</span></span></td>
<td><span data-ttu-id="2873e-329">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-329">HR</span></span></td>
<td><span data-ttu-id="2873e-330">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-330">10001</span></span></td>
<td><span data-ttu-id="2873e-331">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-331">Electricity</span></span></td>
<td><span data-ttu-id="2873e-332">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-332">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-333">500.00</span><span class="sxs-lookup"><span data-stu-id="2873e-333">500.00</span></span></td>
<td><span data-ttu-id="2873e-334">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-335">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-335">CC002</span></span></td>
<td><span data-ttu-id="2873e-336">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-336">Finance</span></span></td>
<td><span data-ttu-id="2873e-337">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-337">10001</span></span></td>
<td><span data-ttu-id="2873e-338">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-338">Electricity</span></span></td>
<td><span data-ttu-id="2873e-339">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-339">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-340">500.00</span><span class="sxs-lookup"><span data-stu-id="2873e-340">500.00</span></span></td>
<td><span data-ttu-id="2873e-341">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-342">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-342">CC099</span></span></td>
<td><span data-ttu-id="2873e-343">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="2873e-343">Default cost center</span></span></td>
<td><span data-ttu-id="2873e-344">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-344">10001</span></span></td>
<td><span data-ttu-id="2873e-345">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-345">Electricity</span></span></td>
<td><span data-ttu-id="2873e-346">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-346">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-347">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="2873e-347">-9,000.00</span></span></td>
<td><span data-ttu-id="2873e-348">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-349">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-349">CC001</span></span></td>
<td><span data-ttu-id="2873e-350">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-350">HR</span></span></td>
<td><span data-ttu-id="2873e-351">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-351">10001</span></span></td>
<td><span data-ttu-id="2873e-352">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-352">Electricity</span></span></td>
<td><span data-ttu-id="2873e-353">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-353">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="2873e-354">1,285.71</span></span></td>
<td><span data-ttu-id="2873e-355">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-356">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-356">CC002</span></span></td>
<td><span data-ttu-id="2873e-357">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-357">Finance</span></span></td>
<td><span data-ttu-id="2873e-358">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-358">10001</span></span></td>
<td><span data-ttu-id="2873e-359">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-359">Electricity</span></span></td>
<td><span data-ttu-id="2873e-360">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-360">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="2873e-361">7,714.29</span></span></td>
<td><span data-ttu-id="2873e-362">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-363">További információért lásd: [Költségelosztási irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="2873e-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="2873e-364">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="2873e-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="2873e-365">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="2873e-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="2873e-366">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="2873e-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="2873e-367">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="2873e-367">Define the overhead rate</span></span>

<span data-ttu-id="2873e-368">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="2873e-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="2873e-369">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="2873e-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-370">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-370">Cost object</span></span></th>
<th><span data-ttu-id="2873e-371">óra</span><span class="sxs-lookup"><span data-stu-id="2873e-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2873e-372">Proj 1</span></span></td>
<td><span data-ttu-id="2873e-373">1. projekt</span><span class="sxs-lookup"><span data-stu-id="2873e-373">Project 1</span></span></td>
<td><span data-ttu-id="2873e-374">3</span><span class="sxs-lookup"><span data-stu-id="2873e-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2873e-375">Proj 2</span></span></td>
<td><span data-ttu-id="2873e-376">2. projekt</span><span class="sxs-lookup"><span data-stu-id="2873e-376">Project 2</span></span></td>
<td><span data-ttu-id="2873e-377">1</span><span class="sxs-lookup"><span data-stu-id="2873e-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-378">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="2873e-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-379">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-379">Cost object</span></span></th>
<th><span data-ttu-id="2873e-380">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="2873e-380">Cost element</span></span></th>
<th><span data-ttu-id="2873e-381">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-381">Cost behavior</span></span></th>
<th><span data-ttu-id="2873e-382">Egységek</span><span class="sxs-lookup"><span data-stu-id="2873e-382">Units</span></span></th>
<th><span data-ttu-id="2873e-383">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="2873e-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-384">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-384">CC001</span></span></td>
<td><span data-ttu-id="2873e-385">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-385">HR</span></span></td>
<td><span data-ttu-id="2873e-386">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-386">10001</span></span></td>
<td><span data-ttu-id="2873e-387">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-387">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-388">1</span><span class="sxs-lookup"><span data-stu-id="2873e-388">1</span></span></td>
<td><span data-ttu-id="2873e-389">10</span><span class="sxs-lookup"><span data-stu-id="2873e-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-390">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="2873e-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-391">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-391">Cost object</span></span></th>
<th><span data-ttu-id="2873e-392">Nagyság</span><span class="sxs-lookup"><span data-stu-id="2873e-392">Magnitude</span></span></th>
<th><span data-ttu-id="2873e-393">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="2873e-393">Cost element</span></span></th>
<th><span data-ttu-id="2873e-394">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="2873e-394">Allocation factor</span></span></th>
<th><span data-ttu-id="2873e-395">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2873e-396">Proj 1</span></span></td>
<td><span data-ttu-id="2873e-397">1. projekt</span><span class="sxs-lookup"><span data-stu-id="2873e-397">Project 1</span></span></td>
<td><span data-ttu-id="2873e-398">3</span><span class="sxs-lookup"><span data-stu-id="2873e-398">3</span></span></td>
<td><span data-ttu-id="2873e-399">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-399">10001</span></span></td>
<td><span data-ttu-id="2873e-400">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="2873e-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="2873e-401">30.00</span><span class="sxs-lookup"><span data-stu-id="2873e-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2873e-402">Proj 2</span></span></td>
<td><span data-ttu-id="2873e-403">2. projekt</span><span class="sxs-lookup"><span data-stu-id="2873e-403">Project 2</span></span></td>
<td><span data-ttu-id="2873e-404">1</span><span class="sxs-lookup"><span data-stu-id="2873e-404">1</span></span></td>
<td><span data-ttu-id="2873e-405">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-405">10001</span></span></td>
<td><span data-ttu-id="2873e-406">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="2873e-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="2873e-407">10.00</span><span class="sxs-lookup"><span data-stu-id="2873e-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="2873e-408">Napló</span><span class="sxs-lookup"><span data-stu-id="2873e-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2873e-409">Napló</span><span class="sxs-lookup"><span data-stu-id="2873e-409">Journal</span></span></th>
<th><span data-ttu-id="2873e-410">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="2873e-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2873e-411">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2873e-412">Verzió</span><span class="sxs-lookup"><span data-stu-id="2873e-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-413">00003</span><span class="sxs-lookup"><span data-stu-id="2873e-413">00003</span></span></td>
<td><span data-ttu-id="2873e-414">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="2873e-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="2873e-415">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="2873e-415">Fiscal</span></span></td>
<td><span data-ttu-id="2873e-416">2017</span><span class="sxs-lookup"><span data-stu-id="2873e-416">2017</span></span></td>
<td><span data-ttu-id="2873e-417">1. időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-417">Period 1</span></span></td>
<td><span data-ttu-id="2873e-418">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="2873e-419">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="2873e-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2873e-420">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="2873e-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-421">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-421">Cost object</span></span></th>
<th><span data-ttu-id="2873e-422">Nagyság</span><span class="sxs-lookup"><span data-stu-id="2873e-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-423">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2873e-424">Proj 1</span></span></td>
<td><span data-ttu-id="2873e-425">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="2873e-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="2873e-426">3,00</span><span class="sxs-lookup"><span data-stu-id="2873e-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-427">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2873e-428">Proj 2</span></span></td>
<td><span data-ttu-id="2873e-429">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="2873e-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="2873e-430">1.00</span><span class="sxs-lookup"><span data-stu-id="2873e-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2873e-431">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="2873e-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-432">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-433">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="2873e-433">Cost element</span></span></th>
<th><span data-ttu-id="2873e-434">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-434">Cost behavior</span></span></th>
<th><span data-ttu-id="2873e-435">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-435">Amount</span></span></th>
<th><span data-ttu-id="2873e-436">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="2873e-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="2873e-437">CC0001</span></span></td>
<td><span data-ttu-id="2873e-438">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-438">HR</span></span></td>
<td><span data-ttu-id="2873e-439">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-439">10001</span></span></td>
<td><span data-ttu-id="2873e-440">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-440">Electricity</span></span></td>
<td><span data-ttu-id="2873e-441">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-441">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-442">-30.00</span><span class="sxs-lookup"><span data-stu-id="2873e-442">-30.00</span></span></td>
<td><span data-ttu-id="2873e-443">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2873e-444">Proj 1</span></span></td>
<td><span data-ttu-id="2873e-445">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="2873e-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="2873e-446">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-446">10001</span></span></td>
<td><span data-ttu-id="2873e-447">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-447">Electricity</span></span></td>
<td><span data-ttu-id="2873e-448">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-448">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-449">30.00</span><span class="sxs-lookup"><span data-stu-id="2873e-449">30.00</span></span></td>
<td><span data-ttu-id="2873e-450">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-451">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-451">CC001</span></span></td>
<td><span data-ttu-id="2873e-452">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-452">HR</span></span></td>
<td><span data-ttu-id="2873e-453">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-453">10001</span></span></td>
<td><span data-ttu-id="2873e-454">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-454">Electricity</span></span></td>
<td><span data-ttu-id="2873e-455">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-455">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="2873e-456">-10.00</span></span></td>
<td><span data-ttu-id="2873e-457">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2873e-458">Proj 2</span></span></td>
<td><span data-ttu-id="2873e-459">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="2873e-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="2873e-460">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-460">10001</span></span></td>
<td><span data-ttu-id="2873e-461">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-461">Electricity</span></span></td>
<td><span data-ttu-id="2873e-462">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-462">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-463">10,00</span><span class="sxs-lookup"><span data-stu-id="2873e-463">10.00</span></span></td>
<td><span data-ttu-id="2873e-464">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-465">További információ: [Járulékosköltség-számítás végrehajtása](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="2873e-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="2873e-466">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="2873e-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="2873e-467">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="2873e-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="2873e-468">A Finance a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="2873e-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="2873e-469">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="2873e-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="2873e-470">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="2873e-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="2873e-471">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="2873e-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="2873e-472">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="2873e-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="2873e-473">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="2873e-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="2873e-474">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="2873e-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="2873e-475">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="2873e-475">Define the cost allocation</span></span>

<span data-ttu-id="2873e-476">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="2873e-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="2873e-477">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="2873e-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="2873e-478">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="2873e-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-479">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-479">Cost object</span></span></th>
<th><span data-ttu-id="2873e-480">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="2873e-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-481">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-481">CC002</span></span></td>
<td><span data-ttu-id="2873e-482">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-482">Finance</span></span></td>
<td><span data-ttu-id="2873e-483">35</span><span class="sxs-lookup"><span data-stu-id="2873e-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-484">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-484">CC003</span></span></td>
<td><span data-ttu-id="2873e-485">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-485">Assembly</span></span></td>
<td><span data-ttu-id="2873e-486">55</span><span class="sxs-lookup"><span data-stu-id="2873e-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-487">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-487">CC004</span></span></td>
<td><span data-ttu-id="2873e-488">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-488">Packaging</span></span></td>
<td><span data-ttu-id="2873e-489">10</span><span class="sxs-lookup"><span data-stu-id="2873e-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-490">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="2873e-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="2873e-491">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="2873e-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-492">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-492">Cost object</span></span></th>
<th><span data-ttu-id="2873e-493">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="2873e-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-494">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-494">CC003</span></span></td>
<td><span data-ttu-id="2873e-495">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-495">Assembly</span></span></td>
<td><span data-ttu-id="2873e-496">65</span><span class="sxs-lookup"><span data-stu-id="2873e-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-497">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-497">CC004</span></span></td>
<td><span data-ttu-id="2873e-498">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-498">Packaging</span></span></td>
<td><span data-ttu-id="2873e-499">35</span><span class="sxs-lookup"><span data-stu-id="2873e-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-500">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="2873e-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="2873e-501">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="2873e-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-502">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-502">Cost object</span></span></th>
<th><span data-ttu-id="2873e-503">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="2873e-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-504">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-504">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-505">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-505">Product 1</span></span></td>
<td><span data-ttu-id="2873e-506">60</span><span class="sxs-lookup"><span data-stu-id="2873e-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-507">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-507">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-508">2. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-508">Product 2</span></span></td>
<td><span data-ttu-id="2873e-509">20</span><span class="sxs-lookup"><span data-stu-id="2873e-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-510">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="2873e-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="2873e-511">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="2873e-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-512">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-512">Cost object</span></span></th>
<th><span data-ttu-id="2873e-513">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="2873e-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-514">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-514">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-515">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-515">Product 1</span></span></td>
<td><span data-ttu-id="2873e-516">80</span><span class="sxs-lookup"><span data-stu-id="2873e-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-517">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-517">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-518">2. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-518">Product 2</span></span></td>
<td><span data-ttu-id="2873e-519">15</span><span class="sxs-lookup"><span data-stu-id="2873e-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="2873e-520">A statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="2873e-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="2873e-521">További információk: [Statisztikaimérték-szolgáltató sablon](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="2873e-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="2873e-522">Az alábbi táblázat azt az eredményt mutatja, amikor a HR szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="2873e-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-523">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-523">Cost object</span></span></th>
<th><span data-ttu-id="2873e-524">Nagyság</span><span class="sxs-lookup"><span data-stu-id="2873e-524">Magnitude</span></span></th>
<th><span data-ttu-id="2873e-525">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="2873e-525">Allocation factor</span></span></th>
<th><span data-ttu-id="2873e-526">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-526">Amount</span></span></th>
<th><span data-ttu-id="2873e-527">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-528">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-528">CC002</span></span></td>
<td><span data-ttu-id="2873e-529">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-529">Finance</span></span></td>
<td><span data-ttu-id="2873e-530">35</span><span class="sxs-lookup"><span data-stu-id="2873e-530">35</span></span></td>
<td><span data-ttu-id="2873e-531">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="2873e-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2873e-532">175.00</span><span class="sxs-lookup"><span data-stu-id="2873e-532">175.00</span></span></td>
<td><span data-ttu-id="2873e-533">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-534">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-534">CC003</span></span></td>
<td><span data-ttu-id="2873e-535">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-535">Assembly</span></span></td>
<td><span data-ttu-id="2873e-536">55</span><span class="sxs-lookup"><span data-stu-id="2873e-536">55</span></span></td>
<td><span data-ttu-id="2873e-537">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="2873e-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2873e-538">275.00</span><span class="sxs-lookup"><span data-stu-id="2873e-538">275.00</span></span></td>
<td><span data-ttu-id="2873e-539">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-540">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-540">CC004</span></span></td>
<td><span data-ttu-id="2873e-541">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-541">Packaging</span></span></td>
<td><span data-ttu-id="2873e-542">10</span><span class="sxs-lookup"><span data-stu-id="2873e-542">10</span></span></td>
<td><span data-ttu-id="2873e-543">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="2873e-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="2873e-544">50,00</span><span class="sxs-lookup"><span data-stu-id="2873e-544">50.00</span></span></td>
<td><span data-ttu-id="2873e-545">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-546">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-546">CC002</span></span></td>
<td><span data-ttu-id="2873e-547">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-547">Finance</span></span></td>
<td><span data-ttu-id="2873e-548">35</span><span class="sxs-lookup"><span data-stu-id="2873e-548">35</span></span></td>
<td><span data-ttu-id="2873e-549">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="2873e-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2873e-550">436.00</span><span class="sxs-lookup"><span data-stu-id="2873e-550">436.00</span></span></td>
<td><span data-ttu-id="2873e-551">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-552">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-552">CC003</span></span></td>
<td><span data-ttu-id="2873e-553">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-553">Assembly</span></span></td>
<td><span data-ttu-id="2873e-554">55</span><span class="sxs-lookup"><span data-stu-id="2873e-554">55</span></span></td>
<td><span data-ttu-id="2873e-555">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="2873e-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2873e-556">685.14</span><span class="sxs-lookup"><span data-stu-id="2873e-556">685.14</span></span></td>
<td><span data-ttu-id="2873e-557">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-558">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-558">CC004</span></span></td>
<td><span data-ttu-id="2873e-559">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-559">Packaging</span></span></td>
<td><span data-ttu-id="2873e-560">10</span><span class="sxs-lookup"><span data-stu-id="2873e-560">10</span></span></td>
<td><span data-ttu-id="2873e-561">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="2873e-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="2873e-562">124.57</span><span class="sxs-lookup"><span data-stu-id="2873e-562">124.57</span></span></td>
<td><span data-ttu-id="2873e-563">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-564">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="2873e-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-565">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-565">Cost object</span></span></th>
<th><span data-ttu-id="2873e-566">Nagyság</span><span class="sxs-lookup"><span data-stu-id="2873e-566">Magnitude</span></span></th>
<th><span data-ttu-id="2873e-567">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="2873e-567">Allocation factor</span></span></th>
<th><span data-ttu-id="2873e-568">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-568">Amount</span></span></th>
<th><span data-ttu-id="2873e-569">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-570">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-570">CC003</span></span></td>
<td><span data-ttu-id="2873e-571">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-571">Assembly</span></span></td>
<td><span data-ttu-id="2873e-572">65</span><span class="sxs-lookup"><span data-stu-id="2873e-572">65</span></span></td>
<td><span data-ttu-id="2873e-573">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="2873e-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="2873e-574">438.75</span><span class="sxs-lookup"><span data-stu-id="2873e-574">438.75</span></span></td>
<td><span data-ttu-id="2873e-575">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-576">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-576">CC004</span></span></td>
<td><span data-ttu-id="2873e-577">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-577">Packaging</span></span></td>
<td><span data-ttu-id="2873e-578">35</span><span class="sxs-lookup"><span data-stu-id="2873e-578">35</span></span></td>
<td><span data-ttu-id="2873e-579">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="2873e-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="2873e-580">236.25</span><span class="sxs-lookup"><span data-stu-id="2873e-580">236.25</span></span></td>
<td><span data-ttu-id="2873e-581">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-582">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-582">CC003</span></span></td>
<td><span data-ttu-id="2873e-583">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-583">Assembly</span></span></td>
<td><span data-ttu-id="2873e-584">65</span><span class="sxs-lookup"><span data-stu-id="2873e-584">65</span></span></td>
<td><span data-ttu-id="2873e-585">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="2873e-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="2873e-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="2873e-586">5,297.69</span></span></td>
<td><span data-ttu-id="2873e-587">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-588">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-588">CC004</span></span></td>
<td><span data-ttu-id="2873e-589">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-589">Packaging</span></span></td>
<td><span data-ttu-id="2873e-590">35</span><span class="sxs-lookup"><span data-stu-id="2873e-590">35</span></span></td>
<td><span data-ttu-id="2873e-591">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="2873e-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="2873e-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="2873e-592">2,852.60</span></span></td>
<td><span data-ttu-id="2873e-593">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-594">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="2873e-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-595">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-595">Cost object</span></span></th>
<th><span data-ttu-id="2873e-596">Nagyság</span><span class="sxs-lookup"><span data-stu-id="2873e-596">Magnitude</span></span></th>
<th><span data-ttu-id="2873e-597">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="2873e-597">Allocation factor</span></span></th>
<th><span data-ttu-id="2873e-598">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-598">Amount</span></span></th>
<th><span data-ttu-id="2873e-599">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-600">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-600">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-601">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-601">Product 1</span></span></td>
<td><span data-ttu-id="2873e-602">60</span><span class="sxs-lookup"><span data-stu-id="2873e-602">60</span></span></td>
<td><span data-ttu-id="2873e-603">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="2873e-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="2873e-604">535.31</span><span class="sxs-lookup"><span data-stu-id="2873e-604">535.31</span></span></td>
<td><span data-ttu-id="2873e-605">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-606">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-606">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-607">2. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-607">Product 2</span></span></td>
<td><span data-ttu-id="2873e-608">20</span><span class="sxs-lookup"><span data-stu-id="2873e-608">20</span></span></td>
<td><span data-ttu-id="2873e-609">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="2873e-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="2873e-610">178.44</span><span class="sxs-lookup"><span data-stu-id="2873e-610">178.44</span></span></td>
<td><span data-ttu-id="2873e-611">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-612">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-612">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-613">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-613">Product 1</span></span></td>
<td><span data-ttu-id="2873e-614">60</span><span class="sxs-lookup"><span data-stu-id="2873e-614">60</span></span></td>
<td><span data-ttu-id="2873e-615">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="2873e-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="2873e-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="2873e-616">4,487.12</span></span></td>
<td><span data-ttu-id="2873e-617">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-618">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-618">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-619">2. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-619">Product 2</span></span></td>
<td><span data-ttu-id="2873e-620">20</span><span class="sxs-lookup"><span data-stu-id="2873e-620">20</span></span></td>
<td><span data-ttu-id="2873e-621">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="2873e-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="2873e-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="2873e-622">1,495.71</span></span></td>
<td><span data-ttu-id="2873e-623">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="2873e-624">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="2873e-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-625">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-625">Cost object</span></span></th>
<th><span data-ttu-id="2873e-626">Nagyság</span><span class="sxs-lookup"><span data-stu-id="2873e-626">Magnitude</span></span></th>
<th><span data-ttu-id="2873e-627">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="2873e-627">Allocation factor</span></span></th>
<th><span data-ttu-id="2873e-628">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-628">Amount</span></span></th>
<th><span data-ttu-id="2873e-629">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-630">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-630">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-631">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-631">Product 1</span></span></td>
<td><span data-ttu-id="2873e-632">80</span><span class="sxs-lookup"><span data-stu-id="2873e-632">80</span></span></td>
<td><span data-ttu-id="2873e-633">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="2873e-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="2873e-634">241.05</span><span class="sxs-lookup"><span data-stu-id="2873e-634">241.05</span></span></td>
<td><span data-ttu-id="2873e-635">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-636">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-636">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-637">2. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-637">Product 2</span></span></td>
<td><span data-ttu-id="2873e-638">15.</span><span class="sxs-lookup"><span data-stu-id="2873e-638">15</span></span></td>
<td><span data-ttu-id="2873e-639">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="2873e-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="2873e-640">45.20</span><span class="sxs-lookup"><span data-stu-id="2873e-640">45.20</span></span></td>
<td><span data-ttu-id="2873e-641">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-642">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-642">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-643">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-643">Product 1</span></span></td>
<td><span data-ttu-id="2873e-644">80</span><span class="sxs-lookup"><span data-stu-id="2873e-644">80</span></span></td>
<td><span data-ttu-id="2873e-645">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="2873e-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="2873e-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="2873e-646">2,507.09</span></span></td>
<td><span data-ttu-id="2873e-647">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-648">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-648">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-649">2. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-649">Product 2</span></span></td>
<td><span data-ttu-id="2873e-650">15.</span><span class="sxs-lookup"><span data-stu-id="2873e-650">15</span></span></td>
<td><span data-ttu-id="2873e-651">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="2873e-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="2873e-652">470.08</span><span class="sxs-lookup"><span data-stu-id="2873e-652">470.08</span></span></td>
<td><span data-ttu-id="2873e-653">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="2873e-654">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="2873e-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2873e-655">Napló</span><span class="sxs-lookup"><span data-stu-id="2873e-655">Journal</span></span></th>
<th><span data-ttu-id="2873e-656">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="2873e-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="2873e-657">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="2873e-658">Verzió</span><span class="sxs-lookup"><span data-stu-id="2873e-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-659">00004</span><span class="sxs-lookup"><span data-stu-id="2873e-659">00004</span></span></td>
<td><span data-ttu-id="2873e-660">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="2873e-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="2873e-661">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="2873e-661">Fiscal</span></span></td>
<td><span data-ttu-id="2873e-662">2017</span><span class="sxs-lookup"><span data-stu-id="2873e-662">2017</span></span></td>
<td><span data-ttu-id="2873e-663">1. időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-663">Period 1</span></span></td>
<td><span data-ttu-id="2873e-664">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="2873e-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="2873e-665">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="2873e-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="2873e-666">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="2873e-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-667">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-668">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="2873e-668">Cost element</span></span></th>
<th><span data-ttu-id="2873e-669">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-669">Cost behavior</span></span></th>
<th><span data-ttu-id="2873e-670">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-671">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-672">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-672">CC001</span></span></td>
<td><span data-ttu-id="2873e-673">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-673">HR</span></span></td>
<td><span data-ttu-id="2873e-674">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-674">10001</span></span></td>
<td><span data-ttu-id="2873e-675">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-675">Electricity</span></span></td>
<td><span data-ttu-id="2873e-676">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-676">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-677">500.00</span><span class="sxs-lookup"><span data-stu-id="2873e-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-678">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-679">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-679">CC001</span></span></td>
<td><span data-ttu-id="2873e-680">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-680">HR</span></span></td>
<td><span data-ttu-id="2873e-681">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-681">10001</span></span></td>
<td><span data-ttu-id="2873e-682">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-682">Electricity</span></span></td>
<td><span data-ttu-id="2873e-683">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-683">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="2873e-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-685">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-686">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-686">CC002</span></span></td>
<td><span data-ttu-id="2873e-687">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-687">Finance</span></span></td>
<td><span data-ttu-id="2873e-688">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-688">10001</span></span></td>
<td><span data-ttu-id="2873e-689">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-689">Electricity</span></span></td>
<td><span data-ttu-id="2873e-690">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-690">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-691">675.00</span><span class="sxs-lookup"><span data-stu-id="2873e-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-692">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-693">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-693">CC002</span></span></td>
<td><span data-ttu-id="2873e-694">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-694">Finance</span></span></td>
<td><span data-ttu-id="2873e-695">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-695">10001</span></span></td>
<td><span data-ttu-id="2873e-696">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-696">Electricity</span></span></td>
<td><span data-ttu-id="2873e-697">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-697">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="2873e-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-699">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-700">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-700">CC003</span></span></td>
<td><span data-ttu-id="2873e-701">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-701">Assembly</span></span></td>
<td><span data-ttu-id="2873e-702">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-702">10001</span></span></td>
<td><span data-ttu-id="2873e-703">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-703">Electricity</span></span></td>
<td><span data-ttu-id="2873e-704">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-704">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-705">713.75</span><span class="sxs-lookup"><span data-stu-id="2873e-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-706">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-707">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-707">CC003</span></span></td>
<td><span data-ttu-id="2873e-708">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-708">Assembly</span></span></td>
<td><span data-ttu-id="2873e-709">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-709">10001</span></span></td>
<td><span data-ttu-id="2873e-710">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-710">Electricity</span></span></td>
<td><span data-ttu-id="2873e-711">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-711">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="2873e-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-713">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-714">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-714">CC003</span></span></td>
<td><span data-ttu-id="2873e-715">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-715">Packaging</span></span></td>
<td><span data-ttu-id="2873e-716">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-716">10001</span></span></td>
<td><span data-ttu-id="2873e-717">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-717">Electricity</span></span></td>
<td><span data-ttu-id="2873e-718">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-718">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-719">286.25</span><span class="sxs-lookup"><span data-stu-id="2873e-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-720">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-721">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-721">CC003</span></span></td>
<td><span data-ttu-id="2873e-722">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-722">Packaging</span></span></td>
<td><span data-ttu-id="2873e-723">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-723">10001</span></span></td>
<td><span data-ttu-id="2873e-724">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-724">Electricity</span></span></td>
<td><span data-ttu-id="2873e-725">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-725">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="2873e-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-727">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-728">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-728">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-729">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-729">Product 1</span></span></td>
<td><span data-ttu-id="2873e-730">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-730">10001</span></span></td>
<td><span data-ttu-id="2873e-731">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-731">Electricity</span></span></td>
<td><span data-ttu-id="2873e-732">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-732">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-733">776.36</span><span class="sxs-lookup"><span data-stu-id="2873e-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-734">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-735">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-735">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-736">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-736">Product 1</span></span></td>
<td><span data-ttu-id="2873e-737">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-737">10001</span></span></td>
<td><span data-ttu-id="2873e-738">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-738">Electricity</span></span></td>
<td><span data-ttu-id="2873e-739">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-739">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="2873e-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-741">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-742">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-742">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-743">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-743">Product 1</span></span></td>
<td><span data-ttu-id="2873e-744">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-744">10001</span></span></td>
<td><span data-ttu-id="2873e-745">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-745">Electricity</span></span></td>
<td><span data-ttu-id="2873e-746">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-746">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-747">223.64</span><span class="sxs-lookup"><span data-stu-id="2873e-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-748">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="2873e-749">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-749">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-750">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-750">Product 1</span></span></td>
<td><span data-ttu-id="2873e-751">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-751">10001</span></span></td>
<td><span data-ttu-id="2873e-752">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-752">Electricity</span></span></td>
<td><span data-ttu-id="2873e-753">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-753">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="2873e-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="2873e-755">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="2873e-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="2873e-756">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="2873e-757">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="2873e-757">Cost element</span></span></th>
<th><span data-ttu-id="2873e-758">Költség működése</span><span class="sxs-lookup"><span data-stu-id="2873e-758">Cost behavior</span></span></th>
<th><span data-ttu-id="2873e-759">Összeg</span><span class="sxs-lookup"><span data-stu-id="2873e-759">Amount</span></span></th>
<th><span data-ttu-id="2873e-760">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="2873e-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="2873e-761">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-761">CC001</span></span></td>
<td><span data-ttu-id="2873e-762">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-762">HR</span></span></td>
<td><span data-ttu-id="2873e-763">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-763">10001</span></span></td>
<td><span data-ttu-id="2873e-764">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-764">Electricity</span></span></td>
<td><span data-ttu-id="2873e-765">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-765">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="2873e-766">-500.00</span></span></td>
<td><span data-ttu-id="2873e-767">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-768">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-768">CC002</span></span></td>
<td><span data-ttu-id="2873e-769">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-769">Finance</span></span></td>
<td><span data-ttu-id="2873e-770">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-770">10001</span></span></td>
<td><span data-ttu-id="2873e-771">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-771">Electricity</span></span></td>
<td><span data-ttu-id="2873e-772">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-772">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-773">175.00</span><span class="sxs-lookup"><span data-stu-id="2873e-773">175.00</span></span></td>
<td><span data-ttu-id="2873e-774">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-775">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-775">CC003</span></span></td>
<td><span data-ttu-id="2873e-776">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-776">Assembly</span></span></td>
<td><span data-ttu-id="2873e-777">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-777">10001</span></span></td>
<td><span data-ttu-id="2873e-778">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-778">Electricity</span></span></td>
<td><span data-ttu-id="2873e-779">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-779">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-780">275.00</span><span class="sxs-lookup"><span data-stu-id="2873e-780">275.00</span></span></td>
<td><span data-ttu-id="2873e-781">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-782">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-782">CC004</span></span></td>
<td><span data-ttu-id="2873e-783">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-783">Packaging</span></span></td>
<td><span data-ttu-id="2873e-784">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-784">10001</span></span></td>
<td><span data-ttu-id="2873e-785">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-785">Electricity</span></span></td>
<td><span data-ttu-id="2873e-786">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-786">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-787">50,00</span><span class="sxs-lookup"><span data-stu-id="2873e-787">50,00</span></span></td>
<td><span data-ttu-id="2873e-788">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-789">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-789">CC001</span></span></td>
<td><span data-ttu-id="2873e-790">HR</span><span class="sxs-lookup"><span data-stu-id="2873e-790">HR</span></span></td>
<td><span data-ttu-id="2873e-791">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-791">10001</span></span></td>
<td><span data-ttu-id="2873e-792">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-792">Electricity</span></span></td>
<td><span data-ttu-id="2873e-793">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-793">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-794">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="2873e-794">-1,245.71</span></span></td>
<td><span data-ttu-id="2873e-795">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-796">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-796">CC002</span></span></td>
<td><span data-ttu-id="2873e-797">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-797">Finance</span></span></td>
<td><span data-ttu-id="2873e-798">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-798">10001</span></span></td>
<td><span data-ttu-id="2873e-799">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-799">Electricity</span></span></td>
<td><span data-ttu-id="2873e-800">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-800">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-801">436.00</span><span class="sxs-lookup"><span data-stu-id="2873e-801">436.00</span></span></td>
<td><span data-ttu-id="2873e-802">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-803">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-803">CC003</span></span></td>
<td><span data-ttu-id="2873e-804">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-804">Assembly</span></span></td>
<td><span data-ttu-id="2873e-805">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-805">10001</span></span></td>
<td><span data-ttu-id="2873e-806">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-806">Electricity</span></span></td>
<td><span data-ttu-id="2873e-807">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-807">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-808">685.14</span><span class="sxs-lookup"><span data-stu-id="2873e-808">685.14</span></span></td>
<td><span data-ttu-id="2873e-809">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-810">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-810">CC004</span></span></td>
<td><span data-ttu-id="2873e-811">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-811">Packaging</span></span></td>
<td><span data-ttu-id="2873e-812">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-812">10001</span></span></td>
<td><span data-ttu-id="2873e-813">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-813">Electricity</span></span></td>
<td><span data-ttu-id="2873e-814">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-814">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-815">124.57</span><span class="sxs-lookup"><span data-stu-id="2873e-815">124.57</span></span></td>
<td><span data-ttu-id="2873e-816">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-817">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-817">CC002</span></span></td>
<td><span data-ttu-id="2873e-818">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-818">Finance</span></span></td>
<td><span data-ttu-id="2873e-819">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-819">10001</span></span></td>
<td><span data-ttu-id="2873e-820">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-820">Electricity</span></span></td>
<td><span data-ttu-id="2873e-821">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-821">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-822">-675.00</span><span class="sxs-lookup"><span data-stu-id="2873e-822">-675.00</span></span></td>
<td><span data-ttu-id="2873e-823">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-824">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-824">CC003</span></span></td>
<td><span data-ttu-id="2873e-825">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-825">Assembly</span></span></td>
<td><span data-ttu-id="2873e-826">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-826">10001</span></span></td>
<td><span data-ttu-id="2873e-827">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-827">Electricity</span></span></td>
<td><span data-ttu-id="2873e-828">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-828">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-829">438.75</span><span class="sxs-lookup"><span data-stu-id="2873e-829">438.75</span></span></td>
<td><span data-ttu-id="2873e-830">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-831">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-831">CC004</span></span></td>
<td><span data-ttu-id="2873e-832">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-832">Packaging</span></span></td>
<td><span data-ttu-id="2873e-833">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-833">10001</span></span></td>
<td><span data-ttu-id="2873e-834">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-834">Electricity</span></span></td>
<td><span data-ttu-id="2873e-835">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-835">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-836">236.25</span><span class="sxs-lookup"><span data-stu-id="2873e-836">236.25</span></span></td>
<td><span data-ttu-id="2873e-837">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-838">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-838">CC002</span></span></td>
<td><span data-ttu-id="2873e-839">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="2873e-839">Finance</span></span></td>
<td><span data-ttu-id="2873e-840">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-840">10001</span></span></td>
<td><span data-ttu-id="2873e-841">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-841">Electricity</span></span></td>
<td><span data-ttu-id="2873e-842">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-842">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-843">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="2873e-843">-8,150.29</span></span></td>
<td><span data-ttu-id="2873e-844">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-845">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-845">CC003</span></span></td>
<td><span data-ttu-id="2873e-846">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-846">Assembly</span></span></td>
<td><span data-ttu-id="2873e-847">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-847">10001</span></span></td>
<td><span data-ttu-id="2873e-848">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-848">Electricity</span></span></td>
<td><span data-ttu-id="2873e-849">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-849">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="2873e-850">5,297.69</span></span></td>
<td><span data-ttu-id="2873e-851">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-852">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-852">CC004</span></span></td>
<td><span data-ttu-id="2873e-853">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="2873e-853">Packaging</span></span></td>
<td><span data-ttu-id="2873e-854">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-854">10001</span></span></td>
<td><span data-ttu-id="2873e-855">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-855">Electricity</span></span></td>
<td><span data-ttu-id="2873e-856">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-856">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="2873e-857">2,852.60</span></span></td>
<td><span data-ttu-id="2873e-858">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-859">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-859">CC003</span></span></td>
<td><span data-ttu-id="2873e-860">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-860">Assembly</span></span></td>
<td><span data-ttu-id="2873e-861">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-861">10001</span></span></td>
<td><span data-ttu-id="2873e-862">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-862">Electricity</span></span></td>
<td><span data-ttu-id="2873e-863">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-863">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-864">-713.75</span><span class="sxs-lookup"><span data-stu-id="2873e-864">-713.75</span></span></td>
<td><span data-ttu-id="2873e-865">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-866">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-866">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-867">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-867">Product 1</span></span></td>
<td><span data-ttu-id="2873e-868">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-868">10001</span></span></td>
<td><span data-ttu-id="2873e-869">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-869">Electricity</span></span></td>
<td><span data-ttu-id="2873e-870">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-870">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-871">535.31</span><span class="sxs-lookup"><span data-stu-id="2873e-871">535.31</span></span></td>
<td><span data-ttu-id="2873e-872">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-873">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-873">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-874">2. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-874">Product 2</span></span></td>
<td><span data-ttu-id="2873e-875">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-875">10001</span></span></td>
<td><span data-ttu-id="2873e-876">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-876">Electricity</span></span></td>
<td><span data-ttu-id="2873e-877">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-877">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-878">178.44</span><span class="sxs-lookup"><span data-stu-id="2873e-878">178.44</span></span></td>
<td><span data-ttu-id="2873e-879">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-880">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-880">CC003</span></span></td>
<td><span data-ttu-id="2873e-881">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-881">Assembly</span></span></td>
<td><span data-ttu-id="2873e-882">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-882">10001</span></span></td>
<td><span data-ttu-id="2873e-883">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-883">Electricity</span></span></td>
<td><span data-ttu-id="2873e-884">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-884">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-885">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="2873e-885">-5,982.83</span></span></td>
<td><span data-ttu-id="2873e-886">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-887">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-887">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-888">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-888">Product 1</span></span></td>
<td><span data-ttu-id="2873e-889">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-889">10001</span></span></td>
<td><span data-ttu-id="2873e-890">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-890">Electricity</span></span></td>
<td><span data-ttu-id="2873e-891">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-891">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="2873e-892">4,487.12</span></span></td>
<td><span data-ttu-id="2873e-893">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-894">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-894">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-895">2. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-895">Product 2</span></span></td>
<td><span data-ttu-id="2873e-896">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-896">10001</span></span></td>
<td><span data-ttu-id="2873e-897">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-897">Electricity</span></span></td>
<td><span data-ttu-id="2873e-898">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-898">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="2873e-899">1,495.71</span></span></td>
<td><span data-ttu-id="2873e-900">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-901">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-901">CC003</span></span></td>
<td><span data-ttu-id="2873e-902">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-902">Assembly</span></span></td>
<td><span data-ttu-id="2873e-903">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-903">10001</span></span></td>
<td><span data-ttu-id="2873e-904">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-904">Electricity</span></span></td>
<td><span data-ttu-id="2873e-905">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-905">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-906">-286.25</span><span class="sxs-lookup"><span data-stu-id="2873e-906">-286.25</span></span></td>
<td><span data-ttu-id="2873e-907">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-908">Term 1</span><span class="sxs-lookup"><span data-stu-id="2873e-908">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-909">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-909">Product 1</span></span></td>
<td><span data-ttu-id="2873e-910">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-910">10001</span></span></td>
<td><span data-ttu-id="2873e-911">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-911">Electricity</span></span></td>
<td><span data-ttu-id="2873e-912">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-912">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-913">241.05</span><span class="sxs-lookup"><span data-stu-id="2873e-913">241.05</span></span></td>
<td><span data-ttu-id="2873e-914">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-915">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-915">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-916">2. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-916">Product 2</span></span></td>
<td><span data-ttu-id="2873e-917">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-917">10001</span></span></td>
<td><span data-ttu-id="2873e-918">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-918">Electricity</span></span></td>
<td><span data-ttu-id="2873e-919">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-919">Fixed cost</span></span></td>
<td><span data-ttu-id="2873e-920">45.20</span><span class="sxs-lookup"><span data-stu-id="2873e-920">45.20</span></span></td>
<td><span data-ttu-id="2873e-921">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-922">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-922">CC003</span></span></td>
<td><span data-ttu-id="2873e-923">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="2873e-923">Assembly</span></span></td>
<td><span data-ttu-id="2873e-924">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-924">10001</span></span></td>
<td><span data-ttu-id="2873e-925">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-925">Electricity</span></span></td>
<td><span data-ttu-id="2873e-926">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-926">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-927">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="2873e-927">-2,977.17</span></span></td>
<td><span data-ttu-id="2873e-928">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-929">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-929">Prod 1</span></span></td>
<td><span data-ttu-id="2873e-930">1. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-930">Product 1</span></span></td>
<td><span data-ttu-id="2873e-931">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-931">10001</span></span></td>
<td><span data-ttu-id="2873e-932">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-932">Electricity</span></span></td>
<td><span data-ttu-id="2873e-933">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-933">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="2873e-934">2,507.09</span></span></td>
<td><span data-ttu-id="2873e-935">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2873e-936">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-936">Prod 2</span></span></td>
<td><span data-ttu-id="2873e-937">2. termék</span><span class="sxs-lookup"><span data-stu-id="2873e-937">Product 2</span></span></td>
<td><span data-ttu-id="2873e-938">10001</span><span class="sxs-lookup"><span data-stu-id="2873e-938">10001</span></span></td>
<td><span data-ttu-id="2873e-939">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-939">Electricity</span></span></td>
<td><span data-ttu-id="2873e-940">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-940">Variable cost</span></span></td>
<td><span data-ttu-id="2873e-941">470.08</span><span class="sxs-lookup"><span data-stu-id="2873e-941">470.08</span></span></td>
<td><span data-ttu-id="2873e-942">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="2873e-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="2873e-943">Következtetés</span><span class="sxs-lookup"><span data-stu-id="2873e-943">Conclusion</span></span>
<span data-ttu-id="2873e-944">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="2873e-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="2873e-945">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="2873e-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="2873e-946">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="2873e-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="2873e-947">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="2873e-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="2873e-948">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="2873e-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="2873e-949">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="2873e-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="2873e-950">Összesen</span><span class="sxs-lookup"><span data-stu-id="2873e-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="2873e-951">CC099</span><span class="sxs-lookup"><span data-stu-id="2873e-951">CC099</span></span></th>
<th><span data-ttu-id="2873e-952">CC001</span><span class="sxs-lookup"><span data-stu-id="2873e-952">CC001</span></span></th>
<th><span data-ttu-id="2873e-953">CC002</span><span class="sxs-lookup"><span data-stu-id="2873e-953">CC002</span></span></th>
<th><span data-ttu-id="2873e-954">CC003</span><span class="sxs-lookup"><span data-stu-id="2873e-954">CC003</span></span></th>
<th><span data-ttu-id="2873e-955">CC004</span><span class="sxs-lookup"><span data-stu-id="2873e-955">CC004</span></span></th>
<th><span data-ttu-id="2873e-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="2873e-956">Proj 1</span></span></th>
<th><span data-ttu-id="2873e-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="2873e-957">Proj 2</span></span></th>
<th><span data-ttu-id="2873e-958">Term. 1</span><span class="sxs-lookup"><span data-stu-id="2873e-958">Prod 1</span></span></th>
<th><span data-ttu-id="2873e-959">Term. 2</span><span class="sxs-lookup"><span data-stu-id="2873e-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="2873e-960">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="2873e-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="2873e-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="2873e-970">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="2873e-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-971">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="2873e-972">Fix költség</span><span class="sxs-lookup"><span data-stu-id="2873e-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-973">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-974">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-975">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-976">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-977">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="2873e-978">776.36</span><span class="sxs-lookup"><span data-stu-id="2873e-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-979">223.64</span><span class="sxs-lookup"><span data-stu-id="2873e-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="2873e-981">Változó költség</span><span class="sxs-lookup"><span data-stu-id="2873e-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-982">000</span><span class="sxs-lookup"><span data-stu-id="2873e-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-983">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-984">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-985">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-986">0,00</span><span class="sxs-lookup"><span data-stu-id="2873e-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-987">30.00</span><span class="sxs-lookup"><span data-stu-id="2873e-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-988">1000</span><span class="sxs-lookup"><span data-stu-id="2873e-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="2873e-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="2873e-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="2873e-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="2873e-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="2873e-992">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="2873e-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="2873e-993">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="2873e-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="2873e-994">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="2873e-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="2873e-995">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="2873e-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="2873e-996">A további tudnivalókat lásd: [Költségösszesítéssel kapcsolatos irányelv és járulékos költség számítása](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="2873e-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



