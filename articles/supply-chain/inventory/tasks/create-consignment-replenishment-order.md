---
title: Új bizományosi feltöltési rendelés létrehozása
description: Ez a témakör bemutatja a bizományosi feltöltési rendelés létrehozását, ahol nyomon követhetők a várható szállítások egy szállítótól a bizományosi készletbe.
author: mkirknel
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e993190150e2d82088390d8db4b7c5ada2b0161
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018353"
---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="a7d18-103">Új bizományosi feltöltési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="a7d18-103">Create a consignment replenishment order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a7d18-104">Ez a témakör bemutatja a bizományosi feltöltési rendelés létrehozását, ahol nyomon követhetők a várható szállítások egy szállítótól a bizományosi készletbe.</span><span class="sxs-lookup"><span data-stu-id="a7d18-104">This topic explains how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="a7d18-105">Azt is bemutatja, hogyan lehet rögzíteni a termékek átvételét úgy, hogy a bizományosi készlet szállító tulajdonában levő aktuális készletként legyen regisztrálva.</span><span class="sxs-lookup"><span data-stu-id="a7d18-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="a7d18-106">Ezt az eljárást általában egy beszerzési szakember végzi el.</span><span class="sxs-lookup"><span data-stu-id="a7d18-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="a7d18-107">Ezt az útmutatót használhatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="a7d18-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="a7d18-108">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="a7d18-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="a7d18-109">Új bizományosi feltöltési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="a7d18-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="a7d18-110">Navigációs ablaktáblán ugorjon a **Modulok > Beszerzés és forrás > Szállítás > Bizományosi feltöltési rendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="a7d18-110">In the navigation pane, go to **Modules > Procurement and sourcing > Consignment > Consignment replenishment orders**.</span></span>
2. <span data-ttu-id="a7d18-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7d18-111">Select **New**.</span></span>
3. <span data-ttu-id="a7d18-112">Válassza ki a **Szállítói számla** mezőben az **US-104** szállítót (tulajdonosként bejegyzett szállítót kell kiválasztani a **készlet tulajdonosai** lapon).</span><span class="sxs-lookup"><span data-stu-id="a7d18-112">In the **Vendor account** field, select vendor **US-104** (you must select a vendor that's registered as an owner in the **inventory owners** page).</span></span> 
4. <span data-ttu-id="a7d18-113">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7d18-113">Select **OK**.</span></span>
5. <span data-ttu-id="a7d18-114">Válassza a **Sor hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7d18-114">Select **Add line**.</span></span>
6. <span data-ttu-id="a7d18-115">Írja be a **cikkszám** mezőbe ezt: `M9211CI` (ki kell választania egy olyan elemet, amely be van állítva a szállítmány készletéhez).</span><span class="sxs-lookup"><span data-stu-id="a7d18-115">In the **Item number** field, type `M9211CI` (you must select an item that is set up for consignment inventory).</span></span>
7. <span data-ttu-id="a7d18-116">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7d18-116">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="a7d18-117">Adjon meg egy dátumot a **Kért kézbesítési dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7d18-117">In the **Requested delivery date** field, enter a date.</span></span> <span data-ttu-id="a7d18-118">A kért és visszaigazolt dátumokat az MRP-kalkulátor használja az áruk várható beérkezéséhez.</span><span class="sxs-lookup"><span data-stu-id="a7d18-118">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="a7d18-119">Adjon meg egy dátumot a **Visszaigazolt szállítási dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a7d18-119">In the **Confirmed delivery date** field, enter a date.</span></span>
10. <span data-ttu-id="a7d18-120">Bontsa ki a **Sorrészletek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a7d18-120">Expand the **Line details** section.</span></span>
11. <span data-ttu-id="a7d18-121">Válassza a **Készletdimenziók** lapot.</span><span class="sxs-lookup"><span data-stu-id="a7d18-121">Select the **Inventory dimensions** tab.</span></span>
12. <span data-ttu-id="a7d18-122">A tulajdonos megjelenítéséhez a **Készletdimenziók tulajdonos** mezőjében, frissítse a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7d18-122">To show the owner in the **Inventory dimensions owner** field, refresh the page.</span></span> <span data-ttu-id="a7d18-123">A tulajdonosként most már a US-104 szállító szerepel.</span><span class="sxs-lookup"><span data-stu-id="a7d18-123">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="a7d18-124">Ellenőrizze a készlettranzakció állapotát.</span><span class="sxs-lookup"><span data-stu-id="a7d18-124">Check the inventory transaction status</span></span>
1. <span data-ttu-id="a7d18-125">Válassza a **Készlet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7d18-125">Select **Inventory**.</span></span>
2. <span data-ttu-id="a7d18-126">Válassza a **Tranzakciók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7d18-126">Select **Transactions**.</span></span>
3. <span data-ttu-id="a7d18-127">A kívánt sorban figyelje meg, hogy a **Fogadás** mező most már a **Megrendelve** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="a7d18-127">In the desired row, notice that the **Receipt** field is set to **Ordered**.</span></span>  
4. <span data-ttu-id="a7d18-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7d18-128">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="a7d18-129">Cikkek átvétele</span><span class="sxs-lookup"><span data-stu-id="a7d18-129">Receive items</span></span>
1. <span data-ttu-id="a7d18-130">Válassza ki a **Termékbevételezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a7d18-130">Select **Product receipt**.</span></span>
2. <span data-ttu-id="a7d18-131">Írjon be egy értéket a **Külső termékbevételezés** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a7d18-131">In the **External product receipt** field, type a value.</span></span>
3. <span data-ttu-id="a7d18-132">A **Mennyiség** mezőben adjon meg egy számot, amely kisebb az ott látható számnál.</span><span class="sxs-lookup"><span data-stu-id="a7d18-132">In the **Quantity** field, enter a number that's lower than the number that's shown there.</span></span> 
4. <span data-ttu-id="a7d18-133">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7d18-133">Select **OK**.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="a7d18-134">Ellenőrizze az aktuális készletet</span><span class="sxs-lookup"><span data-stu-id="a7d18-134">Check the on-hand inventory</span></span>
1. <span data-ttu-id="a7d18-135">Válassza a **Készlet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7d18-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="a7d18-136">Válassza az **Aktuális készlet** elemet.</span><span class="sxs-lookup"><span data-stu-id="a7d18-136">Select **On-hand**.</span></span>
3. <span data-ttu-id="a7d18-137">Válassza az **Áttekintés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a7d18-137">Select **Overview**.</span></span> <span data-ttu-id="a7d18-138">A cikkek, amelyek a szállító tulajdonában álló bizományosi készletként érkeztek, aktuális készletként állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="a7d18-138">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="a7d18-139">A bizományosi feltöltési rendelés fennmaradó mennyisége a **Megrendelve összesen** mezőben jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a7d18-139">The remaining quantity on the consignment replenishment order is shown in the **Ordered in total** field.</span></span>  
4. <span data-ttu-id="a7d18-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7d18-140">Close the page.</span></span>

