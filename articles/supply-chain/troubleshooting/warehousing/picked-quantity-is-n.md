---
title: A kiválasztott mennyiség nem elegendő a szállítólevél létrehozása során
description: Amikor szállítólevelet hoz létre, a kimenő rakomány olyan kiválasztott mennyiséget tartalmaz, amely nem egyezik a rakomány sorában lévő munkamennyiséggel.
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
ms.openlocfilehash: fa6054dc26e4306ec16e37b0e6c320342ed40fe0
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249114"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a><span data-ttu-id="5a2fa-103">A kiválasztott mennyiség nem elegendő a szállítólevél létrehozása során</span><span class="sxs-lookup"><span data-stu-id="5a2fa-103">Picked quantity isn't sufficient during packing slip generation</span></span>

<span data-ttu-id="5a2fa-104">Hibakód: SYS54073</span><span class="sxs-lookup"><span data-stu-id="5a2fa-104">Error code: SYS54073</span></span>

## <a name="symptoms"></a><span data-ttu-id="5a2fa-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="5a2fa-105">Symptoms</span></span>

<span data-ttu-id="5a2fa-106">Amikor szállítólevelet hoz létre, a kimenő rakomány olyan kiválasztott mennyiséget tartalmaz, amely nem egyezik a rakomány sorában lévő munkamennyiséggel.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-106">When you generate a packing slip, the outbound load contains a picked quantity that doesn't match the created work quantity on the load line.</span></span>

<span data-ttu-id="5a2fa-107">Amikor megpróbál létrehozni egy szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="5a2fa-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="5a2fa-108">Mivel %1 lett tárolva, nem frissíthető %2, ha a fennmaradónak %3 értékűnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-108">As %1 have been picked, it is not sufficient to update %2, when, subsequently, the remainder must be %3.</span></span>

<span data-ttu-id="5a2fa-109">Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="5a2fa-110">Ok</span><span class="sxs-lookup"><span data-stu-id="5a2fa-110">Cause</span></span>

<span data-ttu-id="5a2fa-111">A szállítólevél nem hozható létre az adott állapotban, mert a következők valamelyike fennállhat:</span><span class="sxs-lookup"><span data-stu-id="5a2fa-111">The packing slip can't be generated in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="5a2fa-112">A kapcsolódó munkát még nem választották ki és nem helyezték át a végső szállítási helyre.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-112">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="5a2fa-113">A kitárolt munkamennyiség nem egyezik meg a rakománysor létrehozott munkamennyiségével.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-113">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="5a2fa-114">A rakománysorban lévő mennyiség, a munka létrehozott mennyisége és a kiválasztott mennyiség nem egyezik.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-114">The load line quantity, work created quantity, and picked quantity don't match.</span></span>

## <a name="resolution"></a><span data-ttu-id="5a2fa-115">Megoldás</span><span class="sxs-lookup"><span data-stu-id="5a2fa-115">Resolution</span></span>

<span data-ttu-id="5a2fa-116">A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-116">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="5a2fa-117">A probléma javításához végezze el a következő feladatok egyikét:</span><span class="sxs-lookup"><span data-stu-id="5a2fa-117">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="5a2fa-118">Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-118">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="5a2fa-119">Korrigálja a rakománysor mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-119">Adjust the load line quantity.</span></span>
- <span data-ttu-id="5a2fa-120">Sztornírozza az összes kiválasztási regisztrációt, és hajtsa végre újra a kiválasztást.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-120">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="5a2fa-121">Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek</span><span class="sxs-lookup"><span data-stu-id="5a2fa-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="5a2fa-122">Az alábbi módon ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="5a2fa-123">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="5a2fa-124">Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-124">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="5a2fa-125">A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="5a2fa-126">Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="5a2fa-127">A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="5a2fa-128">Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="5a2fa-129">Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="5a2fa-130">Korrigálja a rakománysor mennyiségét</span><span class="sxs-lookup"><span data-stu-id="5a2fa-130">Adjust the load line quantity</span></span>

<span data-ttu-id="5a2fa-131">Az alábbi módon korrigálja a rakománysor mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-131">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="5a2fa-132">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="5a2fa-133">Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="5a2fa-134">A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="5a2fa-135">A  **Rakománysorok** lapon válassza ki annak a cikknek rakománysorát, amely a hibát okozza.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-135">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="5a2fa-136">A kiválasztott mennyiség beállításához válassza a **Kitárolt mennyiség csökkentése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="5a2fa-137">Állítsa be úgy a **Rakománysor csökkentése** mezőt, hogy tükrözze a terhelési sor módosításait.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-137">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="5a2fa-138">Sztornírozza az összes kiválasztási regisztrációt, és hajtsa végre újra a kiválasztást</span><span class="sxs-lookup"><span data-stu-id="5a2fa-138">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="5a2fa-139">A probléma azért fordulhat elő, mert valaki a regisztráció kiválasztását használta arra, hogy munka nélkül lezárja a rakomány sorát.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-139">The issue might occur because someone used pick registration to close a load line without work.</span></span> <span data-ttu-id="5a2fa-140">Ebben az esetben sztornírozni kell a regisztráció kézi kiválasztását, és a kiválasztást a Warehouse Management mobilalkalmazással kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-140">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="5a2fa-141">A regisztráció kiválasztásának sztornírozásához használja a következő eljárást.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-141">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="5a2fa-142">Lépjen a **Kinnlevőségek \> Rendelések \> Minden rendelés** részre.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-142">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="5a2fa-143">Válassza ki azt az értékesítési rendelést, amelynél nem tud szállítólevelet feladni a rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-143">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="5a2fa-144">Az  **Értékesítési rendelés sorai** lapon válassza ki az értékesítési rendelési azon sorát, amelyhez a regisztráció kiválasztása történt.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-144">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="5a2fa-145">Válassza a **Sor frissítése \> Kitárolás** lehetőséget a kiválasztás visszavonásához.</span><span class="sxs-lookup"><span data-stu-id="5a2fa-145">Select **Update line \> Pick** to unpick the items.</span></span>
