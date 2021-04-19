---
title: Alaptermék létrehozása
description: Hozzon létre egy alapterméket az előre megadott változatokhoz.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 70008e903763fff35c6cff12c42396fe5fcabbee
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832082"
---
# <a name="create-a-product-master"></a><span data-ttu-id="abe41-103">Alaptermék létrehozása</span><span class="sxs-lookup"><span data-stu-id="abe41-103">Create a product master</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="abe41-104">Hozzon létre egy alapterméket az előre megadott változatokhoz.</span><span class="sxs-lookup"><span data-stu-id="abe41-104">Create a product master for the predefined variants.</span></span> <span data-ttu-id="abe41-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="abe41-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="abe41-106">Ezt az eljárást a terméktervező használja.</span><span class="sxs-lookup"><span data-stu-id="abe41-106">This procedure is intended for the product designer.</span></span>


## <a name="create-a-new-product-master"></a><span data-ttu-id="abe41-107">Új alaptermék létrehozása</span><span class="sxs-lookup"><span data-stu-id="abe41-107">Create a new product master</span></span>
1. <span data-ttu-id="abe41-108">Válassza a **Navigációs ablaktábla > Modulok > Termékinformációk kezelése > Termékek > Alaptermékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="abe41-108">Go to **Navigation pane > Modules > Product information management > Products > Product masters**.</span></span>
2. <span data-ttu-id="abe41-109">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="abe41-109">Click **New**.</span></span>
3. <span data-ttu-id="abe41-110">Írjon be egy értéket a **Termékszám** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="abe41-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="abe41-111">A számnak egyedinek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="abe41-111">The number must be unique.</span></span> <span data-ttu-id="abe41-112">Egy számsorozat állítható be a **Termékszám** mezőben.</span><span class="sxs-lookup"><span data-stu-id="abe41-112">A number sequence can be set for the **Product number** field.</span></span> <span data-ttu-id="abe41-113">Ebben az esetben a felhasználónak nem kell megadnia értéket.</span><span class="sxs-lookup"><span data-stu-id="abe41-113">In this case, the user doesn't have to enter a value.</span></span>
4. <span data-ttu-id="abe41-114">Írjon be egy értéket a **Terméknév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="abe41-114">In the **Product name** field, type a value.</span></span> <span data-ttu-id="abe41-115">Írjon be egy jól érthető terméknevet.</span><span class="sxs-lookup"><span data-stu-id="abe41-115">Enter a descriptive product name.</span></span> <span data-ttu-id="abe41-116">Az alapértelmezett érték a keresési név, de ez módosítható a felhasználó által.</span><span class="sxs-lookup"><span data-stu-id="abe41-116">The value defaults to the search name, but this can be changed by the user.</span></span>
5. <span data-ttu-id="abe41-117">A **Termékdimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="abe41-117">In the **Product dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="abe41-118">A termékdimenzió-csoport határozza meg, hogy a 4 termékdimenzió melyike használható termékváltozatok létrehozására.</span><span class="sxs-lookup"><span data-stu-id="abe41-118">The product dimension group determines which of the 4 product dimensions that can be used to create product variants.</span></span> <span data-ttu-id="abe41-119">Ez a példa egy mérettel és színnel rendelkező csoportot használ.</span><span class="sxs-lookup"><span data-stu-id="abe41-119">This example uses a group with color and size.</span></span>
6. <span data-ttu-id="abe41-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="abe41-120">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="abe41-121">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="abe41-121">In the list, click the link in the selected row.</span></span> <span data-ttu-id="abe41-122">Az alapértelmezett **Konfigurációs technológia** az „Előre megadott” változat.</span><span class="sxs-lookup"><span data-stu-id="abe41-122">The default **Configuration technology** is 'Predefined variant'.</span></span> <span data-ttu-id="abe41-123">Ebben a példában ezt használjuk.</span><span class="sxs-lookup"><span data-stu-id="abe41-123">This will be used for this example.</span></span>
8. <span data-ttu-id="abe41-124">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="abe41-124">Click **OK**.</span></span>

## <a name="select-product-dimension-groups"></a><span data-ttu-id="abe41-125">Termékdimenzió-csoportok kiválasztása</span><span class="sxs-lookup"><span data-stu-id="abe41-125">Select product dimension groups</span></span>
1. <span data-ttu-id="abe41-126">A **Színcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="abe41-126">In the **Color group** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="abe41-127">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="abe41-127">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="abe41-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="abe41-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="abe41-129">A **Méretcsoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="abe41-129">In the **Size group** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="abe41-130">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="abe41-130">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="abe41-131">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="abe41-131">In the list, click the link in the selected row.</span></span>

## <a name="add-dimension-groups"></a><span data-ttu-id="abe41-132">Dimenziócsoportok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="abe41-132">Add dimension groups</span></span>
1. <span data-ttu-id="abe41-133">A **Műveleti panel** modulon kattintson a **Termék** elemre.</span><span class="sxs-lookup"><span data-stu-id="abe41-133">On the **Action Pane**, click **Product**.</span></span>
2. <span data-ttu-id="abe41-134">A **Méretcsoportok** gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="abe41-134">Click **Dimension groups** to open the drop dialog.</span></span>
3. <span data-ttu-id="abe41-135">A **Tárolási dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="abe41-135">In the **Storage dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="abe41-136">A tárolási dimenziók segítenek a cikkek raktárban való tárolásának és raktárból való kivételének szabályozásában.</span><span class="sxs-lookup"><span data-stu-id="abe41-136">The storage dimensions help you control how items are stored and taken from inventory.</span></span> <span data-ttu-id="abe41-137">Például a tárolási dimenzió magában foglalhatja a Helyet és a Raktárt.</span><span class="sxs-lookup"><span data-stu-id="abe41-137">For example, a storage dimension can include Site and Warehouse.</span></span>
4. <span data-ttu-id="abe41-138">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="abe41-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="abe41-139">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="abe41-139">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="abe41-140">A **Nyomon követési dimenzió csoport** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="abe41-140">In the **Tracking dimension group** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="abe41-141">A nyomon követési dimenziócsoport meghatározza, hogy mely nyomon követési dimenziókat adhatja hozzá egy termékhez.</span><span class="sxs-lookup"><span data-stu-id="abe41-141">The tracking dimension group determines which tracking dimensions you can add to a product.</span></span> <span data-ttu-id="abe41-142">Például a kötegszám, és a sorozatszám is használható a készletcikkek nyomon követésére.</span><span class="sxs-lookup"><span data-stu-id="abe41-142">For example, the batch number and serial number are used to track inventory items.</span></span>
7. <span data-ttu-id="abe41-143">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="abe41-143">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="abe41-144">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="abe41-144">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="abe41-145">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="abe41-145">Click **OK**.</span></span>
10. <span data-ttu-id="abe41-146">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="abe41-146">Click **Save**.</span></span>
11. <span data-ttu-id="abe41-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="abe41-147">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]