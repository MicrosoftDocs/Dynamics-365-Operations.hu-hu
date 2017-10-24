---
title: "Készletobjektum-értékek"
description: "Ez a cikk tájékoztatást egy készletobjektum értékekének számításáról."
author: AndersGirke
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
ms.translationtype: HT
ms.sourcegitcommit: a61761a5c9d98befd67682e1790af5377b7a55e1
ms.openlocfilehash: 2cdd1377d3c7c922a3e4cba7f44eef24b0c6824c
ms.contentlocale: hu-hu
ms.lasthandoff: 10/13/2017

---

# <a name="inventory-object-values"></a><span data-ttu-id="f1356-103">Készletobjektum-értékek</span><span class="sxs-lookup"><span data-stu-id="f1356-103">Inventory object values</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f1356-104">Ez a cikk tájékoztatást egy készletobjektum értékekének számításáról.</span><span class="sxs-lookup"><span data-stu-id="f1356-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="f1356-105">Egy új funkció, aminek a neve **Fizikai mennyiség**, lehetővé teszi, hogy lássa egy megadott készletobjektum értékét.</span><span class="sxs-lookup"><span data-stu-id="f1356-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="f1356-106">Egy költségobjektum annak az entitás szintnek felel meg, ahol a készletkönyvelést végzik.</span><span class="sxs-lookup"><span data-stu-id="f1356-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="f1356-107">A költségobjektummal kapcsolatos további tudnivalókat lásd: [Költségobjektum](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="f1356-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="f1356-108">Egy adott készletobjektum értékeinek megtekintéséhez kattintson a **Fizikai mennyiség** lehetőségre a **Költségobjektum** oldalon.</span><span class="sxs-lookup"><span data-stu-id="f1356-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="f1356-109">Egy készletobjektum értéke az alábbi módon lesz kiszámolva:</span><span class="sxs-lookup"><span data-stu-id="f1356-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="f1356-110">Készletobjektum.Értéke = Költségobjektum.Átlagos egységenkénti költsége × Készletobjektum.Mennyisége.</span><span class="sxs-lookup"><span data-stu-id="f1356-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="f1356-111">Az alábbi példában látható, hogy a készletobjektum értéke és a költségobjektum hogyan számolható ki.</span><span class="sxs-lookup"><span data-stu-id="f1356-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="f1356-112">Két termékbevételezési esemény van az A cikken rögzítve:</span><span class="sxs-lookup"><span data-stu-id="f1356-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="f1356-113">Termékbevételezés 1: Mennyiség = 100 darab. Összeg = 1 000,00 $ Hely = 1 Raktár = 11, Köteg száma</span><span class="sxs-lookup"><span data-stu-id="f1356-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="f1356-114">= B1</span><span class="sxs-lookup"><span data-stu-id="f1356-114">= B1</span></span>
-   <span data-ttu-id="f1356-115">Termékbevételezés 2: Mennyiség = 50 darab. Összeg = 800,00 $ Hely = 1 Raktár = 11, Köteg száma</span><span class="sxs-lookup"><span data-stu-id="f1356-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="f1356-116">= B2</span><span class="sxs-lookup"><span data-stu-id="f1356-116">= B2</span></span>

