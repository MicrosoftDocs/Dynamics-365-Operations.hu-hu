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
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 0ea6f7428cd5c7618d2d69f1fb66fd9539ad1073
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="overhead-calculation"></a><span data-ttu-id="418b0-103">Járulékos költség számítása</span><span class="sxs-lookup"><span data-stu-id="418b0-103">Overhead calculation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="418b0-104">Ez a témakör a járulékos költségek kiszámításának és allokálásának jellemző folyamatait írja le.</span><span class="sxs-lookup"><span data-stu-id="418b0-104">This topic describes the typical processes for calculating and allocating overhead costs.</span></span>

<a name="term-definition"></a><span data-ttu-id="418b0-105">A kifejezés meghatározása</span><span class="sxs-lookup"><span data-stu-id="418b0-105">Term definition</span></span>
---------------

<span data-ttu-id="418b0-106">A járulékos költségek azok a költségek, amelyek egy vállalkozás futtatásánál merülnek fel, de amelyek közvetlenül nem tulajdoníthatók semmilyen konkrét üzleti tevékenységnek, terméknek vagy szolgáltatásnak.</span><span class="sxs-lookup"><span data-stu-id="418b0-106">Overhead costs are the costs that are incurred in order to run a business, but that can't be directly attributed to any specific business activity, product, or service.</span></span> <span data-ttu-id="418b0-107">A járulékos költségek lényeges támogatást biztosítanak a bevételszerző tevékenységek számára.</span><span class="sxs-lookup"><span data-stu-id="418b0-107">Overhead costs provide critical support for the generation of profit-making activities.</span></span> <span data-ttu-id="418b0-108">Az alábbiakban néhány példa látható a járulékos költségekre:</span><span class="sxs-lookup"><span data-stu-id="418b0-108">Here are some examples of overhead costs:</span></span>

-   <span data-ttu-id="418b0-109">Bérlet</span><span class="sxs-lookup"><span data-stu-id="418b0-109">Rent</span></span>
-   <span data-ttu-id="418b0-110">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-110">Electricity</span></span>
-   <span data-ttu-id="418b0-111">Adminisztratív fizetések</span><span class="sxs-lookup"><span data-stu-id="418b0-111">Administrative salaries</span></span>

## <a name="overhead-calculation-overview"></a><span data-ttu-id="418b0-112">Járulékos költség áttekintése</span><span class="sxs-lookup"><span data-stu-id="418b0-112">Overhead calculation overview</span></span>
<span data-ttu-id="418b0-113">A járulékos költség kiszámítása lefuttatja a költségkönyvelési irányelveket a megfelelő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="418b0-113">Overhead calculation runs the cost accounting policies in the correct order.</span></span> <span data-ttu-id="418b0-114">A járulékos költségek kiszámítása többször is módosítható ugyanazon pénzügyi időszakra vonatkozóan, ha a költségkönyvelési irányelvek megváltoztak, illetve bizonyos hibákat észleltek.</span><span class="sxs-lookup"><span data-stu-id="418b0-114">You can run overhead calculation multiple times for the same fiscal period if cost accounting policies have been changed or specific errors have been detected.</span></span> <span data-ttu-id="418b0-115">A járulékos költségek számítás minden egyes futtatása tárolódik, és egyedi verzióazonosítót kap, amely lehetővé teszi a számítások összehasonlítását a különböző verziókban.</span><span class="sxs-lookup"><span data-stu-id="418b0-115">Each run of the overhead calculation is stored and receives a unique version ID that lets you compare the calculations in various versions.</span></span> <span data-ttu-id="418b0-116">Azok a költségbejegyzések, amelyeket a járulékosköltség-számítás generál, könyvelési dátumot kapnak.</span><span class="sxs-lookup"><span data-stu-id="418b0-116">The cost entries that the overhead calculation generates receive an accounting date.</span></span> <span data-ttu-id="418b0-117">A könyvelési dátum megegyezik a számításban használt pénzügyi időszak záró dátumával.</span><span class="sxs-lookup"><span data-stu-id="418b0-117">This accounting date matches the end date of the fiscal period that is used in the calculation.</span></span> <span data-ttu-id="418b0-118">A verzió egyedi azonosítója a következő elemekből áll:</span><span class="sxs-lookup"><span data-stu-id="418b0-118">The unique version ID consists of the following elements:</span></span>

-   <span data-ttu-id="418b0-119">Verziótípus</span><span class="sxs-lookup"><span data-stu-id="418b0-119">Version type</span></span>
-   <span data-ttu-id="418b0-120">Dátum és idő</span><span class="sxs-lookup"><span data-stu-id="418b0-120">Date and time</span></span>
-   <span data-ttu-id="418b0-121">Költségkönyvelési főkönyv</span><span class="sxs-lookup"><span data-stu-id="418b0-121">Cost accounting ledger</span></span>
-   <span data-ttu-id="418b0-122">Pénzügyi év</span><span class="sxs-lookup"><span data-stu-id="418b0-122">Fiscal year</span></span>
-   <span data-ttu-id="418b0-123">Pénzügyi időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-123">Fiscal period</span></span>

<span data-ttu-id="418b0-124">A járulékos költség kiszámítása a verziótól függetlenül fut.</span><span class="sxs-lookup"><span data-stu-id="418b0-124">Overhead calculation is run independently of the version.</span></span> <span data-ttu-id="418b0-125">Ezért a tényleges verzió előtt kiszámíthatja a költségvetési verziót.</span><span class="sxs-lookup"><span data-stu-id="418b0-125">Therefore, you can calculate the Budget version before the Actual version.</span></span> <span data-ttu-id="418b0-126">A járulékos költségek kiszámítása négy lépésből áll, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="418b0-126">Overhead calculation consists of four steps, as shown in the following illustration.</span></span> <span data-ttu-id="418b0-127">Minden lépésnél létrejön egy naplófejléc naplóbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="418b0-127">In each step, a journal header is created that has journal entries.</span></span> <span data-ttu-id="418b0-128">Ez a naplófejléc megtartja az egyes számítási lépések bemeneti adatait.</span><span class="sxs-lookup"><span data-stu-id="418b0-128">This journal header keeps the input data for each calculation step.</span></span> <span data-ttu-id="418b0-129">Az irányelvek és szabályok minden egyes naplósorra érvényesek, és kimenetként költségbejegyzések jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="418b0-129">Policies and rules are applied to each journal line, and cost entries are generated as output.</span></span> <span data-ttu-id="418b0-130">Ezáltal mindig teljes a nyomon követhetőség.</span><span class="sxs-lookup"><span data-stu-id="418b0-130">Therefore, you always have full traceability.</span></span> 

