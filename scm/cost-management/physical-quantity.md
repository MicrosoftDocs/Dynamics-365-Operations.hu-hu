---
title: "Készletobjektum-értékek"
description: "Ez a cikk tájékoztatást egy készletobjektum értékekének számításáról."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 4aec6e70325c7e4d00e6070293a1ab0c719e420b
ms.contentlocale: hu-hu
ms.lasthandoff: 07/18/2017

---

# <a name="inventory-object-values"></a><span data-ttu-id="7205a-103">Készletobjektum-értékek</span><span class="sxs-lookup"><span data-stu-id="7205a-103">Inventory object values</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7205a-104">Ez a cikk tájékoztatást egy készletobjektum értékekének számításáról.</span><span class="sxs-lookup"><span data-stu-id="7205a-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="7205a-105">Egy új funkció, aminek a neve **Fizikai mennyiség**, lehetővé teszi, hogy lássa egy megadott készletobjektum értékét.</span><span class="sxs-lookup"><span data-stu-id="7205a-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="7205a-106">Egy költségobjektum annak az entitás szintnek felel meg, ahol a készletkönyvelést végzik.</span><span class="sxs-lookup"><span data-stu-id="7205a-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="7205a-107">A költségobjektummal kapcsolatos további tudnivalókat lásd: [Költségobjektum](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="7205a-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="7205a-108">Egy adott készletobjektum értékeinek megtekintéséhez kattintson a **Fizikai mennyiség** lehetőségre a **Költségobjektum** oldalon.</span><span class="sxs-lookup"><span data-stu-id="7205a-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="7205a-109">Egy készletobjektum értéke az alábbi módon lesz kiszámolva:</span><span class="sxs-lookup"><span data-stu-id="7205a-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="7205a-110">Készletobjektum.Értéke = Költségobjektum.Átlagos egységenkénti költsége × Készletobjektum.Mennyisége.</span><span class="sxs-lookup"><span data-stu-id="7205a-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="7205a-111">Az alábbi példában látható, hogy a készletobjektum értéke és a költségobjektum hogyan számolható ki.</span><span class="sxs-lookup"><span data-stu-id="7205a-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="7205a-112">Két termékbevételezési esemény van az A cikken rögzítve:</span><span class="sxs-lookup"><span data-stu-id="7205a-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="7205a-113">Termékbevételezés 1: Mennyiség = 100 darab. Összeg = 1 000,00 $ Hely = 1 Raktár = 11, Köteg száma</span><span class="sxs-lookup"><span data-stu-id="7205a-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="7205a-114">= B1</span><span class="sxs-lookup"><span data-stu-id="7205a-114">= B1</span></span>
-   <span data-ttu-id="7205a-115">Termékbevételezés 2: Mennyiség = 50 darab. Összeg = 800,00 $ Hely = 1 Raktár = 11, Köteg száma</span><span class="sxs-lookup"><span data-stu-id="7205a-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="7205a-116">= B2</span><span class="sxs-lookup"><span data-stu-id="7205a-116">= B2</span></span>

