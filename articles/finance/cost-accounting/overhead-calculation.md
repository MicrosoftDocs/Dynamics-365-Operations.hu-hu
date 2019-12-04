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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 954e0669c3d24bcc20fe667c22b7dcc367aba1e7
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770804"
---
# <a name="overhead-calculation"></a><span data-ttu-id="334f0-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="334f0-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="334f0-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="334f0-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="334f0-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="334f0-105">Term definition</span></span>
---------------

<span data-ttu-id="334f0-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="334f0-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="334f0-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="334f0-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="334f0-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="334f0-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="334f0-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="334f0-109">Rent</span></span>
-   <span data-ttu-id="334f0-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-110">Electricity</span></span>
-   <span data-ttu-id="334f0-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="334f0-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="334f0-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="334f0-112">Overhead calculation overview</span></span>
<span data-ttu-id="334f0-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="334f0-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="334f0-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="334f0-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="334f0-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="334f0-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="334f0-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="334f0-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="334f0-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="334f0-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="334f0-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="334f0-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="334f0-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="334f0-119">Version type</span></span>
-   <span data-ttu-id="334f0-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="334f0-120">Date and time</span></span>
-   <span data-ttu-id="334f0-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="334f0-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="334f0-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="334f0-122">Fiscal year</span></span>
-   <span data-ttu-id="334f0-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-123">Fiscal period</span></span>

<span data-ttu-id="334f0-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="334f0-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="334f0-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="334f0-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="334f0-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="334f0-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="334f0-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="334f0-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="334f0-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="334f0-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="334f0-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="334f0-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="334f0-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="334f0-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="334f0-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="334f0-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="334f0-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="334f0-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="334f0-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="334f0-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="334f0-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="334f0-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="334f0-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="334f0-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="334f0-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="334f0-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="334f0-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="334f0-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="334f0-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="334f0-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="334f0-140">Main account</span></span></th>
<th><span data-ttu-id="334f0-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="334f0-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="334f0-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="334f0-143">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-143">CC099</span></span></td>
<td><span data-ttu-id="334f0-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-144">Default cost center</span></span></td>
<td><span data-ttu-id="334f0-145">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-145">10001</span></span></td>
<td><span data-ttu-id="334f0-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-146">Electricity</span></span></td>
<td><span data-ttu-id="334f0-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="334f0-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="334f0-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="334f0-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="334f0-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="334f0-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="334f0-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="334f0-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="334f0-151">Define the cost behavior rule</span></span>

