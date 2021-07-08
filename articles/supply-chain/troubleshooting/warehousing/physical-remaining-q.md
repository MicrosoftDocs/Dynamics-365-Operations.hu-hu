---
title: Az egységben maradó fizikai mennyiség nem lehet nulla
description: Amikor szállítólevelet hoz létre, a hozzá megadott adatok nem nulla készletmennyiséget, hanem nulla értékesítési mennyiséget jelentenek.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bfd381160bcfd1e6e5489e16cc22178b8a5142ee
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248784"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a><span data-ttu-id="39c8f-103">Az egységben maradó fizikai mennyiség nem lehet nulla</span><span class="sxs-lookup"><span data-stu-id="39c8f-103">Physical remaining quantity in the unit must not be zero</span></span>

<span data-ttu-id="39c8f-104">Hibakód: SYS19591</span><span class="sxs-lookup"><span data-stu-id="39c8f-104">Error code: SYS19591</span></span>

## <a name="symptoms"></a><span data-ttu-id="39c8f-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="39c8f-105">Symptoms</span></span>

<span data-ttu-id="39c8f-106">Amikor szállítólevelet hoz létre, a hozzá megadott adatok nem nulla készletmennyiséget, hanem nulla értékesítési mennyiséget jelentenek.</span><span class="sxs-lookup"><span data-stu-id="39c8f-106">When you generate a packing slip, the data that is supplied to it has a non-zero inventory quantity but a zero sales quantity.</span></span>

<span data-ttu-id="39c8f-107">Amikor megpróbálja létrehozni a szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="39c8f-107">When you try to generate the packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="39c8f-108">A tényleges fennmaradó mennyiség a(z) %1 egységben nem lehet nulla.</span><span class="sxs-lookup"><span data-stu-id="39c8f-108">Physical remaining quantity in the unit %1 must be other than zero.</span></span>

<span data-ttu-id="39c8f-109">Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="39c8f-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="39c8f-110">Ok</span><span class="sxs-lookup"><span data-stu-id="39c8f-110">Cause</span></span>

<span data-ttu-id="39c8f-111">A rendszer kiértékeli a készletegységben maradó fizikai mennyiséget, illetve a szállítási egységben maradó fizikai mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="39c8f-111">The system evaluates the physical remaining quantity in the inventory unit and the physical remaining quantity in the shipping unit.</span></span> <span data-ttu-id="39c8f-112">Ha a rendszer azt állapítja meg, hogy a szállítási egységben maradó fizikai mennyiség 0 (nulla), de a készletegységben maradó fizikai mennyiség nem 0, akkor nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="39c8f-112">If the system finds that the physical remaining quantity in the shipping unit is 0 (zero), but the physical remaining quantity in the inventory unit isn't 0, you can't generate the packing slip.</span></span> <span data-ttu-id="39c8f-113">Ez a probléma például akkor fordulhat elő, ha a cikk értékesítési egysége és készletegysége eltér, és az egységek közötti átváltás nem pontos.</span><span class="sxs-lookup"><span data-stu-id="39c8f-113">For example, this issue might occur if the sales unit and inventory unit for the item differ, and the conversion between units isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="39c8f-114">Megoldás</span><span class="sxs-lookup"><span data-stu-id="39c8f-114">Resolution</span></span>

