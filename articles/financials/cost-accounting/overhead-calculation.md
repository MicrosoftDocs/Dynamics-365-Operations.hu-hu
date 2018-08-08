---
title: "Járulékos költség számítása"
description: "Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: be548959985a6fcaabf482f1e5951024633283cf
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="ee9f3-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="ee9f3-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee9f3-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="ee9f3-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="ee9f3-105">Term definition</span></span>
---------------

<span data-ttu-id="ee9f3-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="ee9f3-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="ee9f3-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="ee9f3-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="ee9f3-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="ee9f3-109">Rent</span></span>
-   <span data-ttu-id="ee9f3-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-110">Electricity</span></span>
-   <span data-ttu-id="ee9f3-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="ee9f3-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="ee9f3-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-112">Overhead calculation overview</span></span>
<span data-ttu-id="ee9f3-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="ee9f3-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="ee9f3-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="ee9f3-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="ee9f3-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="ee9f3-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="ee9f3-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="ee9f3-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="ee9f3-119">Version type</span></span>
-   <span data-ttu-id="ee9f3-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-120">Date and time</span></span>
-   <span data-ttu-id="ee9f3-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="ee9f3-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="ee9f3-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="ee9f3-122">Fiscal year</span></span>
-   <span data-ttu-id="ee9f3-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-123">Fiscal period</span></span>

<span data-ttu-id="ee9f3-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="ee9f3-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="ee9f3-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="ee9f3-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="ee9f3-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="ee9f3-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="ee9f3-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="ee9f3-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="ee9f3-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="ee9f3-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="ee9f3-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="ee9f3-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="ee9f3-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="ee9f3-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="ee9f3-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ee9f3-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="ee9f3-140">Main account</span></span></th>
<th><span data-ttu-id="ee9f3-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="ee9f3-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-143">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-143">CC099</span></span></td>
<td><span data-ttu-id="ee9f3-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-144">Default cost center</span></span></td>
<td><span data-ttu-id="ee9f3-145">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-145">10001</span></span></td>
<td><span data-ttu-id="ee9f3-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-146">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="ee9f3-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ee9f3-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="ee9f3-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="ee9f3-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="ee9f3-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="ee9f3-151">Define the cost behavior rule</span></span>

<span data-ttu-id="ee9f3-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="ee9f3-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="ee9f3-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="ee9f3-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="ee9f3-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="ee9f3-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="ee9f3-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="ee9f3-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="ee9f3-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="ee9f3-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="ee9f3-159">Napló</span><span class="sxs-lookup"><span data-stu-id="ee9f3-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ee9f3-160">Napló</span><span class="sxs-lookup"><span data-stu-id="ee9f3-160">Journal</span></span></th>
<th><span data-ttu-id="ee9f3-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="ee9f3-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ee9f3-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ee9f3-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="ee9f3-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-164">00001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-164">00001</span></span></td>
<td><span data-ttu-id="ee9f3-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="ee9f3-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="ee9f3-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="ee9f3-166">Fiscal</span></span></td>
<td><span data-ttu-id="ee9f3-167">2017</span><span class="sxs-lookup"><span data-stu-id="ee9f3-167">2017</span></span></td>
<td><span data-ttu-id="ee9f3-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-168">Period 1</span></span></td>
<td><span data-ttu-id="ee9f3-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ee9f3-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ee9f3-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-173">Cost element</span></span></th>
<th><span data-ttu-id="ee9f3-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-174">Cost behavior</span></span></th>
<th><span data-ttu-id="ee9f3-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-177">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-177">CC099</span></span></td>
<td><span data-ttu-id="ee9f3-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-178">Default cost center</span></span></td>
<td><span data-ttu-id="ee9f3-179">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-179">10001</span></span></td>
<td><span data-ttu-id="ee9f3-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-180">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="ee9f3-181">Unclassified</span></span></td>
<td><span data-ttu-id="ee9f3-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ee9f3-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="ee9f3-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-185">Cost element</span></span></th>
<th><span data-ttu-id="ee9f3-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-186">Cost behavior</span></span></th>
<th><span data-ttu-id="ee9f3-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-187">Amount</span></span></th>
<th><span data-ttu-id="ee9f3-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-189">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-189">CC099</span></span></td>
<td><span data-ttu-id="ee9f3-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-190">Default cost center</span></span></td>
<td><span data-ttu-id="ee9f3-191">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-191">10001</span></span></td>
<td><span data-ttu-id="ee9f3-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-192">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="ee9f3-193">Unclassified</span></span></td>
<td><span data-ttu-id="ee9f3-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-194">10,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-196">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-196">CC099</span></span></td>
<td><span data-ttu-id="ee9f3-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-197">Default cost center</span></span></td>
<td><span data-ttu-id="ee9f3-198">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-198">10001</span></span></td>
<td><span data-ttu-id="ee9f3-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-199">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="ee9f3-200">Unclassified</span></span></td>
<td><span data-ttu-id="ee9f3-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-201">-10,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-203">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-203">CC099</span></span></td>
<td><span data-ttu-id="ee9f3-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-204">Default cost center</span></span></td>
<td><span data-ttu-id="ee9f3-205">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-205">10001</span></span></td>
<td><span data-ttu-id="ee9f3-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-206">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-207">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-208">1,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-210">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-210">CC099</span></span></td>
<td><span data-ttu-id="ee9f3-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-211">Default cost center</span></span></td>
<td><span data-ttu-id="ee9f3-212">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-212">10001</span></span></td>
<td><span data-ttu-id="ee9f3-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-213">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-214">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-215">9,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-217">A költségműködéssel kapcsolatos részletes tudnivalókat lásd a Költségműködési irányelvekben.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="ee9f3-218">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="ee9f3-219">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ee9f3-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="ee9f3-220">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="ee9f3-221">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="ee9f3-222">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="ee9f3-222">Define the cost distribution rule</span></span>

