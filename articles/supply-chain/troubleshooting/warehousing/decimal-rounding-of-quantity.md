---
title: A tényleges frissített mennyiség tizedes kerekítése helytelen
description: Csomagolási bizonylat létrehozásakor a kimenő terhelés olyan mennyiséget tartalmaz, amely nem egyezik meg az egységben meghatározott tizedes pontossággal.
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
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248785"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a><span data-ttu-id="e186c-103">A tényleges frissített mennyiség tizedes kerekítése helytelen</span><span class="sxs-lookup"><span data-stu-id="e186c-103">Decimal rounding of the physical updating quantity is incorrect</span></span>

<span data-ttu-id="e186c-104">Hibakód: SYS19589</span><span class="sxs-lookup"><span data-stu-id="e186c-104">Error code: SYS19589</span></span>

## <a name="symptoms"></a><span data-ttu-id="e186c-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="e186c-105">Symptoms</span></span>

<span data-ttu-id="e186c-106">Csomagolási bizonylat létrehozásakor a kimenő terhelés olyan mennyiséget tartalmaz, amely nem egyezik meg az egységben meghatározott tizedes pontossággal.</span><span class="sxs-lookup"><span data-stu-id="e186c-106">When you generate a packing slip, the outbound load contains a quantity that doesn't match the decimal precision that is defined in the unit.</span></span>

<span data-ttu-id="e186c-107">Amikor megpróbál létrehozni egy szállítólevelet, a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="e186c-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="e186c-108">A tényleges módosító mennyiség tizedes kerekítése a(z) %1 egységben helytelen.</span><span class="sxs-lookup"><span data-stu-id="e186c-108">Decimal rounding of the physical updating quantity in the unit %1 is incorrect.</span></span>

<span data-ttu-id="e186c-109">Ennek megfelelően nem hozható létre szállítólevél a rakományhoz.</span><span class="sxs-lookup"><span data-stu-id="e186c-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="e186c-110">Ok</span><span class="sxs-lookup"><span data-stu-id="e186c-110">Cause</span></span>

<span data-ttu-id="e186c-111">A rendszer kiértékeli, hogy a szállítási mennyiség tizedes kerekítése megfelel-e a szállítási egységnél megadott tizedes pontosságnak.</span><span class="sxs-lookup"><span data-stu-id="e186c-111">The system evaluates whether the decimal rounding of the shipping quantity corresponds to the decimal precision that is defined for the shipping unit.</span></span> <span data-ttu-id="e186c-112">Ha a rendszer a megadott tizedesjegyre kerekítve találja meg a szállítási mennyiséget, és úgy találja, hogy a kerekített szállítási mennyiség nem felel meg a tényleges szállítási mennyiségnek, nem generálhatja a csomagjegyzéket.</span><span class="sxs-lookup"><span data-stu-id="e186c-112">When the system rounds the shipping quantity to the specified number of decimal places, if it finds that the rounded shipping quantity doesn't match the actual shipping quantity, you can't generate the packing slip.</span></span> <span data-ttu-id="e186c-113">Ez a probléma például akkor fordulhat elő, ha az értékesítési mennyiség 1,75 kilogramm (kg), de a tizedes pontosság *1*.</span><span class="sxs-lookup"><span data-stu-id="e186c-113">For example, this issue might occur if the sales quantity is 1.75 kilograms (kg), but the decimal precision is set to *1*.</span></span>

## <a name="resolution"></a><span data-ttu-id="e186c-114">Megoldás</span><span class="sxs-lookup"><span data-stu-id="e186c-114">Resolution</span></span>

<span data-ttu-id="e186c-115">A rakomány vagy a szállítmány jelenlegi állapotában nem hozható létre szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="e186c-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="e186c-116">A probléma javításához végezze el a következő feladatok egyikét:</span><span class="sxs-lookup"><span data-stu-id="e186c-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="e186c-117">Tekintse át a terhelési sorokat, és végezze el a beállításokat annak biztosítására, hogy a mennyiséget tisztán lehet számolni tizedesjegyek és egyéb kerekítési kérdések nélkül.</span><span class="sxs-lookup"><span data-stu-id="e186c-117">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>
- <span data-ttu-id="e186c-118">Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy az egység és a mennyiség igazodjon az egység tizedes pontosságához.</span><span class="sxs-lookup"><span data-stu-id="e186c-118">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a><span data-ttu-id="e186c-119">Tekintse át a terhelési sorokat, és végezze el a beállításokat annak biztosítására, hogy a mennyiséget tisztán lehet számolni tizedesjegyek és egyéb kerekítési kérdések nélkül</span><span class="sxs-lookup"><span data-stu-id="e186c-119">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues</span></span>

<span data-ttu-id="e186c-120">A következő eljárással tekintse át a terhelési sorokat, és végezze el a beállításokat annak biztosítása érdekében, hogy a mennyiség tisztán átváltható legyen tizedesjegyek és egyéb kerekítési problémák nélkül.</span><span class="sxs-lookup"><span data-stu-id="e186c-120">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>

1. <span data-ttu-id="e186c-121">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="e186c-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e186c-122">Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="e186c-122">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="e186c-123">A Művelet panel  **Szállítás és fogadás** lapján lévő  **Sztornírozás** csoportban válassza a  **Szállítmány visszaigazolásának sztornírozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e186c-123">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="e186c-124">A  **Rakománysorok** lapon válassza ki annak a cikknek rakománysorát, amely a hibát okozza.</span><span class="sxs-lookup"><span data-stu-id="e186c-124">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="e186c-125">A kiválasztott mennyiség beállításához válassza a **Kitárolt mennyiség csökkentése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e186c-125">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="e186c-126">A  **Sor részletei** lapon válassza ki a **Rendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e186c-126">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="e186c-127">A **Mennyiség** mezőben állítsa be a kitárolt mennyiség értékét (azaz a **Munka létrehozott mennyisége** mező értékét), hogy a szállítólevél létrehozása elvégezhető legyen.</span><span class="sxs-lookup"><span data-stu-id="e186c-127">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="e186c-128">Tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy az egység és a mennyiség igazodjon az egység tizedes pontosságához</span><span class="sxs-lookup"><span data-stu-id="e186c-128">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="e186c-129">Az alábbi módon tekintse át a rakománysorokat, és hajtsa végre a szükséges módosításokat, hogy az egység és a mennyiség igazodjon az egység tizedes pontosságához.</span><span class="sxs-lookup"><span data-stu-id="e186c-129">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="e186c-130">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="e186c-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e186c-131">Válassza ki azt a rakományt, amelyhez nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="e186c-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="e186c-132">A **Rakománysorok** gyorslapon válassza ki annak a cikknek rakománysorát, amely a hibát okozza.</span><span class="sxs-lookup"><span data-stu-id="e186c-132">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="e186c-133">Jegyezze fel a **Mennyiség** és az **Egység** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="e186c-133">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="e186c-134">Lépjen a **Szervezetadminisztráció \> Egységek \> Egységek** részre.</span><span class="sxs-lookup"><span data-stu-id="e186c-134">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="e186c-135">Válassza ki azt az egységet, amelyhez nem hozható létre a szállítólevél.</span><span class="sxs-lookup"><span data-stu-id="e186c-135">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="e186c-136">Szükség szerint módosítsa a **Tizedes pontosság** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="e186c-136">Adjust the value of the **Decimal precision** field as required.</span></span>
