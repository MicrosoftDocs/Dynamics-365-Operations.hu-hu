---
title: A frissíteni próbált mennyiség meghaladja a kapott/leszállított mennyiséget.
description: Amikor szállítólevelet hoz létre, a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a kiválasztott és az értékesítési rendeléshez lefoglalt munkamennyiséget.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 66d9cd80cc61e00d1d88ab4f59d03054d746cdd9
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249115"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a><span data-ttu-id="aeddb-103">A frissíteni próbált mennyiség meghaladja a kapott/leszállított mennyiséget</span><span class="sxs-lookup"><span data-stu-id="aeddb-103">Quantity that you're trying to update exceeds the received/delivered quantity</span></span>

<span data-ttu-id="aeddb-104">Hibakód: SYS7676</span><span class="sxs-lookup"><span data-stu-id="aeddb-104">Error code: SYS7676</span></span>

## <a name="symptoms"></a><span data-ttu-id="aeddb-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="aeddb-105">Symptoms</span></span>

<span data-ttu-id="aeddb-106">Amikor szállítólevelet hoz létre, a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a kiválasztott és az értékesítési rendeléshez lefoglalt munkamennyiséget.</span><span class="sxs-lookup"><span data-stu-id="aeddb-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the work quantity that was picked and reserved for the sales order.</span></span>

<span data-ttu-id="aeddb-107">Amikor megpróbál létrehozni egy szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="aeddb-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="aeddb-108">A frissíteni kívánt mennyiség meghaladja a bevételezett/szállított mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="aeddb-108">The quantity that you are trying to update exceeds the quantity received/delivered.</span></span>

<span data-ttu-id="aeddb-109">Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="aeddb-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="aeddb-110">Ok</span><span class="sxs-lookup"><span data-stu-id="aeddb-110">Cause</span></span>

<span data-ttu-id="aeddb-111">A kitárolt munkamennyiség nem egyezik meg a rakománysor létrehozott munkamennyiségével.</span><span class="sxs-lookup"><span data-stu-id="aeddb-111">The picked work quantity doesn't match the created work quantity on the load line.</span></span> <span data-ttu-id="aeddb-112">Ez a probléma például akkor fordulhat elő, ha a rakománysorban lévő mennyiség, a munka létrehozott mennyisége vagy a kiválasztott mennyiség nem pontos.</span><span class="sxs-lookup"><span data-stu-id="aeddb-112">For example, this issue might occur if the load line quantity, work created quantity, or picked quantity isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="aeddb-113">Megoldás</span><span class="sxs-lookup"><span data-stu-id="aeddb-113">Resolution</span></span>

<span data-ttu-id="aeddb-114">A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="aeddb-114">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="aeddb-115">A probléma javításához végezze el a következő feladatok egyikét:</span><span class="sxs-lookup"><span data-stu-id="aeddb-115">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="aeddb-116">Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="aeddb-116">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="aeddb-117">Korrigálja a rakománysor mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="aeddb-117">Adjust the load line quantity.</span></span>
- <span data-ttu-id="aeddb-118">Sztornírozza az összes kiválasztási regisztrációt, és hajtsa végre újra a kiválasztást.</span><span class="sxs-lookup"><span data-stu-id="aeddb-118">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="aeddb-119">Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek</span><span class="sxs-lookup"><span data-stu-id="aeddb-119">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="aeddb-120">Az alábbi módon ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="aeddb-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="aeddb-121">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="aeddb-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="aeddb-122">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="aeddb-122">Select the load that the shipment can't be generated for.</span></span>
1. <span data-ttu-id="aeddb-123">A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aeddb-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="aeddb-124">Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="aeddb-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="aeddb-125">A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.</span><span class="sxs-lookup"><span data-stu-id="aeddb-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="aeddb-126">Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.</span><span class="sxs-lookup"><span data-stu-id="aeddb-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="aeddb-127">Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.</span><span class="sxs-lookup"><span data-stu-id="aeddb-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="aeddb-128">Korrigálja a rakománysor mennyiségét</span><span class="sxs-lookup"><span data-stu-id="aeddb-128">Adjust the load line quantity</span></span>

<span data-ttu-id="aeddb-129">Az alábbi módon korrigálja a rakománysor mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="aeddb-129">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="aeddb-130">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="aeddb-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="aeddb-131">Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="aeddb-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="aeddb-132">A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aeddb-132">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="aeddb-133">A  **Rakománysorok** lapon válassza ki annak a cikknek rakománysorát, amely a hibát okozza.</span><span class="sxs-lookup"><span data-stu-id="aeddb-133">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="aeddb-134">A kiválasztott mennyiség beállításához válassza a **Kitárolt mennyiség csökkentése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="aeddb-134">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="aeddb-135">Állítsa be úgy a **Rakománysor csökkentése** mezőt, hogy tükrözze a terhelési sor módosításait.</span><span class="sxs-lookup"><span data-stu-id="aeddb-135">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="aeddb-136">Sztornírozza az összes kiválasztási regisztrációt, és hajtsa végre újra a kiválasztást</span><span class="sxs-lookup"><span data-stu-id="aeddb-136">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="aeddb-137">Ha valaki regisztráció kiválasztásával zárt be egy munka nélküli rakománysort, akkor a rakománysorban lévő mennyiség és a kiválasztott mennyiség eltérhet.</span><span class="sxs-lookup"><span data-stu-id="aeddb-137">If someone used pick registration to close a load line without work, a discrepancy can occur between the load line quantity and the picked quantity.</span></span> <span data-ttu-id="aeddb-138">Ebben az esetben sztornírozni kell a regisztráció kézi kiválasztását, és a kiválasztást a Warehouse Management mobilalkalmazással kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="aeddb-138">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="aeddb-139">A regisztráció kiválasztásának sztornírozásához használja a következő eljárást.</span><span class="sxs-lookup"><span data-stu-id="aeddb-139">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="aeddb-140">Lépjen a **Kinnlevőségek \> Rendelések \> Minden rendelés** részre.</span><span class="sxs-lookup"><span data-stu-id="aeddb-140">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="aeddb-141">Válassza ki azt az értékesítési rendelést, amelynél nem tud szállítólevelet feladni a rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="aeddb-141">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="aeddb-142">Az  **Értékesítési rendelés sorai** lapon válassza ki az értékesítési rendelési azon sorát, amelyhez a regisztráció kiválasztása történt.</span><span class="sxs-lookup"><span data-stu-id="aeddb-142">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="aeddb-143">Válassza a **Sor frissítése \> Kitárolás** lehetőséget a kiválasztás visszavonásához.</span><span class="sxs-lookup"><span data-stu-id="aeddb-143">Select **Update line \> Pick** to unpick the items.</span></span>