<span data-ttu-id="334f0-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="334f0-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="334f0-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="334f0-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="334f0-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="334f0-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="334f0-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="334f0-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="334f0-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="334f0-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="334f0-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="334f0-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="334f0-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="334f0-159">Napló</span><span class="sxs-lookup"><span data-stu-id="334f0-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="334f0-160">Napló</span><span class="sxs-lookup"><span data-stu-id="334f0-160">Journal</span></span></th>
<th><span data-ttu-id="334f0-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="334f0-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="334f0-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="334f0-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="334f0-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-164">00001</span><span class="sxs-lookup"><span data-stu-id="334f0-164">00001</span></span></td>
<td><span data-ttu-id="334f0-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="334f0-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="334f0-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="334f0-166">Fiscal</span></span></td>
<td><span data-ttu-id="334f0-167">2017</span><span class="sxs-lookup"><span data-stu-id="334f0-167">2017</span></span></td>
<td><span data-ttu-id="334f0-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-168">Period 1</span></span></td>
<td><span data-ttu-id="334f0-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="334f0-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="334f0-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="334f0-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="334f0-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="334f0-173">Cost element</span></span></th>
<th><span data-ttu-id="334f0-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-174">Cost behavior</span></span></th>
<th><span data-ttu-id="334f0-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="334f0-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="334f0-177">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-177">CC099</span></span></td>
<td><span data-ttu-id="334f0-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-178">Default cost center</span></span></td>
<td><span data-ttu-id="334f0-179">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-179">10001</span></span></td>
<td><span data-ttu-id="334f0-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-180">Electricity</span></span></td>
<td><span data-ttu-id="334f0-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="334f0-181">Unclassified</span></span></td>
<td><span data-ttu-id="334f0-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="334f0-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="334f0-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="334f0-185">Cost element</span></span></th>
<th><span data-ttu-id="334f0-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-186">Cost behavior</span></span></th>
<th><span data-ttu-id="334f0-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-187">Amount</span></span></th>
<th><span data-ttu-id="334f0-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="334f0-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-189">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-189">CC099</span></span></td>
<td><span data-ttu-id="334f0-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-190">Default cost center</span></span></td>
<td><span data-ttu-id="334f0-191">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-191">10001</span></span></td>
<td><span data-ttu-id="334f0-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-192">Electricity</span></span></td>
<td><span data-ttu-id="334f0-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="334f0-193">Unclassified</span></span></td>
<td><span data-ttu-id="334f0-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-194">10,000.00</span></span></td>
<td><span data-ttu-id="334f0-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="334f0-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-196">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-196">CC099</span></span></td>
<td><span data-ttu-id="334f0-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-197">Default cost center</span></span></td>
<td><span data-ttu-id="334f0-198">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-198">10001</span></span></td>
<td><span data-ttu-id="334f0-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-199">Electricity</span></span></td>
<td><span data-ttu-id="334f0-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="334f0-200">Unclassified</span></span></td>
<td><span data-ttu-id="334f0-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-201">-10,000.00</span></span></td>
<td><span data-ttu-id="334f0-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-203">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-203">CC099</span></span></td>
<td><span data-ttu-id="334f0-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-204">Default cost center</span></span></td>
<td><span data-ttu-id="334f0-205">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-205">10001</span></span></td>
<td><span data-ttu-id="334f0-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-206">Electricity</span></span></td>
<td><span data-ttu-id="334f0-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-207">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="334f0-208">1,000.00</span></span></td>
<td><span data-ttu-id="334f0-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-210">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-210">CC099</span></span></td>
<td><span data-ttu-id="334f0-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-211">Default cost center</span></span></td>
<td><span data-ttu-id="334f0-212">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-212">10001</span></span></td>
<td><span data-ttu-id="334f0-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-213">Electricity</span></span></td>
<td><span data-ttu-id="334f0-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-214">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-215">9,000.00</span></span></td>
<td><span data-ttu-id="334f0-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-217">További információért lásd: [Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="334f0-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="334f0-218">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="334f0-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="334f0-219">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="334f0-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="334f0-220">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="334f0-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="334f0-221">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="334f0-221">Define the cost distribution rule</span></span>

<span data-ttu-id="334f0-222">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="334f0-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="334f0-223">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="334f0-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="334f0-224">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="334f0-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="334f0-225">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="334f0-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="334f0-226">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="334f0-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="334f0-227">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="334f0-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-228">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-228">Cost object</span></span></th>
<th><span data-ttu-id="334f0-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="334f0-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-230">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-230">CC001</span></span></td>
<td><span data-ttu-id="334f0-231">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-231">HR</span></span></td>
<td><span data-ttu-id="334f0-232">1000</span><span class="sxs-lookup"><span data-stu-id="334f0-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-233">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-233">CC002</span></span></td>
<td><span data-ttu-id="334f0-234">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-234">Finance</span></span></td>
<td><span data-ttu-id="334f0-235">6,000</span><span class="sxs-lookup"><span data-stu-id="334f0-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-236">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-236">CC003</span></span></td>
<td><span data-ttu-id="334f0-237">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-237">Assembly</span></span></td>
<td><span data-ttu-id="334f0-238">0</span><span class="sxs-lookup"><span data-stu-id="334f0-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-239">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="334f0-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-240">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-240">Cost object</span></span></th>
<th><span data-ttu-id="334f0-241">Nagyság</span><span class="sxs-lookup"><span data-stu-id="334f0-241">Magnitude</span></span></th>
<th><span data-ttu-id="334f0-242">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="334f0-242">Allocation factor</span></span></th>
<th><span data-ttu-id="334f0-243">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-244">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-244">CC001</span></span></td>
<td><span data-ttu-id="334f0-245">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-245">HR</span></span></td>
<td><span data-ttu-id="334f0-246">1000</span><span class="sxs-lookup"><span data-stu-id="334f0-246">1,000</span></span></td>
<td><span data-ttu-id="334f0-247">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="334f0-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="334f0-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-249">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-249">CC002</span></span></td>
<td><span data-ttu-id="334f0-250">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-250">Finance</span></span></td>
<td><span data-ttu-id="334f0-251">6,000</span><span class="sxs-lookup"><span data-stu-id="334f0-251">6,000</span></span></td>
<td><span data-ttu-id="334f0-252">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="334f0-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="334f0-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-254">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-254">CC003</span></span></td>
<td><span data-ttu-id="334f0-255">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-255">Assembly</span></span></td>
<td><span data-ttu-id="334f0-256">0</span><span class="sxs-lookup"><span data-stu-id="334f0-256">0</span></span></td>
<td><span data-ttu-id="334f0-257">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="334f0-258">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-259">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="334f0-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="334f0-260">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: (Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="334f0-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-261">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-261">Cost object</span></span></th>
<th><span data-ttu-id="334f0-262">Receptúra</span><span class="sxs-lookup"><span data-stu-id="334f0-262">Formula</span></span></th>
<th><span data-ttu-id="334f0-263">Nagyság</span><span class="sxs-lookup"><span data-stu-id="334f0-263">Magnitude</span></span></th>
<th><span data-ttu-id="334f0-264">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="334f0-264">Allocation factor</span></span></th>
<th><span data-ttu-id="334f0-265">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-266">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-266">CC001</span></span></td>
<td><span data-ttu-id="334f0-267">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-267">HR</span></span></td>
<td><span data-ttu-id="334f0-268">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="334f0-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="334f0-269">1</span><span class="sxs-lookup"><span data-stu-id="334f0-269">1</span></span></td>
<td><span data-ttu-id="334f0-270">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="334f0-271">500.00</span><span class="sxs-lookup"><span data-stu-id="334f0-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-272">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-272">CC002</span></span></td>
<td><span data-ttu-id="334f0-273">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-273">Finance</span></span></td>
<td><span data-ttu-id="334f0-274">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="334f0-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="334f0-275">1</span><span class="sxs-lookup"><span data-stu-id="334f0-275">1</span></span></td>
<td><span data-ttu-id="334f0-276">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="334f0-277">500.00</span><span class="sxs-lookup"><span data-stu-id="334f0-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-278">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-278">CC003</span></span></td>
<td><span data-ttu-id="334f0-279">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-279">Assembly</span></span></td>
<td><span data-ttu-id="334f0-280">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="334f0-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="334f0-281">0</span><span class="sxs-lookup"><span data-stu-id="334f0-281">0</span></span></td>
<td><span data-ttu-id="334f0-282">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="334f0-283">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="334f0-284">Napló</span><span class="sxs-lookup"><span data-stu-id="334f0-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="334f0-285">Napló</span><span class="sxs-lookup"><span data-stu-id="334f0-285">Journal</span></span></th>
<th><span data-ttu-id="334f0-286">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="334f0-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="334f0-287">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="334f0-288">Verzió</span><span class="sxs-lookup"><span data-stu-id="334f0-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-289">00002</span><span class="sxs-lookup"><span data-stu-id="334f0-289">00002</span></span></td>
<td><span data-ttu-id="334f0-290">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="334f0-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="334f0-291">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="334f0-291">Fiscal</span></span></td>
<td><span data-ttu-id="334f0-292">2017</span><span class="sxs-lookup"><span data-stu-id="334f0-292">2017</span></span></td>
<td><span data-ttu-id="334f0-293">1. időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-293">Period 1</span></span></td>
<td><span data-ttu-id="334f0-294">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="334f0-295">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="334f0-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="334f0-296">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="334f0-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-297">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-298">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="334f0-298">Cost element</span></span></th>
<th><span data-ttu-id="334f0-299">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-299">Cost behavior</span></span></th>
<th><span data-ttu-id="334f0-300">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-301">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-302">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-302">CC099</span></span></td>
<td><span data-ttu-id="334f0-303">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-303">Default cost center</span></span></td>
<td><span data-ttu-id="334f0-304">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-304">10001</span></span></td>
<td><span data-ttu-id="334f0-305">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-305">Electricity</span></span></td>
<td><span data-ttu-id="334f0-306">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-306">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="334f0-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-308">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-309">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-309">CC099</span></span></td>
<td><span data-ttu-id="334f0-310">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-310">Default cost center</span></span></td>
<td><span data-ttu-id="334f0-311">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-311">10001</span></span></td>
<td><span data-ttu-id="334f0-312">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-312">Electricity</span></span></td>
<td><span data-ttu-id="334f0-313">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-313">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="334f0-315">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="334f0-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-316">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-317">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="334f0-317">Cost element</span></span></th>
<th><span data-ttu-id="334f0-318">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-318">Cost behavior</span></span></th>
<th><span data-ttu-id="334f0-319">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-319">Amount</span></span></th>
<th><span data-ttu-id="334f0-320">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="334f0-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-321">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-321">CC099</span></span></td>
<td><span data-ttu-id="334f0-322">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-322">Default cost center</span></span></td>
<td><span data-ttu-id="334f0-323">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-323">10001</span></span></td>
<td><span data-ttu-id="334f0-324">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-324">Electricity</span></span></td>
<td><span data-ttu-id="334f0-325">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-325">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="334f0-326">-1,000.00</span></span></td>
<td><span data-ttu-id="334f0-327">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-328">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-328">CC001</span></span></td>
<td><span data-ttu-id="334f0-329">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-329">HR</span></span></td>
<td><span data-ttu-id="334f0-330">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-330">10001</span></span></td>
<td><span data-ttu-id="334f0-331">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-331">Electricity</span></span></td>
<td><span data-ttu-id="334f0-332">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-332">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-333">500.00</span><span class="sxs-lookup"><span data-stu-id="334f0-333">500.00</span></span></td>
<td><span data-ttu-id="334f0-334">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-335">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-335">CC002</span></span></td>
<td><span data-ttu-id="334f0-336">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-336">Finance</span></span></td>
<td><span data-ttu-id="334f0-337">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-337">10001</span></span></td>
<td><span data-ttu-id="334f0-338">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-338">Electricity</span></span></td>
<td><span data-ttu-id="334f0-339">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-339">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-340">500.00</span><span class="sxs-lookup"><span data-stu-id="334f0-340">500.00</span></span></td>
<td><span data-ttu-id="334f0-341">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-342">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-342">CC099</span></span></td>
<td><span data-ttu-id="334f0-343">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="334f0-343">Default cost center</span></span></td>
<td><span data-ttu-id="334f0-344">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-344">10001</span></span></td>
<td><span data-ttu-id="334f0-345">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-345">Electricity</span></span></td>
<td><span data-ttu-id="334f0-346">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-346">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-347">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="334f0-347">-9,000.00</span></span></td>
<td><span data-ttu-id="334f0-348">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-349">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-349">CC001</span></span></td>
<td><span data-ttu-id="334f0-350">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-350">HR</span></span></td>
<td><span data-ttu-id="334f0-351">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-351">10001</span></span></td>
<td><span data-ttu-id="334f0-352">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-352">Electricity</span></span></td>
<td><span data-ttu-id="334f0-353">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-353">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="334f0-354">1,285.71</span></span></td>
<td><span data-ttu-id="334f0-355">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-356">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-356">CC002</span></span></td>
<td><span data-ttu-id="334f0-357">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-357">Finance</span></span></td>
<td><span data-ttu-id="334f0-358">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-358">10001</span></span></td>
<td><span data-ttu-id="334f0-359">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-359">Electricity</span></span></td>
<td><span data-ttu-id="334f0-360">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-360">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="334f0-361">7,714.29</span></span></td>
<td><span data-ttu-id="334f0-362">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-363">További információért lásd: [Költségelosztási irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="334f0-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="334f0-364">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="334f0-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="334f0-365">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="334f0-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="334f0-366">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="334f0-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="334f0-367">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="334f0-367">Define the overhead rate</span></span>

<span data-ttu-id="334f0-368">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="334f0-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="334f0-369">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="334f0-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-370">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-370">Cost object</span></span></th>
<th><span data-ttu-id="334f0-371">óra</span><span class="sxs-lookup"><span data-stu-id="334f0-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="334f0-372">Proj 1</span></span></td>
<td><span data-ttu-id="334f0-373">1. projekt</span><span class="sxs-lookup"><span data-stu-id="334f0-373">Project 1</span></span></td>
<td><span data-ttu-id="334f0-374">3</span><span class="sxs-lookup"><span data-stu-id="334f0-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="334f0-375">Proj 2</span></span></td>
<td><span data-ttu-id="334f0-376">2. projekt</span><span class="sxs-lookup"><span data-stu-id="334f0-376">Project 2</span></span></td>
<td><span data-ttu-id="334f0-377">1</span><span class="sxs-lookup"><span data-stu-id="334f0-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-378">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="334f0-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-379">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-379">Cost object</span></span></th>
<th><span data-ttu-id="334f0-380">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="334f0-380">Cost element</span></span></th>
<th><span data-ttu-id="334f0-381">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-381">Cost behavior</span></span></th>
<th><span data-ttu-id="334f0-382">Egységek</span><span class="sxs-lookup"><span data-stu-id="334f0-382">Units</span></span></th>
<th><span data-ttu-id="334f0-383">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="334f0-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-384">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-384">CC001</span></span></td>
<td><span data-ttu-id="334f0-385">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-385">HR</span></span></td>
<td><span data-ttu-id="334f0-386">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-386">10001</span></span></td>
<td><span data-ttu-id="334f0-387">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-387">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-388">1</span><span class="sxs-lookup"><span data-stu-id="334f0-388">1</span></span></td>
<td><span data-ttu-id="334f0-389">10</span><span class="sxs-lookup"><span data-stu-id="334f0-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-390">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="334f0-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-391">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-391">Cost object</span></span></th>
<th><span data-ttu-id="334f0-392">Nagyság</span><span class="sxs-lookup"><span data-stu-id="334f0-392">Magnitude</span></span></th>
<th><span data-ttu-id="334f0-393">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="334f0-393">Cost element</span></span></th>
<th><span data-ttu-id="334f0-394">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="334f0-394">Allocation factor</span></span></th>
<th><span data-ttu-id="334f0-395">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="334f0-396">Proj 1</span></span></td>
<td><span data-ttu-id="334f0-397">1. projekt</span><span class="sxs-lookup"><span data-stu-id="334f0-397">Project 1</span></span></td>
<td><span data-ttu-id="334f0-398">3</span><span class="sxs-lookup"><span data-stu-id="334f0-398">3</span></span></td>
<td><span data-ttu-id="334f0-399">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-399">10001</span></span></td>
<td><span data-ttu-id="334f0-400">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="334f0-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="334f0-401">30.00</span><span class="sxs-lookup"><span data-stu-id="334f0-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="334f0-402">Proj 2</span></span></td>
<td><span data-ttu-id="334f0-403">2. projekt</span><span class="sxs-lookup"><span data-stu-id="334f0-403">Project 2</span></span></td>
<td><span data-ttu-id="334f0-404">1</span><span class="sxs-lookup"><span data-stu-id="334f0-404">1</span></span></td>
<td><span data-ttu-id="334f0-405">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-405">10001</span></span></td>
<td><span data-ttu-id="334f0-406">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="334f0-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="334f0-407">10.00</span><span class="sxs-lookup"><span data-stu-id="334f0-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="334f0-408">Napló</span><span class="sxs-lookup"><span data-stu-id="334f0-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="334f0-409">Napló</span><span class="sxs-lookup"><span data-stu-id="334f0-409">Journal</span></span></th>
<th><span data-ttu-id="334f0-410">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="334f0-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="334f0-411">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="334f0-412">Verzió</span><span class="sxs-lookup"><span data-stu-id="334f0-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-413">00003</span><span class="sxs-lookup"><span data-stu-id="334f0-413">00003</span></span></td>
<td><span data-ttu-id="334f0-414">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="334f0-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="334f0-415">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="334f0-415">Fiscal</span></span></td>
<td><span data-ttu-id="334f0-416">2017</span><span class="sxs-lookup"><span data-stu-id="334f0-416">2017</span></span></td>
<td><span data-ttu-id="334f0-417">1. időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-417">Period 1</span></span></td>
<td><span data-ttu-id="334f0-418">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="334f0-419">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="334f0-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="334f0-420">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="334f0-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-421">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-421">Cost object</span></span></th>
<th><span data-ttu-id="334f0-422">Nagyság</span><span class="sxs-lookup"><span data-stu-id="334f0-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-423">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="334f0-424">Proj 1</span></span></td>
<td><span data-ttu-id="334f0-425">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="334f0-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="334f0-426">3,00</span><span class="sxs-lookup"><span data-stu-id="334f0-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-427">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="334f0-428">Proj 2</span></span></td>
<td><span data-ttu-id="334f0-429">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="334f0-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="334f0-430">1.00</span><span class="sxs-lookup"><span data-stu-id="334f0-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="334f0-431">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="334f0-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-432">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-433">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="334f0-433">Cost element</span></span></th>
<th><span data-ttu-id="334f0-434">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-434">Cost behavior</span></span></th>
<th><span data-ttu-id="334f0-435">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-435">Amount</span></span></th>
<th><span data-ttu-id="334f0-436">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="334f0-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="334f0-437">CC0001</span></span></td>
<td><span data-ttu-id="334f0-438">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-438">HR</span></span></td>
<td><span data-ttu-id="334f0-439">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-439">10001</span></span></td>
<td><span data-ttu-id="334f0-440">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-440">Electricity</span></span></td>
<td><span data-ttu-id="334f0-441">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-441">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-442">-30.00</span><span class="sxs-lookup"><span data-stu-id="334f0-442">-30.00</span></span></td>
<td><span data-ttu-id="334f0-443">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="334f0-444">Proj 1</span></span></td>
<td><span data-ttu-id="334f0-445">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="334f0-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="334f0-446">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-446">10001</span></span></td>
<td><span data-ttu-id="334f0-447">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-447">Electricity</span></span></td>
<td><span data-ttu-id="334f0-448">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-448">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-449">30.00</span><span class="sxs-lookup"><span data-stu-id="334f0-449">30.00</span></span></td>
<td><span data-ttu-id="334f0-450">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-451">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-451">CC001</span></span></td>
<td><span data-ttu-id="334f0-452">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-452">HR</span></span></td>
<td><span data-ttu-id="334f0-453">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-453">10001</span></span></td>
<td><span data-ttu-id="334f0-454">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-454">Electricity</span></span></td>
<td><span data-ttu-id="334f0-455">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-455">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="334f0-456">-10.00</span></span></td>
<td><span data-ttu-id="334f0-457">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="334f0-458">Proj 2</span></span></td>
<td><span data-ttu-id="334f0-459">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="334f0-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="334f0-460">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-460">10001</span></span></td>
<td><span data-ttu-id="334f0-461">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-461">Electricity</span></span></td>
<td><span data-ttu-id="334f0-462">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-462">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-463">10,00</span><span class="sxs-lookup"><span data-stu-id="334f0-463">10.00</span></span></td>
<td><span data-ttu-id="334f0-464">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-465">További információ: [Járulékosköltség-számítás végrehajtása](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="334f0-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="334f0-466">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="334f0-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="334f0-467">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="334f0-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="334f0-468">A Finance a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="334f0-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="334f0-469">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="334f0-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="334f0-470">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="334f0-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="334f0-471">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="334f0-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="334f0-472">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="334f0-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="334f0-473">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="334f0-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="334f0-474">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="334f0-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="334f0-475">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="334f0-475">Define the cost allocation</span></span>

<span data-ttu-id="334f0-476">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="334f0-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="334f0-477">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="334f0-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="334f0-478">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="334f0-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-479">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-479">Cost object</span></span></th>
<th><span data-ttu-id="334f0-480">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="334f0-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-481">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-481">CC002</span></span></td>
<td><span data-ttu-id="334f0-482">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-482">Finance</span></span></td>
<td><span data-ttu-id="334f0-483">35</span><span class="sxs-lookup"><span data-stu-id="334f0-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-484">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-484">CC003</span></span></td>
<td><span data-ttu-id="334f0-485">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-485">Assembly</span></span></td>
<td><span data-ttu-id="334f0-486">55</span><span class="sxs-lookup"><span data-stu-id="334f0-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-487">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-487">CC004</span></span></td>
<td><span data-ttu-id="334f0-488">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-488">Packaging</span></span></td>
<td><span data-ttu-id="334f0-489">10</span><span class="sxs-lookup"><span data-stu-id="334f0-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-490">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="334f0-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="334f0-491">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="334f0-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-492">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-492">Cost object</span></span></th>
<th><span data-ttu-id="334f0-493">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="334f0-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-494">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-494">CC003</span></span></td>
<td><span data-ttu-id="334f0-495">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-495">Assembly</span></span></td>
<td><span data-ttu-id="334f0-496">65</span><span class="sxs-lookup"><span data-stu-id="334f0-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-497">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-497">CC004</span></span></td>
<td><span data-ttu-id="334f0-498">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-498">Packaging</span></span></td>
<td><span data-ttu-id="334f0-499">35</span><span class="sxs-lookup"><span data-stu-id="334f0-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-500">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="334f0-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="334f0-501">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="334f0-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-502">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-502">Cost object</span></span></th>
<th><span data-ttu-id="334f0-503">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="334f0-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-504">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-504">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-505">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-505">Product 1</span></span></td>
<td><span data-ttu-id="334f0-506">60</span><span class="sxs-lookup"><span data-stu-id="334f0-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-507">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-507">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-508">2. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-508">Product 2</span></span></td>
<td><span data-ttu-id="334f0-509">20</span><span class="sxs-lookup"><span data-stu-id="334f0-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-510">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="334f0-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="334f0-511">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="334f0-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-512">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-512">Cost object</span></span></th>
<th><span data-ttu-id="334f0-513">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="334f0-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-514">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-514">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-515">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-515">Product 1</span></span></td>
<td><span data-ttu-id="334f0-516">80</span><span class="sxs-lookup"><span data-stu-id="334f0-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-517">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-517">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-518">2. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-518">Product 2</span></span></td>
<td><span data-ttu-id="334f0-519">15</span><span class="sxs-lookup"><span data-stu-id="334f0-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="334f0-520">A statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="334f0-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="334f0-521">További információk: [Statisztikaimérték-szolgáltató sablon](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="334f0-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="334f0-522">Az alábbi táblázat azt az eredményt mutatja, amikor a HR szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="334f0-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-523">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-523">Cost object</span></span></th>
<th><span data-ttu-id="334f0-524">Nagyság</span><span class="sxs-lookup"><span data-stu-id="334f0-524">Magnitude</span></span></th>
<th><span data-ttu-id="334f0-525">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="334f0-525">Allocation factor</span></span></th>
<th><span data-ttu-id="334f0-526">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-526">Amount</span></span></th>
<th><span data-ttu-id="334f0-527">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-528">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-528">CC002</span></span></td>
<td><span data-ttu-id="334f0-529">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-529">Finance</span></span></td>
<td><span data-ttu-id="334f0-530">35</span><span class="sxs-lookup"><span data-stu-id="334f0-530">35</span></span></td>
<td><span data-ttu-id="334f0-531">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="334f0-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="334f0-532">175.00</span><span class="sxs-lookup"><span data-stu-id="334f0-532">175.00</span></span></td>
<td><span data-ttu-id="334f0-533">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-534">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-534">CC003</span></span></td>
<td><span data-ttu-id="334f0-535">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-535">Assembly</span></span></td>
<td><span data-ttu-id="334f0-536">55</span><span class="sxs-lookup"><span data-stu-id="334f0-536">55</span></span></td>
<td><span data-ttu-id="334f0-537">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="334f0-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="334f0-538">275.00</span><span class="sxs-lookup"><span data-stu-id="334f0-538">275.00</span></span></td>
<td><span data-ttu-id="334f0-539">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-540">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-540">CC004</span></span></td>
<td><span data-ttu-id="334f0-541">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-541">Packaging</span></span></td>
<td><span data-ttu-id="334f0-542">10</span><span class="sxs-lookup"><span data-stu-id="334f0-542">10</span></span></td>
<td><span data-ttu-id="334f0-543">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="334f0-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="334f0-544">50,00</span><span class="sxs-lookup"><span data-stu-id="334f0-544">50.00</span></span></td>
<td><span data-ttu-id="334f0-545">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-546">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-546">CC002</span></span></td>
<td><span data-ttu-id="334f0-547">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-547">Finance</span></span></td>
<td><span data-ttu-id="334f0-548">35</span><span class="sxs-lookup"><span data-stu-id="334f0-548">35</span></span></td>
<td><span data-ttu-id="334f0-549">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="334f0-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="334f0-550">436.00</span><span class="sxs-lookup"><span data-stu-id="334f0-550">436.00</span></span></td>
<td><span data-ttu-id="334f0-551">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-552">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-552">CC003</span></span></td>
<td><span data-ttu-id="334f0-553">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-553">Assembly</span></span></td>
<td><span data-ttu-id="334f0-554">55</span><span class="sxs-lookup"><span data-stu-id="334f0-554">55</span></span></td>
<td><span data-ttu-id="334f0-555">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="334f0-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="334f0-556">685.14</span><span class="sxs-lookup"><span data-stu-id="334f0-556">685.14</span></span></td>
<td><span data-ttu-id="334f0-557">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-558">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-558">CC004</span></span></td>
<td><span data-ttu-id="334f0-559">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-559">Packaging</span></span></td>
<td><span data-ttu-id="334f0-560">10</span><span class="sxs-lookup"><span data-stu-id="334f0-560">10</span></span></td>
<td><span data-ttu-id="334f0-561">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="334f0-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="334f0-562">124.57</span><span class="sxs-lookup"><span data-stu-id="334f0-562">124.57</span></span></td>
<td><span data-ttu-id="334f0-563">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-564">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="334f0-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-565">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-565">Cost object</span></span></th>
<th><span data-ttu-id="334f0-566">Nagyság</span><span class="sxs-lookup"><span data-stu-id="334f0-566">Magnitude</span></span></th>
<th><span data-ttu-id="334f0-567">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="334f0-567">Allocation factor</span></span></th>
<th><span data-ttu-id="334f0-568">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-568">Amount</span></span></th>
<th><span data-ttu-id="334f0-569">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-570">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-570">CC003</span></span></td>
<td><span data-ttu-id="334f0-571">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-571">Assembly</span></span></td>
<td><span data-ttu-id="334f0-572">65</span><span class="sxs-lookup"><span data-stu-id="334f0-572">65</span></span></td>
<td><span data-ttu-id="334f0-573">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="334f0-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="334f0-574">438.75</span><span class="sxs-lookup"><span data-stu-id="334f0-574">438.75</span></span></td>
<td><span data-ttu-id="334f0-575">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-576">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-576">CC004</span></span></td>
<td><span data-ttu-id="334f0-577">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-577">Packaging</span></span></td>
<td><span data-ttu-id="334f0-578">35</span><span class="sxs-lookup"><span data-stu-id="334f0-578">35</span></span></td>
<td><span data-ttu-id="334f0-579">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="334f0-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="334f0-580">236.25</span><span class="sxs-lookup"><span data-stu-id="334f0-580">236.25</span></span></td>
<td><span data-ttu-id="334f0-581">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-582">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-582">CC003</span></span></td>
<td><span data-ttu-id="334f0-583">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-583">Assembly</span></span></td>
<td><span data-ttu-id="334f0-584">65</span><span class="sxs-lookup"><span data-stu-id="334f0-584">65</span></span></td>
<td><span data-ttu-id="334f0-585">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="334f0-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="334f0-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="334f0-586">5,297.69</span></span></td>
<td><span data-ttu-id="334f0-587">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-588">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-588">CC004</span></span></td>
<td><span data-ttu-id="334f0-589">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-589">Packaging</span></span></td>
<td><span data-ttu-id="334f0-590">35</span><span class="sxs-lookup"><span data-stu-id="334f0-590">35</span></span></td>
<td><span data-ttu-id="334f0-591">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="334f0-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="334f0-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="334f0-592">2,852.60</span></span></td>
<td><span data-ttu-id="334f0-593">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-594">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="334f0-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-595">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-595">Cost object</span></span></th>
<th><span data-ttu-id="334f0-596">Nagyság</span><span class="sxs-lookup"><span data-stu-id="334f0-596">Magnitude</span></span></th>
<th><span data-ttu-id="334f0-597">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="334f0-597">Allocation factor</span></span></th>
<th><span data-ttu-id="334f0-598">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-598">Amount</span></span></th>
<th><span data-ttu-id="334f0-599">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-600">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-600">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-601">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-601">Product 1</span></span></td>
<td><span data-ttu-id="334f0-602">60</span><span class="sxs-lookup"><span data-stu-id="334f0-602">60</span></span></td>
<td><span data-ttu-id="334f0-603">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="334f0-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="334f0-604">535.31</span><span class="sxs-lookup"><span data-stu-id="334f0-604">535.31</span></span></td>
<td><span data-ttu-id="334f0-605">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-606">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-606">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-607">2. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-607">Product 2</span></span></td>
<td><span data-ttu-id="334f0-608">20</span><span class="sxs-lookup"><span data-stu-id="334f0-608">20</span></span></td>
<td><span data-ttu-id="334f0-609">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="334f0-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="334f0-610">178.44</span><span class="sxs-lookup"><span data-stu-id="334f0-610">178.44</span></span></td>
<td><span data-ttu-id="334f0-611">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-612">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-612">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-613">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-613">Product 1</span></span></td>
<td><span data-ttu-id="334f0-614">60</span><span class="sxs-lookup"><span data-stu-id="334f0-614">60</span></span></td>
<td><span data-ttu-id="334f0-615">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="334f0-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="334f0-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="334f0-616">4,487.12</span></span></td>
<td><span data-ttu-id="334f0-617">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-618">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-618">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-619">2. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-619">Product 2</span></span></td>
<td><span data-ttu-id="334f0-620">20</span><span class="sxs-lookup"><span data-stu-id="334f0-620">20</span></span></td>
<td><span data-ttu-id="334f0-621">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="334f0-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="334f0-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="334f0-622">1,495.71</span></span></td>
<td><span data-ttu-id="334f0-623">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="334f0-624">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="334f0-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-625">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-625">Cost object</span></span></th>
<th><span data-ttu-id="334f0-626">Nagyság</span><span class="sxs-lookup"><span data-stu-id="334f0-626">Magnitude</span></span></th>
<th><span data-ttu-id="334f0-627">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="334f0-627">Allocation factor</span></span></th>
<th><span data-ttu-id="334f0-628">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-628">Amount</span></span></th>
<th><span data-ttu-id="334f0-629">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-630">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-630">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-631">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-631">Product 1</span></span></td>
<td><span data-ttu-id="334f0-632">80</span><span class="sxs-lookup"><span data-stu-id="334f0-632">80</span></span></td>
<td><span data-ttu-id="334f0-633">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="334f0-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="334f0-634">241.05</span><span class="sxs-lookup"><span data-stu-id="334f0-634">241.05</span></span></td>
<td><span data-ttu-id="334f0-635">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-636">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-636">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-637">2. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-637">Product 2</span></span></td>
<td><span data-ttu-id="334f0-638">15.</span><span class="sxs-lookup"><span data-stu-id="334f0-638">15</span></span></td>
<td><span data-ttu-id="334f0-639">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="334f0-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="334f0-640">45.20</span><span class="sxs-lookup"><span data-stu-id="334f0-640">45.20</span></span></td>
<td><span data-ttu-id="334f0-641">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-642">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-642">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-643">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-643">Product 1</span></span></td>
<td><span data-ttu-id="334f0-644">80</span><span class="sxs-lookup"><span data-stu-id="334f0-644">80</span></span></td>
<td><span data-ttu-id="334f0-645">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="334f0-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="334f0-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="334f0-646">2,507.09</span></span></td>
<td><span data-ttu-id="334f0-647">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-648">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-648">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-649">2. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-649">Product 2</span></span></td>
<td><span data-ttu-id="334f0-650">15.</span><span class="sxs-lookup"><span data-stu-id="334f0-650">15</span></span></td>
<td><span data-ttu-id="334f0-651">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="334f0-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="334f0-652">470.08</span><span class="sxs-lookup"><span data-stu-id="334f0-652">470.08</span></span></td>
<td><span data-ttu-id="334f0-653">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="334f0-654">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="334f0-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="334f0-655">Napló</span><span class="sxs-lookup"><span data-stu-id="334f0-655">Journal</span></span></th>
<th><span data-ttu-id="334f0-656">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="334f0-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="334f0-657">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="334f0-658">Verzió</span><span class="sxs-lookup"><span data-stu-id="334f0-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-659">00004</span><span class="sxs-lookup"><span data-stu-id="334f0-659">00004</span></span></td>
<td><span data-ttu-id="334f0-660">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="334f0-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="334f0-661">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="334f0-661">Fiscal</span></span></td>
<td><span data-ttu-id="334f0-662">2017</span><span class="sxs-lookup"><span data-stu-id="334f0-662">2017</span></span></td>
<td><span data-ttu-id="334f0-663">1. időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-663">Period 1</span></span></td>
<td><span data-ttu-id="334f0-664">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="334f0-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="334f0-665">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="334f0-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="334f0-666">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="334f0-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-667">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-668">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="334f0-668">Cost element</span></span></th>
<th><span data-ttu-id="334f0-669">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-669">Cost behavior</span></span></th>
<th><span data-ttu-id="334f0-670">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-671">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-672">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-672">CC001</span></span></td>
<td><span data-ttu-id="334f0-673">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-673">HR</span></span></td>
<td><span data-ttu-id="334f0-674">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-674">10001</span></span></td>
<td><span data-ttu-id="334f0-675">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-675">Electricity</span></span></td>
<td><span data-ttu-id="334f0-676">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-676">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-677">500.00</span><span class="sxs-lookup"><span data-stu-id="334f0-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-678">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-679">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-679">CC001</span></span></td>
<td><span data-ttu-id="334f0-680">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-680">HR</span></span></td>
<td><span data-ttu-id="334f0-681">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-681">10001</span></span></td>
<td><span data-ttu-id="334f0-682">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-682">Electricity</span></span></td>
<td><span data-ttu-id="334f0-683">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-683">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="334f0-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-685">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-686">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-686">CC002</span></span></td>
<td><span data-ttu-id="334f0-687">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-687">Finance</span></span></td>
<td><span data-ttu-id="334f0-688">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-688">10001</span></span></td>
<td><span data-ttu-id="334f0-689">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-689">Electricity</span></span></td>
<td><span data-ttu-id="334f0-690">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-690">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-691">675.00</span><span class="sxs-lookup"><span data-stu-id="334f0-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-692">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-693">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-693">CC002</span></span></td>
<td><span data-ttu-id="334f0-694">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-694">Finance</span></span></td>
<td><span data-ttu-id="334f0-695">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-695">10001</span></span></td>
<td><span data-ttu-id="334f0-696">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-696">Electricity</span></span></td>
<td><span data-ttu-id="334f0-697">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-697">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="334f0-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-699">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-700">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-700">CC003</span></span></td>
<td><span data-ttu-id="334f0-701">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-701">Assembly</span></span></td>
<td><span data-ttu-id="334f0-702">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-702">10001</span></span></td>
<td><span data-ttu-id="334f0-703">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-703">Electricity</span></span></td>
<td><span data-ttu-id="334f0-704">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-704">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-705">713.75</span><span class="sxs-lookup"><span data-stu-id="334f0-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-706">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-707">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-707">CC003</span></span></td>
<td><span data-ttu-id="334f0-708">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-708">Assembly</span></span></td>
<td><span data-ttu-id="334f0-709">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-709">10001</span></span></td>
<td><span data-ttu-id="334f0-710">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-710">Electricity</span></span></td>
<td><span data-ttu-id="334f0-711">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-711">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="334f0-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-713">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-714">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-714">CC003</span></span></td>
<td><span data-ttu-id="334f0-715">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-715">Packaging</span></span></td>
<td><span data-ttu-id="334f0-716">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-716">10001</span></span></td>
<td><span data-ttu-id="334f0-717">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-717">Electricity</span></span></td>
<td><span data-ttu-id="334f0-718">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-718">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-719">286.25</span><span class="sxs-lookup"><span data-stu-id="334f0-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-720">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-721">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-721">CC003</span></span></td>
<td><span data-ttu-id="334f0-722">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-722">Packaging</span></span></td>
<td><span data-ttu-id="334f0-723">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-723">10001</span></span></td>
<td><span data-ttu-id="334f0-724">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-724">Electricity</span></span></td>
<td><span data-ttu-id="334f0-725">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-725">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="334f0-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-727">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-728">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-728">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-729">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-729">Product 1</span></span></td>
<td><span data-ttu-id="334f0-730">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-730">10001</span></span></td>
<td><span data-ttu-id="334f0-731">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-731">Electricity</span></span></td>
<td><span data-ttu-id="334f0-732">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-732">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-733">776.36</span><span class="sxs-lookup"><span data-stu-id="334f0-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-734">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-735">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-735">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-736">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-736">Product 1</span></span></td>
<td><span data-ttu-id="334f0-737">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-737">10001</span></span></td>
<td><span data-ttu-id="334f0-738">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-738">Electricity</span></span></td>
<td><span data-ttu-id="334f0-739">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-739">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="334f0-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-741">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-742">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-742">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-743">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-743">Product 1</span></span></td>
<td><span data-ttu-id="334f0-744">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-744">10001</span></span></td>
<td><span data-ttu-id="334f0-745">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-745">Electricity</span></span></td>
<td><span data-ttu-id="334f0-746">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-746">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-747">223.64</span><span class="sxs-lookup"><span data-stu-id="334f0-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-748">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="334f0-749">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-749">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-750">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-750">Product 1</span></span></td>
<td><span data-ttu-id="334f0-751">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-751">10001</span></span></td>
<td><span data-ttu-id="334f0-752">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-752">Electricity</span></span></td>
<td><span data-ttu-id="334f0-753">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-753">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="334f0-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="334f0-755">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="334f0-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="334f0-756">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="334f0-757">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="334f0-757">Cost element</span></span></th>
<th><span data-ttu-id="334f0-758">Költség működése</span><span class="sxs-lookup"><span data-stu-id="334f0-758">Cost behavior</span></span></th>
<th><span data-ttu-id="334f0-759">Összeg</span><span class="sxs-lookup"><span data-stu-id="334f0-759">Amount</span></span></th>
<th><span data-ttu-id="334f0-760">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="334f0-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="334f0-761">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-761">CC001</span></span></td>
<td><span data-ttu-id="334f0-762">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-762">HR</span></span></td>
<td><span data-ttu-id="334f0-763">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-763">10001</span></span></td>
<td><span data-ttu-id="334f0-764">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-764">Electricity</span></span></td>
<td><span data-ttu-id="334f0-765">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-765">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="334f0-766">-500.00</span></span></td>
<td><span data-ttu-id="334f0-767">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-768">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-768">CC002</span></span></td>
<td><span data-ttu-id="334f0-769">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-769">Finance</span></span></td>
<td><span data-ttu-id="334f0-770">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-770">10001</span></span></td>
<td><span data-ttu-id="334f0-771">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-771">Electricity</span></span></td>
<td><span data-ttu-id="334f0-772">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-772">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-773">175.00</span><span class="sxs-lookup"><span data-stu-id="334f0-773">175.00</span></span></td>
<td><span data-ttu-id="334f0-774">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-775">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-775">CC003</span></span></td>
<td><span data-ttu-id="334f0-776">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-776">Assembly</span></span></td>
<td><span data-ttu-id="334f0-777">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-777">10001</span></span></td>
<td><span data-ttu-id="334f0-778">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-778">Electricity</span></span></td>
<td><span data-ttu-id="334f0-779">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-779">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-780">275.00</span><span class="sxs-lookup"><span data-stu-id="334f0-780">275.00</span></span></td>
<td><span data-ttu-id="334f0-781">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-782">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-782">CC004</span></span></td>
<td><span data-ttu-id="334f0-783">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-783">Packaging</span></span></td>
<td><span data-ttu-id="334f0-784">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-784">10001</span></span></td>
<td><span data-ttu-id="334f0-785">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-785">Electricity</span></span></td>
<td><span data-ttu-id="334f0-786">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-786">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-787">50,00</span><span class="sxs-lookup"><span data-stu-id="334f0-787">50,00</span></span></td>
<td><span data-ttu-id="334f0-788">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-789">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-789">CC001</span></span></td>
<td><span data-ttu-id="334f0-790">HR</span><span class="sxs-lookup"><span data-stu-id="334f0-790">HR</span></span></td>
<td><span data-ttu-id="334f0-791">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-791">10001</span></span></td>
<td><span data-ttu-id="334f0-792">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-792">Electricity</span></span></td>
<td><span data-ttu-id="334f0-793">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-793">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-794">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="334f0-794">-1,245.71</span></span></td>
<td><span data-ttu-id="334f0-795">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-796">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-796">CC002</span></span></td>
<td><span data-ttu-id="334f0-797">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-797">Finance</span></span></td>
<td><span data-ttu-id="334f0-798">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-798">10001</span></span></td>
<td><span data-ttu-id="334f0-799">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-799">Electricity</span></span></td>
<td><span data-ttu-id="334f0-800">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-800">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-801">436.00</span><span class="sxs-lookup"><span data-stu-id="334f0-801">436.00</span></span></td>
<td><span data-ttu-id="334f0-802">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-803">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-803">CC003</span></span></td>
<td><span data-ttu-id="334f0-804">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-804">Assembly</span></span></td>
<td><span data-ttu-id="334f0-805">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-805">10001</span></span></td>
<td><span data-ttu-id="334f0-806">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-806">Electricity</span></span></td>
<td><span data-ttu-id="334f0-807">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-807">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-808">685.14</span><span class="sxs-lookup"><span data-stu-id="334f0-808">685.14</span></span></td>
<td><span data-ttu-id="334f0-809">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-810">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-810">CC004</span></span></td>
<td><span data-ttu-id="334f0-811">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-811">Packaging</span></span></td>
<td><span data-ttu-id="334f0-812">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-812">10001</span></span></td>
<td><span data-ttu-id="334f0-813">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-813">Electricity</span></span></td>
<td><span data-ttu-id="334f0-814">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-814">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-815">124.57</span><span class="sxs-lookup"><span data-stu-id="334f0-815">124.57</span></span></td>
<td><span data-ttu-id="334f0-816">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-817">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-817">CC002</span></span></td>
<td><span data-ttu-id="334f0-818">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-818">Finance</span></span></td>
<td><span data-ttu-id="334f0-819">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-819">10001</span></span></td>
<td><span data-ttu-id="334f0-820">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-820">Electricity</span></span></td>
<td><span data-ttu-id="334f0-821">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-821">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-822">-675.00</span><span class="sxs-lookup"><span data-stu-id="334f0-822">-675.00</span></span></td>
<td><span data-ttu-id="334f0-823">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-824">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-824">CC003</span></span></td>
<td><span data-ttu-id="334f0-825">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-825">Assembly</span></span></td>
<td><span data-ttu-id="334f0-826">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-826">10001</span></span></td>
<td><span data-ttu-id="334f0-827">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-827">Electricity</span></span></td>
<td><span data-ttu-id="334f0-828">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-828">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-829">438.75</span><span class="sxs-lookup"><span data-stu-id="334f0-829">438.75</span></span></td>
<td><span data-ttu-id="334f0-830">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-831">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-831">CC004</span></span></td>
<td><span data-ttu-id="334f0-832">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-832">Packaging</span></span></td>
<td><span data-ttu-id="334f0-833">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-833">10001</span></span></td>
<td><span data-ttu-id="334f0-834">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-834">Electricity</span></span></td>
<td><span data-ttu-id="334f0-835">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-835">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-836">236.25</span><span class="sxs-lookup"><span data-stu-id="334f0-836">236.25</span></span></td>
<td><span data-ttu-id="334f0-837">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-838">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-838">CC002</span></span></td>
<td><span data-ttu-id="334f0-839">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="334f0-839">Finance</span></span></td>
<td><span data-ttu-id="334f0-840">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-840">10001</span></span></td>
<td><span data-ttu-id="334f0-841">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-841">Electricity</span></span></td>
<td><span data-ttu-id="334f0-842">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-842">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-843">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="334f0-843">-8,150.29</span></span></td>
<td><span data-ttu-id="334f0-844">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-845">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-845">CC003</span></span></td>
<td><span data-ttu-id="334f0-846">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-846">Assembly</span></span></td>
<td><span data-ttu-id="334f0-847">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-847">10001</span></span></td>
<td><span data-ttu-id="334f0-848">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-848">Electricity</span></span></td>
<td><span data-ttu-id="334f0-849">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-849">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="334f0-850">5,297.69</span></span></td>
<td><span data-ttu-id="334f0-851">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-852">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-852">CC004</span></span></td>
<td><span data-ttu-id="334f0-853">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="334f0-853">Packaging</span></span></td>
<td><span data-ttu-id="334f0-854">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-854">10001</span></span></td>
<td><span data-ttu-id="334f0-855">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-855">Electricity</span></span></td>
<td><span data-ttu-id="334f0-856">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-856">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="334f0-857">2,852.60</span></span></td>
<td><span data-ttu-id="334f0-858">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-859">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-859">CC003</span></span></td>
<td><span data-ttu-id="334f0-860">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-860">Assembly</span></span></td>
<td><span data-ttu-id="334f0-861">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-861">10001</span></span></td>
<td><span data-ttu-id="334f0-862">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-862">Electricity</span></span></td>
<td><span data-ttu-id="334f0-863">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-863">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-864">-713.75</span><span class="sxs-lookup"><span data-stu-id="334f0-864">-713.75</span></span></td>
<td><span data-ttu-id="334f0-865">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-866">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-866">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-867">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-867">Product 1</span></span></td>
<td><span data-ttu-id="334f0-868">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-868">10001</span></span></td>
<td><span data-ttu-id="334f0-869">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-869">Electricity</span></span></td>
<td><span data-ttu-id="334f0-870">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-870">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-871">535.31</span><span class="sxs-lookup"><span data-stu-id="334f0-871">535.31</span></span></td>
<td><span data-ttu-id="334f0-872">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-873">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-873">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-874">2. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-874">Product 2</span></span></td>
<td><span data-ttu-id="334f0-875">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-875">10001</span></span></td>
<td><span data-ttu-id="334f0-876">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-876">Electricity</span></span></td>
<td><span data-ttu-id="334f0-877">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-877">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-878">178.44</span><span class="sxs-lookup"><span data-stu-id="334f0-878">178.44</span></span></td>
<td><span data-ttu-id="334f0-879">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-880">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-880">CC003</span></span></td>
<td><span data-ttu-id="334f0-881">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-881">Assembly</span></span></td>
<td><span data-ttu-id="334f0-882">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-882">10001</span></span></td>
<td><span data-ttu-id="334f0-883">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-883">Electricity</span></span></td>
<td><span data-ttu-id="334f0-884">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-884">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-885">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="334f0-885">-5,982.83</span></span></td>
<td><span data-ttu-id="334f0-886">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-887">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-887">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-888">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-888">Product 1</span></span></td>
<td><span data-ttu-id="334f0-889">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-889">10001</span></span></td>
<td><span data-ttu-id="334f0-890">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-890">Electricity</span></span></td>
<td><span data-ttu-id="334f0-891">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-891">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="334f0-892">4,487.12</span></span></td>
<td><span data-ttu-id="334f0-893">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-894">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-894">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-895">2. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-895">Product 2</span></span></td>
<td><span data-ttu-id="334f0-896">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-896">10001</span></span></td>
<td><span data-ttu-id="334f0-897">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-897">Electricity</span></span></td>
<td><span data-ttu-id="334f0-898">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-898">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="334f0-899">1,495.71</span></span></td>
<td><span data-ttu-id="334f0-900">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-901">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-901">CC003</span></span></td>
<td><span data-ttu-id="334f0-902">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-902">Assembly</span></span></td>
<td><span data-ttu-id="334f0-903">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-903">10001</span></span></td>
<td><span data-ttu-id="334f0-904">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-904">Electricity</span></span></td>
<td><span data-ttu-id="334f0-905">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-905">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-906">-286.25</span><span class="sxs-lookup"><span data-stu-id="334f0-906">-286.25</span></span></td>
<td><span data-ttu-id="334f0-907">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-908">Term 1</span><span class="sxs-lookup"><span data-stu-id="334f0-908">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-909">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-909">Product 1</span></span></td>
<td><span data-ttu-id="334f0-910">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-910">10001</span></span></td>
<td><span data-ttu-id="334f0-911">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-911">Electricity</span></span></td>
<td><span data-ttu-id="334f0-912">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-912">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-913">241.05</span><span class="sxs-lookup"><span data-stu-id="334f0-913">241.05</span></span></td>
<td><span data-ttu-id="334f0-914">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-915">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-915">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-916">2. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-916">Product 2</span></span></td>
<td><span data-ttu-id="334f0-917">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-917">10001</span></span></td>
<td><span data-ttu-id="334f0-918">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-918">Electricity</span></span></td>
<td><span data-ttu-id="334f0-919">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-919">Fixed cost</span></span></td>
<td><span data-ttu-id="334f0-920">45.20</span><span class="sxs-lookup"><span data-stu-id="334f0-920">45.20</span></span></td>
<td><span data-ttu-id="334f0-921">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-922">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-922">CC003</span></span></td>
<td><span data-ttu-id="334f0-923">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="334f0-923">Assembly</span></span></td>
<td><span data-ttu-id="334f0-924">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-924">10001</span></span></td>
<td><span data-ttu-id="334f0-925">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-925">Electricity</span></span></td>
<td><span data-ttu-id="334f0-926">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-926">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-927">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="334f0-927">-2,977.17</span></span></td>
<td><span data-ttu-id="334f0-928">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-929">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-929">Prod 1</span></span></td>
<td><span data-ttu-id="334f0-930">1. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-930">Product 1</span></span></td>
<td><span data-ttu-id="334f0-931">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-931">10001</span></span></td>
<td><span data-ttu-id="334f0-932">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-932">Electricity</span></span></td>
<td><span data-ttu-id="334f0-933">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-933">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="334f0-934">2,507.09</span></span></td>
<td><span data-ttu-id="334f0-935">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="334f0-936">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-936">Prod 2</span></span></td>
<td><span data-ttu-id="334f0-937">2. termék</span><span class="sxs-lookup"><span data-stu-id="334f0-937">Product 2</span></span></td>
<td><span data-ttu-id="334f0-938">10001</span><span class="sxs-lookup"><span data-stu-id="334f0-938">10001</span></span></td>
<td><span data-ttu-id="334f0-939">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-939">Electricity</span></span></td>
<td><span data-ttu-id="334f0-940">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-940">Variable cost</span></span></td>
<td><span data-ttu-id="334f0-941">470.08</span><span class="sxs-lookup"><span data-stu-id="334f0-941">470.08</span></span></td>
<td><span data-ttu-id="334f0-942">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="334f0-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="334f0-943">Következtetés</span><span class="sxs-lookup"><span data-stu-id="334f0-943">Conclusion</span></span>
<span data-ttu-id="334f0-944">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="334f0-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="334f0-945">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="334f0-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="334f0-946">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="334f0-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="334f0-947">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="334f0-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="334f0-948">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="334f0-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="334f0-949">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="334f0-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="334f0-950">Összesen</span><span class="sxs-lookup"><span data-stu-id="334f0-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="334f0-951">CC099</span><span class="sxs-lookup"><span data-stu-id="334f0-951">CC099</span></span></th>
<th><span data-ttu-id="334f0-952">CC001</span><span class="sxs-lookup"><span data-stu-id="334f0-952">CC001</span></span></th>
<th><span data-ttu-id="334f0-953">CC002</span><span class="sxs-lookup"><span data-stu-id="334f0-953">CC002</span></span></th>
<th><span data-ttu-id="334f0-954">CC003</span><span class="sxs-lookup"><span data-stu-id="334f0-954">CC003</span></span></th>
<th><span data-ttu-id="334f0-955">CC004</span><span class="sxs-lookup"><span data-stu-id="334f0-955">CC004</span></span></th>
<th><span data-ttu-id="334f0-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="334f0-956">Proj 1</span></span></th>
<th><span data-ttu-id="334f0-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="334f0-957">Proj 2</span></span></th>
<th><span data-ttu-id="334f0-958">Term. 1</span><span class="sxs-lookup"><span data-stu-id="334f0-958">Prod 1</span></span></th>
<th><span data-ttu-id="334f0-959">Term. 2</span><span class="sxs-lookup"><span data-stu-id="334f0-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="334f0-960">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="334f0-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="334f0-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="334f0-970">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="334f0-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-971">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="334f0-972">Fix költség</span><span class="sxs-lookup"><span data-stu-id="334f0-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-973">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-974">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-975">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-976">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-977">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="334f0-978">776.36</span><span class="sxs-lookup"><span data-stu-id="334f0-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-979">223.64</span><span class="sxs-lookup"><span data-stu-id="334f0-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="334f0-981">Változó költség</span><span class="sxs-lookup"><span data-stu-id="334f0-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-982">000</span><span class="sxs-lookup"><span data-stu-id="334f0-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-983">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-984">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-985">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-986">0,00</span><span class="sxs-lookup"><span data-stu-id="334f0-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-987">30.00</span><span class="sxs-lookup"><span data-stu-id="334f0-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-988">1000</span><span class="sxs-lookup"><span data-stu-id="334f0-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="334f0-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="334f0-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="334f0-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="334f0-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="334f0-992">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="334f0-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="334f0-993">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="334f0-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="334f0-994">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="334f0-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="334f0-995">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="334f0-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="334f0-996">A további tudnivalókat lásd: [Költségösszesítéssel kapcsolatos irányelv és járulékos költség számítása](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="334f0-996">For more information, see [Cost rollup policy and overhead calculation](cost-rollup.md).</span></span>



