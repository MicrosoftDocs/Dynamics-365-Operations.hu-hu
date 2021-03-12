---
title: Készletkorosítási jelentés – példák és logika
description: Ez a témakör néhány példát mutat be, amelyek a készletkorosítási jelentés eredményeinek értelmezését mutatják be.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: b3822cf4c26d7ef9cd0d062d57fa909140d7e258
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983925"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="88fd7-103">Készletkorosítási jelentés – példák és logika</span><span class="sxs-lookup"><span data-stu-id="88fd7-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88fd7-104">Ez a témakör néhány példát mutat be, amelyek a **Készletkorosítási** jelentés eredményeinek értelmezését mutatják be.</span><span class="sxs-lookup"><span data-stu-id="88fd7-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="88fd7-105">Ez a jelentés egy kiválasztott cikk vagy cikkcsoport aktuális mennyiségét és készletérték-adatait több időszakra bontja szét.</span><span class="sxs-lookup"><span data-stu-id="88fd7-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="88fd7-106">Ez a témakör a jelentés belső logikáját is bemutatja.</span><span class="sxs-lookup"><span data-stu-id="88fd7-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="88fd7-107">Az ebben a témakörben szereplő példák a standard **Készlet-korosítási** jelentés eredményeinek megjelenítését mutatják be.</span><span class="sxs-lookup"><span data-stu-id="88fd7-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="88fd7-108">Általánosságban azonban azt ajánljuk, hogy a jelentés [Készletkorosítási jelentés tárhely](inventory-aging-report-storage.md) változatát használja, különösen, ha sok cikket és raktárat kell feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="88fd7-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="88fd7-109">A készlet-korosítási jelentés tárolója menti a létrehozott jelentéseket, az eredményeket interaktív lapként és diagramként jeleníti meg, valamint minden elmentett jelentés exportálását is lehetővé teszi.</span><span class="sxs-lookup"><span data-stu-id="88fd7-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="88fd7-110">A példákban használt mintaadatok</span><span class="sxs-lookup"><span data-stu-id="88fd7-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="88fd7-111">Az ebben a témakörben szereplő példák az ebben a szakaszban ismertetett minta tranzakciós adatokon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="88fd7-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="88fd7-112">Tárolásidimenzió beállítása</span><span class="sxs-lookup"><span data-stu-id="88fd7-112">Storage dimension setup</span></span>

<span data-ttu-id="88fd7-113">A példarendszer a tárolási dimenziók következő beállítását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="88fd7-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="88fd7-114">Név</span><span class="sxs-lookup"><span data-stu-id="88fd7-114">Name</span></span>      | <span data-ttu-id="88fd7-115">Aktív</span><span class="sxs-lookup"><span data-stu-id="88fd7-115">Active</span></span> | <span data-ttu-id="88fd7-116">Tényleges készlet</span><span class="sxs-lookup"><span data-stu-id="88fd7-116">Physical inventory</span></span> | <span data-ttu-id="88fd7-117">Pénzügyi készlet</span><span class="sxs-lookup"><span data-stu-id="88fd7-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="88fd7-118">Webhely</span><span class="sxs-lookup"><span data-stu-id="88fd7-118">Site</span></span>      | <span data-ttu-id="88fd7-119">Igen</span><span class="sxs-lookup"><span data-stu-id="88fd7-119">Yes</span></span>    | <span data-ttu-id="88fd7-120">Igen</span><span class="sxs-lookup"><span data-stu-id="88fd7-120">Yes</span></span>                | <span data-ttu-id="88fd7-121">Igen</span><span class="sxs-lookup"><span data-stu-id="88fd7-121">Yes</span></span>                 |
| <span data-ttu-id="88fd7-122">Raktár</span><span class="sxs-lookup"><span data-stu-id="88fd7-122">Warehouse</span></span> | <span data-ttu-id="88fd7-123">Igen</span><span class="sxs-lookup"><span data-stu-id="88fd7-123">Yes</span></span>    | <span data-ttu-id="88fd7-124">Igen</span><span class="sxs-lookup"><span data-stu-id="88fd7-124">Yes</span></span>                | <span data-ttu-id="88fd7-125">Nincs</span><span class="sxs-lookup"><span data-stu-id="88fd7-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="88fd7-126">Készletmodell</span><span class="sxs-lookup"><span data-stu-id="88fd7-126">Inventory model</span></span>

