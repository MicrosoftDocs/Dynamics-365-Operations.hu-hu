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
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544055"
---
# <a name="overhead-calculation"></a><span data-ttu-id="093b5-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="093b5-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="093b5-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="093b5-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="093b5-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="093b5-105">Term definition</span></span>
---------------

<span data-ttu-id="093b5-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="093b5-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="093b5-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="093b5-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="093b5-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="093b5-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="093b5-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="093b5-109">Rent</span></span>
-   <span data-ttu-id="093b5-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-110">Electricity</span></span>
-   <span data-ttu-id="093b5-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="093b5-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="093b5-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="093b5-112">Overhead calculation overview</span></span>
<span data-ttu-id="093b5-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="093b5-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="093b5-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="093b5-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="093b5-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="093b5-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="093b5-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="093b5-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="093b5-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="093b5-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="093b5-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="093b5-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="093b5-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="093b5-119">Version type</span></span>
-   <span data-ttu-id="093b5-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="093b5-120">Date and time</span></span>
-   <span data-ttu-id="093b5-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="093b5-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="093b5-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="093b5-122">Fiscal year</span></span>
-   <span data-ttu-id="093b5-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-123">Fiscal period</span></span>

<span data-ttu-id="093b5-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="093b5-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="093b5-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="093b5-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="093b5-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="093b5-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="093b5-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="093b5-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="093b5-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="093b5-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="093b5-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="093b5-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="093b5-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="093b5-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="093b5-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="093b5-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="093b5-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="093b5-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="093b5-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="093b5-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="093b5-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="093b5-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="093b5-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="093b5-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="093b5-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="093b5-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="093b5-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="093b5-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="093b5-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="093b5-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="093b5-140">Main account</span></span></th>
<th><span data-ttu-id="093b5-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="093b5-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="093b5-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="093b5-143">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-143">CC099</span></span></td>
<td><span data-ttu-id="093b5-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-144">Default cost center</span></span></td>
<td><span data-ttu-id="093b5-145">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-145">10001</span></span></td>
<td><span data-ttu-id="093b5-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-146">Electricity</span></span></td>
<td><span data-ttu-id="093b5-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="093b5-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="093b5-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="093b5-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="093b5-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="093b5-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="093b5-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="093b5-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="093b5-151">Define the cost behavior rule</span></span>