<span data-ttu-id="f1356-117">Az alábbi táblázat a költségobjektum-számítás eredményét mutatja.</span><span class="sxs-lookup"><span data-stu-id="f1356-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="f1356-118">Az eredményeket megtekintheti a **Költségobjektum** oldalon.</span><span class="sxs-lookup"><span data-stu-id="f1356-118">You can view the result on the **Cost object** page.</span></span>

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
<th><span data-ttu-id="f1356-119">Objektumtípus</span><span class="sxs-lookup"><span data-stu-id="f1356-119">Object type</span></span></th>
<th><span data-ttu-id="f1356-120">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="f1356-120">Item number</span></span></th>
<th><span data-ttu-id="f1356-121">Hely</span><span class="sxs-lookup"><span data-stu-id="f1356-121">Site</span></span></th>
<th><span data-ttu-id="f1356-122">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="f1356-122">Quantity</span></span></th>
<th><span data-ttu-id="f1356-123">Készletegység</span><span class="sxs-lookup"><span data-stu-id="f1356-123">Inventory unit</span></span></th>
<th><span data-ttu-id="f1356-124">Érték</span><span class="sxs-lookup"><span data-stu-id="f1356-124">Value</span></span></th>
<th><span data-ttu-id="f1356-125">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="f1356-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f1356-126">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="f1356-126">Cost object</span></span></td>
<td><span data-ttu-id="f1356-127">N</span><span class="sxs-lookup"><span data-stu-id="f1356-127">A</span></span></td>
<td><span data-ttu-id="f1356-128">1</span><span class="sxs-lookup"><span data-stu-id="f1356-128">1</span></span></td>
<td><span data-ttu-id="f1356-129">150</span><span class="sxs-lookup"><span data-stu-id="f1356-129">150</span></span></td>
<td><span data-ttu-id="f1356-130">Darab</span><span class="sxs-lookup"><span data-stu-id="f1356-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="f1356-131">1800.00 $</span><span class="sxs-lookup"><span data-stu-id="f1356-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="f1356-132">12.00 $</span><span class="sxs-lookup"><span data-stu-id="f1356-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f1356-133">Az alábbi táblázat a készletobjektum-számítás eredményét mutatja.</span><span class="sxs-lookup"><span data-stu-id="f1356-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="f1356-134">Az eredményeket megtekintheti a **Fizikai mennyiség** lehetőségnél, a **Költségobjektum** oldalon.</span><span class="sxs-lookup"><span data-stu-id="f1356-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

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
<th><span data-ttu-id="f1356-135">Objektumtípus</span><span class="sxs-lookup"><span data-stu-id="f1356-135">Object type</span></span></th>
<th><span data-ttu-id="f1356-136">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="f1356-136">Item number</span></span></th>
<th><span data-ttu-id="f1356-137">Hely</span><span class="sxs-lookup"><span data-stu-id="f1356-137">Site</span></span></th>
<th><span data-ttu-id="f1356-138">Raktár</span><span class="sxs-lookup"><span data-stu-id="f1356-138">Warehouse</span></span></th>
<th><span data-ttu-id="f1356-139">Kötegsz.</span><span class="sxs-lookup"><span data-stu-id="f1356-139">Batch No.</span></span></th>
<th><span data-ttu-id="f1356-140">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="f1356-140">Quantity</span></span></th>
<th><span data-ttu-id="f1356-141">Készletegység</span><span class="sxs-lookup"><span data-stu-id="f1356-141">Inventory unit</span></span></th>
<th><span data-ttu-id="f1356-142">Érték</span><span class="sxs-lookup"><span data-stu-id="f1356-142">Value</span></span></th>
<th><span data-ttu-id="f1356-143">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="f1356-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f1356-144">Készletobjektum</span><span class="sxs-lookup"><span data-stu-id="f1356-144">Inventory object</span></span></td>
<td><span data-ttu-id="f1356-145">N</span><span class="sxs-lookup"><span data-stu-id="f1356-145">A</span></span></td>
<td><span data-ttu-id="f1356-146">1</span><span class="sxs-lookup"><span data-stu-id="f1356-146">1</span></span></td>
<td><span data-ttu-id="f1356-147">11</span><span class="sxs-lookup"><span data-stu-id="f1356-147">11</span></span></td>
<td><span data-ttu-id="f1356-148">B1</span><span class="sxs-lookup"><span data-stu-id="f1356-148">B1</span></span></td>
<td><span data-ttu-id="f1356-149">100</span><span class="sxs-lookup"><span data-stu-id="f1356-149">100</span></span></td>
<td><span data-ttu-id="f1356-150">Darab</span><span class="sxs-lookup"><span data-stu-id="f1356-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="f1356-151">1200.00 $</span><span class="sxs-lookup"><span data-stu-id="f1356-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="f1356-152">12.00 $</span><span class="sxs-lookup"><span data-stu-id="f1356-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f1356-153">Készletobjektum</span><span class="sxs-lookup"><span data-stu-id="f1356-153">Inventory object</span></span></td>
<td><span data-ttu-id="f1356-154">A:</span><span class="sxs-lookup"><span data-stu-id="f1356-154">A</span></span></td>
<td><span data-ttu-id="f1356-155">1</span><span class="sxs-lookup"><span data-stu-id="f1356-155">1</span></span></td>
<td><span data-ttu-id="f1356-156">11</span><span class="sxs-lookup"><span data-stu-id="f1356-156">11</span></span></td>
<td><span data-ttu-id="f1356-157">B2</span><span class="sxs-lookup"><span data-stu-id="f1356-157">B2</span></span></td>
<td><span data-ttu-id="f1356-158">50</span><span class="sxs-lookup"><span data-stu-id="f1356-158">50</span></span></td>
<td><span data-ttu-id="f1356-159">Darab</span><span class="sxs-lookup"><span data-stu-id="f1356-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="f1356-160">600.00 $</span><span class="sxs-lookup"><span data-stu-id="f1356-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="f1356-161">12.00 $</span><span class="sxs-lookup"><span data-stu-id="f1356-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="f1356-162">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f1356-162">See also</span></span>
--------

[<span data-ttu-id="f1356-163">Költségobjektumok</span><span class="sxs-lookup"><span data-stu-id="f1356-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="f1356-164">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="f1356-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="f1356-165">Új és módosult elemek</span><span class="sxs-lookup"><span data-stu-id="f1356-165">What's new and changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)




