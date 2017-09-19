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
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 9e13fc9fa7e51a1299ca8698f581de979b680a7b
ms.openlocfilehash: a8c867ba49b95af2816fe8294059307e974c0a81
ms.contentlocale: hu-hu
ms.lasthandoff: 09/18/2017

---

# <a name="overhead-calculation"></a><span data-ttu-id="c0a4d-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="c0a4d-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c0a4d-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="c0a4d-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="c0a4d-105">Term definition</span></span>
---------------

<span data-ttu-id="c0a4d-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="c0a4d-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="c0a4d-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="c0a4d-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="c0a4d-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="c0a4d-109">Rent</span></span>
-   <span data-ttu-id="c0a4d-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-110">Electricity</span></span>
-   <span data-ttu-id="c0a4d-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="c0a4d-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="c0a4d-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-112">Overhead calculation overview</span></span>
<span data-ttu-id="c0a4d-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="c0a4d-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="c0a4d-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="c0a4d-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="c0a4d-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="c0a4d-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="c0a4d-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="c0a4d-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="c0a4d-119">Version type</span></span>
-   <span data-ttu-id="c0a4d-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-120">Date and time</span></span>
-   <span data-ttu-id="c0a4d-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="c0a4d-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="c0a4d-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="c0a4d-122">Fiscal year</span></span>
-   <span data-ttu-id="c0a4d-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-123">Fiscal period</span></span>

<span data-ttu-id="c0a4d-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="c0a4d-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="c0a4d-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="c0a4d-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="c0a4d-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="c0a4d-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="c0a4d-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-130">Therefore, you always have full traceability.</span></span> 
<span data-ttu-id="c0a4d-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="c0a4d-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="c0a4d-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="c0a4d-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="c0a4d-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="c0a4d-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="c0a4d-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="c0a4d-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c0a4d-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="c0a4d-140">Main account</span></span></th>
<th><span data-ttu-id="c0a4d-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="c0a4d-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-143">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-143">CC099</span></span></td>
<td><span data-ttu-id="c0a4d-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-144">Default cost center</span></span></td>
<td><span data-ttu-id="c0a4d-145">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-145">10001</span></span></td>
<td><span data-ttu-id="c0a4d-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-146">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="c0a4d-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="c0a4d-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="c0a4d-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="c0a4d-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="c0a4d-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="c0a4d-151">Define the cost behavior rule</span></span>

<span data-ttu-id="c0a4d-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="c0a4d-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="c0a4d-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="c0a4d-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="c0a4d-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="c0a4d-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="c0a4d-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="c0a4d-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="c0a4d-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="c0a4d-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="c0a4d-159">Napló</span><span class="sxs-lookup"><span data-stu-id="c0a4d-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c0a4d-160">Napló</span><span class="sxs-lookup"><span data-stu-id="c0a4d-160">Journal</span></span></th>
<th><span data-ttu-id="c0a4d-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="c0a4d-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c0a4d-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c0a4d-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="c0a4d-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-164">00001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-164">00001</span></span></td>
<td><span data-ttu-id="c0a4d-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="c0a4d-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="c0a4d-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="c0a4d-166">Fiscal</span></span></td>
<td><span data-ttu-id="c0a4d-167">2017</span><span class="sxs-lookup"><span data-stu-id="c0a4d-167">2017</span></span></td>
<td><span data-ttu-id="c0a4d-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-168">Period 1</span></span></td>
<td><span data-ttu-id="c0a4d-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c0a4d-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c0a4d-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-173">Cost element</span></span></th>
<th><span data-ttu-id="c0a4d-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-174">Cost behavior</span></span></th>
<th><span data-ttu-id="c0a4d-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-177">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-177">CC099</span></span></td>
<td><span data-ttu-id="c0a4d-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-178">Default cost center</span></span></td>
<td><span data-ttu-id="c0a4d-179">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-179">10001</span></span></td>
<td><span data-ttu-id="c0a4d-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-180">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="c0a4d-181">Unclassified</span></span></td>
<td><span data-ttu-id="c0a4d-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c0a4d-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="c0a4d-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-185">Cost element</span></span></th>
<th><span data-ttu-id="c0a4d-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-186">Cost behavior</span></span></th>
<th><span data-ttu-id="c0a4d-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-187">Amount</span></span></th>
<th><span data-ttu-id="c0a4d-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-189">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-189">CC099</span></span></td>
<td><span data-ttu-id="c0a4d-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-190">Default cost center</span></span></td>
<td><span data-ttu-id="c0a4d-191">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-191">10001</span></span></td>
<td><span data-ttu-id="c0a4d-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-192">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="c0a4d-193">Unclassified</span></span></td>
<td><span data-ttu-id="c0a4d-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-194">10,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-196">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-196">CC099</span></span></td>
<td><span data-ttu-id="c0a4d-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-197">Default cost center</span></span></td>
<td><span data-ttu-id="c0a4d-198">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-198">10001</span></span></td>
<td><span data-ttu-id="c0a4d-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-199">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="c0a4d-200">Unclassified</span></span></td>
<td><span data-ttu-id="c0a4d-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-201">-10,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-203">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-203">CC099</span></span></td>
<td><span data-ttu-id="c0a4d-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-204">Default cost center</span></span></td>
<td><span data-ttu-id="c0a4d-205">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-205">10001</span></span></td>
<td><span data-ttu-id="c0a4d-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-206">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-207">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-208">1,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-210">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-210">CC099</span></span></td>
<td><span data-ttu-id="c0a4d-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-211">Default cost center</span></span></td>
<td><span data-ttu-id="c0a4d-212">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-212">10001</span></span></td>
<td><span data-ttu-id="c0a4d-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-213">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-214">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-215">9,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-217">A költségműködéssel kapcsolatos részletes tudnivalókat lásd a Költségműködési irányelvekben.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="c0a4d-218">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="c0a4d-219">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="c0a4d-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="c0a4d-220">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="c0a4d-221">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="c0a4d-222">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="c0a4d-222">Define the cost distribution rule</span></span>

