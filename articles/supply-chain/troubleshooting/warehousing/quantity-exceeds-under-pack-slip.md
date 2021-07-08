---
title: A szállítólevél létrehozása során a mennyiség meghaladja a szállítási hiány arányát
description: A szállítólevél létrehozásakor a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a szállítási hiány százalékos arányát.
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
ms.openlocfilehash: ecdd377d12faf40f64736e93671dcf42ff132403
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249110"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="484cf-103">A szállítólevél létrehozása során a mennyiség meghaladja a szállítási hiány arányát</span><span class="sxs-lookup"><span data-stu-id="484cf-103">Quantity exceeds under-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="484cf-104">Hibakód: SYS24921</span><span class="sxs-lookup"><span data-stu-id="484cf-104">Error code: SYS24921</span></span>

## <a name="symptoms"></a><span data-ttu-id="484cf-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="484cf-105">Symptoms</span></span>

<span data-ttu-id="484cf-106">A szállítólevél létrehozásakor a kimenő rakomány olyan mennyiséget tartalmaz, amely meghaladja a szállítási hiány százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="484cf-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the under-delivery percentage.</span></span>

<span data-ttu-id="484cf-107">Amikor megpróbál létrehozni egy szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="484cf-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="484cf-108">A sor alulszállítása %1 százalék, de csak %2 százalékos alulszállítás megengedett.</span><span class="sxs-lookup"><span data-stu-id="484cf-108">Underdelivery of line is %1 percent, but the allowed underdelivery is only %2 percent.</span></span>

<span data-ttu-id="484cf-109">Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="484cf-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="484cf-110">Ok</span><span class="sxs-lookup"><span data-stu-id="484cf-110">Cause</span></span>

<span data-ttu-id="484cf-111">A rakomány vagy a szállítmány kiválasztott mennyisége kisebb, mint a megrendelt mennyiség, és a szállítási hiány százalékos tartományán kívül esik.</span><span class="sxs-lookup"><span data-stu-id="484cf-111">The picked quantity for the load or shipment is less than the ordered quantity and isn't within the range of the under-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="484cf-112">Megoldás</span><span class="sxs-lookup"><span data-stu-id="484cf-112">Resolution</span></span>

<span data-ttu-id="484cf-113">A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="484cf-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="484cf-114">A probléma javításához végezze el a következő feladatok egyikét:</span><span class="sxs-lookup"><span data-stu-id="484cf-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="484cf-115">Korrigálja a szállítási hiány százalékos értékét.</span><span class="sxs-lookup"><span data-stu-id="484cf-115">Adjust the under-delivery percentage.</span></span>
- <span data-ttu-id="484cf-116">Sztornírozzon, és végezzen kiigazításokat.</span><span class="sxs-lookup"><span data-stu-id="484cf-116">Reverse and make adjustments.</span></span>

### <a name="adjust-the-under-delivery-percentage"></a><span data-ttu-id="484cf-117">Korrigálja a szállítási hiány százalékos értékét</span><span class="sxs-lookup"><span data-stu-id="484cf-117">Adjust the under-delivery percentage</span></span>

<span data-ttu-id="484cf-118">Az alábbi módon korrigálja a szállítási hiány százalékos értékét.</span><span class="sxs-lookup"><span data-stu-id="484cf-118">Use the following procedure to adjust the under-delivery percentage.</span></span>

1. <span data-ttu-id="484cf-119">Lépjen a **Kinnlevőségek \> Rendelések \> Minden rendelés** részre.</span><span class="sxs-lookup"><span data-stu-id="484cf-119">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="484cf-120">Válassza ki azt az értékesítési rendelést, amelynél nem tud szállítólevelet feladni a rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="484cf-120">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="484cf-121">Az  **Értékesítési rendelés sorai** lapon válassza ki az értékesítési rendelésnek azt a sorát, amely meghaladja a szállítási hiány százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="484cf-121">On the **Sales order lines** tab, select the sales order line for the item that exceeds the under-delivery percentage.</span></span>
1. <span data-ttu-id="484cf-122">A  **Sor részletei** lapon válassza ki a **Szállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="484cf-122">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="484cf-123">A **Szállítási hiány** mezőben állítson be olyan, nagyobb százalékértéket, amely megfelelő a rakománymennyiséggel szemben kitárolt mennyiségnek; így a rendszer létre tudja hozni a szállítólevelet.</span><span class="sxs-lookup"><span data-stu-id="484cf-123">Set the **Underdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="484cf-124">Sztornírozzon, és végezzen kiigazításokat</span><span class="sxs-lookup"><span data-stu-id="484cf-124">Reverse and make adjustments</span></span>

<span data-ttu-id="484cf-125">A rakományhoz feladott minden részletet (például a szállítólevelet, a szállítás visszaigazolását, a munkát) sztornírozzon, helyesbítse az értékesítési rendelést, adja ki újra a rendelést a raktárba, és zárja le a szállítási folyamatot.</span><span class="sxs-lookup"><span data-stu-id="484cf-125">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="484cf-126">Az alábbi módon érvénytelenítse a szállítólevelet.</span><span class="sxs-lookup"><span data-stu-id="484cf-126">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="484cf-127">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="484cf-127">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="484cf-128">A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítólevelek érvénytelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="484cf-128">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="484cf-129">Az alábbi módon sztornírozza a szállítmányok visszaigazolását.</span><span class="sxs-lookup"><span data-stu-id="484cf-129">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="484cf-130">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="484cf-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="484cf-131">A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="484cf-131">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="484cf-132">A munkák az alábbi módon sztornírozahtók.</span><span class="sxs-lookup"><span data-stu-id="484cf-132">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="484cf-133">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="484cf-133">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="484cf-134">A Művelet ablaktábla  **Rakományok** lapjának  **Munka** csoportjában válassza a  **Munka sztornírozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="484cf-134">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
