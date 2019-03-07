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
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "335117"
---
# <a name="overhead-calculation"></a><span data-ttu-id="0a241-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="0a241-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a241-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="0a241-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="0a241-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="0a241-105">Term definition</span></span>
---------------

<span data-ttu-id="0a241-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="0a241-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="0a241-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="0a241-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="0a241-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="0a241-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="0a241-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="0a241-109">Rent</span></span>
-   <span data-ttu-id="0a241-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-110">Electricity</span></span>
-   <span data-ttu-id="0a241-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="0a241-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="0a241-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="0a241-112">Overhead calculation overview</span></span>
<span data-ttu-id="0a241-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="0a241-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="0a241-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="0a241-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="0a241-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="0a241-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="0a241-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="0a241-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="0a241-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="0a241-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="0a241-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="0a241-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="0a241-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="0a241-119">Version type</span></span>
-   <span data-ttu-id="0a241-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="0a241-120">Date and time</span></span>
-   <span data-ttu-id="0a241-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="0a241-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="0a241-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="0a241-122">Fiscal year</span></span>
-   <span data-ttu-id="0a241-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-123">Fiscal period</span></span>

<span data-ttu-id="0a241-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="0a241-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="0a241-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="0a241-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="0a241-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="0a241-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="0a241-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="0a241-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="0a241-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="0a241-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="0a241-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="0a241-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="0a241-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="0a241-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="0a241-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="0a241-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="0a241-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="0a241-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="0a241-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="0a241-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="0a241-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="0a241-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="0a241-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="0a241-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="0a241-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="0a241-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="0a241-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="0a241-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0a241-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="0a241-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="0a241-140">Main account</span></span></th>
<th><span data-ttu-id="0a241-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="0a241-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="0a241-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="0a241-143">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-143">CC099</span></span></td>
<td><span data-ttu-id="0a241-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-144">Default cost center</span></span></td>
<td><span data-ttu-id="0a241-145">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-145">10001</span></span></td>
<td><span data-ttu-id="0a241-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-146">Electricity</span></span></td>
<td><span data-ttu-id="0a241-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="0a241-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="0a241-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="0a241-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="0a241-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="0a241-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="0a241-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="0a241-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="0a241-151">Define the cost behavior rule</span></span>

