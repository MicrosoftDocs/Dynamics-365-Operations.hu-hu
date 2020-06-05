---
title: Szállítmányok manuális konszolidálása a szállítmányok konszolidálása oldal használatával
description: Ez a témakör egy olyan esetet mutat be, amikor több rendelést adnak ki a raktárba, majd később Szállítmányok konszolidálása oldallal konszolidálják őket.
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
ms.openlocfilehash: acc6e1d09894b57d2bb063bacbcddef239c1a8bd
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383782"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a><span data-ttu-id="eea43-103">Szállítmányok manuális konszolidálása a szállítmányok konszolidálása oldal használatával</span><span class="sxs-lookup"><span data-stu-id="eea43-103">Consolidate shipments manually by using the Consolidate shipments page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eea43-104">Ez a témakör egy olyan esetet mutat be, amikor több rendelést adnak ki a raktárba, majd később a **Szállítmányok konszolidálása** oldallal konszolidálják őket.</span><span class="sxs-lookup"><span data-stu-id="eea43-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated later by using the **Consolidate shipments** page.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="eea43-105">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="eea43-105">Make demo data available</span></span>

<span data-ttu-id="eea43-106">Az ebben a témakörben szereplő minden egyes forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Microsoft Dynamics 365 Supply Chain Management szolgáltatáshoz biztosított standard bemutatóadatokban.</span><span class="sxs-lookup"><span data-stu-id="eea43-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="eea43-107">Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="eea43-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="eea43-108">Szállítmánykonszolidációs irányelvek és a termékszűrők beállítása</span><span class="sxs-lookup"><span data-stu-id="eea43-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="eea43-109">Az itt ismertetett eset feltételezi, hogy már be van kapcsolva a funkció, és végrehajtotta a [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md) részben szereplő gyakorlatokat, és létrehozta az ott ismertetett irányelveket és más rekordokat.</span><span class="sxs-lookup"><span data-stu-id="eea43-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="eea43-110">A jelen forgatókönyv végrehajtása előtt győződjön meg arról, hogy elvégezte azokat a gyakorlatokat.</span><span class="sxs-lookup"><span data-stu-id="eea43-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="eea43-111">Értékesítési rendelések létrehozása ehhez a forgatókönyvhöz</span><span class="sxs-lookup"><span data-stu-id="eea43-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="eea43-112">Első lépésként hozza létre a munkához használni kívánt értékesítési rendelések gyűjteményét.</span><span class="sxs-lookup"><span data-stu-id="eea43-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="eea43-113">A speciális raktár (WMS) folyamataihoz engedélyezett raktárral kell dolgoznia.</span><span class="sxs-lookup"><span data-stu-id="eea43-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="eea43-114">Ha külön nem említik a másik raktárat, akkor ugyanazt a raktárat kell használni a következő rendelések mindegyikéhez.</span><span class="sxs-lookup"><span data-stu-id="eea43-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="eea43-115">Nyissa meg a **Kinnlevőségek \> Rendelések \> Összes értékesítési rendelés** pontot, és hozza létre az értékesítési rendelések gyűjteményét, amelyek a következő alszakaszokban szereplő beállításokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="eea43-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-sales-orders-1-and-2"></a><span data-ttu-id="eea43-116">1. és 2. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="eea43-116">Create sales orders 1 and 2</span></span>

1. <span data-ttu-id="eea43-117">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="eea43-117">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="eea43-118">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="eea43-118">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="eea43-119">**Gyűjtő:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="eea43-119">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="eea43-120">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="eea43-120">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="eea43-121">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="eea43-121">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="eea43-122">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="eea43-122">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="eea43-123">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="eea43-123">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-sales-orders-3-and-4"></a><span data-ttu-id="eea43-124">3. és 4. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="eea43-124">Create sales orders 3 and 4</span></span>

1. <span data-ttu-id="eea43-125">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="eea43-125">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="eea43-126">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="eea43-126">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="eea43-127">**Gyűjtő:** Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="eea43-127">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="eea43-128">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="eea43-128">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="eea43-129">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="eea43-129">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="eea43-130">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="eea43-130">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="eea43-131">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="eea43-131">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="eea43-132">A rendelések kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="eea43-132">Release the orders to the warehouse</span></span>

