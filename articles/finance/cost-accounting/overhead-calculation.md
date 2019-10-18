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
ms.openlocfilehash: 6c045f82f3288dba193721dd80c90e68750af9a7
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178110"
---
# <a name="overhead-calculation"></a><span data-ttu-id="82ea2-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="82ea2-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82ea2-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="82ea2-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="82ea2-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="82ea2-105">Term definition</span></span>
---------------

<span data-ttu-id="82ea2-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="82ea2-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="82ea2-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="82ea2-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="82ea2-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="82ea2-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="82ea2-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="82ea2-109">Rent</span></span>
-   <span data-ttu-id="82ea2-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-110">Electricity</span></span>
-   <span data-ttu-id="82ea2-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="82ea2-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="82ea2-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="82ea2-112">Overhead calculation overview</span></span>
<span data-ttu-id="82ea2-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="82ea2-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="82ea2-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="82ea2-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="82ea2-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="82ea2-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="82ea2-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="82ea2-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="82ea2-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="82ea2-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="82ea2-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="82ea2-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="82ea2-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="82ea2-119">Version type</span></span>
-   <span data-ttu-id="82ea2-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="82ea2-120">Date and time</span></span>
-   <span data-ttu-id="82ea2-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="82ea2-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="82ea2-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="82ea2-122">Fiscal year</span></span>
-   <span data-ttu-id="82ea2-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-123">Fiscal period</span></span>

<span data-ttu-id="82ea2-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="82ea2-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="82ea2-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="82ea2-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="82ea2-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="82ea2-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="82ea2-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="82ea2-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="82ea2-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="82ea2-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="82ea2-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="82ea2-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="82ea2-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="82ea2-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="82ea2-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="82ea2-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="82ea2-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="82ea2-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="82ea2-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="82ea2-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="82ea2-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="82ea2-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="82ea2-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="82ea2-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="82ea2-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="82ea2-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="82ea2-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="82ea2-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="82ea2-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="82ea2-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="82ea2-140">Main account</span></span></th>
<th><span data-ttu-id="82ea2-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="82ea2-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="82ea2-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="82ea2-143">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-143">CC099</span></span></td>
<td><span data-ttu-id="82ea2-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-144">Default cost center</span></span></td>
<td><span data-ttu-id="82ea2-145">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-145">10001</span></span></td>
<td><span data-ttu-id="82ea2-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-146">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="82ea2-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="82ea2-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="82ea2-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="82ea2-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="82ea2-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="82ea2-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="82ea2-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="82ea2-151">Define the cost behavior rule</span></span>

