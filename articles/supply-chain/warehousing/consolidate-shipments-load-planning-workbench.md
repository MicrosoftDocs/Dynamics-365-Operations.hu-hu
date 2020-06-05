---
title: Szállítmányok konszolidálása a Kiadás a raktárba lehetőség használatával a Rakománytervező munkaterület oldalról
description: Ez a témakör egy olyan esetet mutat be, amikor több rendelést adnak ki a raktárba ugyanabban a rakományban, amelyeket a rendszer automatikusan szállítmányokká konszolidál.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 396a038dbf2f4b6835ecbb5fd8cb39a3a3608af7
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383786"
---
# <a name="consolidate-shipments-by-using-release-to-warehouse-from-the-load-planning-workbench"></a><span data-ttu-id="df143-103">Szállítmányok konszolidálása a Kiadás a raktárba lehetőség használatával a Rakománytervező munkaterület oldalról</span><span class="sxs-lookup"><span data-stu-id="df143-103">Consolidate shipments by using Release to warehouse from the load planning workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="df143-104">Ez a témakör egy olyan esetet mutat be, amikor több rendelést adnak ki a raktárba ugyanabban a rakományban, amelyeket a rendszer automatikusan szállítmányokká konszolidál.</span><span class="sxs-lookup"><span data-stu-id="df143-104">This topic presents a scenario where multiple orders are released to the warehouse in the same load and are then automatically consolidated into shipments.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="df143-105">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="df143-105">Make demo data available</span></span>

<span data-ttu-id="df143-106">Az ebben a témakörben szereplő minden egyes forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Microsoft Dynamics 365 Supply Chain Management szolgáltatáshoz biztosított standard bemutatóadatokban.</span><span class="sxs-lookup"><span data-stu-id="df143-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="df143-107">Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="df143-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="df143-108">Szállítmánykonszolidációs irányelvek és a termékszűrők beállítása</span><span class="sxs-lookup"><span data-stu-id="df143-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="df143-109">Az itt ismertetett eset feltételezi, hogy már be van kapcsolva a funkció, és végrehajtotta a [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md) részben szereplő gyakorlatokat, és létrehozta az ott ismertetett irányelveket és más rekordokat.</span><span class="sxs-lookup"><span data-stu-id="df143-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="df143-110">A jelen forgatókönyv végrehajtása előtt győződjön meg arról, hogy elvégezte azokat a gyakorlatokat.</span><span class="sxs-lookup"><span data-stu-id="df143-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="df143-111">Értékesítési rendelések létrehozása ehhez a forgatókönyvhöz</span><span class="sxs-lookup"><span data-stu-id="df143-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="df143-112">Első lépésként hozza létre a munkához használni kívánt értékesítési rendelések gyűjteményét.</span><span class="sxs-lookup"><span data-stu-id="df143-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="df143-113">A speciális raktár (WMS) folyamataihoz engedélyezett raktárral kell dolgoznia.</span><span class="sxs-lookup"><span data-stu-id="df143-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="df143-114">Ha külön nem említik a másik raktárat, akkor ugyanazt a raktárat kell használni a következő rendelések mindegyikéhez.</span><span class="sxs-lookup"><span data-stu-id="df143-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="df143-115">Nyissa meg a **Kinnlevőségek \> Rendelések \> Összes értékesítési rendelés** pontot, és hozza létre az értékesítési rendelések gyűjteményét, amelyek a következő alszakaszokban szereplő beállításokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="df143-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="df143-116">1. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="df143-116">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="df143-117">1-1. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="df143-117">Sales order 1-1</span></span>

1. <span data-ttu-id="df143-118">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-118">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="df143-119">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="df143-119">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="df143-120">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="df143-120">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="df143-121">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-121">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-122">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="df143-122">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="df143-123">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-123">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="df143-124">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-124">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="df143-125">1-2. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="df143-125">Sales order 1-2</span></span>