<span data-ttu-id="39c8f-115">A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="39c8f-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="39c8f-116">A probléma javításához végezze el a következő feladatok egyikét:</span><span class="sxs-lookup"><span data-stu-id="39c8f-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="39c8f-117">Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="39c8f-117">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="39c8f-118">Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy a mennyiség kerekítési problémák nélkül, tisztán átváltható legyen.</span><span class="sxs-lookup"><span data-stu-id="39c8f-118">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>
- <span data-ttu-id="39c8f-119">Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy az egység és a mennyiség igazodjon az egység tizedes pontosságához.</span><span class="sxs-lookup"><span data-stu-id="39c8f-119">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>
- <span data-ttu-id="39c8f-120">Győződjön meg arról, hogy a készlet mértékegysége kisebb, mint az értékesítési mértékegység.</span><span class="sxs-lookup"><span data-stu-id="39c8f-120">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="39c8f-121">Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek</span><span class="sxs-lookup"><span data-stu-id="39c8f-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="39c8f-122">Az alábbi módon ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="39c8f-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="39c8f-123">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="39c8f-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="39c8f-124">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="39c8f-124">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="39c8f-125">A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39c8f-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="39c8f-126">Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="39c8f-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="39c8f-127">A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.</span><span class="sxs-lookup"><span data-stu-id="39c8f-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="39c8f-128">Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.</span><span class="sxs-lookup"><span data-stu-id="39c8f-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="39c8f-129">Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.</span><span class="sxs-lookup"><span data-stu-id="39c8f-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a><span data-ttu-id="39c8f-130">Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy a mennyiség kerekítési problémák nélkül, tisztán átváltható legyen</span><span class="sxs-lookup"><span data-stu-id="39c8f-130">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues</span></span>

<span data-ttu-id="39c8f-131">Az alábbi módon tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy a mennyiség kerekítési problémák nélkül, tisztán átváltható legyen.</span><span class="sxs-lookup"><span data-stu-id="39c8f-131">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>

1. <span data-ttu-id="39c8f-132">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="39c8f-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="39c8f-133">Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="39c8f-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="39c8f-134">A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39c8f-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="39c8f-135">A  **Rakománysorok** lapon válassza ki annak a cikknek rakománysorát, amely meghaladja a felülszállítás százalékos arányát.</span><span class="sxs-lookup"><span data-stu-id="39c8f-135">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery.</span></span>
1. <span data-ttu-id="39c8f-136">A kiválasztott mennyiség beállításához válassza a **Kitárolt mennyiség csökkentése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39c8f-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="39c8f-137">A  **Sor részletei** lapon válassza ki a **Rendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="39c8f-137">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="39c8f-138">A **Mennyiség** mezőben állítsa be a kitárolt mennyiség értékét (azaz a **Munka létrehozott mennyisége** mező értékét), hogy a szállítólevél létrehozása elvégezhető legyen.</span><span class="sxs-lookup"><span data-stu-id="39c8f-138">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="39c8f-139">Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy az egység és a mennyiség igazodjon az egység tizedes pontosságához</span><span class="sxs-lookup"><span data-stu-id="39c8f-139">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="39c8f-140">Az alábbi módon tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy az egység és a mennyiség igazodjon az egység tizedes pontosságához.</span><span class="sxs-lookup"><span data-stu-id="39c8f-140">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="39c8f-141">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="39c8f-141">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="39c8f-142">Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="39c8f-142">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="39c8f-143">A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely a hibát okozza.</span><span class="sxs-lookup"><span data-stu-id="39c8f-143">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="39c8f-144">Jegyezze fel a **Mennyiség** és az **Egység** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="39c8f-144">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="39c8f-145">Lépjen a **Szervezetadminisztráció \> Egységek \> Egységek** részre.</span><span class="sxs-lookup"><span data-stu-id="39c8f-145">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="39c8f-146">Válassza ki azt az egységet, amelyhez nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="39c8f-146">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="39c8f-147">Szükség szerint módosítsa a **Tizedes pontosság** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="39c8f-147">Adjust the value of the **Decimal precision** field as required.</span></span>

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a><span data-ttu-id="39c8f-148">Győződjön meg arról, hogy a készlet mértékegysége kisebb, mint az értékesítési mértékegység</span><span class="sxs-lookup"><span data-stu-id="39c8f-148">Make sure that the inventory unit of measure is smaller than the sales unit of measure</span></span>

<span data-ttu-id="39c8f-149">Győződjön meg arról, hogy a készlet mértékegysége kisebb, mint az értékesítési mértékegység.</span><span class="sxs-lookup"><span data-stu-id="39c8f-149">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span> <span data-ttu-id="39c8f-150">Fontolja meg, érdemes-e újrakonfigurálni a cikk mértékegységét.</span><span class="sxs-lookup"><span data-stu-id="39c8f-150">Consider reconfiguring the unit of measure for the item as required.</span></span>