<span data-ttu-id="82ea2-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="82ea2-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="82ea2-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="82ea2-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="82ea2-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="82ea2-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="82ea2-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="82ea2-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="82ea2-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="82ea2-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="82ea2-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="82ea2-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="82ea2-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="82ea2-159">Napló</span><span class="sxs-lookup"><span data-stu-id="82ea2-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="82ea2-160">Napló</span><span class="sxs-lookup"><span data-stu-id="82ea2-160">Journal</span></span></th>
<th><span data-ttu-id="82ea2-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="82ea2-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="82ea2-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="82ea2-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="82ea2-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-164">00001</span><span class="sxs-lookup"><span data-stu-id="82ea2-164">00001</span></span></td>
<td><span data-ttu-id="82ea2-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="82ea2-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="82ea2-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="82ea2-166">Fiscal</span></span></td>
<td><span data-ttu-id="82ea2-167">2017</span><span class="sxs-lookup"><span data-stu-id="82ea2-167">2017</span></span></td>
<td><span data-ttu-id="82ea2-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-168">Period 1</span></span></td>
<td><span data-ttu-id="82ea2-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="82ea2-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="82ea2-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="82ea2-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="82ea2-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="82ea2-173">Cost element</span></span></th>
<th><span data-ttu-id="82ea2-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-174">Cost behavior</span></span></th>
<th><span data-ttu-id="82ea2-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="82ea2-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="82ea2-177">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-177">CC099</span></span></td>
<td><span data-ttu-id="82ea2-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-178">Default cost center</span></span></td>
<td><span data-ttu-id="82ea2-179">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-179">10001</span></span></td>
<td><span data-ttu-id="82ea2-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-180">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="82ea2-181">Unclassified</span></span></td>
<td><span data-ttu-id="82ea2-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="82ea2-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="82ea2-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="82ea2-185">Cost element</span></span></th>
<th><span data-ttu-id="82ea2-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-186">Cost behavior</span></span></th>
<th><span data-ttu-id="82ea2-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-187">Amount</span></span></th>
<th><span data-ttu-id="82ea2-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="82ea2-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-189">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-189">CC099</span></span></td>
<td><span data-ttu-id="82ea2-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-190">Default cost center</span></span></td>
<td><span data-ttu-id="82ea2-191">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-191">10001</span></span></td>
<td><span data-ttu-id="82ea2-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-192">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="82ea2-193">Unclassified</span></span></td>
<td><span data-ttu-id="82ea2-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-194">10,000.00</span></span></td>
<td><span data-ttu-id="82ea2-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="82ea2-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-196">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-196">CC099</span></span></td>
<td><span data-ttu-id="82ea2-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-197">Default cost center</span></span></td>
<td><span data-ttu-id="82ea2-198">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-198">10001</span></span></td>
<td><span data-ttu-id="82ea2-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-199">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="82ea2-200">Unclassified</span></span></td>
<td><span data-ttu-id="82ea2-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-201">-10,000.00</span></span></td>
<td><span data-ttu-id="82ea2-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-203">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-203">CC099</span></span></td>
<td><span data-ttu-id="82ea2-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-204">Default cost center</span></span></td>
<td><span data-ttu-id="82ea2-205">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-205">10001</span></span></td>
<td><span data-ttu-id="82ea2-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-206">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-207">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-208">1,000.00</span></span></td>
<td><span data-ttu-id="82ea2-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-210">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-210">CC099</span></span></td>
<td><span data-ttu-id="82ea2-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-211">Default cost center</span></span></td>
<td><span data-ttu-id="82ea2-212">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-212">10001</span></span></td>
<td><span data-ttu-id="82ea2-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-213">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-214">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-215">9,000.00</span></span></td>
<td><span data-ttu-id="82ea2-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-217">További információért lásd: [Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="82ea2-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="82ea2-218">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="82ea2-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="82ea2-219">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="82ea2-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="82ea2-220">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="82ea2-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="82ea2-221">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="82ea2-221">Define the cost distribution rule</span></span>

<span data-ttu-id="82ea2-222">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="82ea2-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="82ea2-223">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="82ea2-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="82ea2-224">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="82ea2-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="82ea2-225">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="82ea2-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="82ea2-226">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="82ea2-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="82ea2-227">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="82ea2-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-228">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-228">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="82ea2-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-230">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-230">CC001</span></span></td>
<td><span data-ttu-id="82ea2-231">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-231">HR</span></span></td>
<td><span data-ttu-id="82ea2-232">1000</span><span class="sxs-lookup"><span data-stu-id="82ea2-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-233">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-233">CC002</span></span></td>
<td><span data-ttu-id="82ea2-234">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-234">Finance</span></span></td>
<td><span data-ttu-id="82ea2-235">6,000</span><span class="sxs-lookup"><span data-stu-id="82ea2-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-236">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-236">CC003</span></span></td>
<td><span data-ttu-id="82ea2-237">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-237">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-238">0</span><span class="sxs-lookup"><span data-stu-id="82ea2-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-239">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="82ea2-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-240">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-240">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-241">Nagyság</span><span class="sxs-lookup"><span data-stu-id="82ea2-241">Magnitude</span></span></th>
<th><span data-ttu-id="82ea2-242">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="82ea2-242">Allocation factor</span></span></th>
<th><span data-ttu-id="82ea2-243">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-244">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-244">CC001</span></span></td>
<td><span data-ttu-id="82ea2-245">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-245">HR</span></span></td>
<td><span data-ttu-id="82ea2-246">1000</span><span class="sxs-lookup"><span data-stu-id="82ea2-246">1,000</span></span></td>
<td><span data-ttu-id="82ea2-247">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="82ea2-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="82ea2-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-249">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-249">CC002</span></span></td>
<td><span data-ttu-id="82ea2-250">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-250">Finance</span></span></td>
<td><span data-ttu-id="82ea2-251">6,000</span><span class="sxs-lookup"><span data-stu-id="82ea2-251">6,000</span></span></td>
<td><span data-ttu-id="82ea2-252">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="82ea2-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="82ea2-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-254">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-254">CC003</span></span></td>
<td><span data-ttu-id="82ea2-255">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-255">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-256">0</span><span class="sxs-lookup"><span data-stu-id="82ea2-256">0</span></span></td>
<td><span data-ttu-id="82ea2-257">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="82ea2-258">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-259">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="82ea2-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="82ea2-260">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: (Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="82ea2-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-261">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-261">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-262">Receptúra</span><span class="sxs-lookup"><span data-stu-id="82ea2-262">Formula</span></span></th>
<th><span data-ttu-id="82ea2-263">Nagyság</span><span class="sxs-lookup"><span data-stu-id="82ea2-263">Magnitude</span></span></th>
<th><span data-ttu-id="82ea2-264">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="82ea2-264">Allocation factor</span></span></th>
<th><span data-ttu-id="82ea2-265">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-266">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-266">CC001</span></span></td>
<td><span data-ttu-id="82ea2-267">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-267">HR</span></span></td>
<td><span data-ttu-id="82ea2-268">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="82ea2-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="82ea2-269">1</span><span class="sxs-lookup"><span data-stu-id="82ea2-269">1</span></span></td>
<td><span data-ttu-id="82ea2-270">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="82ea2-271">500.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-272">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-272">CC002</span></span></td>
<td><span data-ttu-id="82ea2-273">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-273">Finance</span></span></td>
<td><span data-ttu-id="82ea2-274">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="82ea2-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="82ea2-275">1</span><span class="sxs-lookup"><span data-stu-id="82ea2-275">1</span></span></td>
<td><span data-ttu-id="82ea2-276">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="82ea2-277">500.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-278">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-278">CC003</span></span></td>
<td><span data-ttu-id="82ea2-279">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-279">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-280">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="82ea2-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="82ea2-281">0</span><span class="sxs-lookup"><span data-stu-id="82ea2-281">0</span></span></td>
<td><span data-ttu-id="82ea2-282">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="82ea2-283">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="82ea2-284">Napló</span><span class="sxs-lookup"><span data-stu-id="82ea2-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="82ea2-285">Napló</span><span class="sxs-lookup"><span data-stu-id="82ea2-285">Journal</span></span></th>
<th><span data-ttu-id="82ea2-286">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="82ea2-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="82ea2-287">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="82ea2-288">Verzió</span><span class="sxs-lookup"><span data-stu-id="82ea2-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-289">00002</span><span class="sxs-lookup"><span data-stu-id="82ea2-289">00002</span></span></td>
<td><span data-ttu-id="82ea2-290">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="82ea2-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="82ea2-291">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="82ea2-291">Fiscal</span></span></td>
<td><span data-ttu-id="82ea2-292">2017</span><span class="sxs-lookup"><span data-stu-id="82ea2-292">2017</span></span></td>
<td><span data-ttu-id="82ea2-293">1. időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-293">Period 1</span></span></td>
<td><span data-ttu-id="82ea2-294">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="82ea2-295">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="82ea2-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="82ea2-296">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="82ea2-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-297">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-298">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="82ea2-298">Cost element</span></span></th>
<th><span data-ttu-id="82ea2-299">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-299">Cost behavior</span></span></th>
<th><span data-ttu-id="82ea2-300">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-301">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-302">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-302">CC099</span></span></td>
<td><span data-ttu-id="82ea2-303">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-303">Default cost center</span></span></td>
<td><span data-ttu-id="82ea2-304">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-304">10001</span></span></td>
<td><span data-ttu-id="82ea2-305">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-305">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-306">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-306">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-308">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-309">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-309">CC099</span></span></td>
<td><span data-ttu-id="82ea2-310">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-310">Default cost center</span></span></td>
<td><span data-ttu-id="82ea2-311">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-311">10001</span></span></td>
<td><span data-ttu-id="82ea2-312">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-312">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-313">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-313">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="82ea2-315">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="82ea2-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-316">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-317">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="82ea2-317">Cost element</span></span></th>
<th><span data-ttu-id="82ea2-318">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-318">Cost behavior</span></span></th>
<th><span data-ttu-id="82ea2-319">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-319">Amount</span></span></th>
<th><span data-ttu-id="82ea2-320">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="82ea2-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-321">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-321">CC099</span></span></td>
<td><span data-ttu-id="82ea2-322">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-322">Default cost center</span></span></td>
<td><span data-ttu-id="82ea2-323">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-323">10001</span></span></td>
<td><span data-ttu-id="82ea2-324">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-324">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-325">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-325">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-326">-1,000.00</span></span></td>
<td><span data-ttu-id="82ea2-327">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-328">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-328">CC001</span></span></td>
<td><span data-ttu-id="82ea2-329">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-329">HR</span></span></td>
<td><span data-ttu-id="82ea2-330">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-330">10001</span></span></td>
<td><span data-ttu-id="82ea2-331">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-331">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-332">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-332">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-333">500.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-333">500.00</span></span></td>
<td><span data-ttu-id="82ea2-334">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-335">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-335">CC002</span></span></td>
<td><span data-ttu-id="82ea2-336">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-336">Finance</span></span></td>
<td><span data-ttu-id="82ea2-337">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-337">10001</span></span></td>
<td><span data-ttu-id="82ea2-338">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-338">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-339">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-339">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-340">500.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-340">500.00</span></span></td>
<td><span data-ttu-id="82ea2-341">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-342">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-342">CC099</span></span></td>
<td><span data-ttu-id="82ea2-343">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="82ea2-343">Default cost center</span></span></td>
<td><span data-ttu-id="82ea2-344">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-344">10001</span></span></td>
<td><span data-ttu-id="82ea2-345">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-345">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-346">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-346">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-347">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-347">-9,000.00</span></span></td>
<td><span data-ttu-id="82ea2-348">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-349">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-349">CC001</span></span></td>
<td><span data-ttu-id="82ea2-350">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-350">HR</span></span></td>
<td><span data-ttu-id="82ea2-351">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-351">10001</span></span></td>
<td><span data-ttu-id="82ea2-352">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-352">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-353">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-353">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="82ea2-354">1,285.71</span></span></td>
<td><span data-ttu-id="82ea2-355">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-356">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-356">CC002</span></span></td>
<td><span data-ttu-id="82ea2-357">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-357">Finance</span></span></td>
<td><span data-ttu-id="82ea2-358">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-358">10001</span></span></td>
<td><span data-ttu-id="82ea2-359">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-359">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-360">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-360">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="82ea2-361">7,714.29</span></span></td>
<td><span data-ttu-id="82ea2-362">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-363">További információért lásd: [Költségelosztási irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="82ea2-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="82ea2-364">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="82ea2-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="82ea2-365">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="82ea2-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="82ea2-366">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="82ea2-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="82ea2-367">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="82ea2-367">Define the overhead rate</span></span>

<span data-ttu-id="82ea2-368">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="82ea2-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="82ea2-369">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="82ea2-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-370">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-370">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-371">óra</span><span class="sxs-lookup"><span data-stu-id="82ea2-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-372">Proj 1</span></span></td>
<td><span data-ttu-id="82ea2-373">1. projekt</span><span class="sxs-lookup"><span data-stu-id="82ea2-373">Project 1</span></span></td>
<td><span data-ttu-id="82ea2-374">3</span><span class="sxs-lookup"><span data-stu-id="82ea2-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-375">Proj 2</span></span></td>
<td><span data-ttu-id="82ea2-376">2. projekt</span><span class="sxs-lookup"><span data-stu-id="82ea2-376">Project 2</span></span></td>
<td><span data-ttu-id="82ea2-377">1</span><span class="sxs-lookup"><span data-stu-id="82ea2-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-378">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="82ea2-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-379">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-379">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-380">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="82ea2-380">Cost element</span></span></th>
<th><span data-ttu-id="82ea2-381">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-381">Cost behavior</span></span></th>
<th><span data-ttu-id="82ea2-382">Egységek</span><span class="sxs-lookup"><span data-stu-id="82ea2-382">Units</span></span></th>
<th><span data-ttu-id="82ea2-383">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="82ea2-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-384">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-384">CC001</span></span></td>
<td><span data-ttu-id="82ea2-385">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-385">HR</span></span></td>
<td><span data-ttu-id="82ea2-386">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-386">10001</span></span></td>
<td><span data-ttu-id="82ea2-387">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-387">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-388">1</span><span class="sxs-lookup"><span data-stu-id="82ea2-388">1</span></span></td>
<td><span data-ttu-id="82ea2-389">10</span><span class="sxs-lookup"><span data-stu-id="82ea2-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-390">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="82ea2-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-391">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-391">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-392">Nagyság</span><span class="sxs-lookup"><span data-stu-id="82ea2-392">Magnitude</span></span></th>
<th><span data-ttu-id="82ea2-393">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="82ea2-393">Cost element</span></span></th>
<th><span data-ttu-id="82ea2-394">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="82ea2-394">Allocation factor</span></span></th>
<th><span data-ttu-id="82ea2-395">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-396">Proj 1</span></span></td>
<td><span data-ttu-id="82ea2-397">1. projekt</span><span class="sxs-lookup"><span data-stu-id="82ea2-397">Project 1</span></span></td>
<td><span data-ttu-id="82ea2-398">3</span><span class="sxs-lookup"><span data-stu-id="82ea2-398">3</span></span></td>
<td><span data-ttu-id="82ea2-399">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-399">10001</span></span></td>
<td><span data-ttu-id="82ea2-400">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="82ea2-401">30.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-402">Proj 2</span></span></td>
<td><span data-ttu-id="82ea2-403">2. projekt</span><span class="sxs-lookup"><span data-stu-id="82ea2-403">Project 2</span></span></td>
<td><span data-ttu-id="82ea2-404">1</span><span class="sxs-lookup"><span data-stu-id="82ea2-404">1</span></span></td>
<td><span data-ttu-id="82ea2-405">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-405">10001</span></span></td>
<td><span data-ttu-id="82ea2-406">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="82ea2-407">10.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="82ea2-408">Napló</span><span class="sxs-lookup"><span data-stu-id="82ea2-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="82ea2-409">Napló</span><span class="sxs-lookup"><span data-stu-id="82ea2-409">Journal</span></span></th>
<th><span data-ttu-id="82ea2-410">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="82ea2-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="82ea2-411">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="82ea2-412">Verzió</span><span class="sxs-lookup"><span data-stu-id="82ea2-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-413">00003</span><span class="sxs-lookup"><span data-stu-id="82ea2-413">00003</span></span></td>
<td><span data-ttu-id="82ea2-414">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="82ea2-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="82ea2-415">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="82ea2-415">Fiscal</span></span></td>
<td><span data-ttu-id="82ea2-416">2017</span><span class="sxs-lookup"><span data-stu-id="82ea2-416">2017</span></span></td>
<td><span data-ttu-id="82ea2-417">1. időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-417">Period 1</span></span></td>
<td><span data-ttu-id="82ea2-418">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="82ea2-419">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="82ea2-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="82ea2-420">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="82ea2-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-421">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-421">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-422">Nagyság</span><span class="sxs-lookup"><span data-stu-id="82ea2-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-423">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-424">Proj 1</span></span></td>
<td><span data-ttu-id="82ea2-425">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="82ea2-426">3,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-427">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-428">Proj 2</span></span></td>
<td><span data-ttu-id="82ea2-429">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="82ea2-430">1.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="82ea2-431">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="82ea2-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-432">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-433">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="82ea2-433">Cost element</span></span></th>
<th><span data-ttu-id="82ea2-434">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-434">Cost behavior</span></span></th>
<th><span data-ttu-id="82ea2-435">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-435">Amount</span></span></th>
<th><span data-ttu-id="82ea2-436">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="82ea2-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="82ea2-437">CC0001</span></span></td>
<td><span data-ttu-id="82ea2-438">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-438">HR</span></span></td>
<td><span data-ttu-id="82ea2-439">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-439">10001</span></span></td>
<td><span data-ttu-id="82ea2-440">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-440">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-441">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-441">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-442">-30.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-442">-30.00</span></span></td>
<td><span data-ttu-id="82ea2-443">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-444">Proj 1</span></span></td>
<td><span data-ttu-id="82ea2-445">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="82ea2-446">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-446">10001</span></span></td>
<td><span data-ttu-id="82ea2-447">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-447">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-448">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-448">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-449">30.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-449">30.00</span></span></td>
<td><span data-ttu-id="82ea2-450">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-451">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-451">CC001</span></span></td>
<td><span data-ttu-id="82ea2-452">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-452">HR</span></span></td>
<td><span data-ttu-id="82ea2-453">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-453">10001</span></span></td>
<td><span data-ttu-id="82ea2-454">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-454">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-455">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-455">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-456">-10.00</span></span></td>
<td><span data-ttu-id="82ea2-457">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-458">Proj 2</span></span></td>
<td><span data-ttu-id="82ea2-459">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="82ea2-460">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-460">10001</span></span></td>
<td><span data-ttu-id="82ea2-461">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-461">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-462">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-462">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-463">10,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-463">10.00</span></span></td>
<td><span data-ttu-id="82ea2-464">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-465">További információ: [Járulékosköltség-számítás végrehajtása](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="82ea2-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="82ea2-466">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="82ea2-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="82ea2-467">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="82ea2-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="82ea2-468">A Finance a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="82ea2-468">Finance supports the reciprocal allocation method.</span></span> <span data-ttu-id="82ea2-469">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="82ea2-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="82ea2-470">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="82ea2-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="82ea2-471">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="82ea2-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="82ea2-472">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="82ea2-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="82ea2-473">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="82ea2-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="82ea2-474">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="82ea2-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="82ea2-475">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="82ea2-475">Define the cost allocation</span></span>

<span data-ttu-id="82ea2-476">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="82ea2-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="82ea2-477">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="82ea2-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="82ea2-478">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="82ea2-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-479">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-479">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-480">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="82ea2-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-481">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-481">CC002</span></span></td>
<td><span data-ttu-id="82ea2-482">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-482">Finance</span></span></td>
<td><span data-ttu-id="82ea2-483">35</span><span class="sxs-lookup"><span data-stu-id="82ea2-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-484">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-484">CC003</span></span></td>
<td><span data-ttu-id="82ea2-485">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-485">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-486">55</span><span class="sxs-lookup"><span data-stu-id="82ea2-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-487">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-487">CC004</span></span></td>
<td><span data-ttu-id="82ea2-488">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-488">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-489">10</span><span class="sxs-lookup"><span data-stu-id="82ea2-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-490">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="82ea2-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="82ea2-491">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="82ea2-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-492">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-492">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-493">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="82ea2-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-494">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-494">CC003</span></span></td>
<td><span data-ttu-id="82ea2-495">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-495">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-496">65</span><span class="sxs-lookup"><span data-stu-id="82ea2-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-497">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-497">CC004</span></span></td>
<td><span data-ttu-id="82ea2-498">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-498">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-499">35</span><span class="sxs-lookup"><span data-stu-id="82ea2-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-500">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="82ea2-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="82ea2-501">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="82ea2-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-502">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-502">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-503">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="82ea2-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-504">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-504">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-505">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-505">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-506">60</span><span class="sxs-lookup"><span data-stu-id="82ea2-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-507">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-507">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-508">2. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-508">Product 2</span></span></td>
<td><span data-ttu-id="82ea2-509">20</span><span class="sxs-lookup"><span data-stu-id="82ea2-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-510">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="82ea2-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="82ea2-511">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="82ea2-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-512">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-512">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-513">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="82ea2-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-514">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-514">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-515">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-515">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-516">80</span><span class="sxs-lookup"><span data-stu-id="82ea2-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-517">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-517">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-518">2. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-518">Product 2</span></span></td>
<td><span data-ttu-id="82ea2-519">15</span><span class="sxs-lookup"><span data-stu-id="82ea2-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="82ea2-520">A statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="82ea2-520">Statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="82ea2-521">További információk: [Statisztikaimérték-szolgáltató sablon](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="82ea2-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="82ea2-522">Az alábbi táblázat azt az eredményt mutatja, amikor a HR szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="82ea2-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-523">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-523">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-524">Nagyság</span><span class="sxs-lookup"><span data-stu-id="82ea2-524">Magnitude</span></span></th>
<th><span data-ttu-id="82ea2-525">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="82ea2-525">Allocation factor</span></span></th>
<th><span data-ttu-id="82ea2-526">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-526">Amount</span></span></th>
<th><span data-ttu-id="82ea2-527">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-528">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-528">CC002</span></span></td>
<td><span data-ttu-id="82ea2-529">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-529">Finance</span></span></td>
<td><span data-ttu-id="82ea2-530">35</span><span class="sxs-lookup"><span data-stu-id="82ea2-530">35</span></span></td>
<td><span data-ttu-id="82ea2-531">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="82ea2-532">175.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-532">175.00</span></span></td>
<td><span data-ttu-id="82ea2-533">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-534">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-534">CC003</span></span></td>
<td><span data-ttu-id="82ea2-535">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-535">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-536">55</span><span class="sxs-lookup"><span data-stu-id="82ea2-536">55</span></span></td>
<td><span data-ttu-id="82ea2-537">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="82ea2-538">275.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-538">275.00</span></span></td>
<td><span data-ttu-id="82ea2-539">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-540">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-540">CC004</span></span></td>
<td><span data-ttu-id="82ea2-541">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-541">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-542">10</span><span class="sxs-lookup"><span data-stu-id="82ea2-542">10</span></span></td>
<td><span data-ttu-id="82ea2-543">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="82ea2-544">50,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-544">50.00</span></span></td>
<td><span data-ttu-id="82ea2-545">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-546">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-546">CC002</span></span></td>
<td><span data-ttu-id="82ea2-547">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-547">Finance</span></span></td>
<td><span data-ttu-id="82ea2-548">35</span><span class="sxs-lookup"><span data-stu-id="82ea2-548">35</span></span></td>
<td><span data-ttu-id="82ea2-549">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="82ea2-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="82ea2-550">436.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-550">436.00</span></span></td>
<td><span data-ttu-id="82ea2-551">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-552">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-552">CC003</span></span></td>
<td><span data-ttu-id="82ea2-553">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-553">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-554">55</span><span class="sxs-lookup"><span data-stu-id="82ea2-554">55</span></span></td>
<td><span data-ttu-id="82ea2-555">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="82ea2-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="82ea2-556">685.14</span><span class="sxs-lookup"><span data-stu-id="82ea2-556">685.14</span></span></td>
<td><span data-ttu-id="82ea2-557">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-558">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-558">CC004</span></span></td>
<td><span data-ttu-id="82ea2-559">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-559">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-560">10</span><span class="sxs-lookup"><span data-stu-id="82ea2-560">10</span></span></td>
<td><span data-ttu-id="82ea2-561">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="82ea2-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="82ea2-562">124.57</span><span class="sxs-lookup"><span data-stu-id="82ea2-562">124.57</span></span></td>
<td><span data-ttu-id="82ea2-563">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-564">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="82ea2-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-565">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-565">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-566">Nagyság</span><span class="sxs-lookup"><span data-stu-id="82ea2-566">Magnitude</span></span></th>
<th><span data-ttu-id="82ea2-567">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="82ea2-567">Allocation factor</span></span></th>
<th><span data-ttu-id="82ea2-568">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-568">Amount</span></span></th>
<th><span data-ttu-id="82ea2-569">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-570">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-570">CC003</span></span></td>
<td><span data-ttu-id="82ea2-571">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-571">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-572">65</span><span class="sxs-lookup"><span data-stu-id="82ea2-572">65</span></span></td>
<td><span data-ttu-id="82ea2-573">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="82ea2-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="82ea2-574">438.75</span><span class="sxs-lookup"><span data-stu-id="82ea2-574">438.75</span></span></td>
<td><span data-ttu-id="82ea2-575">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-576">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-576">CC004</span></span></td>
<td><span data-ttu-id="82ea2-577">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-577">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-578">35</span><span class="sxs-lookup"><span data-stu-id="82ea2-578">35</span></span></td>
<td><span data-ttu-id="82ea2-579">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="82ea2-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="82ea2-580">236.25</span><span class="sxs-lookup"><span data-stu-id="82ea2-580">236.25</span></span></td>
<td><span data-ttu-id="82ea2-581">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-582">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-582">CC003</span></span></td>
<td><span data-ttu-id="82ea2-583">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-583">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-584">65</span><span class="sxs-lookup"><span data-stu-id="82ea2-584">65</span></span></td>
<td><span data-ttu-id="82ea2-585">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="82ea2-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="82ea2-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="82ea2-586">5,297.69</span></span></td>
<td><span data-ttu-id="82ea2-587">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-588">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-588">CC004</span></span></td>
<td><span data-ttu-id="82ea2-589">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-589">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-590">35</span><span class="sxs-lookup"><span data-stu-id="82ea2-590">35</span></span></td>
<td><span data-ttu-id="82ea2-591">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="82ea2-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="82ea2-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="82ea2-592">2,852.60</span></span></td>
<td><span data-ttu-id="82ea2-593">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-594">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="82ea2-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-595">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-595">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-596">Nagyság</span><span class="sxs-lookup"><span data-stu-id="82ea2-596">Magnitude</span></span></th>
<th><span data-ttu-id="82ea2-597">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="82ea2-597">Allocation factor</span></span></th>
<th><span data-ttu-id="82ea2-598">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-598">Amount</span></span></th>
<th><span data-ttu-id="82ea2-599">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-600">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-600">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-601">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-601">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-602">60</span><span class="sxs-lookup"><span data-stu-id="82ea2-602">60</span></span></td>
<td><span data-ttu-id="82ea2-603">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="82ea2-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="82ea2-604">535.31</span><span class="sxs-lookup"><span data-stu-id="82ea2-604">535.31</span></span></td>
<td><span data-ttu-id="82ea2-605">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-606">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-606">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-607">2. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-607">Product 2</span></span></td>
<td><span data-ttu-id="82ea2-608">20</span><span class="sxs-lookup"><span data-stu-id="82ea2-608">20</span></span></td>
<td><span data-ttu-id="82ea2-609">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="82ea2-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="82ea2-610">178.44</span><span class="sxs-lookup"><span data-stu-id="82ea2-610">178.44</span></span></td>
<td><span data-ttu-id="82ea2-611">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-612">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-612">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-613">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-613">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-614">60</span><span class="sxs-lookup"><span data-stu-id="82ea2-614">60</span></span></td>
<td><span data-ttu-id="82ea2-615">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="82ea2-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="82ea2-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="82ea2-616">4,487.12</span></span></td>
<td><span data-ttu-id="82ea2-617">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-618">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-618">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-619">2. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-619">Product 2</span></span></td>
<td><span data-ttu-id="82ea2-620">20</span><span class="sxs-lookup"><span data-stu-id="82ea2-620">20</span></span></td>
<td><span data-ttu-id="82ea2-621">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="82ea2-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="82ea2-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="82ea2-622">1,495.71</span></span></td>
<td><span data-ttu-id="82ea2-623">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="82ea2-624">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="82ea2-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-625">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-625">Cost object</span></span></th>
<th><span data-ttu-id="82ea2-626">Nagyság</span><span class="sxs-lookup"><span data-stu-id="82ea2-626">Magnitude</span></span></th>
<th><span data-ttu-id="82ea2-627">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="82ea2-627">Allocation factor</span></span></th>
<th><span data-ttu-id="82ea2-628">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-628">Amount</span></span></th>
<th><span data-ttu-id="82ea2-629">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-630">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-630">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-631">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-631">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-632">80</span><span class="sxs-lookup"><span data-stu-id="82ea2-632">80</span></span></td>
<td><span data-ttu-id="82ea2-633">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="82ea2-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="82ea2-634">241.05</span><span class="sxs-lookup"><span data-stu-id="82ea2-634">241.05</span></span></td>
<td><span data-ttu-id="82ea2-635">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-636">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-636">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-637">2. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-637">Product 2</span></span></td>
<td><span data-ttu-id="82ea2-638">15.</span><span class="sxs-lookup"><span data-stu-id="82ea2-638">15</span></span></td>
<td><span data-ttu-id="82ea2-639">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="82ea2-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="82ea2-640">45.20</span><span class="sxs-lookup"><span data-stu-id="82ea2-640">45.20</span></span></td>
<td><span data-ttu-id="82ea2-641">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-642">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-642">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-643">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-643">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-644">80</span><span class="sxs-lookup"><span data-stu-id="82ea2-644">80</span></span></td>
<td><span data-ttu-id="82ea2-645">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="82ea2-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="82ea2-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="82ea2-646">2,507.09</span></span></td>
<td><span data-ttu-id="82ea2-647">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-648">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-648">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-649">2. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-649">Product 2</span></span></td>
<td><span data-ttu-id="82ea2-650">15.</span><span class="sxs-lookup"><span data-stu-id="82ea2-650">15</span></span></td>
<td><span data-ttu-id="82ea2-651">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="82ea2-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="82ea2-652">470.08</span><span class="sxs-lookup"><span data-stu-id="82ea2-652">470.08</span></span></td>
<td><span data-ttu-id="82ea2-653">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="82ea2-654">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="82ea2-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="82ea2-655">Napló</span><span class="sxs-lookup"><span data-stu-id="82ea2-655">Journal</span></span></th>
<th><span data-ttu-id="82ea2-656">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="82ea2-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="82ea2-657">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="82ea2-658">Verzió</span><span class="sxs-lookup"><span data-stu-id="82ea2-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-659">00004</span><span class="sxs-lookup"><span data-stu-id="82ea2-659">00004</span></span></td>
<td><span data-ttu-id="82ea2-660">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="82ea2-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="82ea2-661">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="82ea2-661">Fiscal</span></span></td>
<td><span data-ttu-id="82ea2-662">2017</span><span class="sxs-lookup"><span data-stu-id="82ea2-662">2017</span></span></td>
<td><span data-ttu-id="82ea2-663">1. időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-663">Period 1</span></span></td>
<td><span data-ttu-id="82ea2-664">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="82ea2-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="82ea2-665">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="82ea2-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="82ea2-666">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="82ea2-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-667">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-668">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="82ea2-668">Cost element</span></span></th>
<th><span data-ttu-id="82ea2-669">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-669">Cost behavior</span></span></th>
<th><span data-ttu-id="82ea2-670">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-671">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-672">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-672">CC001</span></span></td>
<td><span data-ttu-id="82ea2-673">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-673">HR</span></span></td>
<td><span data-ttu-id="82ea2-674">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-674">10001</span></span></td>
<td><span data-ttu-id="82ea2-675">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-675">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-676">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-676">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-677">500.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-678">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-679">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-679">CC001</span></span></td>
<td><span data-ttu-id="82ea2-680">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-680">HR</span></span></td>
<td><span data-ttu-id="82ea2-681">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-681">10001</span></span></td>
<td><span data-ttu-id="82ea2-682">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-682">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-683">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-683">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="82ea2-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-685">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-686">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-686">CC002</span></span></td>
<td><span data-ttu-id="82ea2-687">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-687">Finance</span></span></td>
<td><span data-ttu-id="82ea2-688">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-688">10001</span></span></td>
<td><span data-ttu-id="82ea2-689">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-689">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-690">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-690">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-691">675.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-692">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-693">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-693">CC002</span></span></td>
<td><span data-ttu-id="82ea2-694">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-694">Finance</span></span></td>
<td><span data-ttu-id="82ea2-695">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-695">10001</span></span></td>
<td><span data-ttu-id="82ea2-696">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-696">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-697">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-697">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="82ea2-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-699">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-700">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-700">CC003</span></span></td>
<td><span data-ttu-id="82ea2-701">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-701">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-702">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-702">10001</span></span></td>
<td><span data-ttu-id="82ea2-703">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-703">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-704">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-704">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-705">713.75</span><span class="sxs-lookup"><span data-stu-id="82ea2-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-706">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-707">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-707">CC003</span></span></td>
<td><span data-ttu-id="82ea2-708">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-708">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-709">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-709">10001</span></span></td>
<td><span data-ttu-id="82ea2-710">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-710">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-711">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-711">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="82ea2-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-713">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-714">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-714">CC003</span></span></td>
<td><span data-ttu-id="82ea2-715">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-715">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-716">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-716">10001</span></span></td>
<td><span data-ttu-id="82ea2-717">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-717">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-718">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-718">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-719">286.25</span><span class="sxs-lookup"><span data-stu-id="82ea2-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-720">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-721">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-721">CC003</span></span></td>
<td><span data-ttu-id="82ea2-722">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-722">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-723">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-723">10001</span></span></td>
<td><span data-ttu-id="82ea2-724">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-724">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-725">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-725">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="82ea2-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-727">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-728">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-728">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-729">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-729">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-730">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-730">10001</span></span></td>
<td><span data-ttu-id="82ea2-731">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-731">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-732">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-732">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-733">776.36</span><span class="sxs-lookup"><span data-stu-id="82ea2-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-734">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-735">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-735">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-736">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-736">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-737">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-737">10001</span></span></td>
<td><span data-ttu-id="82ea2-738">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-738">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-739">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-739">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="82ea2-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-741">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-742">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-742">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-743">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-743">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-744">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-744">10001</span></span></td>
<td><span data-ttu-id="82ea2-745">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-745">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-746">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-746">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-747">223.64</span><span class="sxs-lookup"><span data-stu-id="82ea2-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-748">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="82ea2-749">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-749">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-750">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-750">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-751">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-751">10001</span></span></td>
<td><span data-ttu-id="82ea2-752">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-752">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-753">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-753">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="82ea2-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="82ea2-755">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="82ea2-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="82ea2-756">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="82ea2-757">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="82ea2-757">Cost element</span></span></th>
<th><span data-ttu-id="82ea2-758">Költség működése</span><span class="sxs-lookup"><span data-stu-id="82ea2-758">Cost behavior</span></span></th>
<th><span data-ttu-id="82ea2-759">Összeg</span><span class="sxs-lookup"><span data-stu-id="82ea2-759">Amount</span></span></th>
<th><span data-ttu-id="82ea2-760">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="82ea2-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="82ea2-761">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-761">CC001</span></span></td>
<td><span data-ttu-id="82ea2-762">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-762">HR</span></span></td>
<td><span data-ttu-id="82ea2-763">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-763">10001</span></span></td>
<td><span data-ttu-id="82ea2-764">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-764">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-765">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-765">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-766">-500.00</span></span></td>
<td><span data-ttu-id="82ea2-767">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-768">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-768">CC002</span></span></td>
<td><span data-ttu-id="82ea2-769">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-769">Finance</span></span></td>
<td><span data-ttu-id="82ea2-770">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-770">10001</span></span></td>
<td><span data-ttu-id="82ea2-771">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-771">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-772">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-772">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-773">175.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-773">175.00</span></span></td>
<td><span data-ttu-id="82ea2-774">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-775">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-775">CC003</span></span></td>
<td><span data-ttu-id="82ea2-776">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-776">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-777">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-777">10001</span></span></td>
<td><span data-ttu-id="82ea2-778">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-778">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-779">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-779">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-780">275.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-780">275.00</span></span></td>
<td><span data-ttu-id="82ea2-781">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-782">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-782">CC004</span></span></td>
<td><span data-ttu-id="82ea2-783">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-783">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-784">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-784">10001</span></span></td>
<td><span data-ttu-id="82ea2-785">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-785">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-786">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-786">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-787">50,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-787">50,00</span></span></td>
<td><span data-ttu-id="82ea2-788">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-789">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-789">CC001</span></span></td>
<td><span data-ttu-id="82ea2-790">HR</span><span class="sxs-lookup"><span data-stu-id="82ea2-790">HR</span></span></td>
<td><span data-ttu-id="82ea2-791">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-791">10001</span></span></td>
<td><span data-ttu-id="82ea2-792">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-792">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-793">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-793">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-794">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="82ea2-794">-1,245.71</span></span></td>
<td><span data-ttu-id="82ea2-795">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-796">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-796">CC002</span></span></td>
<td><span data-ttu-id="82ea2-797">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-797">Finance</span></span></td>
<td><span data-ttu-id="82ea2-798">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-798">10001</span></span></td>
<td><span data-ttu-id="82ea2-799">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-799">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-800">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-800">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-801">436.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-801">436.00</span></span></td>
<td><span data-ttu-id="82ea2-802">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-803">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-803">CC003</span></span></td>
<td><span data-ttu-id="82ea2-804">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-804">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-805">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-805">10001</span></span></td>
<td><span data-ttu-id="82ea2-806">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-806">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-807">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-807">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-808">685.14</span><span class="sxs-lookup"><span data-stu-id="82ea2-808">685.14</span></span></td>
<td><span data-ttu-id="82ea2-809">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-810">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-810">CC004</span></span></td>
<td><span data-ttu-id="82ea2-811">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-811">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-812">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-812">10001</span></span></td>
<td><span data-ttu-id="82ea2-813">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-813">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-814">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-814">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-815">124.57</span><span class="sxs-lookup"><span data-stu-id="82ea2-815">124.57</span></span></td>
<td><span data-ttu-id="82ea2-816">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-817">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-817">CC002</span></span></td>
<td><span data-ttu-id="82ea2-818">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-818">Finance</span></span></td>
<td><span data-ttu-id="82ea2-819">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-819">10001</span></span></td>
<td><span data-ttu-id="82ea2-820">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-820">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-821">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-821">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-822">-675.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-822">-675.00</span></span></td>
<td><span data-ttu-id="82ea2-823">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-824">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-824">CC003</span></span></td>
<td><span data-ttu-id="82ea2-825">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-825">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-826">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-826">10001</span></span></td>
<td><span data-ttu-id="82ea2-827">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-827">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-828">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-828">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-829">438.75</span><span class="sxs-lookup"><span data-stu-id="82ea2-829">438.75</span></span></td>
<td><span data-ttu-id="82ea2-830">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-831">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-831">CC004</span></span></td>
<td><span data-ttu-id="82ea2-832">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-832">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-833">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-833">10001</span></span></td>
<td><span data-ttu-id="82ea2-834">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-834">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-835">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-835">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-836">236.25</span><span class="sxs-lookup"><span data-stu-id="82ea2-836">236.25</span></span></td>
<td><span data-ttu-id="82ea2-837">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-838">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-838">CC002</span></span></td>
<td><span data-ttu-id="82ea2-839">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="82ea2-839">Finance</span></span></td>
<td><span data-ttu-id="82ea2-840">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-840">10001</span></span></td>
<td><span data-ttu-id="82ea2-841">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-841">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-842">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-842">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-843">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="82ea2-843">-8,150.29</span></span></td>
<td><span data-ttu-id="82ea2-844">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-845">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-845">CC003</span></span></td>
<td><span data-ttu-id="82ea2-846">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-846">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-847">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-847">10001</span></span></td>
<td><span data-ttu-id="82ea2-848">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-848">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-849">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-849">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="82ea2-850">5,297.69</span></span></td>
<td><span data-ttu-id="82ea2-851">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-852">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-852">CC004</span></span></td>
<td><span data-ttu-id="82ea2-853">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="82ea2-853">Packaging</span></span></td>
<td><span data-ttu-id="82ea2-854">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-854">10001</span></span></td>
<td><span data-ttu-id="82ea2-855">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-855">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-856">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-856">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="82ea2-857">2,852.60</span></span></td>
<td><span data-ttu-id="82ea2-858">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-859">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-859">CC003</span></span></td>
<td><span data-ttu-id="82ea2-860">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-860">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-861">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-861">10001</span></span></td>
<td><span data-ttu-id="82ea2-862">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-862">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-863">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-863">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-864">-713.75</span><span class="sxs-lookup"><span data-stu-id="82ea2-864">-713.75</span></span></td>
<td><span data-ttu-id="82ea2-865">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-866">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-866">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-867">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-867">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-868">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-868">10001</span></span></td>
<td><span data-ttu-id="82ea2-869">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-869">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-870">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-870">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-871">535.31</span><span class="sxs-lookup"><span data-stu-id="82ea2-871">535.31</span></span></td>
<td><span data-ttu-id="82ea2-872">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-873">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-873">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-874">2. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-874">Product 2</span></span></td>
<td><span data-ttu-id="82ea2-875">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-875">10001</span></span></td>
<td><span data-ttu-id="82ea2-876">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-876">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-877">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-877">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-878">178.44</span><span class="sxs-lookup"><span data-stu-id="82ea2-878">178.44</span></span></td>
<td><span data-ttu-id="82ea2-879">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-880">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-880">CC003</span></span></td>
<td><span data-ttu-id="82ea2-881">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-881">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-882">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-882">10001</span></span></td>
<td><span data-ttu-id="82ea2-883">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-883">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-884">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-884">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-885">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="82ea2-885">-5,982.83</span></span></td>
<td><span data-ttu-id="82ea2-886">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-887">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-887">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-888">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-888">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-889">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-889">10001</span></span></td>
<td><span data-ttu-id="82ea2-890">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-890">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-891">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-891">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="82ea2-892">4,487.12</span></span></td>
<td><span data-ttu-id="82ea2-893">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-894">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-894">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-895">2. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-895">Product 2</span></span></td>
<td><span data-ttu-id="82ea2-896">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-896">10001</span></span></td>
<td><span data-ttu-id="82ea2-897">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-897">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-898">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-898">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="82ea2-899">1,495.71</span></span></td>
<td><span data-ttu-id="82ea2-900">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-901">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-901">CC003</span></span></td>
<td><span data-ttu-id="82ea2-902">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-902">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-903">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-903">10001</span></span></td>
<td><span data-ttu-id="82ea2-904">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-904">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-905">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-905">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-906">-286.25</span><span class="sxs-lookup"><span data-stu-id="82ea2-906">-286.25</span></span></td>
<td><span data-ttu-id="82ea2-907">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-908">Term 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-908">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-909">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-909">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-910">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-910">10001</span></span></td>
<td><span data-ttu-id="82ea2-911">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-911">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-912">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-912">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-913">241.05</span><span class="sxs-lookup"><span data-stu-id="82ea2-913">241.05</span></span></td>
<td><span data-ttu-id="82ea2-914">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-915">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-915">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-916">2. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-916">Product 2</span></span></td>
<td><span data-ttu-id="82ea2-917">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-917">10001</span></span></td>
<td><span data-ttu-id="82ea2-918">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-918">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-919">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-919">Fixed cost</span></span></td>
<td><span data-ttu-id="82ea2-920">45.20</span><span class="sxs-lookup"><span data-stu-id="82ea2-920">45.20</span></span></td>
<td><span data-ttu-id="82ea2-921">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-922">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-922">CC003</span></span></td>
<td><span data-ttu-id="82ea2-923">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="82ea2-923">Assembly</span></span></td>
<td><span data-ttu-id="82ea2-924">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-924">10001</span></span></td>
<td><span data-ttu-id="82ea2-925">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-925">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-926">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-926">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-927">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="82ea2-927">-2,977.17</span></span></td>
<td><span data-ttu-id="82ea2-928">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-929">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-929">Prod 1</span></span></td>
<td><span data-ttu-id="82ea2-930">1. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-930">Product 1</span></span></td>
<td><span data-ttu-id="82ea2-931">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-931">10001</span></span></td>
<td><span data-ttu-id="82ea2-932">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-932">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-933">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-933">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="82ea2-934">2,507.09</span></span></td>
<td><span data-ttu-id="82ea2-935">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="82ea2-936">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-936">Prod 2</span></span></td>
<td><span data-ttu-id="82ea2-937">2. termék</span><span class="sxs-lookup"><span data-stu-id="82ea2-937">Product 2</span></span></td>
<td><span data-ttu-id="82ea2-938">10001</span><span class="sxs-lookup"><span data-stu-id="82ea2-938">10001</span></span></td>
<td><span data-ttu-id="82ea2-939">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-939">Electricity</span></span></td>
<td><span data-ttu-id="82ea2-940">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-940">Variable cost</span></span></td>
<td><span data-ttu-id="82ea2-941">470.08</span><span class="sxs-lookup"><span data-stu-id="82ea2-941">470.08</span></span></td>
<td><span data-ttu-id="82ea2-942">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="82ea2-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="82ea2-943">Következtetés</span><span class="sxs-lookup"><span data-stu-id="82ea2-943">Conclusion</span></span>
<span data-ttu-id="82ea2-944">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="82ea2-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="82ea2-945">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="82ea2-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="82ea2-946">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="82ea2-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="82ea2-947">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="82ea2-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="82ea2-948">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="82ea2-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="82ea2-949">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="82ea2-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="82ea2-950">Összesen</span><span class="sxs-lookup"><span data-stu-id="82ea2-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="82ea2-951">CC099</span><span class="sxs-lookup"><span data-stu-id="82ea2-951">CC099</span></span></th>
<th><span data-ttu-id="82ea2-952">CC001</span><span class="sxs-lookup"><span data-stu-id="82ea2-952">CC001</span></span></th>
<th><span data-ttu-id="82ea2-953">CC002</span><span class="sxs-lookup"><span data-stu-id="82ea2-953">CC002</span></span></th>
<th><span data-ttu-id="82ea2-954">CC003</span><span class="sxs-lookup"><span data-stu-id="82ea2-954">CC003</span></span></th>
<th><span data-ttu-id="82ea2-955">CC004</span><span class="sxs-lookup"><span data-stu-id="82ea2-955">CC004</span></span></th>
<th><span data-ttu-id="82ea2-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-956">Proj 1</span></span></th>
<th><span data-ttu-id="82ea2-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-957">Proj 2</span></span></th>
<th><span data-ttu-id="82ea2-958">Term. 1</span><span class="sxs-lookup"><span data-stu-id="82ea2-958">Prod 1</span></span></th>
<th><span data-ttu-id="82ea2-959">Term. 2</span><span class="sxs-lookup"><span data-stu-id="82ea2-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="82ea2-960">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="82ea2-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="82ea2-970">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="82ea2-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-971">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="82ea2-972">Fix költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-973">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-974">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-975">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-976">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-977">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-978">776.36</span><span class="sxs-lookup"><span data-stu-id="82ea2-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-979">223.64</span><span class="sxs-lookup"><span data-stu-id="82ea2-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="82ea2-981">Változó költség</span><span class="sxs-lookup"><span data-stu-id="82ea2-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-982">000</span><span class="sxs-lookup"><span data-stu-id="82ea2-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-983">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-984">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-985">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-986">0,00</span><span class="sxs-lookup"><span data-stu-id="82ea2-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-987">30.00</span><span class="sxs-lookup"><span data-stu-id="82ea2-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-988">1000</span><span class="sxs-lookup"><span data-stu-id="82ea2-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="82ea2-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="82ea2-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="82ea2-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="82ea2-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="82ea2-992">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="82ea2-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="82ea2-993">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="82ea2-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="82ea2-994">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="82ea2-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="82ea2-995">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="82ea2-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="82ea2-996">Részletesebb tájékoztatás: [Költségösszesítési irányelv](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="82ea2-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