1. <span data-ttu-id="df143-126">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-126">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="df143-127">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="df143-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="df143-128">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="df143-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="df143-129">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-130">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="df143-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="df143-131">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="df143-132">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="df143-133">1-3. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="df143-133">Sales order 1-3</span></span>

1. <span data-ttu-id="df143-134">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="df143-135">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="df143-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="df143-136">**Szállítás módja:** *10*</span><span class="sxs-lookup"><span data-stu-id="df143-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="df143-137">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-138">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="df143-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="df143-139">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="df143-140">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="df143-141">Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-142">**Cikkszám:** *A0002* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="df143-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="df143-143">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="df143-144">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="df143-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="df143-145">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a második rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="df143-146">2. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="df143-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="df143-147">2-1. és 2-2. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="df143-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="df143-148">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="df143-149">**Vevőkód** *US-002*</span><span class="sxs-lookup"><span data-stu-id="df143-149">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="df143-150">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-150">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-151">**Cikkszám:** *M9200* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Gyúlékony*)</span><span class="sxs-lookup"><span data-stu-id="df143-151">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="df143-152">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-152">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="df143-153">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-153">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="df143-154">Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-154">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-155">**Cikkszám:** *M9201* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Robbanásveszélyes*)</span><span class="sxs-lookup"><span data-stu-id="df143-155">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="df143-156">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-156">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="df143-157">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="df143-157">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="df143-158">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a második rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-158">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="df143-159">3. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="df143-159">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="df143-160">3-1. és 3-2. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="df143-160">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="df143-161">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-161">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="df143-162">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="df143-162">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="df143-163">**Vevői igénylés:** *1*</span><span class="sxs-lookup"><span data-stu-id="df143-163">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="df143-164">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-164">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-165">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="df143-165">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="df143-166">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-166">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="df143-167">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-167">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="df143-168">3-3. és 3-4. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="df143-168">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="df143-169">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-169">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="df143-170">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="df143-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="df143-171">**Vevői igénylés:** *2*</span><span class="sxs-lookup"><span data-stu-id="df143-171">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="df143-172">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-172">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-173">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="df143-173">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="df143-174">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-174">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="df143-175">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-175">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="df143-176">4. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="df143-176">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="df143-177">4-1. és 4-2. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="df143-177">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="df143-178">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-178">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="df143-179">**Vevőkód** *US-003*</span><span class="sxs-lookup"><span data-stu-id="df143-179">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="df143-180">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-180">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-181">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="df143-181">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="df143-182">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-182">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="df143-183">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-183">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="df143-184">4-3. és 4-4. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="df143-184">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="df143-185">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-185">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="df143-186">**Vevőkód** *US-004*</span><span class="sxs-lookup"><span data-stu-id="df143-186">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="df143-187">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-187">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-188">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="df143-188">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="df143-189">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-189">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="df143-190">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-190">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="df143-191">4-5. és 4-6. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="df143-191">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="df143-192">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-192">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="df143-193">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="df143-193">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="df143-194">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="df143-194">**Site:** *6*</span></span>
    - <span data-ttu-id="df143-195">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="df143-195">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="df143-196">**Gyűjtő:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="df143-196">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="df143-197">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-198">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="df143-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="df143-199">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-199">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="df143-200">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-200">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="df143-201">4-7. és 4-8. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="df143-201">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="df143-202">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-202">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="df143-203">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="df143-203">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="df143-204">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="df143-204">**Site:** *6*</span></span>
    - <span data-ttu-id="df143-205">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="df143-205">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="df143-206">**Gyűjtő:** Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="df143-206">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="df143-207">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="df143-207">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="df143-208">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="df143-208">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="df143-209">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="df143-209">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="df143-210">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="df143-210">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a><span data-ttu-id="df143-211">A rakománytervezési munkaterület használata a rakományok létrehozásához és kiadásához a raktárba</span><span class="sxs-lookup"><span data-stu-id="df143-211">Use the load planning workbench to create loads and release them to the warehouse</span></span>

