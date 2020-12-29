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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429499"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="ad80d-103">Készletkorosítási jelentés – példák és logika</span><span class="sxs-lookup"><span data-stu-id="ad80d-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad80d-104">Ez a témakör néhány példát mutat be, amelyek a **Készletkorosítási** jelentés eredményeinek értelmezését mutatják be.</span><span class="sxs-lookup"><span data-stu-id="ad80d-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="ad80d-105">Ez a jelentés egy kiválasztott cikk vagy cikkcsoport aktuális mennyiségét és készletérték-adatait több időszakra bontja szét.</span><span class="sxs-lookup"><span data-stu-id="ad80d-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="ad80d-106">Ez a témakör a jelentés belső logikáját is bemutatja.</span><span class="sxs-lookup"><span data-stu-id="ad80d-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="ad80d-107">Az ebben a témakörben szereplő példák a standard **Készlet-korosítási** jelentés eredményeinek megjelenítését mutatják be.</span><span class="sxs-lookup"><span data-stu-id="ad80d-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="ad80d-108">Általánosságban azonban azt ajánljuk, hogy a jelentés [Készletkorosítási jelentés tárhely](inventory-aging-report-storage.md) változatát használja, különösen, ha sok cikket és raktárat kell feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="ad80d-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="ad80d-109">A készlet-korosítási jelentés tárolója menti a létrehozott jelentéseket, az eredményeket interaktív lapként és diagramként jeleníti meg, valamint minden elmentett jelentés exportálását is lehetővé teszi.</span><span class="sxs-lookup"><span data-stu-id="ad80d-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="ad80d-110">A példákban használt mintaadatok</span><span class="sxs-lookup"><span data-stu-id="ad80d-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="ad80d-111">Az ebben a témakörben szereplő példák az ebben a szakaszban ismertetett minta tranzakciós adatokon alapulnak.</span><span class="sxs-lookup"><span data-stu-id="ad80d-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="ad80d-112">Tárolásidimenzió beállítása</span><span class="sxs-lookup"><span data-stu-id="ad80d-112">Storage dimension setup</span></span>

<span data-ttu-id="ad80d-113">A példarendszer a tárolási dimenziók következő beállítását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="ad80d-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="ad80d-114">Név</span><span class="sxs-lookup"><span data-stu-id="ad80d-114">Name</span></span>      | <span data-ttu-id="ad80d-115">Aktív</span><span class="sxs-lookup"><span data-stu-id="ad80d-115">Active</span></span> | <span data-ttu-id="ad80d-116">Tényleges készlet</span><span class="sxs-lookup"><span data-stu-id="ad80d-116">Physical inventory</span></span> | <span data-ttu-id="ad80d-117">Pénzügyi készlet</span><span class="sxs-lookup"><span data-stu-id="ad80d-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="ad80d-118">Webhely</span><span class="sxs-lookup"><span data-stu-id="ad80d-118">Site</span></span>      | <span data-ttu-id="ad80d-119">Igen</span><span class="sxs-lookup"><span data-stu-id="ad80d-119">Yes</span></span>    | <span data-ttu-id="ad80d-120">Igen</span><span class="sxs-lookup"><span data-stu-id="ad80d-120">Yes</span></span>                | <span data-ttu-id="ad80d-121">Igen</span><span class="sxs-lookup"><span data-stu-id="ad80d-121">Yes</span></span>                 |
| <span data-ttu-id="ad80d-122">Raktár</span><span class="sxs-lookup"><span data-stu-id="ad80d-122">Warehouse</span></span> | <span data-ttu-id="ad80d-123">Igen</span><span class="sxs-lookup"><span data-stu-id="ad80d-123">Yes</span></span>    | <span data-ttu-id="ad80d-124">Igen</span><span class="sxs-lookup"><span data-stu-id="ad80d-124">Yes</span></span>                | <span data-ttu-id="ad80d-125">Nincs</span><span class="sxs-lookup"><span data-stu-id="ad80d-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="ad80d-126">Készletmodell</span><span class="sxs-lookup"><span data-stu-id="ad80d-126">Inventory model</span></span>

