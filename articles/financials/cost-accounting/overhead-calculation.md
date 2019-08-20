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
ms.openlocfilehash: cef4a80aa12927fdbffea4bb6bcb108ad81494a6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841489"
---
# <a name="overhead-calculation"></a><span data-ttu-id="a4c3a-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="a4c3a-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a4c3a-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="a4c3a-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="a4c3a-105">Term definition</span></span>
---------------

<span data-ttu-id="a4c3a-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="a4c3a-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="a4c3a-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="a4c3a-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="a4c3a-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="a4c3a-109">Rent</span></span>
-   <span data-ttu-id="a4c3a-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-110">Electricity</span></span>
-   <span data-ttu-id="a4c3a-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="a4c3a-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="a4c3a-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-112">Overhead calculation overview</span></span>
<span data-ttu-id="a4c3a-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="a4c3a-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="a4c3a-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="a4c3a-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="a4c3a-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="a4c3a-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="a4c3a-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="a4c3a-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="a4c3a-119">Version type</span></span>
-   <span data-ttu-id="a4c3a-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-120">Date and time</span></span>
-   <span data-ttu-id="a4c3a-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="a4c3a-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="a4c3a-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="a4c3a-122">Fiscal year</span></span>
-   <span data-ttu-id="a4c3a-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-123">Fiscal period</span></span>

<span data-ttu-id="a4c3a-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="a4c3a-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="a4c3a-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="a4c3a-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="a4c3a-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="a4c3a-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="a4c3a-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="a4c3a-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="a4c3a-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="a4c3a-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="a4c3a-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="a4c3a-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="a4c3a-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="a4c3a-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="a4c3a-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a4c3a-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="a4c3a-140">Main account</span></span></th>
<th><span data-ttu-id="a4c3a-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="a4c3a-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-143">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-143">CC099</span></span></td>
<td><span data-ttu-id="a4c3a-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-144">Default cost center</span></span></td>
<td><span data-ttu-id="a4c3a-145">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-145">10001</span></span></td>
<td><span data-ttu-id="a4c3a-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-146">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="a4c3a-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="a4c3a-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="a4c3a-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="a4c3a-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="a4c3a-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="a4c3a-151">Define the cost behavior rule</span></span>

<span data-ttu-id="a4c3a-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="a4c3a-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="a4c3a-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="a4c3a-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="a4c3a-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="a4c3a-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="a4c3a-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="a4c3a-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="a4c3a-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="a4c3a-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="a4c3a-159">Napló</span><span class="sxs-lookup"><span data-stu-id="a4c3a-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a4c3a-160">Napló</span><span class="sxs-lookup"><span data-stu-id="a4c3a-160">Journal</span></span></th>
<th><span data-ttu-id="a4c3a-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="a4c3a-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a4c3a-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a4c3a-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="a4c3a-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-164">00001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-164">00001</span></span></td>
<td><span data-ttu-id="a4c3a-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="a4c3a-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="a4c3a-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="a4c3a-166">Fiscal</span></span></td>
<td><span data-ttu-id="a4c3a-167">2017</span><span class="sxs-lookup"><span data-stu-id="a4c3a-167">2017</span></span></td>
<td><span data-ttu-id="a4c3a-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-168">Period 1</span></span></td>
<td><span data-ttu-id="a4c3a-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a4c3a-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a4c3a-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-173">Cost element</span></span></th>
<th><span data-ttu-id="a4c3a-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-174">Cost behavior</span></span></th>
<th><span data-ttu-id="a4c3a-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-177">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-177">CC099</span></span></td>
<td><span data-ttu-id="a4c3a-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-178">Default cost center</span></span></td>
<td><span data-ttu-id="a4c3a-179">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-179">10001</span></span></td>
<td><span data-ttu-id="a4c3a-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-180">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="a4c3a-181">Unclassified</span></span></td>
<td><span data-ttu-id="a4c3a-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a4c3a-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="a4c3a-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-185">Cost element</span></span></th>
<th><span data-ttu-id="a4c3a-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-186">Cost behavior</span></span></th>
<th><span data-ttu-id="a4c3a-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-187">Amount</span></span></th>
<th><span data-ttu-id="a4c3a-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-189">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-189">CC099</span></span></td>
<td><span data-ttu-id="a4c3a-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-190">Default cost center</span></span></td>
<td><span data-ttu-id="a4c3a-191">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-191">10001</span></span></td>
<td><span data-ttu-id="a4c3a-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-192">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="a4c3a-193">Unclassified</span></span></td>
<td><span data-ttu-id="a4c3a-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-194">10,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-196">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-196">CC099</span></span></td>
<td><span data-ttu-id="a4c3a-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-197">Default cost center</span></span></td>
<td><span data-ttu-id="a4c3a-198">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-198">10001</span></span></td>
<td><span data-ttu-id="a4c3a-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-199">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="a4c3a-200">Unclassified</span></span></td>
<td><span data-ttu-id="a4c3a-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-201">-10,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-203">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-203">CC099</span></span></td>
<td><span data-ttu-id="a4c3a-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-204">Default cost center</span></span></td>
<td><span data-ttu-id="a4c3a-205">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-205">10001</span></span></td>
<td><span data-ttu-id="a4c3a-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-206">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-207">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-208">1,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-210">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-210">CC099</span></span></td>
<td><span data-ttu-id="a4c3a-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-211">Default cost center</span></span></td>
<td><span data-ttu-id="a4c3a-212">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-212">10001</span></span></td>
<td><span data-ttu-id="a4c3a-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-213">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-214">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-215">9,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-217">További információért lásd: [Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="a4c3a-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="a4c3a-218">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="a4c3a-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="a4c3a-219">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="a4c3a-220">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="a4c3a-221">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="a4c3a-221">Define the cost distribution rule</span></span>