<span data-ttu-id="418b0-131">[![Járulékos költség számítása](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span><span class="sxs-lookup"><span data-stu-id="418b0-131">[![Overhead calculation](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)</span></span>

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a><span data-ttu-id="418b0-132">Az elektromos áram járulékos költségének kiszámítása és felosztása</span><span class="sxs-lookup"><span data-stu-id="418b0-132">Calculate and allocate the Electricity overhead cost</span></span>
<span data-ttu-id="418b0-133">A pénzügyi könyvelésben egyes költségeket, így például az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="418b0-133">In Financial accounting, some costs, such as electricity, are registered as a lump sum.</span></span> <span data-ttu-id="418b0-134">Ezért nem jön létre részletes vezetői betekintést a költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="418b0-134">Therefore, detailed managerial insight isn't provided for Cost accounting.</span></span> <span data-ttu-id="418b0-135">A Költségkönyvelés során a szervezeti egységek és a szintek közötti megfelelő vezetői betekintés biztosításához költségeknek kell bekerülnie a szervezeti egységeken keresztül.</span><span class="sxs-lookup"><span data-stu-id="418b0-135">In Cost accounting, to provide correct managerial insight across all organizational units and levels, costs must flow through the organizational units.</span></span> <span data-ttu-id="418b0-136">A folyamatnak vagy a felhasználás pontos rekordján, vagy a helyes becslésén kell alapulnia.</span><span class="sxs-lookup"><span data-stu-id="418b0-136">This flow must be based on either an accurate record of the consumption or a fair assessment.</span></span> <span data-ttu-id="418b0-137">A főkönyvben az elektromos áram költségként feladható a következő táblázatban látható módon.</span><span class="sxs-lookup"><span data-stu-id="418b0-137">In the general ledger, an electricity cost can be posted as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="418b0-138">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="418b0-138">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-139">Költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-139">Cost center</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-140">Fő számla</span><span class="sxs-lookup"><span data-stu-id="418b0-140">Main account</span></span></th>
<th><span data-ttu-id="418b0-141">Összeg a könyvelési pénznemben</span><span class="sxs-lookup"><span data-stu-id="418b0-141">Amount in the accounting currency</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-142">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="418b0-142">January 3, 2017</span></span></td>
<td><span data-ttu-id="418b0-143">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-143">CC099</span></span></td>
<td><span data-ttu-id="418b0-144">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-144">Default cost center</span></span></td>
<td><span data-ttu-id="418b0-145">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-145">10001</span></span></td>
<td><span data-ttu-id="418b0-146">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-146">Electricity</span></span></td>
<td><span data-ttu-id="418b0-147">10,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-147">10,000.00</span></span></td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a><span data-ttu-id="418b0-148">1. lépés: A költségek viselkedésére vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="418b0-148">Step 1: Process the cost behavior calculation</span></span>

<span data-ttu-id="418b0-149">Alapértelmezés szerint a költségbejegyzéseket a forrásadatokból importálja a rendszer, és megkapják a **Nem besorolt** költségviselkedési besorolást a Költségkönyvelésnél.</span><span class="sxs-lookup"><span data-stu-id="418b0-149">By default, when cost entries are imported from the source data, they receive the **Unclassified** cost behavior classification in Cost accounting.</span></span> <span data-ttu-id="418b0-150">A költségviselkedés szabályainak alkalmazásával a költségbejegyzéseket át lehet helyezni a **Rögzített költség** vagy **Változó költség** ponthoz.</span><span class="sxs-lookup"><span data-stu-id="418b0-150">By applying cost behavior policy rules, you can reclassify cost entries as either **Fixed cost** or **Variable cost**.</span></span>

#### <a name="define-the-cost-behavior-rule"></a><span data-ttu-id="418b0-151">A költségviselkedési szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="418b0-151">Define the cost behavior rule</span></span>

<span data-ttu-id="418b0-152">Bizonyos esetekben a költség egy része rögzített díj, a fennmaradó költség pedig felhasználásalapú.</span><span class="sxs-lookup"><span data-stu-id="418b0-152">In some cases, part of the cost is a fixed fee, and the remaining cost is based on consumption.</span></span> <span data-ttu-id="418b0-153">A villanyszámlák gyakran megfelelnek ennek a meghatározásnak.</span><span class="sxs-lookup"><span data-stu-id="418b0-153">Electricity bills often match this definition.</span></span> <span data-ttu-id="418b0-154">Miután befizet egy meghatározott rögzített díjat, kilowattóránként (Kwh) fizet.</span><span class="sxs-lookup"><span data-stu-id="418b0-154">After you pay a specific fixed fee, you pay for consumption per kilowatt hour (Kwh).</span></span> <span data-ttu-id="418b0-155">Ha például a rögzített díj 1000,00, így határozható meg a költségviselkedési szabály:</span><span class="sxs-lookup"><span data-stu-id="418b0-155">For example, if the fixed cost fee is 1,000.00, here is how the cost behavior rule is defined:</span></span>

-   <span data-ttu-id="418b0-156">Rögzített összeg 1,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-156">Fixed amount 1,000.00</span></span>
    -   <span data-ttu-id="418b0-157">0 &lt;= 1,000.00 = Rögzített</span><span class="sxs-lookup"><span data-stu-id="418b0-157">0 &lt;= 1,000.00 = Fixed</span></span>
    -   <span data-ttu-id="418b0-158">1000,01 &lt; N = Változó</span><span class="sxs-lookup"><span data-stu-id="418b0-158">1000,01 &lt; N = Variable</span></span>

##### <a name="journal"></a><span data-ttu-id="418b0-159">Napló</span><span class="sxs-lookup"><span data-stu-id="418b0-159">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="418b0-160">Napló</span><span class="sxs-lookup"><span data-stu-id="418b0-160">Journal</span></span></th>
<th><span data-ttu-id="418b0-161">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="418b0-161">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="418b0-162">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-162">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="418b0-163">Verzió</span><span class="sxs-lookup"><span data-stu-id="418b0-163">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-164">00001</span><span class="sxs-lookup"><span data-stu-id="418b0-164">00001</span></span></td>
<td><span data-ttu-id="418b0-165">Költségműködés számítás napló</span><span class="sxs-lookup"><span data-stu-id="418b0-165">Cost behavior calculation journal</span></span></td>
<td><span data-ttu-id="418b0-166">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="418b0-166">Fiscal</span></span></td>
<td><span data-ttu-id="418b0-167">2017</span><span class="sxs-lookup"><span data-stu-id="418b0-167">2017</span></span></td>
<td><span data-ttu-id="418b0-168">1. időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-168">Period 1</span></span></td>
<td><span data-ttu-id="418b0-169">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-169">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="418b0-170">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="418b0-170">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="418b0-171">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="418b0-171">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-172">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-172">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-173">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="418b0-173">Cost element</span></span></th>
<th><span data-ttu-id="418b0-174">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-174">Cost behavior</span></span></th>
<th><span data-ttu-id="418b0-175">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-175">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-176">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="418b0-176">January 3, 2017</span></span></td>
<td><span data-ttu-id="418b0-177">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-177">CC099</span></span></td>
<td><span data-ttu-id="418b0-178">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-178">Default cost center</span></span></td>
<td><span data-ttu-id="418b0-179">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-179">10001</span></span></td>
<td><span data-ttu-id="418b0-180">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-180">Electricity</span></span></td>
<td><span data-ttu-id="418b0-181">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="418b0-181">Unclassified</span></span></td>
<td><span data-ttu-id="418b0-182">10,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-182">10,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="418b0-183">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="418b0-183">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-184">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-184">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-185">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="418b0-185">Cost element</span></span></th>
<th><span data-ttu-id="418b0-186">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-186">Cost behavior</span></span></th>
<th><span data-ttu-id="418b0-187">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-187">Amount</span></span></th>
<th><span data-ttu-id="418b0-188">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="418b0-188">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-189">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-189">CC099</span></span></td>
<td><span data-ttu-id="418b0-190">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-190">Default cost center</span></span></td>
<td><span data-ttu-id="418b0-191">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-191">10001</span></span></td>
<td><span data-ttu-id="418b0-192">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-192">Electricity</span></span></td>
<td><span data-ttu-id="418b0-193">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="418b0-193">Unclassified</span></span></td>
<td><span data-ttu-id="418b0-194">10,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-194">10,000.00</span></span></td>
<td><span data-ttu-id="418b0-195">2017. január 3.</span><span class="sxs-lookup"><span data-stu-id="418b0-195">January 3, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-196">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-196">CC099</span></span></td>
<td><span data-ttu-id="418b0-197">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-197">Default cost center</span></span></td>
<td><span data-ttu-id="418b0-198">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-198">10001</span></span></td>
<td><span data-ttu-id="418b0-199">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-199">Electricity</span></span></td>
<td><span data-ttu-id="418b0-200">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="418b0-200">Unclassified</span></span></td>
<td><span data-ttu-id="418b0-201">-10,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-201">-10,000.00</span></span></td>
<td><span data-ttu-id="418b0-202">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-202">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-203">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-203">CC099</span></span></td>
<td><span data-ttu-id="418b0-204">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-204">Default cost center</span></span></td>
<td><span data-ttu-id="418b0-205">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-205">10001</span></span></td>
<td><span data-ttu-id="418b0-206">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-206">Electricity</span></span></td>
<td><span data-ttu-id="418b0-207">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-207">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-208">1000,00</span><span class="sxs-lookup"><span data-stu-id="418b0-208">1,000.00</span></span></td>
<td><span data-ttu-id="418b0-209">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-209">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-210">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-210">CC099</span></span></td>
<td><span data-ttu-id="418b0-211">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-211">Default cost center</span></span></td>
<td><span data-ttu-id="418b0-212">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-212">10001</span></span></td>
<td><span data-ttu-id="418b0-213">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-213">Electricity</span></span></td>
<td><span data-ttu-id="418b0-214">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-214">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-215">9,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-215">9,000.00</span></span></td>
<td><span data-ttu-id="418b0-216">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-216">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-217">A költségműködéssel kapcsolatos részletes tudnivalókat lásd a Költségműködési irányelvekben.</span><span class="sxs-lookup"><span data-stu-id="418b0-217">For detailed information about cost behavior, see Cost behavior policy.</span></span> <span data-ttu-id="418b0-218">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="418b0-218">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-2-process-the-cost-distribution-calculation"></a><span data-ttu-id="418b0-219">2. lépés: A kötségelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="418b0-219">Step 2: Process the cost distribution calculation</span></span>

<span data-ttu-id="418b0-220">A költségfelosztást arra használhatja, hogy költségeket egy költségobjektumból egy vagy több más költségobjektumhoz rendelje a megfelelő felosztási bázis alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="418b0-220">Cost distribution is used to redistribute cost from one cost object to one or more other cost objects by applying a relevant allocation base.</span></span> <span data-ttu-id="418b0-221">A költségelosztás és a költségek felosztása abban különbözik, hogy a költségelosztás mindig az eredeti költség elsődleges költségelemének szintjén történik.</span><span class="sxs-lookup"><span data-stu-id="418b0-221">Cost distribution and cost allocation differ in that cost distribution always occurs at the level of the primary cost element of the original cost.</span></span>

#### <a name="define-the-cost-distribution-rule"></a><span data-ttu-id="418b0-222">A költségelosztási szabály meghatározása</span><span class="sxs-lookup"><span data-stu-id="418b0-222">Define the cost distribution rule</span></span>

<span data-ttu-id="418b0-223">Pénzügyi könyvelés, az elektromos áram költségeit gyakran egy összegben regisztrálják.</span><span class="sxs-lookup"><span data-stu-id="418b0-223">In Financial accounting, electricity costs are often registered as a lump sum.</span></span> <span data-ttu-id="418b0-224">A költségkönyvelésben ez a módszer nem elég részletes.</span><span class="sxs-lookup"><span data-stu-id="418b0-224">In Cost accounting, this approach isn't detailed enough.</span></span> <span data-ttu-id="418b0-225">A változó költségeket megfelelően el kell osztani az egyes költségobjektumok között.</span><span class="sxs-lookup"><span data-stu-id="418b0-225">The variable cost should be distributed to the individual cost objects on a fair basis.</span></span> <span data-ttu-id="418b0-226">A leglogikusabb felosztási alap az villamosenergia-fogyasztás (Kwh).</span><span class="sxs-lookup"><span data-stu-id="418b0-226">The most logical allocation basis is the consumption of electricity (Kwh).</span></span> <span data-ttu-id="418b0-227">Létrejön egy statisztikai dimenziótag, melynek neve Villamosenergia, és a rendszer rögzíteni kezdi a villamosenergia-fogyasztást.</span><span class="sxs-lookup"><span data-stu-id="418b0-227">A statistical dimension member that is named Electricity is created, and electricity consumption is recorded.</span></span> <span data-ttu-id="418b0-228">Alapértelmezés szerint minden statisztikai dimenziótag elérhetővé válik felosztási alapként.</span><span class="sxs-lookup"><span data-stu-id="418b0-228">By default, all statistical dimension members become available as allocation bases.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-229">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-229">Cost object</span></span></th>
<th><span data-ttu-id="418b0-230">Kwh</span><span class="sxs-lookup"><span data-stu-id="418b0-230">Kwh</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-231">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-231">CC001</span></span></td>
<td><span data-ttu-id="418b0-232">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-232">HR</span></span></td>
<td><span data-ttu-id="418b0-233">1000</span><span class="sxs-lookup"><span data-stu-id="418b0-233">1,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-234">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-234">CC002</span></span></td>
<td><span data-ttu-id="418b0-235">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-235">Finance</span></span></td>
<td><span data-ttu-id="418b0-236">6,000</span><span class="sxs-lookup"><span data-stu-id="418b0-236">6,000</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-237">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-237">CC003</span></span></td>
<td><span data-ttu-id="418b0-238">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-238">Assembly</span></span></td>
<td><span data-ttu-id="418b0-239">0</span><span class="sxs-lookup"><span data-stu-id="418b0-239">0</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-240">Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztás a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="418b0-240">The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-241">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-241">Cost object</span></span></th>
<th><span data-ttu-id="418b0-242">Nagyság</span><span class="sxs-lookup"><span data-stu-id="418b0-242">Magnitude</span></span></th>
<th><span data-ttu-id="418b0-243">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="418b0-243">Allocation factor</span></span></th>
<th><span data-ttu-id="418b0-244">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-244">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-245">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-245">CC001</span></span></td>
<td><span data-ttu-id="418b0-246">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-246">HR</span></span></td>
<td><span data-ttu-id="418b0-247">1000</span><span class="sxs-lookup"><span data-stu-id="418b0-247">1,000</span></span></td>
<td><span data-ttu-id="418b0-248">(1,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-248">(1,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="418b0-249">1,285.71</span><span class="sxs-lookup"><span data-stu-id="418b0-249">1,285.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-250">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-250">CC002</span></span></td>
<td><span data-ttu-id="418b0-251">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-251">Finance</span></span></td>
<td><span data-ttu-id="418b0-252">6,000</span><span class="sxs-lookup"><span data-stu-id="418b0-252">6,000</span></span></td>
<td><span data-ttu-id="418b0-253">(6,000 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-253">(6,000 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="418b0-254">7,714.29</span><span class="sxs-lookup"><span data-stu-id="418b0-254">7,714.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-255">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-255">CC003</span></span></td>
<td><span data-ttu-id="418b0-256">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-256">Assembly</span></span></td>
<td><span data-ttu-id="418b0-257">0</span><span class="sxs-lookup"><span data-stu-id="418b0-257">0</span></span></td>
<td><span data-ttu-id="418b0-258">(0 ÷ 7,000) × 9,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-258">(0 ÷ 7,000) × 9,000.00</span></span></td>
<td><span data-ttu-id="418b0-259">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-259">0.00</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-260">A rögzített költségeket egyenletesen kell elosztani az olyan egyéni költségobjektumoknál, amelyek villamos energiát fogyasztottak.</span><span class="sxs-lookup"><span data-stu-id="418b0-260">The fixed cost should be distributed evenly to the individual cost objects that have consumed electricity.</span></span> <span data-ttu-id="418b0-261">Ezt az eredményt úgy érhetjük el, hogy a villamos energia statisztikai dimenziótagot egy képletfelosztási bázison használjuk: ((Villamos energia &gt; 0.00) Az alábbi táblázat azt az eredményt mutatja, amikor az áramfogyasztást a változó költségek felosztási alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="418b0-261">You can achieve this result by using the Electricity statistical dimension member in a formula allocation base: (Electricity &gt; 0.00) The following table shows the result when electricity consumption is applied as an allocation base for variable costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-262">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-262">Cost object</span></span></th>
<th><span data-ttu-id="418b0-263">Receptúra</span><span class="sxs-lookup"><span data-stu-id="418b0-263">Formula</span></span></th>
<th><span data-ttu-id="418b0-264">Nagyság</span><span class="sxs-lookup"><span data-stu-id="418b0-264">Magnitude</span></span></th>
<th><span data-ttu-id="418b0-265">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="418b0-265">Allocation factor</span></span></th>
<th><span data-ttu-id="418b0-266">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-266">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-267">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-267">CC001</span></span></td>
<td><span data-ttu-id="418b0-268">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-268">HR</span></span></td>
<td><span data-ttu-id="418b0-269">(1,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="418b0-269">(1,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="418b0-270">1</span><span class="sxs-lookup"><span data-stu-id="418b0-270">1</span></span></td>
<td><span data-ttu-id="418b0-271">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-271">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="418b0-272">500.00</span><span class="sxs-lookup"><span data-stu-id="418b0-272">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-273">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-273">CC002</span></span></td>
<td><span data-ttu-id="418b0-274">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-274">Finance</span></span></td>
<td><span data-ttu-id="418b0-275">(6,000 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="418b0-275">(6,000 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="418b0-276">1</span><span class="sxs-lookup"><span data-stu-id="418b0-276">1</span></span></td>
<td><span data-ttu-id="418b0-277">(1 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-277">(1 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="418b0-278">500.00</span><span class="sxs-lookup"><span data-stu-id="418b0-278">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-279">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-279">CC003</span></span></td>
<td><span data-ttu-id="418b0-280">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-280">Assembly</span></span></td>
<td><span data-ttu-id="418b0-281">(0 &gt; 0.00)</span><span class="sxs-lookup"><span data-stu-id="418b0-281">(0 &gt; 0.00)</span></span></td>
<td><span data-ttu-id="418b0-282">0</span><span class="sxs-lookup"><span data-stu-id="418b0-282">0</span></span></td>
<td><span data-ttu-id="418b0-283">(0 ÷ 2) × 1,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-283">(0 ÷ 2) × 1,000.00</span></span></td>
<td><span data-ttu-id="418b0-284">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-284">0.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="418b0-285">Napló</span><span class="sxs-lookup"><span data-stu-id="418b0-285">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="418b0-286">Napló</span><span class="sxs-lookup"><span data-stu-id="418b0-286">Journal</span></span></th>
<th><span data-ttu-id="418b0-287">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="418b0-287">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="418b0-288">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-288">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="418b0-289">Verzió</span><span class="sxs-lookup"><span data-stu-id="418b0-289">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-290">00002</span><span class="sxs-lookup"><span data-stu-id="418b0-290">00002</span></span></td>
<td><span data-ttu-id="418b0-291">Költségfelosztás számítási naplója</span><span class="sxs-lookup"><span data-stu-id="418b0-291">Cost distribution calculation journal</span></span></td>
<td><span data-ttu-id="418b0-292">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="418b0-292">Fiscal</span></span></td>
<td><span data-ttu-id="418b0-293">2017</span><span class="sxs-lookup"><span data-stu-id="418b0-293">2017</span></span></td>
<td><span data-ttu-id="418b0-294">1. időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-294">Period 1</span></span></td>
<td><span data-ttu-id="418b0-295">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-295">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="418b0-296">Naplóbejegyzések (Költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="418b0-296">Journal entries (Cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="418b0-297">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="418b0-297">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-298">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-298">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-299">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="418b0-299">Cost element</span></span></th>
<th><span data-ttu-id="418b0-300">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-300">Cost behavior</span></span></th>
<th><span data-ttu-id="418b0-301">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-301">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-302">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-302">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-303">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-303">CC099</span></span></td>
<td><span data-ttu-id="418b0-304">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-304">Default cost center</span></span></td>
<td><span data-ttu-id="418b0-305">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-305">10001</span></span></td>
<td><span data-ttu-id="418b0-306">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-306">Electricity</span></span></td>
<td><span data-ttu-id="418b0-307">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-307">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-308">1000,00</span><span class="sxs-lookup"><span data-stu-id="418b0-308">1,000.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-309">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-309">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-310">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-310">CC099</span></span></td>
<td><span data-ttu-id="418b0-311">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-311">Default cost center</span></span></td>
<td><span data-ttu-id="418b0-312">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-312">10001</span></span></td>
<td><span data-ttu-id="418b0-313">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-313">Electricity</span></span></td>
<td><span data-ttu-id="418b0-314">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-314">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-315">9,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-315">9,000.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="418b0-316">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="418b0-316">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-317">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-317">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-318">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="418b0-318">Cost element</span></span></th>
<th><span data-ttu-id="418b0-319">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-319">Cost behavior</span></span></th>
<th><span data-ttu-id="418b0-320">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-320">Amount</span></span></th>
<th><span data-ttu-id="418b0-321">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="418b0-321">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-322">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-322">CC099</span></span></td>
<td><span data-ttu-id="418b0-323">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-323">Default cost center</span></span></td>
<td><span data-ttu-id="418b0-324">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-324">10001</span></span></td>
<td><span data-ttu-id="418b0-325">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-325">Electricity</span></span></td>
<td><span data-ttu-id="418b0-326">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-326">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-327">-1000,00</span><span class="sxs-lookup"><span data-stu-id="418b0-327">-1,000.00</span></span></td>
<td><span data-ttu-id="418b0-328">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-328">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-329">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-329">CC001</span></span></td>
<td><span data-ttu-id="418b0-330">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-330">HR</span></span></td>
<td><span data-ttu-id="418b0-331">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-331">10001</span></span></td>
<td><span data-ttu-id="418b0-332">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-332">Electricity</span></span></td>
<td><span data-ttu-id="418b0-333">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-333">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-334">500.00</span><span class="sxs-lookup"><span data-stu-id="418b0-334">500.00</span></span></td>
<td><span data-ttu-id="418b0-335">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-335">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-336">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-336">CC002</span></span></td>
<td><span data-ttu-id="418b0-337">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-337">Finance</span></span></td>
<td><span data-ttu-id="418b0-338">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-338">10001</span></span></td>
<td><span data-ttu-id="418b0-339">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-339">Electricity</span></span></td>
<td><span data-ttu-id="418b0-340">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-340">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-341">500.00</span><span class="sxs-lookup"><span data-stu-id="418b0-341">500.00</span></span></td>
<td><span data-ttu-id="418b0-342">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-342">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-343">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-343">CC099</span></span></td>
<td><span data-ttu-id="418b0-344">Alapértelmezett költséghely</span><span class="sxs-lookup"><span data-stu-id="418b0-344">Default cost center</span></span></td>
<td><span data-ttu-id="418b0-345">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-345">10001</span></span></td>
<td><span data-ttu-id="418b0-346">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-346">Electricity</span></span></td>
<td><span data-ttu-id="418b0-347">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-347">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-348">-9,000.00</span><span class="sxs-lookup"><span data-stu-id="418b0-348">-9,000.00</span></span></td>
<td><span data-ttu-id="418b0-349">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-349">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-350">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-350">CC001</span></span></td>
<td><span data-ttu-id="418b0-351">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-351">HR</span></span></td>
<td><span data-ttu-id="418b0-352">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-352">10001</span></span></td>
<td><span data-ttu-id="418b0-353">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-353">Electricity</span></span></td>
<td><span data-ttu-id="418b0-354">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-354">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-355">1,285.71</span><span class="sxs-lookup"><span data-stu-id="418b0-355">1,285.71</span></span></td>
<td><span data-ttu-id="418b0-356">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-356">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-357">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-357">CC002</span></span></td>
<td><span data-ttu-id="418b0-358">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-358">Finance</span></span></td>
<td><span data-ttu-id="418b0-359">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-359">10001</span></span></td>
<td><span data-ttu-id="418b0-360">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-360">Electricity</span></span></td>
<td><span data-ttu-id="418b0-361">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-361">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-362">7,714.29</span><span class="sxs-lookup"><span data-stu-id="418b0-362">7,714.29</span></span></td>
<td><span data-ttu-id="418b0-363">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-363">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-364">Ha részletes információt szeretne a költségfelosztásról és a felosztási alapokról, lásd a Költségfelosztási irányelvet és a felosztási alapokat.</span><span class="sxs-lookup"><span data-stu-id="418b0-364">For detailed information about cost distribution and allocation bases, see Cost distribution policy and Allocation bases.</span></span> <span data-ttu-id="418b0-365">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="418b0-365">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-3-process-the-overhead-rate-calculation"></a><span data-ttu-id="418b0-366">3. lépés: A járulékos költégek kiszámításának folyamata</span><span class="sxs-lookup"><span data-stu-id="418b0-366">Step 3: Process the overhead rate calculation</span></span>

<span data-ttu-id="418b0-367">A járulékos költség aránya segítségével számítható fel egy vagy több költségobjektum.</span><span class="sxs-lookup"><span data-stu-id="418b0-367">The overhead rate is used to charge one or more specific cost objects.</span></span> <span data-ttu-id="418b0-368">A díj az előre meghatározott költségarányon és a hozzárendelt kiosztási bázis nagyságán alapul.</span><span class="sxs-lookup"><span data-stu-id="418b0-368">The charge is based on a predetermined cost rate and the magnitude from the assigned allocation base.</span></span> 

#### <a name="define-the-overhead-rate"></a><span data-ttu-id="418b0-369">A járulékos költség meghatározása</span><span class="sxs-lookup"><span data-stu-id="418b0-369">Define the overhead rate</span></span>

<span data-ttu-id="418b0-370">A CC001 HR költségobjektum számos belső projekthez hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="418b0-370">Cost object CC001 HR contributes to a set of internal projects.</span></span> <span data-ttu-id="418b0-371">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR projektek.</span><span class="sxs-lookup"><span data-stu-id="418b0-371">A statistical dimension member that is named HR projects is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-372">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-372">Cost object</span></span></th>
<th><span data-ttu-id="418b0-373">óra</span><span class="sxs-lookup"><span data-stu-id="418b0-373">Hours</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-374">Proj 1</span><span class="sxs-lookup"><span data-stu-id="418b0-374">Proj 1</span></span></td>
<td><span data-ttu-id="418b0-375">1. projekt</span><span class="sxs-lookup"><span data-stu-id="418b0-375">Project 1</span></span></td>
<td><span data-ttu-id="418b0-376">3</span><span class="sxs-lookup"><span data-stu-id="418b0-376">3</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-377">Proj 2</span><span class="sxs-lookup"><span data-stu-id="418b0-377">Proj 2</span></span></td>
<td><span data-ttu-id="418b0-378">2. projekt</span><span class="sxs-lookup"><span data-stu-id="418b0-378">Project 2</span></span></td>
<td><span data-ttu-id="418b0-379">1</span><span class="sxs-lookup"><span data-stu-id="418b0-379">1</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-380">Előre meghatározott költségarány lett definiálva a költségprojektek hozzájárulásához.</span><span class="sxs-lookup"><span data-stu-id="418b0-380">A predetermined cost rate for the cost projects contribution has been defined.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-381">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-381">Cost object</span></span></th>
<th><span data-ttu-id="418b0-382">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="418b0-382">Cost element</span></span></th>
<th><span data-ttu-id="418b0-383">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-383">Cost behavior</span></span></th>
<th><span data-ttu-id="418b0-384">Egységek</span><span class="sxs-lookup"><span data-stu-id="418b0-384">Units</span></span></th>
<th><span data-ttu-id="418b0-385">Árfolyam</span><span class="sxs-lookup"><span data-stu-id="418b0-385">Rate</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-386">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-386">CC001</span></span></td>
<td><span data-ttu-id="418b0-387">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-387">HR</span></span></td>
<td><span data-ttu-id="418b0-388">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-388">10001</span></span></td>
<td><span data-ttu-id="418b0-389">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-389">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-390">1</span><span class="sxs-lookup"><span data-stu-id="418b0-390">1</span></span></td>
<td><span data-ttu-id="418b0-391">10</span><span class="sxs-lookup"><span data-stu-id="418b0-391">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-392">Az alábbi táblázat azt az eredményt mutatja, amikor a HR-projekteket elosztási bázisként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="418b0-392">The following table shows the result when the HR projects are applied as an allocation base.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-393">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-393">Cost object</span></span></th>
<th><span data-ttu-id="418b0-394">Nagyság</span><span class="sxs-lookup"><span data-stu-id="418b0-394">Magnitude</span></span></th>
<th><span data-ttu-id="418b0-395">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="418b0-395">Cost element</span></span></th>
<th><span data-ttu-id="418b0-396">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="418b0-396">Allocation factor</span></span></th>
<th><span data-ttu-id="418b0-397">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-397">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-398">Proj 1</span><span class="sxs-lookup"><span data-stu-id="418b0-398">Proj 1</span></span></td>
<td><span data-ttu-id="418b0-399">1. projekt</span><span class="sxs-lookup"><span data-stu-id="418b0-399">Project 1</span></span></td>
<td><span data-ttu-id="418b0-400">3</span><span class="sxs-lookup"><span data-stu-id="418b0-400">3</span></span></td>
<td><span data-ttu-id="418b0-401">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-401">10001</span></span></td>
<td><span data-ttu-id="418b0-402">(3 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="418b0-402">(3 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="418b0-403">30.00</span><span class="sxs-lookup"><span data-stu-id="418b0-403">30.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-404">Proj 2</span><span class="sxs-lookup"><span data-stu-id="418b0-404">Proj 2</span></span></td>
<td><span data-ttu-id="418b0-405">2. projekt</span><span class="sxs-lookup"><span data-stu-id="418b0-405">Project 2</span></span></td>
<td><span data-ttu-id="418b0-406">1</span><span class="sxs-lookup"><span data-stu-id="418b0-406">1</span></span></td>
<td><span data-ttu-id="418b0-407">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-407">10001</span></span></td>
<td><span data-ttu-id="418b0-408">(1 ÷ 1) × 10.00</span><span class="sxs-lookup"><span data-stu-id="418b0-408">(1 ÷ 1) × 10.00</span></span></td>
<td><span data-ttu-id="418b0-409">10.00</span><span class="sxs-lookup"><span data-stu-id="418b0-409">10.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal"></a><span data-ttu-id="418b0-410">Napló</span><span class="sxs-lookup"><span data-stu-id="418b0-410">Journal</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="418b0-411">Napló</span><span class="sxs-lookup"><span data-stu-id="418b0-411">Journal</span></span></th>
<th><span data-ttu-id="418b0-412">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="418b0-412">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="418b0-413">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-413">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="418b0-414">Verzió</span><span class="sxs-lookup"><span data-stu-id="418b0-414">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-415">00003</span><span class="sxs-lookup"><span data-stu-id="418b0-415">00003</span></span></td>
<td><span data-ttu-id="418b0-416">Járulékos díj számítás napló</span><span class="sxs-lookup"><span data-stu-id="418b0-416">Overhead rate calculation journal</span></span></td>
<td><span data-ttu-id="418b0-417">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="418b0-417">Fiscal</span></span></td>
<td><span data-ttu-id="418b0-418">2017</span><span class="sxs-lookup"><span data-stu-id="418b0-418">2017</span></span></td>
<td><span data-ttu-id="418b0-419">1. időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-419">Period 1</span></span></td>
<td><span data-ttu-id="418b0-420">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-420">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a><span data-ttu-id="418b0-421">Naplóbejegyzések (Naplóbejegyzések járulékos díj számításához)</span><span class="sxs-lookup"><span data-stu-id="418b0-421">Journal entries (Journal entries for overhead rate calculation)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="418b0-422">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="418b0-422">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-423">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-423">Cost object</span></span></th>
<th><span data-ttu-id="418b0-424">Nagyság</span><span class="sxs-lookup"><span data-stu-id="418b0-424">Magnitude</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-425">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-425">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-426">Proj 1</span><span class="sxs-lookup"><span data-stu-id="418b0-426">Proj 1</span></span></td>
<td><span data-ttu-id="418b0-427">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="418b0-427">Internal Proj 1</span></span></td>
<td><span data-ttu-id="418b0-428">3,00</span><span class="sxs-lookup"><span data-stu-id="418b0-428">3.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-429">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-429">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-430">Proj 2</span><span class="sxs-lookup"><span data-stu-id="418b0-430">Proj 2</span></span></td>
<td><span data-ttu-id="418b0-431">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="418b0-431">Internal Proj 2</span></span></td>
<td><span data-ttu-id="418b0-432">1.00</span><span class="sxs-lookup"><span data-stu-id="418b0-432">1.00</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="418b0-433">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="418b0-433">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-434">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-434">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-435">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="418b0-435">Cost element</span></span></th>
<th><span data-ttu-id="418b0-436">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-436">Cost behavior</span></span></th>
<th><span data-ttu-id="418b0-437">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-437">Amount</span></span></th>
<th><span data-ttu-id="418b0-438">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="418b0-438">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-439">CC0001</span><span class="sxs-lookup"><span data-stu-id="418b0-439">CC0001</span></span></td>
<td><span data-ttu-id="418b0-440">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-440">HR</span></span></td>
<td><span data-ttu-id="418b0-441">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-441">10001</span></span></td>
<td><span data-ttu-id="418b0-442">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-442">Electricity</span></span></td>
<td><span data-ttu-id="418b0-443">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-443">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-444">-30.00</span><span class="sxs-lookup"><span data-stu-id="418b0-444">-30.00</span></span></td>
<td><span data-ttu-id="418b0-445">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-445">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-446">Proj 1</span><span class="sxs-lookup"><span data-stu-id="418b0-446">Proj 1</span></span></td>
<td><span data-ttu-id="418b0-447">Belső proj 1</span><span class="sxs-lookup"><span data-stu-id="418b0-447">Internal Proj 1</span></span></td>
<td><span data-ttu-id="418b0-448">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-448">10001</span></span></td>
<td><span data-ttu-id="418b0-449">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-449">Electricity</span></span></td>
<td><span data-ttu-id="418b0-450">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-450">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-451">30.00</span><span class="sxs-lookup"><span data-stu-id="418b0-451">30.00</span></span></td>
<td><span data-ttu-id="418b0-452">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-452">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-453">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-453">CC001</span></span></td>
<td><span data-ttu-id="418b0-454">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-454">HR</span></span></td>
<td><span data-ttu-id="418b0-455">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-455">10001</span></span></td>
<td><span data-ttu-id="418b0-456">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-456">Electricity</span></span></td>
<td><span data-ttu-id="418b0-457">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-457">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-458">-10,00</span><span class="sxs-lookup"><span data-stu-id="418b0-458">-10.00</span></span></td>
<td><span data-ttu-id="418b0-459">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-459">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-460">Proj 2</span><span class="sxs-lookup"><span data-stu-id="418b0-460">Proj 2</span></span></td>
<td><span data-ttu-id="418b0-461">Belső proj 2</span><span class="sxs-lookup"><span data-stu-id="418b0-461">Internal Proj 2</span></span></td>
<td><span data-ttu-id="418b0-462">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-462">10001</span></span></td>
<td><span data-ttu-id="418b0-463">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-463">Electricity</span></span></td>
<td><span data-ttu-id="418b0-464">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-464">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-465">10.00</span><span class="sxs-lookup"><span data-stu-id="418b0-465">10.00</span></span></td>
<td><span data-ttu-id="418b0-466">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-466">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-467">A járulékos díj irányelvére vonatkozó részletes információkért lásd: A járulékos díj irányelvei és Felosztási bázisok.</span><span class="sxs-lookup"><span data-stu-id="418b0-467">For detailed information about overhead rate policy, see Overhead rate policy and Allocation bases.</span></span> <span data-ttu-id="418b0-468">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="418b0-468">(Note that this topic isn't competed yet but is coming soon.)</span></span>

### <a name="step-4-process-the-cost-allocation-calculation"></a><span data-ttu-id="418b0-469">4. lépés: A kötségfelosztásra vonatkozó számítás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="418b0-469">Step 4: Process the cost allocation calculation</span></span>

<span data-ttu-id="418b0-470">A felosztást arra használják, hogy egy költségobjektum egyenlegét mások költségobjektumokhoz hozzárendeljék egy felosztási alap alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="418b0-470">Allocation is used to allocate the balance of a cost object to other cost objects by applying an allocation base.</span></span> <span data-ttu-id="418b0-471">A Finance and Operations a reciprokális felosztási módszert támogatja.</span><span class="sxs-lookup"><span data-stu-id="418b0-471">Finance and Operations supports the reciprocal allocation method.</span></span> <span data-ttu-id="418b0-472">A reciprokális felosztási módszer esetében a segédköltség-objektumok által kicserélt kölcsönös szolgáltatások teljes mértékben elismertek.</span><span class="sxs-lookup"><span data-stu-id="418b0-472">In the reciprocal allocation method, the mutual services that auxiliary cost objects exchange are fully recognized.</span></span> <span data-ttu-id="418b0-473">A rendszer automatikusan meghatározza a felosztások végrehajtásának megfelelő sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="418b0-473">The system automatically determines the correct order to perform the allocations in.</span></span> <span data-ttu-id="418b0-474">A költségobjektumok egyenlegének felosztása egyetlen felosztási alap szerint történik.</span><span class="sxs-lookup"><span data-stu-id="418b0-474">The balance of a cost object is allocated by a single allocation base.</span></span> <span data-ttu-id="418b0-475">A rendszer támogatja a költségobjektum-dimenziók és a hozzájuk tartozó tagok közötti felosztásokat.</span><span class="sxs-lookup"><span data-stu-id="418b0-475">Allocations across cost objects dimensions and their respective members are supported.</span></span> <span data-ttu-id="418b0-476">A felosztás sorrendjét a költség ellenőrzőegysége vezérli.</span><span class="sxs-lookup"><span data-stu-id="418b0-476">The allocation order is controlled by the cost control unit.</span></span> 

<span data-ttu-id="418b0-477">[![Fordított módszer](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span><span class="sxs-lookup"><span data-stu-id="418b0-477">[![Reciprocal method](./media/reciprocal-method.png)](./media/reciprocal-method.png)</span></span>

#### <a name="define-the-cost-allocation"></a><span data-ttu-id="418b0-478">A költségfelosztás meghatározása</span><span class="sxs-lookup"><span data-stu-id="418b0-478">Define the cost allocation</span></span>

<span data-ttu-id="418b0-479">Íme egy egyszerű példa, amely bemutatja, hogyan követhetők nyomon a költségfolyamatok.</span><span class="sxs-lookup"><span data-stu-id="418b0-479">Here is a simple example that explains how you can trace the flow of cost.</span></span> <span data-ttu-id="418b0-480">A CC001 HR költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="418b0-480">Cost object CC001 HR contributes to several cost objects.</span></span> <span data-ttu-id="418b0-481">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: HR-szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="418b0-481">A statistical dimension member that is named HR services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-482">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-482">Cost object</span></span></th>
<th><span data-ttu-id="418b0-483">HR-szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="418b0-483">HR services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-484">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-484">CC002</span></span></td>
<td><span data-ttu-id="418b0-485">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-485">Finance</span></span></td>
<td><span data-ttu-id="418b0-486">35</span><span class="sxs-lookup"><span data-stu-id="418b0-486">35</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-487">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-487">CC003</span></span></td>
<td><span data-ttu-id="418b0-488">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-488">Assembly</span></span></td>
<td><span data-ttu-id="418b0-489">55</span><span class="sxs-lookup"><span data-stu-id="418b0-489">55</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-490">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-490">CC004</span></span></td>
<td><span data-ttu-id="418b0-491">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-491">Packaging</span></span></td>
<td><span data-ttu-id="418b0-492">10</span><span class="sxs-lookup"><span data-stu-id="418b0-492">10</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-493">A CC002 pénzügy költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="418b0-493">Cost object CC002 Finance contributes to several cost objects.</span></span> <span data-ttu-id="418b0-494">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: pénzügyi szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="418b0-494">A statistical dimension member that is named Finance services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-495">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-495">Cost object</span></span></th>
<th><span data-ttu-id="418b0-496">Pénzügyi szolgáltatások</span><span class="sxs-lookup"><span data-stu-id="418b0-496">Finance services</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-497">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-497">CC003</span></span></td>
<td><span data-ttu-id="418b0-498">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-498">Assembly</span></span></td>
<td><span data-ttu-id="418b0-499">65</span><span class="sxs-lookup"><span data-stu-id="418b0-499">65</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-500">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-500">CC004</span></span></td>
<td><span data-ttu-id="418b0-501">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-501">Packaging</span></span></td>
<td><span data-ttu-id="418b0-502">35</span><span class="sxs-lookup"><span data-stu-id="418b0-502">35</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-503">A CC003 összeszerelés költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="418b0-503">Cost object CC003 Assembly contributes to several cost objects.</span></span> <span data-ttu-id="418b0-504">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: összeszerelési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="418b0-504">A statistical dimension member that is named Assembly services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-505">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-505">Cost object</span></span></th>
<th><span data-ttu-id="418b0-506">Összeszerelési szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="418b0-506">Assembly services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-507">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-507">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-508">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-508">Product 1</span></span></td>
<td><span data-ttu-id="418b0-509">60</span><span class="sxs-lookup"><span data-stu-id="418b0-509">60</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-510">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-510">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-511">2. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-511">Product 2</span></span></td>
<td><span data-ttu-id="418b0-512">20</span><span class="sxs-lookup"><span data-stu-id="418b0-512">20</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-513">A CC004 csomagolás költségobjektum több költségobjektumhoz is hozzájárul.</span><span class="sxs-lookup"><span data-stu-id="418b0-513">Cost object CC004 Packaging contributes to several cost objects.</span></span> <span data-ttu-id="418b0-514">A felhasznált mennyiség nagyságának méréséhez létrehoz a rendszer egy statisztikai dimenziótagot, amelynek neve: csomagolási szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="418b0-514">A statistical dimension member that is named Packaging services is created to measure the consumed magnitude.</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-515">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-515">Cost object</span></span></th>
<th><span data-ttu-id="418b0-516">Csomagolóanyag-szolgáltatások (óra)</span><span class="sxs-lookup"><span data-stu-id="418b0-516">Packaging services (hours)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-517">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-517">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-518">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-518">Product 1</span></span></td>
<td><span data-ttu-id="418b0-519">80</span><span class="sxs-lookup"><span data-stu-id="418b0-519">80</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-520">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-520">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-521">2. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-521">Product 2</span></span></td>
<td><span data-ttu-id="418b0-522">15.</span><span class="sxs-lookup"><span data-stu-id="418b0-522">15</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-523">**Megjegyzés:** A Finance and Operations esetében a statisztikai mérések, például a termék gyártásához szükséges órák száma a forrásadatokból származhatnak.</span><span class="sxs-lookup"><span data-stu-id="418b0-523">**Note:** In Finance and Operations, statistical measures such as the production hours that a product consumes can be derived from source data.</span></span> <span data-ttu-id="418b0-524">A statisztikai mérési szolgáltatókról szóló bővebb információkért lásd: Statisztikai mérték szolgáltatójának sablonjai.</span><span class="sxs-lookup"><span data-stu-id="418b0-524">For more detailed information about statistical measure providers, see Statistical measure provider template.</span></span> <span data-ttu-id="418b0-525">(Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.) Az alábbi táblázat azt az eredményt mutatja, amikor a HR-szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="418b0-525">(Note that this topic isn't completed yet but is coming soon.) The following table shows the result when the HR services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-526">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-526">Cost object</span></span></th>
<th><span data-ttu-id="418b0-527">Nagyság</span><span class="sxs-lookup"><span data-stu-id="418b0-527">Magnitude</span></span></th>
<th><span data-ttu-id="418b0-528">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="418b0-528">Allocation factor</span></span></th>
<th><span data-ttu-id="418b0-529">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-529">Amount</span></span></th>
<th><span data-ttu-id="418b0-530">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-530">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-531">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-531">CC002</span></span></td>
<td><span data-ttu-id="418b0-532">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-532">Finance</span></span></td>
<td><span data-ttu-id="418b0-533">35</span><span class="sxs-lookup"><span data-stu-id="418b0-533">35</span></span></td>
<td><span data-ttu-id="418b0-534">(35 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="418b0-534">(35 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="418b0-535">175.00</span><span class="sxs-lookup"><span data-stu-id="418b0-535">175.00</span></span></td>
<td><span data-ttu-id="418b0-536">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-536">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-537">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-537">CC003</span></span></td>
<td><span data-ttu-id="418b0-538">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-538">Assembly</span></span></td>
<td><span data-ttu-id="418b0-539">55</span><span class="sxs-lookup"><span data-stu-id="418b0-539">55</span></span></td>
<td><span data-ttu-id="418b0-540">(55 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="418b0-540">(55 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="418b0-541">275.00</span><span class="sxs-lookup"><span data-stu-id="418b0-541">275.00</span></span></td>
<td><span data-ttu-id="418b0-542">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-542">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-543">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-543">CC004</span></span></td>
<td><span data-ttu-id="418b0-544">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-544">Packaging</span></span></td>
<td><span data-ttu-id="418b0-545">10</span><span class="sxs-lookup"><span data-stu-id="418b0-545">10</span></span></td>
<td><span data-ttu-id="418b0-546">(10 ÷ 100) × 500.00</span><span class="sxs-lookup"><span data-stu-id="418b0-546">(10 ÷ 100) × 500.00</span></span></td>
<td><span data-ttu-id="418b0-547">50,00</span><span class="sxs-lookup"><span data-stu-id="418b0-547">50.00</span></span></td>
<td><span data-ttu-id="418b0-548">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-548">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-549">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-549">CC002</span></span></td>
<td><span data-ttu-id="418b0-550">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-550">Finance</span></span></td>
<td><span data-ttu-id="418b0-551">35</span><span class="sxs-lookup"><span data-stu-id="418b0-551">35</span></span></td>
<td><span data-ttu-id="418b0-552">(35 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="418b0-552">(35 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="418b0-553">436.00</span><span class="sxs-lookup"><span data-stu-id="418b0-553">436.00</span></span></td>
<td><span data-ttu-id="418b0-554">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-554">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-555">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-555">CC003</span></span></td>
<td><span data-ttu-id="418b0-556">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-556">Assembly</span></span></td>
<td><span data-ttu-id="418b0-557">55</span><span class="sxs-lookup"><span data-stu-id="418b0-557">55</span></span></td>
<td><span data-ttu-id="418b0-558">(55 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="418b0-558">(55 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="418b0-559">685.14</span><span class="sxs-lookup"><span data-stu-id="418b0-559">685.14</span></span></td>
<td><span data-ttu-id="418b0-560">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-560">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-561">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-561">CC004</span></span></td>
<td><span data-ttu-id="418b0-562">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-562">Packaging</span></span></td>
<td><span data-ttu-id="418b0-563">10</span><span class="sxs-lookup"><span data-stu-id="418b0-563">10</span></span></td>
<td><span data-ttu-id="418b0-564">(10 ÷ 100) × 1,245.71</span><span class="sxs-lookup"><span data-stu-id="418b0-564">(10 ÷ 100) × 1,245.71</span></span></td>
<td><span data-ttu-id="418b0-565">124.57</span><span class="sxs-lookup"><span data-stu-id="418b0-565">124.57</span></span></td>
<td><span data-ttu-id="418b0-566">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-566">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-567">Az alábbi táblázat azt az eredményt mutatja, amikor a Pénzügyi szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="418b0-567">The following table shows the result when the Finance services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-568">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-568">Cost object</span></span></th>
<th><span data-ttu-id="418b0-569">Nagyság</span><span class="sxs-lookup"><span data-stu-id="418b0-569">Magnitude</span></span></th>
<th><span data-ttu-id="418b0-570">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="418b0-570">Allocation factor</span></span></th>
<th><span data-ttu-id="418b0-571">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-571">Amount</span></span></th>
<th><span data-ttu-id="418b0-572">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-572">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-573">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-573">CC003</span></span></td>
<td><span data-ttu-id="418b0-574">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-574">Assembly</span></span></td>
<td><span data-ttu-id="418b0-575">65</span><span class="sxs-lookup"><span data-stu-id="418b0-575">65</span></span></td>
<td><span data-ttu-id="418b0-576">(65 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="418b0-576">(65 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="418b0-577">438.75</span><span class="sxs-lookup"><span data-stu-id="418b0-577">438.75</span></span></td>
<td><span data-ttu-id="418b0-578">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-578">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-579">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-579">CC004</span></span></td>
<td><span data-ttu-id="418b0-580">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-580">Packaging</span></span></td>
<td><span data-ttu-id="418b0-581">35</span><span class="sxs-lookup"><span data-stu-id="418b0-581">35</span></span></td>
<td><span data-ttu-id="418b0-582">(35 ÷ 100) × (500.00 + 175.00)</span><span class="sxs-lookup"><span data-stu-id="418b0-582">(35 ÷ 100) × (500.00 + 175.00)</span></span></td>
<td><span data-ttu-id="418b0-583">236.25</span><span class="sxs-lookup"><span data-stu-id="418b0-583">236.25</span></span></td>
<td><span data-ttu-id="418b0-584">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-584">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-585">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-585">CC003</span></span></td>
<td><span data-ttu-id="418b0-586">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-586">Assembly</span></span></td>
<td><span data-ttu-id="418b0-587">65</span><span class="sxs-lookup"><span data-stu-id="418b0-587">65</span></span></td>
<td><span data-ttu-id="418b0-588">(65 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="418b0-588">(65 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="418b0-589">5,297.69</span><span class="sxs-lookup"><span data-stu-id="418b0-589">5,297.69</span></span></td>
<td><span data-ttu-id="418b0-590">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-590">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-591">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-591">CC004</span></span></td>
<td><span data-ttu-id="418b0-592">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-592">Packaging</span></span></td>
<td><span data-ttu-id="418b0-593">35</span><span class="sxs-lookup"><span data-stu-id="418b0-593">35</span></span></td>
<td><span data-ttu-id="418b0-594">(35 ÷ 100) × (7,714.29 + 436.00)</span><span class="sxs-lookup"><span data-stu-id="418b0-594">(35 ÷ 100) × (7,714.29 + 436.00)</span></span></td>
<td><span data-ttu-id="418b0-595">2,852.60</span><span class="sxs-lookup"><span data-stu-id="418b0-595">2,852.60</span></span></td>
<td><span data-ttu-id="418b0-596">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-596">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-597">Az alábbi táblázat azt az eredményt mutatja, amikor az Összeszerelési szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="418b0-597">The following table shows the result when the Assembly services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-598">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-598">Cost object</span></span></th>
<th><span data-ttu-id="418b0-599">Nagyság</span><span class="sxs-lookup"><span data-stu-id="418b0-599">Magnitude</span></span></th>
<th><span data-ttu-id="418b0-600">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="418b0-600">Allocation factor</span></span></th>
<th><span data-ttu-id="418b0-601">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-601">Amount</span></span></th>
<th><span data-ttu-id="418b0-602">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-602">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-603">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-603">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-604">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-604">Product 1</span></span></td>
<td><span data-ttu-id="418b0-605">60</span><span class="sxs-lookup"><span data-stu-id="418b0-605">60</span></span></td>
<td><span data-ttu-id="418b0-606">(60 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="418b0-606">(60 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="418b0-607">535.31</span><span class="sxs-lookup"><span data-stu-id="418b0-607">535.31</span></span></td>
<td><span data-ttu-id="418b0-608">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-608">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-609">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-609">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-610">2. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-610">Product 2</span></span></td>
<td><span data-ttu-id="418b0-611">20</span><span class="sxs-lookup"><span data-stu-id="418b0-611">20</span></span></td>
<td><span data-ttu-id="418b0-612">(20 ÷ 80) × (275.00 + 438.75)</span><span class="sxs-lookup"><span data-stu-id="418b0-612">(20 ÷ 80) × (275.00 + 438.75)</span></span></td>
<td><span data-ttu-id="418b0-613">178.44</span><span class="sxs-lookup"><span data-stu-id="418b0-613">178.44</span></span></td>
<td><span data-ttu-id="418b0-614">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-614">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-615">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-615">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-616">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-616">Product 1</span></span></td>
<td><span data-ttu-id="418b0-617">60</span><span class="sxs-lookup"><span data-stu-id="418b0-617">60</span></span></td>
<td><span data-ttu-id="418b0-618">(60 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="418b0-618">(60 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="418b0-619">4,487.12</span><span class="sxs-lookup"><span data-stu-id="418b0-619">4,487.12</span></span></td>
<td><span data-ttu-id="418b0-620">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-620">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-621">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-621">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-622">2. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-622">Product 2</span></span></td>
<td><span data-ttu-id="418b0-623">20</span><span class="sxs-lookup"><span data-stu-id="418b0-623">20</span></span></td>
<td><span data-ttu-id="418b0-624">(20 ÷ 80) × (5,297.69 + 685.14)</span><span class="sxs-lookup"><span data-stu-id="418b0-624">(20 ÷ 80) × (5,297.69 + 685.14)</span></span></td>
<td><span data-ttu-id="418b0-625">1,495.71</span><span class="sxs-lookup"><span data-stu-id="418b0-625">1,495.71</span></span></td>
<td><span data-ttu-id="418b0-626">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-626">Variable cost</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="418b0-627">Az alábbi táblázat azt az eredményt mutatja, amikor a Csomagolási szolgáltatásokat a teljes költség (fix költség és változó költség) allokációs alapjaként alkalmazzák.</span><span class="sxs-lookup"><span data-stu-id="418b0-627">The following table shows the result when the Packaging services are applied as an allocation base for total cost (fixed cost and variable cost).</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-628">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-628">Cost object</span></span></th>
<th><span data-ttu-id="418b0-629">Nagyság</span><span class="sxs-lookup"><span data-stu-id="418b0-629">Magnitude</span></span></th>
<th><span data-ttu-id="418b0-630">Felosztási tényező</span><span class="sxs-lookup"><span data-stu-id="418b0-630">Allocation factor</span></span></th>
<th><span data-ttu-id="418b0-631">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-631">Amount</span></span></th>
<th><span data-ttu-id="418b0-632">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-632">Cost behavior</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-633">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-633">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-634">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-634">Product 1</span></span></td>
<td><span data-ttu-id="418b0-635">80</span><span class="sxs-lookup"><span data-stu-id="418b0-635">80</span></span></td>
<td><span data-ttu-id="418b0-636">(80 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="418b0-636">(80 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="418b0-637">241.05</span><span class="sxs-lookup"><span data-stu-id="418b0-637">241.05</span></span></td>
<td><span data-ttu-id="418b0-638">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-638">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-639">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-639">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-640">2. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-640">Product 2</span></span></td>
<td><span data-ttu-id="418b0-641">15.</span><span class="sxs-lookup"><span data-stu-id="418b0-641">15</span></span></td>
<td><span data-ttu-id="418b0-642">(15 ÷ 95) × (50.00 + 236.25)</span><span class="sxs-lookup"><span data-stu-id="418b0-642">(15 ÷ 95) × (50.00 + 236.25)</span></span></td>
<td><span data-ttu-id="418b0-643">45.20</span><span class="sxs-lookup"><span data-stu-id="418b0-643">45.20</span></span></td>
<td><span data-ttu-id="418b0-644">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-644">Fixed cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-645">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-645">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-646">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-646">Product 1</span></span></td>
<td><span data-ttu-id="418b0-647">80</span><span class="sxs-lookup"><span data-stu-id="418b0-647">80</span></span></td>
<td><span data-ttu-id="418b0-648">(80 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="418b0-648">(80 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="418b0-649">2,507.09</span><span class="sxs-lookup"><span data-stu-id="418b0-649">2,507.09</span></span></td>
<td><span data-ttu-id="418b0-650">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-650">Variable cost</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-651">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-651">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-652">2. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-652">Product 2</span></span></td>
<td><span data-ttu-id="418b0-653">15.</span><span class="sxs-lookup"><span data-stu-id="418b0-653">15</span></span></td>
<td><span data-ttu-id="418b0-654">(15 ÷ 95) × (2,852.60 + 124.57)</span><span class="sxs-lookup"><span data-stu-id="418b0-654">(15 ÷ 95) × (2,852.60 + 124.57)</span></span></td>
<td><span data-ttu-id="418b0-655">470.08</span><span class="sxs-lookup"><span data-stu-id="418b0-655">470.08</span></span></td>
<td><span data-ttu-id="418b0-656">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-656">Variable cost</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a><span data-ttu-id="418b0-657">Naplóbejegyzések (költségobjektum-egyenlegek naplóbejegyzései)</span><span class="sxs-lookup"><span data-stu-id="418b0-657">Journal entries (cost object balance journal entries)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="418b0-658">Napló</span><span class="sxs-lookup"><span data-stu-id="418b0-658">Journal</span></span></th>
<th><span data-ttu-id="418b0-659">Napló típusa</span><span class="sxs-lookup"><span data-stu-id="418b0-659">Journal type</span></span></th>
<th colspan="3"><span data-ttu-id="418b0-660">Pénzügyi naptári időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-660">Fiscal calendar period</span></span></th>
<th><span data-ttu-id="418b0-661">Verzió</span><span class="sxs-lookup"><span data-stu-id="418b0-661">Version</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-662">00004</span><span class="sxs-lookup"><span data-stu-id="418b0-662">00004</span></span></td>
<td><span data-ttu-id="418b0-663">Költségfelosztási napló</span><span class="sxs-lookup"><span data-stu-id="418b0-663">Cost allocation journal</span></span></td>
<td><span data-ttu-id="418b0-664">Pénzügyi</span><span class="sxs-lookup"><span data-stu-id="418b0-664">Fiscal</span></span></td>
<td><span data-ttu-id="418b0-665">2017</span><span class="sxs-lookup"><span data-stu-id="418b0-665">2017</span></span></td>
<td><span data-ttu-id="418b0-666">1. időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-666">Period 1</span></span></td>
<td><span data-ttu-id="418b0-667">Járulékos költség számítása / 01-02-2017 11:51:00 PM / Főkönyv /2017 / 1. időszak</span><span class="sxs-lookup"><span data-stu-id="418b0-667">Overhead calculation / 01-02-2017 11:51:00 PM / Ledger /2017 / Period 1</span></span></td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a><span data-ttu-id="418b0-668">Naplósorok</span><span class="sxs-lookup"><span data-stu-id="418b0-668">Journal lines</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="418b0-669">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="418b0-669">Accounting date</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-670">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-670">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-671">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="418b0-671">Cost element</span></span></th>
<th><span data-ttu-id="418b0-672">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-672">Cost behavior</span></span></th>
<th><span data-ttu-id="418b0-673">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-673">Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-674">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-674">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-675">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-675">CC001</span></span></td>
<td><span data-ttu-id="418b0-676">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-676">HR</span></span></td>
<td><span data-ttu-id="418b0-677">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-677">10001</span></span></td>
<td><span data-ttu-id="418b0-678">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-678">Electricity</span></span></td>
<td><span data-ttu-id="418b0-679">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-679">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-680">500.00</span><span class="sxs-lookup"><span data-stu-id="418b0-680">500.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-681">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-681">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-682">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-682">CC001</span></span></td>
<td><span data-ttu-id="418b0-683">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-683">HR</span></span></td>
<td><span data-ttu-id="418b0-684">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-684">10001</span></span></td>
<td><span data-ttu-id="418b0-685">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-685">Electricity</span></span></td>
<td><span data-ttu-id="418b0-686">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-686">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-687">1,245.71</span><span class="sxs-lookup"><span data-stu-id="418b0-687">1,245.71</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-688">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-688">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-689">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-689">CC002</span></span></td>
<td><span data-ttu-id="418b0-690">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-690">Finance</span></span></td>
<td><span data-ttu-id="418b0-691">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-691">10001</span></span></td>
<td><span data-ttu-id="418b0-692">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-692">Electricity</span></span></td>
<td><span data-ttu-id="418b0-693">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-693">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-694">675.00</span><span class="sxs-lookup"><span data-stu-id="418b0-694">675.00</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-695">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-695">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-696">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-696">CC002</span></span></td>
<td><span data-ttu-id="418b0-697">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-697">Finance</span></span></td>
<td><span data-ttu-id="418b0-698">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-698">10001</span></span></td>
<td><span data-ttu-id="418b0-699">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-699">Electricity</span></span></td>
<td><span data-ttu-id="418b0-700">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-700">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-701">8,150.29</span><span class="sxs-lookup"><span data-stu-id="418b0-701">8,150.29</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-702">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-702">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-703">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-703">CC003</span></span></td>
<td><span data-ttu-id="418b0-704">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-704">Assembly</span></span></td>
<td><span data-ttu-id="418b0-705">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-705">10001</span></span></td>
<td><span data-ttu-id="418b0-706">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-706">Electricity</span></span></td>
<td><span data-ttu-id="418b0-707">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-707">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-708">713.75</span><span class="sxs-lookup"><span data-stu-id="418b0-708">713.75</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-709">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-709">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-710">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-710">CC003</span></span></td>
<td><span data-ttu-id="418b0-711">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-711">Assembly</span></span></td>
<td><span data-ttu-id="418b0-712">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-712">10001</span></span></td>
<td><span data-ttu-id="418b0-713">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-713">Electricity</span></span></td>
<td><span data-ttu-id="418b0-714">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-714">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-715">5,982.83</span><span class="sxs-lookup"><span data-stu-id="418b0-715">5,982.83</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-716">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-716">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-717">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-717">CC003</span></span></td>
<td><span data-ttu-id="418b0-718">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-718">Packaging</span></span></td>
<td><span data-ttu-id="418b0-719">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-719">10001</span></span></td>
<td><span data-ttu-id="418b0-720">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-720">Electricity</span></span></td>
<td><span data-ttu-id="418b0-721">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-721">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-722">286.25</span><span class="sxs-lookup"><span data-stu-id="418b0-722">286.25</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-723">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-723">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-724">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-724">CC003</span></span></td>
<td><span data-ttu-id="418b0-725">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-725">Packaging</span></span></td>
<td><span data-ttu-id="418b0-726">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-726">10001</span></span></td>
<td><span data-ttu-id="418b0-727">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-727">Electricity</span></span></td>
<td><span data-ttu-id="418b0-728">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-728">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-729">2,977.17</span><span class="sxs-lookup"><span data-stu-id="418b0-729">2,977.17</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-730">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-730">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-731">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-731">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-732">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-732">Product 1</span></span></td>
<td><span data-ttu-id="418b0-733">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-733">10001</span></span></td>
<td><span data-ttu-id="418b0-734">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-734">Electricity</span></span></td>
<td><span data-ttu-id="418b0-735">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-735">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-736">776.36</span><span class="sxs-lookup"><span data-stu-id="418b0-736">776.36</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-737">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-737">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-738">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-738">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-739">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-739">Product 1</span></span></td>
<td><span data-ttu-id="418b0-740">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-740">10001</span></span></td>
<td><span data-ttu-id="418b0-741">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-741">Electricity</span></span></td>
<td><span data-ttu-id="418b0-742">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-742">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-743">6,994.21</span><span class="sxs-lookup"><span data-stu-id="418b0-743">6,994.21</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-744">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-744">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-745">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-745">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-746">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-746">Product 1</span></span></td>
<td><span data-ttu-id="418b0-747">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-747">10001</span></span></td>
<td><span data-ttu-id="418b0-748">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-748">Electricity</span></span></td>
<td><span data-ttu-id="418b0-749">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-749">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-750">223.64</span><span class="sxs-lookup"><span data-stu-id="418b0-750">223.64</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-751">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-751">January 31, 2017</span></span></td>
<td><span data-ttu-id="418b0-752">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-752">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-753">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-753">Product 1</span></span></td>
<td><span data-ttu-id="418b0-754">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-754">10001</span></span></td>
<td><span data-ttu-id="418b0-755">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-755">Electricity</span></span></td>
<td><span data-ttu-id="418b0-756">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-756">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-757">1,965.79</span><span class="sxs-lookup"><span data-stu-id="418b0-757">1,965.79</span></span></td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a><span data-ttu-id="418b0-758">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="418b0-758">Cost entries</span></span>

<table>
<thead>
<tr>
<th colspan="2"><span data-ttu-id="418b0-759">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-759">Cost object</span></span></th>
<th colspan="2"><span data-ttu-id="418b0-760">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="418b0-760">Cost element</span></span></th>
<th><span data-ttu-id="418b0-761">Költség működése</span><span class="sxs-lookup"><span data-stu-id="418b0-761">Cost behavior</span></span></th>
<th><span data-ttu-id="418b0-762">Összeg</span><span class="sxs-lookup"><span data-stu-id="418b0-762">Amount</span></span></th>
<th><span data-ttu-id="418b0-763">Könyvelési dátum</span><span class="sxs-lookup"><span data-stu-id="418b0-763">Accounting date</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="418b0-764">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-764">CC001</span></span></td>
<td><span data-ttu-id="418b0-765">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-765">HR</span></span></td>
<td><span data-ttu-id="418b0-766">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-766">10001</span></span></td>
<td><span data-ttu-id="418b0-767">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-767">Electricity</span></span></td>
<td><span data-ttu-id="418b0-768">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-768">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-769">-500,00</span><span class="sxs-lookup"><span data-stu-id="418b0-769">-500.00</span></span></td>
<td><span data-ttu-id="418b0-770">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-770">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-771">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-771">CC002</span></span></td>
<td><span data-ttu-id="418b0-772">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-772">Finance</span></span></td>
<td><span data-ttu-id="418b0-773">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-773">10001</span></span></td>
<td><span data-ttu-id="418b0-774">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-774">Electricity</span></span></td>
<td><span data-ttu-id="418b0-775">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-775">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-776">175.00</span><span class="sxs-lookup"><span data-stu-id="418b0-776">175.00</span></span></td>
<td><span data-ttu-id="418b0-777">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-777">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-778">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-778">CC003</span></span></td>
<td><span data-ttu-id="418b0-779">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-779">Assembly</span></span></td>
<td><span data-ttu-id="418b0-780">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-780">10001</span></span></td>
<td><span data-ttu-id="418b0-781">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-781">Electricity</span></span></td>
<td><span data-ttu-id="418b0-782">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-782">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-783">275.00</span><span class="sxs-lookup"><span data-stu-id="418b0-783">275.00</span></span></td>
<td><span data-ttu-id="418b0-784">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-784">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-785">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-785">CC004</span></span></td>
<td><span data-ttu-id="418b0-786">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-786">Packaging</span></span></td>
<td><span data-ttu-id="418b0-787">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-787">10001</span></span></td>
<td><span data-ttu-id="418b0-788">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-788">Electricity</span></span></td>
<td><span data-ttu-id="418b0-789">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-789">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-790">50,00</span><span class="sxs-lookup"><span data-stu-id="418b0-790">50,00</span></span></td>
<td><span data-ttu-id="418b0-791">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-791">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-792">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-792">CC001</span></span></td>
<td><span data-ttu-id="418b0-793">HR</span><span class="sxs-lookup"><span data-stu-id="418b0-793">HR</span></span></td>
<td><span data-ttu-id="418b0-794">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-794">10001</span></span></td>
<td><span data-ttu-id="418b0-795">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-795">Electricity</span></span></td>
<td><span data-ttu-id="418b0-796">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-796">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-797">-1,245.71</span><span class="sxs-lookup"><span data-stu-id="418b0-797">-1,245.71</span></span></td>
<td><span data-ttu-id="418b0-798">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-798">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-799">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-799">CC002</span></span></td>
<td><span data-ttu-id="418b0-800">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-800">Finance</span></span></td>
<td><span data-ttu-id="418b0-801">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-801">10001</span></span></td>
<td><span data-ttu-id="418b0-802">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-802">Electricity</span></span></td>
<td><span data-ttu-id="418b0-803">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-803">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-804">436.00</span><span class="sxs-lookup"><span data-stu-id="418b0-804">436.00</span></span></td>
<td><span data-ttu-id="418b0-805">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-805">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-806">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-806">CC003</span></span></td>
<td><span data-ttu-id="418b0-807">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-807">Assembly</span></span></td>
<td><span data-ttu-id="418b0-808">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-808">10001</span></span></td>
<td><span data-ttu-id="418b0-809">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-809">Electricity</span></span></td>
<td><span data-ttu-id="418b0-810">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-810">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-811">685.14</span><span class="sxs-lookup"><span data-stu-id="418b0-811">685.14</span></span></td>
<td><span data-ttu-id="418b0-812">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-812">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-813">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-813">CC004</span></span></td>
<td><span data-ttu-id="418b0-814">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-814">Packaging</span></span></td>
<td><span data-ttu-id="418b0-815">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-815">10001</span></span></td>
<td><span data-ttu-id="418b0-816">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-816">Electricity</span></span></td>
<td><span data-ttu-id="418b0-817">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-817">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-818">124.57</span><span class="sxs-lookup"><span data-stu-id="418b0-818">124.57</span></span></td>
<td><span data-ttu-id="418b0-819">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-819">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-820">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-820">CC002</span></span></td>
<td><span data-ttu-id="418b0-821">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-821">Finance</span></span></td>
<td><span data-ttu-id="418b0-822">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-822">10001</span></span></td>
<td><span data-ttu-id="418b0-823">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-823">Electricity</span></span></td>
<td><span data-ttu-id="418b0-824">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-824">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-825">-675.00</span><span class="sxs-lookup"><span data-stu-id="418b0-825">-675.00</span></span></td>
<td><span data-ttu-id="418b0-826">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-826">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-827">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-827">CC003</span></span></td>
<td><span data-ttu-id="418b0-828">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-828">Assembly</span></span></td>
<td><span data-ttu-id="418b0-829">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-829">10001</span></span></td>
<td><span data-ttu-id="418b0-830">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-830">Electricity</span></span></td>
<td><span data-ttu-id="418b0-831">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-831">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-832">438.75</span><span class="sxs-lookup"><span data-stu-id="418b0-832">438.75</span></span></td>
<td><span data-ttu-id="418b0-833">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-833">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-834">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-834">CC004</span></span></td>
<td><span data-ttu-id="418b0-835">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-835">Packaging</span></span></td>
<td><span data-ttu-id="418b0-836">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-836">10001</span></span></td>
<td><span data-ttu-id="418b0-837">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-837">Electricity</span></span></td>
<td><span data-ttu-id="418b0-838">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-838">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-839">236.25</span><span class="sxs-lookup"><span data-stu-id="418b0-839">236.25</span></span></td>
<td><span data-ttu-id="418b0-840">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-840">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-841">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-841">CC002</span></span></td>
<td><span data-ttu-id="418b0-842">Pénzügy</span><span class="sxs-lookup"><span data-stu-id="418b0-842">Finance</span></span></td>
<td><span data-ttu-id="418b0-843">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-843">10001</span></span></td>
<td><span data-ttu-id="418b0-844">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-844">Electricity</span></span></td>
<td><span data-ttu-id="418b0-845">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-845">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-846">-8,150.29</span><span class="sxs-lookup"><span data-stu-id="418b0-846">-8,150.29</span></span></td>
<td><span data-ttu-id="418b0-847">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-847">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-848">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-848">CC003</span></span></td>
<td><span data-ttu-id="418b0-849">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-849">Assembly</span></span></td>
<td><span data-ttu-id="418b0-850">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-850">10001</span></span></td>
<td><span data-ttu-id="418b0-851">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-851">Electricity</span></span></td>
<td><span data-ttu-id="418b0-852">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-852">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-853">5,297.69</span><span class="sxs-lookup"><span data-stu-id="418b0-853">5,297.69</span></span></td>
<td><span data-ttu-id="418b0-854">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-854">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-855">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-855">CC004</span></span></td>
<td><span data-ttu-id="418b0-856">Csomagolás</span><span class="sxs-lookup"><span data-stu-id="418b0-856">Packaging</span></span></td>
<td><span data-ttu-id="418b0-857">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-857">10001</span></span></td>
<td><span data-ttu-id="418b0-858">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-858">Electricity</span></span></td>
<td><span data-ttu-id="418b0-859">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-859">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-860">2,852.60</span><span class="sxs-lookup"><span data-stu-id="418b0-860">2,852.60</span></span></td>
<td><span data-ttu-id="418b0-861">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-861">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-862">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-862">CC003</span></span></td>
<td><span data-ttu-id="418b0-863">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-863">Assembly</span></span></td>
<td><span data-ttu-id="418b0-864">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-864">10001</span></span></td>
<td><span data-ttu-id="418b0-865">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-865">Electricity</span></span></td>
<td><span data-ttu-id="418b0-866">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-866">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-867">-713.75</span><span class="sxs-lookup"><span data-stu-id="418b0-867">-713.75</span></span></td>
<td><span data-ttu-id="418b0-868">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-868">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-869">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-869">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-870">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-870">Product 1</span></span></td>
<td><span data-ttu-id="418b0-871">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-871">10001</span></span></td>
<td><span data-ttu-id="418b0-872">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-872">Electricity</span></span></td>
<td><span data-ttu-id="418b0-873">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-873">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-874">535.31</span><span class="sxs-lookup"><span data-stu-id="418b0-874">535.31</span></span></td>
<td><span data-ttu-id="418b0-875">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-875">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-876">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-876">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-877">2. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-877">Product 2</span></span></td>
<td><span data-ttu-id="418b0-878">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-878">10001</span></span></td>
<td><span data-ttu-id="418b0-879">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-879">Electricity</span></span></td>
<td><span data-ttu-id="418b0-880">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-880">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-881">178.44</span><span class="sxs-lookup"><span data-stu-id="418b0-881">178.44</span></span></td>
<td><span data-ttu-id="418b0-882">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-882">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-883">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-883">CC003</span></span></td>
<td><span data-ttu-id="418b0-884">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-884">Assembly</span></span></td>
<td><span data-ttu-id="418b0-885">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-885">10001</span></span></td>
<td><span data-ttu-id="418b0-886">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-886">Electricity</span></span></td>
<td><span data-ttu-id="418b0-887">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-887">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-888">-5,982.83</span><span class="sxs-lookup"><span data-stu-id="418b0-888">-5,982.83</span></span></td>
<td><span data-ttu-id="418b0-889">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-889">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-890">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-890">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-891">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-891">Product 1</span></span></td>
<td><span data-ttu-id="418b0-892">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-892">10001</span></span></td>
<td><span data-ttu-id="418b0-893">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-893">Electricity</span></span></td>
<td><span data-ttu-id="418b0-894">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-894">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-895">4,487.12</span><span class="sxs-lookup"><span data-stu-id="418b0-895">4,487.12</span></span></td>
<td><span data-ttu-id="418b0-896">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-896">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-897">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-897">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-898">2. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-898">Product 2</span></span></td>
<td><span data-ttu-id="418b0-899">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-899">10001</span></span></td>
<td><span data-ttu-id="418b0-900">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-900">Electricity</span></span></td>
<td><span data-ttu-id="418b0-901">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-901">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-902">1,495.71</span><span class="sxs-lookup"><span data-stu-id="418b0-902">1,495.71</span></span></td>
<td><span data-ttu-id="418b0-903">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-903">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-904">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-904">CC003</span></span></td>
<td><span data-ttu-id="418b0-905">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-905">Assembly</span></span></td>
<td><span data-ttu-id="418b0-906">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-906">10001</span></span></td>
<td><span data-ttu-id="418b0-907">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-907">Electricity</span></span></td>
<td><span data-ttu-id="418b0-908">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-908">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-909">-286.25</span><span class="sxs-lookup"><span data-stu-id="418b0-909">-286.25</span></span></td>
<td><span data-ttu-id="418b0-910">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-910">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-911">Term 1</span><span class="sxs-lookup"><span data-stu-id="418b0-911">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-912">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-912">Product 1</span></span></td>
<td><span data-ttu-id="418b0-913">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-913">10001</span></span></td>
<td><span data-ttu-id="418b0-914">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-914">Electricity</span></span></td>
<td><span data-ttu-id="418b0-915">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-915">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-916">241.05</span><span class="sxs-lookup"><span data-stu-id="418b0-916">241.05</span></span></td>
<td><span data-ttu-id="418b0-917">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-917">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-918">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-918">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-919">2. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-919">Product 2</span></span></td>
<td><span data-ttu-id="418b0-920">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-920">10001</span></span></td>
<td><span data-ttu-id="418b0-921">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-921">Electricity</span></span></td>
<td><span data-ttu-id="418b0-922">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-922">Fixed cost</span></span></td>
<td><span data-ttu-id="418b0-923">45.20</span><span class="sxs-lookup"><span data-stu-id="418b0-923">45.20</span></span></td>
<td><span data-ttu-id="418b0-924">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-924">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-925">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-925">CC003</span></span></td>
<td><span data-ttu-id="418b0-926">Szerelvény</span><span class="sxs-lookup"><span data-stu-id="418b0-926">Assembly</span></span></td>
<td><span data-ttu-id="418b0-927">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-927">10001</span></span></td>
<td><span data-ttu-id="418b0-928">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-928">Electricity</span></span></td>
<td><span data-ttu-id="418b0-929">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-929">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-930">-2,977.17</span><span class="sxs-lookup"><span data-stu-id="418b0-930">-2,977.17</span></span></td>
<td><span data-ttu-id="418b0-931">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-931">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-932">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-932">Prod 1</span></span></td>
<td><span data-ttu-id="418b0-933">1. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-933">Product 1</span></span></td>
<td><span data-ttu-id="418b0-934">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-934">10001</span></span></td>
<td><span data-ttu-id="418b0-935">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-935">Electricity</span></span></td>
<td><span data-ttu-id="418b0-936">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-936">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-937">2,507.09</span><span class="sxs-lookup"><span data-stu-id="418b0-937">2,507.09</span></span></td>
<td><span data-ttu-id="418b0-938">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-938">January 31, 2017</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="418b0-939">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-939">Prod 2</span></span></td>
<td><span data-ttu-id="418b0-940">2. termék</span><span class="sxs-lookup"><span data-stu-id="418b0-940">Product 2</span></span></td>
<td><span data-ttu-id="418b0-941">10001</span><span class="sxs-lookup"><span data-stu-id="418b0-941">10001</span></span></td>
<td><span data-ttu-id="418b0-942">Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-942">Electricity</span></span></td>
<td><span data-ttu-id="418b0-943">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-943">Variable cost</span></span></td>
<td><span data-ttu-id="418b0-944">470.08</span><span class="sxs-lookup"><span data-stu-id="418b0-944">470.08</span></span></td>
<td><span data-ttu-id="418b0-945">2017. január 31.</span><span class="sxs-lookup"><span data-stu-id="418b0-945">January 31, 2017</span></span></td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a><span data-ttu-id="418b0-946">Következtetés</span><span class="sxs-lookup"><span data-stu-id="418b0-946">Conclusion</span></span>
<span data-ttu-id="418b0-947">A pénzügyi könyvelésnél egy 10 000,00 értékű költséget adnak fel az elektromos áram költségéről egy üres költséghely-azonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="418b0-947">In Financial accounting, a cost of 10,000.00 for Electricity is posted to a dummy cost center ID.</span></span> <span data-ttu-id="418b0-948">Így a költségkönyvelők tudni fogják, hogy ezt a költséget fel kell osztani.</span><span class="sxs-lookup"><span data-stu-id="418b0-948">Therefore, cost accountants will know that this cost must be allocated.</span></span> <span data-ttu-id="418b0-949">A költségkönyvelésnél a költségek szervezeti szintek és egységek felé irányulnak az alkalmazott szabályok és irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="418b0-949">In Cost accounting, the costs flow across organizational units and levels, based on the policies and rules that are applied.</span></span> <span data-ttu-id="418b0-950">Minden költséghez olyan felosztási bázis társul, amely a költségek felosztása szempontjából a legjobb értékelést nyújtja.</span><span class="sxs-lookup"><span data-stu-id="418b0-950">Each cost has been associated with an allocation base that provides the best assessment for the allocation of costs.</span></span>

<table>
<thead>
<tr>
<th colspan="2" rowspan="2"><span data-ttu-id="418b0-951">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="418b0-951">Cost element</span></span></th>
<th colspan="9"><span data-ttu-id="418b0-952">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="418b0-952">Cost object</span></span></th>
<th rowspan="2"><span data-ttu-id="418b0-953">Összesen</span><span class="sxs-lookup"><span data-stu-id="418b0-953">Total</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="418b0-954">CC099</span><span class="sxs-lookup"><span data-stu-id="418b0-954">CC099</span></span></th>
<th><span data-ttu-id="418b0-955">CC001</span><span class="sxs-lookup"><span data-stu-id="418b0-955">CC001</span></span></th>
<th><span data-ttu-id="418b0-956">CC002</span><span class="sxs-lookup"><span data-stu-id="418b0-956">CC002</span></span></th>
<th><span data-ttu-id="418b0-957">CC003</span><span class="sxs-lookup"><span data-stu-id="418b0-957">CC003</span></span></th>
<th><span data-ttu-id="418b0-958">CC004</span><span class="sxs-lookup"><span data-stu-id="418b0-958">CC004</span></span></th>
<th><span data-ttu-id="418b0-959">Proj 1</span><span class="sxs-lookup"><span data-stu-id="418b0-959">Proj 1</span></span></th>
<th><span data-ttu-id="418b0-960">Proj 2</span><span class="sxs-lookup"><span data-stu-id="418b0-960">Proj 2</span></span></th>
<th><span data-ttu-id="418b0-961">Term. 1</span><span class="sxs-lookup"><span data-stu-id="418b0-961">Prod 1</span></span></th>
<th><span data-ttu-id="418b0-962">Term. 2</span><span class="sxs-lookup"><span data-stu-id="418b0-962">Prod 2</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><span data-ttu-id="418b0-963">10001 Villamos energia</span><span class="sxs-lookup"><span data-stu-id="418b0-963">10001 Electricity</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-964"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-964"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-965"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-965"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-966"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-966"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-967"><strong>0,00</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-967"><strong>0.00</strong></span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="418b0-968"><strong>30,00</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-968"><strong>30.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-969"><strong>10,00</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-969"><strong>10.00</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-970"><strong>7.770,57</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-970"><strong>7,770.57</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-971"><strong>2.189,43</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-971"><strong>2,189.43</strong></span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-972"><strong>10.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-972"><strong>10,000.00</strong></span></span></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;"><span data-ttu-id="418b0-973">Nem besorolt</span><span class="sxs-lookup"><span data-stu-id="418b0-973">Unclassified</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-974">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-974">0.00</span></span></td>
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
<td style="text-align: left;"><span data-ttu-id="418b0-975">Fix költség</span><span class="sxs-lookup"><span data-stu-id="418b0-975">Fixed cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-976">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-976">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-977">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-977">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-978">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-978">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-979">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-979">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-980">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-980">0.00</span></span></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><span data-ttu-id="418b0-981">776.36</span><span class="sxs-lookup"><span data-stu-id="418b0-981">776.36</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-982">223.64</span><span class="sxs-lookup"><span data-stu-id="418b0-982">223.64</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-983"><strong>1.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-983"><strong>1,000.00</strong></span></span></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;"><span data-ttu-id="418b0-984">Változó költség</span><span class="sxs-lookup"><span data-stu-id="418b0-984">Variable cost</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-985">000</span><span class="sxs-lookup"><span data-stu-id="418b0-985">000</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-986">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-986">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-987">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-987">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-988">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-988">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-989">0,00</span><span class="sxs-lookup"><span data-stu-id="418b0-989">0.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-990">30.00</span><span class="sxs-lookup"><span data-stu-id="418b0-990">30.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-991">1000</span><span class="sxs-lookup"><span data-stu-id="418b0-991">10.00</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-992">6,994.21</span><span class="sxs-lookup"><span data-stu-id="418b0-992">6,994.21</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-993">1,965.79</span><span class="sxs-lookup"><span data-stu-id="418b0-993">1,965.79</span></span></td>
<td style="text-align: right;"><span data-ttu-id="418b0-994"><strong>9.000,00</strong></span><span class="sxs-lookup"><span data-stu-id="418b0-994"><strong>9,000.00</strong></span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="418b0-995">Ez a témakör azt mutatja meg, hogy egy elsődleges költségelem, az 10001 villamosenergia hogyan irányul a költségelemekhez.</span><span class="sxs-lookup"><span data-stu-id="418b0-995">This topic shows how a primary cost element, 10001 Electricity, flows through the cost objects.</span></span> <span data-ttu-id="418b0-996">Emiatt ez a járulékos költség a szervezet legalsó szintjéig fel van osztva.</span><span class="sxs-lookup"><span data-stu-id="418b0-996">Therefore, this overhead cost is allocated to the lowest level in the organization.</span></span> <span data-ttu-id="418b0-997">Más szóval a legalsó szintű költségobjektumok viselik a költséget.</span><span class="sxs-lookup"><span data-stu-id="418b0-997">In other words, the cost objects at the lowest level bear the cost.</span></span> <span data-ttu-id="418b0-998">Ha a költségobjektumok közötti költség vizuális áramlását szeretné megtekinteni, a költségösszesítési házirend szabályaival megjelenítheti a költség áramlását.</span><span class="sxs-lookup"><span data-stu-id="418b0-998">If you require a visual flow of the cost between the cost objects, you can use the cost roll-up policy rules to visualize the flow of the cost.</span></span> <span data-ttu-id="418b0-999">Részletesebb tájékoztatás: Költségösszesítési irányelv.</span><span class="sxs-lookup"><span data-stu-id="418b0-999">For more detailed information, see Cost roll-up policy.</span></span> <span data-ttu-id="418b0-1000">Kérjük, vegye figyelembe, hogy ez a témakör még nem készült el, de hamarosan megérkezik.)</span><span class="sxs-lookup"><span data-stu-id="418b0-1000">(Note that this topic isn't competed yet but is coming soon.)</span></span>




