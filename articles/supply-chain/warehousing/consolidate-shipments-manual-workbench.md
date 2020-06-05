---
title: Szállítmányok konszolidálása a szállítmánykonszolidációs munkaterület használatával
description: Ez a témakör egy olyan esetet mutat be, amikor több rendelést adnak ki a raktárba, majd később szállítmánykonszolidációs munkaterület használatával szállítmányokba konszolidálják őket.
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
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b1a2c9506b4444fc98a9e4f0389cbd69db4ce052
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383785"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="c4346-103">Szállítmányok konszolidálása a szállítmánykonszolidációs munkaterület használatával</span><span class="sxs-lookup"><span data-stu-id="c4346-103">Consolidate shipments by using the shipment consolidation workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4346-104">Ez a témakör egy olyan esetet mutat be, amikor több rendelést adnak ki a raktárba, majd később szállítmánykonszolidációs munkaterület használatával szállítmányokba konszolidálják őket.</span><span class="sxs-lookup"><span data-stu-id="c4346-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated into shipments later by using the shipment consolidation workbench.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="c4346-105">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="c4346-105">Make demo data available</span></span>

<span data-ttu-id="c4346-106">Az ebben a témakörben szereplő minden egyes forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Microsoft Dynamics 365 Supply Chain Management szolgáltatáshoz biztosított standard bemutatóadatokban.</span><span class="sxs-lookup"><span data-stu-id="c4346-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c4346-107">Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="c4346-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="c4346-108">Szállítmánykonszolidációs irányelvek és a termékszűrők beállítása</span><span class="sxs-lookup"><span data-stu-id="c4346-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="c4346-109">Az itt ismertetett eset feltételezi, hogy már be van kapcsolva a funkció, és végrehajtotta a [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md) részben szereplő gyakorlatokat, és létrehozta az ott ismertetett irányelveket és más rekordokat.</span><span class="sxs-lookup"><span data-stu-id="c4346-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="c4346-110">A jelen forgatókönyv végrehajtása előtt győződjön meg arról, hogy elvégezte azokat a gyakorlatokat.</span><span class="sxs-lookup"><span data-stu-id="c4346-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a><span data-ttu-id="c4346-111">A manuális szállítmánykonszolidáció funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="c4346-111">Turn on the manual shipment consolidation feature</span></span>

<span data-ttu-id="c4346-112">A *Manuális szállítmánykonszolidáció* funkció használata előtt először be kell kapcsolnia rendszerében.</span><span class="sxs-lookup"><span data-stu-id="c4346-112">Before you can use the *Manual shipment consolidation* feature, you must turn it on in your system.</span></span> <span data-ttu-id="c4346-113">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="c4346-114">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="c4346-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c4346-115">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="c4346-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="c4346-116">**Funkció neve:** *Manuális szállítmánykonszolidáció*</span><span class="sxs-lookup"><span data-stu-id="c4346-116">**Feature name:** *Manual shipment consolidation*</span></span>

<span data-ttu-id="c4346-117">Ahogy az a [Szállítmánykonfigurációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md) részben szerepelt, az irányelvek létrehozása előtt a *Szállítmányok konszolidálása* funkciót is be kell kapcsolnia.</span><span class="sxs-lookup"><span data-stu-id="c4346-117">As was mentioned in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), you must also turn on the *Consolidate shipment* feature before you can create policies.</span></span> <span data-ttu-id="c4346-118">Azonban már korábban végre kellett volna hajtania ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="c4346-118">However, you should already have completed that step.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="c4346-119">Értékesítési rendelések létrehozása ehhez a forgatókönyvhöz</span><span class="sxs-lookup"><span data-stu-id="c4346-119">Create the sales orders for this scenario</span></span>

<span data-ttu-id="c4346-120">Első lépésként hozza létre a munkához használni kívánt értékesítési rendelések gyűjteményét.</span><span class="sxs-lookup"><span data-stu-id="c4346-120">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="c4346-121">A speciális raktár (WMS) folyamataihoz engedélyezett raktárral kell dolgoznia.</span><span class="sxs-lookup"><span data-stu-id="c4346-121">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="c4346-122">Ha külön nem említik a másik raktárat, akkor ugyanazt a raktárat kell használni a következő rendelések mindegyikéhez.</span><span class="sxs-lookup"><span data-stu-id="c4346-122">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="c4346-123">Nyissa meg a **Kinnlevőségek \> Rendelések \> Összes értékesítési rendelés** pontot, és hozza létre az értékesítési rendelések gyűjteményét, amelyek a következő alszakaszokban szereplő beállításokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="c4346-123">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="c4346-124">1. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4346-124">Create order set 1</span></span>