<span data-ttu-id="ee9f3-223">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="ee9f3-224">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="ee9f3-225">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="ee9f3-226">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="ee9f3-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="ee9f3-227">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="ee9f3-228">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-229">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-229">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="ee9f3-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-231">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-231">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-232">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-232">HR</span></span></td>
<td><span data-ttu-id="ee9f3-233">1000</span><span class="sxs-lookup"><span data-stu-id="ee9f3-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-234">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-234">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-235">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-235">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-236">6,000</span><span class="sxs-lookup"><span data-stu-id="ee9f3-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-237">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-237">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-238">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-238">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-239">0</span><span class="sxs-lookup"><span data-stu-id="ee9f3-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-240">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-241">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-241">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-242">Nagyság</span><span class="sxs-lookup"><span data-stu-id="ee9f3-242">Magnitude</span></span></th>
<th><span data-ttu-id="ee9f3-243">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="ee9f3-243">Allocation factor</span></span></th>
<th><span data-ttu-id="ee9f3-244">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-245">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-245">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-246">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-246">HR</span></span></td>
<td><span data-ttu-id="ee9f3-247">1000</span><span class="sxs-lookup"><span data-stu-id="ee9f3-247">1,000</span></span></td>
<td><span data-ttu-id="ee9f3-248">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ee9f3-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-250">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-250">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-251">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-251">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-252">6,000</span><span class="sxs-lookup"><span data-stu-id="ee9f3-252">6,000</span></span></td>
<td><span data-ttu-id="ee9f3-253">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ee9f3-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-255">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-255">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-256">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-256">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-257">0</span><span class="sxs-lookup"><span data-stu-id="ee9f3-257">0</span></span></td>
<td><span data-ttu-id="ee9f3-258">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-259">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-260">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="ee9f3-261">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: ((Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-262">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-262">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-263">Receptúra</span><span class="sxs-lookup"><span data-stu-id="ee9f3-263">Formula</span></span></th>
<th><span data-ttu-id="ee9f3-264">Nagyság</span><span class="sxs-lookup"><span data-stu-id="ee9f3-264">Magnitude</span></span></th>
<th><span data-ttu-id="ee9f3-265">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="ee9f3-265">Allocation factor</span></span></th>
<th><span data-ttu-id="ee9f3-266">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-267">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-267">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-268">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-268">HR</span></span></td>
<td><span data-ttu-id="ee9f3-269">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ee9f3-270">1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-270">1</span></span></td>
<td><span data-ttu-id="ee9f3-271">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-272">500.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-273">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-273">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-274">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-274">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-275">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ee9f3-276">1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-276">1</span></span></td>
<td><span data-ttu-id="ee9f3-277">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-278">500.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-279">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-279">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-280">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-280">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-281">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="ee9f3-282">0</span><span class="sxs-lookup"><span data-stu-id="ee9f3-282">0</span></span></td>
<td><span data-ttu-id="ee9f3-283">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-284">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ee9f3-285">Napló</span><span class="sxs-lookup"><span data-stu-id="ee9f3-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ee9f3-286">Napló</span><span class="sxs-lookup"><span data-stu-id="ee9f3-286">Journal</span></span></th>
<th><span data-ttu-id="ee9f3-287">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="ee9f3-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ee9f3-288">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ee9f3-289">Verzió</span><span class="sxs-lookup"><span data-stu-id="ee9f3-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-290">00002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-290">00002</span></span></td>
<td><span data-ttu-id="ee9f3-291">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="ee9f3-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="ee9f3-292">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="ee9f3-292">Fiscal</span></span></td>
<td><span data-ttu-id="ee9f3-293">2017</span><span class="sxs-lookup"><span data-stu-id="ee9f3-293">2017</span></span></td>
<td><span data-ttu-id="ee9f3-294">1. időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-294">Period 1</span></span></td>
<td><span data-ttu-id="ee9f3-295">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ee9f3-296">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ee9f3-297">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-298">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-299">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-299">Cost element</span></span></th>
<th><span data-ttu-id="ee9f3-300">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-300">Cost behavior</span></span></th>
<th><span data-ttu-id="ee9f3-301">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-302">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-303">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-303">CC099</span></span></td>
<td><span data-ttu-id="ee9f3-304">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-304">Default cost center</span></span></td>
<td><span data-ttu-id="ee9f3-305">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-305">10001</span></span></td>
<td><span data-ttu-id="ee9f3-306">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-306">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-307">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-307">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-308">1000,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-309">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-310">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-310">CC099</span></span></td>
<td><span data-ttu-id="ee9f3-311">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-311">Default cost center</span></span></td>
<td><span data-ttu-id="ee9f3-312">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-312">10001</span></span></td>
<td><span data-ttu-id="ee9f3-313">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-313">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-314">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-314">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ee9f3-316">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="ee9f3-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-317">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-318">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-318">Cost element</span></span></th>
<th><span data-ttu-id="ee9f3-319">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-319">Cost behavior</span></span></th>
<th><span data-ttu-id="ee9f3-320">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-320">Amount</span></span></th>
<th><span data-ttu-id="ee9f3-321">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-322">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-322">CC099</span></span></td>
<td><span data-ttu-id="ee9f3-323">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-323">Default cost center</span></span></td>
<td><span data-ttu-id="ee9f3-324">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-324">10001</span></span></td>
<td><span data-ttu-id="ee9f3-325">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-325">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-326">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-326">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-327">-1000,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-327">-1,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-328">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-329">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-329">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-330">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-330">HR</span></span></td>
<td><span data-ttu-id="ee9f3-331">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-331">10001</span></span></td>
<td><span data-ttu-id="ee9f3-332">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-332">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-333">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-333">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-334">500.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-334">500.00</span></span></td>
<td><span data-ttu-id="ee9f3-335">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-336">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-336">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-337">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-337">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-338">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-338">10001</span></span></td>
<td><span data-ttu-id="ee9f3-339">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-339">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-340">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-340">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-341">500.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-341">500.00</span></span></td>
<td><span data-ttu-id="ee9f3-342">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-343">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-343">CC099</span></span></td>
<td><span data-ttu-id="ee9f3-344">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="ee9f3-344">Default cost center</span></span></td>
<td><span data-ttu-id="ee9f3-345">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-345">10001</span></span></td>
<td><span data-ttu-id="ee9f3-346">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-346">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-347">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-347">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-348">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-348">-9,000.00</span></span></td>
<td><span data-ttu-id="ee9f3-349">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-350">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-350">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-351">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-351">HR</span></span></td>
<td><span data-ttu-id="ee9f3-352">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-352">10001</span></span></td>
<td><span data-ttu-id="ee9f3-353">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-353">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-354">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-354">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="ee9f3-355">1,285.71</span></span></td>
<td><span data-ttu-id="ee9f3-356">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-357">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-357">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-358">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-358">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-359">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-359">10001</span></span></td>
<td><span data-ttu-id="ee9f3-360">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-360">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-361">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-361">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="ee9f3-362">7,714.29</span></span></td>
<td><span data-ttu-id="ee9f3-363">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-364">Ha részletes információt szeretne a költségfelosztásról és a felosztási alapokról, lásd a Költségfelosztási irányelvet és a felosztási alapokat.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="ee9f3-365">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="ee9f3-366">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="ee9f3-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="ee9f3-367">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="ee9f3-368">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="ee9f3-369">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="ee9f3-369">Define the overhead rate</span></span>

<span data-ttu-id="ee9f3-370">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="ee9f3-371">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-372">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-372">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-373">óra</span><span class="sxs-lookup"><span data-stu-id="ee9f3-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-374">Proj 1</span></span></td>
<td><span data-ttu-id="ee9f3-375">1. projekt</span><span class="sxs-lookup"><span data-stu-id="ee9f3-375">Project 1</span></span></td>
<td><span data-ttu-id="ee9f3-376">3</span><span class="sxs-lookup"><span data-stu-id="ee9f3-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-377">Proj 2</span></span></td>
<td><span data-ttu-id="ee9f3-378">2. projekt</span><span class="sxs-lookup"><span data-stu-id="ee9f3-378">Project 2</span></span></td>
<td><span data-ttu-id="ee9f3-379">1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-380">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-381">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-381">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-382">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-382">Cost element</span></span></th>
<th><span data-ttu-id="ee9f3-383">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-383">Cost behavior</span></span></th>
<th><span data-ttu-id="ee9f3-384">Egységek</span><span class="sxs-lookup"><span data-stu-id="ee9f3-384">Units</span></span></th>
<th><span data-ttu-id="ee9f3-385">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="ee9f3-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-386">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-386">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-387">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-387">HR</span></span></td>
<td><span data-ttu-id="ee9f3-388">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-388">10001</span></span></td>
<td><span data-ttu-id="ee9f3-389">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-389">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-390">1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-390">1</span></span></td>
<td><span data-ttu-id="ee9f3-391">10</span><span class="sxs-lookup"><span data-stu-id="ee9f3-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-392">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-393">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-393">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-394">Nagyság</span><span class="sxs-lookup"><span data-stu-id="ee9f3-394">Magnitude</span></span></th>
<th><span data-ttu-id="ee9f3-395">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-395">Cost element</span></span></th>
<th><span data-ttu-id="ee9f3-396">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="ee9f3-396">Allocation factor</span></span></th>
<th><span data-ttu-id="ee9f3-397">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-398">Proj 1</span></span></td>
<td><span data-ttu-id="ee9f3-399">1. projekt</span><span class="sxs-lookup"><span data-stu-id="ee9f3-399">Project 1</span></span></td>
<td><span data-ttu-id="ee9f3-400">3</span><span class="sxs-lookup"><span data-stu-id="ee9f3-400">3</span></span></td>
<td><span data-ttu-id="ee9f3-401">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-401">10001</span></span></td>
<td><span data-ttu-id="ee9f3-402">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ee9f3-403">30.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-404">Proj 2</span></span></td>
<td><span data-ttu-id="ee9f3-405">2. projekt</span><span class="sxs-lookup"><span data-stu-id="ee9f3-405">Project 2</span></span></td>
<td><span data-ttu-id="ee9f3-406">1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-406">1</span></span></td>
<td><span data-ttu-id="ee9f3-407">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-407">10001</span></span></td>
<td><span data-ttu-id="ee9f3-408">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="ee9f3-409">10.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="ee9f3-410">Napló</span><span class="sxs-lookup"><span data-stu-id="ee9f3-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ee9f3-411">Napló</span><span class="sxs-lookup"><span data-stu-id="ee9f3-411">Journal</span></span></th>
<th><span data-ttu-id="ee9f3-412">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="ee9f3-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ee9f3-413">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ee9f3-414">Verzió</span><span class="sxs-lookup"><span data-stu-id="ee9f3-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-415">00003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-415">00003</span></span></td>
<td><span data-ttu-id="ee9f3-416">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="ee9f3-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="ee9f3-417">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="ee9f3-417">Fiscal</span></span></td>
<td><span data-ttu-id="ee9f3-418">2017</span><span class="sxs-lookup"><span data-stu-id="ee9f3-418">2017</span></span></td>
<td><span data-ttu-id="ee9f3-419">1. időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-419">Period 1</span></span></td>
<td><span data-ttu-id="ee9f3-420">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="ee9f3-421">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ee9f3-422">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-423">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-423">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-424">Nagyság</span><span class="sxs-lookup"><span data-stu-id="ee9f3-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-425">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-426">Proj 1</span></span></td>
<td><span data-ttu-id="ee9f3-427">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ee9f3-428">3,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-429">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-430">Proj 2</span></span></td>
<td><span data-ttu-id="ee9f3-431">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ee9f3-432">1.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ee9f3-433">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="ee9f3-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-434">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-435">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-435">Cost element</span></span></th>
<th><span data-ttu-id="ee9f3-436">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-436">Cost behavior</span></span></th>
<th><span data-ttu-id="ee9f3-437">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-437">Amount</span></span></th>
<th><span data-ttu-id="ee9f3-438">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-439">CC0001</span></span></td>
<td><span data-ttu-id="ee9f3-440">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-440">HR</span></span></td>
<td><span data-ttu-id="ee9f3-441">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-441">10001</span></span></td>
<td><span data-ttu-id="ee9f3-442">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-442">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-443">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-443">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-444">-30.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-444">-30.00</span></span></td>
<td><span data-ttu-id="ee9f3-445">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-446">Proj 1</span></span></td>
<td><span data-ttu-id="ee9f3-447">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="ee9f3-448">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-448">10001</span></span></td>
<td><span data-ttu-id="ee9f3-449">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-449">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-450">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-450">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-451">30.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-451">30.00</span></span></td>
<td><span data-ttu-id="ee9f3-452">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-453">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-453">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-454">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-454">HR</span></span></td>
<td><span data-ttu-id="ee9f3-455">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-455">10001</span></span></td>
<td><span data-ttu-id="ee9f3-456">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-456">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-457">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-457">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-458">-10.00</span></span></td>
<td><span data-ttu-id="ee9f3-459">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-460">Proj 2</span></span></td>
<td><span data-ttu-id="ee9f3-461">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="ee9f3-462">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-462">10001</span></span></td>
<td><span data-ttu-id="ee9f3-463">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-463">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-464">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-464">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-465">10.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-465">10.00</span></span></td>
<td><span data-ttu-id="ee9f3-466">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-467">A járulékos díj irányelvére vonatkozó részletes információkért lásd: A járulékos díj irányelvei és Felosztási bázisok.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="ee9f3-468">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="ee9f3-469">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="ee9f3-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="ee9f3-470">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="ee9f3-471">A Finance and Operations a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="ee9f3-472">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="ee9f3-473">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="ee9f3-474">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="ee9f3-475">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="ee9f3-476">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="ee9f3-477">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="ee9f3-478">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="ee9f3-478">Define the cost allocation</span></span>

<span data-ttu-id="ee9f3-479">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="ee9f3-480">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="ee9f3-481">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-482">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-482">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-483">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="ee9f3-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-484">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-484">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-485">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-485">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-486">35</span><span class="sxs-lookup"><span data-stu-id="ee9f3-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-487">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-487">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-488">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-488">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-489">55</span><span class="sxs-lookup"><span data-stu-id="ee9f3-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-490">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-490">CC004</span></span></td>
<td><span data-ttu-id="ee9f3-491">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-491">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-492">10</span><span class="sxs-lookup"><span data-stu-id="ee9f3-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-493">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="ee9f3-494">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-495">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-495">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-496">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="ee9f3-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-497">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-497">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-498">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-498">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-499">65</span><span class="sxs-lookup"><span data-stu-id="ee9f3-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-500">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-500">CC004</span></span></td>
<td><span data-ttu-id="ee9f3-501">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-501">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-502">35</span><span class="sxs-lookup"><span data-stu-id="ee9f3-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-503">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="ee9f3-504">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-505">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-505">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-506">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-507">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-507">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-508">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-508">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-509">60</span><span class="sxs-lookup"><span data-stu-id="ee9f3-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-510">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-510">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-511">2. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-511">Product 2</span></span></td>
<td><span data-ttu-id="ee9f3-512">20</span><span class="sxs-lookup"><span data-stu-id="ee9f3-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-513">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="ee9f3-514">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-515">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-515">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-516">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-517">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-517">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-518">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-518">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-519">80</span><span class="sxs-lookup"><span data-stu-id="ee9f3-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-520">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-520">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-521">2. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-521">Product 2</span></span></td>
<td><span data-ttu-id="ee9f3-522">15.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-523">**Megjegyzés:** A Finance and Operations esetében a statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="ee9f3-524">A statisztikai mérési szolgáltatókról szóló bővebb információkért lásd: Statisztikai mérték szolgáltatójának sablonjai.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="ee9f3-525">(Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.) Az alábbi táblázat azt az eredményt mutatja, amikor a HR-szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-526">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-526">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-527">Nagyság</span><span class="sxs-lookup"><span data-stu-id="ee9f3-527">Magnitude</span></span></th>
<th><span data-ttu-id="ee9f3-528">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="ee9f3-528">Allocation factor</span></span></th>
<th><span data-ttu-id="ee9f3-529">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-529">Amount</span></span></th>
<th><span data-ttu-id="ee9f3-530">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-531">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-531">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-532">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-532">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-533">35</span><span class="sxs-lookup"><span data-stu-id="ee9f3-533">35</span></span></td>
<td><span data-ttu-id="ee9f3-534">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ee9f3-535">175.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-535">175.00</span></span></td>
<td><span data-ttu-id="ee9f3-536">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-537">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-537">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-538">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-538">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-539">55</span><span class="sxs-lookup"><span data-stu-id="ee9f3-539">55</span></span></td>
<td><span data-ttu-id="ee9f3-540">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ee9f3-541">275.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-541">275.00</span></span></td>
<td><span data-ttu-id="ee9f3-542">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-543">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-543">CC004</span></span></td>
<td><span data-ttu-id="ee9f3-544">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-544">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-545">10</span><span class="sxs-lookup"><span data-stu-id="ee9f3-545">10</span></span></td>
<td><span data-ttu-id="ee9f3-546">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="ee9f3-547">50,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-547">50.00</span></span></td>
<td><span data-ttu-id="ee9f3-548">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-549">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-549">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-550">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-550">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-551">35</span><span class="sxs-lookup"><span data-stu-id="ee9f3-551">35</span></span></td>
<td><span data-ttu-id="ee9f3-552">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="ee9f3-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ee9f3-553">436.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-553">436.00</span></span></td>
<td><span data-ttu-id="ee9f3-554">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-555">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-555">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-556">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-556">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-557">55</span><span class="sxs-lookup"><span data-stu-id="ee9f3-557">55</span></span></td>
<td><span data-ttu-id="ee9f3-558">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="ee9f3-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ee9f3-559">685.14</span><span class="sxs-lookup"><span data-stu-id="ee9f3-559">685.14</span></span></td>
<td><span data-ttu-id="ee9f3-560">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-561">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-561">CC004</span></span></td>
<td><span data-ttu-id="ee9f3-562">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-562">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-563">10</span><span class="sxs-lookup"><span data-stu-id="ee9f3-563">10</span></span></td>
<td><span data-ttu-id="ee9f3-564">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="ee9f3-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="ee9f3-565">124.57</span><span class="sxs-lookup"><span data-stu-id="ee9f3-565">124.57</span></span></td>
<td><span data-ttu-id="ee9f3-566">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-567">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-568">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-568">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-569">Nagyság</span><span class="sxs-lookup"><span data-stu-id="ee9f3-569">Magnitude</span></span></th>
<th><span data-ttu-id="ee9f3-570">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="ee9f3-570">Allocation factor</span></span></th>
<th><span data-ttu-id="ee9f3-571">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-571">Amount</span></span></th>
<th><span data-ttu-id="ee9f3-572">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-573">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-573">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-574">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-574">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-575">65</span><span class="sxs-lookup"><span data-stu-id="ee9f3-575">65</span></span></td>
<td><span data-ttu-id="ee9f3-576">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ee9f3-577">438.75</span><span class="sxs-lookup"><span data-stu-id="ee9f3-577">438.75</span></span></td>
<td><span data-ttu-id="ee9f3-578">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-579">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-579">CC004</span></span></td>
<td><span data-ttu-id="ee9f3-580">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-580">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-581">35</span><span class="sxs-lookup"><span data-stu-id="ee9f3-581">35</span></span></td>
<td><span data-ttu-id="ee9f3-582">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="ee9f3-583">236.25</span><span class="sxs-lookup"><span data-stu-id="ee9f3-583">236.25</span></span></td>
<td><span data-ttu-id="ee9f3-584">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-585">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-585">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-586">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-586">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-587">65</span><span class="sxs-lookup"><span data-stu-id="ee9f3-587">65</span></span></td>
<td><span data-ttu-id="ee9f3-588">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ee9f3-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ee9f3-589">5,297.69</span></span></td>
<td><span data-ttu-id="ee9f3-590">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-591">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-591">CC004</span></span></td>
<td><span data-ttu-id="ee9f3-592">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-592">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-593">35</span><span class="sxs-lookup"><span data-stu-id="ee9f3-593">35</span></span></td>
<td><span data-ttu-id="ee9f3-594">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="ee9f3-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ee9f3-595">2,852.60</span></span></td>
<td><span data-ttu-id="ee9f3-596">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-597">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-598">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-598">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-599">Nagyság</span><span class="sxs-lookup"><span data-stu-id="ee9f3-599">Magnitude</span></span></th>
<th><span data-ttu-id="ee9f3-600">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="ee9f3-600">Allocation factor</span></span></th>
<th><span data-ttu-id="ee9f3-601">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-601">Amount</span></span></th>
<th><span data-ttu-id="ee9f3-602">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-603">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-603">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-604">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-604">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-605">60</span><span class="sxs-lookup"><span data-stu-id="ee9f3-605">60</span></span></td>
<td><span data-ttu-id="ee9f3-606">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ee9f3-607">535.31</span><span class="sxs-lookup"><span data-stu-id="ee9f3-607">535.31</span></span></td>
<td><span data-ttu-id="ee9f3-608">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-609">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-609">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-610">2. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-610">Product 2</span></span></td>
<td><span data-ttu-id="ee9f3-611">20</span><span class="sxs-lookup"><span data-stu-id="ee9f3-611">20</span></span></td>
<td><span data-ttu-id="ee9f3-612">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="ee9f3-613">178.44</span><span class="sxs-lookup"><span data-stu-id="ee9f3-613">178.44</span></span></td>
<td><span data-ttu-id="ee9f3-614">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-615">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-615">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-616">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-616">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-617">60</span><span class="sxs-lookup"><span data-stu-id="ee9f3-617">60</span></span></td>
<td><span data-ttu-id="ee9f3-618">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ee9f3-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ee9f3-619">4,487.12</span></span></td>
<td><span data-ttu-id="ee9f3-620">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-621">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-621">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-622">2. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-622">Product 2</span></span></td>
<td><span data-ttu-id="ee9f3-623">20</span><span class="sxs-lookup"><span data-stu-id="ee9f3-623">20</span></span></td>
<td><span data-ttu-id="ee9f3-624">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="ee9f3-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ee9f3-625">1,495.71</span></span></td>
<td><span data-ttu-id="ee9f3-626">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ee9f3-627">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-628">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-628">Cost object</span></span></th>
<th><span data-ttu-id="ee9f3-629">Nagyság</span><span class="sxs-lookup"><span data-stu-id="ee9f3-629">Magnitude</span></span></th>
<th><span data-ttu-id="ee9f3-630">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="ee9f3-630">Allocation factor</span></span></th>
<th><span data-ttu-id="ee9f3-631">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-631">Amount</span></span></th>
<th><span data-ttu-id="ee9f3-632">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-633">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-633">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-634">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-634">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-635">80</span><span class="sxs-lookup"><span data-stu-id="ee9f3-635">80</span></span></td>
<td><span data-ttu-id="ee9f3-636">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ee9f3-637">241.05</span><span class="sxs-lookup"><span data-stu-id="ee9f3-637">241.05</span></span></td>
<td><span data-ttu-id="ee9f3-638">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-639">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-639">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-640">2. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-640">Product 2</span></span></td>
<td><span data-ttu-id="ee9f3-641">15.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-641">15</span></span></td>
<td><span data-ttu-id="ee9f3-642">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="ee9f3-643">45.20</span><span class="sxs-lookup"><span data-stu-id="ee9f3-643">45.20</span></span></td>
<td><span data-ttu-id="ee9f3-644">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-645">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-645">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-646">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-646">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-647">80</span><span class="sxs-lookup"><span data-stu-id="ee9f3-647">80</span></span></td>
<td><span data-ttu-id="ee9f3-648">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ee9f3-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ee9f3-649">2,507.09</span></span></td>
<td><span data-ttu-id="ee9f3-650">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-651">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-651">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-652">2. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-652">Product 2</span></span></td>
<td><span data-ttu-id="ee9f3-653">15.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-653">15</span></span></td>
<td><span data-ttu-id="ee9f3-654">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="ee9f3-655">470.08</span><span class="sxs-lookup"><span data-stu-id="ee9f3-655">470.08</span></span></td>
<td><span data-ttu-id="ee9f3-656">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="ee9f3-657">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ee9f3-658">Napló</span><span class="sxs-lookup"><span data-stu-id="ee9f3-658">Journal</span></span></th>
<th><span data-ttu-id="ee9f3-659">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="ee9f3-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="ee9f3-660">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="ee9f3-661">Verzió</span><span class="sxs-lookup"><span data-stu-id="ee9f3-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-662">00004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-662">00004</span></span></td>
<td><span data-ttu-id="ee9f3-663">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="ee9f3-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="ee9f3-664">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="ee9f3-664">Fiscal</span></span></td>
<td><span data-ttu-id="ee9f3-665">2017</span><span class="sxs-lookup"><span data-stu-id="ee9f3-665">2017</span></span></td>
<td><span data-ttu-id="ee9f3-666">1. időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-666">Period 1</span></span></td>
<td><span data-ttu-id="ee9f3-667">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="ee9f3-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="ee9f3-668">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="ee9f3-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="ee9f3-669">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-670">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-671">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-671">Cost element</span></span></th>
<th><span data-ttu-id="ee9f3-672">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-672">Cost behavior</span></span></th>
<th><span data-ttu-id="ee9f3-673">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-674">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-675">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-675">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-676">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-676">HR</span></span></td>
<td><span data-ttu-id="ee9f3-677">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-677">10001</span></span></td>
<td><span data-ttu-id="ee9f3-678">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-678">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-679">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-679">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-680">500.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-681">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-682">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-682">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-683">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-683">HR</span></span></td>
<td><span data-ttu-id="ee9f3-684">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-684">10001</span></span></td>
<td><span data-ttu-id="ee9f3-685">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-685">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-686">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-686">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="ee9f3-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-688">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-689">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-689">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-690">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-690">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-691">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-691">10001</span></span></td>
<td><span data-ttu-id="ee9f3-692">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-692">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-693">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-693">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-694">675.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-695">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-696">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-696">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-697">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-697">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-698">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-698">10001</span></span></td>
<td><span data-ttu-id="ee9f3-699">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-699">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-700">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-700">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="ee9f3-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-702">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-703">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-703">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-704">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-704">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-705">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-705">10001</span></span></td>
<td><span data-ttu-id="ee9f3-706">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-706">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-707">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-707">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-708">713.75</span><span class="sxs-lookup"><span data-stu-id="ee9f3-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-709">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-710">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-710">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-711">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-711">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-712">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-712">10001</span></span></td>
<td><span data-ttu-id="ee9f3-713">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-713">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-714">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-714">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="ee9f3-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-716">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-717">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-717">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-718">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-718">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-719">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-719">10001</span></span></td>
<td><span data-ttu-id="ee9f3-720">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-720">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-721">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-721">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-722">286.25</span><span class="sxs-lookup"><span data-stu-id="ee9f3-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-723">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-724">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-724">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-725">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-725">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-726">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-726">10001</span></span></td>
<td><span data-ttu-id="ee9f3-727">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-727">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-728">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-728">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="ee9f3-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-730">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-731">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-731">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-732">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-732">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-733">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-733">10001</span></span></td>
<td><span data-ttu-id="ee9f3-734">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-734">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-735">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-735">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-736">776.36</span><span class="sxs-lookup"><span data-stu-id="ee9f3-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-737">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-738">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-738">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-739">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-739">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-740">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-740">10001</span></span></td>
<td><span data-ttu-id="ee9f3-741">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-741">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-742">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-742">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ee9f3-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-744">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-745">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-745">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-746">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-746">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-747">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-747">10001</span></span></td>
<td><span data-ttu-id="ee9f3-748">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-748">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-749">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-749">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-750">223.64</span><span class="sxs-lookup"><span data-stu-id="ee9f3-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-751">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="ee9f3-752">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-752">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-753">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-753">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-754">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-754">10001</span></span></td>
<td><span data-ttu-id="ee9f3-755">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-755">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-756">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-756">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ee9f3-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="ee9f3-758">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="ee9f3-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="ee9f3-759">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="ee9f3-760">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-760">Cost element</span></span></th>
<th><span data-ttu-id="ee9f3-761">Költség működése</span><span class="sxs-lookup"><span data-stu-id="ee9f3-761">Cost behavior</span></span></th>
<th><span data-ttu-id="ee9f3-762">Összeg</span><span class="sxs-lookup"><span data-stu-id="ee9f3-762">Amount</span></span></th>
<th><span data-ttu-id="ee9f3-763">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="ee9f3-764">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-764">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-765">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-765">HR</span></span></td>
<td><span data-ttu-id="ee9f3-766">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-766">10001</span></span></td>
<td><span data-ttu-id="ee9f3-767">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-767">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-768">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-768">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-769">-500.00</span></span></td>
<td><span data-ttu-id="ee9f3-770">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-771">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-771">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-772">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-772">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-773">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-773">10001</span></span></td>
<td><span data-ttu-id="ee9f3-774">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-774">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-775">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-775">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-776">175.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-776">175.00</span></span></td>
<td><span data-ttu-id="ee9f3-777">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-778">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-778">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-779">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-779">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-780">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-780">10001</span></span></td>
<td><span data-ttu-id="ee9f3-781">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-781">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-782">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-782">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-783">275.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-783">275.00</span></span></td>
<td><span data-ttu-id="ee9f3-784">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-785">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-785">CC004</span></span></td>
<td><span data-ttu-id="ee9f3-786">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-786">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-787">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-787">10001</span></span></td>
<td><span data-ttu-id="ee9f3-788">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-788">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-789">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-789">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-790">50,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-790">50,00</span></span></td>
<td><span data-ttu-id="ee9f3-791">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-792">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-792">CC001</span></span></td>
<td><span data-ttu-id="ee9f3-793">HR</span><span class="sxs-lookup"><span data-stu-id="ee9f3-793">HR</span></span></td>
<td><span data-ttu-id="ee9f3-794">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-794">10001</span></span></td>
<td><span data-ttu-id="ee9f3-795">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-795">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-796">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-796">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-797">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="ee9f3-797">-1,245.71</span></span></td>
<td><span data-ttu-id="ee9f3-798">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-799">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-799">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-800">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-800">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-801">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-801">10001</span></span></td>
<td><span data-ttu-id="ee9f3-802">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-802">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-803">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-803">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-804">436.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-804">436.00</span></span></td>
<td><span data-ttu-id="ee9f3-805">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-806">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-806">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-807">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-807">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-808">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-808">10001</span></span></td>
<td><span data-ttu-id="ee9f3-809">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-809">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-810">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-810">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-811">685.14</span><span class="sxs-lookup"><span data-stu-id="ee9f3-811">685.14</span></span></td>
<td><span data-ttu-id="ee9f3-812">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-813">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-813">CC004</span></span></td>
<td><span data-ttu-id="ee9f3-814">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-814">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-815">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-815">10001</span></span></td>
<td><span data-ttu-id="ee9f3-816">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-816">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-817">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-817">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-818">124.57</span><span class="sxs-lookup"><span data-stu-id="ee9f3-818">124.57</span></span></td>
<td><span data-ttu-id="ee9f3-819">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-820">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-820">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-821">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-821">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-822">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-822">10001</span></span></td>
<td><span data-ttu-id="ee9f3-823">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-823">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-824">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-824">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-825">-675.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-825">-675.00</span></span></td>
<td><span data-ttu-id="ee9f3-826">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-827">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-827">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-828">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-828">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-829">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-829">10001</span></span></td>
<td><span data-ttu-id="ee9f3-830">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-830">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-831">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-831">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-832">438.75</span><span class="sxs-lookup"><span data-stu-id="ee9f3-832">438.75</span></span></td>
<td><span data-ttu-id="ee9f3-833">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-834">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-834">CC004</span></span></td>
<td><span data-ttu-id="ee9f3-835">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-835">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-836">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-836">10001</span></span></td>
<td><span data-ttu-id="ee9f3-837">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-837">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-838">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-838">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-839">236.25</span><span class="sxs-lookup"><span data-stu-id="ee9f3-839">236.25</span></span></td>
<td><span data-ttu-id="ee9f3-840">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-841">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-841">CC002</span></span></td>
<td><span data-ttu-id="ee9f3-842">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="ee9f3-842">Finance</span></span></td>
<td><span data-ttu-id="ee9f3-843">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-843">10001</span></span></td>
<td><span data-ttu-id="ee9f3-844">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-844">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-845">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-845">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-846">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="ee9f3-846">-8,150.29</span></span></td>
<td><span data-ttu-id="ee9f3-847">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-848">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-848">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-849">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-849">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-850">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-850">10001</span></span></td>
<td><span data-ttu-id="ee9f3-851">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-851">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-852">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-852">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="ee9f3-853">5,297.69</span></span></td>
<td><span data-ttu-id="ee9f3-854">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-855">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-855">CC004</span></span></td>
<td><span data-ttu-id="ee9f3-856">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="ee9f3-856">Packaging</span></span></td>
<td><span data-ttu-id="ee9f3-857">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-857">10001</span></span></td>
<td><span data-ttu-id="ee9f3-858">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-858">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-859">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-859">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="ee9f3-860">2,852.60</span></span></td>
<td><span data-ttu-id="ee9f3-861">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-862">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-862">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-863">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-863">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-864">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-864">10001</span></span></td>
<td><span data-ttu-id="ee9f3-865">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-865">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-866">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-866">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-867">-713.75</span><span class="sxs-lookup"><span data-stu-id="ee9f3-867">-713.75</span></span></td>
<td><span data-ttu-id="ee9f3-868">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-869">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-869">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-870">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-870">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-871">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-871">10001</span></span></td>
<td><span data-ttu-id="ee9f3-872">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-872">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-873">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-873">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-874">535.31</span><span class="sxs-lookup"><span data-stu-id="ee9f3-874">535.31</span></span></td>
<td><span data-ttu-id="ee9f3-875">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-876">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-876">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-877">2. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-877">Product 2</span></span></td>
<td><span data-ttu-id="ee9f3-878">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-878">10001</span></span></td>
<td><span data-ttu-id="ee9f3-879">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-879">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-880">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-880">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-881">178.44</span><span class="sxs-lookup"><span data-stu-id="ee9f3-881">178.44</span></span></td>
<td><span data-ttu-id="ee9f3-882">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-883">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-883">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-884">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-884">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-885">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-885">10001</span></span></td>
<td><span data-ttu-id="ee9f3-886">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-886">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-887">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-887">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-888">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="ee9f3-888">-5,982.83</span></span></td>
<td><span data-ttu-id="ee9f3-889">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-890">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-890">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-891">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-891">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-892">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-892">10001</span></span></td>
<td><span data-ttu-id="ee9f3-893">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-893">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-894">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-894">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="ee9f3-895">4,487.12</span></span></td>
<td><span data-ttu-id="ee9f3-896">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-897">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-897">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-898">2. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-898">Product 2</span></span></td>
<td><span data-ttu-id="ee9f3-899">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-899">10001</span></span></td>
<td><span data-ttu-id="ee9f3-900">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-900">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-901">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-901">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="ee9f3-902">1,495.71</span></span></td>
<td><span data-ttu-id="ee9f3-903">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-904">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-904">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-905">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-905">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-906">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-906">10001</span></span></td>
<td><span data-ttu-id="ee9f3-907">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-907">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-908">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-908">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-909">-286.25</span><span class="sxs-lookup"><span data-stu-id="ee9f3-909">-286.25</span></span></td>
<td><span data-ttu-id="ee9f3-910">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-911">Term 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-911">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-912">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-912">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-913">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-913">10001</span></span></td>
<td><span data-ttu-id="ee9f3-914">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-914">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-915">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-915">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-916">241.05</span><span class="sxs-lookup"><span data-stu-id="ee9f3-916">241.05</span></span></td>
<td><span data-ttu-id="ee9f3-917">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-918">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-918">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-919">2. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-919">Product 2</span></span></td>
<td><span data-ttu-id="ee9f3-920">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-920">10001</span></span></td>
<td><span data-ttu-id="ee9f3-921">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-921">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-922">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-922">Fixed cost</span></span></td>
<td><span data-ttu-id="ee9f3-923">45.20</span><span class="sxs-lookup"><span data-stu-id="ee9f3-923">45.20</span></span></td>
<td><span data-ttu-id="ee9f3-924">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-925">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-925">CC003</span></span></td>
<td><span data-ttu-id="ee9f3-926">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="ee9f3-926">Assembly</span></span></td>
<td><span data-ttu-id="ee9f3-927">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-927">10001</span></span></td>
<td><span data-ttu-id="ee9f3-928">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-928">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-929">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-929">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-930">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="ee9f3-930">-2,977.17</span></span></td>
<td><span data-ttu-id="ee9f3-931">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-932">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-932">Prod 1</span></span></td>
<td><span data-ttu-id="ee9f3-933">1. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-933">Product 1</span></span></td>
<td><span data-ttu-id="ee9f3-934">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-934">10001</span></span></td>
<td><span data-ttu-id="ee9f3-935">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-935">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-936">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-936">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="ee9f3-937">2,507.09</span></span></td>
<td><span data-ttu-id="ee9f3-938">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="ee9f3-939">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-939">Prod 2</span></span></td>
<td><span data-ttu-id="ee9f3-940">2. termék</span><span class="sxs-lookup"><span data-stu-id="ee9f3-940">Product 2</span></span></td>
<td><span data-ttu-id="ee9f3-941">10001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-941">10001</span></span></td>
<td><span data-ttu-id="ee9f3-942">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-942">Electricity</span></span></td>
<td><span data-ttu-id="ee9f3-943">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-943">Variable cost</span></span></td>
<td><span data-ttu-id="ee9f3-944">470.08</span><span class="sxs-lookup"><span data-stu-id="ee9f3-944">470.08</span></span></td>
<td><span data-ttu-id="ee9f3-945">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="ee9f3-946">Következtetés</span><span class="sxs-lookup"><span data-stu-id="ee9f3-946">Conclusion</span></span>
<span data-ttu-id="ee9f3-947">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="ee9f3-948">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="ee9f3-949">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="ee9f3-950">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="ee9f3-951">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="ee9f3-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="ee9f3-952">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ee9f3-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="ee9f3-953">Összesen</span><span class="sxs-lookup"><span data-stu-id="ee9f3-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="ee9f3-954">CC099</span><span class="sxs-lookup"><span data-stu-id="ee9f3-954">CC099</span></span></th>
<th><span data-ttu-id="ee9f3-955">CC001</span><span class="sxs-lookup"><span data-stu-id="ee9f3-955">CC001</span></span></th>
<th><span data-ttu-id="ee9f3-956">CC002</span><span class="sxs-lookup"><span data-stu-id="ee9f3-956">CC002</span></span></th>
<th><span data-ttu-id="ee9f3-957">CC003</span><span class="sxs-lookup"><span data-stu-id="ee9f3-957">CC003</span></span></th>
<th><span data-ttu-id="ee9f3-958">CC004</span><span class="sxs-lookup"><span data-stu-id="ee9f3-958">CC004</span></span></th>
<th><span data-ttu-id="ee9f3-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-959">Proj 1</span></span></th>
<th><span data-ttu-id="ee9f3-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-960">Proj 2</span></span></th>
<th><span data-ttu-id="ee9f3-961">Term. 1</span><span class="sxs-lookup"><span data-stu-id="ee9f3-961">Prod 1</span></span></th>
<th><span data-ttu-id="ee9f3-962">Term. 2</span><span class="sxs-lookup"><span data-stu-id="ee9f3-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="ee9f3-963">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="ee9f3-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-965"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-966"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-967"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-968"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-969"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-970"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-971"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-972"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="ee9f3-973">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="ee9f3-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-974">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="ee9f3-975">Fix költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-976">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-977">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-978">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-979">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-980">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-981">776.36</span><span class="sxs-lookup"><span data-stu-id="ee9f3-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-982">223.64</span><span class="sxs-lookup"><span data-stu-id="ee9f3-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-983"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="ee9f3-984">Változó költség</span><span class="sxs-lookup"><span data-stu-id="ee9f3-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-985">000</span><span class="sxs-lookup"><span data-stu-id="ee9f3-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-986">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-987">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-988">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-989">0,00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-990">30.00</span><span class="sxs-lookup"><span data-stu-id="ee9f3-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-991">1000</span><span class="sxs-lookup"><span data-stu-id="ee9f3-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="ee9f3-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="ee9f3-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="ee9f3-994"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="ee9f3-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ee9f3-995">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="ee9f3-996">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="ee9f3-997">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="ee9f3-998">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="ee9f3-999">Részletesebb tájékoztatás: Költségösszesítési irányelv.</span><span class="sxs-lookup"><span data-stu-id="ee9f3-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="ee9f3-1000">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="ee9f3-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




