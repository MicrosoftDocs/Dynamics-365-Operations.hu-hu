---
title: "Új bizományosi feltöltési rendelés létrehozása"
description: "Ez az eljárás bemutatja a bizományosi feltöltési rendelés létrehozását, ahol nyomon követhetők a várható szállítások egy szállítótól a bizományosi készletbe."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 6286e8f52b8131a8e4779f1e11d84233b8e0760e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/12/2017

---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="acb18-103">Új bizományosi feltöltési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="acb18-103">Create a consignment replenishment order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="acb18-104">Ez az eljárás bemutatja a bizományosi feltöltési rendelés létrehozását, ahol nyomon követhetők a várható szállítások egy szállítótól a bizományosi készletbe.</span><span class="sxs-lookup"><span data-stu-id="acb18-104">This procedure shows how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="acb18-105">Azt is bemutatja, hogyan lehet rögzíteni a termékek átvételét úgy, hogy a bizományosi készlet szállító tulajdonában levő aktuális készletként legyen regisztrálva.</span><span class="sxs-lookup"><span data-stu-id="acb18-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="acb18-106">Ezt az eljárást általában egy beszerzési szakember végzi el.</span><span class="sxs-lookup"><span data-stu-id="acb18-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="acb18-107">Ezt az útmutatót használhatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="acb18-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="acb18-108">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="acb18-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>




## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="acb18-109">Új bizományosi feltöltési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="acb18-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="acb18-110">Ugrás a Beszerzés és forrás > Bizományos > Bizományosi feltöltési rendelések elemre.</span><span class="sxs-lookup"><span data-stu-id="acb18-110">Go to Procurement and sourcing > Consignment > Consignment replenishment orders.</span></span>
2. <span data-ttu-id="acb18-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="acb18-111">Click New.</span></span>
3. <span data-ttu-id="acb18-112">Válassza az US-104 szállítót a Szállítói számla mezőben.</span><span class="sxs-lookup"><span data-stu-id="acb18-112">In the Vendor account field, select vendor US-104.</span></span>
    * <span data-ttu-id="acb18-113">Ki kell jelölnie egy szállítót, amelyik tulajdonosként van regisztrálva a Készlettulajdonosok lapon.</span><span class="sxs-lookup"><span data-stu-id="acb18-113">You must select a vendor that’s registered as an owner in the Inventory owners page.</span></span>  
4. <span data-ttu-id="acb18-114">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="acb18-114">Click OK.</span></span>
5. <span data-ttu-id="acb18-115">Kattintson az Új sor hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="acb18-115">Click Add line.</span></span>
6. <span data-ttu-id="acb18-116">A Cikkszám mezőbe írja be az M9211CI értéket.</span><span class="sxs-lookup"><span data-stu-id="acb18-116">In the Item number field, type M9211CI.</span></span>
    * <span data-ttu-id="acb18-117">Ki kell választania egy cikket, amelyik be van állítva a bizományosi készlethez.</span><span class="sxs-lookup"><span data-stu-id="acb18-117">You must select an item that is set up for consignment inventory.</span></span>  
7. <span data-ttu-id="acb18-118">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="acb18-118">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="acb18-119">Adjon meg egy dátumot a Kért kézbesítési dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="acb18-119">In the Requested delivery date field, enter a date.</span></span>
    * <span data-ttu-id="acb18-120">A kért és visszaigazolt dátumokat az MRP-kalkulátor használja az áruk várható beérkezéséhez.</span><span class="sxs-lookup"><span data-stu-id="acb18-120">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="acb18-121">Adjon meg egy dátumot a Visszaigazolt szállítási dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="acb18-121">In the Confirmed delivery date field, enter a date.</span></span>
10. <span data-ttu-id="acb18-122">Bontsa ki a Soradatok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="acb18-122">Expand the Line details section.</span></span>
11. <span data-ttu-id="acb18-123">Kattintson a Készlet dimenziók lapra.</span><span class="sxs-lookup"><span data-stu-id="acb18-123">Click the Inventory dimensions tab.</span></span>
12. <span data-ttu-id="acb18-124">A tulajdonos megjelenítéséhez a Készletdimenziók tulajdonos mezőjében, frissítse a lapot.</span><span class="sxs-lookup"><span data-stu-id="acb18-124">To show the owner in the Inventory dimensions owner field, refresh the page.</span></span>
    * <span data-ttu-id="acb18-125">A tulajdonosként most már a US-104 szállító szerepel.</span><span class="sxs-lookup"><span data-stu-id="acb18-125">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="acb18-126">Ellenőrizze a készlettranzakció állapotát.</span><span class="sxs-lookup"><span data-stu-id="acb18-126">Check the inventory transaction status</span></span>
1. <span data-ttu-id="acb18-127">Kattintson a Készlet parancsra.</span><span class="sxs-lookup"><span data-stu-id="acb18-127">Click Inventory.</span></span>
2. <span data-ttu-id="acb18-128">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="acb18-128">Click Transactions.</span></span>
3. <span data-ttu-id="acb18-129">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="acb18-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="acb18-130">Figyelje meg, hogy a Fogadás mező most már a Megrendelve értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="acb18-130">Notice that the Receipt field is set to Ordered.</span></span>  
4. <span data-ttu-id="acb18-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="acb18-131">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="acb18-132">Cikkek átvétele</span><span class="sxs-lookup"><span data-stu-id="acb18-132">Receive items</span></span>
1. <span data-ttu-id="acb18-133">Kattintson a Termékbevételezés elemre.</span><span class="sxs-lookup"><span data-stu-id="acb18-133">Click Product receipt.</span></span>
2. <span data-ttu-id="acb18-134">Írjon be egy értéket a Külső termékbevételezés mezőbe.</span><span class="sxs-lookup"><span data-stu-id="acb18-134">In the External product receipt field, type a value.</span></span>
3. <span data-ttu-id="acb18-135">A Mennyiség mezőben adjon meg egy számot, amely kisebb az ott látható számnál.</span><span class="sxs-lookup"><span data-stu-id="acb18-135">In the Quantity field, enter a number that’s lower than the number that’s shown there.</span></span>
4. <span data-ttu-id="acb18-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="acb18-136">Click OK.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="acb18-137">Ellenőrizze az aktuális készletet</span><span class="sxs-lookup"><span data-stu-id="acb18-137">Check the on-hand inventory</span></span>
1. <span data-ttu-id="acb18-138">Kattintson a Készlet parancsra.</span><span class="sxs-lookup"><span data-stu-id="acb18-138">Click Inventory.</span></span>
2. <span data-ttu-id="acb18-139">Kattintson az Aktuális készlet elemre.</span><span class="sxs-lookup"><span data-stu-id="acb18-139">Click On-hand.</span></span>
3. <span data-ttu-id="acb18-140">Kattintson az Áttekintés elemre.</span><span class="sxs-lookup"><span data-stu-id="acb18-140">Click Overview.</span></span>
    * <span data-ttu-id="acb18-141">A cikkek, amelyek a szállító tulajdonában álló bizományosi készletként érkeztek, aktuális készletként állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="acb18-141">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="acb18-142">A bizományosi feltöltési rendelés fennmaradó mennyisége a Megrendelve összesen mezőben jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="acb18-142">The remaining quantity on the consignment replenishment order is shown in the Ordered in total field.</span></span>  
4. <span data-ttu-id="acb18-143">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="acb18-143">Close the page.</span></span>
5. <span data-ttu-id="acb18-144">Kattintson a Bezárás gombra.</span><span class="sxs-lookup"><span data-stu-id="acb18-144">Click Close.</span></span>

