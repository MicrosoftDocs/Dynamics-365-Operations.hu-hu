---
title: Szállítmányok konszolidálása a raktárba történő kiadáskor Értékesítési rendelések automatikus kiadása funkció használatával
description: Ez a témakör olyan esetet mutat be, amikor több rendelést adnak ki a raktárba ugyanabban az automatizált raktárba történő kiadás időszakos eljárásában.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 376c7418b61c0192f9071a879b50b9ece7699894
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970356"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a><span data-ttu-id="4ebb0-103">Szállítmányok konszolidálása a raktárba történő kiadáskor Értékesítési rendelések automatikus kiadása funkció használatával</span><span class="sxs-lookup"><span data-stu-id="4ebb0-103">Consolidate shipments when they are released to the warehouse by using Automatic release of sales orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ebb0-104">Ez a témakör olyan esetet mutat be, amikor több rendelést adnak ki a raktárba ugyanabban az automatizált raktárba történő kiadás időszakos eljárásában.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-104">This topic presents a scenario where multiple orders are released to the warehouse in the same automated release-to-warehouse periodic procedure.</span></span> <span data-ttu-id="4ebb0-105">A rendeléseket a program automatikusan konszolidálja szállítmányokba, a szállítási konszolidációs irányelvként meghatározott szabályok alapján.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-105">The orders will automatically be consolidated into shipments, based on rules that are defined as shipment consolidation policies.</span></span>

<span data-ttu-id="4ebb0-106">A forgatókönyv során értékesítési rendelések készletét hozza létre, és minden készletet kiad a raktárba.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-106">During the scenario, you will create sets of sales orders and release each set to the warehouse.</span></span> <span data-ttu-id="4ebb0-107">Ezt követően megtekintheti a szállítmánykonszolidáció során létrehozott vagy frissített szállítmányokat a konfigurált irányelvek alapján.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-107">You will then review the shipments that are created or updated during shipment consolidation, based on the configured policies.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="4ebb0-108">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="4ebb0-108">Make demo data available</span></span>

<span data-ttu-id="4ebb0-109">Az ebben a témakörben szereplő minden egyes forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Microsoft Dynamics 365 Supply Chain Management szolgáltatáshoz biztosított standard bemutatóadatokban.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-109">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="4ebb0-110">Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-110">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="4ebb0-111">Szállítmánykonszolidációs irányelvek és a termékszűrők beállítása</span><span class="sxs-lookup"><span data-stu-id="4ebb0-111">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="4ebb0-112">Az itt ismertetett eset feltételezi, hogy már be van kapcsolva a funkció, és végrehajtotta a [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md) részben szereplő gyakorlatokat, és létrehozta az ott ismertetett irányelveket és más rekordokat.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-112">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="4ebb0-113">A jelen forgatókönyv végrehajtása előtt győződjön meg arról, hogy elvégezte azokat a gyakorlatokat.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-113">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="4ebb0-114">Értékesítési rendelések létrehozása ehhez a forgatókönyvhöz</span><span class="sxs-lookup"><span data-stu-id="4ebb0-114">Create the sales orders for this scenario</span></span>

<span data-ttu-id="4ebb0-115">Első lépésként hozza létre a munkához használni kívánt értékesítési rendelések gyűjteményét.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-115">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="4ebb0-116">A speciális raktár (WMS) folyamataihoz engedélyezett raktárral kell dolgoznia.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-116">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="4ebb0-117">Ha külön nem említik a másik raktárat, akkor ugyanazt a raktárat kell használni a következő rendelések mindegyikéhez.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-117">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="4ebb0-118">Nyissa meg a **Kinnlevőségek \> Rendelések \> Összes értékesítési rendelés** pontot, és hozza létre az értékesítési rendelések gyűjteményét, amelyek a következő alszakaszokban szereplő beállításokkal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-118">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="4ebb0-119">1. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="4ebb0-119">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="4ebb0-120">1-1. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="4ebb0-120">Sales order 1-1</span></span>