<span data-ttu-id="a4c3a-222">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="a4c3a-223">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="a4c3a-224">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="a4c3a-225">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="a4c3a-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="a4c3a-226">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="a4c3a-227">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-228">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-228">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="a4c3a-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-230">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-230">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-231">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-231">HR</span></span></td>
<td><span data-ttu-id="a4c3a-232">1000</span><span class="sxs-lookup"><span data-stu-id="a4c3a-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-233">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-233">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-234">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-234">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-235">6,000</span><span class="sxs-lookup"><span data-stu-id="a4c3a-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-236">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-236">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-237">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-237">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-238">0</span><span class="sxs-lookup"><span data-stu-id="a4c3a-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-239">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-240">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-240">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-241">Nagyság</span><span class="sxs-lookup"><span data-stu-id="a4c3a-241">Magnitude</span></span></th>
<th><span data-ttu-id="a4c3a-242">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="a4c3a-242">Allocation factor</span></span></th>
<th><span data-ttu-id="a4c3a-243">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-244">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-244">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-245">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-245">HR</span></span></td>
<td><span data-ttu-id="a4c3a-246">1000</span><span class="sxs-lookup"><span data-stu-id="a4c3a-246">1,000</span></span></td>
<td><span data-ttu-id="a4c3a-247">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="a4c3a-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-249">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-249">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-250">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-250">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-251">6,000</span><span class="sxs-lookup"><span data-stu-id="a4c3a-251">6,000</span></span></td>
<td><span data-ttu-id="a4c3a-252">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="a4c3a-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-254">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-254">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-255">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-255">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-256">0</span><span class="sxs-lookup"><span data-stu-id="a4c3a-256">0</span></span></td>
<td><span data-ttu-id="a4c3a-257">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-258">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-259">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="a4c3a-260">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: (Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-261">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-261">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-262">Receptúra</span><span class="sxs-lookup"><span data-stu-id="a4c3a-262">Formula</span></span></th>
<th><span data-ttu-id="a4c3a-263">Nagyság</span><span class="sxs-lookup"><span data-stu-id="a4c3a-263">Magnitude</span></span></th>
<th><span data-ttu-id="a4c3a-264">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="a4c3a-264">Allocation factor</span></span></th>
<th><span data-ttu-id="a4c3a-265">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-266">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-266">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-267">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-267">HR</span></span></td>
<td><span data-ttu-id="a4c3a-268">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a4c3a-269">1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-269">1</span></span></td>
<td><span data-ttu-id="a4c3a-270">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-271">500.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-272">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-272">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-273">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-273">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-274">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a4c3a-275">1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-275">1</span></span></td>
<td><span data-ttu-id="a4c3a-276">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-277">500.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-278">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-278">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-279">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-279">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-280">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="a4c3a-281">0</span><span class="sxs-lookup"><span data-stu-id="a4c3a-281">0</span></span></td>
<td><span data-ttu-id="a4c3a-282">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-283">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="a4c3a-284">Napló</span><span class="sxs-lookup"><span data-stu-id="a4c3a-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a4c3a-285">Napló</span><span class="sxs-lookup"><span data-stu-id="a4c3a-285">Journal</span></span></th>
<th><span data-ttu-id="a4c3a-286">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="a4c3a-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a4c3a-287">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a4c3a-288">Verzió</span><span class="sxs-lookup"><span data-stu-id="a4c3a-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-289">00002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-289">00002</span></span></td>
<td><span data-ttu-id="a4c3a-290">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="a4c3a-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="a4c3a-291">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="a4c3a-291">Fiscal</span></span></td>
<td><span data-ttu-id="a4c3a-292">2017</span><span class="sxs-lookup"><span data-stu-id="a4c3a-292">2017</span></span></td>
<td><span data-ttu-id="a4c3a-293">1. időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-293">Period 1</span></span></td>
<td><span data-ttu-id="a4c3a-294">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a4c3a-295">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a4c3a-296">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-297">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-298">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-298">Cost element</span></span></th>
<th><span data-ttu-id="a4c3a-299">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-299">Cost behavior</span></span></th>
<th><span data-ttu-id="a4c3a-300">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-301">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-302">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-302">CC099</span></span></td>
<td><span data-ttu-id="a4c3a-303">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-303">Default cost center</span></span></td>
<td><span data-ttu-id="a4c3a-304">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-304">10001</span></span></td>
<td><span data-ttu-id="a4c3a-305">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-305">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-306">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-306">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-308">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-309">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-309">CC099</span></span></td>
<td><span data-ttu-id="a4c3a-310">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-310">Default cost center</span></span></td>
<td><span data-ttu-id="a4c3a-311">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-311">10001</span></span></td>
<td><span data-ttu-id="a4c3a-312">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-312">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-313">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-313">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a4c3a-315">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="a4c3a-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-316">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-317">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-317">Cost element</span></span></th>
<th><span data-ttu-id="a4c3a-318">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-318">Cost behavior</span></span></th>
<th><span data-ttu-id="a4c3a-319">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-319">Amount</span></span></th>
<th><span data-ttu-id="a4c3a-320">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-321">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-321">CC099</span></span></td>
<td><span data-ttu-id="a4c3a-322">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-322">Default cost center</span></span></td>
<td><span data-ttu-id="a4c3a-323">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-323">10001</span></span></td>
<td><span data-ttu-id="a4c3a-324">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-324">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-325">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-325">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-326">-1,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-327">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-328">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-328">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-329">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-329">HR</span></span></td>
<td><span data-ttu-id="a4c3a-330">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-330">10001</span></span></td>
<td><span data-ttu-id="a4c3a-331">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-331">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-332">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-332">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-333">500.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-333">500.00</span></span></td>
<td><span data-ttu-id="a4c3a-334">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-335">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-335">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-336">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-336">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-337">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-337">10001</span></span></td>
<td><span data-ttu-id="a4c3a-338">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-338">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-339">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-339">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-340">500.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-340">500.00</span></span></td>
<td><span data-ttu-id="a4c3a-341">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-342">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-342">CC099</span></span></td>
<td><span data-ttu-id="a4c3a-343">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="a4c3a-343">Default cost center</span></span></td>
<td><span data-ttu-id="a4c3a-344">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-344">10001</span></span></td>
<td><span data-ttu-id="a4c3a-345">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-345">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-346">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-346">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-347">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-347">-9,000.00</span></span></td>
<td><span data-ttu-id="a4c3a-348">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-349">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-349">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-350">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-350">HR</span></span></td>
<td><span data-ttu-id="a4c3a-351">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-351">10001</span></span></td>
<td><span data-ttu-id="a4c3a-352">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-352">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-353">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-353">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="a4c3a-354">1,285.71</span></span></td>
<td><span data-ttu-id="a4c3a-355">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-356">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-356">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-357">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-357">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-358">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-358">10001</span></span></td>
<td><span data-ttu-id="a4c3a-359">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-359">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-360">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-360">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="a4c3a-361">7,714.29</span></span></td>
<td><span data-ttu-id="a4c3a-362">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-363">További információért lásd: [Költségelosztási irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="a4c3a-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="a4c3a-364">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="a4c3a-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="a4c3a-365">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="a4c3a-366">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="a4c3a-367">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="a4c3a-367">Define the overhead rate</span></span>

<span data-ttu-id="a4c3a-368">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="a4c3a-369">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-370">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-370">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-371">óra</span><span class="sxs-lookup"><span data-stu-id="a4c3a-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-372">Proj 1</span></span></td>
<td><span data-ttu-id="a4c3a-373">1. projekt</span><span class="sxs-lookup"><span data-stu-id="a4c3a-373">Project 1</span></span></td>
<td><span data-ttu-id="a4c3a-374">3</span><span class="sxs-lookup"><span data-stu-id="a4c3a-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-375">Proj 2</span></span></td>
<td><span data-ttu-id="a4c3a-376">2. projekt</span><span class="sxs-lookup"><span data-stu-id="a4c3a-376">Project 2</span></span></td>
<td><span data-ttu-id="a4c3a-377">1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-378">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-379">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-379">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-380">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-380">Cost element</span></span></th>
<th><span data-ttu-id="a4c3a-381">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-381">Cost behavior</span></span></th>
<th><span data-ttu-id="a4c3a-382">Egységek</span><span class="sxs-lookup"><span data-stu-id="a4c3a-382">Units</span></span></th>
<th><span data-ttu-id="a4c3a-383">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="a4c3a-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-384">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-384">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-385">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-385">HR</span></span></td>
<td><span data-ttu-id="a4c3a-386">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-386">10001</span></span></td>
<td><span data-ttu-id="a4c3a-387">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-387">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-388">1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-388">1</span></span></td>
<td><span data-ttu-id="a4c3a-389">10</span><span class="sxs-lookup"><span data-stu-id="a4c3a-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-390">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-391">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-391">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-392">Nagyság</span><span class="sxs-lookup"><span data-stu-id="a4c3a-392">Magnitude</span></span></th>
<th><span data-ttu-id="a4c3a-393">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-393">Cost element</span></span></th>
<th><span data-ttu-id="a4c3a-394">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="a4c3a-394">Allocation factor</span></span></th>
<th><span data-ttu-id="a4c3a-395">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-396">Proj 1</span></span></td>
<td><span data-ttu-id="a4c3a-397">1. projekt</span><span class="sxs-lookup"><span data-stu-id="a4c3a-397">Project 1</span></span></td>
<td><span data-ttu-id="a4c3a-398">3</span><span class="sxs-lookup"><span data-stu-id="a4c3a-398">3</span></span></td>
<td><span data-ttu-id="a4c3a-399">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-399">10001</span></span></td>
<td><span data-ttu-id="a4c3a-400">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="a4c3a-401">30.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-402">Proj 2</span></span></td>
<td><span data-ttu-id="a4c3a-403">2. projekt</span><span class="sxs-lookup"><span data-stu-id="a4c3a-403">Project 2</span></span></td>
<td><span data-ttu-id="a4c3a-404">1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-404">1</span></span></td>
<td><span data-ttu-id="a4c3a-405">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-405">10001</span></span></td>
<td><span data-ttu-id="a4c3a-406">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="a4c3a-407">10.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="a4c3a-408">Napló</span><span class="sxs-lookup"><span data-stu-id="a4c3a-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a4c3a-409">Napló</span><span class="sxs-lookup"><span data-stu-id="a4c3a-409">Journal</span></span></th>
<th><span data-ttu-id="a4c3a-410">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="a4c3a-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a4c3a-411">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a4c3a-412">Verzió</span><span class="sxs-lookup"><span data-stu-id="a4c3a-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-413">00003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-413">00003</span></span></td>
<td><span data-ttu-id="a4c3a-414">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="a4c3a-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="a4c3a-415">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="a4c3a-415">Fiscal</span></span></td>
<td><span data-ttu-id="a4c3a-416">2017</span><span class="sxs-lookup"><span data-stu-id="a4c3a-416">2017</span></span></td>
<td><span data-ttu-id="a4c3a-417">1. időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-417">Period 1</span></span></td>
<td><span data-ttu-id="a4c3a-418">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="a4c3a-419">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a4c3a-420">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-421">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-421">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-422">Nagyság</span><span class="sxs-lookup"><span data-stu-id="a4c3a-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-423">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-424">Proj 1</span></span></td>
<td><span data-ttu-id="a4c3a-425">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="a4c3a-426">3,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-427">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-428">Proj 2</span></span></td>
<td><span data-ttu-id="a4c3a-429">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="a4c3a-430">1.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a4c3a-431">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="a4c3a-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-432">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-433">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-433">Cost element</span></span></th>
<th><span data-ttu-id="a4c3a-434">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-434">Cost behavior</span></span></th>
<th><span data-ttu-id="a4c3a-435">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-435">Amount</span></span></th>
<th><span data-ttu-id="a4c3a-436">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-437">CC0001</span></span></td>
<td><span data-ttu-id="a4c3a-438">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-438">HR</span></span></td>
<td><span data-ttu-id="a4c3a-439">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-439">10001</span></span></td>
<td><span data-ttu-id="a4c3a-440">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-440">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-441">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-441">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-442">-30.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-442">-30.00</span></span></td>
<td><span data-ttu-id="a4c3a-443">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-444">Proj 1</span></span></td>
<td><span data-ttu-id="a4c3a-445">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="a4c3a-446">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-446">10001</span></span></td>
<td><span data-ttu-id="a4c3a-447">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-447">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-448">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-448">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-449">30.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-449">30.00</span></span></td>
<td><span data-ttu-id="a4c3a-450">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-451">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-451">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-452">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-452">HR</span></span></td>
<td><span data-ttu-id="a4c3a-453">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-453">10001</span></span></td>
<td><span data-ttu-id="a4c3a-454">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-454">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-455">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-455">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-456">-10.00</span></span></td>
<td><span data-ttu-id="a4c3a-457">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-458">Proj 2</span></span></td>
<td><span data-ttu-id="a4c3a-459">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="a4c3a-460">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-460">10001</span></span></td>
<td><span data-ttu-id="a4c3a-461">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-461">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-462">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-462">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-463">10,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-463">10.00</span></span></td>
<td><span data-ttu-id="a4c3a-464">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-465">További információ: [Járulékosköltség-számítás végrehajtása](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="a4c3a-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="a4c3a-466">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="a4c3a-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="a4c3a-467">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="a4c3a-468">A Finance and Operations a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="a4c3a-469">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="a4c3a-470">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="a4c3a-471">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="a4c3a-472">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="a4c3a-473">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="a4c3a-474">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="a4c3a-475">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="a4c3a-475">Define the cost allocation</span></span>

<span data-ttu-id="a4c3a-476">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="a4c3a-477">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="a4c3a-478">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-479">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-479">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-480">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="a4c3a-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-481">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-481">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-482">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-482">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-483">35</span><span class="sxs-lookup"><span data-stu-id="a4c3a-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-484">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-484">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-485">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-485">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-486">55</span><span class="sxs-lookup"><span data-stu-id="a4c3a-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-487">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-487">CC004</span></span></td>
<td><span data-ttu-id="a4c3a-488">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-488">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-489">10</span><span class="sxs-lookup"><span data-stu-id="a4c3a-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-490">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="a4c3a-491">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-492">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-492">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-493">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="a4c3a-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-494">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-494">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-495">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-495">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-496">65</span><span class="sxs-lookup"><span data-stu-id="a4c3a-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-497">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-497">CC004</span></span></td>
<td><span data-ttu-id="a4c3a-498">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-498">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-499">35</span><span class="sxs-lookup"><span data-stu-id="a4c3a-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-500">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="a4c3a-501">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-502">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-502">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-503">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-504">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-504">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-505">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-505">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-506">60</span><span class="sxs-lookup"><span data-stu-id="a4c3a-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-507">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-507">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-508">2. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-508">Product 2</span></span></td>
<td><span data-ttu-id="a4c3a-509">20</span><span class="sxs-lookup"><span data-stu-id="a4c3a-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-510">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="a4c3a-511">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-512">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-512">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-513">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-514">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-514">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-515">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-515">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-516">80</span><span class="sxs-lookup"><span data-stu-id="a4c3a-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-517">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-517">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-518">2. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-518">Product 2</span></span></td>
<td><span data-ttu-id="a4c3a-519">15.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="a4c3a-520">A Finance and Operations esetében a statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="a4c3a-521">További információk: [Statisztikaimérték-szolgáltató sablon](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="a4c3a-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="a4c3a-522">Az alábbi táblázat azt az eredményt mutatja, amikor a HR szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-523">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-523">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-524">Nagyság</span><span class="sxs-lookup"><span data-stu-id="a4c3a-524">Magnitude</span></span></th>
<th><span data-ttu-id="a4c3a-525">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="a4c3a-525">Allocation factor</span></span></th>
<th><span data-ttu-id="a4c3a-526">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-526">Amount</span></span></th>
<th><span data-ttu-id="a4c3a-527">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-528">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-528">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-529">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-529">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-530">35</span><span class="sxs-lookup"><span data-stu-id="a4c3a-530">35</span></span></td>
<td><span data-ttu-id="a4c3a-531">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a4c3a-532">175.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-532">175.00</span></span></td>
<td><span data-ttu-id="a4c3a-533">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-534">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-534">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-535">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-535">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-536">55</span><span class="sxs-lookup"><span data-stu-id="a4c3a-536">55</span></span></td>
<td><span data-ttu-id="a4c3a-537">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a4c3a-538">275.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-538">275.00</span></span></td>
<td><span data-ttu-id="a4c3a-539">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-540">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-540">CC004</span></span></td>
<td><span data-ttu-id="a4c3a-541">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-541">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-542">10</span><span class="sxs-lookup"><span data-stu-id="a4c3a-542">10</span></span></td>
<td><span data-ttu-id="a4c3a-543">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="a4c3a-544">50,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-544">50.00</span></span></td>
<td><span data-ttu-id="a4c3a-545">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-546">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-546">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-547">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-547">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-548">35</span><span class="sxs-lookup"><span data-stu-id="a4c3a-548">35</span></span></td>
<td><span data-ttu-id="a4c3a-549">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="a4c3a-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a4c3a-550">436.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-550">436.00</span></span></td>
<td><span data-ttu-id="a4c3a-551">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-552">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-552">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-553">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-553">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-554">55</span><span class="sxs-lookup"><span data-stu-id="a4c3a-554">55</span></span></td>
<td><span data-ttu-id="a4c3a-555">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="a4c3a-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a4c3a-556">685.14</span><span class="sxs-lookup"><span data-stu-id="a4c3a-556">685.14</span></span></td>
<td><span data-ttu-id="a4c3a-557">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-558">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-558">CC004</span></span></td>
<td><span data-ttu-id="a4c3a-559">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-559">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-560">10</span><span class="sxs-lookup"><span data-stu-id="a4c3a-560">10</span></span></td>
<td><span data-ttu-id="a4c3a-561">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="a4c3a-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="a4c3a-562">124.57</span><span class="sxs-lookup"><span data-stu-id="a4c3a-562">124.57</span></span></td>
<td><span data-ttu-id="a4c3a-563">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-564">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-565">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-565">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-566">Nagyság</span><span class="sxs-lookup"><span data-stu-id="a4c3a-566">Magnitude</span></span></th>
<th><span data-ttu-id="a4c3a-567">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="a4c3a-567">Allocation factor</span></span></th>
<th><span data-ttu-id="a4c3a-568">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-568">Amount</span></span></th>
<th><span data-ttu-id="a4c3a-569">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-570">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-570">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-571">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-571">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-572">65</span><span class="sxs-lookup"><span data-stu-id="a4c3a-572">65</span></span></td>
<td><span data-ttu-id="a4c3a-573">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="a4c3a-574">438.75</span><span class="sxs-lookup"><span data-stu-id="a4c3a-574">438.75</span></span></td>
<td><span data-ttu-id="a4c3a-575">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-576">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-576">CC004</span></span></td>
<td><span data-ttu-id="a4c3a-577">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-577">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-578">35</span><span class="sxs-lookup"><span data-stu-id="a4c3a-578">35</span></span></td>
<td><span data-ttu-id="a4c3a-579">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="a4c3a-580">236.25</span><span class="sxs-lookup"><span data-stu-id="a4c3a-580">236.25</span></span></td>
<td><span data-ttu-id="a4c3a-581">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-582">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-582">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-583">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-583">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-584">65</span><span class="sxs-lookup"><span data-stu-id="a4c3a-584">65</span></span></td>
<td><span data-ttu-id="a4c3a-585">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="a4c3a-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="a4c3a-586">5,297.69</span></span></td>
<td><span data-ttu-id="a4c3a-587">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-588">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-588">CC004</span></span></td>
<td><span data-ttu-id="a4c3a-589">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-589">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-590">35</span><span class="sxs-lookup"><span data-stu-id="a4c3a-590">35</span></span></td>
<td><span data-ttu-id="a4c3a-591">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="a4c3a-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="a4c3a-592">2,852.60</span></span></td>
<td><span data-ttu-id="a4c3a-593">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-594">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-595">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-595">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-596">Nagyság</span><span class="sxs-lookup"><span data-stu-id="a4c3a-596">Magnitude</span></span></th>
<th><span data-ttu-id="a4c3a-597">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="a4c3a-597">Allocation factor</span></span></th>
<th><span data-ttu-id="a4c3a-598">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-598">Amount</span></span></th>
<th><span data-ttu-id="a4c3a-599">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-600">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-600">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-601">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-601">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-602">60</span><span class="sxs-lookup"><span data-stu-id="a4c3a-602">60</span></span></td>
<td><span data-ttu-id="a4c3a-603">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="a4c3a-604">535.31</span><span class="sxs-lookup"><span data-stu-id="a4c3a-604">535.31</span></span></td>
<td><span data-ttu-id="a4c3a-605">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-606">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-606">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-607">2. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-607">Product 2</span></span></td>
<td><span data-ttu-id="a4c3a-608">20</span><span class="sxs-lookup"><span data-stu-id="a4c3a-608">20</span></span></td>
<td><span data-ttu-id="a4c3a-609">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="a4c3a-610">178.44</span><span class="sxs-lookup"><span data-stu-id="a4c3a-610">178.44</span></span></td>
<td><span data-ttu-id="a4c3a-611">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-612">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-612">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-613">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-613">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-614">60</span><span class="sxs-lookup"><span data-stu-id="a4c3a-614">60</span></span></td>
<td><span data-ttu-id="a4c3a-615">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="a4c3a-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="a4c3a-616">4,487.12</span></span></td>
<td><span data-ttu-id="a4c3a-617">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-618">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-618">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-619">2. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-619">Product 2</span></span></td>
<td><span data-ttu-id="a4c3a-620">20</span><span class="sxs-lookup"><span data-stu-id="a4c3a-620">20</span></span></td>
<td><span data-ttu-id="a4c3a-621">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="a4c3a-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="a4c3a-622">1,495.71</span></span></td>
<td><span data-ttu-id="a4c3a-623">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a4c3a-624">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-625">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-625">Cost object</span></span></th>
<th><span data-ttu-id="a4c3a-626">Nagyság</span><span class="sxs-lookup"><span data-stu-id="a4c3a-626">Magnitude</span></span></th>
<th><span data-ttu-id="a4c3a-627">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="a4c3a-627">Allocation factor</span></span></th>
<th><span data-ttu-id="a4c3a-628">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-628">Amount</span></span></th>
<th><span data-ttu-id="a4c3a-629">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-630">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-630">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-631">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-631">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-632">80</span><span class="sxs-lookup"><span data-stu-id="a4c3a-632">80</span></span></td>
<td><span data-ttu-id="a4c3a-633">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="a4c3a-634">241.05</span><span class="sxs-lookup"><span data-stu-id="a4c3a-634">241.05</span></span></td>
<td><span data-ttu-id="a4c3a-635">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-636">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-636">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-637">2. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-637">Product 2</span></span></td>
<td><span data-ttu-id="a4c3a-638">15.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-638">15</span></span></td>
<td><span data-ttu-id="a4c3a-639">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="a4c3a-640">45.20</span><span class="sxs-lookup"><span data-stu-id="a4c3a-640">45.20</span></span></td>
<td><span data-ttu-id="a4c3a-641">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-642">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-642">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-643">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-643">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-644">80</span><span class="sxs-lookup"><span data-stu-id="a4c3a-644">80</span></span></td>
<td><span data-ttu-id="a4c3a-645">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="a4c3a-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="a4c3a-646">2,507.09</span></span></td>
<td><span data-ttu-id="a4c3a-647">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-648">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-648">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-649">2. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-649">Product 2</span></span></td>
<td><span data-ttu-id="a4c3a-650">15.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-650">15</span></span></td>
<td><span data-ttu-id="a4c3a-651">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="a4c3a-652">470.08</span><span class="sxs-lookup"><span data-stu-id="a4c3a-652">470.08</span></span></td>
<td><span data-ttu-id="a4c3a-653">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="a4c3a-654">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="a4c3a-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a4c3a-655">Napló</span><span class="sxs-lookup"><span data-stu-id="a4c3a-655">Journal</span></span></th>
<th><span data-ttu-id="a4c3a-656">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="a4c3a-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="a4c3a-657">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="a4c3a-658">Verzió</span><span class="sxs-lookup"><span data-stu-id="a4c3a-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-659">00004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-659">00004</span></span></td>
<td><span data-ttu-id="a4c3a-660">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="a4c3a-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="a4c3a-661">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="a4c3a-661">Fiscal</span></span></td>
<td><span data-ttu-id="a4c3a-662">2017</span><span class="sxs-lookup"><span data-stu-id="a4c3a-662">2017</span></span></td>
<td><span data-ttu-id="a4c3a-663">1. időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-663">Period 1</span></span></td>
<td><span data-ttu-id="a4c3a-664">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="a4c3a-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="a4c3a-665">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="a4c3a-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="a4c3a-666">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-667">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-668">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-668">Cost element</span></span></th>
<th><span data-ttu-id="a4c3a-669">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-669">Cost behavior</span></span></th>
<th><span data-ttu-id="a4c3a-670">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-671">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-672">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-672">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-673">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-673">HR</span></span></td>
<td><span data-ttu-id="a4c3a-674">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-674">10001</span></span></td>
<td><span data-ttu-id="a4c3a-675">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-675">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-676">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-676">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-677">500.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-678">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-679">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-679">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-680">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-680">HR</span></span></td>
<td><span data-ttu-id="a4c3a-681">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-681">10001</span></span></td>
<td><span data-ttu-id="a4c3a-682">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-682">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-683">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-683">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="a4c3a-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-685">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-686">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-686">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-687">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-687">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-688">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-688">10001</span></span></td>
<td><span data-ttu-id="a4c3a-689">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-689">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-690">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-690">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-691">675.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-692">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-693">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-693">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-694">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-694">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-695">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-695">10001</span></span></td>
<td><span data-ttu-id="a4c3a-696">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-696">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-697">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-697">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="a4c3a-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-699">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-700">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-700">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-701">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-701">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-702">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-702">10001</span></span></td>
<td><span data-ttu-id="a4c3a-703">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-703">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-704">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-704">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-705">713.75</span><span class="sxs-lookup"><span data-stu-id="a4c3a-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-706">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-707">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-707">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-708">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-708">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-709">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-709">10001</span></span></td>
<td><span data-ttu-id="a4c3a-710">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-710">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-711">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-711">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="a4c3a-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-713">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-714">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-714">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-715">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-715">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-716">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-716">10001</span></span></td>
<td><span data-ttu-id="a4c3a-717">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-717">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-718">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-718">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-719">286.25</span><span class="sxs-lookup"><span data-stu-id="a4c3a-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-720">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-721">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-721">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-722">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-722">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-723">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-723">10001</span></span></td>
<td><span data-ttu-id="a4c3a-724">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-724">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-725">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-725">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="a4c3a-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-727">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-728">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-728">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-729">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-729">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-730">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-730">10001</span></span></td>
<td><span data-ttu-id="a4c3a-731">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-731">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-732">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-732">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-733">776.36</span><span class="sxs-lookup"><span data-stu-id="a4c3a-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-734">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-735">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-735">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-736">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-736">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-737">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-737">10001</span></span></td>
<td><span data-ttu-id="a4c3a-738">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-738">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-739">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-739">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="a4c3a-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-741">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-742">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-742">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-743">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-743">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-744">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-744">10001</span></span></td>
<td><span data-ttu-id="a4c3a-745">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-745">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-746">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-746">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-747">223.64</span><span class="sxs-lookup"><span data-stu-id="a4c3a-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-748">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="a4c3a-749">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-749">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-750">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-750">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-751">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-751">10001</span></span></td>
<td><span data-ttu-id="a4c3a-752">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-752">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-753">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-753">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="a4c3a-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="a4c3a-755">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="a4c3a-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="a4c3a-756">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="a4c3a-757">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-757">Cost element</span></span></th>
<th><span data-ttu-id="a4c3a-758">Költség működése</span><span class="sxs-lookup"><span data-stu-id="a4c3a-758">Cost behavior</span></span></th>
<th><span data-ttu-id="a4c3a-759">Összeg</span><span class="sxs-lookup"><span data-stu-id="a4c3a-759">Amount</span></span></th>
<th><span data-ttu-id="a4c3a-760">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="a4c3a-761">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-761">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-762">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-762">HR</span></span></td>
<td><span data-ttu-id="a4c3a-763">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-763">10001</span></span></td>
<td><span data-ttu-id="a4c3a-764">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-764">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-765">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-765">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-766">-500.00</span></span></td>
<td><span data-ttu-id="a4c3a-767">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-768">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-768">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-769">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-769">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-770">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-770">10001</span></span></td>
<td><span data-ttu-id="a4c3a-771">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-771">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-772">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-772">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-773">175.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-773">175.00</span></span></td>
<td><span data-ttu-id="a4c3a-774">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-775">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-775">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-776">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-776">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-777">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-777">10001</span></span></td>
<td><span data-ttu-id="a4c3a-778">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-778">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-779">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-779">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-780">275.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-780">275.00</span></span></td>
<td><span data-ttu-id="a4c3a-781">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-782">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-782">CC004</span></span></td>
<td><span data-ttu-id="a4c3a-783">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-783">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-784">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-784">10001</span></span></td>
<td><span data-ttu-id="a4c3a-785">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-785">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-786">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-786">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-787">50,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-787">50,00</span></span></td>
<td><span data-ttu-id="a4c3a-788">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-789">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-789">CC001</span></span></td>
<td><span data-ttu-id="a4c3a-790">HR</span><span class="sxs-lookup"><span data-stu-id="a4c3a-790">HR</span></span></td>
<td><span data-ttu-id="a4c3a-791">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-791">10001</span></span></td>
<td><span data-ttu-id="a4c3a-792">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-792">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-793">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-793">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-794">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="a4c3a-794">-1,245.71</span></span></td>
<td><span data-ttu-id="a4c3a-795">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-796">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-796">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-797">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-797">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-798">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-798">10001</span></span></td>
<td><span data-ttu-id="a4c3a-799">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-799">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-800">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-800">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-801">436.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-801">436.00</span></span></td>
<td><span data-ttu-id="a4c3a-802">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-803">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-803">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-804">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-804">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-805">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-805">10001</span></span></td>
<td><span data-ttu-id="a4c3a-806">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-806">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-807">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-807">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-808">685.14</span><span class="sxs-lookup"><span data-stu-id="a4c3a-808">685.14</span></span></td>
<td><span data-ttu-id="a4c3a-809">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-810">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-810">CC004</span></span></td>
<td><span data-ttu-id="a4c3a-811">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-811">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-812">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-812">10001</span></span></td>
<td><span data-ttu-id="a4c3a-813">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-813">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-814">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-814">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-815">124.57</span><span class="sxs-lookup"><span data-stu-id="a4c3a-815">124.57</span></span></td>
<td><span data-ttu-id="a4c3a-816">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-817">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-817">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-818">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-818">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-819">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-819">10001</span></span></td>
<td><span data-ttu-id="a4c3a-820">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-820">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-821">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-821">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-822">-675.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-822">-675.00</span></span></td>
<td><span data-ttu-id="a4c3a-823">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-824">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-824">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-825">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-825">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-826">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-826">10001</span></span></td>
<td><span data-ttu-id="a4c3a-827">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-827">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-828">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-828">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-829">438.75</span><span class="sxs-lookup"><span data-stu-id="a4c3a-829">438.75</span></span></td>
<td><span data-ttu-id="a4c3a-830">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-831">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-831">CC004</span></span></td>
<td><span data-ttu-id="a4c3a-832">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-832">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-833">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-833">10001</span></span></td>
<td><span data-ttu-id="a4c3a-834">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-834">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-835">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-835">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-836">236.25</span><span class="sxs-lookup"><span data-stu-id="a4c3a-836">236.25</span></span></td>
<td><span data-ttu-id="a4c3a-837">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-838">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-838">CC002</span></span></td>
<td><span data-ttu-id="a4c3a-839">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="a4c3a-839">Finance</span></span></td>
<td><span data-ttu-id="a4c3a-840">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-840">10001</span></span></td>
<td><span data-ttu-id="a4c3a-841">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-841">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-842">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-842">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-843">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="a4c3a-843">-8,150.29</span></span></td>
<td><span data-ttu-id="a4c3a-844">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-845">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-845">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-846">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-846">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-847">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-847">10001</span></span></td>
<td><span data-ttu-id="a4c3a-848">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-848">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-849">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-849">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="a4c3a-850">5,297.69</span></span></td>
<td><span data-ttu-id="a4c3a-851">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-852">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-852">CC004</span></span></td>
<td><span data-ttu-id="a4c3a-853">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="a4c3a-853">Packaging</span></span></td>
<td><span data-ttu-id="a4c3a-854">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-854">10001</span></span></td>
<td><span data-ttu-id="a4c3a-855">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-855">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-856">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-856">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="a4c3a-857">2,852.60</span></span></td>
<td><span data-ttu-id="a4c3a-858">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-859">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-859">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-860">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-860">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-861">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-861">10001</span></span></td>
<td><span data-ttu-id="a4c3a-862">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-862">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-863">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-863">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-864">-713.75</span><span class="sxs-lookup"><span data-stu-id="a4c3a-864">-713.75</span></span></td>
<td><span data-ttu-id="a4c3a-865">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-866">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-866">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-867">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-867">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-868">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-868">10001</span></span></td>
<td><span data-ttu-id="a4c3a-869">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-869">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-870">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-870">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-871">535.31</span><span class="sxs-lookup"><span data-stu-id="a4c3a-871">535.31</span></span></td>
<td><span data-ttu-id="a4c3a-872">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-873">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-873">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-874">2. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-874">Product 2</span></span></td>
<td><span data-ttu-id="a4c3a-875">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-875">10001</span></span></td>
<td><span data-ttu-id="a4c3a-876">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-876">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-877">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-877">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-878">178.44</span><span class="sxs-lookup"><span data-stu-id="a4c3a-878">178.44</span></span></td>
<td><span data-ttu-id="a4c3a-879">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-880">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-880">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-881">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-881">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-882">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-882">10001</span></span></td>
<td><span data-ttu-id="a4c3a-883">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-883">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-884">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-884">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-885">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="a4c3a-885">-5,982.83</span></span></td>
<td><span data-ttu-id="a4c3a-886">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-887">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-887">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-888">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-888">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-889">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-889">10001</span></span></td>
<td><span data-ttu-id="a4c3a-890">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-890">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-891">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-891">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="a4c3a-892">4,487.12</span></span></td>
<td><span data-ttu-id="a4c3a-893">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-894">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-894">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-895">2. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-895">Product 2</span></span></td>
<td><span data-ttu-id="a4c3a-896">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-896">10001</span></span></td>
<td><span data-ttu-id="a4c3a-897">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-897">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-898">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-898">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="a4c3a-899">1,495.71</span></span></td>
<td><span data-ttu-id="a4c3a-900">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-901">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-901">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-902">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-902">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-903">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-903">10001</span></span></td>
<td><span data-ttu-id="a4c3a-904">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-904">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-905">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-905">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-906">-286.25</span><span class="sxs-lookup"><span data-stu-id="a4c3a-906">-286.25</span></span></td>
<td><span data-ttu-id="a4c3a-907">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-908">Term 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-908">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-909">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-909">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-910">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-910">10001</span></span></td>
<td><span data-ttu-id="a4c3a-911">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-911">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-912">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-912">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-913">241.05</span><span class="sxs-lookup"><span data-stu-id="a4c3a-913">241.05</span></span></td>
<td><span data-ttu-id="a4c3a-914">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-915">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-915">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-916">2. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-916">Product 2</span></span></td>
<td><span data-ttu-id="a4c3a-917">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-917">10001</span></span></td>
<td><span data-ttu-id="a4c3a-918">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-918">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-919">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-919">Fixed cost</span></span></td>
<td><span data-ttu-id="a4c3a-920">45.20</span><span class="sxs-lookup"><span data-stu-id="a4c3a-920">45.20</span></span></td>
<td><span data-ttu-id="a4c3a-921">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-922">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-922">CC003</span></span></td>
<td><span data-ttu-id="a4c3a-923">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="a4c3a-923">Assembly</span></span></td>
<td><span data-ttu-id="a4c3a-924">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-924">10001</span></span></td>
<td><span data-ttu-id="a4c3a-925">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-925">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-926">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-926">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-927">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="a4c3a-927">-2,977.17</span></span></td>
<td><span data-ttu-id="a4c3a-928">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-929">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-929">Prod 1</span></span></td>
<td><span data-ttu-id="a4c3a-930">1. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-930">Product 1</span></span></td>
<td><span data-ttu-id="a4c3a-931">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-931">10001</span></span></td>
<td><span data-ttu-id="a4c3a-932">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-932">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-933">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-933">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="a4c3a-934">2,507.09</span></span></td>
<td><span data-ttu-id="a4c3a-935">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="a4c3a-936">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-936">Prod 2</span></span></td>
<td><span data-ttu-id="a4c3a-937">2. termék</span><span class="sxs-lookup"><span data-stu-id="a4c3a-937">Product 2</span></span></td>
<td><span data-ttu-id="a4c3a-938">10001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-938">10001</span></span></td>
<td><span data-ttu-id="a4c3a-939">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-939">Electricity</span></span></td>
<td><span data-ttu-id="a4c3a-940">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-940">Variable cost</span></span></td>
<td><span data-ttu-id="a4c3a-941">470.08</span><span class="sxs-lookup"><span data-stu-id="a4c3a-941">470.08</span></span></td>
<td><span data-ttu-id="a4c3a-942">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="a4c3a-943">Következtetés</span><span class="sxs-lookup"><span data-stu-id="a4c3a-943">Conclusion</span></span>
<span data-ttu-id="a4c3a-944">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="a4c3a-945">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="a4c3a-946">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="a4c3a-947">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="a4c3a-948">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="a4c3a-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="a4c3a-949">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="a4c3a-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="a4c3a-950">Összesen</span><span class="sxs-lookup"><span data-stu-id="a4c3a-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a4c3a-951">CC099</span><span class="sxs-lookup"><span data-stu-id="a4c3a-951">CC099</span></span></th>
<th><span data-ttu-id="a4c3a-952">CC001</span><span class="sxs-lookup"><span data-stu-id="a4c3a-952">CC001</span></span></th>
<th><span data-ttu-id="a4c3a-953">CC002</span><span class="sxs-lookup"><span data-stu-id="a4c3a-953">CC002</span></span></th>
<th><span data-ttu-id="a4c3a-954">CC003</span><span class="sxs-lookup"><span data-stu-id="a4c3a-954">CC003</span></span></th>
<th><span data-ttu-id="a4c3a-955">CC004</span><span class="sxs-lookup"><span data-stu-id="a4c3a-955">CC004</span></span></th>
<th><span data-ttu-id="a4c3a-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-956">Proj 1</span></span></th>
<th><span data-ttu-id="a4c3a-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-957">Proj 2</span></span></th>
<th><span data-ttu-id="a4c3a-958">Term. 1</span><span class="sxs-lookup"><span data-stu-id="a4c3a-958">Prod 1</span></span></th>
<th><span data-ttu-id="a4c3a-959">Term. 2</span><span class="sxs-lookup"><span data-stu-id="a4c3a-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="a4c3a-960">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="a4c3a-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="a4c3a-970">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="a4c3a-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-971">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="a4c3a-972">Fix költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-973">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-974">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-975">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-976">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-977">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-978">776.36</span><span class="sxs-lookup"><span data-stu-id="a4c3a-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-979">223.64</span><span class="sxs-lookup"><span data-stu-id="a4c3a-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="a4c3a-981">Változó költség</span><span class="sxs-lookup"><span data-stu-id="a4c3a-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-982">000</span><span class="sxs-lookup"><span data-stu-id="a4c3a-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-983">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-984">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-985">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-986">0,00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-987">30.00</span><span class="sxs-lookup"><span data-stu-id="a4c3a-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-988">1000</span><span class="sxs-lookup"><span data-stu-id="a4c3a-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="a4c3a-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="a4c3a-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="a4c3a-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="a4c3a-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="a4c3a-992">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="a4c3a-993">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="a4c3a-994">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="a4c3a-995">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="a4c3a-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="a4c3a-996">Részletesebb tájékoztatás: [Költségösszesítési irányelv](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="a4c3a-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>