<span data-ttu-id="df143-212">A következő lépések végrehajtásával rakományt hozhat létre az egyes rendeléskészletekhez, amelyeket ehhez az esethez készített, majd kiadhatja azt a raktárnak.</span><span class="sxs-lookup"><span data-stu-id="df143-212">Follow these steps to create a load for each order set that you created for this scenario and then release it to the warehouse.</span></span>

1. <span data-ttu-id="df143-213">Ugorjon a **Raktárkezelés \> Rakományok \> Rakománytervező munkaterület** elemre.</span><span class="sxs-lookup"><span data-stu-id="df143-213">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="df143-214">Az **Értékesítési sorok** lapon megkeresheti és kiválaszthatja az adott esethez létrehozott rendeléskészletek egyikének összes értékesítési rendelési sorait.</span><span class="sxs-lookup"><span data-stu-id="df143-214">On the **Sales lines** tab, find and select all the sales order lines from one of the order sets that you created for this scenario.</span></span>
1. <span data-ttu-id="df143-215">A művelet ablaktábla **Kereslet és kínálat** lapján válassza a **Hozzáadás \> Új rakományhoz** lehetőséget, amellyel a kiválasztott rendelési sorokat új rakományhoz adhatja.</span><span class="sxs-lookup"><span data-stu-id="df143-215">On the Action Pane, on the **Supply and demand** tab, select **Add \> To new load** to add the selected order lines to a new Load.</span></span>
1. <span data-ttu-id="df143-216">A **Rakománysablon hozzárendelése** párbeszédablakban a **Rakománysablon azonosítója** mezőben válassza ki a rakománysablont, pl. a *Normál rakománysablon* elemet.</span><span class="sxs-lookup"><span data-stu-id="df143-216">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *Stnd Load Template*.</span></span>
1. <span data-ttu-id="df143-217">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="df143-217">Select **OK** to close the dialog box.</span></span> 
1. <span data-ttu-id="df143-218">A **Rakomány** szakaszban keresse meg és válassza ki az imént létrehozott rakományt.</span><span class="sxs-lookup"><span data-stu-id="df143-218">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="df143-219">A kiválasztott rakomány raktárba történő kiadásához válassza a **Kiadás \> Kiadás a raktárba** elemet.</span><span class="sxs-lookup"><span data-stu-id="df143-219">Select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="df143-220">Ismételje meg ezt az eljárást a három további rendeléskészletnél, amelyet az adott esethez létrehozott.</span><span class="sxs-lookup"><span data-stu-id="df143-220">Repeat this procedure for the other three order sets that you created for this scenario.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="df143-221">Szállítmányok ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="df143-221">Verify the shipments</span></span>

<span data-ttu-id="df143-222">A következő eljárással ellenőrizhetők a szállítmánykonszolidálás eredményeképpen létrehozott vagy frissített szállítmányok.</span><span class="sxs-lookup"><span data-stu-id="df143-222">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="df143-223">Ennek segítségével ellenőrizheti az adott esethez létrehozott összes rendeléskészletet, majd megtekintheti a következő részszakaszokat, amellyel meggyőződhet arról, hogy a várt eredményeket kapta.</span><span class="sxs-lookup"><span data-stu-id="df143-223">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="df143-224">Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="df143-224">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="df143-225">Keresse meg és válassza ki a kívánt szállítmányt.</span><span class="sxs-lookup"><span data-stu-id="df143-225">Find and select the required shipment.</span></span>
1. <span data-ttu-id="df143-226">Ha a szállítmány létrehozásakor használt konszolidációs irányelvet létrehozzák vagy frissítik, akkor meg kell jelennie a **Szállítmánykonszolidációs irányelv** mezőben.</span><span class="sxs-lookup"><span data-stu-id="df143-226">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-order-set-1-in-one-load"></a><span data-ttu-id="df143-227">1. rendeléskészlet kiadása egy rakományban</span><span class="sxs-lookup"><span data-stu-id="df143-227">Release order set 1 in one load</span></span>

