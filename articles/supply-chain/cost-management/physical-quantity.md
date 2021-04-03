---
title: Készletobjektum-értékek
description: Ez a cikk tájékoztatást egy készletobjektum értékekének számításáról.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f14248ffa8f9f5a460b090ca5754442cd50bf45a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263542"
---
# <a name="inventory-object-values"></a><span data-ttu-id="184f0-103">Készletobjektum-értékek</span><span class="sxs-lookup"><span data-stu-id="184f0-103">Inventory object values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="184f0-104">Ez a cikk tájékoztatást egy készletobjektum értékekének számításáról.</span><span class="sxs-lookup"><span data-stu-id="184f0-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="184f0-105">Egy új funkció, aminek a neve **Fizikai mennyiség**, lehetővé teszi, hogy lássa egy megadott készletobjektum értékét.</span><span class="sxs-lookup"><span data-stu-id="184f0-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="184f0-106">Egy költségobjektum annak az entitás szintnek felel meg, ahol a készletkönyvelést végzik.</span><span class="sxs-lookup"><span data-stu-id="184f0-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="184f0-107">A költségobjektummal kapcsolatos további tudnivalókat lásd: [Költségobjektum](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="184f0-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="184f0-108">Egy adott készletobjektum értékeinek megtekintéséhez kattintson a **Fizikai mennyiség** lehetőségre a **Költségobjektum** oldalon.</span><span class="sxs-lookup"><span data-stu-id="184f0-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="184f0-109">Egy készletobjektum értéke az alábbi módon lesz kiszámolva:</span><span class="sxs-lookup"><span data-stu-id="184f0-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="184f0-110">Készletobjektum.Értéke = Költségobjektum.Átlagos egységenkénti költsége × Készletobjektum.Mennyisége.</span><span class="sxs-lookup"><span data-stu-id="184f0-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="184f0-111">Az alábbi példában látható, hogy a készletobjektum értéke és a költségobjektum hogyan számolható ki.</span><span class="sxs-lookup"><span data-stu-id="184f0-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="184f0-112">Két termékbevételezési esemény van az A cikken rögzítve:</span><span class="sxs-lookup"><span data-stu-id="184f0-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="184f0-113">Termékbevételezés 1: Mennyiség = 100 darab. Összeg = 1 000,00 $ Hely = 1 Raktár = 11, Köteg száma</span><span class="sxs-lookup"><span data-stu-id="184f0-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="184f0-114">= B1</span><span class="sxs-lookup"><span data-stu-id="184f0-114">= B1</span></span>
-   <span data-ttu-id="184f0-115">Termékbevételezés 2: Mennyiség = 50 darab. Összeg = 800,00 $ Hely = 1 Raktár = 11, Köteg száma</span><span class="sxs-lookup"><span data-stu-id="184f0-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="184f0-116">= B2</span><span class="sxs-lookup"><span data-stu-id="184f0-116">= B2</span></span>