<span data-ttu-id="093b5-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="093b5-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="093b5-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="093b5-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="093b5-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="093b5-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="093b5-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="093b5-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="093b5-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="093b5-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="093b5-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="093b5-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="093b5-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="093b5-159">Napló</span><span class="sxs-lookup"><span data-stu-id="093b5-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="093b5-160">Napló</span><span class="sxs-lookup"><span data-stu-id="093b5-160">Journal</span></span></th>
<th><span data-ttu-id="093b5-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="093b5-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="093b5-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="093b5-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="093b5-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-164">00001</span><span class="sxs-lookup"><span data-stu-id="093b5-164">00001</span></span></td>
<td><span data-ttu-id="093b5-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="093b5-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="093b5-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="093b5-166">Fiscal</span></span></td>
<td><span data-ttu-id="093b5-167">2017</span><span class="sxs-lookup"><span data-stu-id="093b5-167">2017</span></span></td>
<td><span data-ttu-id="093b5-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-168">Period 1</span></span></td>
<td><span data-ttu-id="093b5-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="093b5-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="093b5-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="093b5-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="093b5-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="093b5-173">Cost element</span></span></th>
<th><span data-ttu-id="093b5-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-174">Cost behavior</span></span></th>
<th><span data-ttu-id="093b5-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="093b5-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="093b5-177">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-177">CC099</span></span></td>
<td><span data-ttu-id="093b5-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-178">Default cost center</span></span></td>
<td><span data-ttu-id="093b5-179">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-179">10001</span></span></td>
<td><span data-ttu-id="093b5-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-180">Electricity</span></span></td>
<td><span data-ttu-id="093b5-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="093b5-181">Unclassified</span></span></td>
<td><span data-ttu-id="093b5-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="093b5-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="093b5-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="093b5-185">Cost element</span></span></th>
<th><span data-ttu-id="093b5-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-186">Cost behavior</span></span></th>
<th><span data-ttu-id="093b5-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-187">Amount</span></span></th>
<th><span data-ttu-id="093b5-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="093b5-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-189">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-189">CC099</span></span></td>
<td><span data-ttu-id="093b5-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-190">Default cost center</span></span></td>
<td><span data-ttu-id="093b5-191">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-191">10001</span></span></td>
<td><span data-ttu-id="093b5-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-192">Electricity</span></span></td>
<td><span data-ttu-id="093b5-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="093b5-193">Unclassified</span></span></td>
<td><span data-ttu-id="093b5-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-194">10,000.00</span></span></td>
<td><span data-ttu-id="093b5-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="093b5-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-196">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-196">CC099</span></span></td>
<td><span data-ttu-id="093b5-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-197">Default cost center</span></span></td>
<td><span data-ttu-id="093b5-198">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-198">10001</span></span></td>
<td><span data-ttu-id="093b5-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-199">Electricity</span></span></td>
<td><span data-ttu-id="093b5-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="093b5-200">Unclassified</span></span></td>
<td><span data-ttu-id="093b5-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-201">-10,000.00</span></span></td>
<td><span data-ttu-id="093b5-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-203">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-203">CC099</span></span></td>
<td><span data-ttu-id="093b5-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-204">Default cost center</span></span></td>
<td><span data-ttu-id="093b5-205">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-205">10001</span></span></td>
<td><span data-ttu-id="093b5-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-206">Electricity</span></span></td>
<td><span data-ttu-id="093b5-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-207">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="093b5-208">1,000.00</span></span></td>
<td><span data-ttu-id="093b5-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-210">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-210">CC099</span></span></td>
<td><span data-ttu-id="093b5-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-211">Default cost center</span></span></td>
<td><span data-ttu-id="093b5-212">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-212">10001</span></span></td>
<td><span data-ttu-id="093b5-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-213">Electricity</span></span></td>
<td><span data-ttu-id="093b5-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-214">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-215">9,000.00</span></span></td>
<td><span data-ttu-id="093b5-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-217">További információért lásd: [Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="093b5-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="093b5-218">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="093b5-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="093b5-219">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="093b5-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="093b5-220">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="093b5-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="093b5-221">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="093b5-221">Define the cost distribution rule</span></span>

<span data-ttu-id="093b5-222">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="093b5-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="093b5-223">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="093b5-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="093b5-224">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="093b5-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="093b5-225">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="093b5-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="093b5-226">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="093b5-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="093b5-227">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="093b5-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-228">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-228">Cost object</span></span></th>
<th><span data-ttu-id="093b5-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="093b5-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-230">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-230">CC001</span></span></td>
<td><span data-ttu-id="093b5-231">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-231">HR</span></span></td>
<td><span data-ttu-id="093b5-232">1000</span><span class="sxs-lookup"><span data-stu-id="093b5-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-233">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-233">CC002</span></span></td>
<td><span data-ttu-id="093b5-234">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-234">Finance</span></span></td>
<td><span data-ttu-id="093b5-235">6,000</span><span class="sxs-lookup"><span data-stu-id="093b5-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-236">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-236">CC003</span></span></td>
<td><span data-ttu-id="093b5-237">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-237">Assembly</span></span></td>
<td><span data-ttu-id="093b5-238">0</span><span class="sxs-lookup"><span data-stu-id="093b5-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-239">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="093b5-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-240">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-240">Cost object</span></span></th>
<th><span data-ttu-id="093b5-241">Nagyság</span><span class="sxs-lookup"><span data-stu-id="093b5-241">Magnitude</span></span></th>
<th><span data-ttu-id="093b5-242">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="093b5-242">Allocation factor</span></span></th>
<th><span data-ttu-id="093b5-243">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-244">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-244">CC001</span></span></td>
<td><span data-ttu-id="093b5-245">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-245">HR</span></span></td>
<td><span data-ttu-id="093b5-246">1000</span><span class="sxs-lookup"><span data-stu-id="093b5-246">1,000</span></span></td>
<td><span data-ttu-id="093b5-247">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="093b5-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="093b5-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-249">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-249">CC002</span></span></td>
<td><span data-ttu-id="093b5-250">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-250">Finance</span></span></td>
<td><span data-ttu-id="093b5-251">6,000</span><span class="sxs-lookup"><span data-stu-id="093b5-251">6,000</span></span></td>
<td><span data-ttu-id="093b5-252">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="093b5-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="093b5-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-254">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-254">CC003</span></span></td>
<td><span data-ttu-id="093b5-255">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-255">Assembly</span></span></td>
<td><span data-ttu-id="093b5-256">0</span><span class="sxs-lookup"><span data-stu-id="093b5-256">0</span></span></td>
<td><span data-ttu-id="093b5-257">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="093b5-258">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-259">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="093b5-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="093b5-260">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: (Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="093b5-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-261">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-261">Cost object</span></span></th>
<th><span data-ttu-id="093b5-262">Receptúra</span><span class="sxs-lookup"><span data-stu-id="093b5-262">Formula</span></span></th>
<th><span data-ttu-id="093b5-263">Nagyság</span><span class="sxs-lookup"><span data-stu-id="093b5-263">Magnitude</span></span></th>
<th><span data-ttu-id="093b5-264">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="093b5-264">Allocation factor</span></span></th>
<th><span data-ttu-id="093b5-265">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-266">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-266">CC001</span></span></td>
<td><span data-ttu-id="093b5-267">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-267">HR</span></span></td>
<td><span data-ttu-id="093b5-268">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="093b5-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="093b5-269">1</span><span class="sxs-lookup"><span data-stu-id="093b5-269">1</span></span></td>
<td><span data-ttu-id="093b5-270">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="093b5-271">500.00</span><span class="sxs-lookup"><span data-stu-id="093b5-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-272">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-272">CC002</span></span></td>
<td><span data-ttu-id="093b5-273">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-273">Finance</span></span></td>
<td><span data-ttu-id="093b5-274">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="093b5-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="093b5-275">1</span><span class="sxs-lookup"><span data-stu-id="093b5-275">1</span></span></td>
<td><span data-ttu-id="093b5-276">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="093b5-277">500.00</span><span class="sxs-lookup"><span data-stu-id="093b5-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-278">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-278">CC003</span></span></td>
<td><span data-ttu-id="093b5-279">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-279">Assembly</span></span></td>
<td><span data-ttu-id="093b5-280">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="093b5-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="093b5-281">0</span><span class="sxs-lookup"><span data-stu-id="093b5-281">0</span></span></td>
<td><span data-ttu-id="093b5-282">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="093b5-283">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="093b5-284">Napló</span><span class="sxs-lookup"><span data-stu-id="093b5-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="093b5-285">Napló</span><span class="sxs-lookup"><span data-stu-id="093b5-285">Journal</span></span></th>
<th><span data-ttu-id="093b5-286">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="093b5-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="093b5-287">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="093b5-288">Verzió</span><span class="sxs-lookup"><span data-stu-id="093b5-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-289">00002</span><span class="sxs-lookup"><span data-stu-id="093b5-289">00002</span></span></td>
<td><span data-ttu-id="093b5-290">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="093b5-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="093b5-291">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="093b5-291">Fiscal</span></span></td>
<td><span data-ttu-id="093b5-292">2017</span><span class="sxs-lookup"><span data-stu-id="093b5-292">2017</span></span></td>
<td><span data-ttu-id="093b5-293">1. időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-293">Period 1</span></span></td>
<td><span data-ttu-id="093b5-294">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="093b5-295">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="093b5-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="093b5-296">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="093b5-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-297">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-298">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="093b5-298">Cost element</span></span></th>
<th><span data-ttu-id="093b5-299">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-299">Cost behavior</span></span></th>
<th><span data-ttu-id="093b5-300">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-301">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-302">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-302">CC099</span></span></td>
<td><span data-ttu-id="093b5-303">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-303">Default cost center</span></span></td>
<td><span data-ttu-id="093b5-304">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-304">10001</span></span></td>
<td><span data-ttu-id="093b5-305">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-305">Electricity</span></span></td>
<td><span data-ttu-id="093b5-306">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-306">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="093b5-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-308">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-309">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-309">CC099</span></span></td>
<td><span data-ttu-id="093b5-310">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-310">Default cost center</span></span></td>
<td><span data-ttu-id="093b5-311">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-311">10001</span></span></td>
<td><span data-ttu-id="093b5-312">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-312">Electricity</span></span></td>
<td><span data-ttu-id="093b5-313">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-313">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="093b5-315">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="093b5-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-316">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-317">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="093b5-317">Cost element</span></span></th>
<th><span data-ttu-id="093b5-318">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-318">Cost behavior</span></span></th>
<th><span data-ttu-id="093b5-319">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-319">Amount</span></span></th>
<th><span data-ttu-id="093b5-320">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="093b5-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-321">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-321">CC099</span></span></td>
<td><span data-ttu-id="093b5-322">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-322">Default cost center</span></span></td>
<td><span data-ttu-id="093b5-323">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-323">10001</span></span></td>
<td><span data-ttu-id="093b5-324">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-324">Electricity</span></span></td>
<td><span data-ttu-id="093b5-325">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-325">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="093b5-326">-1,000.00</span></span></td>
<td><span data-ttu-id="093b5-327">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-328">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-328">CC001</span></span></td>
<td><span data-ttu-id="093b5-329">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-329">HR</span></span></td>
<td><span data-ttu-id="093b5-330">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-330">10001</span></span></td>
<td><span data-ttu-id="093b5-331">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-331">Electricity</span></span></td>
<td><span data-ttu-id="093b5-332">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-332">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-333">500.00</span><span class="sxs-lookup"><span data-stu-id="093b5-333">500.00</span></span></td>
<td><span data-ttu-id="093b5-334">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-335">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-335">CC002</span></span></td>
<td><span data-ttu-id="093b5-336">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-336">Finance</span></span></td>
<td><span data-ttu-id="093b5-337">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-337">10001</span></span></td>
<td><span data-ttu-id="093b5-338">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-338">Electricity</span></span></td>
<td><span data-ttu-id="093b5-339">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-339">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-340">500.00</span><span class="sxs-lookup"><span data-stu-id="093b5-340">500.00</span></span></td>
<td><span data-ttu-id="093b5-341">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-342">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-342">CC099</span></span></td>
<td><span data-ttu-id="093b5-343">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="093b5-343">Default cost center</span></span></td>
<td><span data-ttu-id="093b5-344">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-344">10001</span></span></td>
<td><span data-ttu-id="093b5-345">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-345">Electricity</span></span></td>
<td><span data-ttu-id="093b5-346">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-346">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-347">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="093b5-347">-9,000.00</span></span></td>
<td><span data-ttu-id="093b5-348">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-349">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-349">CC001</span></span></td>
<td><span data-ttu-id="093b5-350">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-350">HR</span></span></td>
<td><span data-ttu-id="093b5-351">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-351">10001</span></span></td>
<td><span data-ttu-id="093b5-352">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-352">Electricity</span></span></td>
<td><span data-ttu-id="093b5-353">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-353">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="093b5-354">1,285.71</span></span></td>
<td><span data-ttu-id="093b5-355">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-356">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-356">CC002</span></span></td>
<td><span data-ttu-id="093b5-357">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-357">Finance</span></span></td>
<td><span data-ttu-id="093b5-358">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-358">10001</span></span></td>
<td><span data-ttu-id="093b5-359">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-359">Electricity</span></span></td>
<td><span data-ttu-id="093b5-360">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-360">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="093b5-361">7,714.29</span></span></td>
<td><span data-ttu-id="093b5-362">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-363">További információért lásd: [Költségelosztási irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="093b5-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="093b5-364">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="093b5-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="093b5-365">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="093b5-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="093b5-366">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="093b5-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="093b5-367">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="093b5-367">Define the overhead rate</span></span>

<span data-ttu-id="093b5-368">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="093b5-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="093b5-369">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="093b5-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-370">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-370">Cost object</span></span></th>
<th><span data-ttu-id="093b5-371">óra</span><span class="sxs-lookup"><span data-stu-id="093b5-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="093b5-372">Proj 1</span></span></td>
<td><span data-ttu-id="093b5-373">1. projekt</span><span class="sxs-lookup"><span data-stu-id="093b5-373">Project 1</span></span></td>
<td><span data-ttu-id="093b5-374">3</span><span class="sxs-lookup"><span data-stu-id="093b5-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="093b5-375">Proj 2</span></span></td>
<td><span data-ttu-id="093b5-376">2. projekt</span><span class="sxs-lookup"><span data-stu-id="093b5-376">Project 2</span></span></td>
<td><span data-ttu-id="093b5-377">1</span><span class="sxs-lookup"><span data-stu-id="093b5-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-378">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="093b5-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-379">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-379">Cost object</span></span></th>
<th><span data-ttu-id="093b5-380">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="093b5-380">Cost element</span></span></th>
<th><span data-ttu-id="093b5-381">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-381">Cost behavior</span></span></th>
<th><span data-ttu-id="093b5-382">Egységek</span><span class="sxs-lookup"><span data-stu-id="093b5-382">Units</span></span></th>
<th><span data-ttu-id="093b5-383">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="093b5-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-384">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-384">CC001</span></span></td>
<td><span data-ttu-id="093b5-385">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-385">HR</span></span></td>
<td><span data-ttu-id="093b5-386">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-386">10001</span></span></td>
<td><span data-ttu-id="093b5-387">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-387">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-388">1</span><span class="sxs-lookup"><span data-stu-id="093b5-388">1</span></span></td>
<td><span data-ttu-id="093b5-389">10</span><span class="sxs-lookup"><span data-stu-id="093b5-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-390">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="093b5-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-391">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-391">Cost object</span></span></th>
<th><span data-ttu-id="093b5-392">Nagyság</span><span class="sxs-lookup"><span data-stu-id="093b5-392">Magnitude</span></span></th>
<th><span data-ttu-id="093b5-393">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="093b5-393">Cost element</span></span></th>
<th><span data-ttu-id="093b5-394">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="093b5-394">Allocation factor</span></span></th>
<th><span data-ttu-id="093b5-395">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="093b5-396">Proj 1</span></span></td>
<td><span data-ttu-id="093b5-397">1. projekt</span><span class="sxs-lookup"><span data-stu-id="093b5-397">Project 1</span></span></td>
<td><span data-ttu-id="093b5-398">3</span><span class="sxs-lookup"><span data-stu-id="093b5-398">3</span></span></td>
<td><span data-ttu-id="093b5-399">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-399">10001</span></span></td>
<td><span data-ttu-id="093b5-400">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="093b5-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="093b5-401">30.00</span><span class="sxs-lookup"><span data-stu-id="093b5-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="093b5-402">Proj 2</span></span></td>
<td><span data-ttu-id="093b5-403">2. projekt</span><span class="sxs-lookup"><span data-stu-id="093b5-403">Project 2</span></span></td>
<td><span data-ttu-id="093b5-404">1</span><span class="sxs-lookup"><span data-stu-id="093b5-404">1</span></span></td>
<td><span data-ttu-id="093b5-405">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-405">10001</span></span></td>
<td><span data-ttu-id="093b5-406">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="093b5-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="093b5-407">10.00</span><span class="sxs-lookup"><span data-stu-id="093b5-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="093b5-408">Napló</span><span class="sxs-lookup"><span data-stu-id="093b5-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="093b5-409">Napló</span><span class="sxs-lookup"><span data-stu-id="093b5-409">Journal</span></span></th>
<th><span data-ttu-id="093b5-410">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="093b5-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="093b5-411">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="093b5-412">Verzió</span><span class="sxs-lookup"><span data-stu-id="093b5-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-413">00003</span><span class="sxs-lookup"><span data-stu-id="093b5-413">00003</span></span></td>
<td><span data-ttu-id="093b5-414">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="093b5-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="093b5-415">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="093b5-415">Fiscal</span></span></td>
<td><span data-ttu-id="093b5-416">2017</span><span class="sxs-lookup"><span data-stu-id="093b5-416">2017</span></span></td>
<td><span data-ttu-id="093b5-417">1. időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-417">Period 1</span></span></td>
<td><span data-ttu-id="093b5-418">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="093b5-419">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="093b5-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="093b5-420">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="093b5-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-421">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-421">Cost object</span></span></th>
<th><span data-ttu-id="093b5-422">Nagyság</span><span class="sxs-lookup"><span data-stu-id="093b5-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-423">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="093b5-424">Proj 1</span></span></td>
<td><span data-ttu-id="093b5-425">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="093b5-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="093b5-426">3,00</span><span class="sxs-lookup"><span data-stu-id="093b5-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-427">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="093b5-428">Proj 2</span></span></td>
<td><span data-ttu-id="093b5-429">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="093b5-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="093b5-430">1.00</span><span class="sxs-lookup"><span data-stu-id="093b5-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="093b5-431">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="093b5-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-432">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-433">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="093b5-433">Cost element</span></span></th>
<th><span data-ttu-id="093b5-434">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-434">Cost behavior</span></span></th>
<th><span data-ttu-id="093b5-435">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-435">Amount</span></span></th>
<th><span data-ttu-id="093b5-436">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="093b5-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="093b5-437">CC0001</span></span></td>
<td><span data-ttu-id="093b5-438">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-438">HR</span></span></td>
<td><span data-ttu-id="093b5-439">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-439">10001</span></span></td>
<td><span data-ttu-id="093b5-440">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-440">Electricity</span></span></td>
<td><span data-ttu-id="093b5-441">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-441">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-442">-30.00</span><span class="sxs-lookup"><span data-stu-id="093b5-442">-30.00</span></span></td>
<td><span data-ttu-id="093b5-443">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="093b5-444">Proj 1</span></span></td>
<td><span data-ttu-id="093b5-445">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="093b5-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="093b5-446">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-446">10001</span></span></td>
<td><span data-ttu-id="093b5-447">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-447">Electricity</span></span></td>
<td><span data-ttu-id="093b5-448">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-448">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-449">30.00</span><span class="sxs-lookup"><span data-stu-id="093b5-449">30.00</span></span></td>
<td><span data-ttu-id="093b5-450">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-451">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-451">CC001</span></span></td>
<td><span data-ttu-id="093b5-452">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-452">HR</span></span></td>
<td><span data-ttu-id="093b5-453">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-453">10001</span></span></td>
<td><span data-ttu-id="093b5-454">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-454">Electricity</span></span></td>
<td><span data-ttu-id="093b5-455">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-455">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="093b5-456">-10.00</span></span></td>
<td><span data-ttu-id="093b5-457">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="093b5-458">Proj 2</span></span></td>
<td><span data-ttu-id="093b5-459">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="093b5-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="093b5-460">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-460">10001</span></span></td>
<td><span data-ttu-id="093b5-461">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-461">Electricity</span></span></td>
<td><span data-ttu-id="093b5-462">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-462">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-463">10,00</span><span class="sxs-lookup"><span data-stu-id="093b5-463">10.00</span></span></td>
<td><span data-ttu-id="093b5-464">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-465">További információ: [Járulékosköltség-számítás végrehajtása](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="093b5-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="093b5-466">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="093b5-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="093b5-467">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="093b5-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="093b5-468">A Finance and Operations a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="093b5-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="093b5-469">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="093b5-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="093b5-470">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="093b5-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="093b5-471">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="093b5-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="093b5-472">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="093b5-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="093b5-473">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="093b5-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="093b5-474">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="093b5-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="093b5-475">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="093b5-475">Define the cost allocation</span></span>

<span data-ttu-id="093b5-476">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="093b5-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="093b5-477">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="093b5-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="093b5-478">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="093b5-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-479">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-479">Cost object</span></span></th>
<th><span data-ttu-id="093b5-480">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="093b5-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-481">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-481">CC002</span></span></td>
<td><span data-ttu-id="093b5-482">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-482">Finance</span></span></td>
<td><span data-ttu-id="093b5-483">35</span><span class="sxs-lookup"><span data-stu-id="093b5-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-484">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-484">CC003</span></span></td>
<td><span data-ttu-id="093b5-485">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-485">Assembly</span></span></td>
<td><span data-ttu-id="093b5-486">55</span><span class="sxs-lookup"><span data-stu-id="093b5-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-487">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-487">CC004</span></span></td>
<td><span data-ttu-id="093b5-488">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-488">Packaging</span></span></td>
<td><span data-ttu-id="093b5-489">10</span><span class="sxs-lookup"><span data-stu-id="093b5-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-490">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="093b5-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="093b5-491">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="093b5-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-492">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-492">Cost object</span></span></th>
<th><span data-ttu-id="093b5-493">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="093b5-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-494">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-494">CC003</span></span></td>
<td><span data-ttu-id="093b5-495">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-495">Assembly</span></span></td>
<td><span data-ttu-id="093b5-496">65</span><span class="sxs-lookup"><span data-stu-id="093b5-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-497">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-497">CC004</span></span></td>
<td><span data-ttu-id="093b5-498">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-498">Packaging</span></span></td>
<td><span data-ttu-id="093b5-499">35</span><span class="sxs-lookup"><span data-stu-id="093b5-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-500">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="093b5-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="093b5-501">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="093b5-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-502">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-502">Cost object</span></span></th>
<th><span data-ttu-id="093b5-503">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="093b5-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-504">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-504">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-505">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-505">Product 1</span></span></td>
<td><span data-ttu-id="093b5-506">60</span><span class="sxs-lookup"><span data-stu-id="093b5-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-507">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-507">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-508">2. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-508">Product 2</span></span></td>
<td><span data-ttu-id="093b5-509">20</span><span class="sxs-lookup"><span data-stu-id="093b5-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-510">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="093b5-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="093b5-511">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="093b5-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-512">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-512">Cost object</span></span></th>
<th><span data-ttu-id="093b5-513">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="093b5-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-514">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-514">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-515">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-515">Product 1</span></span></td>
<td><span data-ttu-id="093b5-516">80</span><span class="sxs-lookup"><span data-stu-id="093b5-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-517">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-517">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-518">2. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-518">Product 2</span></span></td>
<td><span data-ttu-id="093b5-519">15.</span><span class="sxs-lookup"><span data-stu-id="093b5-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="093b5-520">A Finance and Operations esetében a statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="093b5-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="093b5-521">További információk: [Statisztikaimérték-szolgáltató sablon](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="093b5-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="093b5-522">Az alábbi táblázat azt az eredményt mutatja, amikor a HR szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="093b5-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-523">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-523">Cost object</span></span></th>
<th><span data-ttu-id="093b5-524">Nagyság</span><span class="sxs-lookup"><span data-stu-id="093b5-524">Magnitude</span></span></th>
<th><span data-ttu-id="093b5-525">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="093b5-525">Allocation factor</span></span></th>
<th><span data-ttu-id="093b5-526">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-526">Amount</span></span></th>
<th><span data-ttu-id="093b5-527">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-528">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-528">CC002</span></span></td>
<td><span data-ttu-id="093b5-529">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-529">Finance</span></span></td>
<td><span data-ttu-id="093b5-530">35</span><span class="sxs-lookup"><span data-stu-id="093b5-530">35</span></span></td>
<td><span data-ttu-id="093b5-531">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="093b5-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="093b5-532">175.00</span><span class="sxs-lookup"><span data-stu-id="093b5-532">175.00</span></span></td>
<td><span data-ttu-id="093b5-533">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-534">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-534">CC003</span></span></td>
<td><span data-ttu-id="093b5-535">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-535">Assembly</span></span></td>
<td><span data-ttu-id="093b5-536">55</span><span class="sxs-lookup"><span data-stu-id="093b5-536">55</span></span></td>
<td><span data-ttu-id="093b5-537">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="093b5-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="093b5-538">275.00</span><span class="sxs-lookup"><span data-stu-id="093b5-538">275.00</span></span></td>
<td><span data-ttu-id="093b5-539">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-540">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-540">CC004</span></span></td>
<td><span data-ttu-id="093b5-541">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-541">Packaging</span></span></td>
<td><span data-ttu-id="093b5-542">10</span><span class="sxs-lookup"><span data-stu-id="093b5-542">10</span></span></td>
<td><span data-ttu-id="093b5-543">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="093b5-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="093b5-544">50,00</span><span class="sxs-lookup"><span data-stu-id="093b5-544">50.00</span></span></td>
<td><span data-ttu-id="093b5-545">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-546">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-546">CC002</span></span></td>
<td><span data-ttu-id="093b5-547">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-547">Finance</span></span></td>
<td><span data-ttu-id="093b5-548">35</span><span class="sxs-lookup"><span data-stu-id="093b5-548">35</span></span></td>
<td><span data-ttu-id="093b5-549">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="093b5-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="093b5-550">436.00</span><span class="sxs-lookup"><span data-stu-id="093b5-550">436.00</span></span></td>
<td><span data-ttu-id="093b5-551">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-552">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-552">CC003</span></span></td>
<td><span data-ttu-id="093b5-553">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-553">Assembly</span></span></td>
<td><span data-ttu-id="093b5-554">55</span><span class="sxs-lookup"><span data-stu-id="093b5-554">55</span></span></td>
<td><span data-ttu-id="093b5-555">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="093b5-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="093b5-556">685.14</span><span class="sxs-lookup"><span data-stu-id="093b5-556">685.14</span></span></td>
<td><span data-ttu-id="093b5-557">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-558">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-558">CC004</span></span></td>
<td><span data-ttu-id="093b5-559">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-559">Packaging</span></span></td>
<td><span data-ttu-id="093b5-560">10</span><span class="sxs-lookup"><span data-stu-id="093b5-560">10</span></span></td>
<td><span data-ttu-id="093b5-561">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="093b5-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="093b5-562">124.57</span><span class="sxs-lookup"><span data-stu-id="093b5-562">124.57</span></span></td>
<td><span data-ttu-id="093b5-563">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-564">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="093b5-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-565">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-565">Cost object</span></span></th>
<th><span data-ttu-id="093b5-566">Nagyság</span><span class="sxs-lookup"><span data-stu-id="093b5-566">Magnitude</span></span></th>
<th><span data-ttu-id="093b5-567">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="093b5-567">Allocation factor</span></span></th>
<th><span data-ttu-id="093b5-568">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-568">Amount</span></span></th>
<th><span data-ttu-id="093b5-569">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-570">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-570">CC003</span></span></td>
<td><span data-ttu-id="093b5-571">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-571">Assembly</span></span></td>
<td><span data-ttu-id="093b5-572">65</span><span class="sxs-lookup"><span data-stu-id="093b5-572">65</span></span></td>
<td><span data-ttu-id="093b5-573">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="093b5-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="093b5-574">438.75</span><span class="sxs-lookup"><span data-stu-id="093b5-574">438.75</span></span></td>
<td><span data-ttu-id="093b5-575">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-576">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-576">CC004</span></span></td>
<td><span data-ttu-id="093b5-577">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-577">Packaging</span></span></td>
<td><span data-ttu-id="093b5-578">35</span><span class="sxs-lookup"><span data-stu-id="093b5-578">35</span></span></td>
<td><span data-ttu-id="093b5-579">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="093b5-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="093b5-580">236.25</span><span class="sxs-lookup"><span data-stu-id="093b5-580">236.25</span></span></td>
<td><span data-ttu-id="093b5-581">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-582">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-582">CC003</span></span></td>
<td><span data-ttu-id="093b5-583">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-583">Assembly</span></span></td>
<td><span data-ttu-id="093b5-584">65</span><span class="sxs-lookup"><span data-stu-id="093b5-584">65</span></span></td>
<td><span data-ttu-id="093b5-585">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="093b5-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="093b5-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="093b5-586">5,297.69</span></span></td>
<td><span data-ttu-id="093b5-587">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-588">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-588">CC004</span></span></td>
<td><span data-ttu-id="093b5-589">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-589">Packaging</span></span></td>
<td><span data-ttu-id="093b5-590">35</span><span class="sxs-lookup"><span data-stu-id="093b5-590">35</span></span></td>
<td><span data-ttu-id="093b5-591">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="093b5-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="093b5-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="093b5-592">2,852.60</span></span></td>
<td><span data-ttu-id="093b5-593">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-594">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="093b5-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-595">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-595">Cost object</span></span></th>
<th><span data-ttu-id="093b5-596">Nagyság</span><span class="sxs-lookup"><span data-stu-id="093b5-596">Magnitude</span></span></th>
<th><span data-ttu-id="093b5-597">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="093b5-597">Allocation factor</span></span></th>
<th><span data-ttu-id="093b5-598">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-598">Amount</span></span></th>
<th><span data-ttu-id="093b5-599">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-600">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-600">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-601">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-601">Product 1</span></span></td>
<td><span data-ttu-id="093b5-602">60</span><span class="sxs-lookup"><span data-stu-id="093b5-602">60</span></span></td>
<td><span data-ttu-id="093b5-603">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="093b5-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="093b5-604">535.31</span><span class="sxs-lookup"><span data-stu-id="093b5-604">535.31</span></span></td>
<td><span data-ttu-id="093b5-605">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-606">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-606">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-607">2. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-607">Product 2</span></span></td>
<td><span data-ttu-id="093b5-608">20</span><span class="sxs-lookup"><span data-stu-id="093b5-608">20</span></span></td>
<td><span data-ttu-id="093b5-609">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="093b5-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="093b5-610">178.44</span><span class="sxs-lookup"><span data-stu-id="093b5-610">178.44</span></span></td>
<td><span data-ttu-id="093b5-611">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-612">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-612">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-613">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-613">Product 1</span></span></td>
<td><span data-ttu-id="093b5-614">60</span><span class="sxs-lookup"><span data-stu-id="093b5-614">60</span></span></td>
<td><span data-ttu-id="093b5-615">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="093b5-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="093b5-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="093b5-616">4,487.12</span></span></td>
<td><span data-ttu-id="093b5-617">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-618">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-618">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-619">2. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-619">Product 2</span></span></td>
<td><span data-ttu-id="093b5-620">20</span><span class="sxs-lookup"><span data-stu-id="093b5-620">20</span></span></td>
<td><span data-ttu-id="093b5-621">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="093b5-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="093b5-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="093b5-622">1,495.71</span></span></td>
<td><span data-ttu-id="093b5-623">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="093b5-624">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="093b5-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-625">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-625">Cost object</span></span></th>
<th><span data-ttu-id="093b5-626">Nagyság</span><span class="sxs-lookup"><span data-stu-id="093b5-626">Magnitude</span></span></th>
<th><span data-ttu-id="093b5-627">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="093b5-627">Allocation factor</span></span></th>
<th><span data-ttu-id="093b5-628">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-628">Amount</span></span></th>
<th><span data-ttu-id="093b5-629">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-630">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-630">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-631">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-631">Product 1</span></span></td>
<td><span data-ttu-id="093b5-632">80</span><span class="sxs-lookup"><span data-stu-id="093b5-632">80</span></span></td>
<td><span data-ttu-id="093b5-633">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="093b5-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="093b5-634">241.05</span><span class="sxs-lookup"><span data-stu-id="093b5-634">241.05</span></span></td>
<td><span data-ttu-id="093b5-635">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-636">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-636">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-637">2. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-637">Product 2</span></span></td>
<td><span data-ttu-id="093b5-638">15.</span><span class="sxs-lookup"><span data-stu-id="093b5-638">15</span></span></td>
<td><span data-ttu-id="093b5-639">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="093b5-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="093b5-640">45.20</span><span class="sxs-lookup"><span data-stu-id="093b5-640">45.20</span></span></td>
<td><span data-ttu-id="093b5-641">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-642">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-642">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-643">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-643">Product 1</span></span></td>
<td><span data-ttu-id="093b5-644">80</span><span class="sxs-lookup"><span data-stu-id="093b5-644">80</span></span></td>
<td><span data-ttu-id="093b5-645">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="093b5-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="093b5-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="093b5-646">2,507.09</span></span></td>
<td><span data-ttu-id="093b5-647">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-648">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-648">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-649">2. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-649">Product 2</span></span></td>
<td><span data-ttu-id="093b5-650">15.</span><span class="sxs-lookup"><span data-stu-id="093b5-650">15</span></span></td>
<td><span data-ttu-id="093b5-651">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="093b5-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="093b5-652">470.08</span><span class="sxs-lookup"><span data-stu-id="093b5-652">470.08</span></span></td>
<td><span data-ttu-id="093b5-653">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="093b5-654">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="093b5-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="093b5-655">Napló</span><span class="sxs-lookup"><span data-stu-id="093b5-655">Journal</span></span></th>
<th><span data-ttu-id="093b5-656">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="093b5-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="093b5-657">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="093b5-658">Verzió</span><span class="sxs-lookup"><span data-stu-id="093b5-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-659">00004</span><span class="sxs-lookup"><span data-stu-id="093b5-659">00004</span></span></td>
<td><span data-ttu-id="093b5-660">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="093b5-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="093b5-661">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="093b5-661">Fiscal</span></span></td>
<td><span data-ttu-id="093b5-662">2017</span><span class="sxs-lookup"><span data-stu-id="093b5-662">2017</span></span></td>
<td><span data-ttu-id="093b5-663">1. időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-663">Period 1</span></span></td>
<td><span data-ttu-id="093b5-664">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="093b5-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="093b5-665">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="093b5-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="093b5-666">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="093b5-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-667">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-668">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="093b5-668">Cost element</span></span></th>
<th><span data-ttu-id="093b5-669">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-669">Cost behavior</span></span></th>
<th><span data-ttu-id="093b5-670">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-671">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-672">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-672">CC001</span></span></td>
<td><span data-ttu-id="093b5-673">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-673">HR</span></span></td>
<td><span data-ttu-id="093b5-674">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-674">10001</span></span></td>
<td><span data-ttu-id="093b5-675">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-675">Electricity</span></span></td>
<td><span data-ttu-id="093b5-676">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-676">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-677">500.00</span><span class="sxs-lookup"><span data-stu-id="093b5-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-678">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-679">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-679">CC001</span></span></td>
<td><span data-ttu-id="093b5-680">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-680">HR</span></span></td>
<td><span data-ttu-id="093b5-681">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-681">10001</span></span></td>
<td><span data-ttu-id="093b5-682">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-682">Electricity</span></span></td>
<td><span data-ttu-id="093b5-683">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-683">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="093b5-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-685">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-686">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-686">CC002</span></span></td>
<td><span data-ttu-id="093b5-687">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-687">Finance</span></span></td>
<td><span data-ttu-id="093b5-688">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-688">10001</span></span></td>
<td><span data-ttu-id="093b5-689">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-689">Electricity</span></span></td>
<td><span data-ttu-id="093b5-690">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-690">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-691">675.00</span><span class="sxs-lookup"><span data-stu-id="093b5-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-692">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-693">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-693">CC002</span></span></td>
<td><span data-ttu-id="093b5-694">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-694">Finance</span></span></td>
<td><span data-ttu-id="093b5-695">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-695">10001</span></span></td>
<td><span data-ttu-id="093b5-696">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-696">Electricity</span></span></td>
<td><span data-ttu-id="093b5-697">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-697">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="093b5-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-699">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-700">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-700">CC003</span></span></td>
<td><span data-ttu-id="093b5-701">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-701">Assembly</span></span></td>
<td><span data-ttu-id="093b5-702">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-702">10001</span></span></td>
<td><span data-ttu-id="093b5-703">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-703">Electricity</span></span></td>
<td><span data-ttu-id="093b5-704">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-704">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-705">713.75</span><span class="sxs-lookup"><span data-stu-id="093b5-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-706">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-707">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-707">CC003</span></span></td>
<td><span data-ttu-id="093b5-708">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-708">Assembly</span></span></td>
<td><span data-ttu-id="093b5-709">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-709">10001</span></span></td>
<td><span data-ttu-id="093b5-710">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-710">Electricity</span></span></td>
<td><span data-ttu-id="093b5-711">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-711">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="093b5-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-713">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-714">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-714">CC003</span></span></td>
<td><span data-ttu-id="093b5-715">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-715">Packaging</span></span></td>
<td><span data-ttu-id="093b5-716">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-716">10001</span></span></td>
<td><span data-ttu-id="093b5-717">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-717">Electricity</span></span></td>
<td><span data-ttu-id="093b5-718">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-718">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-719">286.25</span><span class="sxs-lookup"><span data-stu-id="093b5-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-720">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-721">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-721">CC003</span></span></td>
<td><span data-ttu-id="093b5-722">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-722">Packaging</span></span></td>
<td><span data-ttu-id="093b5-723">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-723">10001</span></span></td>
<td><span data-ttu-id="093b5-724">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-724">Electricity</span></span></td>
<td><span data-ttu-id="093b5-725">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-725">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="093b5-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-727">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-728">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-728">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-729">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-729">Product 1</span></span></td>
<td><span data-ttu-id="093b5-730">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-730">10001</span></span></td>
<td><span data-ttu-id="093b5-731">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-731">Electricity</span></span></td>
<td><span data-ttu-id="093b5-732">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-732">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-733">776.36</span><span class="sxs-lookup"><span data-stu-id="093b5-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-734">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-735">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-735">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-736">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-736">Product 1</span></span></td>
<td><span data-ttu-id="093b5-737">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-737">10001</span></span></td>
<td><span data-ttu-id="093b5-738">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-738">Electricity</span></span></td>
<td><span data-ttu-id="093b5-739">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-739">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="093b5-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-741">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-742">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-742">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-743">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-743">Product 1</span></span></td>
<td><span data-ttu-id="093b5-744">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-744">10001</span></span></td>
<td><span data-ttu-id="093b5-745">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-745">Electricity</span></span></td>
<td><span data-ttu-id="093b5-746">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-746">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-747">223.64</span><span class="sxs-lookup"><span data-stu-id="093b5-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-748">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="093b5-749">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-749">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-750">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-750">Product 1</span></span></td>
<td><span data-ttu-id="093b5-751">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-751">10001</span></span></td>
<td><span data-ttu-id="093b5-752">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-752">Electricity</span></span></td>
<td><span data-ttu-id="093b5-753">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-753">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="093b5-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="093b5-755">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="093b5-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="093b5-756">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="093b5-757">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="093b5-757">Cost element</span></span></th>
<th><span data-ttu-id="093b5-758">Költség működése</span><span class="sxs-lookup"><span data-stu-id="093b5-758">Cost behavior</span></span></th>
<th><span data-ttu-id="093b5-759">Összeg</span><span class="sxs-lookup"><span data-stu-id="093b5-759">Amount</span></span></th>
<th><span data-ttu-id="093b5-760">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="093b5-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="093b5-761">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-761">CC001</span></span></td>
<td><span data-ttu-id="093b5-762">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-762">HR</span></span></td>
<td><span data-ttu-id="093b5-763">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-763">10001</span></span></td>
<td><span data-ttu-id="093b5-764">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-764">Electricity</span></span></td>
<td><span data-ttu-id="093b5-765">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-765">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="093b5-766">-500.00</span></span></td>
<td><span data-ttu-id="093b5-767">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-768">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-768">CC002</span></span></td>
<td><span data-ttu-id="093b5-769">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-769">Finance</span></span></td>
<td><span data-ttu-id="093b5-770">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-770">10001</span></span></td>
<td><span data-ttu-id="093b5-771">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-771">Electricity</span></span></td>
<td><span data-ttu-id="093b5-772">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-772">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-773">175.00</span><span class="sxs-lookup"><span data-stu-id="093b5-773">175.00</span></span></td>
<td><span data-ttu-id="093b5-774">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-775">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-775">CC003</span></span></td>
<td><span data-ttu-id="093b5-776">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-776">Assembly</span></span></td>
<td><span data-ttu-id="093b5-777">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-777">10001</span></span></td>
<td><span data-ttu-id="093b5-778">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-778">Electricity</span></span></td>
<td><span data-ttu-id="093b5-779">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-779">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-780">275.00</span><span class="sxs-lookup"><span data-stu-id="093b5-780">275.00</span></span></td>
<td><span data-ttu-id="093b5-781">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-782">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-782">CC004</span></span></td>
<td><span data-ttu-id="093b5-783">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-783">Packaging</span></span></td>
<td><span data-ttu-id="093b5-784">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-784">10001</span></span></td>
<td><span data-ttu-id="093b5-785">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-785">Electricity</span></span></td>
<td><span data-ttu-id="093b5-786">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-786">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-787">50,00</span><span class="sxs-lookup"><span data-stu-id="093b5-787">50,00</span></span></td>
<td><span data-ttu-id="093b5-788">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-789">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-789">CC001</span></span></td>
<td><span data-ttu-id="093b5-790">HR</span><span class="sxs-lookup"><span data-stu-id="093b5-790">HR</span></span></td>
<td><span data-ttu-id="093b5-791">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-791">10001</span></span></td>
<td><span data-ttu-id="093b5-792">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-792">Electricity</span></span></td>
<td><span data-ttu-id="093b5-793">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-793">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-794">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="093b5-794">-1,245.71</span></span></td>
<td><span data-ttu-id="093b5-795">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-796">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-796">CC002</span></span></td>
<td><span data-ttu-id="093b5-797">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-797">Finance</span></span></td>
<td><span data-ttu-id="093b5-798">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-798">10001</span></span></td>
<td><span data-ttu-id="093b5-799">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-799">Electricity</span></span></td>
<td><span data-ttu-id="093b5-800">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-800">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-801">436.00</span><span class="sxs-lookup"><span data-stu-id="093b5-801">436.00</span></span></td>
<td><span data-ttu-id="093b5-802">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-803">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-803">CC003</span></span></td>
<td><span data-ttu-id="093b5-804">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-804">Assembly</span></span></td>
<td><span data-ttu-id="093b5-805">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-805">10001</span></span></td>
<td><span data-ttu-id="093b5-806">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-806">Electricity</span></span></td>
<td><span data-ttu-id="093b5-807">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-807">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-808">685.14</span><span class="sxs-lookup"><span data-stu-id="093b5-808">685.14</span></span></td>
<td><span data-ttu-id="093b5-809">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-810">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-810">CC004</span></span></td>
<td><span data-ttu-id="093b5-811">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-811">Packaging</span></span></td>
<td><span data-ttu-id="093b5-812">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-812">10001</span></span></td>
<td><span data-ttu-id="093b5-813">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-813">Electricity</span></span></td>
<td><span data-ttu-id="093b5-814">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-814">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-815">124.57</span><span class="sxs-lookup"><span data-stu-id="093b5-815">124.57</span></span></td>
<td><span data-ttu-id="093b5-816">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-817">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-817">CC002</span></span></td>
<td><span data-ttu-id="093b5-818">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-818">Finance</span></span></td>
<td><span data-ttu-id="093b5-819">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-819">10001</span></span></td>
<td><span data-ttu-id="093b5-820">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-820">Electricity</span></span></td>
<td><span data-ttu-id="093b5-821">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-821">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-822">-675.00</span><span class="sxs-lookup"><span data-stu-id="093b5-822">-675.00</span></span></td>
<td><span data-ttu-id="093b5-823">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-824">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-824">CC003</span></span></td>
<td><span data-ttu-id="093b5-825">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-825">Assembly</span></span></td>
<td><span data-ttu-id="093b5-826">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-826">10001</span></span></td>
<td><span data-ttu-id="093b5-827">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-827">Electricity</span></span></td>
<td><span data-ttu-id="093b5-828">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-828">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-829">438.75</span><span class="sxs-lookup"><span data-stu-id="093b5-829">438.75</span></span></td>
<td><span data-ttu-id="093b5-830">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-831">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-831">CC004</span></span></td>
<td><span data-ttu-id="093b5-832">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-832">Packaging</span></span></td>
<td><span data-ttu-id="093b5-833">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-833">10001</span></span></td>
<td><span data-ttu-id="093b5-834">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-834">Electricity</span></span></td>
<td><span data-ttu-id="093b5-835">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-835">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-836">236.25</span><span class="sxs-lookup"><span data-stu-id="093b5-836">236.25</span></span></td>
<td><span data-ttu-id="093b5-837">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-838">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-838">CC002</span></span></td>
<td><span data-ttu-id="093b5-839">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="093b5-839">Finance</span></span></td>
<td><span data-ttu-id="093b5-840">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-840">10001</span></span></td>
<td><span data-ttu-id="093b5-841">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-841">Electricity</span></span></td>
<td><span data-ttu-id="093b5-842">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-842">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-843">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="093b5-843">-8,150.29</span></span></td>
<td><span data-ttu-id="093b5-844">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-845">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-845">CC003</span></span></td>
<td><span data-ttu-id="093b5-846">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-846">Assembly</span></span></td>
<td><span data-ttu-id="093b5-847">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-847">10001</span></span></td>
<td><span data-ttu-id="093b5-848">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-848">Electricity</span></span></td>
<td><span data-ttu-id="093b5-849">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-849">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="093b5-850">5,297.69</span></span></td>
<td><span data-ttu-id="093b5-851">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-852">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-852">CC004</span></span></td>
<td><span data-ttu-id="093b5-853">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="093b5-853">Packaging</span></span></td>
<td><span data-ttu-id="093b5-854">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-854">10001</span></span></td>
<td><span data-ttu-id="093b5-855">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-855">Electricity</span></span></td>
<td><span data-ttu-id="093b5-856">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-856">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="093b5-857">2,852.60</span></span></td>
<td><span data-ttu-id="093b5-858">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-859">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-859">CC003</span></span></td>
<td><span data-ttu-id="093b5-860">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-860">Assembly</span></span></td>
<td><span data-ttu-id="093b5-861">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-861">10001</span></span></td>
<td><span data-ttu-id="093b5-862">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-862">Electricity</span></span></td>
<td><span data-ttu-id="093b5-863">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-863">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-864">-713.75</span><span class="sxs-lookup"><span data-stu-id="093b5-864">-713.75</span></span></td>
<td><span data-ttu-id="093b5-865">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-866">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-866">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-867">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-867">Product 1</span></span></td>
<td><span data-ttu-id="093b5-868">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-868">10001</span></span></td>
<td><span data-ttu-id="093b5-869">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-869">Electricity</span></span></td>
<td><span data-ttu-id="093b5-870">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-870">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-871">535.31</span><span class="sxs-lookup"><span data-stu-id="093b5-871">535.31</span></span></td>
<td><span data-ttu-id="093b5-872">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-873">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-873">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-874">2. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-874">Product 2</span></span></td>
<td><span data-ttu-id="093b5-875">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-875">10001</span></span></td>
<td><span data-ttu-id="093b5-876">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-876">Electricity</span></span></td>
<td><span data-ttu-id="093b5-877">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-877">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-878">178.44</span><span class="sxs-lookup"><span data-stu-id="093b5-878">178.44</span></span></td>
<td><span data-ttu-id="093b5-879">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-880">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-880">CC003</span></span></td>
<td><span data-ttu-id="093b5-881">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-881">Assembly</span></span></td>
<td><span data-ttu-id="093b5-882">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-882">10001</span></span></td>
<td><span data-ttu-id="093b5-883">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-883">Electricity</span></span></td>
<td><span data-ttu-id="093b5-884">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-884">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-885">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="093b5-885">-5,982.83</span></span></td>
<td><span data-ttu-id="093b5-886">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-887">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-887">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-888">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-888">Product 1</span></span></td>
<td><span data-ttu-id="093b5-889">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-889">10001</span></span></td>
<td><span data-ttu-id="093b5-890">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-890">Electricity</span></span></td>
<td><span data-ttu-id="093b5-891">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-891">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="093b5-892">4,487.12</span></span></td>
<td><span data-ttu-id="093b5-893">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-894">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-894">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-895">2. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-895">Product 2</span></span></td>
<td><span data-ttu-id="093b5-896">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-896">10001</span></span></td>
<td><span data-ttu-id="093b5-897">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-897">Electricity</span></span></td>
<td><span data-ttu-id="093b5-898">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-898">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="093b5-899">1,495.71</span></span></td>
<td><span data-ttu-id="093b5-900">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-901">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-901">CC003</span></span></td>
<td><span data-ttu-id="093b5-902">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-902">Assembly</span></span></td>
<td><span data-ttu-id="093b5-903">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-903">10001</span></span></td>
<td><span data-ttu-id="093b5-904">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-904">Electricity</span></span></td>
<td><span data-ttu-id="093b5-905">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-905">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-906">-286.25</span><span class="sxs-lookup"><span data-stu-id="093b5-906">-286.25</span></span></td>
<td><span data-ttu-id="093b5-907">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-908">Term 1</span><span class="sxs-lookup"><span data-stu-id="093b5-908">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-909">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-909">Product 1</span></span></td>
<td><span data-ttu-id="093b5-910">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-910">10001</span></span></td>
<td><span data-ttu-id="093b5-911">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-911">Electricity</span></span></td>
<td><span data-ttu-id="093b5-912">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-912">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-913">241.05</span><span class="sxs-lookup"><span data-stu-id="093b5-913">241.05</span></span></td>
<td><span data-ttu-id="093b5-914">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-915">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-915">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-916">2. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-916">Product 2</span></span></td>
<td><span data-ttu-id="093b5-917">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-917">10001</span></span></td>
<td><span data-ttu-id="093b5-918">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-918">Electricity</span></span></td>
<td><span data-ttu-id="093b5-919">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-919">Fixed cost</span></span></td>
<td><span data-ttu-id="093b5-920">45.20</span><span class="sxs-lookup"><span data-stu-id="093b5-920">45.20</span></span></td>
<td><span data-ttu-id="093b5-921">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-922">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-922">CC003</span></span></td>
<td><span data-ttu-id="093b5-923">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="093b5-923">Assembly</span></span></td>
<td><span data-ttu-id="093b5-924">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-924">10001</span></span></td>
<td><span data-ttu-id="093b5-925">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-925">Electricity</span></span></td>
<td><span data-ttu-id="093b5-926">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-926">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-927">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="093b5-927">-2,977.17</span></span></td>
<td><span data-ttu-id="093b5-928">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-929">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-929">Prod 1</span></span></td>
<td><span data-ttu-id="093b5-930">1. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-930">Product 1</span></span></td>
<td><span data-ttu-id="093b5-931">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-931">10001</span></span></td>
<td><span data-ttu-id="093b5-932">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-932">Electricity</span></span></td>
<td><span data-ttu-id="093b5-933">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-933">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="093b5-934">2,507.09</span></span></td>
<td><span data-ttu-id="093b5-935">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="093b5-936">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-936">Prod 2</span></span></td>
<td><span data-ttu-id="093b5-937">2. termék</span><span class="sxs-lookup"><span data-stu-id="093b5-937">Product 2</span></span></td>
<td><span data-ttu-id="093b5-938">10001</span><span class="sxs-lookup"><span data-stu-id="093b5-938">10001</span></span></td>
<td><span data-ttu-id="093b5-939">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-939">Electricity</span></span></td>
<td><span data-ttu-id="093b5-940">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-940">Variable cost</span></span></td>
<td><span data-ttu-id="093b5-941">470.08</span><span class="sxs-lookup"><span data-stu-id="093b5-941">470.08</span></span></td>
<td><span data-ttu-id="093b5-942">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="093b5-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="093b5-943">Következtetés</span><span class="sxs-lookup"><span data-stu-id="093b5-943">Conclusion</span></span>
<span data-ttu-id="093b5-944">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="093b5-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="093b5-945">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="093b5-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="093b5-946">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="093b5-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="093b5-947">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="093b5-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="093b5-948">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="093b5-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="093b5-949">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="093b5-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="093b5-950">Összesen</span><span class="sxs-lookup"><span data-stu-id="093b5-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="093b5-951">CC099</span><span class="sxs-lookup"><span data-stu-id="093b5-951">CC099</span></span></th>
<th><span data-ttu-id="093b5-952">CC001</span><span class="sxs-lookup"><span data-stu-id="093b5-952">CC001</span></span></th>
<th><span data-ttu-id="093b5-953">CC002</span><span class="sxs-lookup"><span data-stu-id="093b5-953">CC002</span></span></th>
<th><span data-ttu-id="093b5-954">CC003</span><span class="sxs-lookup"><span data-stu-id="093b5-954">CC003</span></span></th>
<th><span data-ttu-id="093b5-955">CC004</span><span class="sxs-lookup"><span data-stu-id="093b5-955">CC004</span></span></th>
<th><span data-ttu-id="093b5-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="093b5-956">Proj 1</span></span></th>
<th><span data-ttu-id="093b5-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="093b5-957">Proj 2</span></span></th>
<th><span data-ttu-id="093b5-958">Term. 1</span><span class="sxs-lookup"><span data-stu-id="093b5-958">Prod 1</span></span></th>
<th><span data-ttu-id="093b5-959">Term. 2</span><span class="sxs-lookup"><span data-stu-id="093b5-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="093b5-960">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="093b5-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="093b5-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="093b5-970">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="093b5-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-971">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="093b5-972">Fix költség</span><span class="sxs-lookup"><span data-stu-id="093b5-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-973">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-974">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-975">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-976">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-977">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="093b5-978">776.36</span><span class="sxs-lookup"><span data-stu-id="093b5-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-979">223.64</span><span class="sxs-lookup"><span data-stu-id="093b5-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="093b5-981">Változó költség</span><span class="sxs-lookup"><span data-stu-id="093b5-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-982">000</span><span class="sxs-lookup"><span data-stu-id="093b5-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-983">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-984">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-985">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-986">0,00</span><span class="sxs-lookup"><span data-stu-id="093b5-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-987">30.00</span><span class="sxs-lookup"><span data-stu-id="093b5-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-988">1000</span><span class="sxs-lookup"><span data-stu-id="093b5-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="093b5-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="093b5-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="093b5-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="093b5-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="093b5-992">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="093b5-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="093b5-993">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="093b5-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="093b5-994">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="093b5-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="093b5-995">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="093b5-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="093b5-996">Részletesebb tájékoztatás: [Költségösszesítési irányelv](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="093b5-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