<span data-ttu-id="c0a4d-223">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="c0a4d-224">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="c0a4d-225">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="c0a4d-226">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="c0a4d-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="c0a4d-227">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="c0a4d-228">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-229">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-229">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="c0a4d-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-231">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-231">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-232">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-232">HR</span></span></td>
<td><span data-ttu-id="c0a4d-233">1000</span><span class="sxs-lookup"><span data-stu-id="c0a4d-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-234">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-234">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-235">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-235">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-236">6,000</span><span class="sxs-lookup"><span data-stu-id="c0a4d-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-237">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-237">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-238">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-238">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-239">0</span><span class="sxs-lookup"><span data-stu-id="c0a4d-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-240">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-241">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-241">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-242">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c0a4d-242">Magnitude</span></span></th>
<th><span data-ttu-id="c0a4d-243">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c0a4d-243">Allocation factor</span></span></th>
<th><span data-ttu-id="c0a4d-244">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-245">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-245">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-246">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-246">HR</span></span></td>
<td><span data-ttu-id="c0a4d-247">1000</span><span class="sxs-lookup"><span data-stu-id="c0a4d-247">1,000</span></span></td>
<td><span data-ttu-id="c0a4d-248">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c0a4d-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-250">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-250">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-251">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-251">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-252">6,000</span><span class="sxs-lookup"><span data-stu-id="c0a4d-252">6,000</span></span></td>
<td><span data-ttu-id="c0a4d-253">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c0a4d-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-255">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-255">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-256">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-256">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-257">0</span><span class="sxs-lookup"><span data-stu-id="c0a4d-257">0</span></span></td>
<td><span data-ttu-id="c0a4d-258">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-259">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-260">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="c0a4d-261">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: ((Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-262">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-262">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-263">Receptúra</span><span class="sxs-lookup"><span data-stu-id="c0a4d-263">Formula</span></span></th>
<th><span data-ttu-id="c0a4d-264">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c0a4d-264">Magnitude</span></span></th>
<th><span data-ttu-id="c0a4d-265">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c0a4d-265">Allocation factor</span></span></th>
<th><span data-ttu-id="c0a4d-266">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-267">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-267">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-268">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-268">HR</span></span></td>
<td><span data-ttu-id="c0a4d-269">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c0a4d-270">1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-270">1</span></span></td>
<td><span data-ttu-id="c0a4d-271">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-272">500.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-273">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-273">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-274">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-274">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-275">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c0a4d-276">1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-276">1</span></span></td>
<td><span data-ttu-id="c0a4d-277">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-278">500.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-279">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-279">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-280">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-280">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-281">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="c0a4d-282">0</span><span class="sxs-lookup"><span data-stu-id="c0a4d-282">0</span></span></td>
<td><span data-ttu-id="c0a4d-283">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-284">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c0a4d-285">Napló</span><span class="sxs-lookup"><span data-stu-id="c0a4d-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c0a4d-286">Napló</span><span class="sxs-lookup"><span data-stu-id="c0a4d-286">Journal</span></span></th>
<th><span data-ttu-id="c0a4d-287">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="c0a4d-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c0a4d-288">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c0a4d-289">Verzió</span><span class="sxs-lookup"><span data-stu-id="c0a4d-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-290">00002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-290">00002</span></span></td>
<td><span data-ttu-id="c0a4d-291">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="c0a4d-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="c0a4d-292">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="c0a4d-292">Fiscal</span></span></td>
<td><span data-ttu-id="c0a4d-293">2017</span><span class="sxs-lookup"><span data-stu-id="c0a4d-293">2017</span></span></td>
<td><span data-ttu-id="c0a4d-294">1. időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-294">Period 1</span></span></td>
<td><span data-ttu-id="c0a4d-295">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c0a4d-296">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c0a4d-297">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-298">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-299">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-299">Cost element</span></span></th>
<th><span data-ttu-id="c0a4d-300">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-300">Cost behavior</span></span></th>
<th><span data-ttu-id="c0a4d-301">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-302">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-303">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-303">CC099</span></span></td>
<td><span data-ttu-id="c0a4d-304">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-304">Default cost center</span></span></td>
<td><span data-ttu-id="c0a4d-305">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-305">10001</span></span></td>
<td><span data-ttu-id="c0a4d-306">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-306">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-307">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-307">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-308">1000,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-309">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-310">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-310">CC099</span></span></td>
<td><span data-ttu-id="c0a4d-311">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-311">Default cost center</span></span></td>
<td><span data-ttu-id="c0a4d-312">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-312">10001</span></span></td>
<td><span data-ttu-id="c0a4d-313">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-313">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-314">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-314">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c0a4d-316">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="c0a4d-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-317">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-318">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-318">Cost element</span></span></th>
<th><span data-ttu-id="c0a4d-319">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-319">Cost behavior</span></span></th>
<th><span data-ttu-id="c0a4d-320">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-320">Amount</span></span></th>
<th><span data-ttu-id="c0a4d-321">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-322">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-322">CC099</span></span></td>
<td><span data-ttu-id="c0a4d-323">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-323">Default cost center</span></span></td>
<td><span data-ttu-id="c0a4d-324">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-324">10001</span></span></td>
<td><span data-ttu-id="c0a4d-325">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-325">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-326">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-326">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-327">-1000,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-327">-1,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-328">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-329">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-329">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-330">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-330">HR</span></span></td>
<td><span data-ttu-id="c0a4d-331">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-331">10001</span></span></td>
<td><span data-ttu-id="c0a4d-332">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-332">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-333">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-333">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-334">500.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-334">500.00</span></span></td>
<td><span data-ttu-id="c0a4d-335">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-336">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-336">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-337">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-337">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-338">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-338">10001</span></span></td>
<td><span data-ttu-id="c0a4d-339">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-339">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-340">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-340">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-341">500.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-341">500.00</span></span></td>
<td><span data-ttu-id="c0a4d-342">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-343">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-343">CC099</span></span></td>
<td><span data-ttu-id="c0a4d-344">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="c0a4d-344">Default cost center</span></span></td>
<td><span data-ttu-id="c0a4d-345">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-345">10001</span></span></td>
<td><span data-ttu-id="c0a4d-346">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-346">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-347">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-347">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-348">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-348">-9,000.00</span></span></td>
<td><span data-ttu-id="c0a4d-349">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-350">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-350">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-351">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-351">HR</span></span></td>
<td><span data-ttu-id="c0a4d-352">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-352">10001</span></span></td>
<td><span data-ttu-id="c0a4d-353">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-353">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-354">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-354">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="c0a4d-355">1,285.71</span></span></td>
<td><span data-ttu-id="c0a4d-356">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-357">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-357">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-358">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-358">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-359">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-359">10001</span></span></td>
<td><span data-ttu-id="c0a4d-360">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-360">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-361">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-361">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="c0a4d-362">7,714.29</span></span></td>
<td><span data-ttu-id="c0a4d-363">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-364">Ha részletes információt szeretne a költségfelosztásról és a felosztási alapokról, lásd a Költségfelosztási irányelvet és a felosztási alapokat.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="c0a4d-365">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="c0a4d-366">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="c0a4d-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="c0a4d-367">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="c0a4d-368">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="c0a4d-369">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="c0a4d-369">Define the overhead rate</span></span>

<span data-ttu-id="c0a4d-370">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="c0a4d-371">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-372">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-372">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-373">óra</span><span class="sxs-lookup"><span data-stu-id="c0a4d-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-374">Proj 1</span></span></td>
<td><span data-ttu-id="c0a4d-375">1. projekt</span><span class="sxs-lookup"><span data-stu-id="c0a4d-375">Project 1</span></span></td>
<td><span data-ttu-id="c0a4d-376">3</span><span class="sxs-lookup"><span data-stu-id="c0a4d-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-377">Proj 2</span></span></td>
<td><span data-ttu-id="c0a4d-378">2. projekt</span><span class="sxs-lookup"><span data-stu-id="c0a4d-378">Project 2</span></span></td>
<td><span data-ttu-id="c0a4d-379">1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-380">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-381">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-381">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-382">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-382">Cost element</span></span></th>
<th><span data-ttu-id="c0a4d-383">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-383">Cost behavior</span></span></th>
<th><span data-ttu-id="c0a4d-384">Egységek</span><span class="sxs-lookup"><span data-stu-id="c0a4d-384">Units</span></span></th>
<th><span data-ttu-id="c0a4d-385">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="c0a4d-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-386">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-386">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-387">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-387">HR</span></span></td>
<td><span data-ttu-id="c0a4d-388">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-388">10001</span></span></td>
<td><span data-ttu-id="c0a4d-389">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-389">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-390">1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-390">1</span></span></td>
<td><span data-ttu-id="c0a4d-391">10</span><span class="sxs-lookup"><span data-stu-id="c0a4d-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-392">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-393">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-393">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-394">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c0a4d-394">Magnitude</span></span></th>
<th><span data-ttu-id="c0a4d-395">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-395">Cost element</span></span></th>
<th><span data-ttu-id="c0a4d-396">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c0a4d-396">Allocation factor</span></span></th>
<th><span data-ttu-id="c0a4d-397">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-398">Proj 1</span></span></td>
<td><span data-ttu-id="c0a4d-399">1. projekt</span><span class="sxs-lookup"><span data-stu-id="c0a4d-399">Project 1</span></span></td>
<td><span data-ttu-id="c0a4d-400">3</span><span class="sxs-lookup"><span data-stu-id="c0a4d-400">3</span></span></td>
<td><span data-ttu-id="c0a4d-401">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-401">10001</span></span></td>
<td><span data-ttu-id="c0a4d-402">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c0a4d-403">30.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-404">Proj 2</span></span></td>
<td><span data-ttu-id="c0a4d-405">2. projekt</span><span class="sxs-lookup"><span data-stu-id="c0a4d-405">Project 2</span></span></td>
<td><span data-ttu-id="c0a4d-406">1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-406">1</span></span></td>
<td><span data-ttu-id="c0a4d-407">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-407">10001</span></span></td>
<td><span data-ttu-id="c0a4d-408">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="c0a4d-409">10.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="c0a4d-410">Napló</span><span class="sxs-lookup"><span data-stu-id="c0a4d-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c0a4d-411">Napló</span><span class="sxs-lookup"><span data-stu-id="c0a4d-411">Journal</span></span></th>
<th><span data-ttu-id="c0a4d-412">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="c0a4d-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c0a4d-413">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c0a4d-414">Verzió</span><span class="sxs-lookup"><span data-stu-id="c0a4d-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-415">00003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-415">00003</span></span></td>
<td><span data-ttu-id="c0a4d-416">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="c0a4d-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="c0a4d-417">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="c0a4d-417">Fiscal</span></span></td>
<td><span data-ttu-id="c0a4d-418">2017</span><span class="sxs-lookup"><span data-stu-id="c0a4d-418">2017</span></span></td>
<td><span data-ttu-id="c0a4d-419">1. időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-419">Period 1</span></span></td>
<td><span data-ttu-id="c0a4d-420">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="c0a4d-421">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c0a4d-422">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-423">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-423">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-424">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c0a4d-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-425">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-426">Proj 1</span></span></td>
<td><span data-ttu-id="c0a4d-427">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c0a4d-428">3,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-429">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-430">Proj 2</span></span></td>
<td><span data-ttu-id="c0a4d-431">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c0a4d-432">1.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c0a4d-433">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="c0a4d-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-434">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-435">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-435">Cost element</span></span></th>
<th><span data-ttu-id="c0a4d-436">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-436">Cost behavior</span></span></th>
<th><span data-ttu-id="c0a4d-437">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-437">Amount</span></span></th>
<th><span data-ttu-id="c0a4d-438">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-439">CC0001</span></span></td>
<td><span data-ttu-id="c0a4d-440">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-440">HR</span></span></td>
<td><span data-ttu-id="c0a4d-441">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-441">10001</span></span></td>
<td><span data-ttu-id="c0a4d-442">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-442">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-443">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-443">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-444">-30.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-444">-30.00</span></span></td>
<td><span data-ttu-id="c0a4d-445">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-446">Proj 1</span></span></td>
<td><span data-ttu-id="c0a4d-447">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="c0a4d-448">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-448">10001</span></span></td>
<td><span data-ttu-id="c0a4d-449">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-449">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-450">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-450">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-451">30.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-451">30.00</span></span></td>
<td><span data-ttu-id="c0a4d-452">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-453">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-453">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-454">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-454">HR</span></span></td>
<td><span data-ttu-id="c0a4d-455">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-455">10001</span></span></td>
<td><span data-ttu-id="c0a4d-456">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-456">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-457">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-457">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-458">-10.00</span></span></td>
<td><span data-ttu-id="c0a4d-459">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-460">Proj 2</span></span></td>
<td><span data-ttu-id="c0a4d-461">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="c0a4d-462">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-462">10001</span></span></td>
<td><span data-ttu-id="c0a4d-463">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-463">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-464">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-464">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-465">10.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-465">10.00</span></span></td>
<td><span data-ttu-id="c0a4d-466">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-467">A járulékos díj irányelvére vonatkozó részletes információkért lásd: A járulékos díj irányelvei és Felosztási bázisok.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="c0a4d-468">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="c0a4d-469">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="c0a4d-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="c0a4d-470">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="c0a4d-471">A Finance and Operations a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="c0a4d-472">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="c0a4d-473">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="c0a4d-474">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="c0a4d-475">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="c0a4d-476">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-476">The allocation order is controlled by the cost control unit.</span></span> <span data-ttu-id="c0a4d-477">[![Fordított módszer](./media/reciprocal-method.png)]</span><span class="sxs-lookup"><span data-stu-id="c0a4d-477">[![Reciprocal method](./media/reciprocal-method.png)]</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="c0a4d-478">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="c0a4d-478">Define the cost allocation</span></span>

<span data-ttu-id="c0a4d-479">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="c0a4d-480">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="c0a4d-481">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-482">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-482">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-483">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="c0a4d-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-484">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-484">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-485">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-485">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-486">35</span><span class="sxs-lookup"><span data-stu-id="c0a4d-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-487">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-487">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-488">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-488">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-489">55</span><span class="sxs-lookup"><span data-stu-id="c0a4d-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-490">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-490">CC004</span></span></td>
<td><span data-ttu-id="c0a4d-491">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-491">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-492">10</span><span class="sxs-lookup"><span data-stu-id="c0a4d-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-493">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="c0a4d-494">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-495">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-495">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-496">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="c0a4d-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-497">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-497">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-498">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-498">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-499">65</span><span class="sxs-lookup"><span data-stu-id="c0a4d-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-500">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-500">CC004</span></span></td>
<td><span data-ttu-id="c0a4d-501">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-501">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-502">35</span><span class="sxs-lookup"><span data-stu-id="c0a4d-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-503">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="c0a4d-504">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-505">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-505">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-506">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-507">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-507">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-508">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-508">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-509">60</span><span class="sxs-lookup"><span data-stu-id="c0a4d-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-510">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-510">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-511">2. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-511">Product 2</span></span></td>
<td><span data-ttu-id="c0a4d-512">20</span><span class="sxs-lookup"><span data-stu-id="c0a4d-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-513">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="c0a4d-514">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-515">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-515">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-516">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-517">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-517">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-518">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-518">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-519">80</span><span class="sxs-lookup"><span data-stu-id="c0a4d-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-520">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-520">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-521">2. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-521">Product 2</span></span></td>
<td><span data-ttu-id="c0a4d-522">15.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-523">**Megjegyzés:** A Finance and Operations esetében a statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="c0a4d-524">A statisztikai mérési szolgáltatókról szóló bővebb információkért lásd: Statisztikai mérték szolgáltatójának sablonjai.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="c0a4d-525">(Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.) Az alábbi táblázat azt az eredményt mutatja, amikor a HR-szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-526">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-526">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-527">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c0a4d-527">Magnitude</span></span></th>
<th><span data-ttu-id="c0a4d-528">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c0a4d-528">Allocation factor</span></span></th>
<th><span data-ttu-id="c0a4d-529">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-529">Amount</span></span></th>
<th><span data-ttu-id="c0a4d-530">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-531">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-531">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-532">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-532">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-533">35</span><span class="sxs-lookup"><span data-stu-id="c0a4d-533">35</span></span></td>
<td><span data-ttu-id="c0a4d-534">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c0a4d-535">175.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-535">175.00</span></span></td>
<td><span data-ttu-id="c0a4d-536">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-537">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-537">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-538">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-538">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-539">55</span><span class="sxs-lookup"><span data-stu-id="c0a4d-539">55</span></span></td>
<td><span data-ttu-id="c0a4d-540">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c0a4d-541">275.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-541">275.00</span></span></td>
<td><span data-ttu-id="c0a4d-542">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-543">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-543">CC004</span></span></td>
<td><span data-ttu-id="c0a4d-544">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-544">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-545">10</span><span class="sxs-lookup"><span data-stu-id="c0a4d-545">10</span></span></td>
<td><span data-ttu-id="c0a4d-546">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="c0a4d-547">50,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-547">50.00</span></span></td>
<td><span data-ttu-id="c0a4d-548">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-549">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-549">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-550">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-550">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-551">35</span><span class="sxs-lookup"><span data-stu-id="c0a4d-551">35</span></span></td>
<td><span data-ttu-id="c0a4d-552">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="c0a4d-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c0a4d-553">436.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-553">436.00</span></span></td>
<td><span data-ttu-id="c0a4d-554">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-555">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-555">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-556">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-556">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-557">55</span><span class="sxs-lookup"><span data-stu-id="c0a4d-557">55</span></span></td>
<td><span data-ttu-id="c0a4d-558">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="c0a4d-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c0a4d-559">685.14</span><span class="sxs-lookup"><span data-stu-id="c0a4d-559">685.14</span></span></td>
<td><span data-ttu-id="c0a4d-560">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-561">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-561">CC004</span></span></td>
<td><span data-ttu-id="c0a4d-562">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-562">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-563">10</span><span class="sxs-lookup"><span data-stu-id="c0a4d-563">10</span></span></td>
<td><span data-ttu-id="c0a4d-564">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="c0a4d-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="c0a4d-565">124.57</span><span class="sxs-lookup"><span data-stu-id="c0a4d-565">124.57</span></span></td>
<td><span data-ttu-id="c0a4d-566">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-567">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-568">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-568">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-569">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c0a4d-569">Magnitude</span></span></th>
<th><span data-ttu-id="c0a4d-570">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c0a4d-570">Allocation factor</span></span></th>
<th><span data-ttu-id="c0a4d-571">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-571">Amount</span></span></th>
<th><span data-ttu-id="c0a4d-572">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-573">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-573">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-574">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-574">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-575">65</span><span class="sxs-lookup"><span data-stu-id="c0a4d-575">65</span></span></td>
<td><span data-ttu-id="c0a4d-576">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c0a4d-577">438.75</span><span class="sxs-lookup"><span data-stu-id="c0a4d-577">438.75</span></span></td>
<td><span data-ttu-id="c0a4d-578">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-579">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-579">CC004</span></span></td>
<td><span data-ttu-id="c0a4d-580">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-580">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-581">35</span><span class="sxs-lookup"><span data-stu-id="c0a4d-581">35</span></span></td>
<td><span data-ttu-id="c0a4d-582">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="c0a4d-583">236.25</span><span class="sxs-lookup"><span data-stu-id="c0a4d-583">236.25</span></span></td>
<td><span data-ttu-id="c0a4d-584">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-585">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-585">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-586">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-586">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-587">65</span><span class="sxs-lookup"><span data-stu-id="c0a4d-587">65</span></span></td>
<td><span data-ttu-id="c0a4d-588">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c0a4d-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c0a4d-589">5,297.69</span></span></td>
<td><span data-ttu-id="c0a4d-590">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-591">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-591">CC004</span></span></td>
<td><span data-ttu-id="c0a4d-592">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-592">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-593">35</span><span class="sxs-lookup"><span data-stu-id="c0a4d-593">35</span></span></td>
<td><span data-ttu-id="c0a4d-594">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="c0a4d-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c0a4d-595">2,852.60</span></span></td>
<td><span data-ttu-id="c0a4d-596">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-597">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-598">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-598">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-599">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c0a4d-599">Magnitude</span></span></th>
<th><span data-ttu-id="c0a4d-600">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c0a4d-600">Allocation factor</span></span></th>
<th><span data-ttu-id="c0a4d-601">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-601">Amount</span></span></th>
<th><span data-ttu-id="c0a4d-602">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-603">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-603">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-604">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-604">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-605">60</span><span class="sxs-lookup"><span data-stu-id="c0a4d-605">60</span></span></td>
<td><span data-ttu-id="c0a4d-606">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c0a4d-607">535.31</span><span class="sxs-lookup"><span data-stu-id="c0a4d-607">535.31</span></span></td>
<td><span data-ttu-id="c0a4d-608">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-609">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-609">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-610">2. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-610">Product 2</span></span></td>
<td><span data-ttu-id="c0a4d-611">20</span><span class="sxs-lookup"><span data-stu-id="c0a4d-611">20</span></span></td>
<td><span data-ttu-id="c0a4d-612">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="c0a4d-613">178.44</span><span class="sxs-lookup"><span data-stu-id="c0a4d-613">178.44</span></span></td>
<td><span data-ttu-id="c0a4d-614">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-615">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-615">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-616">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-616">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-617">60</span><span class="sxs-lookup"><span data-stu-id="c0a4d-617">60</span></span></td>
<td><span data-ttu-id="c0a4d-618">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c0a4d-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c0a4d-619">4,487.12</span></span></td>
<td><span data-ttu-id="c0a4d-620">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-621">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-621">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-622">2. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-622">Product 2</span></span></td>
<td><span data-ttu-id="c0a4d-623">20</span><span class="sxs-lookup"><span data-stu-id="c0a4d-623">20</span></span></td>
<td><span data-ttu-id="c0a4d-624">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="c0a4d-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c0a4d-625">1,495.71</span></span></td>
<td><span data-ttu-id="c0a4d-626">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="c0a4d-627">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-628">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-628">Cost object</span></span></th>
<th><span data-ttu-id="c0a4d-629">Nagyság</span><span class="sxs-lookup"><span data-stu-id="c0a4d-629">Magnitude</span></span></th>
<th><span data-ttu-id="c0a4d-630">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="c0a4d-630">Allocation factor</span></span></th>
<th><span data-ttu-id="c0a4d-631">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-631">Amount</span></span></th>
<th><span data-ttu-id="c0a4d-632">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-633">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-633">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-634">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-634">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-635">80</span><span class="sxs-lookup"><span data-stu-id="c0a4d-635">80</span></span></td>
<td><span data-ttu-id="c0a4d-636">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c0a4d-637">241.05</span><span class="sxs-lookup"><span data-stu-id="c0a4d-637">241.05</span></span></td>
<td><span data-ttu-id="c0a4d-638">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-639">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-639">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-640">2. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-640">Product 2</span></span></td>
<td><span data-ttu-id="c0a4d-641">15.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-641">15</span></span></td>
<td><span data-ttu-id="c0a4d-642">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="c0a4d-643">45.20</span><span class="sxs-lookup"><span data-stu-id="c0a4d-643">45.20</span></span></td>
<td><span data-ttu-id="c0a4d-644">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-645">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-645">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-646">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-646">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-647">80</span><span class="sxs-lookup"><span data-stu-id="c0a4d-647">80</span></span></td>
<td><span data-ttu-id="c0a4d-648">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c0a4d-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c0a4d-649">2,507.09</span></span></td>
<td><span data-ttu-id="c0a4d-650">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-651">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-651">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-652">2. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-652">Product 2</span></span></td>
<td><span data-ttu-id="c0a4d-653">15.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-653">15</span></span></td>
<td><span data-ttu-id="c0a4d-654">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="c0a4d-655">470.08</span><span class="sxs-lookup"><span data-stu-id="c0a4d-655">470.08</span></span></td>
<td><span data-ttu-id="c0a4d-656">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="c0a4d-657">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c0a4d-658">Napló</span><span class="sxs-lookup"><span data-stu-id="c0a4d-658">Journal</span></span></th>
<th><span data-ttu-id="c0a4d-659">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="c0a4d-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="c0a4d-660">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="c0a4d-661">Verzió</span><span class="sxs-lookup"><span data-stu-id="c0a4d-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-662">00004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-662">00004</span></span></td>
<td><span data-ttu-id="c0a4d-663">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="c0a4d-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="c0a4d-664">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="c0a4d-664">Fiscal</span></span></td>
<td><span data-ttu-id="c0a4d-665">2017</span><span class="sxs-lookup"><span data-stu-id="c0a4d-665">2017</span></span></td>
<td><span data-ttu-id="c0a4d-666">1. időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-666">Period 1</span></span></td>
<td><span data-ttu-id="c0a4d-667">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="c0a4d-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="c0a4d-668">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="c0a4d-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="c0a4d-669">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-670">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-671">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-671">Cost element</span></span></th>
<th><span data-ttu-id="c0a4d-672">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-672">Cost behavior</span></span></th>
<th><span data-ttu-id="c0a4d-673">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-674">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-675">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-675">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-676">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-676">HR</span></span></td>
<td><span data-ttu-id="c0a4d-677">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-677">10001</span></span></td>
<td><span data-ttu-id="c0a4d-678">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-678">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-679">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-679">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-680">500.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-681">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-682">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-682">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-683">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-683">HR</span></span></td>
<td><span data-ttu-id="c0a4d-684">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-684">10001</span></span></td>
<td><span data-ttu-id="c0a4d-685">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-685">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-686">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-686">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="c0a4d-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-688">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-689">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-689">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-690">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-690">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-691">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-691">10001</span></span></td>
<td><span data-ttu-id="c0a4d-692">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-692">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-693">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-693">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-694">675.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-695">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-696">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-696">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-697">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-697">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-698">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-698">10001</span></span></td>
<td><span data-ttu-id="c0a4d-699">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-699">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-700">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-700">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="c0a4d-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-702">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-703">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-703">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-704">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-704">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-705">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-705">10001</span></span></td>
<td><span data-ttu-id="c0a4d-706">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-706">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-707">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-707">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-708">713.75</span><span class="sxs-lookup"><span data-stu-id="c0a4d-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-709">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-710">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-710">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-711">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-711">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-712">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-712">10001</span></span></td>
<td><span data-ttu-id="c0a4d-713">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-713">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-714">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-714">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="c0a4d-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-716">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-717">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-717">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-718">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-718">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-719">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-719">10001</span></span></td>
<td><span data-ttu-id="c0a4d-720">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-720">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-721">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-721">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-722">286.25</span><span class="sxs-lookup"><span data-stu-id="c0a4d-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-723">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-724">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-724">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-725">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-725">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-726">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-726">10001</span></span></td>
<td><span data-ttu-id="c0a4d-727">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-727">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-728">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-728">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="c0a4d-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-730">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-731">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-731">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-732">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-732">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-733">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-733">10001</span></span></td>
<td><span data-ttu-id="c0a4d-734">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-734">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-735">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-735">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-736">776.36</span><span class="sxs-lookup"><span data-stu-id="c0a4d-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-737">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-738">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-738">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-739">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-739">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-740">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-740">10001</span></span></td>
<td><span data-ttu-id="c0a4d-741">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-741">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-742">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-742">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c0a4d-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-744">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-745">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-745">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-746">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-746">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-747">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-747">10001</span></span></td>
<td><span data-ttu-id="c0a4d-748">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-748">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-749">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-749">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-750">223.64</span><span class="sxs-lookup"><span data-stu-id="c0a4d-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-751">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="c0a4d-752">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-752">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-753">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-753">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-754">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-754">10001</span></span></td>
<td><span data-ttu-id="c0a4d-755">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-755">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-756">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-756">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c0a4d-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="c0a4d-758">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="c0a4d-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="c0a4d-759">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="c0a4d-760">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-760">Cost element</span></span></th>
<th><span data-ttu-id="c0a4d-761">Költség működése</span><span class="sxs-lookup"><span data-stu-id="c0a4d-761">Cost behavior</span></span></th>
<th><span data-ttu-id="c0a4d-762">Összeg</span><span class="sxs-lookup"><span data-stu-id="c0a4d-762">Amount</span></span></th>
<th><span data-ttu-id="c0a4d-763">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="c0a4d-764">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-764">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-765">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-765">HR</span></span></td>
<td><span data-ttu-id="c0a4d-766">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-766">10001</span></span></td>
<td><span data-ttu-id="c0a4d-767">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-767">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-768">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-768">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-769">-500.00</span></span></td>
<td><span data-ttu-id="c0a4d-770">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-771">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-771">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-772">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-772">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-773">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-773">10001</span></span></td>
<td><span data-ttu-id="c0a4d-774">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-774">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-775">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-775">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-776">175.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-776">175.00</span></span></td>
<td><span data-ttu-id="c0a4d-777">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-778">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-778">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-779">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-779">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-780">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-780">10001</span></span></td>
<td><span data-ttu-id="c0a4d-781">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-781">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-782">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-782">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-783">275.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-783">275.00</span></span></td>
<td><span data-ttu-id="c0a4d-784">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-785">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-785">CC004</span></span></td>
<td><span data-ttu-id="c0a4d-786">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-786">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-787">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-787">10001</span></span></td>
<td><span data-ttu-id="c0a4d-788">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-788">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-789">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-789">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-790">50,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-790">50,00</span></span></td>
<td><span data-ttu-id="c0a4d-791">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-792">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-792">CC001</span></span></td>
<td><span data-ttu-id="c0a4d-793">HR</span><span class="sxs-lookup"><span data-stu-id="c0a4d-793">HR</span></span></td>
<td><span data-ttu-id="c0a4d-794">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-794">10001</span></span></td>
<td><span data-ttu-id="c0a4d-795">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-795">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-796">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-796">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-797">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="c0a4d-797">-1,245.71</span></span></td>
<td><span data-ttu-id="c0a4d-798">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-799">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-799">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-800">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-800">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-801">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-801">10001</span></span></td>
<td><span data-ttu-id="c0a4d-802">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-802">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-803">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-803">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-804">436.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-804">436.00</span></span></td>
<td><span data-ttu-id="c0a4d-805">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-806">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-806">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-807">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-807">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-808">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-808">10001</span></span></td>
<td><span data-ttu-id="c0a4d-809">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-809">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-810">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-810">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-811">685.14</span><span class="sxs-lookup"><span data-stu-id="c0a4d-811">685.14</span></span></td>
<td><span data-ttu-id="c0a4d-812">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-813">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-813">CC004</span></span></td>
<td><span data-ttu-id="c0a4d-814">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-814">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-815">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-815">10001</span></span></td>
<td><span data-ttu-id="c0a4d-816">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-816">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-817">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-817">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-818">124.57</span><span class="sxs-lookup"><span data-stu-id="c0a4d-818">124.57</span></span></td>
<td><span data-ttu-id="c0a4d-819">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-820">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-820">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-821">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-821">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-822">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-822">10001</span></span></td>
<td><span data-ttu-id="c0a4d-823">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-823">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-824">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-824">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-825">-675.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-825">-675.00</span></span></td>
<td><span data-ttu-id="c0a4d-826">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-827">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-827">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-828">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-828">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-829">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-829">10001</span></span></td>
<td><span data-ttu-id="c0a4d-830">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-830">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-831">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-831">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-832">438.75</span><span class="sxs-lookup"><span data-stu-id="c0a4d-832">438.75</span></span></td>
<td><span data-ttu-id="c0a4d-833">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-834">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-834">CC004</span></span></td>
<td><span data-ttu-id="c0a4d-835">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-835">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-836">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-836">10001</span></span></td>
<td><span data-ttu-id="c0a4d-837">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-837">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-838">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-838">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-839">236.25</span><span class="sxs-lookup"><span data-stu-id="c0a4d-839">236.25</span></span></td>
<td><span data-ttu-id="c0a4d-840">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-841">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-841">CC002</span></span></td>
<td><span data-ttu-id="c0a4d-842">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="c0a4d-842">Finance</span></span></td>
<td><span data-ttu-id="c0a4d-843">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-843">10001</span></span></td>
<td><span data-ttu-id="c0a4d-844">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-844">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-845">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-845">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-846">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="c0a4d-846">-8,150.29</span></span></td>
<td><span data-ttu-id="c0a4d-847">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-848">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-848">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-849">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-849">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-850">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-850">10001</span></span></td>
<td><span data-ttu-id="c0a4d-851">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-851">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-852">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-852">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="c0a4d-853">5,297.69</span></span></td>
<td><span data-ttu-id="c0a4d-854">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-855">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-855">CC004</span></span></td>
<td><span data-ttu-id="c0a4d-856">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="c0a4d-856">Packaging</span></span></td>
<td><span data-ttu-id="c0a4d-857">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-857">10001</span></span></td>
<td><span data-ttu-id="c0a4d-858">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-858">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-859">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-859">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="c0a4d-860">2,852.60</span></span></td>
<td><span data-ttu-id="c0a4d-861">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-862">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-862">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-863">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-863">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-864">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-864">10001</span></span></td>
<td><span data-ttu-id="c0a4d-865">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-865">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-866">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-866">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-867">-713.75</span><span class="sxs-lookup"><span data-stu-id="c0a4d-867">-713.75</span></span></td>
<td><span data-ttu-id="c0a4d-868">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-869">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-869">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-870">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-870">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-871">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-871">10001</span></span></td>
<td><span data-ttu-id="c0a4d-872">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-872">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-873">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-873">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-874">535.31</span><span class="sxs-lookup"><span data-stu-id="c0a4d-874">535.31</span></span></td>
<td><span data-ttu-id="c0a4d-875">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-876">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-876">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-877">2. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-877">Product 2</span></span></td>
<td><span data-ttu-id="c0a4d-878">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-878">10001</span></span></td>
<td><span data-ttu-id="c0a4d-879">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-879">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-880">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-880">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-881">178.44</span><span class="sxs-lookup"><span data-stu-id="c0a4d-881">178.44</span></span></td>
<td><span data-ttu-id="c0a4d-882">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-883">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-883">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-884">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-884">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-885">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-885">10001</span></span></td>
<td><span data-ttu-id="c0a4d-886">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-886">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-887">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-887">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-888">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="c0a4d-888">-5,982.83</span></span></td>
<td><span data-ttu-id="c0a4d-889">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-890">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-890">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-891">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-891">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-892">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-892">10001</span></span></td>
<td><span data-ttu-id="c0a4d-893">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-893">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-894">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-894">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="c0a4d-895">4,487.12</span></span></td>
<td><span data-ttu-id="c0a4d-896">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-897">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-897">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-898">2. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-898">Product 2</span></span></td>
<td><span data-ttu-id="c0a4d-899">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-899">10001</span></span></td>
<td><span data-ttu-id="c0a4d-900">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-900">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-901">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-901">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="c0a4d-902">1,495.71</span></span></td>
<td><span data-ttu-id="c0a4d-903">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-904">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-904">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-905">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-905">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-906">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-906">10001</span></span></td>
<td><span data-ttu-id="c0a4d-907">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-907">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-908">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-908">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-909">-286.25</span><span class="sxs-lookup"><span data-stu-id="c0a4d-909">-286.25</span></span></td>
<td><span data-ttu-id="c0a4d-910">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-911">Term 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-911">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-912">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-912">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-913">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-913">10001</span></span></td>
<td><span data-ttu-id="c0a4d-914">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-914">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-915">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-915">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-916">241.05</span><span class="sxs-lookup"><span data-stu-id="c0a4d-916">241.05</span></span></td>
<td><span data-ttu-id="c0a4d-917">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-918">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-918">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-919">2. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-919">Product 2</span></span></td>
<td><span data-ttu-id="c0a4d-920">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-920">10001</span></span></td>
<td><span data-ttu-id="c0a4d-921">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-921">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-922">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-922">Fixed cost</span></span></td>
<td><span data-ttu-id="c0a4d-923">45.20</span><span class="sxs-lookup"><span data-stu-id="c0a4d-923">45.20</span></span></td>
<td><span data-ttu-id="c0a4d-924">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-925">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-925">CC003</span></span></td>
<td><span data-ttu-id="c0a4d-926">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="c0a4d-926">Assembly</span></span></td>
<td><span data-ttu-id="c0a4d-927">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-927">10001</span></span></td>
<td><span data-ttu-id="c0a4d-928">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-928">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-929">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-929">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-930">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="c0a4d-930">-2,977.17</span></span></td>
<td><span data-ttu-id="c0a4d-931">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-932">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-932">Prod 1</span></span></td>
<td><span data-ttu-id="c0a4d-933">1. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-933">Product 1</span></span></td>
<td><span data-ttu-id="c0a4d-934">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-934">10001</span></span></td>
<td><span data-ttu-id="c0a4d-935">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-935">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-936">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-936">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="c0a4d-937">2,507.09</span></span></td>
<td><span data-ttu-id="c0a4d-938">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="c0a4d-939">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-939">Prod 2</span></span></td>
<td><span data-ttu-id="c0a4d-940">2. termék</span><span class="sxs-lookup"><span data-stu-id="c0a4d-940">Product 2</span></span></td>
<td><span data-ttu-id="c0a4d-941">10001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-941">10001</span></span></td>
<td><span data-ttu-id="c0a4d-942">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-942">Electricity</span></span></td>
<td><span data-ttu-id="c0a4d-943">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-943">Variable cost</span></span></td>
<td><span data-ttu-id="c0a4d-944">470.08</span><span class="sxs-lookup"><span data-stu-id="c0a4d-944">470.08</span></span></td>
<td><span data-ttu-id="c0a4d-945">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="c0a4d-946">Következtetés</span><span class="sxs-lookup"><span data-stu-id="c0a4d-946">Conclusion</span></span>
<span data-ttu-id="c0a4d-947">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="c0a4d-948">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="c0a4d-949">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="c0a4d-950">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="c0a4d-951">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="c0a4d-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="c0a4d-952">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="c0a4d-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="c0a4d-953">Összesen</span><span class="sxs-lookup"><span data-stu-id="c0a4d-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="c0a4d-954">CC099</span><span class="sxs-lookup"><span data-stu-id="c0a4d-954">CC099</span></span></th>
<th><span data-ttu-id="c0a4d-955">CC001</span><span class="sxs-lookup"><span data-stu-id="c0a4d-955">CC001</span></span></th>
<th><span data-ttu-id="c0a4d-956">CC002</span><span class="sxs-lookup"><span data-stu-id="c0a4d-956">CC002</span></span></th>
<th><span data-ttu-id="c0a4d-957">CC003</span><span class="sxs-lookup"><span data-stu-id="c0a4d-957">CC003</span></span></th>
<th><span data-ttu-id="c0a4d-958">CC004</span><span class="sxs-lookup"><span data-stu-id="c0a4d-958">CC004</span></span></th>
<th><span data-ttu-id="c0a4d-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-959">Proj 1</span></span></th>
<th><span data-ttu-id="c0a4d-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-960">Proj 2</span></span></th>
<th><span data-ttu-id="c0a4d-961">Term. 1</span><span class="sxs-lookup"><span data-stu-id="c0a4d-961">Prod 1</span></span></th>
<th><span data-ttu-id="c0a4d-962">Term. 2</span><span class="sxs-lookup"><span data-stu-id="c0a4d-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="c0a4d-963">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="c0a4d-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-965"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-966"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-967"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-968"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-969"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-970"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-971"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-972"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="c0a4d-973">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="c0a4d-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-974">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="c0a4d-975">Fix költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-976">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-977">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-978">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-979">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-980">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-981">776.36</span><span class="sxs-lookup"><span data-stu-id="c0a4d-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-982">223.64</span><span class="sxs-lookup"><span data-stu-id="c0a4d-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-983"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="c0a4d-984">Változó költség</span><span class="sxs-lookup"><span data-stu-id="c0a4d-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-985">000</span><span class="sxs-lookup"><span data-stu-id="c0a4d-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-986">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-987">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-988">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-989">0,00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-990">30.00</span><span class="sxs-lookup"><span data-stu-id="c0a4d-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-991">1000</span><span class="sxs-lookup"><span data-stu-id="c0a4d-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="c0a4d-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="c0a4d-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="c0a4d-994"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="c0a4d-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="c0a4d-995">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="c0a4d-996">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="c0a4d-997">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="c0a4d-998">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="c0a4d-999">Részletesebb tájékoztatás: Költségösszesítési irányelv.</span><span class="sxs-lookup"><span data-stu-id="c0a4d-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="c0a4d-1000">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="c0a4d-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




