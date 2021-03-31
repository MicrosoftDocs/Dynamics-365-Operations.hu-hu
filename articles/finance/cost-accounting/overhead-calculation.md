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
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 882804141a6b520e2420343958c7a6b02a7e09ae
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208847"
---
# <a name="overhead-calculation"></a><span data-ttu-id="5bfd8-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="5bfd8-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5bfd8-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="5bfd8-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="5bfd8-105">Term definition</span></span>
---------------

<span data-ttu-id="5bfd8-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="5bfd8-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="5bfd8-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="5bfd8-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="5bfd8-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="5bfd8-109">Rent</span></span>
-   <span data-ttu-id="5bfd8-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-110">Electricity</span></span>
-   <span data-ttu-id="5bfd8-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="5bfd8-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="5bfd8-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-112">Overhead calculation overview</span></span>
<span data-ttu-id="5bfd8-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="5bfd8-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="5bfd8-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="5bfd8-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="5bfd8-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="5bfd8-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="5bfd8-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="5bfd8-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="5bfd8-119">Version type</span></span>
-   <span data-ttu-id="5bfd8-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-120">Date and time</span></span>
-   <span data-ttu-id="5bfd8-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="5bfd8-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="5bfd8-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="5bfd8-122">Fiscal year</span></span>
-   <span data-ttu-id="5bfd8-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-123">Fiscal period</span></span>

<span data-ttu-id="5bfd8-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="5bfd8-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="5bfd8-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="5bfd8-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="5bfd8-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="5bfd8-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="5bfd8-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="5bfd8-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="5bfd8-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="5bfd8-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="5bfd8-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="5bfd8-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="5bfd8-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="5bfd8-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="5bfd8-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bfd8-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="5bfd8-140">Main account</span></span></th>
<th><span data-ttu-id="5bfd8-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="5bfd8-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-143">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-143">CC099</span></span></td>
<td><span data-ttu-id="5bfd8-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-144">Default cost center</span></span></td>
<td><span data-ttu-id="5bfd8-145">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-145">10001</span></span></td>
<td><span data-ttu-id="5bfd8-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-146">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="5bfd8-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="5bfd8-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="5bfd8-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="5bfd8-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="5bfd8-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="5bfd8-151">Define the cost behavior rule</span></span>

<span data-ttu-id="5bfd8-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="5bfd8-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="5bfd8-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="5bfd8-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="5bfd8-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="5bfd8-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="5bfd8-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="5bfd8-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="5bfd8-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="5bfd8-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="5bfd8-159">Napló</span><span class="sxs-lookup"><span data-stu-id="5bfd8-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bfd8-160">Napló</span><span class="sxs-lookup"><span data-stu-id="5bfd8-160">Journal</span></span></th>
<th><span data-ttu-id="5bfd8-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="5bfd8-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5bfd8-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5bfd8-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="5bfd8-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-164">00001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-164">00001</span></span></td>
<td><span data-ttu-id="5bfd8-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="5bfd8-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="5bfd8-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="5bfd8-166">Fiscal</span></span></td>
<td><span data-ttu-id="5bfd8-167">2017</span><span class="sxs-lookup"><span data-stu-id="5bfd8-167">2017</span></span></td>
<td><span data-ttu-id="5bfd8-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-168">Period 1</span></span></td>
<td><span data-ttu-id="5bfd8-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5bfd8-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bfd8-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-173">Cost element</span></span></th>
<th><span data-ttu-id="5bfd8-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-174">Cost behavior</span></span></th>
<th><span data-ttu-id="5bfd8-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-177">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-177">CC099</span></span></td>
<td><span data-ttu-id="5bfd8-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-178">Default cost center</span></span></td>
<td><span data-ttu-id="5bfd8-179">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-179">10001</span></span></td>
<td><span data-ttu-id="5bfd8-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-180">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="5bfd8-181">Unclassified</span></span></td>
<td><span data-ttu-id="5bfd8-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5bfd8-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="5bfd8-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-185">Cost element</span></span></th>
<th><span data-ttu-id="5bfd8-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-186">Cost behavior</span></span></th>
<th><span data-ttu-id="5bfd8-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-187">Amount</span></span></th>
<th><span data-ttu-id="5bfd8-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-189">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-189">CC099</span></span></td>
<td><span data-ttu-id="5bfd8-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-190">Default cost center</span></span></td>
<td><span data-ttu-id="5bfd8-191">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-191">10001</span></span></td>
<td><span data-ttu-id="5bfd8-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-192">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="5bfd8-193">Unclassified</span></span></td>
<td><span data-ttu-id="5bfd8-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-194">10,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-196">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-196">CC099</span></span></td>
<td><span data-ttu-id="5bfd8-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-197">Default cost center</span></span></td>
<td><span data-ttu-id="5bfd8-198">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-198">10001</span></span></td>
<td><span data-ttu-id="5bfd8-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-199">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="5bfd8-200">Unclassified</span></span></td>
<td><span data-ttu-id="5bfd8-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-201">-10,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-203">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-203">CC099</span></span></td>
<td><span data-ttu-id="5bfd8-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-204">Default cost center</span></span></td>
<td><span data-ttu-id="5bfd8-205">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-205">10001</span></span></td>
<td><span data-ttu-id="5bfd8-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-206">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-207">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-208">1,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-210">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-210">CC099</span></span></td>
<td><span data-ttu-id="5bfd8-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-211">Default cost center</span></span></td>
<td><span data-ttu-id="5bfd8-212">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-212">10001</span></span></td>
<td><span data-ttu-id="5bfd8-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-213">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-214">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-215">9,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-217">További információért lásd: [Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="5bfd8-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="5bfd8-218">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="5bfd8-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="5bfd8-219">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="5bfd8-220">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="5bfd8-221">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="5bfd8-221">Define the cost distribution rule</span></span>

