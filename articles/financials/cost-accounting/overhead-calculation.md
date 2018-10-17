---
title: "Járulékos költség számítása"
description: "Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le."
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
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
ms.sourcegitcommit: 12ae99c15bafcd9cc08b30903fe3f251f446b17d
ms.openlocfilehash: 4de705324ac497cfb11fae3dadc6f57d038fd0b5
ms.contentlocale: hu-hu
ms.lasthandoff: 10/05/2018

---

# <a name="overhead-calculation"></a><span data-ttu-id="03e0c-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="03e0c-103">Overhead calculation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03e0c-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="03e0c-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="03e0c-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="03e0c-105">Term definition</span></span>
---------------

<span data-ttu-id="03e0c-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="03e0c-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="03e0c-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="03e0c-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="03e0c-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="03e0c-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="03e0c-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="03e0c-109">Rent</span></span>
-   <span data-ttu-id="03e0c-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-110">Electricity</span></span>
-   <span data-ttu-id="03e0c-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="03e0c-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="03e0c-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="03e0c-112">Overhead calculation overview</span></span>
<span data-ttu-id="03e0c-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="03e0c-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="03e0c-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="03e0c-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="03e0c-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="03e0c-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="03e0c-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="03e0c-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="03e0c-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="03e0c-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="03e0c-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="03e0c-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="03e0c-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="03e0c-119">Version type</span></span>
-   <span data-ttu-id="03e0c-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="03e0c-120">Date and time</span></span>
-   <span data-ttu-id="03e0c-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="03e0c-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="03e0c-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="03e0c-122">Fiscal year</span></span>
-   <span data-ttu-id="03e0c-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-123">Fiscal period</span></span>

<span data-ttu-id="03e0c-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="03e0c-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="03e0c-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="03e0c-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="03e0c-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="03e0c-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="03e0c-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="03e0c-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="03e0c-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="03e0c-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="03e0c-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="03e0c-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="03e0c-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="03e0c-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="03e0c-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="03e0c-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="03e0c-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="03e0c-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="03e0c-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="03e0c-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="03e0c-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="03e0c-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="03e0c-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="03e0c-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="03e0c-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="03e0c-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="03e0c-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="03e0c-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="03e0c-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="03e0c-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="03e0c-140">Main account</span></span></th>
<th><span data-ttu-id="03e0c-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="03e0c-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="03e0c-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="03e0c-143">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-143">CC099</span></span></td>
<td><span data-ttu-id="03e0c-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-144">Default cost center</span></span></td>
<td><span data-ttu-id="03e0c-145">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-145">10001</span></span></td>
<td><span data-ttu-id="03e0c-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-146">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="03e0c-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="03e0c-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="03e0c-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="03e0c-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="03e0c-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="03e0c-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="03e0c-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="03e0c-151">Define the cost behavior rule</span></span>