<span data-ttu-id="88fd7-127">A példarendszer esetében a kiadott termékhez tartozó készletmodell *FIFO*, és a készletmodell-beállítás **Költségár** beállítása *Tartalmazza a fizikai értéket*.</span><span class="sxs-lookup"><span data-stu-id="88fd7-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="88fd7-128">Készlettranzakciók</span><span class="sxs-lookup"><span data-stu-id="88fd7-128">Inventory transactions</span></span>

<span data-ttu-id="88fd7-129">A példarendszer a következő készlettranzakciókat tartalmazz a kiadott termékhez, amelynek cikkszáma *1000*.</span><span class="sxs-lookup"><span data-stu-id="88fd7-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="88fd7-130">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="88fd7-130">Reference</span></span>      | <span data-ttu-id="88fd7-131">Webhely</span><span class="sxs-lookup"><span data-stu-id="88fd7-131">Site</span></span> | <span data-ttu-id="88fd7-132">Raktár</span><span class="sxs-lookup"><span data-stu-id="88fd7-132">Warehouse</span></span> | <span data-ttu-id="88fd7-133">Fogadás</span><span class="sxs-lookup"><span data-stu-id="88fd7-133">Receipt</span></span>   | <span data-ttu-id="88fd7-134">Kiadás</span><span class="sxs-lookup"><span data-stu-id="88fd7-134">Issue</span></span> | <span data-ttu-id="88fd7-135">Tényleges dátum</span><span class="sxs-lookup"><span data-stu-id="88fd7-135">Physical date</span></span> | <span data-ttu-id="88fd7-136">Pénzügyi dátum</span><span class="sxs-lookup"><span data-stu-id="88fd7-136">Financial date</span></span> | <span data-ttu-id="88fd7-137">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-137">Quantity</span></span> | <span data-ttu-id="88fd7-138">Költség összege</span><span class="sxs-lookup"><span data-stu-id="88fd7-138">Cost amount</span></span> | <span data-ttu-id="88fd7-139">Tényleges önköltségi érték</span><span class="sxs-lookup"><span data-stu-id="88fd7-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="88fd7-140">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="88fd7-140">Purchase order</span></span> | <span data-ttu-id="88fd7-141">1</span><span class="sxs-lookup"><span data-stu-id="88fd7-141">1</span></span>    | <span data-ttu-id="88fd7-142">11</span><span class="sxs-lookup"><span data-stu-id="88fd7-142">11</span></span>        | <span data-ttu-id="88fd7-143">Beszerezve</span><span class="sxs-lookup"><span data-stu-id="88fd7-143">Purchased</span></span> |       | <span data-ttu-id="88fd7-144">március 15.</span><span class="sxs-lookup"><span data-stu-id="88fd7-144">March 15</span></span>      | <span data-ttu-id="88fd7-145">március 15.</span><span class="sxs-lookup"><span data-stu-id="88fd7-145">March 15</span></span>       | <span data-ttu-id="88fd7-146">10</span><span class="sxs-lookup"><span data-stu-id="88fd7-146">10</span></span>       | <span data-ttu-id="88fd7-147">1000</span><span class="sxs-lookup"><span data-stu-id="88fd7-147">1,000</span></span>       | <span data-ttu-id="88fd7-148">1000</span><span class="sxs-lookup"><span data-stu-id="88fd7-148">1,000</span></span>                |
| <span data-ttu-id="88fd7-149">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="88fd7-149">Purchase order</span></span> | <span data-ttu-id="88fd7-150">2</span><span class="sxs-lookup"><span data-stu-id="88fd7-150">2</span></span>    | <span data-ttu-id="88fd7-151">21</span><span class="sxs-lookup"><span data-stu-id="88fd7-151">21</span></span>        | <span data-ttu-id="88fd7-152">Beszerezve</span><span class="sxs-lookup"><span data-stu-id="88fd7-152">Purchased</span></span> |       | <span data-ttu-id="88fd7-153">március 15.</span><span class="sxs-lookup"><span data-stu-id="88fd7-153">March 15</span></span>      | <span data-ttu-id="88fd7-154">március 15.</span><span class="sxs-lookup"><span data-stu-id="88fd7-154">March 15</span></span>       | <span data-ttu-id="88fd7-155">10</span><span class="sxs-lookup"><span data-stu-id="88fd7-155">10</span></span>       | <span data-ttu-id="88fd7-156">2,000</span><span class="sxs-lookup"><span data-stu-id="88fd7-156">2,000</span></span>       | <span data-ttu-id="88fd7-157">2,000</span><span class="sxs-lookup"><span data-stu-id="88fd7-157">2,000</span></span>                |
| <span data-ttu-id="88fd7-158">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="88fd7-158">Purchase order</span></span> | <span data-ttu-id="88fd7-159">1</span><span class="sxs-lookup"><span data-stu-id="88fd7-159">1</span></span>    | <span data-ttu-id="88fd7-160">11</span><span class="sxs-lookup"><span data-stu-id="88fd7-160">11</span></span>        | <span data-ttu-id="88fd7-161">Bevételezve</span><span class="sxs-lookup"><span data-stu-id="88fd7-161">Received</span></span>  |       | <span data-ttu-id="88fd7-162">április 15.</span><span class="sxs-lookup"><span data-stu-id="88fd7-162">April 15</span></span>      |                | <span data-ttu-id="88fd7-163">5</span><span class="sxs-lookup"><span data-stu-id="88fd7-163">5</span></span>        |             | <span data-ttu-id="88fd7-164">375</span><span class="sxs-lookup"><span data-stu-id="88fd7-164">375</span></span>                  |
| <span data-ttu-id="88fd7-165">Átmozgatási rendelés</span><span class="sxs-lookup"><span data-stu-id="88fd7-165">Transfer order</span></span> | <span data-ttu-id="88fd7-166">1</span><span class="sxs-lookup"><span data-stu-id="88fd7-166">1</span></span>    | <span data-ttu-id="88fd7-167">11</span><span class="sxs-lookup"><span data-stu-id="88fd7-167">11</span></span>        |           | <span data-ttu-id="88fd7-168">Eladva</span><span class="sxs-lookup"><span data-stu-id="88fd7-168">Sold</span></span>  | <span data-ttu-id="88fd7-169">május 2.</span><span class="sxs-lookup"><span data-stu-id="88fd7-169">May 2</span></span>         | <span data-ttu-id="88fd7-170">május 2.</span><span class="sxs-lookup"><span data-stu-id="88fd7-170">May 2</span></span>          | <span data-ttu-id="88fd7-171">-5</span><span class="sxs-lookup"><span data-stu-id="88fd7-171">-5</span></span>       | <span data-ttu-id="88fd7-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="88fd7-172">-458.33</span></span>     | <span data-ttu-id="88fd7-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="88fd7-173">-458.33</span></span>              |
| <span data-ttu-id="88fd7-174">Átmozgatási rendelés</span><span class="sxs-lookup"><span data-stu-id="88fd7-174">Transfer order</span></span> | <span data-ttu-id="88fd7-175">1</span><span class="sxs-lookup"><span data-stu-id="88fd7-175">1</span></span>    | <span data-ttu-id="88fd7-176">12</span><span class="sxs-lookup"><span data-stu-id="88fd7-176">12</span></span>        | <span data-ttu-id="88fd7-177">Beszerezve</span><span class="sxs-lookup"><span data-stu-id="88fd7-177">Purchased</span></span> |       | <span data-ttu-id="88fd7-178">május 2.</span><span class="sxs-lookup"><span data-stu-id="88fd7-178">May 2</span></span>         | <span data-ttu-id="88fd7-179">május 2.</span><span class="sxs-lookup"><span data-stu-id="88fd7-179">May 2</span></span>          | <span data-ttu-id="88fd7-180">5</span><span class="sxs-lookup"><span data-stu-id="88fd7-180">5</span></span>        | <span data-ttu-id="88fd7-181">458.33</span><span class="sxs-lookup"><span data-stu-id="88fd7-181">458.33</span></span>      | <span data-ttu-id="88fd7-182">458.33</span><span class="sxs-lookup"><span data-stu-id="88fd7-182">458.33</span></span>               |
| <span data-ttu-id="88fd7-183">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="88fd7-183">Sales order</span></span>    | <span data-ttu-id="88fd7-184">1</span><span class="sxs-lookup"><span data-stu-id="88fd7-184">1</span></span>    | <span data-ttu-id="88fd7-185">12</span><span class="sxs-lookup"><span data-stu-id="88fd7-185">12</span></span>        |           | <span data-ttu-id="88fd7-186">Eladva</span><span class="sxs-lookup"><span data-stu-id="88fd7-186">Sold</span></span>  | <span data-ttu-id="88fd7-187">május 3.</span><span class="sxs-lookup"><span data-stu-id="88fd7-187">May 3</span></span>         | <span data-ttu-id="88fd7-188">május 3.</span><span class="sxs-lookup"><span data-stu-id="88fd7-188">May 3</span></span>          | <span data-ttu-id="88fd7-189">-1</span><span class="sxs-lookup"><span data-stu-id="88fd7-189">-1</span></span>       | <span data-ttu-id="88fd7-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="88fd7-190">-91.67</span></span>      | <span data-ttu-id="88fd7-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="88fd7-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="88fd7-192">Hogyan történik mennyiségek és az összegek számítása az egyes időszakokban</span><span class="sxs-lookup"><span data-stu-id="88fd7-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="88fd7-193">Az előző szakaszokban ismertetett mintaadatok használatával a következő beállításokkal rendelkező **Készlet-korosítási** jelentés futtatható:</span><span class="sxs-lookup"><span data-stu-id="88fd7-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="88fd7-194">**Adott dátumtól:** *2020. május 9.*</span><span class="sxs-lookup"><span data-stu-id="88fd7-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="88fd7-195">**Hely:** *Megtekintés*</span><span class="sxs-lookup"><span data-stu-id="88fd7-195">**Site:** *View*</span></span>
- <span data-ttu-id="88fd7-196">**Raktár:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="88fd7-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="88fd7-197">**Cikkszám:** *Összes*</span><span class="sxs-lookup"><span data-stu-id="88fd7-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="88fd7-198">**Korosítási időszak:** Állítsa be ezt a mezőt havi időszakok generálásához.</span><span class="sxs-lookup"><span data-stu-id="88fd7-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="88fd7-199">Ebben az esetben a létrejövő jelentés tartalma a következő példához hasonlóan fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="88fd7-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="88fd7-200">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="88fd7-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-201">Webhely</span><span class="sxs-lookup"><span data-stu-id="88fd7-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-202">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-203">Aktuális készlet értéke</span><span class="sxs-lookup"><span data-stu-id="88fd7-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-204">Készletérték mennyisége</span><span class="sxs-lookup"><span data-stu-id="88fd7-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-205">Készletérték</span><span class="sxs-lookup"><span data-stu-id="88fd7-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-206">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="88fd7-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="88fd7-207">2020/8/5 – 2020/1/5</span><span class="sxs-lookup"><span data-stu-id="88fd7-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="88fd7-208">2020/4/30 – 2020/4/1</span><span class="sxs-lookup"><span data-stu-id="88fd7-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="88fd7-209">2020/3/31 – 2020/3/1</span><span class="sxs-lookup"><span data-stu-id="88fd7-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="88fd7-210">P1:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="88fd7-211">P1:Összeg</span><span class="sxs-lookup"><span data-stu-id="88fd7-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="88fd7-212">P2:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="88fd7-213">P2:Összeg</span><span class="sxs-lookup"><span data-stu-id="88fd7-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="88fd7-214">P3:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="88fd7-215">P3:Összeg</span><span class="sxs-lookup"><span data-stu-id="88fd7-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="88fd7-216">1000</span><span class="sxs-lookup"><span data-stu-id="88fd7-216">1000</span></span></td>
    <td><span data-ttu-id="88fd7-217">1</span><span class="sxs-lookup"><span data-stu-id="88fd7-217">1</span></span></td>
    <td><span data-ttu-id="88fd7-218">14</span><span class="sxs-lookup"><span data-stu-id="88fd7-218">14</span></span></td>
    <td><span data-ttu-id="88fd7-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="88fd7-219">1,283.33</span></span></td>
    <td><span data-ttu-id="88fd7-220">14</span><span class="sxs-lookup"><span data-stu-id="88fd7-220">14</span></span></td>
    <td><span data-ttu-id="88fd7-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="88fd7-221">1,283.33</span></span></td>
    <td><span data-ttu-id="88fd7-222">91.67</span><span class="sxs-lookup"><span data-stu-id="88fd7-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="88fd7-223">5.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-223">5.00</span></span></td>
    <td><span data-ttu-id="88fd7-224">458.33</span><span class="sxs-lookup"><span data-stu-id="88fd7-224">458.33</span></span></td>
    <td><span data-ttu-id="88fd7-225">9.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-225">9.00</span></span></td>
    <td><span data-ttu-id="88fd7-226">825.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="88fd7-227">1000</span><span class="sxs-lookup"><span data-stu-id="88fd7-227">1000</span></span></td>
    <td><span data-ttu-id="88fd7-228">2</span><span class="sxs-lookup"><span data-stu-id="88fd7-228">2</span></span></td>
    <td><span data-ttu-id="88fd7-229">10</span><span class="sxs-lookup"><span data-stu-id="88fd7-229">10</span></span></td>
    <td><span data-ttu-id="88fd7-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-230">2,000.00</span></span></td>
    <td><span data-ttu-id="88fd7-231">10</span><span class="sxs-lookup"><span data-stu-id="88fd7-231">10</span></span></td>
    <td><span data-ttu-id="88fd7-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-232">2,000.00</span></span></td>
    <td><span data-ttu-id="88fd7-233">200.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="88fd7-234">10,00</span><span class="sxs-lookup"><span data-stu-id="88fd7-234">10.00</span></span></td>
    <td><span data-ttu-id="88fd7-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="88fd7-236"><strong>1000 összegek</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="88fd7-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="88fd7-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="88fd7-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="88fd7-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="88fd7-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="88fd7-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="88fd7-243">Jegyezze fel a példajelentés következő adatait:</span><span class="sxs-lookup"><span data-stu-id="88fd7-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="88fd7-244">A jelentésen megjelenő **Készletérték mennyiség**, **Készletérték** és **Átlagos egységköltség** értékei pénzügyi készletdimenzió értékei (**Telephely** ebben az esetben).</span><span class="sxs-lookup"><span data-stu-id="88fd7-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="88fd7-245">Az 1- telephely esetében például a jelentés a következő adatokat jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="88fd7-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="88fd7-246">A **Készletérték-mennyiség** értéke *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="88fd7-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="88fd7-247">A **Készletértékérték** értéke *1283,33* (= 1000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="88fd7-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="88fd7-248">Az **Átlagos egységenkénti költség** *91,67*.</span><span class="sxs-lookup"><span data-stu-id="88fd7-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="88fd7-249">Az **Aktuális készlet** értékének és a **Mennyiség** értékét az egyes időszakokban a rendszer az **Átlagos egységenkénti** érték alapján számítja ki a program.</span><span class="sxs-lookup"><span data-stu-id="88fd7-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="88fd7-250">A jelentés határozza meg az egyes időszakok készleten lévő mennyiségét az egyes időszakok összes bevételezett készletmennyiségének összesítésével.</span><span class="sxs-lookup"><span data-stu-id="88fd7-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="88fd7-251">Ezt követően az először be, először ki (FIFO) elv alapján vonja le a teljes kiadott mennyiséget, függetlenül attól, hogy milyen készletmodell van használatban a cikkekhez.</span><span class="sxs-lookup"><span data-stu-id="88fd7-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="88fd7-252">Ha ismét ugyanazt a jelentést futtatja, de ezúttal a **Telephely** és **Raktár** mezőt is *Megtekintés* értékre állítja, akkor az új jelentés a következő példához hasonló lesz.</span><span class="sxs-lookup"><span data-stu-id="88fd7-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="88fd7-253">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="88fd7-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-254">Webhely</span><span class="sxs-lookup"><span data-stu-id="88fd7-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-255">Raktár</span><span class="sxs-lookup"><span data-stu-id="88fd7-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-256">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-257">Aktuális készlet értéke</span><span class="sxs-lookup"><span data-stu-id="88fd7-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-258">Készletérték mennyisége</span><span class="sxs-lookup"><span data-stu-id="88fd7-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-259">Készletérték</span><span class="sxs-lookup"><span data-stu-id="88fd7-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-260">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="88fd7-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="88fd7-261">2020/8/5 – 2020/1/5</span><span class="sxs-lookup"><span data-stu-id="88fd7-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="88fd7-262">2020/4/30 – 2020/4/1</span><span class="sxs-lookup"><span data-stu-id="88fd7-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="88fd7-263">2020/3/31 – 2020/3/1</span><span class="sxs-lookup"><span data-stu-id="88fd7-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="88fd7-264">P1:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="88fd7-265">P1:Összeg</span><span class="sxs-lookup"><span data-stu-id="88fd7-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="88fd7-266">P2:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="88fd7-267">P2:Összeg</span><span class="sxs-lookup"><span data-stu-id="88fd7-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="88fd7-268">P3:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="88fd7-269">P3:Összeg</span><span class="sxs-lookup"><span data-stu-id="88fd7-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="88fd7-270">1000</span><span class="sxs-lookup"><span data-stu-id="88fd7-270">1000</span></span></td>
    <td><span data-ttu-id="88fd7-271">1</span><span class="sxs-lookup"><span data-stu-id="88fd7-271">1</span></span></td>
    <td><span data-ttu-id="88fd7-272">11</span><span class="sxs-lookup"><span data-stu-id="88fd7-272">11</span></span></td>
    <td><span data-ttu-id="88fd7-273">10</span><span class="sxs-lookup"><span data-stu-id="88fd7-273">10</span></span></td>
    <td><span data-ttu-id="88fd7-274">916.67</span><span class="sxs-lookup"><span data-stu-id="88fd7-274">916.67</span></span></td>
    <td><span data-ttu-id="88fd7-275">14</span><span class="sxs-lookup"><span data-stu-id="88fd7-275">14</span></span></td>
    <td><span data-ttu-id="88fd7-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="88fd7-276">1,283.33</span></span></td>
    <td><span data-ttu-id="88fd7-277">91.67</span><span class="sxs-lookup"><span data-stu-id="88fd7-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="88fd7-278">5.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-278">5.00</span></span></td>
    <td><span data-ttu-id="88fd7-279">458.33</span><span class="sxs-lookup"><span data-stu-id="88fd7-279">458.33</span></span></td>
    <td><span data-ttu-id="88fd7-280">5.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-280">5.00</span></span></td>
    <td><span data-ttu-id="88fd7-281">458.33</span><span class="sxs-lookup"><span data-stu-id="88fd7-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="88fd7-282">1000</span><span class="sxs-lookup"><span data-stu-id="88fd7-282">1000</span></span></td>
    <td><span data-ttu-id="88fd7-283">1</span><span class="sxs-lookup"><span data-stu-id="88fd7-283">1</span></span></td>
    <td><span data-ttu-id="88fd7-284">12</span><span class="sxs-lookup"><span data-stu-id="88fd7-284">12</span></span></td>
    <td><span data-ttu-id="88fd7-285">4</span><span class="sxs-lookup"><span data-stu-id="88fd7-285">4</span></span></td>
    <td><span data-ttu-id="88fd7-286">366.67</span><span class="sxs-lookup"><span data-stu-id="88fd7-286">366.67</span></span></td>
    <td><span data-ttu-id="88fd7-287">14</span><span class="sxs-lookup"><span data-stu-id="88fd7-287">14</span></span></td>
    <td><span data-ttu-id="88fd7-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="88fd7-288">1,283.33</span></span></td>
    <td><span data-ttu-id="88fd7-289">91.67</span><span class="sxs-lookup"><span data-stu-id="88fd7-289">91.67</span></span></td>
    <td><span data-ttu-id="88fd7-290">4.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-290">4.00</span></span></td>
    <td><span data-ttu-id="88fd7-291">366.67</span><span class="sxs-lookup"><span data-stu-id="88fd7-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="88fd7-292">1000</span><span class="sxs-lookup"><span data-stu-id="88fd7-292">1000</span></span></td>
    <td><span data-ttu-id="88fd7-293">2</span><span class="sxs-lookup"><span data-stu-id="88fd7-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="88fd7-294">10</span><span class="sxs-lookup"><span data-stu-id="88fd7-294">10</span></span></td>
    <td><span data-ttu-id="88fd7-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-295">2,000.00</span></span></td>
    <td><span data-ttu-id="88fd7-296">10</span><span class="sxs-lookup"><span data-stu-id="88fd7-296">10</span></span></td>
    <td><span data-ttu-id="88fd7-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-297">2,000.00</span></span></td>
    <td><span data-ttu-id="88fd7-298">200.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="88fd7-299">10,00</span><span class="sxs-lookup"><span data-stu-id="88fd7-299">10.00</span></span></td>
    <td><span data-ttu-id="88fd7-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="88fd7-301"><strong>1000 összegek</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="88fd7-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="88fd7-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="88fd7-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="88fd7-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="88fd7-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="88fd7-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="88fd7-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="88fd7-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="88fd7-310">Ez alkalommal az 1. telephely két sorra van osztva, egy a 11-es raktárhoz, egy a 12-es raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="88fd7-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="88fd7-311">Ugyanakkor a **Készletérték mennyiség**, **Készletérték** és **Átlagos egységköltség** értékei nem változnak, mert a **Raktár** nem egy készletdimenzió.</span><span class="sxs-lookup"><span data-stu-id="88fd7-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="88fd7-312">Ezenkívül figyelje meg, hogy az 1. telephely mennyiségi felosztása eltérő.</span><span class="sxs-lookup"><span data-stu-id="88fd7-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="88fd7-313">A rendszer az elsőként futtatott jelentésben figyelmen kívül hagyta az ugyanazon a telephelyen belül bekövetkezett átmozgatási rendelést, és levonta az értékesítési számla mennyiségét az 1. telephely **2020/3/31 – 2020/3/1** időszakából.</span><span class="sxs-lookup"><span data-stu-id="88fd7-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="88fd7-314">Az új jelentésben azonban a rendszer levonja az értékesítési számla mennyiségét a **2020/5/8 – 2020/5/1** időszakra a 12. raktárban.</span><span class="sxs-lookup"><span data-stu-id="88fd7-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="88fd7-315">Készletzárás hatásai</span><span class="sxs-lookup"><span data-stu-id="88fd7-315">Effects of inventory closing</span></span>