<span data-ttu-id="184f0-117">Az alábbi táblázat a költségobjektum-számítás eredményét mutatja.</span><span class="sxs-lookup"><span data-stu-id="184f0-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="184f0-118">Az eredményeket megtekintheti a **Költségobjektum** oldalon.</span><span class="sxs-lookup"><span data-stu-id="184f0-118">You can view the result on the **Cost object** page.</span></span>

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
<th><span data-ttu-id="184f0-119">Objektumtípus</span><span class="sxs-lookup"><span data-stu-id="184f0-119">Object type</span></span></th>
<th><span data-ttu-id="184f0-120">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="184f0-120">Item number</span></span></th>
<th><span data-ttu-id="184f0-121">Hely</span><span class="sxs-lookup"><span data-stu-id="184f0-121">Site</span></span></th>
<th><span data-ttu-id="184f0-122">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="184f0-122">Quantity</span></span></th>
<th><span data-ttu-id="184f0-123">Készletegység</span><span class="sxs-lookup"><span data-stu-id="184f0-123">Inventory unit</span></span></th>
<th><span data-ttu-id="184f0-124">Érték</span><span class="sxs-lookup"><span data-stu-id="184f0-124">Value</span></span></th>
<th><span data-ttu-id="184f0-125">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="184f0-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="184f0-126">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="184f0-126">Cost object</span></span></td>
<td><span data-ttu-id="184f0-127">N</span><span class="sxs-lookup"><span data-stu-id="184f0-127">A</span></span></td>
<td><span data-ttu-id="184f0-128">1</span><span class="sxs-lookup"><span data-stu-id="184f0-128">1</span></span></td>
<td><span data-ttu-id="184f0-129">150</span><span class="sxs-lookup"><span data-stu-id="184f0-129">150</span></span></td>
<td><span data-ttu-id="184f0-130">Darab</span><span class="sxs-lookup"><span data-stu-id="184f0-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="184f0-131">1800.00 $</span><span class="sxs-lookup"><span data-stu-id="184f0-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="184f0-132">12.00 $</span><span class="sxs-lookup"><span data-stu-id="184f0-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="184f0-133">Az alábbi táblázat a készletobjektum-számítás eredményét mutatja.</span><span class="sxs-lookup"><span data-stu-id="184f0-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="184f0-134">Az eredményeket megtekintheti a **Fizikai mennyiség** lehetőségnél, a **Költségobjektum** oldalon.</span><span class="sxs-lookup"><span data-stu-id="184f0-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

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
<th><span data-ttu-id="184f0-135">Objektumtípus</span><span class="sxs-lookup"><span data-stu-id="184f0-135">Object type</span></span></th>
<th><span data-ttu-id="184f0-136">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="184f0-136">Item number</span></span></th>
<th><span data-ttu-id="184f0-137">Hely</span><span class="sxs-lookup"><span data-stu-id="184f0-137">Site</span></span></th>
<th><span data-ttu-id="184f0-138">Raktár</span><span class="sxs-lookup"><span data-stu-id="184f0-138">Warehouse</span></span></th>
<th><span data-ttu-id="184f0-139">Kötegsz.</span><span class="sxs-lookup"><span data-stu-id="184f0-139">Batch No.</span></span></th>
<th><span data-ttu-id="184f0-140">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="184f0-140">Quantity</span></span></th>
<th><span data-ttu-id="184f0-141">Készletegység</span><span class="sxs-lookup"><span data-stu-id="184f0-141">Inventory unit</span></span></th>
<th><span data-ttu-id="184f0-142">Érték</span><span class="sxs-lookup"><span data-stu-id="184f0-142">Value</span></span></th>
<th><span data-ttu-id="184f0-143">Átlagos egységenkénti költség</span><span class="sxs-lookup"><span data-stu-id="184f0-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="184f0-144">Készletobjektum</span><span class="sxs-lookup"><span data-stu-id="184f0-144">Inventory object</span></span></td>
<td><span data-ttu-id="184f0-145">N</span><span class="sxs-lookup"><span data-stu-id="184f0-145">A</span></span></td>
<td><span data-ttu-id="184f0-146">1</span><span class="sxs-lookup"><span data-stu-id="184f0-146">1</span></span></td>
<td><span data-ttu-id="184f0-147">11</span><span class="sxs-lookup"><span data-stu-id="184f0-147">11</span></span></td>
<td><span data-ttu-id="184f0-148">B1</span><span class="sxs-lookup"><span data-stu-id="184f0-148">B1</span></span></td>
<td><span data-ttu-id="184f0-149">100</span><span class="sxs-lookup"><span data-stu-id="184f0-149">100</span></span></td>
<td><span data-ttu-id="184f0-150">Darab</span><span class="sxs-lookup"><span data-stu-id="184f0-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="184f0-151">1200.00 $</span><span class="sxs-lookup"><span data-stu-id="184f0-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="184f0-152">12.00 $</span><span class="sxs-lookup"><span data-stu-id="184f0-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="184f0-153">Készletobjektum</span><span class="sxs-lookup"><span data-stu-id="184f0-153">Inventory object</span></span></td>
<td><span data-ttu-id="184f0-154">A</span><span class="sxs-lookup"><span data-stu-id="184f0-154">A</span></span></td>
<td><span data-ttu-id="184f0-155">1</span><span class="sxs-lookup"><span data-stu-id="184f0-155">1</span></span></td>
<td><span data-ttu-id="184f0-156">11</span><span class="sxs-lookup"><span data-stu-id="184f0-156">11</span></span></td>
<td><span data-ttu-id="184f0-157">B2</span><span class="sxs-lookup"><span data-stu-id="184f0-157">B2</span></span></td>
<td><span data-ttu-id="184f0-158">50</span><span class="sxs-lookup"><span data-stu-id="184f0-158">50</span></span></td>
<td><span data-ttu-id="184f0-159">Darab</span><span class="sxs-lookup"><span data-stu-id="184f0-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="184f0-160">600.00 $</span><span class="sxs-lookup"><span data-stu-id="184f0-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="184f0-161">12.00 $</span><span class="sxs-lookup"><span data-stu-id="184f0-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="184f0-162">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="184f0-162">Additional resources</span></span>
--------

[<span data-ttu-id="184f0-163">Költségobjektumok</span><span class="sxs-lookup"><span data-stu-id="184f0-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="184f0-164">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="184f0-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="184f0-165">Új és módosult elemek</span><span class="sxs-lookup"><span data-stu-id="184f0-165">What's new and changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]