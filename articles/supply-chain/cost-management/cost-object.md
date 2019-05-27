---
title: Költségobjektumok
description: Ez a cikk tájékoztatást ad a költségobjektumokról és elmagyarázza hogyan halmozódnak föl a költségek és a mennyiségek. Egy költségobjektum egy olyan entitás, amelyhez költségek és mennyiségek halmozódnak föl. A költségobjektum-entitás lehet egy termék vagy egy termékváltozat, úgy mint változatok a stílusra és színre.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 275855f2fb4d32df91449d7ebb9ad9ba2bd3f36b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558549"
---
# <a name="cost-objects"></a><span data-ttu-id="ffb99-105">Költségobjektumok</span><span class="sxs-lookup"><span data-stu-id="ffb99-105">Cost objects</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ffb99-106">Ez a cikk tájékoztatást ad a költségobjektumokról és elmagyarázza hogyan halmozódnak föl a költségek és a mennyiségek.</span><span class="sxs-lookup"><span data-stu-id="ffb99-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="ffb99-107">Egy költségobjektum egy olyan entitás, amelyhez költségek és mennyiségek halmozódnak föl.</span><span class="sxs-lookup"><span data-stu-id="ffb99-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="ffb99-108">A költségobjektum-entitás lehet egy termék vagy egy termékváltozat, úgy mint változatok a stílusra és színre.</span><span class="sxs-lookup"><span data-stu-id="ffb99-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

## <a name="cost-objects"></a><span data-ttu-id="ffb99-109">Költségobjektumok</span><span class="sxs-lookup"><span data-stu-id="ffb99-109">Cost objects</span></span>

<span data-ttu-id="ffb99-110">A **Költségobjektumok** lap felsorolja az összes költségobjektumot, ami regisztrálva van egy termékhez.</span><span class="sxs-lookup"><span data-stu-id="ffb99-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="ffb99-111">A költségobjektumokat az alábbi forrásokból származó adatok határozzák meg:</span><span class="sxs-lookup"><span data-stu-id="ffb99-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="ffb99-112">Termék</span><span class="sxs-lookup"><span data-stu-id="ffb99-112">Product</span></span>
-   <span data-ttu-id="ffb99-113">Termékdimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="ffb99-113">Product dimension group</span></span>
-   <span data-ttu-id="ffb99-114">Tárolásidimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="ffb99-114">Storage dimension group</span></span>
-   <span data-ttu-id="ffb99-115">Nyomonkövetésidimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="ffb99-115">Tracking dimension group</span></span>