1. <span data-ttu-id="4ebb0-121">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-121">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-122">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-122">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4ebb0-123">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-123">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="4ebb0-124">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-124">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-125">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-125">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-126">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-126">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="4ebb0-127">1-2. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="4ebb0-127">Sales order 1-2</span></span>

1. <span data-ttu-id="4ebb0-128">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-128">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-129">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-129">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4ebb0-130">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-130">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="4ebb0-131">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-131">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-132">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-132">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-133">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-133">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="4ebb0-134">1-3. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="4ebb0-134">Sales order 1-3</span></span>

1. <span data-ttu-id="4ebb0-135">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-135">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-136">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-136">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4ebb0-137">**Szállítás módja:** *10*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-137">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="4ebb0-138">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-138">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-139">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-139">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-140">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-140">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="4ebb0-141">Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-142">**Cikkszám:** *A0002* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-143">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="4ebb0-144">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-144">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="4ebb0-145">2. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="4ebb0-145">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="4ebb0-146">2-1. és 2-2. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="4ebb0-146">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="4ebb0-147">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-147">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4ebb0-148">**Vevőkód** *US-002*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-148">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="4ebb0-149">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-149">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-150">**Cikkszám:** *M9200* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Gyúlékony*)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-150">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="4ebb0-151">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-151">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="4ebb0-152">Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-152">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-153">**Cikkszám:** *M9201* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Robbanásveszélyes*)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-153">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="4ebb0-154">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-154">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="4ebb0-155">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-155">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="4ebb0-156">3. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="4ebb0-156">Create order set 3</span></span>

#### <a name="sales-order-3-1"></a><span data-ttu-id="4ebb0-157">3-1. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="4ebb0-157">Sales order 3-1</span></span>

1. <span data-ttu-id="4ebb0-158">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-158">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-159">**Vevőkód** *US-002*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-159">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="4ebb0-160">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-160">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-161">**Cikkszám:** *M9200* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Gyúlékony*)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-161">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="4ebb0-162">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-162">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="4ebb0-163">Adjon hozzá egy második rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-163">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-164">**Cikkszám:** *M9201* (olyan cikk, amelynél a **4.kód** szűrő beállítása *Robbanásveszélyes*)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-164">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="4ebb0-165">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-165">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="4ebb0-166">**Szállítási mód:** *Légitá-légi*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-166">**Mode of delivery:** *Airwa-Air*</span></span>

> [!NOTE]
> <span data-ttu-id="4ebb0-167">Ez a rendelés megegyezik azzal a két rendeléssel, amelyet a 2. rendelési készlethez hozott létre.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-167">This order is identical to the two orders that you created for order set 2.</span></span> <span data-ttu-id="4ebb0-168">A program azonban a saját rendeléskészletként jeleníti meg, mert a későbbiekben ezt a forgatókönyvet külön kell kiadni.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-168">However, it's listed as its own order set because you will release it separately later in this scenario.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="4ebb0-169">4. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="4ebb0-169">Create order set 4</span></span>

#### <a name="sales-order-4-1"></a><span data-ttu-id="4ebb0-170">4-1. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="4ebb0-170">Sales order 4-1</span></span>

1. <span data-ttu-id="4ebb0-171">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-171">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-172">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-172">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4ebb0-173">**Vevői igénylés:** *1*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-173">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="4ebb0-174">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-174">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-175">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-175">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-176">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-176">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-5"></a><span data-ttu-id="4ebb0-177">5. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="4ebb0-177">Create order set 5</span></span>

#### <a name="sales-orders-5-1-and-5-2"></a><span data-ttu-id="4ebb0-178">5-1. és 5-2. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="4ebb0-178">Sales orders 5-1 and 5-2</span></span>