<span data-ttu-id="5bfd8-222">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="5bfd8-223">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="5bfd8-224">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="5bfd8-225">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="5bfd8-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="5bfd8-226">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="5bfd8-227">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-228">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-228">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="5bfd8-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-230">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-230">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-231">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-231">HR</span></span></td>
<td><span data-ttu-id="5bfd8-232">1000</span><span class="sxs-lookup"><span data-stu-id="5bfd8-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-233">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-233">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-234">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-234">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-235">6,000</span><span class="sxs-lookup"><span data-stu-id="5bfd8-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-236">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-236">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-237">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-237">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-238">0</span><span class="sxs-lookup"><span data-stu-id="5bfd8-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-239">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-240">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-240">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-241">Nagyság</span><span class="sxs-lookup"><span data-stu-id="5bfd8-241">Magnitude</span></span></th>
<th><span data-ttu-id="5bfd8-242">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="5bfd8-242">Allocation factor</span></span></th>
<th><span data-ttu-id="5bfd8-243">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-244">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-244">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-245">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-245">HR</span></span></td>
<td><span data-ttu-id="5bfd8-246">1000</span><span class="sxs-lookup"><span data-stu-id="5bfd8-246">1,000</span></span></td>
<td><span data-ttu-id="5bfd8-247">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="5bfd8-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-249">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-249">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-250">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-250">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-251">6,000</span><span class="sxs-lookup"><span data-stu-id="5bfd8-251">6,000</span></span></td>
<td><span data-ttu-id="5bfd8-252">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="5bfd8-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-254">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-254">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-255">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-255">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-256">0</span><span class="sxs-lookup"><span data-stu-id="5bfd8-256">0</span></span></td>
<td><span data-ttu-id="5bfd8-257">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-258">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-259">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="5bfd8-260">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: (Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-261">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-261">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-262">Receptúra</span><span class="sxs-lookup"><span data-stu-id="5bfd8-262">Formula</span></span></th>
<th><span data-ttu-id="5bfd8-263">Nagyság</span><span class="sxs-lookup"><span data-stu-id="5bfd8-263">Magnitude</span></span></th>
<th><span data-ttu-id="5bfd8-264">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="5bfd8-264">Allocation factor</span></span></th>
<th><span data-ttu-id="5bfd8-265">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-266">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-266">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-267">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-267">HR</span></span></td>
<td><span data-ttu-id="5bfd8-268">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5bfd8-269">1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-269">1</span></span></td>
<td><span data-ttu-id="5bfd8-270">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-271">500.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-272">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-272">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-273">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-273">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-274">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5bfd8-275">1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-275">1</span></span></td>
<td><span data-ttu-id="5bfd8-276">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-277">500.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-278">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-278">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-279">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-279">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-280">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="5bfd8-281">0</span><span class="sxs-lookup"><span data-stu-id="5bfd8-281">0</span></span></td>
<td><span data-ttu-id="5bfd8-282">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-283">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="5bfd8-284">Napló</span><span class="sxs-lookup"><span data-stu-id="5bfd8-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bfd8-285">Napló</span><span class="sxs-lookup"><span data-stu-id="5bfd8-285">Journal</span></span></th>
<th><span data-ttu-id="5bfd8-286">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="5bfd8-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5bfd8-287">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5bfd8-288">Verzió</span><span class="sxs-lookup"><span data-stu-id="5bfd8-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-289">00002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-289">00002</span></span></td>
<td><span data-ttu-id="5bfd8-290">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="5bfd8-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="5bfd8-291">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="5bfd8-291">Fiscal</span></span></td>
<td><span data-ttu-id="5bfd8-292">2017</span><span class="sxs-lookup"><span data-stu-id="5bfd8-292">2017</span></span></td>
<td><span data-ttu-id="5bfd8-293">1. időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-293">Period 1</span></span></td>
<td><span data-ttu-id="5bfd8-294">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5bfd8-295">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bfd8-296">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-297">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-298">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-298">Cost element</span></span></th>
<th><span data-ttu-id="5bfd8-299">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-299">Cost behavior</span></span></th>
<th><span data-ttu-id="5bfd8-300">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-301">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-302">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-302">CC099</span></span></td>
<td><span data-ttu-id="5bfd8-303">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-303">Default cost center</span></span></td>
<td><span data-ttu-id="5bfd8-304">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-304">10001</span></span></td>
<td><span data-ttu-id="5bfd8-305">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-305">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-306">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-306">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-308">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-309">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-309">CC099</span></span></td>
<td><span data-ttu-id="5bfd8-310">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-310">Default cost center</span></span></td>
<td><span data-ttu-id="5bfd8-311">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-311">10001</span></span></td>
<td><span data-ttu-id="5bfd8-312">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-312">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-313">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-313">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5bfd8-315">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="5bfd8-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-316">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-317">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-317">Cost element</span></span></th>
<th><span data-ttu-id="5bfd8-318">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-318">Cost behavior</span></span></th>
<th><span data-ttu-id="5bfd8-319">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-319">Amount</span></span></th>
<th><span data-ttu-id="5bfd8-320">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-321">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-321">CC099</span></span></td>
<td><span data-ttu-id="5bfd8-322">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-322">Default cost center</span></span></td>
<td><span data-ttu-id="5bfd8-323">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-323">10001</span></span></td>
<td><span data-ttu-id="5bfd8-324">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-324">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-325">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-325">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-326">-1,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-327">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-328">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-328">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-329">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-329">HR</span></span></td>
<td><span data-ttu-id="5bfd8-330">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-330">10001</span></span></td>
<td><span data-ttu-id="5bfd8-331">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-331">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-332">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-332">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-333">500.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-333">500.00</span></span></td>
<td><span data-ttu-id="5bfd8-334">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-335">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-335">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-336">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-336">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-337">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-337">10001</span></span></td>
<td><span data-ttu-id="5bfd8-338">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-338">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-339">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-339">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-340">500.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-340">500.00</span></span></td>
<td><span data-ttu-id="5bfd8-341">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-342">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-342">CC099</span></span></td>
<td><span data-ttu-id="5bfd8-343">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="5bfd8-343">Default cost center</span></span></td>
<td><span data-ttu-id="5bfd8-344">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-344">10001</span></span></td>
<td><span data-ttu-id="5bfd8-345">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-345">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-346">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-346">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-347">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-347">-9,000.00</span></span></td>
<td><span data-ttu-id="5bfd8-348">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-349">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-349">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-350">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-350">HR</span></span></td>
<td><span data-ttu-id="5bfd8-351">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-351">10001</span></span></td>
<td><span data-ttu-id="5bfd8-352">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-352">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-353">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-353">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="5bfd8-354">1,285.71</span></span></td>
<td><span data-ttu-id="5bfd8-355">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-356">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-356">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-357">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-357">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-358">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-358">10001</span></span></td>
<td><span data-ttu-id="5bfd8-359">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-359">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-360">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-360">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="5bfd8-361">7,714.29</span></span></td>
<td><span data-ttu-id="5bfd8-362">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-363">További információért lásd: [Költségelosztási irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="5bfd8-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="5bfd8-364">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="5bfd8-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="5bfd8-365">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="5bfd8-366">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="5bfd8-367">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="5bfd8-367">Define the overhead rate</span></span>

<span data-ttu-id="5bfd8-368">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="5bfd8-369">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-370">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-370">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-371">óra</span><span class="sxs-lookup"><span data-stu-id="5bfd8-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-372">Proj 1</span></span></td>
<td><span data-ttu-id="5bfd8-373">1. projekt</span><span class="sxs-lookup"><span data-stu-id="5bfd8-373">Project 1</span></span></td>
<td><span data-ttu-id="5bfd8-374">3</span><span class="sxs-lookup"><span data-stu-id="5bfd8-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-375">Proj 2</span></span></td>
<td><span data-ttu-id="5bfd8-376">2. projekt</span><span class="sxs-lookup"><span data-stu-id="5bfd8-376">Project 2</span></span></td>
<td><span data-ttu-id="5bfd8-377">1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-378">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-379">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-379">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-380">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-380">Cost element</span></span></th>
<th><span data-ttu-id="5bfd8-381">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-381">Cost behavior</span></span></th>
<th><span data-ttu-id="5bfd8-382">Egységek</span><span class="sxs-lookup"><span data-stu-id="5bfd8-382">Units</span></span></th>
<th><span data-ttu-id="5bfd8-383">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="5bfd8-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-384">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-384">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-385">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-385">HR</span></span></td>
<td><span data-ttu-id="5bfd8-386">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-386">10001</span></span></td>
<td><span data-ttu-id="5bfd8-387">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-387">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-388">1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-388">1</span></span></td>
<td><span data-ttu-id="5bfd8-389">10</span><span class="sxs-lookup"><span data-stu-id="5bfd8-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-390">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-391">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-391">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-392">Nagyság</span><span class="sxs-lookup"><span data-stu-id="5bfd8-392">Magnitude</span></span></th>
<th><span data-ttu-id="5bfd8-393">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-393">Cost element</span></span></th>
<th><span data-ttu-id="5bfd8-394">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="5bfd8-394">Allocation factor</span></span></th>
<th><span data-ttu-id="5bfd8-395">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-396">Proj 1</span></span></td>
<td><span data-ttu-id="5bfd8-397">1. projekt</span><span class="sxs-lookup"><span data-stu-id="5bfd8-397">Project 1</span></span></td>
<td><span data-ttu-id="5bfd8-398">3</span><span class="sxs-lookup"><span data-stu-id="5bfd8-398">3</span></span></td>
<td><span data-ttu-id="5bfd8-399">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-399">10001</span></span></td>
<td><span data-ttu-id="5bfd8-400">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="5bfd8-401">30.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-402">Proj 2</span></span></td>
<td><span data-ttu-id="5bfd8-403">2. projekt</span><span class="sxs-lookup"><span data-stu-id="5bfd8-403">Project 2</span></span></td>
<td><span data-ttu-id="5bfd8-404">1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-404">1</span></span></td>
<td><span data-ttu-id="5bfd8-405">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-405">10001</span></span></td>
<td><span data-ttu-id="5bfd8-406">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="5bfd8-407">10.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="5bfd8-408">Napló</span><span class="sxs-lookup"><span data-stu-id="5bfd8-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bfd8-409">Napló</span><span class="sxs-lookup"><span data-stu-id="5bfd8-409">Journal</span></span></th>
<th><span data-ttu-id="5bfd8-410">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="5bfd8-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5bfd8-411">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5bfd8-412">Verzió</span><span class="sxs-lookup"><span data-stu-id="5bfd8-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-413">00003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-413">00003</span></span></td>
<td><span data-ttu-id="5bfd8-414">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="5bfd8-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="5bfd8-415">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="5bfd8-415">Fiscal</span></span></td>
<td><span data-ttu-id="5bfd8-416">2017</span><span class="sxs-lookup"><span data-stu-id="5bfd8-416">2017</span></span></td>
<td><span data-ttu-id="5bfd8-417">1. időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-417">Period 1</span></span></td>
<td><span data-ttu-id="5bfd8-418">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="5bfd8-419">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bfd8-420">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-421">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-421">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-422">Nagyság</span><span class="sxs-lookup"><span data-stu-id="5bfd8-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-423">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-424">Proj 1</span></span></td>
<td><span data-ttu-id="5bfd8-425">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="5bfd8-426">3,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-427">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-428">Proj 2</span></span></td>
<td><span data-ttu-id="5bfd8-429">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="5bfd8-430">1.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5bfd8-431">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="5bfd8-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-432">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-433">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-433">Cost element</span></span></th>
<th><span data-ttu-id="5bfd8-434">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-434">Cost behavior</span></span></th>
<th><span data-ttu-id="5bfd8-435">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-435">Amount</span></span></th>
<th><span data-ttu-id="5bfd8-436">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-437">CC0001</span></span></td>
<td><span data-ttu-id="5bfd8-438">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-438">HR</span></span></td>
<td><span data-ttu-id="5bfd8-439">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-439">10001</span></span></td>
<td><span data-ttu-id="5bfd8-440">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-440">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-441">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-441">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-442">-30.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-442">-30.00</span></span></td>
<td><span data-ttu-id="5bfd8-443">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-444">Proj 1</span></span></td>
<td><span data-ttu-id="5bfd8-445">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="5bfd8-446">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-446">10001</span></span></td>
<td><span data-ttu-id="5bfd8-447">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-447">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-448">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-448">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-449">30.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-449">30.00</span></span></td>
<td><span data-ttu-id="5bfd8-450">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-451">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-451">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-452">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-452">HR</span></span></td>
<td><span data-ttu-id="5bfd8-453">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-453">10001</span></span></td>
<td><span data-ttu-id="5bfd8-454">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-454">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-455">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-455">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-456">-10.00</span></span></td>
<td><span data-ttu-id="5bfd8-457">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-458">Proj 2</span></span></td>
<td><span data-ttu-id="5bfd8-459">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="5bfd8-460">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-460">10001</span></span></td>
<td><span data-ttu-id="5bfd8-461">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-461">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-462">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-462">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-463">10,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-463">10.00</span></span></td>
<td><span data-ttu-id="5bfd8-464">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-465">További információ: [Járulékosköltség-számítás végrehajtása](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="5bfd8-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="5bfd8-466">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="5bfd8-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="5bfd8-467">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="5bfd8-468">A Finance a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="5bfd8-469">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="5bfd8-470">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="5bfd8-471">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="5bfd8-472">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="5bfd8-473">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="5bfd8-474">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="5bfd8-475">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="5bfd8-475">Define the cost allocation</span></span>

<span data-ttu-id="5bfd8-476">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="5bfd8-477">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="5bfd8-478">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-479">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-479">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-480">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="5bfd8-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-481">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-481">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-482">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-482">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-483">35</span><span class="sxs-lookup"><span data-stu-id="5bfd8-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-484">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-484">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-485">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-485">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-486">55</span><span class="sxs-lookup"><span data-stu-id="5bfd8-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-487">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-487">CC004</span></span></td>
<td><span data-ttu-id="5bfd8-488">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-488">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-489">10</span><span class="sxs-lookup"><span data-stu-id="5bfd8-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-490">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="5bfd8-491">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-492">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-492">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-493">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="5bfd8-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-494">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-494">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-495">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-495">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-496">65</span><span class="sxs-lookup"><span data-stu-id="5bfd8-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-497">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-497">CC004</span></span></td>
<td><span data-ttu-id="5bfd8-498">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-498">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-499">35</span><span class="sxs-lookup"><span data-stu-id="5bfd8-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-500">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="5bfd8-501">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-502">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-502">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-503">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-504">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-504">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-505">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-505">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-506">60</span><span class="sxs-lookup"><span data-stu-id="5bfd8-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-507">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-507">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-508">2. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-508">Product 2</span></span></td>
<td><span data-ttu-id="5bfd8-509">20</span><span class="sxs-lookup"><span data-stu-id="5bfd8-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-510">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="5bfd8-511">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-512">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-512">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-513">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-514">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-514">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-515">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-515">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-516">80</span><span class="sxs-lookup"><span data-stu-id="5bfd8-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-517">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-517">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-518">2. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-518">Product 2</span></span></td>
<td><span data-ttu-id="5bfd8-519">15</span><span class="sxs-lookup"><span data-stu-id="5bfd8-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="5bfd8-520">A statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="5bfd8-521">További információk: [Statisztikaimérték-szolgáltató sablon](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="5bfd8-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="5bfd8-522">Az alábbi táblázat azt az eredményt mutatja, amikor a HR szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-523">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-523">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-524">Nagyság</span><span class="sxs-lookup"><span data-stu-id="5bfd8-524">Magnitude</span></span></th>
<th><span data-ttu-id="5bfd8-525">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="5bfd8-525">Allocation factor</span></span></th>
<th><span data-ttu-id="5bfd8-526">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-526">Amount</span></span></th>
<th><span data-ttu-id="5bfd8-527">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-528">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-528">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-529">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-529">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-530">35</span><span class="sxs-lookup"><span data-stu-id="5bfd8-530">35</span></span></td>
<td><span data-ttu-id="5bfd8-531">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5bfd8-532">175.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-532">175.00</span></span></td>
<td><span data-ttu-id="5bfd8-533">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-534">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-534">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-535">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-535">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-536">55</span><span class="sxs-lookup"><span data-stu-id="5bfd8-536">55</span></span></td>
<td><span data-ttu-id="5bfd8-537">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5bfd8-538">275.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-538">275.00</span></span></td>
<td><span data-ttu-id="5bfd8-539">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-540">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-540">CC004</span></span></td>
<td><span data-ttu-id="5bfd8-541">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-541">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-542">10</span><span class="sxs-lookup"><span data-stu-id="5bfd8-542">10</span></span></td>
<td><span data-ttu-id="5bfd8-543">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="5bfd8-544">50,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-544">50.00</span></span></td>
<td><span data-ttu-id="5bfd8-545">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-546">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-546">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-547">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-547">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-548">35</span><span class="sxs-lookup"><span data-stu-id="5bfd8-548">35</span></span></td>
<td><span data-ttu-id="5bfd8-549">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="5bfd8-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5bfd8-550">436.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-550">436.00</span></span></td>
<td><span data-ttu-id="5bfd8-551">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-552">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-552">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-553">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-553">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-554">55</span><span class="sxs-lookup"><span data-stu-id="5bfd8-554">55</span></span></td>
<td><span data-ttu-id="5bfd8-555">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="5bfd8-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5bfd8-556">685.14</span><span class="sxs-lookup"><span data-stu-id="5bfd8-556">685.14</span></span></td>
<td><span data-ttu-id="5bfd8-557">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-558">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-558">CC004</span></span></td>
<td><span data-ttu-id="5bfd8-559">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-559">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-560">10</span><span class="sxs-lookup"><span data-stu-id="5bfd8-560">10</span></span></td>
<td><span data-ttu-id="5bfd8-561">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="5bfd8-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="5bfd8-562">124.57</span><span class="sxs-lookup"><span data-stu-id="5bfd8-562">124.57</span></span></td>
<td><span data-ttu-id="5bfd8-563">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-564">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-565">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-565">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-566">Nagyság</span><span class="sxs-lookup"><span data-stu-id="5bfd8-566">Magnitude</span></span></th>
<th><span data-ttu-id="5bfd8-567">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="5bfd8-567">Allocation factor</span></span></th>
<th><span data-ttu-id="5bfd8-568">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-568">Amount</span></span></th>
<th><span data-ttu-id="5bfd8-569">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-570">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-570">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-571">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-571">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-572">65</span><span class="sxs-lookup"><span data-stu-id="5bfd8-572">65</span></span></td>
<td><span data-ttu-id="5bfd8-573">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="5bfd8-574">438.75</span><span class="sxs-lookup"><span data-stu-id="5bfd8-574">438.75</span></span></td>
<td><span data-ttu-id="5bfd8-575">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-576">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-576">CC004</span></span></td>
<td><span data-ttu-id="5bfd8-577">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-577">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-578">35</span><span class="sxs-lookup"><span data-stu-id="5bfd8-578">35</span></span></td>
<td><span data-ttu-id="5bfd8-579">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="5bfd8-580">236.25</span><span class="sxs-lookup"><span data-stu-id="5bfd8-580">236.25</span></span></td>
<td><span data-ttu-id="5bfd8-581">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-582">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-582">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-583">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-583">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-584">65</span><span class="sxs-lookup"><span data-stu-id="5bfd8-584">65</span></span></td>
<td><span data-ttu-id="5bfd8-585">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="5bfd8-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="5bfd8-586">5,297.69</span></span></td>
<td><span data-ttu-id="5bfd8-587">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-588">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-588">CC004</span></span></td>
<td><span data-ttu-id="5bfd8-589">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-589">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-590">35</span><span class="sxs-lookup"><span data-stu-id="5bfd8-590">35</span></span></td>
<td><span data-ttu-id="5bfd8-591">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="5bfd8-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="5bfd8-592">2,852.60</span></span></td>
<td><span data-ttu-id="5bfd8-593">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-594">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-595">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-595">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-596">Nagyság</span><span class="sxs-lookup"><span data-stu-id="5bfd8-596">Magnitude</span></span></th>
<th><span data-ttu-id="5bfd8-597">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="5bfd8-597">Allocation factor</span></span></th>
<th><span data-ttu-id="5bfd8-598">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-598">Amount</span></span></th>
<th><span data-ttu-id="5bfd8-599">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-600">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-600">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-601">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-601">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-602">60</span><span class="sxs-lookup"><span data-stu-id="5bfd8-602">60</span></span></td>
<td><span data-ttu-id="5bfd8-603">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="5bfd8-604">535.31</span><span class="sxs-lookup"><span data-stu-id="5bfd8-604">535.31</span></span></td>
<td><span data-ttu-id="5bfd8-605">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-606">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-606">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-607">2. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-607">Product 2</span></span></td>
<td><span data-ttu-id="5bfd8-608">20</span><span class="sxs-lookup"><span data-stu-id="5bfd8-608">20</span></span></td>
<td><span data-ttu-id="5bfd8-609">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="5bfd8-610">178.44</span><span class="sxs-lookup"><span data-stu-id="5bfd8-610">178.44</span></span></td>
<td><span data-ttu-id="5bfd8-611">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-612">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-612">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-613">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-613">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-614">60</span><span class="sxs-lookup"><span data-stu-id="5bfd8-614">60</span></span></td>
<td><span data-ttu-id="5bfd8-615">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="5bfd8-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="5bfd8-616">4,487.12</span></span></td>
<td><span data-ttu-id="5bfd8-617">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-618">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-618">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-619">2. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-619">Product 2</span></span></td>
<td><span data-ttu-id="5bfd8-620">20</span><span class="sxs-lookup"><span data-stu-id="5bfd8-620">20</span></span></td>
<td><span data-ttu-id="5bfd8-621">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="5bfd8-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="5bfd8-622">1,495.71</span></span></td>
<td><span data-ttu-id="5bfd8-623">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5bfd8-624">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-625">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-625">Cost object</span></span></th>
<th><span data-ttu-id="5bfd8-626">Nagyság</span><span class="sxs-lookup"><span data-stu-id="5bfd8-626">Magnitude</span></span></th>
<th><span data-ttu-id="5bfd8-627">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="5bfd8-627">Allocation factor</span></span></th>
<th><span data-ttu-id="5bfd8-628">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-628">Amount</span></span></th>
<th><span data-ttu-id="5bfd8-629">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-630">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-630">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-631">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-631">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-632">80</span><span class="sxs-lookup"><span data-stu-id="5bfd8-632">80</span></span></td>
<td><span data-ttu-id="5bfd8-633">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="5bfd8-634">241.05</span><span class="sxs-lookup"><span data-stu-id="5bfd8-634">241.05</span></span></td>
<td><span data-ttu-id="5bfd8-635">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-636">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-636">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-637">2. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-637">Product 2</span></span></td>
<td><span data-ttu-id="5bfd8-638">15.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-638">15</span></span></td>
<td><span data-ttu-id="5bfd8-639">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="5bfd8-640">45.20</span><span class="sxs-lookup"><span data-stu-id="5bfd8-640">45.20</span></span></td>
<td><span data-ttu-id="5bfd8-641">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-642">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-642">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-643">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-643">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-644">80</span><span class="sxs-lookup"><span data-stu-id="5bfd8-644">80</span></span></td>
<td><span data-ttu-id="5bfd8-645">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="5bfd8-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="5bfd8-646">2,507.09</span></span></td>
<td><span data-ttu-id="5bfd8-647">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-648">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-648">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-649">2. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-649">Product 2</span></span></td>
<td><span data-ttu-id="5bfd8-650">15.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-650">15</span></span></td>
<td><span data-ttu-id="5bfd8-651">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="5bfd8-652">470.08</span><span class="sxs-lookup"><span data-stu-id="5bfd8-652">470.08</span></span></td>
<td><span data-ttu-id="5bfd8-653">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="5bfd8-654">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="5bfd8-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bfd8-655">Napló</span><span class="sxs-lookup"><span data-stu-id="5bfd8-655">Journal</span></span></th>
<th><span data-ttu-id="5bfd8-656">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="5bfd8-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="5bfd8-657">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="5bfd8-658">Verzió</span><span class="sxs-lookup"><span data-stu-id="5bfd8-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-659">00004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-659">00004</span></span></td>
<td><span data-ttu-id="5bfd8-660">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="5bfd8-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="5bfd8-661">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="5bfd8-661">Fiscal</span></span></td>
<td><span data-ttu-id="5bfd8-662">2017</span><span class="sxs-lookup"><span data-stu-id="5bfd8-662">2017</span></span></td>
<td><span data-ttu-id="5bfd8-663">1. időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-663">Period 1</span></span></td>
<td><span data-ttu-id="5bfd8-664">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="5bfd8-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="5bfd8-665">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="5bfd8-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="5bfd8-666">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-667">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-668">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-668">Cost element</span></span></th>
<th><span data-ttu-id="5bfd8-669">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-669">Cost behavior</span></span></th>
<th><span data-ttu-id="5bfd8-670">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-671">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-672">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-672">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-673">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-673">HR</span></span></td>
<td><span data-ttu-id="5bfd8-674">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-674">10001</span></span></td>
<td><span data-ttu-id="5bfd8-675">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-675">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-676">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-676">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-677">500.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-678">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-679">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-679">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-680">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-680">HR</span></span></td>
<td><span data-ttu-id="5bfd8-681">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-681">10001</span></span></td>
<td><span data-ttu-id="5bfd8-682">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-682">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-683">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-683">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="5bfd8-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-685">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-686">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-686">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-687">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-687">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-688">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-688">10001</span></span></td>
<td><span data-ttu-id="5bfd8-689">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-689">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-690">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-690">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-691">675.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-692">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-693">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-693">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-694">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-694">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-695">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-695">10001</span></span></td>
<td><span data-ttu-id="5bfd8-696">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-696">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-697">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-697">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="5bfd8-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-699">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-700">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-700">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-701">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-701">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-702">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-702">10001</span></span></td>
<td><span data-ttu-id="5bfd8-703">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-703">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-704">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-704">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-705">713.75</span><span class="sxs-lookup"><span data-stu-id="5bfd8-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-706">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-707">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-707">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-708">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-708">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-709">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-709">10001</span></span></td>
<td><span data-ttu-id="5bfd8-710">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-710">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-711">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-711">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="5bfd8-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-713">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-714">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-714">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-715">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-715">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-716">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-716">10001</span></span></td>
<td><span data-ttu-id="5bfd8-717">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-717">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-718">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-718">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-719">286.25</span><span class="sxs-lookup"><span data-stu-id="5bfd8-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-720">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-721">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-721">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-722">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-722">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-723">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-723">10001</span></span></td>
<td><span data-ttu-id="5bfd8-724">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-724">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-725">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-725">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="5bfd8-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-727">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-728">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-728">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-729">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-729">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-730">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-730">10001</span></span></td>
<td><span data-ttu-id="5bfd8-731">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-731">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-732">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-732">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-733">776.36</span><span class="sxs-lookup"><span data-stu-id="5bfd8-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-734">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-735">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-735">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-736">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-736">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-737">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-737">10001</span></span></td>
<td><span data-ttu-id="5bfd8-738">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-738">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-739">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-739">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="5bfd8-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-741">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-742">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-742">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-743">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-743">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-744">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-744">10001</span></span></td>
<td><span data-ttu-id="5bfd8-745">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-745">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-746">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-746">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-747">223.64</span><span class="sxs-lookup"><span data-stu-id="5bfd8-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-748">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="5bfd8-749">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-749">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-750">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-750">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-751">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-751">10001</span></span></td>
<td><span data-ttu-id="5bfd8-752">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-752">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-753">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-753">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="5bfd8-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="5bfd8-755">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="5bfd8-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="5bfd8-756">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="5bfd8-757">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-757">Cost element</span></span></th>
<th><span data-ttu-id="5bfd8-758">Költség működése</span><span class="sxs-lookup"><span data-stu-id="5bfd8-758">Cost behavior</span></span></th>
<th><span data-ttu-id="5bfd8-759">Összeg</span><span class="sxs-lookup"><span data-stu-id="5bfd8-759">Amount</span></span></th>
<th><span data-ttu-id="5bfd8-760">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="5bfd8-761">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-761">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-762">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-762">HR</span></span></td>
<td><span data-ttu-id="5bfd8-763">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-763">10001</span></span></td>
<td><span data-ttu-id="5bfd8-764">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-764">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-765">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-765">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-766">-500.00</span></span></td>
<td><span data-ttu-id="5bfd8-767">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-768">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-768">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-769">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-769">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-770">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-770">10001</span></span></td>
<td><span data-ttu-id="5bfd8-771">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-771">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-772">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-772">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-773">175.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-773">175.00</span></span></td>
<td><span data-ttu-id="5bfd8-774">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-775">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-775">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-776">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-776">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-777">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-777">10001</span></span></td>
<td><span data-ttu-id="5bfd8-778">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-778">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-779">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-779">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-780">275.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-780">275.00</span></span></td>
<td><span data-ttu-id="5bfd8-781">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-782">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-782">CC004</span></span></td>
<td><span data-ttu-id="5bfd8-783">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-783">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-784">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-784">10001</span></span></td>
<td><span data-ttu-id="5bfd8-785">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-785">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-786">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-786">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-787">50,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-787">50,00</span></span></td>
<td><span data-ttu-id="5bfd8-788">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-789">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-789">CC001</span></span></td>
<td><span data-ttu-id="5bfd8-790">HR</span><span class="sxs-lookup"><span data-stu-id="5bfd8-790">HR</span></span></td>
<td><span data-ttu-id="5bfd8-791">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-791">10001</span></span></td>
<td><span data-ttu-id="5bfd8-792">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-792">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-793">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-793">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-794">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="5bfd8-794">-1,245.71</span></span></td>
<td><span data-ttu-id="5bfd8-795">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-796">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-796">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-797">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-797">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-798">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-798">10001</span></span></td>
<td><span data-ttu-id="5bfd8-799">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-799">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-800">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-800">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-801">436.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-801">436.00</span></span></td>
<td><span data-ttu-id="5bfd8-802">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-803">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-803">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-804">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-804">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-805">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-805">10001</span></span></td>
<td><span data-ttu-id="5bfd8-806">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-806">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-807">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-807">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-808">685.14</span><span class="sxs-lookup"><span data-stu-id="5bfd8-808">685.14</span></span></td>
<td><span data-ttu-id="5bfd8-809">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-810">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-810">CC004</span></span></td>
<td><span data-ttu-id="5bfd8-811">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-811">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-812">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-812">10001</span></span></td>
<td><span data-ttu-id="5bfd8-813">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-813">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-814">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-814">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-815">124.57</span><span class="sxs-lookup"><span data-stu-id="5bfd8-815">124.57</span></span></td>
<td><span data-ttu-id="5bfd8-816">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-817">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-817">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-818">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-818">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-819">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-819">10001</span></span></td>
<td><span data-ttu-id="5bfd8-820">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-820">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-821">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-821">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-822">-675.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-822">-675.00</span></span></td>
<td><span data-ttu-id="5bfd8-823">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-824">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-824">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-825">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-825">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-826">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-826">10001</span></span></td>
<td><span data-ttu-id="5bfd8-827">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-827">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-828">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-828">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-829">438.75</span><span class="sxs-lookup"><span data-stu-id="5bfd8-829">438.75</span></span></td>
<td><span data-ttu-id="5bfd8-830">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-831">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-831">CC004</span></span></td>
<td><span data-ttu-id="5bfd8-832">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-832">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-833">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-833">10001</span></span></td>
<td><span data-ttu-id="5bfd8-834">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-834">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-835">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-835">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-836">236.25</span><span class="sxs-lookup"><span data-stu-id="5bfd8-836">236.25</span></span></td>
<td><span data-ttu-id="5bfd8-837">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-838">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-838">CC002</span></span></td>
<td><span data-ttu-id="5bfd8-839">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="5bfd8-839">Finance</span></span></td>
<td><span data-ttu-id="5bfd8-840">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-840">10001</span></span></td>
<td><span data-ttu-id="5bfd8-841">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-841">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-842">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-842">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-843">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="5bfd8-843">-8,150.29</span></span></td>
<td><span data-ttu-id="5bfd8-844">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-845">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-845">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-846">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-846">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-847">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-847">10001</span></span></td>
<td><span data-ttu-id="5bfd8-848">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-848">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-849">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-849">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="5bfd8-850">5,297.69</span></span></td>
<td><span data-ttu-id="5bfd8-851">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-852">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-852">CC004</span></span></td>
<td><span data-ttu-id="5bfd8-853">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="5bfd8-853">Packaging</span></span></td>
<td><span data-ttu-id="5bfd8-854">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-854">10001</span></span></td>
<td><span data-ttu-id="5bfd8-855">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-855">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-856">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-856">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="5bfd8-857">2,852.60</span></span></td>
<td><span data-ttu-id="5bfd8-858">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-859">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-859">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-860">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-860">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-861">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-861">10001</span></span></td>
<td><span data-ttu-id="5bfd8-862">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-862">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-863">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-863">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-864">-713.75</span><span class="sxs-lookup"><span data-stu-id="5bfd8-864">-713.75</span></span></td>
<td><span data-ttu-id="5bfd8-865">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-866">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-866">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-867">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-867">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-868">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-868">10001</span></span></td>
<td><span data-ttu-id="5bfd8-869">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-869">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-870">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-870">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-871">535.31</span><span class="sxs-lookup"><span data-stu-id="5bfd8-871">535.31</span></span></td>
<td><span data-ttu-id="5bfd8-872">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-873">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-873">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-874">2. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-874">Product 2</span></span></td>
<td><span data-ttu-id="5bfd8-875">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-875">10001</span></span></td>
<td><span data-ttu-id="5bfd8-876">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-876">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-877">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-877">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-878">178.44</span><span class="sxs-lookup"><span data-stu-id="5bfd8-878">178.44</span></span></td>
<td><span data-ttu-id="5bfd8-879">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-880">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-880">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-881">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-881">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-882">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-882">10001</span></span></td>
<td><span data-ttu-id="5bfd8-883">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-883">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-884">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-884">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-885">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="5bfd8-885">-5,982.83</span></span></td>
<td><span data-ttu-id="5bfd8-886">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-887">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-887">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-888">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-888">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-889">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-889">10001</span></span></td>
<td><span data-ttu-id="5bfd8-890">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-890">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-891">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-891">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="5bfd8-892">4,487.12</span></span></td>
<td><span data-ttu-id="5bfd8-893">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-894">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-894">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-895">2. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-895">Product 2</span></span></td>
<td><span data-ttu-id="5bfd8-896">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-896">10001</span></span></td>
<td><span data-ttu-id="5bfd8-897">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-897">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-898">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-898">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="5bfd8-899">1,495.71</span></span></td>
<td><span data-ttu-id="5bfd8-900">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-901">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-901">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-902">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-902">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-903">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-903">10001</span></span></td>
<td><span data-ttu-id="5bfd8-904">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-904">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-905">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-905">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-906">-286.25</span><span class="sxs-lookup"><span data-stu-id="5bfd8-906">-286.25</span></span></td>
<td><span data-ttu-id="5bfd8-907">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-908">Term 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-908">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-909">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-909">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-910">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-910">10001</span></span></td>
<td><span data-ttu-id="5bfd8-911">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-911">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-912">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-912">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-913">241.05</span><span class="sxs-lookup"><span data-stu-id="5bfd8-913">241.05</span></span></td>
<td><span data-ttu-id="5bfd8-914">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-915">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-915">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-916">2. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-916">Product 2</span></span></td>
<td><span data-ttu-id="5bfd8-917">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-917">10001</span></span></td>
<td><span data-ttu-id="5bfd8-918">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-918">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-919">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-919">Fixed cost</span></span></td>
<td><span data-ttu-id="5bfd8-920">45.20</span><span class="sxs-lookup"><span data-stu-id="5bfd8-920">45.20</span></span></td>
<td><span data-ttu-id="5bfd8-921">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-922">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-922">CC003</span></span></td>
<td><span data-ttu-id="5bfd8-923">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="5bfd8-923">Assembly</span></span></td>
<td><span data-ttu-id="5bfd8-924">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-924">10001</span></span></td>
<td><span data-ttu-id="5bfd8-925">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-925">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-926">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-926">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-927">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="5bfd8-927">-2,977.17</span></span></td>
<td><span data-ttu-id="5bfd8-928">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-929">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-929">Prod 1</span></span></td>
<td><span data-ttu-id="5bfd8-930">1. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-930">Product 1</span></span></td>
<td><span data-ttu-id="5bfd8-931">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-931">10001</span></span></td>
<td><span data-ttu-id="5bfd8-932">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-932">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-933">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-933">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="5bfd8-934">2,507.09</span></span></td>
<td><span data-ttu-id="5bfd8-935">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfd8-936">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-936">Prod 2</span></span></td>
<td><span data-ttu-id="5bfd8-937">2. termék</span><span class="sxs-lookup"><span data-stu-id="5bfd8-937">Product 2</span></span></td>
<td><span data-ttu-id="5bfd8-938">10001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-938">10001</span></span></td>
<td><span data-ttu-id="5bfd8-939">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-939">Electricity</span></span></td>
<td><span data-ttu-id="5bfd8-940">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-940">Variable cost</span></span></td>
<td><span data-ttu-id="5bfd8-941">470.08</span><span class="sxs-lookup"><span data-stu-id="5bfd8-941">470.08</span></span></td>
<td><span data-ttu-id="5bfd8-942">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="5bfd8-943">Következtetés</span><span class="sxs-lookup"><span data-stu-id="5bfd8-943">Conclusion</span></span>
<span data-ttu-id="5bfd8-944">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="5bfd8-945">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="5bfd8-946">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="5bfd8-947">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="5bfd8-948">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="5bfd8-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="5bfd8-949">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="5bfd8-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="5bfd8-950">Összesen</span><span class="sxs-lookup"><span data-stu-id="5bfd8-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="5bfd8-951">CC099</span><span class="sxs-lookup"><span data-stu-id="5bfd8-951">CC099</span></span></th>
<th><span data-ttu-id="5bfd8-952">CC001</span><span class="sxs-lookup"><span data-stu-id="5bfd8-952">CC001</span></span></th>
<th><span data-ttu-id="5bfd8-953">CC002</span><span class="sxs-lookup"><span data-stu-id="5bfd8-953">CC002</span></span></th>
<th><span data-ttu-id="5bfd8-954">CC003</span><span class="sxs-lookup"><span data-stu-id="5bfd8-954">CC003</span></span></th>
<th><span data-ttu-id="5bfd8-955">CC004</span><span class="sxs-lookup"><span data-stu-id="5bfd8-955">CC004</span></span></th>
<th><span data-ttu-id="5bfd8-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-956">Proj 1</span></span></th>
<th><span data-ttu-id="5bfd8-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-957">Proj 2</span></span></th>
<th><span data-ttu-id="5bfd8-958">Term. 1</span><span class="sxs-lookup"><span data-stu-id="5bfd8-958">Prod 1</span></span></th>
<th><span data-ttu-id="5bfd8-959">Term. 2</span><span class="sxs-lookup"><span data-stu-id="5bfd8-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="5bfd8-960">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="5bfd8-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="5bfd8-970">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="5bfd8-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-971">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="5bfd8-972">Fix költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-973">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-974">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-975">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-976">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-977">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-978">776.36</span><span class="sxs-lookup"><span data-stu-id="5bfd8-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-979">223.64</span><span class="sxs-lookup"><span data-stu-id="5bfd8-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="5bfd8-981">Változó költség</span><span class="sxs-lookup"><span data-stu-id="5bfd8-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-982">000</span><span class="sxs-lookup"><span data-stu-id="5bfd8-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-983">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-984">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-985">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-986">0,00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-987">30.00</span><span class="sxs-lookup"><span data-stu-id="5bfd8-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-988">1000</span><span class="sxs-lookup"><span data-stu-id="5bfd8-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="5bfd8-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="5bfd8-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="5bfd8-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="5bfd8-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="5bfd8-992">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="5bfd8-993">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="5bfd8-994">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="5bfd8-995">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="5bfd8-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="5bfd8-996">A további tudnivalókat lásd: [Költségösszesítéssel kapcsolatos irányelv és járulékos költség számítása](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="5bfd8-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]