#### <a name="sales-orders-1-1-and-1-2"></a><span data-ttu-id="c4346-125">1-1. és 1-2. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="c4346-125">Sales orders 1-1 and 1-2</span></span>

1. <span data-ttu-id="c4346-126">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-126">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c4346-127">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c4346-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c4346-128">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="c4346-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="c4346-129">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-130">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="c4346-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c4346-131">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c4346-132">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="c4346-133">1-3. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="c4346-133">Sales order 1-3</span></span>

1. <span data-ttu-id="c4346-134">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="c4346-135">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c4346-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c4346-136">**Szállítás módja:** *10*</span><span class="sxs-lookup"><span data-stu-id="c4346-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="c4346-137">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-138">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="c4346-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c4346-139">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c4346-140">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="c4346-141">Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-142">**Cikkszám:** *A0002* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="c4346-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c4346-143">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="c4346-144">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="c4346-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="c4346-145">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a második rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="c4346-146">2. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4346-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="c4346-147">2-1. és 2-2. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="c4346-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="c4346-148">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c4346-149">**Vevőkód** *US-002*</span><span class="sxs-lookup"><span data-stu-id="c4346-149">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="c4346-150">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="c4346-150">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="c4346-151">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-151">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-152">**Cikkszám:** *M9200* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Gyúlékony*)</span><span class="sxs-lookup"><span data-stu-id="c4346-152">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="c4346-153">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-153">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c4346-154">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-154">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="c4346-155">Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-155">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-156">**Cikkszám:** *M9201* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Robbanásveszélyes*)</span><span class="sxs-lookup"><span data-stu-id="c4346-156">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="c4346-157">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-157">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="c4346-158">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="c4346-158">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="c4346-159">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a második rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-159">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="c4346-160">3. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4346-160">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="c4346-161">3-1. és 3-2. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="c4346-161">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="c4346-162">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-162">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c4346-163">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c4346-163">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c4346-164">**Vevői igénylés:** *1*</span><span class="sxs-lookup"><span data-stu-id="c4346-164">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="c4346-165">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-165">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-166">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="c4346-166">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c4346-167">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-167">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c4346-168">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-168">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="c4346-169">3-3. és 3-4. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="c4346-169">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="c4346-170">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-170">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c4346-171">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c4346-171">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c4346-172">**Vevői igénylés:** *2*</span><span class="sxs-lookup"><span data-stu-id="c4346-172">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="c4346-173">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-173">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-174">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="c4346-174">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c4346-175">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-175">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c4346-176">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-176">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="c4346-177">4. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4346-177">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="c4346-178">4-1. és 4-2. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="c4346-178">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="c4346-179">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c4346-180">**Vevőkód** *US-003*</span><span class="sxs-lookup"><span data-stu-id="c4346-180">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="c4346-181">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-181">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-182">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="c4346-182">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c4346-183">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-183">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c4346-184">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-184">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="c4346-185">4-3. és 4-4. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="c4346-185">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="c4346-186">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-186">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c4346-187">**Vevőkód** *US-004*</span><span class="sxs-lookup"><span data-stu-id="c4346-187">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="c4346-188">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-188">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-189">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="c4346-189">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c4346-190">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-190">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c4346-191">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-191">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="c4346-192">4-5. és 4-6. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="c4346-192">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="c4346-193">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-193">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c4346-194">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="c4346-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="c4346-195">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="c4346-195">**Site:** *6*</span></span>
    - <span data-ttu-id="c4346-196">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="c4346-196">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="c4346-197">**Gyűjtő:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="c4346-197">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="c4346-198">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-198">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-199">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="c4346-199">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c4346-200">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-200">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c4346-201">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-201">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="c4346-202">4-7. és 4-8. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="c4346-202">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="c4346-203">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-203">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="c4346-204">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="c4346-204">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="c4346-205">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="c4346-205">**Site:** *6*</span></span>
    - <span data-ttu-id="c4346-206">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="c4346-206">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="c4346-207">**Gyűjtő:** Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="c4346-207">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="c4346-208">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="c4346-208">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="c4346-209">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="c4346-209">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="c4346-210">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="c4346-210">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="c4346-211">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-211">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="c4346-212">A rendelések kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="c4346-212">Release the orders to the warehouse</span></span>

