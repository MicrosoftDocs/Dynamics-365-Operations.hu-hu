---
title: " Termékcsomagok létrehozása beszerzési rendelések"
description: Ez az eljárás bemutatja, hogy hogyan hozhat létre termékcsomagot, illetve hogyan használhatja azt beszerzési rendelésen.
author: josaw1
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4c84c829ca1344d70dee294da35b659299d6fa37
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802719"
---
# <a name="create-product-packages-for-purchase-orders"></a><span data-ttu-id="83dd5-103"> Termékcsomagok létrehozása beszerzési rendelések</span><span class="sxs-lookup"><span data-stu-id="83dd5-103">Create product packages for purchase orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83dd5-104">Ez az eljárás bemutatja, hogy hogyan hozhat létre termékcsomagot, illetve hogyan használhatja azt beszerzési rendelésen.</span><span class="sxs-lookup"><span data-stu-id="83dd5-104">This procedure walks through creating a product package and using it on a purchase order.</span></span> <span data-ttu-id="83dd5-105">A beszerzési rendelés egy előre meghatározott termékköre vonatkozó megrendeléshez használható.</span><span class="sxs-lookup"><span data-stu-id="83dd5-105">The purchase order will be used to create an order for a pre-defined set of products.</span></span> <span data-ttu-id="83dd5-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="83dd5-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-product-package"></a><span data-ttu-id="83dd5-107">Termékcsomag létrehozása</span><span class="sxs-lookup"><span data-stu-id="83dd5-107">Create a product package</span></span>
1. <span data-ttu-id="83dd5-108">Ugrás a következőhöz: Kiskereskedelem és kereskedelem > Készletkezelés > Feltöltés > Termékcsomagok.</span><span class="sxs-lookup"><span data-stu-id="83dd5-108">Go to Retail and Commerce > Inventory management > Replenishment > Product packages.</span></span>
2. <span data-ttu-id="83dd5-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83dd5-109">Click New.</span></span>
3. <span data-ttu-id="83dd5-110">Írjon be egy értéket a Csomagszám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="83dd5-110">In the Package number field, type a value.</span></span>
4. <span data-ttu-id="83dd5-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="83dd5-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="83dd5-112">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="83dd5-112">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="83dd5-113">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="83dd5-114">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-114">Click Add.</span></span>
8. <span data-ttu-id="83dd5-115">A cikkszám mezőbe írja be a „0160” értéket.</span><span class="sxs-lookup"><span data-stu-id="83dd5-115">In the Item number field, type '0160'.</span></span>
9. <span data-ttu-id="83dd5-116">A Méret mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="83dd5-116">In the Size field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="83dd5-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="83dd5-118">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="83dd5-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="83dd5-119">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-119">Click Add.</span></span>
13. <span data-ttu-id="83dd5-120">A cikkszám mezőbe írja be a „0160” értéket.</span><span class="sxs-lookup"><span data-stu-id="83dd5-120">In the Item number field, type '0160'.</span></span>
14. <span data-ttu-id="83dd5-121">A Változatszám mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="83dd5-121">In the Variant number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="83dd5-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="83dd5-123">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="83dd5-123">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="83dd5-124">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-124">Click Add.</span></span>
18. <span data-ttu-id="83dd5-125">A cikkszám mezőbe írja be a „0175” értéket.</span><span class="sxs-lookup"><span data-stu-id="83dd5-125">In the Item number field, type '0175'.</span></span>
19. <span data-ttu-id="83dd5-126">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="83dd5-126">In the Quantity field, enter a number.</span></span>
20. <span data-ttu-id="83dd5-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-127">Click Save.</span></span>
21. <span data-ttu-id="83dd5-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="83dd5-128">Close the page.</span></span>

## <a name="add-package-to-purchase-order"></a><span data-ttu-id="83dd5-129">Csomag hozzáadása beszerzési rendeléshez</span><span class="sxs-lookup"><span data-stu-id="83dd5-129">Add package to purchase order</span></span>
1. <span data-ttu-id="83dd5-130">Nyissa meg a következőt: Kötelezettségek > Beszerzési rendelések > Minden beszerzési rendelés.</span><span class="sxs-lookup"><span data-stu-id="83dd5-130">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="83dd5-131">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83dd5-131">Click New.</span></span>
3. <span data-ttu-id="83dd5-132">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="83dd5-132">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="83dd5-133">Szállító kiválasztása esetén a listából azt a szállítót válassza ki, amely kapcsán a termékcsomagot korábban létrehozták.</span><span class="sxs-lookup"><span data-stu-id="83dd5-133">In the list, select the same vendor that the product package was previously created for, if a vendor was selected.</span></span>
5. <span data-ttu-id="83dd5-134">Az Általános szakasz bővítésének átváltása.</span><span class="sxs-lookup"><span data-stu-id="83dd5-134">Toggle the expansion of the General section.</span></span>
6. <span data-ttu-id="83dd5-135">A Hely mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="83dd5-135">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="83dd5-136">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-136">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="83dd5-137">A Raktár mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="83dd5-137">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="83dd5-138">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-138">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="83dd5-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-139">Click OK.</span></span>
11. <span data-ttu-id="83dd5-140">Bontsa ki a Sorok részletei részt.</span><span class="sxs-lookup"><span data-stu-id="83dd5-140">Toggle the expansion of the Line details section.</span></span>
12. <span data-ttu-id="83dd5-141">Kattintson a Termékcsomag fülre.</span><span class="sxs-lookup"><span data-stu-id="83dd5-141">Click the Product packages tab.</span></span>
13. <span data-ttu-id="83dd5-142">Kattintson a Beszerzési-rendelés sorra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-142">Click Purchase order line.</span></span>
14. <span data-ttu-id="83dd5-143">Kattintson a Sorok létrehozása csomagból elemre.</span><span class="sxs-lookup"><span data-stu-id="83dd5-143">Click Create lines from package.</span></span>
15. <span data-ttu-id="83dd5-144">A listában keresse meg és válassza az előző lépésben létrehozott termékcsomagot.</span><span class="sxs-lookup"><span data-stu-id="83dd5-144">In the list, find and select the product package created in previous step.</span></span>
16. <span data-ttu-id="83dd5-145">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="83dd5-145">In the Quantity field, enter a number.</span></span>
17. <span data-ttu-id="83dd5-146">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="83dd5-146">Click Create.</span></span>
18. <span data-ttu-id="83dd5-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="83dd5-147">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]