<span data-ttu-id="03e0c-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="03e0c-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="03e0c-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="03e0c-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="03e0c-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="03e0c-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="03e0c-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="03e0c-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="03e0c-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="03e0c-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="03e0c-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="03e0c-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="03e0c-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="03e0c-159">Napló</span><span class="sxs-lookup"><span data-stu-id="03e0c-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="03e0c-160">Napló</span><span class="sxs-lookup"><span data-stu-id="03e0c-160">Journal</span></span></th>
<th><span data-ttu-id="03e0c-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="03e0c-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="03e0c-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="03e0c-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="03e0c-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-164">00001</span><span class="sxs-lookup"><span data-stu-id="03e0c-164">00001</span></span></td>
<td><span data-ttu-id="03e0c-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="03e0c-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="03e0c-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="03e0c-166">Fiscal</span></span></td>
<td><span data-ttu-id="03e0c-167">2017</span><span class="sxs-lookup"><span data-stu-id="03e0c-167">2017</span></span></td>
<td><span data-ttu-id="03e0c-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-168">Period 1</span></span></td>
<td><span data-ttu-id="03e0c-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="03e0c-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="03e0c-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="03e0c-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="03e0c-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="03e0c-173">Cost element</span></span></th>
<th><span data-ttu-id="03e0c-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-174">Cost behavior</span></span></th>
<th><span data-ttu-id="03e0c-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="03e0c-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="03e0c-177">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-177">CC099</span></span></td>
<td><span data-ttu-id="03e0c-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-178">Default cost center</span></span></td>
<td><span data-ttu-id="03e0c-179">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-179">10001</span></span></td>
<td><span data-ttu-id="03e0c-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-180">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="03e0c-181">Unclassified</span></span></td>
<td><span data-ttu-id="03e0c-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="03e0c-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="03e0c-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="03e0c-185">Cost element</span></span></th>
<th><span data-ttu-id="03e0c-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-186">Cost behavior</span></span></th>
<th><span data-ttu-id="03e0c-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-187">Amount</span></span></th>
<th><span data-ttu-id="03e0c-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="03e0c-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-189">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-189">CC099</span></span></td>
<td><span data-ttu-id="03e0c-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-190">Default cost center</span></span></td>
<td><span data-ttu-id="03e0c-191">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-191">10001</span></span></td>
<td><span data-ttu-id="03e0c-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-192">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="03e0c-193">Unclassified</span></span></td>
<td><span data-ttu-id="03e0c-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-194">10,000.00</span></span></td>
<td><span data-ttu-id="03e0c-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="03e0c-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-196">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-196">CC099</span></span></td>
<td><span data-ttu-id="03e0c-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-197">Default cost center</span></span></td>
<td><span data-ttu-id="03e0c-198">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-198">10001</span></span></td>
<td><span data-ttu-id="03e0c-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-199">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="03e0c-200">Unclassified</span></span></td>
<td><span data-ttu-id="03e0c-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-201">-10,000.00</span></span></td>
<td><span data-ttu-id="03e0c-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-203">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-203">CC099</span></span></td>
<td><span data-ttu-id="03e0c-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-204">Default cost center</span></span></td>
<td><span data-ttu-id="03e0c-205">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-205">10001</span></span></td>
<td><span data-ttu-id="03e0c-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-206">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-207">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-208">1,000.00</span></span></td>
<td><span data-ttu-id="03e0c-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-210">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-210">CC099</span></span></td>
<td><span data-ttu-id="03e0c-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-211">Default cost center</span></span></td>
<td><span data-ttu-id="03e0c-212">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-212">10001</span></span></td>
<td><span data-ttu-id="03e0c-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-213">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-214">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-215">9,000.00</span></span></td>
<td><span data-ttu-id="03e0c-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-217">További információért lásd: [Költségviselkedési irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="03e0c-217">For more information, see [Create and assign a cost behavior policy to a cost control unit](tasks/create-assign-cost-behavior-policy-cost-control-unit.md).</span></span>
### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="03e0c-218">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="03e0c-218">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="03e0c-219">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="03e0c-219">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="03e0c-220">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="03e0c-220">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="03e0c-221">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="03e0c-221">Define the cost distribution rule</span></span>

<span data-ttu-id="03e0c-222">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="03e0c-222">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="03e0c-223">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="03e0c-223">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="03e0c-224">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="03e0c-224">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="03e0c-225">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="03e0c-225">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="03e0c-226">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="03e0c-226">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="03e0c-227">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="03e0c-227">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-228">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-228">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-229">Kwh</span><span class="sxs-lookup"><span data-stu-id="03e0c-229">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-230">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-230">CC001</span></span></td>
<td><span data-ttu-id="03e0c-231">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-231">HR</span></span></td>
<td><span data-ttu-id="03e0c-232">1000</span><span class="sxs-lookup"><span data-stu-id="03e0c-232">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-233">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-233">CC002</span></span></td>
<td><span data-ttu-id="03e0c-234">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-234">Finance</span></span></td>
<td><span data-ttu-id="03e0c-235">6,000</span><span class="sxs-lookup"><span data-stu-id="03e0c-235">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-236">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-236">CC003</span></span></td>
<td><span data-ttu-id="03e0c-237">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-237">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-238">0</span><span class="sxs-lookup"><span data-stu-id="03e0c-238">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-239">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="03e0c-239">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-240">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-240">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-241">Nagyság</span><span class="sxs-lookup"><span data-stu-id="03e0c-241">Magnitude</span></span></th>
<th><span data-ttu-id="03e0c-242">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="03e0c-242">Allocation factor</span></span></th>
<th><span data-ttu-id="03e0c-243">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-243">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-244">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-244">CC001</span></span></td>
<td><span data-ttu-id="03e0c-245">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-245">HR</span></span></td>
<td><span data-ttu-id="03e0c-246">1000</span><span class="sxs-lookup"><span data-stu-id="03e0c-246">1,000</span></span></td>
<td><span data-ttu-id="03e0c-247">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-247">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="03e0c-248">1,285.71</span><span class="sxs-lookup"><span data-stu-id="03e0c-248">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-249">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-249">CC002</span></span></td>
<td><span data-ttu-id="03e0c-250">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-250">Finance</span></span></td>
<td><span data-ttu-id="03e0c-251">6,000</span><span class="sxs-lookup"><span data-stu-id="03e0c-251">6,000</span></span></td>
<td><span data-ttu-id="03e0c-252">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-252">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="03e0c-253">7,714.29</span><span class="sxs-lookup"><span data-stu-id="03e0c-253">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-254">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-254">CC003</span></span></td>
<td><span data-ttu-id="03e0c-255">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-255">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-256">0</span><span class="sxs-lookup"><span data-stu-id="03e0c-256">0</span></span></td>
<td><span data-ttu-id="03e0c-257">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-257">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="03e0c-258">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-258">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-259">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="03e0c-259">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="03e0c-260">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: (Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="03e0c-260">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-261">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-261">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-262">Receptúra</span><span class="sxs-lookup"><span data-stu-id="03e0c-262">Formula</span></span></th>
<th><span data-ttu-id="03e0c-263">Nagyság</span><span class="sxs-lookup"><span data-stu-id="03e0c-263">Magnitude</span></span></th>
<th><span data-ttu-id="03e0c-264">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="03e0c-264">Allocation factor</span></span></th>
<th><span data-ttu-id="03e0c-265">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-265">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-266">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-266">CC001</span></span></td>
<td><span data-ttu-id="03e0c-267">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-267">HR</span></span></td>
<td><span data-ttu-id="03e0c-268">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="03e0c-268">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="03e0c-269">1</span><span class="sxs-lookup"><span data-stu-id="03e0c-269">1</span></span></td>
<td><span data-ttu-id="03e0c-270">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-270">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="03e0c-271">500.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-271">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-272">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-272">CC002</span></span></td>
<td><span data-ttu-id="03e0c-273">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-273">Finance</span></span></td>
<td><span data-ttu-id="03e0c-274">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="03e0c-274">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="03e0c-275">1</span><span class="sxs-lookup"><span data-stu-id="03e0c-275">1</span></span></td>
<td><span data-ttu-id="03e0c-276">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-276">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="03e0c-277">500.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-277">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-278">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-278">CC003</span></span></td>
<td><span data-ttu-id="03e0c-279">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-279">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-280">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="03e0c-280">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="03e0c-281">0</span><span class="sxs-lookup"><span data-stu-id="03e0c-281">0</span></span></td>
<td><span data-ttu-id="03e0c-282">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-282">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="03e0c-283">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-283">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="03e0c-284">Napló</span><span class="sxs-lookup"><span data-stu-id="03e0c-284">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="03e0c-285">Napló</span><span class="sxs-lookup"><span data-stu-id="03e0c-285">Journal</span></span></th>
<th><span data-ttu-id="03e0c-286">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="03e0c-286">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="03e0c-287">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-287">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="03e0c-288">Verzió</span><span class="sxs-lookup"><span data-stu-id="03e0c-288">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-289">00002</span><span class="sxs-lookup"><span data-stu-id="03e0c-289">00002</span></span></td>
<td><span data-ttu-id="03e0c-290">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="03e0c-290">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="03e0c-291">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="03e0c-291">Fiscal</span></span></td>
<td><span data-ttu-id="03e0c-292">2017</span><span class="sxs-lookup"><span data-stu-id="03e0c-292">2017</span></span></td>
<td><span data-ttu-id="03e0c-293">1. időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-293">Period 1</span></span></td>
<td><span data-ttu-id="03e0c-294">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-294">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="03e0c-295">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="03e0c-295">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="03e0c-296">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="03e0c-296">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-297">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-297">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-298">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="03e0c-298">Cost element</span></span></th>
<th><span data-ttu-id="03e0c-299">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-299">Cost behavior</span></span></th>
<th><span data-ttu-id="03e0c-300">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-300">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-301">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-301">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-302">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-302">CC099</span></span></td>
<td><span data-ttu-id="03e0c-303">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-303">Default cost center</span></span></td>
<td><span data-ttu-id="03e0c-304">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-304">10001</span></span></td>
<td><span data-ttu-id="03e0c-305">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-305">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-306">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-306">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-307">1000,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-307">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-308">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-308">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-309">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-309">CC099</span></span></td>
<td><span data-ttu-id="03e0c-310">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-310">Default cost center</span></span></td>
<td><span data-ttu-id="03e0c-311">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-311">10001</span></span></td>
<td><span data-ttu-id="03e0c-312">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-312">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-313">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-313">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-314">9,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-314">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="03e0c-315">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="03e0c-315">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-316">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-316">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-317">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="03e0c-317">Cost element</span></span></th>
<th><span data-ttu-id="03e0c-318">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-318">Cost behavior</span></span></th>
<th><span data-ttu-id="03e0c-319">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-319">Amount</span></span></th>
<th><span data-ttu-id="03e0c-320">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="03e0c-320">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-321">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-321">CC099</span></span></td>
<td><span data-ttu-id="03e0c-322">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-322">Default cost center</span></span></td>
<td><span data-ttu-id="03e0c-323">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-323">10001</span></span></td>
<td><span data-ttu-id="03e0c-324">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-324">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-325">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-325">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-326">-1000,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-326">-1,000.00</span></span></td>
<td><span data-ttu-id="03e0c-327">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-327">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-328">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-328">CC001</span></span></td>
<td><span data-ttu-id="03e0c-329">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-329">HR</span></span></td>
<td><span data-ttu-id="03e0c-330">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-330">10001</span></span></td>
<td><span data-ttu-id="03e0c-331">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-331">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-332">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-332">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-333">500.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-333">500.00</span></span></td>
<td><span data-ttu-id="03e0c-334">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-334">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-335">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-335">CC002</span></span></td>
<td><span data-ttu-id="03e0c-336">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-336">Finance</span></span></td>
<td><span data-ttu-id="03e0c-337">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-337">10001</span></span></td>
<td><span data-ttu-id="03e0c-338">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-338">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-339">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-339">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-340">500.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-340">500.00</span></span></td>
<td><span data-ttu-id="03e0c-341">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-341">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-342">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-342">CC099</span></span></td>
<td><span data-ttu-id="03e0c-343">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="03e0c-343">Default cost center</span></span></td>
<td><span data-ttu-id="03e0c-344">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-344">10001</span></span></td>
<td><span data-ttu-id="03e0c-345">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-345">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-346">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-346">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-347">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-347">-9,000.00</span></span></td>
<td><span data-ttu-id="03e0c-348">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-348">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-349">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-349">CC001</span></span></td>
<td><span data-ttu-id="03e0c-350">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-350">HR</span></span></td>
<td><span data-ttu-id="03e0c-351">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-351">10001</span></span></td>
<td><span data-ttu-id="03e0c-352">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-352">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-353">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-353">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-354">1,285.71</span><span class="sxs-lookup"><span data-stu-id="03e0c-354">1,285.71</span></span></td>
<td><span data-ttu-id="03e0c-355">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-355">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-356">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-356">CC002</span></span></td>
<td><span data-ttu-id="03e0c-357">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-357">Finance</span></span></td>
<td><span data-ttu-id="03e0c-358">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-358">10001</span></span></td>
<td><span data-ttu-id="03e0c-359">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-359">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-360">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-360">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-361">7,714.29</span><span class="sxs-lookup"><span data-stu-id="03e0c-361">7,714.29</span></span></td>
<td><span data-ttu-id="03e0c-362">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-362">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-363">További információért lásd: [Költségelosztási irányelv létrehozása egy költségellenőrző-egységhez](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span><span class="sxs-lookup"><span data-stu-id="03e0c-363">For more information, see [Create and assign a cost distribution policy to a cost control unit](tasks/create-assign-cost-distribution-policy-cost-control-unit.md).</span></span> 

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="03e0c-364">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="03e0c-364">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="03e0c-365">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="03e0c-365">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="03e0c-366">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="03e0c-366">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="03e0c-367">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="03e0c-367">Define the overhead rate</span></span>

<span data-ttu-id="03e0c-368">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="03e0c-368">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="03e0c-369">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="03e0c-369">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-370">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-370">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-371">óra</span><span class="sxs-lookup"><span data-stu-id="03e0c-371">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-372">Proj 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-372">Proj 1</span></span></td>
<td><span data-ttu-id="03e0c-373">1. projekt</span><span class="sxs-lookup"><span data-stu-id="03e0c-373">Project 1</span></span></td>
<td><span data-ttu-id="03e0c-374">3</span><span class="sxs-lookup"><span data-stu-id="03e0c-374">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-375">Proj 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-375">Proj 2</span></span></td>
<td><span data-ttu-id="03e0c-376">2. projekt</span><span class="sxs-lookup"><span data-stu-id="03e0c-376">Project 2</span></span></td>
<td><span data-ttu-id="03e0c-377">1</span><span class="sxs-lookup"><span data-stu-id="03e0c-377">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-378">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="03e0c-378">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-379">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-379">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-380">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="03e0c-380">Cost element</span></span></th>
<th><span data-ttu-id="03e0c-381">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-381">Cost behavior</span></span></th>
<th><span data-ttu-id="03e0c-382">Egységek</span><span class="sxs-lookup"><span data-stu-id="03e0c-382">Units</span></span></th>
<th><span data-ttu-id="03e0c-383">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="03e0c-383">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-384">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-384">CC001</span></span></td>
<td><span data-ttu-id="03e0c-385">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-385">HR</span></span></td>
<td><span data-ttu-id="03e0c-386">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-386">10001</span></span></td>
<td><span data-ttu-id="03e0c-387">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-387">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-388">1</span><span class="sxs-lookup"><span data-stu-id="03e0c-388">1</span></span></td>
<td><span data-ttu-id="03e0c-389">10</span><span class="sxs-lookup"><span data-stu-id="03e0c-389">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-390">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="03e0c-390">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-391">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-391">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-392">Nagyság</span><span class="sxs-lookup"><span data-stu-id="03e0c-392">Magnitude</span></span></th>
<th><span data-ttu-id="03e0c-393">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="03e0c-393">Cost element</span></span></th>
<th><span data-ttu-id="03e0c-394">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="03e0c-394">Allocation factor</span></span></th>
<th><span data-ttu-id="03e0c-395">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-395">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-396">Proj 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-396">Proj 1</span></span></td>
<td><span data-ttu-id="03e0c-397">1. projekt</span><span class="sxs-lookup"><span data-stu-id="03e0c-397">Project 1</span></span></td>
<td><span data-ttu-id="03e0c-398">3</span><span class="sxs-lookup"><span data-stu-id="03e0c-398">3</span></span></td>
<td><span data-ttu-id="03e0c-399">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-399">10001</span></span></td>
<td><span data-ttu-id="03e0c-400">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-400">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="03e0c-401">30.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-401">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-402">Proj 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-402">Proj 2</span></span></td>
<td><span data-ttu-id="03e0c-403">2. projekt</span><span class="sxs-lookup"><span data-stu-id="03e0c-403">Project 2</span></span></td>
<td><span data-ttu-id="03e0c-404">1</span><span class="sxs-lookup"><span data-stu-id="03e0c-404">1</span></span></td>
<td><span data-ttu-id="03e0c-405">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-405">10001</span></span></td>
<td><span data-ttu-id="03e0c-406">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-406">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="03e0c-407">10.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-407">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="03e0c-408">Napló</span><span class="sxs-lookup"><span data-stu-id="03e0c-408">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="03e0c-409">Napló</span><span class="sxs-lookup"><span data-stu-id="03e0c-409">Journal</span></span></th>
<th><span data-ttu-id="03e0c-410">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="03e0c-410">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="03e0c-411">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-411">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="03e0c-412">Verzió</span><span class="sxs-lookup"><span data-stu-id="03e0c-412">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-413">00003</span><span class="sxs-lookup"><span data-stu-id="03e0c-413">00003</span></span></td>
<td><span data-ttu-id="03e0c-414">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="03e0c-414">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="03e0c-415">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="03e0c-415">Fiscal</span></span></td>
<td><span data-ttu-id="03e0c-416">2017</span><span class="sxs-lookup"><span data-stu-id="03e0c-416">2017</span></span></td>
<td><span data-ttu-id="03e0c-417">1. időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-417">Period 1</span></span></td>
<td><span data-ttu-id="03e0c-418">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-418">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="03e0c-419">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="03e0c-419">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="03e0c-420">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="03e0c-420">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-421">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-421">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-422">Nagyság</span><span class="sxs-lookup"><span data-stu-id="03e0c-422">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-423">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-423">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-424">Proj 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-424">Proj 1</span></span></td>
<td><span data-ttu-id="03e0c-425">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-425">Internal Proj 1</span></span></td>
<td><span data-ttu-id="03e0c-426">3,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-426">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-427">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-427">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-428">Proj 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-428">Proj 2</span></span></td>
<td><span data-ttu-id="03e0c-429">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-429">Internal Proj 2</span></span></td>
<td><span data-ttu-id="03e0c-430">1.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-430">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="03e0c-431">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="03e0c-431">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-432">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-432">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-433">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="03e0c-433">Cost element</span></span></th>
<th><span data-ttu-id="03e0c-434">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-434">Cost behavior</span></span></th>
<th><span data-ttu-id="03e0c-435">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-435">Amount</span></span></th>
<th><span data-ttu-id="03e0c-436">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="03e0c-436">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-437">CC0001</span><span class="sxs-lookup"><span data-stu-id="03e0c-437">CC0001</span></span></td>
<td><span data-ttu-id="03e0c-438">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-438">HR</span></span></td>
<td><span data-ttu-id="03e0c-439">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-439">10001</span></span></td>
<td><span data-ttu-id="03e0c-440">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-440">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-441">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-441">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-442">-30.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-442">-30.00</span></span></td>
<td><span data-ttu-id="03e0c-443">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-443">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-444">Proj 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-444">Proj 1</span></span></td>
<td><span data-ttu-id="03e0c-445">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-445">Internal Proj 1</span></span></td>
<td><span data-ttu-id="03e0c-446">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-446">10001</span></span></td>
<td><span data-ttu-id="03e0c-447">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-447">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-448">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-448">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-449">30.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-449">30.00</span></span></td>
<td><span data-ttu-id="03e0c-450">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-450">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-451">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-451">CC001</span></span></td>
<td><span data-ttu-id="03e0c-452">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-452">HR</span></span></td>
<td><span data-ttu-id="03e0c-453">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-453">10001</span></span></td>
<td><span data-ttu-id="03e0c-454">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-454">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-455">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-455">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-456">-10,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-456">-10.00</span></span></td>
<td><span data-ttu-id="03e0c-457">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-457">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-458">Proj 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-458">Proj 2</span></span></td>
<td><span data-ttu-id="03e0c-459">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-459">Internal Proj 2</span></span></td>
<td><span data-ttu-id="03e0c-460">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-460">10001</span></span></td>
<td><span data-ttu-id="03e0c-461">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-461">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-462">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-462">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-463">10,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-463">10.00</span></span></td>
<td><span data-ttu-id="03e0c-464">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-464">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-465">További információ: [Járulékosköltség-számítás végrehajtása](cost-rollup.md#perform-overhead-calculation).</span><span class="sxs-lookup"><span data-stu-id="03e0c-465">For more information, see [Perform overhead calculation](cost-rollup.md#perform-overhead-calculation).</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="03e0c-466">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="03e0c-466">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="03e0c-467">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="03e0c-467">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="03e0c-468">A Finance and Operations a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="03e0c-468">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="03e0c-469">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="03e0c-469">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="03e0c-470">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="03e0c-470">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="03e0c-471">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="03e0c-471">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="03e0c-472">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="03e0c-472">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="03e0c-473">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="03e0c-473">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="03e0c-474">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="03e0c-474">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="03e0c-475">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="03e0c-475">Define the cost allocation</span></span>

<span data-ttu-id="03e0c-476">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="03e0c-476">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="03e0c-477">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="03e0c-477">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="03e0c-478">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="03e0c-478">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-479">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-479">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-480">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="03e0c-480">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-481">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-481">CC002</span></span></td>
<td><span data-ttu-id="03e0c-482">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-482">Finance</span></span></td>
<td><span data-ttu-id="03e0c-483">35</span><span class="sxs-lookup"><span data-stu-id="03e0c-483">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-484">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-484">CC003</span></span></td>
<td><span data-ttu-id="03e0c-485">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-485">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-486">55</span><span class="sxs-lookup"><span data-stu-id="03e0c-486">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-487">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-487">CC004</span></span></td>
<td><span data-ttu-id="03e0c-488">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-488">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-489">10</span><span class="sxs-lookup"><span data-stu-id="03e0c-489">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-490">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="03e0c-490">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="03e0c-491">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="03e0c-491">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-492">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-492">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-493">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="03e0c-493">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-494">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-494">CC003</span></span></td>
<td><span data-ttu-id="03e0c-495">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-495">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-496">65</span><span class="sxs-lookup"><span data-stu-id="03e0c-496">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-497">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-497">CC004</span></span></td>
<td><span data-ttu-id="03e0c-498">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-498">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-499">35</span><span class="sxs-lookup"><span data-stu-id="03e0c-499">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-500">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="03e0c-500">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="03e0c-501">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="03e0c-501">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-502">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-502">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-503">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="03e0c-503">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-504">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-504">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-505">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-505">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-506">60</span><span class="sxs-lookup"><span data-stu-id="03e0c-506">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-507">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-507">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-508">2. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-508">Product 2</span></span></td>
<td><span data-ttu-id="03e0c-509">20</span><span class="sxs-lookup"><span data-stu-id="03e0c-509">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-510">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="03e0c-510">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="03e0c-511">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="03e0c-511">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-512">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-512">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-513">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="03e0c-513">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-514">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-514">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-515">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-515">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-516">80</span><span class="sxs-lookup"><span data-stu-id="03e0c-516">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-517">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-517">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-518">2. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-518">Product 2</span></span></td>
<td><span data-ttu-id="03e0c-519">15.</span><span class="sxs-lookup"><span data-stu-id="03e0c-519">15</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="03e0c-520">A Finance and Operations esetében a statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="03e0c-520">In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="03e0c-521">További információk: [Statisztikaimérték-szolgáltató sablon](statistical-measure-provider-template.md#statistical-measure-provider-template).</span><span class="sxs-lookup"><span data-stu-id="03e0c-521">For more information, see [Statistical measure provider template](statistical-measure-provider-template.md#statistical-measure-provider-template).</span></span> <span data-ttu-id="03e0c-522">Az alábbi táblázat azt az eredményt mutatja, amikor a HR szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="03e0c-522">The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-523">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-523">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-524">Nagyság</span><span class="sxs-lookup"><span data-stu-id="03e0c-524">Magnitude</span></span></th>
<th><span data-ttu-id="03e0c-525">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="03e0c-525">Allocation factor</span></span></th>
<th><span data-ttu-id="03e0c-526">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-526">Amount</span></span></th>
<th><span data-ttu-id="03e0c-527">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-527">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-528">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-528">CC002</span></span></td>
<td><span data-ttu-id="03e0c-529">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-529">Finance</span></span></td>
<td><span data-ttu-id="03e0c-530">35</span><span class="sxs-lookup"><span data-stu-id="03e0c-530">35</span></span></td>
<td><span data-ttu-id="03e0c-531">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-531">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="03e0c-532">175.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-532">175.00</span></span></td>
<td><span data-ttu-id="03e0c-533">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-533">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-534">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-534">CC003</span></span></td>
<td><span data-ttu-id="03e0c-535">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-535">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-536">55</span><span class="sxs-lookup"><span data-stu-id="03e0c-536">55</span></span></td>
<td><span data-ttu-id="03e0c-537">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-537">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="03e0c-538">275.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-538">275.00</span></span></td>
<td><span data-ttu-id="03e0c-539">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-539">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-540">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-540">CC004</span></span></td>
<td><span data-ttu-id="03e0c-541">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-541">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-542">10</span><span class="sxs-lookup"><span data-stu-id="03e0c-542">10</span></span></td>
<td><span data-ttu-id="03e0c-543">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-543">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="03e0c-544">50,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-544">50.00</span></span></td>
<td><span data-ttu-id="03e0c-545">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-545">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-546">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-546">CC002</span></span></td>
<td><span data-ttu-id="03e0c-547">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-547">Finance</span></span></td>
<td><span data-ttu-id="03e0c-548">35</span><span class="sxs-lookup"><span data-stu-id="03e0c-548">35</span></span></td>
<td><span data-ttu-id="03e0c-549">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="03e0c-549">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="03e0c-550">436.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-550">436.00</span></span></td>
<td><span data-ttu-id="03e0c-551">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-551">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-552">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-552">CC003</span></span></td>
<td><span data-ttu-id="03e0c-553">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-553">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-554">55</span><span class="sxs-lookup"><span data-stu-id="03e0c-554">55</span></span></td>
<td><span data-ttu-id="03e0c-555">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="03e0c-555">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="03e0c-556">685.14</span><span class="sxs-lookup"><span data-stu-id="03e0c-556">685.14</span></span></td>
<td><span data-ttu-id="03e0c-557">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-557">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-558">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-558">CC004</span></span></td>
<td><span data-ttu-id="03e0c-559">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-559">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-560">10</span><span class="sxs-lookup"><span data-stu-id="03e0c-560">10</span></span></td>
<td><span data-ttu-id="03e0c-561">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="03e0c-561">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="03e0c-562">124.57</span><span class="sxs-lookup"><span data-stu-id="03e0c-562">124.57</span></span></td>
<td><span data-ttu-id="03e0c-563">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-563">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-564">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="03e0c-564">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-565">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-565">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-566">Nagyság</span><span class="sxs-lookup"><span data-stu-id="03e0c-566">Magnitude</span></span></th>
<th><span data-ttu-id="03e0c-567">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="03e0c-567">Allocation factor</span></span></th>
<th><span data-ttu-id="03e0c-568">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-568">Amount</span></span></th>
<th><span data-ttu-id="03e0c-569">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-569">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-570">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-570">CC003</span></span></td>
<td><span data-ttu-id="03e0c-571">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-571">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-572">65</span><span class="sxs-lookup"><span data-stu-id="03e0c-572">65</span></span></td>
<td><span data-ttu-id="03e0c-573">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="03e0c-573">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="03e0c-574">438.75</span><span class="sxs-lookup"><span data-stu-id="03e0c-574">438.75</span></span></td>
<td><span data-ttu-id="03e0c-575">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-575">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-576">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-576">CC004</span></span></td>
<td><span data-ttu-id="03e0c-577">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-577">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-578">35</span><span class="sxs-lookup"><span data-stu-id="03e0c-578">35</span></span></td>
<td><span data-ttu-id="03e0c-579">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="03e0c-579">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="03e0c-580">236.25</span><span class="sxs-lookup"><span data-stu-id="03e0c-580">236.25</span></span></td>
<td><span data-ttu-id="03e0c-581">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-581">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-582">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-582">CC003</span></span></td>
<td><span data-ttu-id="03e0c-583">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-583">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-584">65</span><span class="sxs-lookup"><span data-stu-id="03e0c-584">65</span></span></td>
<td><span data-ttu-id="03e0c-585">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="03e0c-585">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="03e0c-586">5,297.69</span><span class="sxs-lookup"><span data-stu-id="03e0c-586">5,297.69</span></span></td>
<td><span data-ttu-id="03e0c-587">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-587">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-588">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-588">CC004</span></span></td>
<td><span data-ttu-id="03e0c-589">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-589">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-590">35</span><span class="sxs-lookup"><span data-stu-id="03e0c-590">35</span></span></td>
<td><span data-ttu-id="03e0c-591">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="03e0c-591">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="03e0c-592">2,852.60</span><span class="sxs-lookup"><span data-stu-id="03e0c-592">2,852.60</span></span></td>
<td><span data-ttu-id="03e0c-593">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-593">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-594">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="03e0c-594">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-595">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-595">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-596">Nagyság</span><span class="sxs-lookup"><span data-stu-id="03e0c-596">Magnitude</span></span></th>
<th><span data-ttu-id="03e0c-597">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="03e0c-597">Allocation factor</span></span></th>
<th><span data-ttu-id="03e0c-598">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-598">Amount</span></span></th>
<th><span data-ttu-id="03e0c-599">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-599">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-600">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-600">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-601">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-601">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-602">60</span><span class="sxs-lookup"><span data-stu-id="03e0c-602">60</span></span></td>
<td><span data-ttu-id="03e0c-603">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="03e0c-603">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="03e0c-604">535.31</span><span class="sxs-lookup"><span data-stu-id="03e0c-604">535.31</span></span></td>
<td><span data-ttu-id="03e0c-605">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-605">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-606">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-606">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-607">2. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-607">Product 2</span></span></td>
<td><span data-ttu-id="03e0c-608">20</span><span class="sxs-lookup"><span data-stu-id="03e0c-608">20</span></span></td>
<td><span data-ttu-id="03e0c-609">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="03e0c-609">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="03e0c-610">178.44</span><span class="sxs-lookup"><span data-stu-id="03e0c-610">178.44</span></span></td>
<td><span data-ttu-id="03e0c-611">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-611">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-612">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-612">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-613">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-613">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-614">60</span><span class="sxs-lookup"><span data-stu-id="03e0c-614">60</span></span></td>
<td><span data-ttu-id="03e0c-615">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="03e0c-615">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="03e0c-616">4,487.12</span><span class="sxs-lookup"><span data-stu-id="03e0c-616">4,487.12</span></span></td>
<td><span data-ttu-id="03e0c-617">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-617">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-618">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-618">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-619">2. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-619">Product 2</span></span></td>
<td><span data-ttu-id="03e0c-620">20</span><span class="sxs-lookup"><span data-stu-id="03e0c-620">20</span></span></td>
<td><span data-ttu-id="03e0c-621">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="03e0c-621">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="03e0c-622">1,495.71</span><span class="sxs-lookup"><span data-stu-id="03e0c-622">1,495.71</span></span></td>
<td><span data-ttu-id="03e0c-623">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-623">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="03e0c-624">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="03e0c-624">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-625">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-625">Cost object</span></span></th>
<th><span data-ttu-id="03e0c-626">Nagyság</span><span class="sxs-lookup"><span data-stu-id="03e0c-626">Magnitude</span></span></th>
<th><span data-ttu-id="03e0c-627">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="03e0c-627">Allocation factor</span></span></th>
<th><span data-ttu-id="03e0c-628">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-628">Amount</span></span></th>
<th><span data-ttu-id="03e0c-629">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-629">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-630">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-630">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-631">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-631">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-632">80</span><span class="sxs-lookup"><span data-stu-id="03e0c-632">80</span></span></td>
<td><span data-ttu-id="03e0c-633">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="03e0c-633">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="03e0c-634">241.05</span><span class="sxs-lookup"><span data-stu-id="03e0c-634">241.05</span></span></td>
<td><span data-ttu-id="03e0c-635">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-635">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-636">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-636">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-637">2. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-637">Product 2</span></span></td>
<td><span data-ttu-id="03e0c-638">15.</span><span class="sxs-lookup"><span data-stu-id="03e0c-638">15</span></span></td>
<td><span data-ttu-id="03e0c-639">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="03e0c-639">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="03e0c-640">45.20</span><span class="sxs-lookup"><span data-stu-id="03e0c-640">45.20</span></span></td>
<td><span data-ttu-id="03e0c-641">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-641">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-642">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-642">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-643">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-643">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-644">80</span><span class="sxs-lookup"><span data-stu-id="03e0c-644">80</span></span></td>
<td><span data-ttu-id="03e0c-645">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="03e0c-645">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="03e0c-646">2,507.09</span><span class="sxs-lookup"><span data-stu-id="03e0c-646">2,507.09</span></span></td>
<td><span data-ttu-id="03e0c-647">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-647">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-648">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-648">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-649">2. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-649">Product 2</span></span></td>
<td><span data-ttu-id="03e0c-650">15.</span><span class="sxs-lookup"><span data-stu-id="03e0c-650">15</span></span></td>
<td><span data-ttu-id="03e0c-651">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="03e0c-651">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="03e0c-652">470.08</span><span class="sxs-lookup"><span data-stu-id="03e0c-652">470.08</span></span></td>
<td><span data-ttu-id="03e0c-653">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-653">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="03e0c-654">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="03e0c-654">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="03e0c-655">Napló</span><span class="sxs-lookup"><span data-stu-id="03e0c-655">Journal</span></span></th>
<th><span data-ttu-id="03e0c-656">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="03e0c-656">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="03e0c-657">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-657">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="03e0c-658">Verzió</span><span class="sxs-lookup"><span data-stu-id="03e0c-658">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-659">00004</span><span class="sxs-lookup"><span data-stu-id="03e0c-659">00004</span></span></td>
<td><span data-ttu-id="03e0c-660">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="03e0c-660">Cost allocation journal</span></span></td>
<td><span data-ttu-id="03e0c-661">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="03e0c-661">Fiscal</span></span></td>
<td><span data-ttu-id="03e0c-662">2017</span><span class="sxs-lookup"><span data-stu-id="03e0c-662">2017</span></span></td>
<td><span data-ttu-id="03e0c-663">1. időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-663">Period 1</span></span></td>
<td><span data-ttu-id="03e0c-664">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="03e0c-664">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="03e0c-665">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="03e0c-665">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="03e0c-666">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="03e0c-666">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-667">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-667">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-668">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="03e0c-668">Cost element</span></span></th>
<th><span data-ttu-id="03e0c-669">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-669">Cost behavior</span></span></th>
<th><span data-ttu-id="03e0c-670">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-670">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-671">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-671">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-672">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-672">CC001</span></span></td>
<td><span data-ttu-id="03e0c-673">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-673">HR</span></span></td>
<td><span data-ttu-id="03e0c-674">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-674">10001</span></span></td>
<td><span data-ttu-id="03e0c-675">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-675">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-676">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-676">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-677">500.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-677">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-678">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-678">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-679">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-679">CC001</span></span></td>
<td><span data-ttu-id="03e0c-680">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-680">HR</span></span></td>
<td><span data-ttu-id="03e0c-681">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-681">10001</span></span></td>
<td><span data-ttu-id="03e0c-682">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-682">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-683">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-683">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-684">1,245.71</span><span class="sxs-lookup"><span data-stu-id="03e0c-684">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-685">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-685">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-686">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-686">CC002</span></span></td>
<td><span data-ttu-id="03e0c-687">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-687">Finance</span></span></td>
<td><span data-ttu-id="03e0c-688">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-688">10001</span></span></td>
<td><span data-ttu-id="03e0c-689">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-689">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-690">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-690">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-691">675.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-691">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-692">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-692">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-693">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-693">CC002</span></span></td>
<td><span data-ttu-id="03e0c-694">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-694">Finance</span></span></td>
<td><span data-ttu-id="03e0c-695">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-695">10001</span></span></td>
<td><span data-ttu-id="03e0c-696">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-696">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-697">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-697">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-698">8,150.29</span><span class="sxs-lookup"><span data-stu-id="03e0c-698">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-699">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-699">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-700">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-700">CC003</span></span></td>
<td><span data-ttu-id="03e0c-701">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-701">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-702">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-702">10001</span></span></td>
<td><span data-ttu-id="03e0c-703">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-703">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-704">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-704">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-705">713.75</span><span class="sxs-lookup"><span data-stu-id="03e0c-705">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-706">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-706">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-707">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-707">CC003</span></span></td>
<td><span data-ttu-id="03e0c-708">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-708">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-709">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-709">10001</span></span></td>
<td><span data-ttu-id="03e0c-710">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-710">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-711">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-711">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-712">5,982.83</span><span class="sxs-lookup"><span data-stu-id="03e0c-712">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-713">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-713">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-714">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-714">CC003</span></span></td>
<td><span data-ttu-id="03e0c-715">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-715">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-716">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-716">10001</span></span></td>
<td><span data-ttu-id="03e0c-717">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-717">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-718">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-718">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-719">286.25</span><span class="sxs-lookup"><span data-stu-id="03e0c-719">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-720">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-720">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-721">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-721">CC003</span></span></td>
<td><span data-ttu-id="03e0c-722">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-722">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-723">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-723">10001</span></span></td>
<td><span data-ttu-id="03e0c-724">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-724">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-725">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-725">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-726">2,977.17</span><span class="sxs-lookup"><span data-stu-id="03e0c-726">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-727">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-727">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-728">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-728">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-729">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-729">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-730">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-730">10001</span></span></td>
<td><span data-ttu-id="03e0c-731">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-731">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-732">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-732">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-733">776.36</span><span class="sxs-lookup"><span data-stu-id="03e0c-733">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-734">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-734">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-735">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-735">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-736">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-736">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-737">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-737">10001</span></span></td>
<td><span data-ttu-id="03e0c-738">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-738">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-739">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-739">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-740">6,994.21</span><span class="sxs-lookup"><span data-stu-id="03e0c-740">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-741">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-741">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-742">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-742">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-743">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-743">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-744">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-744">10001</span></span></td>
<td><span data-ttu-id="03e0c-745">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-745">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-746">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-746">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-747">223.64</span><span class="sxs-lookup"><span data-stu-id="03e0c-747">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-748">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-748">January 31, 2017</span></span></td>
<td><span data-ttu-id="03e0c-749">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-749">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-750">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-750">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-751">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-751">10001</span></span></td>
<td><span data-ttu-id="03e0c-752">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-752">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-753">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-753">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-754">1,965.79</span><span class="sxs-lookup"><span data-stu-id="03e0c-754">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="03e0c-755">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="03e0c-755">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="03e0c-756">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-756">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="03e0c-757">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="03e0c-757">Cost element</span></span></th>
<th><span data-ttu-id="03e0c-758">Költség működése</span><span class="sxs-lookup"><span data-stu-id="03e0c-758">Cost behavior</span></span></th>
<th><span data-ttu-id="03e0c-759">Összeg</span><span class="sxs-lookup"><span data-stu-id="03e0c-759">Amount</span></span></th>
<th><span data-ttu-id="03e0c-760">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="03e0c-760">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="03e0c-761">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-761">CC001</span></span></td>
<td><span data-ttu-id="03e0c-762">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-762">HR</span></span></td>
<td><span data-ttu-id="03e0c-763">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-763">10001</span></span></td>
<td><span data-ttu-id="03e0c-764">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-764">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-765">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-765">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-766">-500,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-766">-500.00</span></span></td>
<td><span data-ttu-id="03e0c-767">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-767">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-768">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-768">CC002</span></span></td>
<td><span data-ttu-id="03e0c-769">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-769">Finance</span></span></td>
<td><span data-ttu-id="03e0c-770">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-770">10001</span></span></td>
<td><span data-ttu-id="03e0c-771">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-771">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-772">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-772">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-773">175.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-773">175.00</span></span></td>
<td><span data-ttu-id="03e0c-774">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-774">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-775">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-775">CC003</span></span></td>
<td><span data-ttu-id="03e0c-776">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-776">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-777">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-777">10001</span></span></td>
<td><span data-ttu-id="03e0c-778">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-778">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-779">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-779">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-780">275.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-780">275.00</span></span></td>
<td><span data-ttu-id="03e0c-781">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-781">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-782">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-782">CC004</span></span></td>
<td><span data-ttu-id="03e0c-783">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-783">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-784">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-784">10001</span></span></td>
<td><span data-ttu-id="03e0c-785">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-785">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-786">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-786">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-787">50,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-787">50,00</span></span></td>
<td><span data-ttu-id="03e0c-788">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-788">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-789">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-789">CC001</span></span></td>
<td><span data-ttu-id="03e0c-790">HR</span><span class="sxs-lookup"><span data-stu-id="03e0c-790">HR</span></span></td>
<td><span data-ttu-id="03e0c-791">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-791">10001</span></span></td>
<td><span data-ttu-id="03e0c-792">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-792">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-793">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-793">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-794">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="03e0c-794">-1,245.71</span></span></td>
<td><span data-ttu-id="03e0c-795">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-795">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-796">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-796">CC002</span></span></td>
<td><span data-ttu-id="03e0c-797">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-797">Finance</span></span></td>
<td><span data-ttu-id="03e0c-798">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-798">10001</span></span></td>
<td><span data-ttu-id="03e0c-799">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-799">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-800">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-800">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-801">436.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-801">436.00</span></span></td>
<td><span data-ttu-id="03e0c-802">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-802">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-803">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-803">CC003</span></span></td>
<td><span data-ttu-id="03e0c-804">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-804">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-805">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-805">10001</span></span></td>
<td><span data-ttu-id="03e0c-806">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-806">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-807">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-807">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-808">685.14</span><span class="sxs-lookup"><span data-stu-id="03e0c-808">685.14</span></span></td>
<td><span data-ttu-id="03e0c-809">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-809">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-810">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-810">CC004</span></span></td>
<td><span data-ttu-id="03e0c-811">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-811">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-812">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-812">10001</span></span></td>
<td><span data-ttu-id="03e0c-813">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-813">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-814">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-814">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-815">124.57</span><span class="sxs-lookup"><span data-stu-id="03e0c-815">124.57</span></span></td>
<td><span data-ttu-id="03e0c-816">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-816">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-817">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-817">CC002</span></span></td>
<td><span data-ttu-id="03e0c-818">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-818">Finance</span></span></td>
<td><span data-ttu-id="03e0c-819">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-819">10001</span></span></td>
<td><span data-ttu-id="03e0c-820">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-820">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-821">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-821">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-822">-675.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-822">-675.00</span></span></td>
<td><span data-ttu-id="03e0c-823">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-823">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-824">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-824">CC003</span></span></td>
<td><span data-ttu-id="03e0c-825">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-825">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-826">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-826">10001</span></span></td>
<td><span data-ttu-id="03e0c-827">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-827">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-828">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-828">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-829">438.75</span><span class="sxs-lookup"><span data-stu-id="03e0c-829">438.75</span></span></td>
<td><span data-ttu-id="03e0c-830">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-830">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-831">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-831">CC004</span></span></td>
<td><span data-ttu-id="03e0c-832">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-832">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-833">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-833">10001</span></span></td>
<td><span data-ttu-id="03e0c-834">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-834">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-835">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-835">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-836">236.25</span><span class="sxs-lookup"><span data-stu-id="03e0c-836">236.25</span></span></td>
<td><span data-ttu-id="03e0c-837">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-837">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-838">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-838">CC002</span></span></td>
<td><span data-ttu-id="03e0c-839">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="03e0c-839">Finance</span></span></td>
<td><span data-ttu-id="03e0c-840">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-840">10001</span></span></td>
<td><span data-ttu-id="03e0c-841">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-841">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-842">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-842">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-843">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="03e0c-843">-8,150.29</span></span></td>
<td><span data-ttu-id="03e0c-844">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-844">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-845">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-845">CC003</span></span></td>
<td><span data-ttu-id="03e0c-846">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-846">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-847">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-847">10001</span></span></td>
<td><span data-ttu-id="03e0c-848">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-848">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-849">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-849">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-850">5,297.69</span><span class="sxs-lookup"><span data-stu-id="03e0c-850">5,297.69</span></span></td>
<td><span data-ttu-id="03e0c-851">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-851">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-852">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-852">CC004</span></span></td>
<td><span data-ttu-id="03e0c-853">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="03e0c-853">Packaging</span></span></td>
<td><span data-ttu-id="03e0c-854">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-854">10001</span></span></td>
<td><span data-ttu-id="03e0c-855">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-855">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-856">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-856">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-857">2,852.60</span><span class="sxs-lookup"><span data-stu-id="03e0c-857">2,852.60</span></span></td>
<td><span data-ttu-id="03e0c-858">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-858">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-859">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-859">CC003</span></span></td>
<td><span data-ttu-id="03e0c-860">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-860">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-861">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-861">10001</span></span></td>
<td><span data-ttu-id="03e0c-862">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-862">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-863">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-863">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-864">-713.75</span><span class="sxs-lookup"><span data-stu-id="03e0c-864">-713.75</span></span></td>
<td><span data-ttu-id="03e0c-865">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-865">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-866">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-866">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-867">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-867">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-868">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-868">10001</span></span></td>
<td><span data-ttu-id="03e0c-869">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-869">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-870">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-870">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-871">535.31</span><span class="sxs-lookup"><span data-stu-id="03e0c-871">535.31</span></span></td>
<td><span data-ttu-id="03e0c-872">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-872">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-873">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-873">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-874">2. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-874">Product 2</span></span></td>
<td><span data-ttu-id="03e0c-875">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-875">10001</span></span></td>
<td><span data-ttu-id="03e0c-876">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-876">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-877">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-877">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-878">178.44</span><span class="sxs-lookup"><span data-stu-id="03e0c-878">178.44</span></span></td>
<td><span data-ttu-id="03e0c-879">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-879">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-880">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-880">CC003</span></span></td>
<td><span data-ttu-id="03e0c-881">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-881">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-882">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-882">10001</span></span></td>
<td><span data-ttu-id="03e0c-883">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-883">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-884">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-884">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-885">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="03e0c-885">-5,982.83</span></span></td>
<td><span data-ttu-id="03e0c-886">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-886">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-887">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-887">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-888">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-888">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-889">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-889">10001</span></span></td>
<td><span data-ttu-id="03e0c-890">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-890">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-891">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-891">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-892">4,487.12</span><span class="sxs-lookup"><span data-stu-id="03e0c-892">4,487.12</span></span></td>
<td><span data-ttu-id="03e0c-893">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-893">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-894">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-894">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-895">2. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-895">Product 2</span></span></td>
<td><span data-ttu-id="03e0c-896">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-896">10001</span></span></td>
<td><span data-ttu-id="03e0c-897">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-897">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-898">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-898">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-899">1,495.71</span><span class="sxs-lookup"><span data-stu-id="03e0c-899">1,495.71</span></span></td>
<td><span data-ttu-id="03e0c-900">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-900">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-901">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-901">CC003</span></span></td>
<td><span data-ttu-id="03e0c-902">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-902">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-903">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-903">10001</span></span></td>
<td><span data-ttu-id="03e0c-904">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-904">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-905">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-905">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-906">-286.25</span><span class="sxs-lookup"><span data-stu-id="03e0c-906">-286.25</span></span></td>
<td><span data-ttu-id="03e0c-907">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-907">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-908">Term 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-908">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-909">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-909">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-910">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-910">10001</span></span></td>
<td><span data-ttu-id="03e0c-911">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-911">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-912">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-912">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-913">241.05</span><span class="sxs-lookup"><span data-stu-id="03e0c-913">241.05</span></span></td>
<td><span data-ttu-id="03e0c-914">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-914">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-915">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-915">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-916">2. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-916">Product 2</span></span></td>
<td><span data-ttu-id="03e0c-917">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-917">10001</span></span></td>
<td><span data-ttu-id="03e0c-918">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-918">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-919">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-919">Fixed cost</span></span></td>
<td><span data-ttu-id="03e0c-920">45.20</span><span class="sxs-lookup"><span data-stu-id="03e0c-920">45.20</span></span></td>
<td><span data-ttu-id="03e0c-921">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-921">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-922">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-922">CC003</span></span></td>
<td><span data-ttu-id="03e0c-923">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="03e0c-923">Assembly</span></span></td>
<td><span data-ttu-id="03e0c-924">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-924">10001</span></span></td>
<td><span data-ttu-id="03e0c-925">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-925">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-926">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-926">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-927">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="03e0c-927">-2,977.17</span></span></td>
<td><span data-ttu-id="03e0c-928">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-928">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-929">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-929">Prod 1</span></span></td>
<td><span data-ttu-id="03e0c-930">1. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-930">Product 1</span></span></td>
<td><span data-ttu-id="03e0c-931">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-931">10001</span></span></td>
<td><span data-ttu-id="03e0c-932">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-932">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-933">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-933">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-934">2,507.09</span><span class="sxs-lookup"><span data-stu-id="03e0c-934">2,507.09</span></span></td>
<td><span data-ttu-id="03e0c-935">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-935">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="03e0c-936">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-936">Prod 2</span></span></td>
<td><span data-ttu-id="03e0c-937">2. termék</span><span class="sxs-lookup"><span data-stu-id="03e0c-937">Product 2</span></span></td>
<td><span data-ttu-id="03e0c-938">10001</span><span class="sxs-lookup"><span data-stu-id="03e0c-938">10001</span></span></td>
<td><span data-ttu-id="03e0c-939">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-939">Electricity</span></span></td>
<td><span data-ttu-id="03e0c-940">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-940">Variable cost</span></span></td>
<td><span data-ttu-id="03e0c-941">470.08</span><span class="sxs-lookup"><span data-stu-id="03e0c-941">470.08</span></span></td>
<td><span data-ttu-id="03e0c-942">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="03e0c-942">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="03e0c-943">Következtetés</span><span class="sxs-lookup"><span data-stu-id="03e0c-943">Conclusion</span></span>
<span data-ttu-id="03e0c-944">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="03e0c-944">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="03e0c-945">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="03e0c-945">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="03e0c-946">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="03e0c-946">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="03e0c-947">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="03e0c-947">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="03e0c-948">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="03e0c-948">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="03e0c-949">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="03e0c-949">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="03e0c-950">Összesen</span><span class="sxs-lookup"><span data-stu-id="03e0c-950">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="03e0c-951">CC099</span><span class="sxs-lookup"><span data-stu-id="03e0c-951">CC099</span></span></th>
<th><span data-ttu-id="03e0c-952">CC001</span><span class="sxs-lookup"><span data-stu-id="03e0c-952">CC001</span></span></th>
<th><span data-ttu-id="03e0c-953">CC002</span><span class="sxs-lookup"><span data-stu-id="03e0c-953">CC002</span></span></th>
<th><span data-ttu-id="03e0c-954">CC003</span><span class="sxs-lookup"><span data-stu-id="03e0c-954">CC003</span></span></th>
<th><span data-ttu-id="03e0c-955">CC004</span><span class="sxs-lookup"><span data-stu-id="03e0c-955">CC004</span></span></th>
<th><span data-ttu-id="03e0c-956">Proj 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-956">Proj 1</span></span></th>
<th><span data-ttu-id="03e0c-957">Proj 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-957">Proj 2</span></span></th>
<th><span data-ttu-id="03e0c-958">Term. 1</span><span class="sxs-lookup"><span data-stu-id="03e0c-958">Prod 1</span></span></th>
<th><span data-ttu-id="03e0c-959">Term. 2</span><span class="sxs-lookup"><span data-stu-id="03e0c-959">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="03e0c-960">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="03e0c-960">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-961"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-961"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-962"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-962"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-963"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-963"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-965"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-965"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-966"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-966"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-967"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-967"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-968"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-968"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-969"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-969"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="03e0c-970">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="03e0c-970">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-971">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-971">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="03e0c-972">Fix költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-972">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-973">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-973">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-974">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-974">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-975">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-975">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-976">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-977">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-977">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-978">776.36</span><span class="sxs-lookup"><span data-stu-id="03e0c-978">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-979">223.64</span><span class="sxs-lookup"><span data-stu-id="03e0c-979">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-980"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-980"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="03e0c-981">Változó költség</span><span class="sxs-lookup"><span data-stu-id="03e0c-981">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-982">000</span><span class="sxs-lookup"><span data-stu-id="03e0c-982">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-983">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-983">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-984">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-984">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-985">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-985">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-986">0,00</span><span class="sxs-lookup"><span data-stu-id="03e0c-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-987">30.00</span><span class="sxs-lookup"><span data-stu-id="03e0c-987">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-988">1000</span><span class="sxs-lookup"><span data-stu-id="03e0c-988">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-989">6,994.21</span><span class="sxs-lookup"><span data-stu-id="03e0c-989">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-990">1,965.79</span><span class="sxs-lookup"><span data-stu-id="03e0c-990">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="03e0c-991"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="03e0c-991"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="03e0c-992">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="03e0c-992">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="03e0c-993">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="03e0c-993">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="03e0c-994">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="03e0c-994">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="03e0c-995">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="03e0c-995">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="03e0c-996">Részletesebb tájékoztatás: [Költségösszesítési irányelv](cost-rollup.md).</span><span class="sxs-lookup"><span data-stu-id="03e0c-996">For more information, see [Cost roll-up](cost-rollup.md).</span></span>