<span data-ttu-id="c4346-213">A következő lépések végrehajtásával kiadhatja az ehhez az esethez létrehozott összes értékesítési rendelést a raktárba.</span><span class="sxs-lookup"><span data-stu-id="c4346-213">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="c4346-214">Ugrás a **Kinnlevőségek \> Rendelések \> Minden értékesítési rendelésre**.</span><span class="sxs-lookup"><span data-stu-id="c4346-214">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="c4346-215">Keresse meg és válassza ki a kiadandó értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="c4346-215">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="c4346-216">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek \> Kiadás raktárba** parancsot a kiválasztott értékesítési rendelés kiadásához.</span><span class="sxs-lookup"><span data-stu-id="c4346-216">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="c4346-217">Ismételje meg ezt az eljárást minden olyan értékesítési rendelésnél, amelyet az adott esethez létrehozott.</span><span class="sxs-lookup"><span data-stu-id="c4346-217">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="c4346-218">Szállítmányok konszolidálása a szállítmánykonszolidációs munkaterület használatával</span><span class="sxs-lookup"><span data-stu-id="c4346-218">Consolidate the shipments by using the shipment consolidation workbench</span></span>

1. <span data-ttu-id="c4346-219">Nyissa meg a **Raktárkezelés \> Kiadás raktárba \> Szállítmánykonszolidációs munkaterület** pontot.</span><span class="sxs-lookup"><span data-stu-id="c4346-219">Go to **Warehouse management \> Release to warehouse \> Shipment consolidation workbench**.</span></span>
1. <span data-ttu-id="c4346-220">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4346-220">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="c4346-221">A lekérdezésszerkesztő párbeszédablak **Tartomány** lapján a **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="c4346-221">In the query editor dialog box, on the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="c4346-222">**Tábla:** *Értékesítési rendelések*</span><span class="sxs-lookup"><span data-stu-id="c4346-222">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="c4346-223">**Mező:** *Értékesítési rendelés*</span><span class="sxs-lookup"><span data-stu-id="c4346-223">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="c4346-224">**Feltételek:** Adja meg az értékesítési rendelések számának vesszővel tagolt listáját a jelen esethez létrehozott minden egyes rendelési készlethez.</span><span class="sxs-lookup"><span data-stu-id="c4346-224">**Criteria:** Enter a comma-separated list of the sales order numbers for each order set that you created for this scenario.</span></span>

1. <span data-ttu-id="c4346-225">Az **OK** gombra kattintva mentse a lekérdezését, és zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c4346-225">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="c4346-226">A Művelet panelen válassza a **Szállítmányok konszolidálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c4346-226">On the Action Pane, select **Consolidate shipments**.</span></span>
1. <span data-ttu-id="c4346-227">Válassza ki az összes szállítmányt, majd a műveleti ablaktáblán válassza a **Konszolidálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4346-227">Select all the shipments, and then, on the Action Pane, select **Consolidate**.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="c4346-228">Szállítmányok ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="c4346-228">Verify the shipments</span></span>

<span data-ttu-id="c4346-229">A következő eljárással ellenőrizhetők a szállítmánykonszolidálás eredményeképpen létrehozott vagy frissített szállítmányok.</span><span class="sxs-lookup"><span data-stu-id="c4346-229">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="c4346-230">Ennek segítségével ellenőrizheti az adott esethez létrehozott összes rendeléskészletet, majd megtekintheti a következő részszakaszokat, amellyel meggyőződhet arról, hogy a várt eredményeket kapta.</span><span class="sxs-lookup"><span data-stu-id="c4346-230">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="c4346-231">Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="c4346-231">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="c4346-232">Keresse meg és válassza ki a kívánt szállítmányt.</span><span class="sxs-lookup"><span data-stu-id="c4346-232">Find and select the required shipment.</span></span>
1. <span data-ttu-id="c4346-233">Ha a szállítmány létrehozásakor használt konszolidációs irányelvet létrehozzák vagy frissítik, akkor meg kell jelennie a **Szállítmánykonszolidációs irányelv** mezőben.</span><span class="sxs-lookup"><span data-stu-id="c4346-233">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="related-shipments-for-order-set-1"></a><span data-ttu-id="c4346-234">Az 1. rendeléskészlethez kapcsolódó szállítmányok</span><span class="sxs-lookup"><span data-stu-id="c4346-234">Related shipments for order set 1</span></span>

