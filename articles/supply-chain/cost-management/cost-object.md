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
ms.openlocfilehash: 6501e8d809d12df421ad081662d23a6b5005f39c
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742137"
---
# <a name="cost-objects"></a><span data-ttu-id="1660c-105">Költségobjektumok</span><span class="sxs-lookup"><span data-stu-id="1660c-105">Cost objects</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1660c-106">Ez a cikk tájékoztatást ad a költségobjektumokról és elmagyarázza hogyan halmozódnak föl a költségek és a mennyiségek.</span><span class="sxs-lookup"><span data-stu-id="1660c-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="1660c-107">Egy költségobjektum egy olyan entitás, amelyhez költségek és mennyiségek halmozódnak föl.</span><span class="sxs-lookup"><span data-stu-id="1660c-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="1660c-108">A költségobjektum-entitás lehet egy termék vagy egy termékváltozat, úgy mint változatok a stílusra és színre.</span><span class="sxs-lookup"><span data-stu-id="1660c-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

## <a name="cost-objects"></a><span data-ttu-id="1660c-109">Költségobjektumok</span><span class="sxs-lookup"><span data-stu-id="1660c-109">Cost objects</span></span>

<span data-ttu-id="1660c-110">A **Költségobjektumok** lap felsorolja az összes költségobjektumot, ami regisztrálva van egy termékhez.</span><span class="sxs-lookup"><span data-stu-id="1660c-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="1660c-111">A költségobjektumokat az alábbi forrásokból származó adatok határozzák meg:</span><span class="sxs-lookup"><span data-stu-id="1660c-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="1660c-112">Termék</span><span class="sxs-lookup"><span data-stu-id="1660c-112">Product</span></span>
-   <span data-ttu-id="1660c-113">Termékdimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="1660c-113">Product dimension group</span></span>
-   <span data-ttu-id="1660c-114">Tárolásidimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="1660c-114">Storage dimension group</span></span>
-   <span data-ttu-id="1660c-115">Nyomonkövetésidimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="1660c-115">Tracking dimension group</span></span>

<span data-ttu-id="1660c-116">**Megjegyzés:** A költségobjektum csak a **Közvetlen anyag** költségösszetevőjének felel meg.</span><span class="sxs-lookup"><span data-stu-id="1660c-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="1660c-117">A költségobjektum és a készletobjektum abban különböznek, hogy a költségobjektumot a pénzügyi készlet számára kiválasztott készletdimenzió határozza meg.</span><span class="sxs-lookup"><span data-stu-id="1660c-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="1660c-118">Például egy cikk az alábbi konfigurációval rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="1660c-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="1660c-119">**Webhely:** Tényleges készlet = Igen, Pénzügyi készlet = Igen</span><span class="sxs-lookup"><span data-stu-id="1660c-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="1660c-120">**Raktár:** Tényleges készlet = Igen, Pénzügyi készlet = Nem</span><span class="sxs-lookup"><span data-stu-id="1660c-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="1660c-121">**Köteg szám:** Tényleges készlet = Igen, Pénzügyi készlet = Nem</span><span class="sxs-lookup"><span data-stu-id="1660c-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="1660c-122">Az alábbi táblázat bemutatja, hogy mi a költségobjektum és mi a készletobjektum.</span><span class="sxs-lookup"><span data-stu-id="1660c-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="1660c-123">Objektumtípus</span><span class="sxs-lookup"><span data-stu-id="1660c-123">Object type</span></span>      | <span data-ttu-id="1660c-124">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="1660c-124">Item number</span></span> | <span data-ttu-id="1660c-125">Hely</span><span class="sxs-lookup"><span data-stu-id="1660c-125">Site</span></span> | <span data-ttu-id="1660c-126">Raktár</span><span class="sxs-lookup"><span data-stu-id="1660c-126">Warehouse</span></span> | <span data-ttu-id="1660c-127">Kötegsz.</span><span class="sxs-lookup"><span data-stu-id="1660c-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="1660c-128">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="1660c-128">Cost object</span></span>      | <span data-ttu-id="1660c-129">x</span><span class="sxs-lookup"><span data-stu-id="1660c-129">x</span></span>           | <span data-ttu-id="1660c-130">x</span><span class="sxs-lookup"><span data-stu-id="1660c-130">x</span></span>    |           |           |
| <span data-ttu-id="1660c-131">Készletobjektum</span><span class="sxs-lookup"><span data-stu-id="1660c-131">Inventory object</span></span> | <span data-ttu-id="1660c-132">x</span><span class="sxs-lookup"><span data-stu-id="1660c-132">x</span></span>           | <span data-ttu-id="1660c-133">x</span><span class="sxs-lookup"><span data-stu-id="1660c-133">x</span></span>    |  <span data-ttu-id="1660c-134">x</span><span class="sxs-lookup"><span data-stu-id="1660c-134">x</span></span>        | <span data-ttu-id="1660c-135">x</span><span class="sxs-lookup"><span data-stu-id="1660c-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="1660c-136">A költség és mennyiség összevonása</span><span class="sxs-lookup"><span data-stu-id="1660c-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="1660c-137">Az érték az **Érték** mezőben az alábbi értékek összessége:</span><span class="sxs-lookup"><span data-stu-id="1660c-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="1660c-138">Tényleges önköltségi érték</span><span class="sxs-lookup"><span data-stu-id="1660c-138">Physical cost amount</span></span>
    -   <span data-ttu-id="1660c-139">Pénzügyi költség összege</span><span class="sxs-lookup"><span data-stu-id="1660c-139">Financial cost amount</span></span>
    -   <span data-ttu-id="1660c-140">Kiigazítások</span><span class="sxs-lookup"><span data-stu-id="1660c-140">Adjustments</span></span>