1. <span data-ttu-id="4ebb0-179">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4ebb0-180">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-180">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4ebb0-181">**Vevői igénylés:** *2*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-181">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="4ebb0-182">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-182">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-183">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-183">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-184">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-184">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-5-3"></a><span data-ttu-id="4ebb0-185">5-3. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="4ebb0-185">Sales order 5-3</span></span>

1. <span data-ttu-id="4ebb0-186">Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-186">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-187">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-187">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="4ebb0-188">**Vevői igénylés:** *1*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-188">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="4ebb0-189">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-189">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-190">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-190">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-191">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-191">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-6"></a><span data-ttu-id="4ebb0-192">6. rendeléskészlet létrehozása</span><span class="sxs-lookup"><span data-stu-id="4ebb0-192">Create order set 6</span></span>

#### <a name="sales-orders-6-1-and-6-2"></a><span data-ttu-id="4ebb0-193">6-1. és 6-2. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="4ebb0-193">Sales orders 6-1 and 6-2</span></span>

1. <span data-ttu-id="4ebb0-194">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-194">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4ebb0-195">**Vevőkód** *US-003*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-195">**Customer account:** *US-003*</span></span>
    - <span data-ttu-id="4ebb0-196">**Vevői igénylés:** *2*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-196">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="4ebb0-197">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-198">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-199">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-199">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-3-and-6-4"></a><span data-ttu-id="4ebb0-200">6-3. és 6-4. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="4ebb0-200">Sales orders 6-3 and 6-4</span></span>

1. <span data-ttu-id="4ebb0-201">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-201">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4ebb0-202">**Vevőkód** *US-004*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-202">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="4ebb0-203">**Vevői igénylés:** *1*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-203">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="4ebb0-204">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-204">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-205">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-205">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-206">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-206">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-5-and-6-6"></a><span data-ttu-id="4ebb0-207">6-5. és 6-6. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="4ebb0-207">Sales orders 6-5 and 6-6</span></span>

1. <span data-ttu-id="4ebb0-208">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-208">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4ebb0-209">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-209">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="4ebb0-210">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-210">**Site:** *6*</span></span>
    - <span data-ttu-id="4ebb0-211">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-211">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="4ebb0-212">**Gyűjtő:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-212">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="4ebb0-213">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-213">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-214">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-214">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-215">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-215">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-7-and-6-8"></a><span data-ttu-id="4ebb0-216">6-7. és 6-8. értékesítési rendelések</span><span class="sxs-lookup"><span data-stu-id="4ebb0-216">Sales orders 6-7 and 6-8</span></span>

1. <span data-ttu-id="4ebb0-217">Hozzon létre két egyforma olyan értékesítési rendelést, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-217">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="4ebb0-218">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-218">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="4ebb0-219">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-219">**Site:** *6*</span></span>
    - <span data-ttu-id="4ebb0-220">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-220">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="4ebb0-221">**Gyűjtő:** Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-221">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="4ebb0-222">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-222">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="4ebb0-223">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="4ebb0-223">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="4ebb0-224">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-224">**Quantity:** *1.00*</span></span>

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a><span data-ttu-id="4ebb0-225">Értékesítési rendelések automatikus kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="4ebb0-225">Automatic release of sales orders to the warehouse</span></span>