<span data-ttu-id="ffb99-116">**Megjegyzés:** A költségobjektum csak a **Közvetlen anyag** költségösszetevőjének felel meg.</span><span class="sxs-lookup"><span data-stu-id="ffb99-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="ffb99-117">A költségobjektum és a készletobjektum abban különböznek, hogy a költségobjektumot a pénzügyi készlet számára kiválasztott készletdimenzió határozza meg.</span><span class="sxs-lookup"><span data-stu-id="ffb99-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="ffb99-118">Például egy cikk az alábbi konfigurációval rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="ffb99-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="ffb99-119">**Webhely:** Tényleges készlet = Igen, Pénzügyi készlet = Igen</span><span class="sxs-lookup"><span data-stu-id="ffb99-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="ffb99-120">**Raktár:** Tényleges készlet = Igen, Pénzügyi készlet = Nem</span><span class="sxs-lookup"><span data-stu-id="ffb99-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="ffb99-121">**Köteg szám:** Tényleges készlet = Igen, Pénzügyi készlet = Nem</span><span class="sxs-lookup"><span data-stu-id="ffb99-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="ffb99-122">Az alábbi táblázat bemutatja, hogy mi a költségobjektum és mi a készletobjektum.</span><span class="sxs-lookup"><span data-stu-id="ffb99-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="ffb99-123">Objektumtípus</span><span class="sxs-lookup"><span data-stu-id="ffb99-123">Object type</span></span>      | <span data-ttu-id="ffb99-124">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="ffb99-124">Item number</span></span> | <span data-ttu-id="ffb99-125">Hely</span><span class="sxs-lookup"><span data-stu-id="ffb99-125">Site</span></span> | <span data-ttu-id="ffb99-126">Raktár</span><span class="sxs-lookup"><span data-stu-id="ffb99-126">Warehouse</span></span> | <span data-ttu-id="ffb99-127">Kötegsz.</span><span class="sxs-lookup"><span data-stu-id="ffb99-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="ffb99-128">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="ffb99-128">Cost object</span></span>      | <span data-ttu-id="ffb99-129">x</span><span class="sxs-lookup"><span data-stu-id="ffb99-129">x</span></span>           | <span data-ttu-id="ffb99-130">x</span><span class="sxs-lookup"><span data-stu-id="ffb99-130">x</span></span>    |           |           |
| <span data-ttu-id="ffb99-131">Készletobjektum</span><span class="sxs-lookup"><span data-stu-id="ffb99-131">Inventory object</span></span> | <span data-ttu-id="ffb99-132">x</span><span class="sxs-lookup"><span data-stu-id="ffb99-132">x</span></span>           | <span data-ttu-id="ffb99-133">x</span><span class="sxs-lookup"><span data-stu-id="ffb99-133">x</span></span>    |  <span data-ttu-id="ffb99-134">x</span><span class="sxs-lookup"><span data-stu-id="ffb99-134">x</span></span>        | <span data-ttu-id="ffb99-135">x</span><span class="sxs-lookup"><span data-stu-id="ffb99-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="ffb99-136">A költség és mennyiség összevonása</span><span class="sxs-lookup"><span data-stu-id="ffb99-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="ffb99-137">Az érték az **Érték** mezőben az alábbi értékek összessége:</span><span class="sxs-lookup"><span data-stu-id="ffb99-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="ffb99-138">Tényleges önköltségi érték</span><span class="sxs-lookup"><span data-stu-id="ffb99-138">Physical cost amount</span></span>
    -   <span data-ttu-id="ffb99-139">Pénzügyi költség összege</span><span class="sxs-lookup"><span data-stu-id="ffb99-139">Financial cost amount</span></span>
    -   <span data-ttu-id="ffb99-140">Kiigazítások</span><span class="sxs-lookup"><span data-stu-id="ffb99-140">Adjustments</span></span>
-   <span data-ttu-id="ffb99-141">Az érték a **Mennyiség** mezőben az alábbi értékek összessége:</span><span class="sxs-lookup"><span data-stu-id="ffb99-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="ffb99-142">Bevételezve</span><span class="sxs-lookup"><span data-stu-id="ffb99-142">Received</span></span>
    -   <span data-ttu-id="ffb99-143">Kiszállított</span><span class="sxs-lookup"><span data-stu-id="ffb99-143">Deducted</span></span>
    -   <span data-ttu-id="ffb99-144">Feladott mennyiség</span><span class="sxs-lookup"><span data-stu-id="ffb99-144">Posted quantity</span></span>
-   <span data-ttu-id="ffb99-145">Az **Átlagos egységenkénti költség** mező egy kiszámított mező.</span><span class="sxs-lookup"><span data-stu-id="ffb99-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="ffb99-146">Az értékét az **Érték** mező **Mennyiség** mezővel való elosztásával kapjuk meg.</span><span class="sxs-lookup"><span data-stu-id="ffb99-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="ffb99-147">**Megjegyzés**: A **Tényleges érték beszámítása** paraméter nem befolyásolja az előző számításokat.</span><span class="sxs-lookup"><span data-stu-id="ffb99-147">**Note:** The \*\*Include physical value \*\*parameter has no effect on the preceding calculations.</span></span>

<a name="additional-resources"></a><span data-ttu-id="ffb99-148">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="ffb99-148">Additional resources</span></span>
--------

[<span data-ttu-id="ffb99-149">Termékdimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="ffb99-149">Product dimension group</span></span>](https://technet.microsoft.com/en-us/library/aa499382.aspx)

[<span data-ttu-id="ffb99-150">Tárolásidimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="ffb99-150">Storage dimension group</span></span>](https://technet.microsoft.com/en-us/library/hh209317.aspx)

[<span data-ttu-id="ffb99-151">Nyomonkövetésidimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="ffb99-151">Tracking dimension group</span></span>](https://technet.microsoft.com/en-us/library/hh209465.aspx)

[<span data-ttu-id="ffb99-152">Új vagy módosult elemek</span><span class="sxs-lookup"><span data-stu-id="ffb99-152">What's new or changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)

[<span data-ttu-id="ffb99-153">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="ffb99-153">Cost entries</span></span>](cost-entries.md)



