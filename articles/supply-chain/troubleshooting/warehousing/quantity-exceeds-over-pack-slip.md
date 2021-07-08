---
title: A szállítólevél létrehozása során a mennyiség meghaladja a túlszállítás arányát
description: A szállítólevél létrehozásakor a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a túlszállítás százalékos arányát.
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
ms.openlocfilehash: 1106322cc3772c1b671b7fa82fb74039c028ba35
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249112"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="b7745-103">A szállítólevél létrehozása során a mennyiség meghaladja a túlszállítás arányát</span><span class="sxs-lookup"><span data-stu-id="b7745-103">Quantity exceeds over-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="b7745-104">Hibakód: SYS24920</span><span class="sxs-lookup"><span data-stu-id="b7745-104">Error code: SYS24920</span></span>

## <a name="symptoms"></a><span data-ttu-id="b7745-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="b7745-105">Symptoms</span></span>

<span data-ttu-id="b7745-106">A szállítólevél létrehozásakor a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a túlszállítás százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="b7745-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the over-delivery percentage.</span></span>

<span data-ttu-id="b7745-107">Amikor megpróbál létrehozni egy szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="b7745-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="b7745-108">A sor túlszállítása %1 százalék, de csak %2 százalékos túlszállítás megengedett.</span><span class="sxs-lookup"><span data-stu-id="b7745-108">Overdelivery of line is %1 percent, but the allowed overdelivery is only %2 percent.</span></span>

<span data-ttu-id="b7745-109">Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="b7745-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="b7745-110">Ok</span><span class="sxs-lookup"><span data-stu-id="b7745-110">Cause</span></span>

<span data-ttu-id="b7745-111">A rakomány vagy a szállítmány kiválasztott mennyisége nagyobb, mint a megrendelt mennyiség, és a túlszállítás százalékos tartományán kívül esik.</span><span class="sxs-lookup"><span data-stu-id="b7745-111">The picked quantity for the load or shipment is more than the ordered quantity and isn't within the range of the over-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="b7745-112">Megoldás</span><span class="sxs-lookup"><span data-stu-id="b7745-112">Resolution</span></span>

<span data-ttu-id="b7745-113">A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="b7745-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="b7745-114">A probléma javításához végezze el a következő feladatok egyikét:</span><span class="sxs-lookup"><span data-stu-id="b7745-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="b7745-115">Korrigálja a rakománysor mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="b7745-115">Adjust the load line quantity.</span></span>
- <span data-ttu-id="b7745-116">Korrigálja a túlszállítás százalékos értékét.</span><span class="sxs-lookup"><span data-stu-id="b7745-116">Adjust the over-delivery percentage.</span></span>
- <span data-ttu-id="b7745-117">Sztornírozzon, és végezzen kiigazításokat.</span><span class="sxs-lookup"><span data-stu-id="b7745-117">Reverse and make adjustments.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="b7745-118">Korrigálja a rakománysor mennyiségét</span><span class="sxs-lookup"><span data-stu-id="b7745-118">Adjust the load line quantity</span></span>

<span data-ttu-id="b7745-119">Az alábbi módon korrigálja a rakománysor mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="b7745-119">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="b7745-120">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="b7745-120">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="b7745-121">Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="b7745-121">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="b7745-122">A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b7745-122">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="b7745-123">A  **Rakománysorok** lapon válassza ki annak a cikknek rakománysorát, amely meghaladja a túlszállítás százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="b7745-123">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="b7745-124">A kiválasztott mennyiség beállításához válassza a **Kitárolt mennyiség csökkentése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b7745-124">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="b7745-125">A  **Sor részletei** lapon válassza ki a **Rendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b7745-125">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="b7745-126">A **Mennyiség** mezőben állítsa be a kitárolt mennyiség értékét (azaz a **Munka létrehozott mennyisége** mező értékét), hogy a szállítólevél létrehozása elvégezhető legyen.</span><span class="sxs-lookup"><span data-stu-id="b7745-126">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="adjust-the-over-delivery-percentage"></a><span data-ttu-id="b7745-127">Korrigálja a túlszállítás százalékos értékét</span><span class="sxs-lookup"><span data-stu-id="b7745-127">Adjust the over-delivery percentage</span></span>

<span data-ttu-id="b7745-128">Az alábbi módon korrigálja a túlszállítás százalékos értékét.</span><span class="sxs-lookup"><span data-stu-id="b7745-128">Use the following procedure to adjust the over-delivery percentage.</span></span>

1. <span data-ttu-id="b7745-129">Lépjen a **Kinnlevőségek \> Rendelések \> Minden rendelés** részre.</span><span class="sxs-lookup"><span data-stu-id="b7745-129">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="b7745-130">Válassza ki azt az értékesítési rendelést, amelynél nem tud szállítólevelet feladni a rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="b7745-130">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="b7745-131">Az  **Értékesítési rendelés sorai** lapon válassza ki az értékesítési rendelésnek azt a sorát, amely meghaladja a túlszállítás százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="b7745-131">On the **Sales order lines** tab, select the sales order line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="b7745-132">A  **Sor részletei** lapon válassza ki a **Szállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b7745-132">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="b7745-133">A **Túlszállítás** mezőben állítson be olyan, nagyobb százalékértéket, amely megfelelő a rakománymennyiséggel szemben kitárolt mennyiségnek; így a rendszer létre tudja hozni a szállítólevelet.</span><span class="sxs-lookup"><span data-stu-id="b7745-133">Set the **Overdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="b7745-134">Sztornírozzon, és végezzen kiigazításokat</span><span class="sxs-lookup"><span data-stu-id="b7745-134">Reverse and make adjustments</span></span>

<span data-ttu-id="b7745-135">A rakományhoz feladott minden részletet (például a szállítólevelet, a szállítás visszaigazolását, a munkát) sztornírozzon, helyesbítse az értékesítési rendelést, adja ki újra a rendelést a raktárba, és zárja le a szállítási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="b7745-135">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="b7745-136">Az alábbi módon érvénytelenítse a szállítólevelet.</span><span class="sxs-lookup"><span data-stu-id="b7745-136">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="b7745-137">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="b7745-137">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="b7745-138">A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítólevelek érvénytelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b7745-138">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="b7745-139">Az alábbi módon sztornírozza a szállítmányok visszaigazolását.</span><span class="sxs-lookup"><span data-stu-id="b7745-139">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="b7745-140">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="b7745-140">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="b7745-141">A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b7745-141">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="b7745-142">A munkák az alábbi módon sztornírozahtók.</span><span class="sxs-lookup"><span data-stu-id="b7745-142">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="b7745-143">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="b7745-143">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="b7745-144">A Művelet ablaktábla  **Rakományok** lapjának  **Munka** csoportjában válassza a  **Munka sztornírozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b7745-144">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