<span data-ttu-id="0a241-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="0a241-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="0a241-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="0a241-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="0a241-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="0a241-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="0a241-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="0a241-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="0a241-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="0a241-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="0a241-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="0a241-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="0a241-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="0a241-159">Napló</span><span class="sxs-lookup"><span data-stu-id="0a241-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0a241-160">Napló</span><span class="sxs-lookup"><span data-stu-id="0a241-160">Journal</span></span></th>
<th><span data-ttu-id="0a241-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="0a241-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="0a241-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="0a241-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="0a241-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-164">00001</span><span class="sxs-lookup"><span data-stu-id="0a241-164">00001</span></span></td>
<td><span data-ttu-id="0a241-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="0a241-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="0a241-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="0a241-166">Fiscal</span></span></td>
<td><span data-ttu-id="0a241-167">2017</span><span class="sxs-lookup"><span data-stu-id="0a241-167">2017</span></span></td>
<td><span data-ttu-id="0a241-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-168">Period 1</span></span></td>
<td><span data-ttu-id="0a241-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="0a241-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="0a241-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0a241-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="0a241-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="0a241-173">Cost element</span></span></th>
<th><span data-ttu-id="0a241-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-174">Cost behavior</span></span></th>
<th><span data-ttu-id="0a241-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="0a241-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="0a241-177">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-177">CC099</span></span></td>
<td><span data-ttu-id="0a241-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-178">Default cost center</span></span></td>
<td><span data-ttu-id="0a241-179">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-179">10001</span></span></td>
<td><span data-ttu-id="0a241-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-180">Electricity</span></span></td>
<td><span data-ttu-id="0a241-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="0a241-181">Unclassified</span></span></td>
<td><span data-ttu-id="0a241-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="0a241-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="0a241-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="0a241-185">Cost element</span></span></th>
<th><span data-ttu-id="0a241-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-186">Cost behavior</span></span></th>
<th><span data-ttu-id="0a241-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-187">Amount</span></span></th>
<th><span data-ttu-id="0a241-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="0a241-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-189">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-189">CC099</span></span></td>
<td><span data-ttu-id="0a241-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-190">Default cost center</span></span></td>
<td><span data-ttu-id="0a241-191">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-191">10001</span></span></td>
<td><span data-ttu-id="0a241-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-192">Electricity</span></span></td>
<td><span data-ttu-id="0a241-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="0a241-193">Unclassified</span></span></td>
<td><span data-ttu-id="0a241-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-194">10,000.00</span></span></td>
<td><span data-ttu-id="0a241-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="0a241-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-196">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-196">CC099</span></span></td>
<td><span data-ttu-id="0a241-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-197">Default cost center</span></span></td>
<td><span data-ttu-id="0a241-198">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-198">10001</span></span></td>
<td><span data-ttu-id="0a241-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-199">Electricity</span></span></td>
<td><span data-ttu-id="0a241-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="0a241-200">Unclassified</span></span></td>
<td><span data-ttu-id="0a241-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-201">-10,000.00</span></span></td>
<td><span data-ttu-id="0a241-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-203">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-203">CC099</span></span></td>
<td><span data-ttu-id="0a241-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-204">Default cost center</span></span></td>
<td><span data-ttu-id="0a241-205">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-205">10001</span></span></td>
<td><span data-ttu-id="0a241-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-206">Electricity</span></span></td>
<td><span data-ttu-id="0a241-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-207">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="0a241-208">1,000.00</span></span></td>
<td><span data-ttu-id="0a241-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-210">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-210">CC099</span></span></td>
<td><span data-ttu-id="0a241-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-211">Default cost center</span></span></td>
<td><span data-ttu-id="0a241-212">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-212">10001</span></span></td>
<td><span data-ttu-id="0a241-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-213">Electricity</span></span></td>
<td><span data-ttu-id="0a241-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-214">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-215">9,000.00</span></span></td>
<td><span data-ttu-id="0a241-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-217">További információért lásd: [Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="0a241-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="0a241-218">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="0a241-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="0a241-219">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="0a241-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="0a241-220">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="0a241-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="0a241-221">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="0a241-221">Define the cost distribution rule</span></span>

<span data-ttu-id="0a241-222">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="0a241-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="0a241-223">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="0a241-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="0a241-224">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="0a241-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="0a241-225">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="0a241-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="0a241-226">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="0a241-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="0a241-227">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="0a241-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-228">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-228">Cost object</span></span></th>
<th><span data-ttu-id="0a241-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="0a241-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-230">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-230">CC001</span></span></td>
<td><span data-ttu-id="0a241-231">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-231">HR</span></span></td>
<td><span data-ttu-id="0a241-232">1000</span><span class="sxs-lookup"><span data-stu-id="0a241-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-233">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-233">CC002</span></span></td>
<td><span data-ttu-id="0a241-234">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-234">Finance</span></span></td>
<td><span data-ttu-id="0a241-235">6,000</span><span class="sxs-lookup"><span data-stu-id="0a241-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-236">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-236">CC003</span></span></td>
<td><span data-ttu-id="0a241-237">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-237">Assembly</span></span></td>
<td><span data-ttu-id="0a241-238">0</span><span class="sxs-lookup"><span data-stu-id="0a241-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-239">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="0a241-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-240">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-240">Cost object</span></span></th>
<th><span data-ttu-id="0a241-241">Nagyság</span><span class="sxs-lookup"><span data-stu-id="0a241-241">Magnitude</span></span></th>
<th><span data-ttu-id="0a241-242">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="0a241-242">Allocation factor</span></span></th>
<th><span data-ttu-id="0a241-243">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-244">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-244">CC001</span></span></td>
<td><span data-ttu-id="0a241-245">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-245">HR</span></span></td>
<td><span data-ttu-id="0a241-246">1000</span><span class="sxs-lookup"><span data-stu-id="0a241-246">1,000</span></span></td>
<td><span data-ttu-id="0a241-247">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="0a241-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="0a241-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-249">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-249">CC002</span></span></td>
<td><span data-ttu-id="0a241-250">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-250">Finance</span></span></td>
<td><span data-ttu-id="0a241-251">6,000</span><span class="sxs-lookup"><span data-stu-id="0a241-251">6,000</span></span></td>
<td><span data-ttu-id="0a241-252">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="0a241-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="0a241-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-254">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-254">CC003</span></span></td>
<td><span data-ttu-id="0a241-255">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-255">Assembly</span></span></td>
<td><span data-ttu-id="0a241-256">0</span><span class="sxs-lookup"><span data-stu-id="0a241-256">0</span></span></td>
<td><span data-ttu-id="0a241-257">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="0a241-258">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-259">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="0a241-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="0a241-260">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: (Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="0a241-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-261">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-261">Cost object</span></span></th>
<th><span data-ttu-id="0a241-262">Receptúra</span><span class="sxs-lookup"><span data-stu-id="0a241-262">Formula</span></span></th>
<th><span data-ttu-id="0a241-263">Nagyság</span><span class="sxs-lookup"><span data-stu-id="0a241-263">Magnitude</span></span></th>
<th><span data-ttu-id="0a241-264">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="0a241-264">Allocation factor</span></span></th>
<th><span data-ttu-id="0a241-265">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-266">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-266">CC001</span></span></td>
<td><span data-ttu-id="0a241-267">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-267">HR</span></span></td>
<td><span data-ttu-id="0a241-268">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="0a241-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="0a241-269">1</span><span class="sxs-lookup"><span data-stu-id="0a241-269">1</span></span></td>
<td><span data-ttu-id="0a241-270">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="0a241-271">500.00</span><span class="sxs-lookup"><span data-stu-id="0a241-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-272">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-272">CC002</span></span></td>
<td><span data-ttu-id="0a241-273">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-273">Finance</span></span></td>
<td><span data-ttu-id="0a241-274">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="0a241-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="0a241-275">1</span><span class="sxs-lookup"><span data-stu-id="0a241-275">1</span></span></td>
<td><span data-ttu-id="0a241-276">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="0a241-277">500.00</span><span class="sxs-lookup"><span data-stu-id="0a241-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-278">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-278">CC003</span></span></td>
<td><span data-ttu-id="0a241-279">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-279">Assembly</span></span></td>
<td><span data-ttu-id="0a241-280">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="0a241-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="0a241-281">0</span><span class="sxs-lookup"><span data-stu-id="0a241-281">0</span></span></td>
<td><span data-ttu-id="0a241-282">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="0a241-283">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="0a241-284">Napló</span><span class="sxs-lookup"><span data-stu-id="0a241-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0a241-285">Napló</span><span class="sxs-lookup"><span data-stu-id="0a241-285">Journal</span></span></th>
<th><span data-ttu-id="0a241-286">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="0a241-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="0a241-287">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="0a241-288">Verzió</span><span class="sxs-lookup"><span data-stu-id="0a241-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-289">00002</span><span class="sxs-lookup"><span data-stu-id="0a241-289">00002</span></span></td>
<td><span data-ttu-id="0a241-290">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="0a241-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="0a241-291">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="0a241-291">Fiscal</span></span></td>
<td><span data-ttu-id="0a241-292">2017</span><span class="sxs-lookup"><span data-stu-id="0a241-292">2017</span></span></td>
<td><span data-ttu-id="0a241-293">1. időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-293">Period 1</span></span></td>
<td><span data-ttu-id="0a241-294">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="0a241-295">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="0a241-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0a241-296">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="0a241-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-297">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-298">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="0a241-298">Cost element</span></span></th>
<th><span data-ttu-id="0a241-299">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-299">Cost behavior</span></span></th>
<th><span data-ttu-id="0a241-300">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-301">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-302">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-302">CC099</span></span></td>
<td><span data-ttu-id="0a241-303">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-303">Default cost center</span></span></td>
<td><span data-ttu-id="0a241-304">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-304">10001</span></span></td>
<td><span data-ttu-id="0a241-305">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-305">Electricity</span></span></td>
<td><span data-ttu-id="0a241-306">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-306">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="0a241-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-308">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-309">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-309">CC099</span></span></td>
<td><span data-ttu-id="0a241-310">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-310">Default cost center</span></span></td>
<td><span data-ttu-id="0a241-311">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-311">10001</span></span></td>
<td><span data-ttu-id="0a241-312">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-312">Electricity</span></span></td>
<td><span data-ttu-id="0a241-313">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-313">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="0a241-315">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="0a241-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-316">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-317">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="0a241-317">Cost element</span></span></th>
<th><span data-ttu-id="0a241-318">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-318">Cost behavior</span></span></th>
<th><span data-ttu-id="0a241-319">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-319">Amount</span></span></th>
<th><span data-ttu-id="0a241-320">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="0a241-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-321">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-321">CC099</span></span></td>
<td><span data-ttu-id="0a241-322">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-322">Default cost center</span></span></td>
<td><span data-ttu-id="0a241-323">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-323">10001</span></span></td>
<td><span data-ttu-id="0a241-324">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-324">Electricity</span></span></td>
<td><span data-ttu-id="0a241-325">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-325">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="0a241-326">-1,000.00</span></span></td>
<td><span data-ttu-id="0a241-327">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-328">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-328">CC001</span></span></td>
<td><span data-ttu-id="0a241-329">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-329">HR</span></span></td>
<td><span data-ttu-id="0a241-330">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-330">10001</span></span></td>
<td><span data-ttu-id="0a241-331">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-331">Electricity</span></span></td>
<td><span data-ttu-id="0a241-332">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-332">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-333">500.00</span><span class="sxs-lookup"><span data-stu-id="0a241-333">500.00</span></span></td>
<td><span data-ttu-id="0a241-334">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-335">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-335">CC002</span></span></td>
<td><span data-ttu-id="0a241-336">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-336">Finance</span></span></td>
<td><span data-ttu-id="0a241-337">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-337">10001</span></span></td>
<td><span data-ttu-id="0a241-338">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-338">Electricity</span></span></td>
<td><span data-ttu-id="0a241-339">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-339">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-340">500.00</span><span class="sxs-lookup"><span data-stu-id="0a241-340">500.00</span></span></td>
<td><span data-ttu-id="0a241-341">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-342">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-342">CC099</span></span></td>
<td><span data-ttu-id="0a241-343">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="0a241-343">Default cost center</span></span></td>
<td><span data-ttu-id="0a241-344">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-344">10001</span></span></td>
<td><span data-ttu-id="0a241-345">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-345">Electricity</span></span></td>
<td><span data-ttu-id="0a241-346">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-346">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-347">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="0a241-347">-9,000.00</span></span></td>
<td><span data-ttu-id="0a241-348">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-349">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-349">CC001</span></span></td>
<td><span data-ttu-id="0a241-350">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-350">HR</span></span></td>
<td><span data-ttu-id="0a241-351">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-351">10001</span></span></td>
<td><span data-ttu-id="0a241-352">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-352">Electricity</span></span></td>
<td><span data-ttu-id="0a241-353">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-353">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="0a241-354">1,285.71</span></span></td>
<td><span data-ttu-id="0a241-355">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-356">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-356">CC002</span></span></td>
<td><span data-ttu-id="0a241-357">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-357">Finance</span></span></td>
<td><span data-ttu-id="0a241-358">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-358">10001</span></span></td>
<td><span data-ttu-id="0a241-359">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-359">Electricity</span></span></td>
<td><span data-ttu-id="0a241-360">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-360">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="0a241-361">7,714.29</span></span></td>
<td><span data-ttu-id="0a241-362">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-363">További információért lásd: [Költségelosztási irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="0a241-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="0a241-364">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="0a241-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="0a241-365">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="0a241-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="0a241-366">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="0a241-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="0a241-367">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="0a241-367">Define the overhead rate</span></span>

<span data-ttu-id="0a241-368">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="0a241-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="0a241-369">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="0a241-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-370">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-370">Cost object</span></span></th>
<th><span data-ttu-id="0a241-371">óra</span><span class="sxs-lookup"><span data-stu-id="0a241-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="0a241-372">Proj 1</span></span></td>
<td><span data-ttu-id="0a241-373">1. projekt</span><span class="sxs-lookup"><span data-stu-id="0a241-373">Project 1</span></span></td>
<td><span data-ttu-id="0a241-374">3</span><span class="sxs-lookup"><span data-stu-id="0a241-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="0a241-375">Proj 2</span></span></td>
<td><span data-ttu-id="0a241-376">2. projekt</span><span class="sxs-lookup"><span data-stu-id="0a241-376">Project 2</span></span></td>
<td><span data-ttu-id="0a241-377">1</span><span class="sxs-lookup"><span data-stu-id="0a241-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-378">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="0a241-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-379">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-379">Cost object</span></span></th>
<th><span data-ttu-id="0a241-380">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="0a241-380">Cost element</span></span></th>
<th><span data-ttu-id="0a241-381">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-381">Cost behavior</span></span></th>
<th><span data-ttu-id="0a241-382">Egységek</span><span class="sxs-lookup"><span data-stu-id="0a241-382">Units</span></span></th>
<th><span data-ttu-id="0a241-383">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="0a241-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-384">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-384">CC001</span></span></td>
<td><span data-ttu-id="0a241-385">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-385">HR</span></span></td>
<td><span data-ttu-id="0a241-386">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-386">10001</span></span></td>
<td><span data-ttu-id="0a241-387">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-387">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-388">1</span><span class="sxs-lookup"><span data-stu-id="0a241-388">1</span></span></td>
<td><span data-ttu-id="0a241-389">10</span><span class="sxs-lookup"><span data-stu-id="0a241-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-390">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="0a241-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-391">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-391">Cost object</span></span></th>
<th><span data-ttu-id="0a241-392">Nagyság</span><span class="sxs-lookup"><span data-stu-id="0a241-392">Magnitude</span></span></th>
<th><span data-ttu-id="0a241-393">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="0a241-393">Cost element</span></span></th>
<th><span data-ttu-id="0a241-394">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="0a241-394">Allocation factor</span></span></th>
<th><span data-ttu-id="0a241-395">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="0a241-396">Proj 1</span></span></td>
<td><span data-ttu-id="0a241-397">1. projekt</span><span class="sxs-lookup"><span data-stu-id="0a241-397">Project 1</span></span></td>
<td><span data-ttu-id="0a241-398">3</span><span class="sxs-lookup"><span data-stu-id="0a241-398">3</span></span></td>
<td><span data-ttu-id="0a241-399">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-399">10001</span></span></td>
<td><span data-ttu-id="0a241-400">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="0a241-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="0a241-401">30.00</span><span class="sxs-lookup"><span data-stu-id="0a241-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="0a241-402">Proj 2</span></span></td>
<td><span data-ttu-id="0a241-403">2. projekt</span><span class="sxs-lookup"><span data-stu-id="0a241-403">Project 2</span></span></td>
<td><span data-ttu-id="0a241-404">1</span><span class="sxs-lookup"><span data-stu-id="0a241-404">1</span></span></td>
<td><span data-ttu-id="0a241-405">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-405">10001</span></span></td>
<td><span data-ttu-id="0a241-406">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="0a241-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="0a241-407">10.00</span><span class="sxs-lookup"><span data-stu-id="0a241-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="0a241-408">Napló</span><span class="sxs-lookup"><span data-stu-id="0a241-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0a241-409">Napló</span><span class="sxs-lookup"><span data-stu-id="0a241-409">Journal</span></span></th>
<th><span data-ttu-id="0a241-410">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="0a241-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="0a241-411">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="0a241-412">Verzió</span><span class="sxs-lookup"><span data-stu-id="0a241-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-413">00003</span><span class="sxs-lookup"><span data-stu-id="0a241-413">00003</span></span></td>
<td><span data-ttu-id="0a241-414">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="0a241-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="0a241-415">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="0a241-415">Fiscal</span></span></td>
<td><span data-ttu-id="0a241-416">2017</span><span class="sxs-lookup"><span data-stu-id="0a241-416">2017</span></span></td>
<td><span data-ttu-id="0a241-417">1. időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-417">Period 1</span></span></td>
<td><span data-ttu-id="0a241-418">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="0a241-419">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="0a241-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0a241-420">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="0a241-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-421">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-421">Cost object</span></span></th>
<th><span data-ttu-id="0a241-422">Nagyság</span><span class="sxs-lookup"><span data-stu-id="0a241-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-423">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="0a241-424">Proj 1</span></span></td>
<td><span data-ttu-id="0a241-425">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="0a241-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="0a241-426">3,00</span><span class="sxs-lookup"><span data-stu-id="0a241-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-427">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="0a241-428">Proj 2</span></span></td>
<td><span data-ttu-id="0a241-429">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="0a241-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="0a241-430">1.00</span><span class="sxs-lookup"><span data-stu-id="0a241-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="0a241-431">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="0a241-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-432">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-433">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="0a241-433">Cost element</span></span></th>
<th><span data-ttu-id="0a241-434">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-434">Cost behavior</span></span></th>
<th><span data-ttu-id="0a241-435">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-435">Amount</span></span></th>
<th><span data-ttu-id="0a241-436">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="0a241-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="0a241-437">CC0001</span></span></td>
<td><span data-ttu-id="0a241-438">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-438">HR</span></span></td>
<td><span data-ttu-id="0a241-439">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-439">10001</span></span></td>
<td><span data-ttu-id="0a241-440">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-440">Electricity</span></span></td>
<td><span data-ttu-id="0a241-441">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-441">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-442">-30.00</span><span class="sxs-lookup"><span data-stu-id="0a241-442">-30.00</span></span></td>
<td><span data-ttu-id="0a241-443">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="0a241-444">Proj 1</span></span></td>
<td><span data-ttu-id="0a241-445">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="0a241-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="0a241-446">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-446">10001</span></span></td>
<td><span data-ttu-id="0a241-447">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-447">Electricity</span></span></td>
<td><span data-ttu-id="0a241-448">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-448">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-449">30.00</span><span class="sxs-lookup"><span data-stu-id="0a241-449">30.00</span></span></td>
<td><span data-ttu-id="0a241-450">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-451">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-451">CC001</span></span></td>
<td><span data-ttu-id="0a241-452">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-452">HR</span></span></td>
<td><span data-ttu-id="0a241-453">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-453">10001</span></span></td>
<td><span data-ttu-id="0a241-454">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-454">Electricity</span></span></td>
<td><span data-ttu-id="0a241-455">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-455">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="0a241-456">-10.00</span></span></td>
<td><span data-ttu-id="0a241-457">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="0a241-458">Proj 2</span></span></td>
<td><span data-ttu-id="0a241-459">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="0a241-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="0a241-460">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-460">10001</span></span></td>
<td><span data-ttu-id="0a241-461">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-461">Electricity</span></span></td>
<td><span data-ttu-id="0a241-462">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-462">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-463">10,00</span><span class="sxs-lookup"><span data-stu-id="0a241-463">10.00</span></span></td>
<td><span data-ttu-id="0a241-464">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-465">További információ: [Járulékosköltség-számítás végrehajtása](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="0a241-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="0a241-466">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="0a241-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="0a241-467">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="0a241-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="0a241-468">A Finance and Operations a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="0a241-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="0a241-469">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="0a241-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="0a241-470">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="0a241-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="0a241-471">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="0a241-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="0a241-472">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="0a241-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="0a241-473">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="0a241-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="0a241-474">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="0a241-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="0a241-475">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="0a241-475">Define the cost allocation</span></span>

<span data-ttu-id="0a241-476">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="0a241-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="0a241-477">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="0a241-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="0a241-478">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="0a241-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-479">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-479">Cost object</span></span></th>
<th><span data-ttu-id="0a241-480">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="0a241-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-481">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-481">CC002</span></span></td>
<td><span data-ttu-id="0a241-482">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-482">Finance</span></span></td>
<td><span data-ttu-id="0a241-483">35</span><span class="sxs-lookup"><span data-stu-id="0a241-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-484">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-484">CC003</span></span></td>
<td><span data-ttu-id="0a241-485">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-485">Assembly</span></span></td>
<td><span data-ttu-id="0a241-486">55</span><span class="sxs-lookup"><span data-stu-id="0a241-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-487">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-487">CC004</span></span></td>
<td><span data-ttu-id="0a241-488">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-488">Packaging</span></span></td>
<td><span data-ttu-id="0a241-489">10</span><span class="sxs-lookup"><span data-stu-id="0a241-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-490">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="0a241-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="0a241-491">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="0a241-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-492">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-492">Cost object</span></span></th>
<th><span data-ttu-id="0a241-493">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="0a241-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-494">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-494">CC003</span></span></td>
<td><span data-ttu-id="0a241-495">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-495">Assembly</span></span></td>
<td><span data-ttu-id="0a241-496">65</span><span class="sxs-lookup"><span data-stu-id="0a241-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-497">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-497">CC004</span></span></td>
<td><span data-ttu-id="0a241-498">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-498">Packaging</span></span></td>
<td><span data-ttu-id="0a241-499">35</span><span class="sxs-lookup"><span data-stu-id="0a241-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-500">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="0a241-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="0a241-501">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="0a241-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-502">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-502">Cost object</span></span></th>
<th><span data-ttu-id="0a241-503">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="0a241-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-504">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-504">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-505">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-505">Product 1</span></span></td>
<td><span data-ttu-id="0a241-506">60</span><span class="sxs-lookup"><span data-stu-id="0a241-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-507">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-507">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-508">2. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-508">Product 2</span></span></td>
<td><span data-ttu-id="0a241-509">20</span><span class="sxs-lookup"><span data-stu-id="0a241-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-510">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="0a241-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="0a241-511">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="0a241-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-512">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-512">Cost object</span></span></th>
<th><span data-ttu-id="0a241-513">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="0a241-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-514">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-514">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-515">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-515">Product 1</span></span></td>
<td><span data-ttu-id="0a241-516">80</span><span class="sxs-lookup"><span data-stu-id="0a241-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-517">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-517">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-518">2. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-518">Product 2</span></span></td>
<td><span data-ttu-id="0a241-519">15.</span><span class="sxs-lookup"><span data-stu-id="0a241-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="0a241-520">A Finance and Operations esetében a statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="0a241-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="0a241-521">További információk: [Statisztikaimérték-szolgáltató sablon](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="0a241-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="0a241-522">Az alábbi táblázat azt az eredményt mutatja, amikor a HR szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="0a241-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-523">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-523">Cost object</span></span></th>
<th><span data-ttu-id="0a241-524">Nagyság</span><span class="sxs-lookup"><span data-stu-id="0a241-524">Magnitude</span></span></th>
<th><span data-ttu-id="0a241-525">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="0a241-525">Allocation factor</span></span></th>
<th><span data-ttu-id="0a241-526">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-526">Amount</span></span></th>
<th><span data-ttu-id="0a241-527">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-528">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-528">CC002</span></span></td>
<td><span data-ttu-id="0a241-529">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-529">Finance</span></span></td>
<td><span data-ttu-id="0a241-530">35</span><span class="sxs-lookup"><span data-stu-id="0a241-530">35</span></span></td>
<td><span data-ttu-id="0a241-531">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="0a241-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="0a241-532">175.00</span><span class="sxs-lookup"><span data-stu-id="0a241-532">175.00</span></span></td>
<td><span data-ttu-id="0a241-533">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-534">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-534">CC003</span></span></td>
<td><span data-ttu-id="0a241-535">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-535">Assembly</span></span></td>
<td><span data-ttu-id="0a241-536">55</span><span class="sxs-lookup"><span data-stu-id="0a241-536">55</span></span></td>
<td><span data-ttu-id="0a241-537">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="0a241-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="0a241-538">275.00</span><span class="sxs-lookup"><span data-stu-id="0a241-538">275.00</span></span></td>
<td><span data-ttu-id="0a241-539">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-540">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-540">CC004</span></span></td>
<td><span data-ttu-id="0a241-541">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-541">Packaging</span></span></td>
<td><span data-ttu-id="0a241-542">10</span><span class="sxs-lookup"><span data-stu-id="0a241-542">10</span></span></td>
<td><span data-ttu-id="0a241-543">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="0a241-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="0a241-544">50,00</span><span class="sxs-lookup"><span data-stu-id="0a241-544">50.00</span></span></td>
<td><span data-ttu-id="0a241-545">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-546">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-546">CC002</span></span></td>
<td><span data-ttu-id="0a241-547">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-547">Finance</span></span></td>
<td><span data-ttu-id="0a241-548">35</span><span class="sxs-lookup"><span data-stu-id="0a241-548">35</span></span></td>
<td><span data-ttu-id="0a241-549">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="0a241-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="0a241-550">436.00</span><span class="sxs-lookup"><span data-stu-id="0a241-550">436.00</span></span></td>
<td><span data-ttu-id="0a241-551">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-552">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-552">CC003</span></span></td>
<td><span data-ttu-id="0a241-553">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-553">Assembly</span></span></td>
<td><span data-ttu-id="0a241-554">55</span><span class="sxs-lookup"><span data-stu-id="0a241-554">55</span></span></td>
<td><span data-ttu-id="0a241-555">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="0a241-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="0a241-556">685.14</span><span class="sxs-lookup"><span data-stu-id="0a241-556">685.14</span></span></td>
<td><span data-ttu-id="0a241-557">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-558">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-558">CC004</span></span></td>
<td><span data-ttu-id="0a241-559">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-559">Packaging</span></span></td>
<td><span data-ttu-id="0a241-560">10</span><span class="sxs-lookup"><span data-stu-id="0a241-560">10</span></span></td>
<td><span data-ttu-id="0a241-561">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="0a241-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="0a241-562">124.57</span><span class="sxs-lookup"><span data-stu-id="0a241-562">124.57</span></span></td>
<td><span data-ttu-id="0a241-563">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-564">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="0a241-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-565">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-565">Cost object</span></span></th>
<th><span data-ttu-id="0a241-566">Nagyság</span><span class="sxs-lookup"><span data-stu-id="0a241-566">Magnitude</span></span></th>
<th><span data-ttu-id="0a241-567">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="0a241-567">Allocation factor</span></span></th>
<th><span data-ttu-id="0a241-568">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-568">Amount</span></span></th>
<th><span data-ttu-id="0a241-569">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-570">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-570">CC003</span></span></td>
<td><span data-ttu-id="0a241-571">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-571">Assembly</span></span></td>
<td><span data-ttu-id="0a241-572">65</span><span class="sxs-lookup"><span data-stu-id="0a241-572">65</span></span></td>
<td><span data-ttu-id="0a241-573">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="0a241-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="0a241-574">438.75</span><span class="sxs-lookup"><span data-stu-id="0a241-574">438.75</span></span></td>
<td><span data-ttu-id="0a241-575">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-576">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-576">CC004</span></span></td>
<td><span data-ttu-id="0a241-577">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-577">Packaging</span></span></td>
<td><span data-ttu-id="0a241-578">35</span><span class="sxs-lookup"><span data-stu-id="0a241-578">35</span></span></td>
<td><span data-ttu-id="0a241-579">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="0a241-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="0a241-580">236.25</span><span class="sxs-lookup"><span data-stu-id="0a241-580">236.25</span></span></td>
<td><span data-ttu-id="0a241-581">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-582">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-582">CC003</span></span></td>
<td><span data-ttu-id="0a241-583">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-583">Assembly</span></span></td>
<td><span data-ttu-id="0a241-584">65</span><span class="sxs-lookup"><span data-stu-id="0a241-584">65</span></span></td>
<td><span data-ttu-id="0a241-585">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="0a241-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="0a241-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="0a241-586">5,297.69</span></span></td>
<td><span data-ttu-id="0a241-587">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-588">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-588">CC004</span></span></td>
<td><span data-ttu-id="0a241-589">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-589">Packaging</span></span></td>
<td><span data-ttu-id="0a241-590">35</span><span class="sxs-lookup"><span data-stu-id="0a241-590">35</span></span></td>
<td><span data-ttu-id="0a241-591">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="0a241-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="0a241-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="0a241-592">2,852.60</span></span></td>
<td><span data-ttu-id="0a241-593">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-594">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="0a241-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-595">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-595">Cost object</span></span></th>
<th><span data-ttu-id="0a241-596">Nagyság</span><span class="sxs-lookup"><span data-stu-id="0a241-596">Magnitude</span></span></th>
<th><span data-ttu-id="0a241-597">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="0a241-597">Allocation factor</span></span></th>
<th><span data-ttu-id="0a241-598">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-598">Amount</span></span></th>
<th><span data-ttu-id="0a241-599">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-600">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-600">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-601">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-601">Product 1</span></span></td>
<td><span data-ttu-id="0a241-602">60</span><span class="sxs-lookup"><span data-stu-id="0a241-602">60</span></span></td>
<td><span data-ttu-id="0a241-603">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="0a241-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="0a241-604">535.31</span><span class="sxs-lookup"><span data-stu-id="0a241-604">535.31</span></span></td>
<td><span data-ttu-id="0a241-605">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-606">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-606">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-607">2. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-607">Product 2</span></span></td>
<td><span data-ttu-id="0a241-608">20</span><span class="sxs-lookup"><span data-stu-id="0a241-608">20</span></span></td>
<td><span data-ttu-id="0a241-609">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="0a241-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="0a241-610">178.44</span><span class="sxs-lookup"><span data-stu-id="0a241-610">178.44</span></span></td>
<td><span data-ttu-id="0a241-611">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-612">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-612">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-613">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-613">Product 1</span></span></td>
<td><span data-ttu-id="0a241-614">60</span><span class="sxs-lookup"><span data-stu-id="0a241-614">60</span></span></td>
<td><span data-ttu-id="0a241-615">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="0a241-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="0a241-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="0a241-616">4,487.12</span></span></td>
<td><span data-ttu-id="0a241-617">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-618">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-618">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-619">2. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-619">Product 2</span></span></td>
<td><span data-ttu-id="0a241-620">20</span><span class="sxs-lookup"><span data-stu-id="0a241-620">20</span></span></td>
<td><span data-ttu-id="0a241-621">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="0a241-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="0a241-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="0a241-622">1,495.71</span></span></td>
<td><span data-ttu-id="0a241-623">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="0a241-624">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="0a241-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-625">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-625">Cost object</span></span></th>
<th><span data-ttu-id="0a241-626">Nagyság</span><span class="sxs-lookup"><span data-stu-id="0a241-626">Magnitude</span></span></th>
<th><span data-ttu-id="0a241-627">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="0a241-627">Allocation factor</span></span></th>
<th><span data-ttu-id="0a241-628">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-628">Amount</span></span></th>
<th><span data-ttu-id="0a241-629">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-630">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-630">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-631">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-631">Product 1</span></span></td>
<td><span data-ttu-id="0a241-632">80</span><span class="sxs-lookup"><span data-stu-id="0a241-632">80</span></span></td>
<td><span data-ttu-id="0a241-633">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="0a241-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="0a241-634">241.05</span><span class="sxs-lookup"><span data-stu-id="0a241-634">241.05</span></span></td>
<td><span data-ttu-id="0a241-635">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-636">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-636">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-637">2. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-637">Product 2</span></span></td>
<td><span data-ttu-id="0a241-638">15.</span><span class="sxs-lookup"><span data-stu-id="0a241-638">15</span></span></td>
<td><span data-ttu-id="0a241-639">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="0a241-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="0a241-640">45.20</span><span class="sxs-lookup"><span data-stu-id="0a241-640">45.20</span></span></td>
<td><span data-ttu-id="0a241-641">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-642">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-642">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-643">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-643">Product 1</span></span></td>
<td><span data-ttu-id="0a241-644">80</span><span class="sxs-lookup"><span data-stu-id="0a241-644">80</span></span></td>
<td><span data-ttu-id="0a241-645">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="0a241-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="0a241-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="0a241-646">2,507.09</span></span></td>
<td><span data-ttu-id="0a241-647">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-648">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-648">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-649">2. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-649">Product 2</span></span></td>
<td><span data-ttu-id="0a241-650">15.</span><span class="sxs-lookup"><span data-stu-id="0a241-650">15</span></span></td>
<td><span data-ttu-id="0a241-651">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="0a241-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="0a241-652">470.08</span><span class="sxs-lookup"><span data-stu-id="0a241-652">470.08</span></span></td>
<td><span data-ttu-id="0a241-653">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="0a241-654">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="0a241-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0a241-655">Napló</span><span class="sxs-lookup"><span data-stu-id="0a241-655">Journal</span></span></th>
<th><span data-ttu-id="0a241-656">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="0a241-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="0a241-657">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="0a241-658">Verzió</span><span class="sxs-lookup"><span data-stu-id="0a241-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-659">00004</span><span class="sxs-lookup"><span data-stu-id="0a241-659">00004</span></span></td>
<td><span data-ttu-id="0a241-660">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="0a241-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="0a241-661">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="0a241-661">Fiscal</span></span></td>
<td><span data-ttu-id="0a241-662">2017</span><span class="sxs-lookup"><span data-stu-id="0a241-662">2017</span></span></td>
<td><span data-ttu-id="0a241-663">1. időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-663">Period 1</span></span></td>
<td><span data-ttu-id="0a241-664">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="0a241-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="0a241-665">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="0a241-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="0a241-666">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="0a241-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-667">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-668">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="0a241-668">Cost element</span></span></th>
<th><span data-ttu-id="0a241-669">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-669">Cost behavior</span></span></th>
<th><span data-ttu-id="0a241-670">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-671">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-672">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-672">CC001</span></span></td>
<td><span data-ttu-id="0a241-673">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-673">HR</span></span></td>
<td><span data-ttu-id="0a241-674">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-674">10001</span></span></td>
<td><span data-ttu-id="0a241-675">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-675">Electricity</span></span></td>
<td><span data-ttu-id="0a241-676">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-676">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-677">500.00</span><span class="sxs-lookup"><span data-stu-id="0a241-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-678">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-679">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-679">CC001</span></span></td>
<td><span data-ttu-id="0a241-680">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-680">HR</span></span></td>
<td><span data-ttu-id="0a241-681">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-681">10001</span></span></td>
<td><span data-ttu-id="0a241-682">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-682">Electricity</span></span></td>
<td><span data-ttu-id="0a241-683">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-683">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="0a241-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-685">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-686">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-686">CC002</span></span></td>
<td><span data-ttu-id="0a241-687">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-687">Finance</span></span></td>
<td><span data-ttu-id="0a241-688">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-688">10001</span></span></td>
<td><span data-ttu-id="0a241-689">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-689">Electricity</span></span></td>
<td><span data-ttu-id="0a241-690">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-690">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-691">675.00</span><span class="sxs-lookup"><span data-stu-id="0a241-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-692">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-693">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-693">CC002</span></span></td>
<td><span data-ttu-id="0a241-694">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-694">Finance</span></span></td>
<td><span data-ttu-id="0a241-695">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-695">10001</span></span></td>
<td><span data-ttu-id="0a241-696">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-696">Electricity</span></span></td>
<td><span data-ttu-id="0a241-697">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-697">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="0a241-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-699">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-700">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-700">CC003</span></span></td>
<td><span data-ttu-id="0a241-701">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-701">Assembly</span></span></td>
<td><span data-ttu-id="0a241-702">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-702">10001</span></span></td>
<td><span data-ttu-id="0a241-703">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-703">Electricity</span></span></td>
<td><span data-ttu-id="0a241-704">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-704">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-705">713.75</span><span class="sxs-lookup"><span data-stu-id="0a241-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-706">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-707">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-707">CC003</span></span></td>
<td><span data-ttu-id="0a241-708">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-708">Assembly</span></span></td>
<td><span data-ttu-id="0a241-709">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-709">10001</span></span></td>
<td><span data-ttu-id="0a241-710">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-710">Electricity</span></span></td>
<td><span data-ttu-id="0a241-711">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-711">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="0a241-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-713">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-714">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-714">CC003</span></span></td>
<td><span data-ttu-id="0a241-715">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-715">Packaging</span></span></td>
<td><span data-ttu-id="0a241-716">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-716">10001</span></span></td>
<td><span data-ttu-id="0a241-717">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-717">Electricity</span></span></td>
<td><span data-ttu-id="0a241-718">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-718">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-719">286.25</span><span class="sxs-lookup"><span data-stu-id="0a241-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-720">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-721">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-721">CC003</span></span></td>
<td><span data-ttu-id="0a241-722">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-722">Packaging</span></span></td>
<td><span data-ttu-id="0a241-723">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-723">10001</span></span></td>
<td><span data-ttu-id="0a241-724">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-724">Electricity</span></span></td>
<td><span data-ttu-id="0a241-725">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-725">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="0a241-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-727">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-728">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-728">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-729">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-729">Product 1</span></span></td>
<td><span data-ttu-id="0a241-730">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-730">10001</span></span></td>
<td><span data-ttu-id="0a241-731">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-731">Electricity</span></span></td>
<td><span data-ttu-id="0a241-732">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-732">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-733">776.36</span><span class="sxs-lookup"><span data-stu-id="0a241-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-734">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-735">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-735">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-736">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-736">Product 1</span></span></td>
<td><span data-ttu-id="0a241-737">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-737">10001</span></span></td>
<td><span data-ttu-id="0a241-738">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-738">Electricity</span></span></td>
<td><span data-ttu-id="0a241-739">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-739">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="0a241-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-741">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-742">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-742">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-743">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-743">Product 1</span></span></td>
<td><span data-ttu-id="0a241-744">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-744">10001</span></span></td>
<td><span data-ttu-id="0a241-745">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-745">Electricity</span></span></td>
<td><span data-ttu-id="0a241-746">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-746">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-747">223.64</span><span class="sxs-lookup"><span data-stu-id="0a241-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-748">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="0a241-749">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-749">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-750">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-750">Product 1</span></span></td>
<td><span data-ttu-id="0a241-751">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-751">10001</span></span></td>
<td><span data-ttu-id="0a241-752">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-752">Electricity</span></span></td>
<td><span data-ttu-id="0a241-753">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-753">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="0a241-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="0a241-755">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="0a241-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="0a241-756">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="0a241-757">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="0a241-757">Cost element</span></span></th>
<th><span data-ttu-id="0a241-758">Költség működése</span><span class="sxs-lookup"><span data-stu-id="0a241-758">Cost behavior</span></span></th>
<th><span data-ttu-id="0a241-759">Összeg</span><span class="sxs-lookup"><span data-stu-id="0a241-759">Amount</span></span></th>
<th><span data-ttu-id="0a241-760">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="0a241-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="0a241-761">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-761">CC001</span></span></td>
<td><span data-ttu-id="0a241-762">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-762">HR</span></span></td>
<td><span data-ttu-id="0a241-763">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-763">10001</span></span></td>
<td><span data-ttu-id="0a241-764">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-764">Electricity</span></span></td>
<td><span data-ttu-id="0a241-765">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-765">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="0a241-766">-500.00</span></span></td>
<td><span data-ttu-id="0a241-767">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-768">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-768">CC002</span></span></td>
<td><span data-ttu-id="0a241-769">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-769">Finance</span></span></td>
<td><span data-ttu-id="0a241-770">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-770">10001</span></span></td>
<td><span data-ttu-id="0a241-771">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-771">Electricity</span></span></td>
<td><span data-ttu-id="0a241-772">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-772">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-773">175.00</span><span class="sxs-lookup"><span data-stu-id="0a241-773">175.00</span></span></td>
<td><span data-ttu-id="0a241-774">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-775">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-775">CC003</span></span></td>
<td><span data-ttu-id="0a241-776">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-776">Assembly</span></span></td>
<td><span data-ttu-id="0a241-777">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-777">10001</span></span></td>
<td><span data-ttu-id="0a241-778">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-778">Electricity</span></span></td>
<td><span data-ttu-id="0a241-779">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-779">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-780">275.00</span><span class="sxs-lookup"><span data-stu-id="0a241-780">275.00</span></span></td>
<td><span data-ttu-id="0a241-781">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-782">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-782">CC004</span></span></td>
<td><span data-ttu-id="0a241-783">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-783">Packaging</span></span></td>
<td><span data-ttu-id="0a241-784">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-784">10001</span></span></td>
<td><span data-ttu-id="0a241-785">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-785">Electricity</span></span></td>
<td><span data-ttu-id="0a241-786">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-786">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-787">50,00</span><span class="sxs-lookup"><span data-stu-id="0a241-787">50,00</span></span></td>
<td><span data-ttu-id="0a241-788">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-789">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-789">CC001</span></span></td>
<td><span data-ttu-id="0a241-790">HR</span><span class="sxs-lookup"><span data-stu-id="0a241-790">HR</span></span></td>
<td><span data-ttu-id="0a241-791">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-791">10001</span></span></td>
<td><span data-ttu-id="0a241-792">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-792">Electricity</span></span></td>
<td><span data-ttu-id="0a241-793">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-793">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-794">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="0a241-794">-1,245.71</span></span></td>
<td><span data-ttu-id="0a241-795">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-796">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-796">CC002</span></span></td>
<td><span data-ttu-id="0a241-797">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-797">Finance</span></span></td>
<td><span data-ttu-id="0a241-798">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-798">10001</span></span></td>
<td><span data-ttu-id="0a241-799">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-799">Electricity</span></span></td>
<td><span data-ttu-id="0a241-800">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-800">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-801">436.00</span><span class="sxs-lookup"><span data-stu-id="0a241-801">436.00</span></span></td>
<td><span data-ttu-id="0a241-802">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-803">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-803">CC003</span></span></td>
<td><span data-ttu-id="0a241-804">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-804">Assembly</span></span></td>
<td><span data-ttu-id="0a241-805">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-805">10001</span></span></td>
<td><span data-ttu-id="0a241-806">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-806">Electricity</span></span></td>
<td><span data-ttu-id="0a241-807">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-807">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-808">685.14</span><span class="sxs-lookup"><span data-stu-id="0a241-808">685.14</span></span></td>
<td><span data-ttu-id="0a241-809">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-810">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-810">CC004</span></span></td>
<td><span data-ttu-id="0a241-811">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-811">Packaging</span></span></td>
<td><span data-ttu-id="0a241-812">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-812">10001</span></span></td>
<td><span data-ttu-id="0a241-813">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-813">Electricity</span></span></td>
<td><span data-ttu-id="0a241-814">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-814">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-815">124.57</span><span class="sxs-lookup"><span data-stu-id="0a241-815">124.57</span></span></td>
<td><span data-ttu-id="0a241-816">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-817">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-817">CC002</span></span></td>
<td><span data-ttu-id="0a241-818">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-818">Finance</span></span></td>
<td><span data-ttu-id="0a241-819">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-819">10001</span></span></td>
<td><span data-ttu-id="0a241-820">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-820">Electricity</span></span></td>
<td><span data-ttu-id="0a241-821">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-821">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-822">-675.00</span><span class="sxs-lookup"><span data-stu-id="0a241-822">-675.00</span></span></td>
<td><span data-ttu-id="0a241-823">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-824">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-824">CC003</span></span></td>
<td><span data-ttu-id="0a241-825">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-825">Assembly</span></span></td>
<td><span data-ttu-id="0a241-826">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-826">10001</span></span></td>
<td><span data-ttu-id="0a241-827">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-827">Electricity</span></span></td>
<td><span data-ttu-id="0a241-828">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-828">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-829">438.75</span><span class="sxs-lookup"><span data-stu-id="0a241-829">438.75</span></span></td>
<td><span data-ttu-id="0a241-830">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-831">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-831">CC004</span></span></td>
<td><span data-ttu-id="0a241-832">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-832">Packaging</span></span></td>
<td><span data-ttu-id="0a241-833">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-833">10001</span></span></td>
<td><span data-ttu-id="0a241-834">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-834">Electricity</span></span></td>
<td><span data-ttu-id="0a241-835">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-835">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-836">236.25</span><span class="sxs-lookup"><span data-stu-id="0a241-836">236.25</span></span></td>
<td><span data-ttu-id="0a241-837">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-838">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-838">CC002</span></span></td>
<td><span data-ttu-id="0a241-839">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0a241-839">Finance</span></span></td>
<td><span data-ttu-id="0a241-840">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-840">10001</span></span></td>
<td><span data-ttu-id="0a241-841">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-841">Electricity</span></span></td>
<td><span data-ttu-id="0a241-842">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-842">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-843">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="0a241-843">-8,150.29</span></span></td>
<td><span data-ttu-id="0a241-844">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-845">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-845">CC003</span></span></td>
<td><span data-ttu-id="0a241-846">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-846">Assembly</span></span></td>
<td><span data-ttu-id="0a241-847">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-847">10001</span></span></td>
<td><span data-ttu-id="0a241-848">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-848">Electricity</span></span></td>
<td><span data-ttu-id="0a241-849">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-849">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="0a241-850">5,297.69</span></span></td>
<td><span data-ttu-id="0a241-851">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-852">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-852">CC004</span></span></td>
<td><span data-ttu-id="0a241-853">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0a241-853">Packaging</span></span></td>
<td><span data-ttu-id="0a241-854">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-854">10001</span></span></td>
<td><span data-ttu-id="0a241-855">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-855">Electricity</span></span></td>
<td><span data-ttu-id="0a241-856">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-856">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="0a241-857">2,852.60</span></span></td>
<td><span data-ttu-id="0a241-858">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-859">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-859">CC003</span></span></td>
<td><span data-ttu-id="0a241-860">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-860">Assembly</span></span></td>
<td><span data-ttu-id="0a241-861">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-861">10001</span></span></td>
<td><span data-ttu-id="0a241-862">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-862">Electricity</span></span></td>
<td><span data-ttu-id="0a241-863">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-863">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-864">-713.75</span><span class="sxs-lookup"><span data-stu-id="0a241-864">-713.75</span></span></td>
<td><span data-ttu-id="0a241-865">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-866">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-866">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-867">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-867">Product 1</span></span></td>
<td><span data-ttu-id="0a241-868">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-868">10001</span></span></td>
<td><span data-ttu-id="0a241-869">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-869">Electricity</span></span></td>
<td><span data-ttu-id="0a241-870">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-870">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-871">535.31</span><span class="sxs-lookup"><span data-stu-id="0a241-871">535.31</span></span></td>
<td><span data-ttu-id="0a241-872">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-873">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-873">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-874">2. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-874">Product 2</span></span></td>
<td><span data-ttu-id="0a241-875">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-875">10001</span></span></td>
<td><span data-ttu-id="0a241-876">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-876">Electricity</span></span></td>
<td><span data-ttu-id="0a241-877">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-877">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-878">178.44</span><span class="sxs-lookup"><span data-stu-id="0a241-878">178.44</span></span></td>
<td><span data-ttu-id="0a241-879">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-880">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-880">CC003</span></span></td>
<td><span data-ttu-id="0a241-881">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-881">Assembly</span></span></td>
<td><span data-ttu-id="0a241-882">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-882">10001</span></span></td>
<td><span data-ttu-id="0a241-883">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-883">Electricity</span></span></td>
<td><span data-ttu-id="0a241-884">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-884">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-885">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="0a241-885">-5,982.83</span></span></td>
<td><span data-ttu-id="0a241-886">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-887">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-887">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-888">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-888">Product 1</span></span></td>
<td><span data-ttu-id="0a241-889">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-889">10001</span></span></td>
<td><span data-ttu-id="0a241-890">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-890">Electricity</span></span></td>
<td><span data-ttu-id="0a241-891">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-891">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="0a241-892">4,487.12</span></span></td>
<td><span data-ttu-id="0a241-893">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-894">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-894">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-895">2. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-895">Product 2</span></span></td>
<td><span data-ttu-id="0a241-896">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-896">10001</span></span></td>
<td><span data-ttu-id="0a241-897">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-897">Electricity</span></span></td>
<td><span data-ttu-id="0a241-898">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-898">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="0a241-899">1,495.71</span></span></td>
<td><span data-ttu-id="0a241-900">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-901">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-901">CC003</span></span></td>
<td><span data-ttu-id="0a241-902">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-902">Assembly</span></span></td>
<td><span data-ttu-id="0a241-903">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-903">10001</span></span></td>
<td><span data-ttu-id="0a241-904">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-904">Electricity</span></span></td>
<td><span data-ttu-id="0a241-905">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-905">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-906">-286.25</span><span class="sxs-lookup"><span data-stu-id="0a241-906">-286.25</span></span></td>
<td><span data-ttu-id="0a241-907">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-908">Term 1</span><span class="sxs-lookup"><span data-stu-id="0a241-908">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-909">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-909">Product 1</span></span></td>
<td><span data-ttu-id="0a241-910">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-910">10001</span></span></td>
<td><span data-ttu-id="0a241-911">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-911">Electricity</span></span></td>
<td><span data-ttu-id="0a241-912">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-912">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-913">241.05</span><span class="sxs-lookup"><span data-stu-id="0a241-913">241.05</span></span></td>
<td><span data-ttu-id="0a241-914">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-915">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-915">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-916">2. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-916">Product 2</span></span></td>
<td><span data-ttu-id="0a241-917">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-917">10001</span></span></td>
<td><span data-ttu-id="0a241-918">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-918">Electricity</span></span></td>
<td><span data-ttu-id="0a241-919">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-919">Fixed cost</span></span></td>
<td><span data-ttu-id="0a241-920">45.20</span><span class="sxs-lookup"><span data-stu-id="0a241-920">45.20</span></span></td>
<td><span data-ttu-id="0a241-921">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-922">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-922">CC003</span></span></td>
<td><span data-ttu-id="0a241-923">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0a241-923">Assembly</span></span></td>
<td><span data-ttu-id="0a241-924">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-924">10001</span></span></td>
<td><span data-ttu-id="0a241-925">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-925">Electricity</span></span></td>
<td><span data-ttu-id="0a241-926">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-926">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-927">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="0a241-927">-2,977.17</span></span></td>
<td><span data-ttu-id="0a241-928">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-929">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-929">Prod 1</span></span></td>
<td><span data-ttu-id="0a241-930">1. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-930">Product 1</span></span></td>
<td><span data-ttu-id="0a241-931">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-931">10001</span></span></td>
<td><span data-ttu-id="0a241-932">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-932">Electricity</span></span></td>
<td><span data-ttu-id="0a241-933">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-933">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="0a241-934">2,507.09</span></span></td>
<td><span data-ttu-id="0a241-935">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="0a241-936">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-936">Prod 2</span></span></td>
<td><span data-ttu-id="0a241-937">2. termék</span><span class="sxs-lookup"><span data-stu-id="0a241-937">Product 2</span></span></td>
<td><span data-ttu-id="0a241-938">10001</span><span class="sxs-lookup"><span data-stu-id="0a241-938">10001</span></span></td>
<td><span data-ttu-id="0a241-939">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-939">Electricity</span></span></td>
<td><span data-ttu-id="0a241-940">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-940">Variable cost</span></span></td>
<td><span data-ttu-id="0a241-941">470.08</span><span class="sxs-lookup"><span data-stu-id="0a241-941">470.08</span></span></td>
<td><span data-ttu-id="0a241-942">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="0a241-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="0a241-943">Következtetés</span><span class="sxs-lookup"><span data-stu-id="0a241-943">Conclusion</span></span>
<span data-ttu-id="0a241-944">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="0a241-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="0a241-945">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="0a241-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="0a241-946">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="0a241-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="0a241-947">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="0a241-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="0a241-948">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="0a241-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="0a241-949">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="0a241-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="0a241-950">Összesen</span><span class="sxs-lookup"><span data-stu-id="0a241-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="0a241-951">CC099</span><span class="sxs-lookup"><span data-stu-id="0a241-951">CC099</span></span></th>
<th><span data-ttu-id="0a241-952">CC001</span><span class="sxs-lookup"><span data-stu-id="0a241-952">CC001</span></span></th>
<th><span data-ttu-id="0a241-953">CC002</span><span class="sxs-lookup"><span data-stu-id="0a241-953">CC002</span></span></th>
<th><span data-ttu-id="0a241-954">CC003</span><span class="sxs-lookup"><span data-stu-id="0a241-954">CC003</span></span></th>
<th><span data-ttu-id="0a241-955">CC004</span><span class="sxs-lookup"><span data-stu-id="0a241-955">CC004</span></span></th>
<th><span data-ttu-id="0a241-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="0a241-956">Proj 1</span></span></th>
<th><span data-ttu-id="0a241-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="0a241-957">Proj 2</span></span></th>
<th><span data-ttu-id="0a241-958">Term. 1</span><span class="sxs-lookup"><span data-stu-id="0a241-958">Prod 1</span></span></th>
<th><span data-ttu-id="0a241-959">Term. 2</span><span class="sxs-lookup"><span data-stu-id="0a241-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="0a241-960">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="0a241-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="0a241-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="0a241-970">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="0a241-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-971">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="0a241-972">Fix költség</span><span class="sxs-lookup"><span data-stu-id="0a241-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-973">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-974">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-975">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-976">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-977">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="0a241-978">776.36</span><span class="sxs-lookup"><span data-stu-id="0a241-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-979">223.64</span><span class="sxs-lookup"><span data-stu-id="0a241-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="0a241-981">Változó költség</span><span class="sxs-lookup"><span data-stu-id="0a241-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-982">000</span><span class="sxs-lookup"><span data-stu-id="0a241-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-983">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-984">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-985">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-986">0,00</span><span class="sxs-lookup"><span data-stu-id="0a241-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-987">30.00</span><span class="sxs-lookup"><span data-stu-id="0a241-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-988">1000</span><span class="sxs-lookup"><span data-stu-id="0a241-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="0a241-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="0a241-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="0a241-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="0a241-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="0a241-992">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="0a241-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="0a241-993">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="0a241-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="0a241-994">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="0a241-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="0a241-995">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="0a241-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="0a241-996">Részletesebb tájékoztatás: [Költségösszesítési irányelv](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="0a241-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