<span data-ttu-id="4ebb0-226">A korábban létrehozott értékesítési rendelések mindegyik készletéhez végre kell hajtania egy eljárást a raktárba történő automatikus kiadáshoz.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-226">For each set of sales orders that you created earlier, you will complete a procedure for automatic release to the warehouse.</span></span> <span data-ttu-id="4ebb0-227">Minden esetben az itt megadott [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) kell végrehajtania.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-227">In each case, you will work through the [basic release-to-warehouse procedure](#release-procedure) that is provided here.</span></span>

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a><span data-ttu-id="4ebb0-228">Alapszintű eljárás raktárba történő kiadáshoz</span><span class="sxs-lookup"><span data-stu-id="4ebb0-228">Basic release-to-warehouse procedure</span></span>

<span data-ttu-id="4ebb0-229">A korábban létrehozott értékesítési rendelések mindegyik készletéhez végre kell hajtania a következő alszakaszban ismertetett három eljárást.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-229">For each set of sales orders that you created earlier, you will complete the three procedures that are outlined in the following subsections.</span></span>

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a><span data-ttu-id="4ebb0-230">A kiadás során használandó hullámsablon frissítése</span><span class="sxs-lookup"><span data-stu-id="4ebb0-230">Update the wave template that will be used during release</span></span>

1. <span data-ttu-id="4ebb0-231">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-231">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="4ebb0-232">Állítsa a **Hullámsablontípus** mezőt *Szállítás* értékre.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-232">Set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="4ebb0-233">Keresse meg és válassza ki azt a hullámsablont, amely az adott esethez létrehozott rendeléskészletekben használt raktárhoz van társítva.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-233">Find and select the wave template that is associated with the warehouse that you used in the order sets that you created for this scenario.</span></span> <span data-ttu-id="4ebb0-234">Ha például a *24*-es számú raktárat használta, akkor válassza a **24 – szállítás – alapértelmezett** hullámsablont.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-234">For example, if you used warehouse *24*, select the **24 Shipping Default** wave template.</span></span> <span data-ttu-id="4ebb0-235">Ha a *61*-es számú raktárat használta, akkor válassza a **61 – szállítás** hullámsablont.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-235">If you used warehouse *61*, select the **61 Shipping** wave template.</span></span>
1. <span data-ttu-id="4ebb0-236">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-236">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="4ebb0-237">Állítsa a **Hullám feldolgozása a raktárba történő kiadáskor** lehetőséget *Nem* értékre.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-237">Set the **Process wave at release to warehouse** option to *No*.</span></span>

#### <a name="release-to-the-warehouse"></a><span data-ttu-id="4ebb0-238">Kiadás a raktárba</span><span class="sxs-lookup"><span data-stu-id="4ebb0-238">Release to the warehouse</span></span>

1. <span data-ttu-id="4ebb0-239">Nyissa meg a **Raktárkezelés \> Kiadás a raktárba \> Értékesítési rendelések automatikus kiadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-239">Go to **Warehouse management \> Release to warehouse \> Automatic release of sales orders**.</span></span>
1. <span data-ttu-id="4ebb0-240">Állítsa a **Kiadandó mennyiség** mezőt *Mind* értékre.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-240">Set the **Quantity to release** field to *All*.</span></span>
1. <span data-ttu-id="4ebb0-241">A **Szerepeltetni kívánt rekordok** gyorslapján válassza a **Szűrő** parancsot, hogy megnyíljon a lekérdezés párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-241">On the **Records to include** FastTab, select **Filter** to open the query dialog box.</span></span>
1. <span data-ttu-id="4ebb0-242">A **Tartomány** lapon a **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-242">On the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="4ebb0-243">**Tábla:** *Értékesítési rendelés*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-243">**Table:** *Sales order*</span></span>
    - <span data-ttu-id="4ebb0-244">**Származtatott tábla:** *Értékesítési rendelés*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-244">**Derived table:** *Sales order*</span></span>
    - <span data-ttu-id="4ebb0-245">**Mező:** *Értékesítési rendelés*</span><span class="sxs-lookup"><span data-stu-id="4ebb0-245">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="4ebb0-246">**Feltételek:** Adja meg az értékesítési rendelések számának vesszővel tagolt listáját a kívánt rendelési készletből.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-246">**Criteria:** Enter a comma-separated list of the sales order numbers from the desired order set.</span></span>

1. <span data-ttu-id="4ebb0-247">A lekérdezés mentéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-247">Select **OK** to save your query.</span></span>
1. <span data-ttu-id="4ebb0-248">Az **OK** gombra kattintva elindíthatja az *Automatikus kiadás a raktárba* eljárást.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-248">Select **OK** to start the *Automatic release to warehouse* procedure.</span></span>

#### <a name="review-the-shipment-that-is-created-or-updated"></a><span data-ttu-id="4ebb0-249">A létrehozott vagy frissített szállítmány áttekintése</span><span class="sxs-lookup"><span data-stu-id="4ebb0-249">Review the shipment that is created or updated</span></span>

1. <span data-ttu-id="4ebb0-250">Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-250">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="4ebb0-251">Keresse meg és válassza ki a kívánt szállítmányt.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-251">Find and select the required shipment.</span></span>
1. <span data-ttu-id="4ebb0-252">Ha a szállítmány létrehozásakor használt konszolidációs irányelvet létrehozzák vagy frissítik, akkor meg kell jelennie a **Szállítmánykonszolidációs irányelv** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-252">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-sales-orders-from-order-set-1"></a><span data-ttu-id="4ebb0-253">Értékesítési rendelések kiadása az 1. rendeléskészletből</span><span class="sxs-lookup"><span data-stu-id="4ebb0-253">Release sales orders from order set 1</span></span>

<span data-ttu-id="4ebb0-254">Az 1. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-254">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 1.</span></span>

<span data-ttu-id="4ebb0-255">Ha befejezte a munkát, akkor azt kell látnia, hogy két szállítmány jött létre:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-255">When you've finished, you should see that two shipments were created:</span></span>

- <span data-ttu-id="4ebb0-256">Az első szállítmány három sort tartalmaz, és a *CustomerMode* szállítmánykonszolidációs irányelv használatával jött létre.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-256">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="4ebb0-257">A második szállítmányt, amely nem a *Légitársaságok* szállítási módot használja, a *CustomerOrderNo* szállítmánykonszolidációs irányelv használatával hozták létre.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-257">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-sales-orders-from-order-set-2"></a><span data-ttu-id="4ebb0-258">Értékesítési rendelések kiadása a 2. rendeléskészletből</span><span class="sxs-lookup"><span data-stu-id="4ebb0-258">Release sales orders from order set 2</span></span>

<span data-ttu-id="4ebb0-259">A 2. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-259">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 2.</span></span>

<span data-ttu-id="4ebb0-260">Ha befejezte a munkát, akkor azt kell látnia, hogy három szállítmány jött létre:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-260">When you've finished, you should see that three shipments were created:</span></span>

- <span data-ttu-id="4ebb0-261">Az első szállítmány *Gyúlékony* cikkeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-261">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="4ebb0-262">A másik két szállítmány mindegyike egy sort tartalmaz, amelyben a *Robbanásveszélyes* cikk szerepel.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-262">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-3"></a><span data-ttu-id="4ebb0-263">Értékesítési rendelések kiadása a 3. rendeléskészletből</span><span class="sxs-lookup"><span data-stu-id="4ebb0-263">Release sales orders from order set 3</span></span>

<span data-ttu-id="4ebb0-264">A 3. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-264">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 3.</span></span>

<span data-ttu-id="4ebb0-265">Ha befejezte a műveletet, a következő műveletek végrehajtását kell látnia:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-265">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="4ebb0-266">Egy létező szállítmány frissült (a 2. rendeléskészlet raktárba való kiadásakor létrejött szállítmány).</span><span class="sxs-lookup"><span data-stu-id="4ebb0-266">One existing shipment (the shipment that was created when order set 2 was released to the warehouse) was updated.</span></span> <span data-ttu-id="4ebb0-267">A sor, amelyhez a *Gyúlékony* cikk lett hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-267">A line that has the *Flammable* item was added.</span></span>
- <span data-ttu-id="4ebb0-268">Létrejött egy új szállítmány, amelyben a *Robbanásveszélyes* cikk szerepel.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-268">One new shipment was created that contains the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-4"></a><span data-ttu-id="4ebb0-269">Értékesítési rendelések kiadása a 4. rendeléskészletből</span><span class="sxs-lookup"><span data-stu-id="4ebb0-269">Release sales orders from order set 4</span></span>

<span data-ttu-id="4ebb0-270">A 4. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-270">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 4.</span></span>

<span data-ttu-id="4ebb0-271">Ha befejezte a munkát, akkor látnia kell, hogy egy meglévő szállítmány frissült (ahol a **Vevői igénylés** mező értéke *1*).</span><span class="sxs-lookup"><span data-stu-id="4ebb0-271">When you've finished, you should see that one existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="4ebb0-272">Egy új sor lett hozzáadva a szállítmányhoz.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-272">One new line was added to it.</span></span>

### <a name="release-sales-orders-from-order-set-5"></a><span data-ttu-id="4ebb0-273">Értékesítési rendelések kiadása az 5. rendeléskészletből</span><span class="sxs-lookup"><span data-stu-id="4ebb0-273">Release sales orders from order set 5</span></span>

<span data-ttu-id="4ebb0-274">Az 5. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-274">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 5.</span></span>

<span data-ttu-id="4ebb0-275">Ha befejezte a műveletet, a következő műveletek végrehajtását kell látnia:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-275">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="4ebb0-276">Egy meglévő szállítmány frissült (ahol a **Vevői igénylés** mező értéke *1*).</span><span class="sxs-lookup"><span data-stu-id="4ebb0-276">One existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="4ebb0-277">A rendszer hozzáadta az 5-3. értékesítési rendelés (ahol a **Vevői igénylés** mező értéke *1*) egyik sorát.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-277">A line from sales order 5-3 (where the **Customer requisition** field is set to *1*) was added to it.</span></span>
- <span data-ttu-id="4ebb0-278">Egy új szállítmány jött létre, ahol az 5-1. és 5-2. értékesítési rendelések sorai egyetlen szállítmányba vannak csoportosítva.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-278">One new shipment was created, where lines from sales orders 5-1 and 5-2 are grouped into one shipment.</span></span>

### <a name="release-sales-orders-from-order-set-6"></a><span data-ttu-id="4ebb0-279">Értékesítési rendelések kiadása a 6. rendeléskészletből</span><span class="sxs-lookup"><span data-stu-id="4ebb0-279">Release sales orders from order set 6</span></span>

<span data-ttu-id="4ebb0-280">A 6. rendeléskészlet értékesítési rendeléseinek kiadásához kövesse az [Alapszintű eljárás raktárba történő kiadáshoz](#release-procedure) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-280">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 6.</span></span>

<span data-ttu-id="4ebb0-281">Ha befejezte a munkát, akkor azt kell látnia, hogy négy szállítmány jött létre:</span><span class="sxs-lookup"><span data-stu-id="4ebb0-281">When you've finished, you should see that four shipments were created:</span></span>

- <span data-ttu-id="4ebb0-282">Az *US-003* vevő két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-282">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="4ebb0-283">Az *US-004* vevő két rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-283">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="4ebb0-284">Az *US-007* vevő 6-5. és 6-6. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *Rendelésgyűjtő* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-284">Lines from sales orders 6-5 and 6-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="4ebb0-285">Az *US-007* vevő 6-7. és 6-8. értékesítési rendelésének sorait egyetlen szállítmányba csoportosították a *CrossOrder* szállítmánykonszolidációs irányelv használatával.</span><span class="sxs-lookup"><span data-stu-id="4ebb0-285">Lines from sales orders 6-7 and 6-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ebb0-286">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4ebb0-286">Additional resources</span></span>

- [<span data-ttu-id="4ebb0-287">Szállítmánykonszolidációs irányelvek</span><span class="sxs-lookup"><span data-stu-id="4ebb0-287">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="4ebb0-288">Szállítmánykonszolidációs irányelvek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="4ebb0-288">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