<span data-ttu-id="7205a-117">Az alábbi táblázat a költségobjektum-számítás eredményét mutatja.</span><span class="sxs-lookup"><span data-stu-id="7205a-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="7205a-118">Az eredményeket megtekintheti a **Költségobjektum** oldalon.</span><span class="sxs-lookup"><span data-stu-id="7205a-118">You can view the result on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7205a-119">Objektumtípus</span><span class="sxs-lookup"><span data-stu-id="7205a-119">Object type</span></span></th>
<th><span data-ttu-id="7205a-120">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="7205a-120">Item number</span></span></th>
<th><span data-ttu-id="7205a-121">Hely</span><span class="sxs-lookup"><span data-stu-id="7205a-121">Site</span></span></th>
<th><span data-ttu-id="7205a-122">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="7205a-122">Quantity</span></span></th>
<th><span data-ttu-id="7205a-123">Készletegység</span><span class="sxs-lookup"><span data-stu-id="7205a-123">Inventory unit</span></span></th>
<th><span data-ttu-id="7205a-124">Érték</span><span class="sxs-lookup"><span data-stu-id="7205a-124">Value</span></span></th>
<th><span data-ttu-id="7205a-125">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="7205a-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7205a-126">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="7205a-126">Cost object</span></span></td>
<td><span data-ttu-id="7205a-127">N</span><span class="sxs-lookup"><span data-stu-id="7205a-127">A</span></span></td>
<td><span data-ttu-id="7205a-128">1</span><span class="sxs-lookup"><span data-stu-id="7205a-128">1</span></span></td>
<td><span data-ttu-id="7205a-129">150</span><span class="sxs-lookup"><span data-stu-id="7205a-129">150</span></span></td>
<td><span data-ttu-id="7205a-130">Darab</span><span class="sxs-lookup"><span data-stu-id="7205a-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="7205a-131">1800.00 $</span><span class="sxs-lookup"><span data-stu-id="7205a-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="7205a-132">12.00 $</span><span class="sxs-lookup"><span data-stu-id="7205a-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="7205a-133">Az alábbi táblázat a készletobjektum-számítás eredményét mutatja.</span><span class="sxs-lookup"><span data-stu-id="7205a-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="7205a-134">Az eredményeket megtekintheti a **Fizikai mennyiség** lehetőségnél, a **Költségobjektum** oldalon.</span><span class="sxs-lookup"><span data-stu-id="7205a-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7205a-135">Objektumtípus</span><span class="sxs-lookup"><span data-stu-id="7205a-135">Object type</span></span></th>
<th><span data-ttu-id="7205a-136">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="7205a-136">Item number</span></span></th>
<th><span data-ttu-id="7205a-137">Hely</span><span class="sxs-lookup"><span data-stu-id="7205a-137">Site</span></span></th>
<th><span data-ttu-id="7205a-138">Raktár</span><span class="sxs-lookup"><span data-stu-id="7205a-138">Warehouse</span></span></th>
<th><span data-ttu-id="7205a-139">Kötegsz.</span><span class="sxs-lookup"><span data-stu-id="7205a-139">Batch No.</span></span></th>
<th><span data-ttu-id="7205a-140">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="7205a-140">Quantity</span></span></th>
<th><span data-ttu-id="7205a-141">Készletegység</span><span class="sxs-lookup"><span data-stu-id="7205a-141">Inventory unit</span></span></th>
<th><span data-ttu-id="7205a-142">Érték</span><span class="sxs-lookup"><span data-stu-id="7205a-142">Value</span></span></th>
<th><span data-ttu-id="7205a-143">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="7205a-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7205a-144">Készletobjektum</span><span class="sxs-lookup"><span data-stu-id="7205a-144">Inventory object</span></span></td>
<td><span data-ttu-id="7205a-145">N</span><span class="sxs-lookup"><span data-stu-id="7205a-145">A</span></span></td>
<td><span data-ttu-id="7205a-146">1</span><span class="sxs-lookup"><span data-stu-id="7205a-146">1</span></span></td>
<td><span data-ttu-id="7205a-147">11</span><span class="sxs-lookup"><span data-stu-id="7205a-147">11</span></span></td>
<td><span data-ttu-id="7205a-148">B1</span><span class="sxs-lookup"><span data-stu-id="7205a-148">B1</span></span></td>
<td><span data-ttu-id="7205a-149">100</span><span class="sxs-lookup"><span data-stu-id="7205a-149">100</span></span></td>
<td><span data-ttu-id="7205a-150">Darab</span><span class="sxs-lookup"><span data-stu-id="7205a-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="7205a-151">1200.00 $</span><span class="sxs-lookup"><span data-stu-id="7205a-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="7205a-152">12.00 $</span><span class="sxs-lookup"><span data-stu-id="7205a-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7205a-153">Készletobjektum</span><span class="sxs-lookup"><span data-stu-id="7205a-153">Inventory object</span></span></td>
<td><span data-ttu-id="7205a-154">A:</span><span class="sxs-lookup"><span data-stu-id="7205a-154">A</span></span></td>
<td><span data-ttu-id="7205a-155">1</span><span class="sxs-lookup"><span data-stu-id="7205a-155">1</span></span></td>
<td><span data-ttu-id="7205a-156">11</span><span class="sxs-lookup"><span data-stu-id="7205a-156">11</span></span></td>
<td><span data-ttu-id="7205a-157">B2</span><span class="sxs-lookup"><span data-stu-id="7205a-157">B2</span></span></td>
<td><span data-ttu-id="7205a-158">50</span><span class="sxs-lookup"><span data-stu-id="7205a-158">50</span></span></td>
<td><span data-ttu-id="7205a-159">Darab</span><span class="sxs-lookup"><span data-stu-id="7205a-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="7205a-160">600.00 $</span><span class="sxs-lookup"><span data-stu-id="7205a-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="7205a-161">12.00 $</span><span class="sxs-lookup"><span data-stu-id="7205a-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="7205a-162">Lásd még</span><span class="sxs-lookup"><span data-stu-id="7205a-162">See also</span></span>
--------

[<span data-ttu-id="7205a-163">Költségobjektumok</span><span class="sxs-lookup"><span data-stu-id="7205a-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="7205a-164">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="7205a-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="7205a-165">Új és módosult elemek</span><span class="sxs-lookup"><span data-stu-id="7205a-165">What's new and changed</span></span>](/dynamics365/unified-operations/dev-itpro/get-started/whats-new-changed)