<span data-ttu-id="ad80d-127">A példarendszer esetében a kiadott termékhez tartozó készletmodell *FIFO*, és a készletmodell-beállítás **Költségár** beállítása *Tartalmazza a fizikai értéket*.</span><span class="sxs-lookup"><span data-stu-id="ad80d-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="ad80d-128">Készlettranzakciók</span><span class="sxs-lookup"><span data-stu-id="ad80d-128">Inventory transactions</span></span>

<span data-ttu-id="ad80d-129">A példarendszer a következő készlettranzakciókat tartalmazz a kiadott termékhez, amelynek cikkszáma *1000*.</span><span class="sxs-lookup"><span data-stu-id="ad80d-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="ad80d-130">Hivatkozás</span><span class="sxs-lookup"><span data-stu-id="ad80d-130">Reference</span></span>      | <span data-ttu-id="ad80d-131">Webhely</span><span class="sxs-lookup"><span data-stu-id="ad80d-131">Site</span></span> | <span data-ttu-id="ad80d-132">Raktár</span><span class="sxs-lookup"><span data-stu-id="ad80d-132">Warehouse</span></span> | <span data-ttu-id="ad80d-133">Fogadás</span><span class="sxs-lookup"><span data-stu-id="ad80d-133">Receipt</span></span>   | <span data-ttu-id="ad80d-134">Kiadás</span><span class="sxs-lookup"><span data-stu-id="ad80d-134">Issue</span></span> | <span data-ttu-id="ad80d-135">Tényleges dátum</span><span class="sxs-lookup"><span data-stu-id="ad80d-135">Physical date</span></span> | <span data-ttu-id="ad80d-136">Pénzügyi dátum</span><span class="sxs-lookup"><span data-stu-id="ad80d-136">Financial date</span></span> | <span data-ttu-id="ad80d-137">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-137">Quantity</span></span> | <span data-ttu-id="ad80d-138">Költség összege</span><span class="sxs-lookup"><span data-stu-id="ad80d-138">Cost amount</span></span> | <span data-ttu-id="ad80d-139">Tényleges önköltségi érték</span><span class="sxs-lookup"><span data-stu-id="ad80d-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="ad80d-140">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="ad80d-140">Purchase order</span></span> | <span data-ttu-id="ad80d-141">1</span><span class="sxs-lookup"><span data-stu-id="ad80d-141">1</span></span>    | <span data-ttu-id="ad80d-142">11</span><span class="sxs-lookup"><span data-stu-id="ad80d-142">11</span></span>        | <span data-ttu-id="ad80d-143">Beszerezve</span><span class="sxs-lookup"><span data-stu-id="ad80d-143">Purchased</span></span> |       | <span data-ttu-id="ad80d-144">március 15.</span><span class="sxs-lookup"><span data-stu-id="ad80d-144">March 15</span></span>      | <span data-ttu-id="ad80d-145">március 15.</span><span class="sxs-lookup"><span data-stu-id="ad80d-145">March 15</span></span>       | <span data-ttu-id="ad80d-146">10</span><span class="sxs-lookup"><span data-stu-id="ad80d-146">10</span></span>       | <span data-ttu-id="ad80d-147">1000</span><span class="sxs-lookup"><span data-stu-id="ad80d-147">1,000</span></span>       | <span data-ttu-id="ad80d-148">1000</span><span class="sxs-lookup"><span data-stu-id="ad80d-148">1,000</span></span>                |
| <span data-ttu-id="ad80d-149">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="ad80d-149">Purchase order</span></span> | <span data-ttu-id="ad80d-150">2</span><span class="sxs-lookup"><span data-stu-id="ad80d-150">2</span></span>    | <span data-ttu-id="ad80d-151">21</span><span class="sxs-lookup"><span data-stu-id="ad80d-151">21</span></span>        | <span data-ttu-id="ad80d-152">Beszerezve</span><span class="sxs-lookup"><span data-stu-id="ad80d-152">Purchased</span></span> |       | <span data-ttu-id="ad80d-153">március 15.</span><span class="sxs-lookup"><span data-stu-id="ad80d-153">March 15</span></span>      | <span data-ttu-id="ad80d-154">március 15.</span><span class="sxs-lookup"><span data-stu-id="ad80d-154">March 15</span></span>       | <span data-ttu-id="ad80d-155">10</span><span class="sxs-lookup"><span data-stu-id="ad80d-155">10</span></span>       | <span data-ttu-id="ad80d-156">2,000</span><span class="sxs-lookup"><span data-stu-id="ad80d-156">2,000</span></span>       | <span data-ttu-id="ad80d-157">2,000</span><span class="sxs-lookup"><span data-stu-id="ad80d-157">2,000</span></span>                |
| <span data-ttu-id="ad80d-158">Beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="ad80d-158">Purchase order</span></span> | <span data-ttu-id="ad80d-159">1</span><span class="sxs-lookup"><span data-stu-id="ad80d-159">1</span></span>    | <span data-ttu-id="ad80d-160">11</span><span class="sxs-lookup"><span data-stu-id="ad80d-160">11</span></span>        | <span data-ttu-id="ad80d-161">Bevételezve</span><span class="sxs-lookup"><span data-stu-id="ad80d-161">Received</span></span>  |       | <span data-ttu-id="ad80d-162">április 15.</span><span class="sxs-lookup"><span data-stu-id="ad80d-162">April 15</span></span>      |                | <span data-ttu-id="ad80d-163">5</span><span class="sxs-lookup"><span data-stu-id="ad80d-163">5</span></span>        |             | <span data-ttu-id="ad80d-164">375</span><span class="sxs-lookup"><span data-stu-id="ad80d-164">375</span></span>                  |
| <span data-ttu-id="ad80d-165">Átmozgatási rendelés</span><span class="sxs-lookup"><span data-stu-id="ad80d-165">Transfer order</span></span> | <span data-ttu-id="ad80d-166">1</span><span class="sxs-lookup"><span data-stu-id="ad80d-166">1</span></span>    | <span data-ttu-id="ad80d-167">11</span><span class="sxs-lookup"><span data-stu-id="ad80d-167">11</span></span>        |           | <span data-ttu-id="ad80d-168">Eladva</span><span class="sxs-lookup"><span data-stu-id="ad80d-168">Sold</span></span>  | <span data-ttu-id="ad80d-169">május 2.</span><span class="sxs-lookup"><span data-stu-id="ad80d-169">May 2</span></span>         | <span data-ttu-id="ad80d-170">május 2.</span><span class="sxs-lookup"><span data-stu-id="ad80d-170">May 2</span></span>          | <span data-ttu-id="ad80d-171">-5</span><span class="sxs-lookup"><span data-stu-id="ad80d-171">-5</span></span>       | <span data-ttu-id="ad80d-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="ad80d-172">-458.33</span></span>     | <span data-ttu-id="ad80d-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="ad80d-173">-458.33</span></span>              |
| <span data-ttu-id="ad80d-174">Átmozgatási rendelés</span><span class="sxs-lookup"><span data-stu-id="ad80d-174">Transfer order</span></span> | <span data-ttu-id="ad80d-175">1</span><span class="sxs-lookup"><span data-stu-id="ad80d-175">1</span></span>    | <span data-ttu-id="ad80d-176">12</span><span class="sxs-lookup"><span data-stu-id="ad80d-176">12</span></span>        | <span data-ttu-id="ad80d-177">Beszerezve</span><span class="sxs-lookup"><span data-stu-id="ad80d-177">Purchased</span></span> |       | <span data-ttu-id="ad80d-178">május 2.</span><span class="sxs-lookup"><span data-stu-id="ad80d-178">May 2</span></span>         | <span data-ttu-id="ad80d-179">május 2.</span><span class="sxs-lookup"><span data-stu-id="ad80d-179">May 2</span></span>          | <span data-ttu-id="ad80d-180">5</span><span class="sxs-lookup"><span data-stu-id="ad80d-180">5</span></span>        | <span data-ttu-id="ad80d-181">458.33</span><span class="sxs-lookup"><span data-stu-id="ad80d-181">458.33</span></span>      | <span data-ttu-id="ad80d-182">458.33</span><span class="sxs-lookup"><span data-stu-id="ad80d-182">458.33</span></span>               |
| <span data-ttu-id="ad80d-183">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="ad80d-183">Sales order</span></span>    | <span data-ttu-id="ad80d-184">1</span><span class="sxs-lookup"><span data-stu-id="ad80d-184">1</span></span>    | <span data-ttu-id="ad80d-185">12</span><span class="sxs-lookup"><span data-stu-id="ad80d-185">12</span></span>        |           | <span data-ttu-id="ad80d-186">Eladva</span><span class="sxs-lookup"><span data-stu-id="ad80d-186">Sold</span></span>  | <span data-ttu-id="ad80d-187">május 3.</span><span class="sxs-lookup"><span data-stu-id="ad80d-187">May 3</span></span>         | <span data-ttu-id="ad80d-188">május 3.</span><span class="sxs-lookup"><span data-stu-id="ad80d-188">May 3</span></span>          | <span data-ttu-id="ad80d-189">-1</span><span class="sxs-lookup"><span data-stu-id="ad80d-189">-1</span></span>       | <span data-ttu-id="ad80d-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="ad80d-190">-91.67</span></span>      | <span data-ttu-id="ad80d-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="ad80d-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="ad80d-192">Hogyan történik mennyiségek és az összegek számítása az egyes időszakokban</span><span class="sxs-lookup"><span data-stu-id="ad80d-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="ad80d-193">Az előző szakaszokban ismertetett mintaadatok használatával a következő beállításokkal rendelkező **Készlet-korosítási** jelentés futtatható:</span><span class="sxs-lookup"><span data-stu-id="ad80d-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="ad80d-194">**Adott dátumtól:** *2020. május 9.*</span><span class="sxs-lookup"><span data-stu-id="ad80d-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="ad80d-195">**Hely:** *Megtekintés*</span><span class="sxs-lookup"><span data-stu-id="ad80d-195">**Site:** *View*</span></span>
- <span data-ttu-id="ad80d-196">**Raktár:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="ad80d-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="ad80d-197">**Cikkszám:** *Összes*</span><span class="sxs-lookup"><span data-stu-id="ad80d-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="ad80d-198">**Korosítási időszak:** Állítsa be ezt a mezőt havi időszakok generálásához.</span><span class="sxs-lookup"><span data-stu-id="ad80d-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="ad80d-199">Ebben az esetben a létrejövő jelentés tartalma a következő példához hasonlóan fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="ad80d-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="ad80d-200">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="ad80d-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-201">Webhely</span><span class="sxs-lookup"><span data-stu-id="ad80d-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-202">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-203">Aktuális készlet értéke</span><span class="sxs-lookup"><span data-stu-id="ad80d-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-204">Készletérték mennyisége</span><span class="sxs-lookup"><span data-stu-id="ad80d-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-205">Készletérték</span><span class="sxs-lookup"><span data-stu-id="ad80d-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-206">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="ad80d-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="ad80d-207">2020/8/5 – 2020/1/5</span><span class="sxs-lookup"><span data-stu-id="ad80d-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="ad80d-208">2020/4/30 – 2020/4/1</span><span class="sxs-lookup"><span data-stu-id="ad80d-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="ad80d-209">2020/3/31 – 2020/3/1</span><span class="sxs-lookup"><span data-stu-id="ad80d-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="ad80d-210">P1:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="ad80d-211">P1:Összeg</span><span class="sxs-lookup"><span data-stu-id="ad80d-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="ad80d-212">P2:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="ad80d-213">P2:Összeg</span><span class="sxs-lookup"><span data-stu-id="ad80d-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="ad80d-214">P3:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="ad80d-215">P3:Összeg</span><span class="sxs-lookup"><span data-stu-id="ad80d-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="ad80d-216">1000</span><span class="sxs-lookup"><span data-stu-id="ad80d-216">1000</span></span></td>
    <td><span data-ttu-id="ad80d-217">1</span><span class="sxs-lookup"><span data-stu-id="ad80d-217">1</span></span></td>
    <td><span data-ttu-id="ad80d-218">14</span><span class="sxs-lookup"><span data-stu-id="ad80d-218">14</span></span></td>
    <td><span data-ttu-id="ad80d-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="ad80d-219">1,283.33</span></span></td>
    <td><span data-ttu-id="ad80d-220">14</span><span class="sxs-lookup"><span data-stu-id="ad80d-220">14</span></span></td>
    <td><span data-ttu-id="ad80d-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="ad80d-221">1,283.33</span></span></td>
    <td><span data-ttu-id="ad80d-222">91.67</span><span class="sxs-lookup"><span data-stu-id="ad80d-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="ad80d-223">5.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-223">5.00</span></span></td>
    <td><span data-ttu-id="ad80d-224">458.33</span><span class="sxs-lookup"><span data-stu-id="ad80d-224">458.33</span></span></td>
    <td><span data-ttu-id="ad80d-225">9.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-225">9.00</span></span></td>
    <td><span data-ttu-id="ad80d-226">825.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="ad80d-227">1000</span><span class="sxs-lookup"><span data-stu-id="ad80d-227">1000</span></span></td>
    <td><span data-ttu-id="ad80d-228">2</span><span class="sxs-lookup"><span data-stu-id="ad80d-228">2</span></span></td>
    <td><span data-ttu-id="ad80d-229">10</span><span class="sxs-lookup"><span data-stu-id="ad80d-229">10</span></span></td>
    <td><span data-ttu-id="ad80d-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-230">2,000.00</span></span></td>
    <td><span data-ttu-id="ad80d-231">10</span><span class="sxs-lookup"><span data-stu-id="ad80d-231">10</span></span></td>
    <td><span data-ttu-id="ad80d-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-232">2,000.00</span></span></td>
    <td><span data-ttu-id="ad80d-233">200.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="ad80d-234">10,00</span><span class="sxs-lookup"><span data-stu-id="ad80d-234">10.00</span></span></td>
    <td><span data-ttu-id="ad80d-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="ad80d-236"><strong>1000 összegek</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="ad80d-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="ad80d-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="ad80d-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="ad80d-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="ad80d-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="ad80d-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="ad80d-243">Jegyezze fel a példajelentés következő adatait:</span><span class="sxs-lookup"><span data-stu-id="ad80d-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="ad80d-244">A jelentésen megjelenő **Készletérték mennyiség**, **Készletérték** és **Átlagos egységköltség** értékei pénzügyi készletdimenzió értékei (**Telephely** ebben az esetben).</span><span class="sxs-lookup"><span data-stu-id="ad80d-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="ad80d-245">Az 1- telephely esetében például a jelentés a következő adatokat jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="ad80d-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="ad80d-246">A **Készletérték-mennyiség** értéke *14* (= 10 + 5 – 5 + 5 – 1).</span><span class="sxs-lookup"><span data-stu-id="ad80d-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="ad80d-247">A **Készletértékérték** értéke *1283,33* (= 1000 + 375 – 458,33 + 458,33 – 91,67).</span><span class="sxs-lookup"><span data-stu-id="ad80d-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="ad80d-248">Az **Átlagos egységenkénti költség** *91,67*.</span><span class="sxs-lookup"><span data-stu-id="ad80d-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="ad80d-249">Az **Aktuális készlet** értékének és a **Mennyiség** értékét az egyes időszakokban a rendszer az **Átlagos egységenkénti** érték alapján számítja ki a program.</span><span class="sxs-lookup"><span data-stu-id="ad80d-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="ad80d-250">A jelentés határozza meg az egyes időszakok készleten lévő mennyiségét az egyes időszakok összes bevételezett készletmennyiségének összesítésével.</span><span class="sxs-lookup"><span data-stu-id="ad80d-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="ad80d-251">Ezt követően az először be, először ki (FIFO) elv alapján vonja le a teljes kiadott mennyiséget, függetlenül attól, hogy milyen készletmodell van használatban a cikkekhez.</span><span class="sxs-lookup"><span data-stu-id="ad80d-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="ad80d-252">Ha ismét ugyanazt a jelentést futtatja, de ezúttal a **Telephely** és **Raktár** mezőt is *Megtekintés* értékre állítja, akkor az új jelentés a következő példához hasonló lesz.</span><span class="sxs-lookup"><span data-stu-id="ad80d-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="ad80d-253">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="ad80d-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-254">Webhely</span><span class="sxs-lookup"><span data-stu-id="ad80d-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-255">Raktár</span><span class="sxs-lookup"><span data-stu-id="ad80d-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-256">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-257">Aktuális készlet értéke</span><span class="sxs-lookup"><span data-stu-id="ad80d-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-258">Készletérték mennyisége</span><span class="sxs-lookup"><span data-stu-id="ad80d-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-259">Készletérték</span><span class="sxs-lookup"><span data-stu-id="ad80d-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-260">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="ad80d-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="ad80d-261">2020/8/5 – 2020/1/5</span><span class="sxs-lookup"><span data-stu-id="ad80d-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="ad80d-262">2020/4/30 – 2020/4/1</span><span class="sxs-lookup"><span data-stu-id="ad80d-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="ad80d-263">2020/3/31 – 2020/3/1</span><span class="sxs-lookup"><span data-stu-id="ad80d-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="ad80d-264">P1:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="ad80d-265">P1:Összeg</span><span class="sxs-lookup"><span data-stu-id="ad80d-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="ad80d-266">P2:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="ad80d-267">P2:Összeg</span><span class="sxs-lookup"><span data-stu-id="ad80d-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="ad80d-268">P3:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="ad80d-269">P3:Összeg</span><span class="sxs-lookup"><span data-stu-id="ad80d-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="ad80d-270">1000</span><span class="sxs-lookup"><span data-stu-id="ad80d-270">1000</span></span></td>
    <td><span data-ttu-id="ad80d-271">1</span><span class="sxs-lookup"><span data-stu-id="ad80d-271">1</span></span></td>
    <td><span data-ttu-id="ad80d-272">11</span><span class="sxs-lookup"><span data-stu-id="ad80d-272">11</span></span></td>
    <td><span data-ttu-id="ad80d-273">10</span><span class="sxs-lookup"><span data-stu-id="ad80d-273">10</span></span></td>
    <td><span data-ttu-id="ad80d-274">916.67</span><span class="sxs-lookup"><span data-stu-id="ad80d-274">916.67</span></span></td>
    <td><span data-ttu-id="ad80d-275">14</span><span class="sxs-lookup"><span data-stu-id="ad80d-275">14</span></span></td>
    <td><span data-ttu-id="ad80d-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="ad80d-276">1,283.33</span></span></td>
    <td><span data-ttu-id="ad80d-277">91.67</span><span class="sxs-lookup"><span data-stu-id="ad80d-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="ad80d-278">5.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-278">5.00</span></span></td>
    <td><span data-ttu-id="ad80d-279">458.33</span><span class="sxs-lookup"><span data-stu-id="ad80d-279">458.33</span></span></td>
    <td><span data-ttu-id="ad80d-280">5.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-280">5.00</span></span></td>
    <td><span data-ttu-id="ad80d-281">458.33</span><span class="sxs-lookup"><span data-stu-id="ad80d-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="ad80d-282">1000</span><span class="sxs-lookup"><span data-stu-id="ad80d-282">1000</span></span></td>
    <td><span data-ttu-id="ad80d-283">1</span><span class="sxs-lookup"><span data-stu-id="ad80d-283">1</span></span></td>
    <td><span data-ttu-id="ad80d-284">12</span><span class="sxs-lookup"><span data-stu-id="ad80d-284">12</span></span></td>
    <td><span data-ttu-id="ad80d-285">4</span><span class="sxs-lookup"><span data-stu-id="ad80d-285">4</span></span></td>
    <td><span data-ttu-id="ad80d-286">366.67</span><span class="sxs-lookup"><span data-stu-id="ad80d-286">366.67</span></span></td>
    <td><span data-ttu-id="ad80d-287">14</span><span class="sxs-lookup"><span data-stu-id="ad80d-287">14</span></span></td>
    <td><span data-ttu-id="ad80d-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="ad80d-288">1,283.33</span></span></td>
    <td><span data-ttu-id="ad80d-289">91.67</span><span class="sxs-lookup"><span data-stu-id="ad80d-289">91.67</span></span></td>
    <td><span data-ttu-id="ad80d-290">4.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-290">4.00</span></span></td>
    <td><span data-ttu-id="ad80d-291">366.67</span><span class="sxs-lookup"><span data-stu-id="ad80d-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="ad80d-292">1000</span><span class="sxs-lookup"><span data-stu-id="ad80d-292">1000</span></span></td>
    <td><span data-ttu-id="ad80d-293">2</span><span class="sxs-lookup"><span data-stu-id="ad80d-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="ad80d-294">10</span><span class="sxs-lookup"><span data-stu-id="ad80d-294">10</span></span></td>
    <td><span data-ttu-id="ad80d-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-295">2,000.00</span></span></td>
    <td><span data-ttu-id="ad80d-296">10</span><span class="sxs-lookup"><span data-stu-id="ad80d-296">10</span></span></td>
    <td><span data-ttu-id="ad80d-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-297">2,000.00</span></span></td>
    <td><span data-ttu-id="ad80d-298">200.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="ad80d-299">10,00</span><span class="sxs-lookup"><span data-stu-id="ad80d-299">10.00</span></span></td>
    <td><span data-ttu-id="ad80d-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="ad80d-301"><strong>1000 összegek</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="ad80d-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="ad80d-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="ad80d-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="ad80d-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="ad80d-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="ad80d-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="ad80d-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="ad80d-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="ad80d-310">Ez alkalommal az 1. telephely két sorra van osztva, egy a 11-es raktárhoz, egy a 12-es raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="ad80d-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="ad80d-311">Ugyanakkor a **Készletérték mennyiség**, **Készletérték** és **Átlagos egységköltség** értékei nem változnak, mert a **Raktár** nem egy készletdimenzió.</span><span class="sxs-lookup"><span data-stu-id="ad80d-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="ad80d-312">Ezenkívül figyelje meg, hogy az 1. telephely mennyiségi felosztása eltérő.</span><span class="sxs-lookup"><span data-stu-id="ad80d-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="ad80d-313">A rendszer az elsőként futtatott jelentésben figyelmen kívül hagyta az ugyanazon a telephelyen belül bekövetkezett átmozgatási rendelést, és levonta az értékesítési számla mennyiségét az 1. telephely **2020/3/31 – 2020/3/1** időszakából.</span><span class="sxs-lookup"><span data-stu-id="ad80d-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="ad80d-314">Az új jelentésben azonban a rendszer levonja az értékesítési számla mennyiségét a **2020/5/8 – 2020/5/1** időszakra a 12. raktárban.</span><span class="sxs-lookup"><span data-stu-id="ad80d-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="ad80d-315">Készletzárás hatásai</span><span class="sxs-lookup"><span data-stu-id="ad80d-315">Effects of inventory closing</span></span>