<span data-ttu-id="df143-228">Két szállítmányt kellett létrehozni:</span><span class="sxs-lookup"><span data-stu-id="df143-228">Two shipments should have been created:</span></span>

- <span data-ttu-id="df143-229">Az első szállítmány három sort tartalmaz, és a *CustomerMode* szállítmánykonszolidációs irányelv használatával jött létre.</span><span class="sxs-lookup"><span data-stu-id="df143-229">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="df143-230">A második szállítmányt, amely nem a *Légitársaságok* szállítási módot használja, a *CustomerOrderNo* szállítmánykonszolidációs irányelv használatával hozták létre.</span><span class="sxs-lookup"><span data-stu-id="df143-230">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-order-set-2-in-one-load"></a><span data-ttu-id="df143-231">2. rendeléskészlet kiadása egy rakományban</span><span class="sxs-lookup"><span data-stu-id="df143-231">Release order set 2 in one load</span></span>

<span data-ttu-id="df143-232">Három szállítmányt kellett létrehozni:</span><span class="sxs-lookup"><span data-stu-id="df143-232">Three shipments should have been created:</span></span>

- <span data-ttu-id="df143-233">Az első szállítmány a *Gyúlékony* cikkeket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="df143-233">The first shipment contains the *Flammable* items.</span></span>
- <span data-ttu-id="df143-234">A másik két szállítmány mindegyike egy sort tartalmaz, amelyben a *Robbanásveszélyes* cikk szerepel.</span><span class="sxs-lookup"><span data-stu-id="df143-234">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-order-set-3-in-one-load"></a><span data-ttu-id="df143-235">3. rendeléskészlet kiadása egy rakományban</span><span class="sxs-lookup"><span data-stu-id="df143-235">Release order set 3 in one load</span></span>

<span data-ttu-id="df143-236">Két szállítmányt kellett létrehozni:</span><span class="sxs-lookup"><span data-stu-id="df143-236">Two shipments should have been created:</span></span>

- <span data-ttu-id="df143-237">Az első szállítmány azon értékesítési rendelés sorait tartalmazza, amelynél a **Vevői igénylés** mező értéke *1*.</span><span class="sxs-lookup"><span data-stu-id="df143-237">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="df143-238">A második szállítmány azon értékesítési rendelés sorait tartalmazza, amelynél a **Vevői igénylés** mező értéke *2*.</span><span class="sxs-lookup"><span data-stu-id="df143-238">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="release-order-set-4-in-one-load"></a><span data-ttu-id="df143-239">4. rendeléskészlet kiadása egy rakományban</span><span class="sxs-lookup"><span data-stu-id="df143-239">Release order set 4 in one load</span></span>

<span data-ttu-id="df143-240">Négy szállítmányt kellett létrehozni:</span><span class="sxs-lookup"><span data-stu-id="df143-240">Four shipments should have been created:</span></span>

- <span data-ttu-id="df143-241">Az *US-003* vevői számla két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="df143-241">Lines from two orders for customer account *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="df143-242">Az *US-004* vevői számla két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="df143-242">Lines from two orders for customer account *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="df143-243">Az *US-007* vevői számla 4-5. és 4-6. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="df143-243">Lines from sales orders 4-5 and 4-6 for customer account *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="df143-244">Az *US-007* vevői számla 4-7. és 4-8. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *CrossOrder* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="df143-244">Lines from sales orders 4-7 and 4-8 for customer account *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df143-245">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="df143-245">Additional resources</span></span>

- [<span data-ttu-id="df143-246">Szállítmánykonszolidációs irányelvek</span><span class="sxs-lookup"><span data-stu-id="df143-246">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="df143-247">Szállítmánykonszolidációs irányelvek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="df143-247">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)