-   <span data-ttu-id="1660c-141">Az érték a **Mennyiség** mezőben az alábbi értékek összessége:</span><span class="sxs-lookup"><span data-stu-id="1660c-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="1660c-142">Bevételezve</span><span class="sxs-lookup"><span data-stu-id="1660c-142">Received</span></span>
    -   <span data-ttu-id="1660c-143">Kiszállított</span><span class="sxs-lookup"><span data-stu-id="1660c-143">Deducted</span></span>
    -   <span data-ttu-id="1660c-144">Feladott mennyiség</span><span class="sxs-lookup"><span data-stu-id="1660c-144">Posted quantity</span></span>
-   <span data-ttu-id="1660c-145">Az **Átlagos egységenkénti költség** mező egy kiszámított mező.</span><span class="sxs-lookup"><span data-stu-id="1660c-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="1660c-146">Az értékét az **Érték** mező **Mennyiség** mezővel való elosztásával kapjuk meg.</span><span class="sxs-lookup"><span data-stu-id="1660c-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="1660c-147">**Megjegyzés**: A **Tényleges érték beszámítása** paraméter nem befolyásolja az előző számításokat.</span><span class="sxs-lookup"><span data-stu-id="1660c-147">**Note:** The \*\*Include physical value \*\*parameter has no effect on the preceding calculations.</span></span>

<a name="additional-resources"></a><span data-ttu-id="1660c-148">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1660c-148">Additional resources</span></span>
--------

[<span data-ttu-id="1660c-149">Termékdimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="1660c-149">Product dimension group</span></span>](https://technet.microsoft.com/library/aa499382.aspx)

[<span data-ttu-id="1660c-150">Tárolásidimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="1660c-150">Storage dimension group</span></span>](https://technet.microsoft.com/library/hh209317.aspx)

[<span data-ttu-id="1660c-151">Nyomonkövetésidimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="1660c-151">Tracking dimension group</span></span>](https://technet.microsoft.com/library/hh209465.aspx)

[<span data-ttu-id="1660c-152">Új vagy módosult elemek</span><span class="sxs-lookup"><span data-stu-id="1660c-152">What's new or changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)

[<span data-ttu-id="1660c-153">Költségbejegyzések</span><span class="sxs-lookup"><span data-stu-id="1660c-153">Cost entries</span></span>](cost-entries.md)