<span data-ttu-id="eea43-133">A következő lépések végrehajtásával kiadhatja az ehhez az esethez létrehozott összes értékesítési rendelést a raktárba.</span><span class="sxs-lookup"><span data-stu-id="eea43-133">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="eea43-134">Ugrás a **Kinnlevőségek \> Rendelések \> Minden értékesítési rendelésre**.</span><span class="sxs-lookup"><span data-stu-id="eea43-134">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="eea43-135">Keresse meg és válassza ki a kiadandó értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="eea43-135">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="eea43-136">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek \> Kiadás raktárba** parancsot a kiválasztott értékesítési rendelés kiadásához.</span><span class="sxs-lookup"><span data-stu-id="eea43-136">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="eea43-137">Ismételje meg ezt az eljárást minden olyan értékesítési rendelésnél, amelyet az adott esethez létrehozott.</span><span class="sxs-lookup"><span data-stu-id="eea43-137">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-shipments"></a><span data-ttu-id="eea43-138">Szállítmányok konszolidálása</span><span class="sxs-lookup"><span data-stu-id="eea43-138">Consolidate shipments</span></span>

1. <span data-ttu-id="eea43-139">Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="eea43-139">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="eea43-140">Keresse meg és válassza ki a szállítmányt, amely az 1. értékesítési rendelés raktárba való kiadásakor jött létre.</span><span class="sxs-lookup"><span data-stu-id="eea43-140">Find and select a shipment that was created when sales order 1 was released to the warehouse.</span></span> <span data-ttu-id="eea43-141">(Ennek **Szállítmánykonszolidációs irányelv** mezőjének *Rendelésgyűjtő* értékűnek kell lennie.)</span><span class="sxs-lookup"><span data-stu-id="eea43-141">(Its **Shipment consolidation policy** field should be set to *Order pool*.)</span></span>
1. <span data-ttu-id="eea43-142">A Művelet panel **Szállítmányok** lapján válassza a **Szállítmányok \> Szállítmányok konszolidálása** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="eea43-142">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="eea43-143">Ellenőrizze a konszolidálásra javasolt szállítmányokat.</span><span class="sxs-lookup"><span data-stu-id="eea43-143">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="eea43-144">A rendszer csak egyetlen olyan szállítmányt javasolhat a konszolidálásra, amelynek ugyanaz az irányelve.</span><span class="sxs-lookup"><span data-stu-id="eea43-144">Only one shipment that has the same policy should be suggested for consolidation.</span></span>
1. <span data-ttu-id="eea43-145">Zárja be a **Szállítmány konszolidációja** oldalt.</span><span class="sxs-lookup"><span data-stu-id="eea43-145">Close the **Shipment consolidation** page.</span></span>
1. <span data-ttu-id="eea43-146">Keresse meg és válassza ki a szállítmányt, amely az 3. értékesítési rendelés raktárba való kiadásakor jött létre.</span><span class="sxs-lookup"><span data-stu-id="eea43-146">Find and select a shipment that was created when sales order 3 was released to the warehouse.</span></span> <span data-ttu-id="eea43-147">(Ennek **Szállítmánykonszolidációs irányelv** mezőjének *Alapértelmezett* értékűnek kell lennie.)</span><span class="sxs-lookup"><span data-stu-id="eea43-147">(Its **Shipment consolidation policy** field should be set to *Default*.)</span></span>
1. <span data-ttu-id="eea43-148">A Művelet panel **Szállítmányok** lapján válassza a **Szállítmányok \> Szállítmányok konszolidálása** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="eea43-148">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="eea43-149">Ellenőrizze, hogy nincs konszolidálásra javasolt szállítmány.</span><span class="sxs-lookup"><span data-stu-id="eea43-149">Verify that no shipments are suggested for consolidation.</span></span>
1. <span data-ttu-id="eea43-150">Válassza ki a **Szűrők megjelenítése** elemet.</span><span class="sxs-lookup"><span data-stu-id="eea43-150">Select **Show filters**.</span></span>
1. <span data-ttu-id="eea43-151">A **szűrők** ablaktáblán távolítsa el a **Rendelésszám** szűrőt, majd válassza az **alkalmazás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="eea43-151">In the **Filters** pane, remove the **Order number** filter, and then select **Apply**.</span></span>
1. <span data-ttu-id="eea43-152">Ellenőrizze a konszolidálásra javasolt szállítmányokat.</span><span class="sxs-lookup"><span data-stu-id="eea43-152">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="eea43-153">A rendszer csak egyetlen olyan szállítmányt javasolhat a konszolidálásra, amelynek ugyanaz az irányelve.</span><span class="sxs-lookup"><span data-stu-id="eea43-153">Only one shipment that has the same policy should be suggested for consolidation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eea43-154">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="eea43-154">Additional resources</span></span>

- [<span data-ttu-id="eea43-155">Szállítmánykonszolidációs irányelvek</span><span class="sxs-lookup"><span data-stu-id="eea43-155">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="eea43-156">Szállítmánykonszolidációs irányelvek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="eea43-156">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)