<span data-ttu-id="ad80d-316">Ha májusra futtatja a készletzárást futtatja, majd újra futtatja az előző jelentést, de az **Adott dátumtól** mező értéke *2020 május 31*, a következő eredményeket kapja:</span><span class="sxs-lookup"><span data-stu-id="ad80d-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="ad80d-317">A program frissíti a **Készletérték** és az **Átlagos egységköltség** értékét.</span><span class="sxs-lookup"><span data-stu-id="ad80d-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="ad80d-318">A program ennek megfelelően frissíti az **Aktuális készletérték** és az **Összeg** értéket az összes időszakra.</span><span class="sxs-lookup"><span data-stu-id="ad80d-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="ad80d-319">Az új jelentés az alábbi példához hasonlóan jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ad80d-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="ad80d-320">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="ad80d-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-321">Webhely</span><span class="sxs-lookup"><span data-stu-id="ad80d-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-322">Raktár</span><span class="sxs-lookup"><span data-stu-id="ad80d-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-323">Aktuális mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-324">Aktuális készlet értéke</span><span class="sxs-lookup"><span data-stu-id="ad80d-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-325">Készletérték mennyisége</span><span class="sxs-lookup"><span data-stu-id="ad80d-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-326">Készletérték</span><span class="sxs-lookup"><span data-stu-id="ad80d-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="ad80d-327">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="ad80d-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="ad80d-328">2020/5/31 – 2020/5/1</span><span class="sxs-lookup"><span data-stu-id="ad80d-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="ad80d-329">2020/4/30 – 2020/4/1</span><span class="sxs-lookup"><span data-stu-id="ad80d-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="ad80d-330">2020/3/31 – 2020/3/1</span><span class="sxs-lookup"><span data-stu-id="ad80d-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="ad80d-331">P1:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="ad80d-332">P1:Összeg</span><span class="sxs-lookup"><span data-stu-id="ad80d-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="ad80d-333">P2:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="ad80d-334">P2:Összeg</span><span class="sxs-lookup"><span data-stu-id="ad80d-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="ad80d-335">P3:Mennyiség</span><span class="sxs-lookup"><span data-stu-id="ad80d-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="ad80d-336">P3:Összeg</span><span class="sxs-lookup"><span data-stu-id="ad80d-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="ad80d-337">1000</span><span class="sxs-lookup"><span data-stu-id="ad80d-337">1000</span></span></td>
    <td><span data-ttu-id="ad80d-338">1</span><span class="sxs-lookup"><span data-stu-id="ad80d-338">1</span></span></td>
    <td><span data-ttu-id="ad80d-339">11</span><span class="sxs-lookup"><span data-stu-id="ad80d-339">11</span></span></td>
    <td><span data-ttu-id="ad80d-340">10</span><span class="sxs-lookup"><span data-stu-id="ad80d-340">10</span></span></td>
    <td><span data-ttu-id="ad80d-341">910.70</span><span class="sxs-lookup"><span data-stu-id="ad80d-341">910.70</span></span></td>
    <td><span data-ttu-id="ad80d-342">14</span><span class="sxs-lookup"><span data-stu-id="ad80d-342">14</span></span></td>
    <td><span data-ttu-id="ad80d-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-343">1,275.00</span></span></td>
    <td><span data-ttu-id="ad80d-344">91.07</span><span class="sxs-lookup"><span data-stu-id="ad80d-344">91.07</span></span></td>
    <td><span data-ttu-id="ad80d-345">0,00</span><span class="sxs-lookup"><span data-stu-id="ad80d-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="ad80d-346">5.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-346">5.00</span></span></td>
    <td><span data-ttu-id="ad80d-347">455.36</span><span class="sxs-lookup"><span data-stu-id="ad80d-347">455.36</span></span></td>
    <td><span data-ttu-id="ad80d-348">5.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-348">5.00</span></span></td>
    <td><span data-ttu-id="ad80d-349">455.36</span><span class="sxs-lookup"><span data-stu-id="ad80d-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="ad80d-350">1000</span><span class="sxs-lookup"><span data-stu-id="ad80d-350">1000</span></span></td>
    <td><span data-ttu-id="ad80d-351">1</span><span class="sxs-lookup"><span data-stu-id="ad80d-351">1</span></span></td>
    <td><span data-ttu-id="ad80d-352">12</span><span class="sxs-lookup"><span data-stu-id="ad80d-352">12</span></span></td>
    <td><span data-ttu-id="ad80d-353">4</span><span class="sxs-lookup"><span data-stu-id="ad80d-353">4</span></span></td>
    <td><span data-ttu-id="ad80d-354">364.29</span><span class="sxs-lookup"><span data-stu-id="ad80d-354">364.29</span></span></td>
    <td><span data-ttu-id="ad80d-355">14</span><span class="sxs-lookup"><span data-stu-id="ad80d-355">14</span></span></td>
    <td><span data-ttu-id="ad80d-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-356">1,275.00</span></span></td>
    <td><span data-ttu-id="ad80d-357">91.07</span><span class="sxs-lookup"><span data-stu-id="ad80d-357">91.07</span></span></td>
    <td><span data-ttu-id="ad80d-358">4.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-358">4.00</span></span></td>
    <td><span data-ttu-id="ad80d-359">364.29</span><span class="sxs-lookup"><span data-stu-id="ad80d-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="ad80d-360">1000</span><span class="sxs-lookup"><span data-stu-id="ad80d-360">1000</span></span></td>
    <td><span data-ttu-id="ad80d-361">2</span><span class="sxs-lookup"><span data-stu-id="ad80d-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="ad80d-362">10</span><span class="sxs-lookup"><span data-stu-id="ad80d-362">10</span></span></td>
    <td><span data-ttu-id="ad80d-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-363">2,000.00</span></span></td>
    <td><span data-ttu-id="ad80d-364">10</span><span class="sxs-lookup"><span data-stu-id="ad80d-364">10</span></span></td>
    <td><span data-ttu-id="ad80d-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-365">2,000.00</span></span></td>
    <td><span data-ttu-id="ad80d-366">200.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="ad80d-367">10,00</span><span class="sxs-lookup"><span data-stu-id="ad80d-367">10.00</span></span></td>
    <td><span data-ttu-id="ad80d-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="ad80d-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="ad80d-369"><strong>1000 összegek</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="ad80d-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="ad80d-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="ad80d-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="ad80d-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="ad80d-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="ad80d-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="ad80d-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="ad80d-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="ad80d-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