<span data-ttu-id="c4346-235">Két szállítmányt kellett létrehozni:</span><span class="sxs-lookup"><span data-stu-id="c4346-235">Two shipments should have been created:</span></span>

- <span data-ttu-id="c4346-236">Az első szállítmány három sort tartalmaz, és a *CustomerMode* szállítmánykonszolidációs irányelv használatával jött létre.</span><span class="sxs-lookup"><span data-stu-id="c4346-236">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="c4346-237">A második szállítmányt, amely nem a *Légitársaságok* szállítási módot használja, a *CustomerOrderNo* szállítmánykonszolidációs irányelv használatával hozták létre.</span><span class="sxs-lookup"><span data-stu-id="c4346-237">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="related-shipments-for-order-set-2"></a><span data-ttu-id="c4346-238">A 2. rendeléskészlethez kapcsolódó szállítmányok</span><span class="sxs-lookup"><span data-stu-id="c4346-238">Related shipments for order set 2</span></span>

<span data-ttu-id="c4346-239">Három szállítmányt kellett létrehozni:</span><span class="sxs-lookup"><span data-stu-id="c4346-239">Three shipments should have been created:</span></span>

- <span data-ttu-id="c4346-240">Az első szállítmány *Gyúlékony* cikkeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="c4346-240">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="c4346-241">A másik két szállítmány mindegyike egy sort tartalmaz, amelyben a *Robbanásveszélyes* cikk szerepel.</span><span class="sxs-lookup"><span data-stu-id="c4346-241">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="related-shipments-for-order-set-3"></a><span data-ttu-id="c4346-242">A 3. rendeléskészlethez kapcsolódó szállítmányok</span><span class="sxs-lookup"><span data-stu-id="c4346-242">Related shipments for order set 3</span></span>

<span data-ttu-id="c4346-243">Két szállítmányt kellett létrehozni:</span><span class="sxs-lookup"><span data-stu-id="c4346-243">Two shipments should have been created:</span></span>

- <span data-ttu-id="c4346-244">Az első szállítmány azon értékesítési rendelés sorait tartalmazza, amelynél a **Vevői igénylés** mező értéke *1*.</span><span class="sxs-lookup"><span data-stu-id="c4346-244">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="c4346-245">A második szállítmány azon értékesítési rendelés sorait tartalmazza, amelynél a **Vevői igénylés** mező értéke *2*.</span><span class="sxs-lookup"><span data-stu-id="c4346-245">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="related-shipments-for-order-set-4"></a><span data-ttu-id="c4346-246">A 4. rendeléskészlethez kapcsolódó szállítmányok</span><span class="sxs-lookup"><span data-stu-id="c4346-246">Related shipments for order set 4</span></span>

<span data-ttu-id="c4346-247">Négy szállítmányt kellett létrehozni:</span><span class="sxs-lookup"><span data-stu-id="c4346-247">Four shipments should have been created:</span></span>

- <span data-ttu-id="c4346-248">Az *US-003* vevő két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="c4346-248">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="c4346-249">Az *US-004* vevő két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="c4346-249">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="c4346-250">Az *US-007* vevő 4-5. és 4-6. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="c4346-250">Lines from sales orders 4-5 and 4-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="c4346-251">Az *US-007* vevő 4-7. és 4-8. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *CrossOrder* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="c4346-251">Lines from sales orders 4-7 and 4-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c4346-252">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c4346-252">Additional resources</span></span>

- [<span data-ttu-id="c4346-253">Szállítmánykonszolidációs irányelvek</span><span class="sxs-lookup"><span data-stu-id="c4346-253">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="c4346-254">Szállítmánykonszolidációs irányelvek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c4346-254">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)