<span data-ttu-id="88fd7-316">Ha májusra futtatja a készletzárást futtatja, majd újra futtatja az előző jelentést, de az **Adott dátumtól** mező értéke *2020 május 31*, a következő eredményeket kapja:</span><span class="sxs-lookup"><span data-stu-id="88fd7-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="88fd7-317">A program frissíti a **Készletérték** és az **Átlagos egységköltség** értékét.</span><span class="sxs-lookup"><span data-stu-id="88fd7-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="88fd7-318">A program ennek megfelelően frissíti az **Aktuális készletérték** és az **Összeg** értéket az összes időszakra.</span><span class="sxs-lookup"><span data-stu-id="88fd7-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="88fd7-319">Az új jelentés az alábbi példához hasonlóan jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="88fd7-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="88fd7-320">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="88fd7-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-321">Webhely</span><span class="sxs-lookup"><span data-stu-id="88fd7-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-322">Raktár</span><span class="sxs-lookup"><span data-stu-id="88fd7-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-323">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-324">Aktuális készlet értéke</span><span class="sxs-lookup"><span data-stu-id="88fd7-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-325">Készletérték mennyisége</span><span class="sxs-lookup"><span data-stu-id="88fd7-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-326">Készletérték</span><span class="sxs-lookup"><span data-stu-id="88fd7-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="88fd7-327">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="88fd7-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="88fd7-328">2020/5/31 – 2020/5/1</span><span class="sxs-lookup"><span data-stu-id="88fd7-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="88fd7-329">2020/4/30 – 2020/4/1</span><span class="sxs-lookup"><span data-stu-id="88fd7-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="88fd7-330">2020/3/31 – 2020/3/1</span><span class="sxs-lookup"><span data-stu-id="88fd7-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="88fd7-331">P1:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="88fd7-332">P1:Összeg</span><span class="sxs-lookup"><span data-stu-id="88fd7-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="88fd7-333">P2:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="88fd7-334">P2:Összeg</span><span class="sxs-lookup"><span data-stu-id="88fd7-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="88fd7-335">P3:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="88fd7-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="88fd7-336">P3:Összeg</span><span class="sxs-lookup"><span data-stu-id="88fd7-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="88fd7-337">1000</span><span class="sxs-lookup"><span data-stu-id="88fd7-337">1000</span></span></td>
    <td><span data-ttu-id="88fd7-338">1</span><span class="sxs-lookup"><span data-stu-id="88fd7-338">1</span></span></td>
    <td><span data-ttu-id="88fd7-339">11</span><span class="sxs-lookup"><span data-stu-id="88fd7-339">11</span></span></td>
    <td><span data-ttu-id="88fd7-340">10</span><span class="sxs-lookup"><span data-stu-id="88fd7-340">10</span></span></td>
    <td><span data-ttu-id="88fd7-341">910.70</span><span class="sxs-lookup"><span data-stu-id="88fd7-341">910.70</span></span></td>
    <td><span data-ttu-id="88fd7-342">14</span><span class="sxs-lookup"><span data-stu-id="88fd7-342">14</span></span></td>
    <td><span data-ttu-id="88fd7-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-343">1,275.00</span></span></td>
    <td><span data-ttu-id="88fd7-344">91.07</span><span class="sxs-lookup"><span data-stu-id="88fd7-344">91.07</span></span></td>
    <td><span data-ttu-id="88fd7-345">0,00</span><span class="sxs-lookup"><span data-stu-id="88fd7-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="88fd7-346">5.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-346">5.00</span></span></td>
    <td><span data-ttu-id="88fd7-347">455.36</span><span class="sxs-lookup"><span data-stu-id="88fd7-347">455.36</span></span></td>
    <td><span data-ttu-id="88fd7-348">5.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-348">5.00</span></span></td>
    <td><span data-ttu-id="88fd7-349">455.36</span><span class="sxs-lookup"><span data-stu-id="88fd7-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="88fd7-350">1000</span><span class="sxs-lookup"><span data-stu-id="88fd7-350">1000</span></span></td>
    <td><span data-ttu-id="88fd7-351">1</span><span class="sxs-lookup"><span data-stu-id="88fd7-351">1</span></span></td>
    <td><span data-ttu-id="88fd7-352">12</span><span class="sxs-lookup"><span data-stu-id="88fd7-352">12</span></span></td>
    <td><span data-ttu-id="88fd7-353">4</span><span class="sxs-lookup"><span data-stu-id="88fd7-353">4</span></span></td>
    <td><span data-ttu-id="88fd7-354">364.29</span><span class="sxs-lookup"><span data-stu-id="88fd7-354">364.29</span></span></td>
    <td><span data-ttu-id="88fd7-355">14</span><span class="sxs-lookup"><span data-stu-id="88fd7-355">14</span></span></td>
    <td><span data-ttu-id="88fd7-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-356">1,275.00</span></span></td>
    <td><span data-ttu-id="88fd7-357">91.07</span><span class="sxs-lookup"><span data-stu-id="88fd7-357">91.07</span></span></td>
    <td><span data-ttu-id="88fd7-358">4.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-358">4.00</span></span></td>
    <td><span data-ttu-id="88fd7-359">364.29</span><span class="sxs-lookup"><span data-stu-id="88fd7-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="88fd7-360">1000</span><span class="sxs-lookup"><span data-stu-id="88fd7-360">1000</span></span></td>
    <td><span data-ttu-id="88fd7-361">2</span><span class="sxs-lookup"><span data-stu-id="88fd7-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="88fd7-362">10</span><span class="sxs-lookup"><span data-stu-id="88fd7-362">10</span></span></td>
    <td><span data-ttu-id="88fd7-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-363">2,000.00</span></span></td>
    <td><span data-ttu-id="88fd7-364">10</span><span class="sxs-lookup"><span data-stu-id="88fd7-364">10</span></span></td>
    <td><span data-ttu-id="88fd7-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-365">2,000.00</span></span></td>
    <td><span data-ttu-id="88fd7-366">200.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="88fd7-367">10,00</span><span class="sxs-lookup"><span data-stu-id="88fd7-367">10.00</span></span></td>
    <td><span data-ttu-id="88fd7-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="88fd7-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="88fd7-369"><strong>1000 összegek</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="88fd7-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="88fd7-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="88fd7-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="88fd7-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="88fd7-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="88fd7-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="88fd7-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="88fd7-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="88fd7-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
