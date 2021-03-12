---
title: Szállítmányok konszolidálása, amikor a szállítmánykonszolidációs irányelv felülírásra kerül a Kiadástól a raktárba lapról
description: Ez a témakör egy olyan esetet mutat be, amikor egy vagy több értékesítési sort manuálisan kell kiadni a raktárba a Kiadás a raktárba oldalról, és a rendszer által definiált szállítmánykonszolidációs irányelvet felül kell írni a kiadás előtt.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 4aaaa7949d988607b38dd6e38a3c3497f227b8af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963335"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden-from-the-release-to-warehouse-page"></a><span data-ttu-id="52dda-103">Szállítmányok konszolidálása, amikor a szállítmánykonszolidációs irányelv felülírásra kerül a Kiadástól a raktárba lapról</span><span class="sxs-lookup"><span data-stu-id="52dda-103">Consolidate shipments when the shipment consolidation policy is overridden from the Release to warehouse page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52dda-104">Ez a témakör egy olyan esetet mutat be, amikor egy vagy több értékesítési sort manuálisan kell kiadni a raktárba a **Kiadás a raktárba** oldalról, és a rendszer által definiált szállítmánykonszolidációs irányelvet felül kell írni a kiadás előtt.</span><span class="sxs-lookup"><span data-stu-id="52dda-104">This topic presents a scenario where one or more sales lines must be manually released to the warehouse from the **Release to warehouse** page, and the system-defined shipment consolidation policy must be overridden before the release.</span></span> <span data-ttu-id="52dda-105">Előfordulhat, hogy a szállítmánykonszolidációs irányelvének felülbírálására szükség lehet, ha például egy olyan rendelést, amelynél a nyitott szállítmányok általában nem lettek összesítve, nyitott szállítmányokkal kell összesíteni.</span><span class="sxs-lookup"><span data-stu-id="52dda-105">An override of the shipment consolidation policy might be required if, for example, an order that isn't usually consolidated with open shipments must be consolidated with open shipments.</span></span>

<span data-ttu-id="52dda-106">Az eset során létrehoz egy értékesítési rendelést, majd felülírja az alapértelmezett szállítmánykonszolidációs irányelvet, mielőtt a rendeléseket kiadja a raktárba.</span><span class="sxs-lookup"><span data-stu-id="52dda-106">During the scenario, you will create a set of sales orders and then override the default shipment consolidation policy before you release the orders to the warehouse.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="52dda-107">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="52dda-107">Make demo data available</span></span>

<span data-ttu-id="52dda-108">Az ebben a témakörben szereplő minden egyes forgatókönyv olyan értékekre és rekordokra hivatkozik, amelyek szerepelnek a Microsoft Dynamics 365 Supply Chain Management szolgáltatáshoz biztosított standard bemutatóadatokban.</span><span class="sxs-lookup"><span data-stu-id="52dda-108">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="52dda-109">Ha azt szeretné, hogy az itt megadott értékeket használja a feladatok végrehajtásához, akkor győződjön meg róla, hogy olyan környezetben dolgozik, ahol a bemutatóadatokat telepítették, és a jogi személy beállítása legyen **USMF**.</span><span class="sxs-lookup"><span data-stu-id="52dda-109">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="52dda-110">Szállítmánykonszolidációs irányelvek és a termékszűrők beállítása</span><span class="sxs-lookup"><span data-stu-id="52dda-110">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="52dda-111">Az itt ismertetett eset feltételezi, hogy már be van kapcsolva a funkció, és végrehajtotta a [Szállítmánykonszolidációs irányelvek konfigurálása](configure-shipment-consolidation-policies.md) részben szereplő gyakorlatokat, és létrehozta az ott ismertetett irányelveket és más rekordokat.</span><span class="sxs-lookup"><span data-stu-id="52dda-111">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="52dda-112">A jelen forgatókönyv végrehajtása előtt győződjön meg arról, hogy elvégezte azokat a gyakorlatokat.</span><span class="sxs-lookup"><span data-stu-id="52dda-112">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="52dda-113">Értékesítési rendelések létrehozása ehhez a forgatókönyvhöz</span><span class="sxs-lookup"><span data-stu-id="52dda-113">Create the sales orders for this scenario</span></span>

1. <span data-ttu-id="52dda-114">Ugorjon a **Kinnlevőségek \> Rendelések \> Összes értékesítési rendelés** lehetőséghez, és hozza létre a következő beállításokat tartalmazó három azonos értékesítési rendelést:</span><span class="sxs-lookup"><span data-stu-id="52dda-114">Go to **Accounts receivable \> Orders \> All sales orders**, and create three identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="52dda-115">**Vevőkód** *US-002*</span><span class="sxs-lookup"><span data-stu-id="52dda-115">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="52dda-116">Adjon hozzá egy olyan rendelési sort, amelynek beállításai a következők:</span><span class="sxs-lookup"><span data-stu-id="52dda-116">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="52dda-117">**Cikkszám:** *A0001* (olyan cikk, amelyhez nem tartozik **4.kód** szűrő)</span><span class="sxs-lookup"><span data-stu-id="52dda-117">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="52dda-118">**Mennyiség:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="52dda-118">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="52dda-119">Válassza a **Készlet \> Foglalás** elemet, majd a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor foglalásához.</span><span class="sxs-lookup"><span data-stu-id="52dda-119">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a><span data-ttu-id="52dda-120">Értékesítési rendelések kiadása a Kiadás a raktárba oldalról</span><span class="sxs-lookup"><span data-stu-id="52dda-120">Release the sales orders from the Release to warehouse page</span></span>

<span data-ttu-id="52dda-121">Hajtsa végre a következő lépéseket a szállítmánykonszolidációs irányelv felülbírálásához a raktárba történő kiadás során.</span><span class="sxs-lookup"><span data-stu-id="52dda-121">Follow these steps to override the shipment consolidation policy during the release to the warehouse.</span></span>

1. <span data-ttu-id="52dda-122">Ugrás a **Raktárkezelés \> Kiadás a raktárba \> Kiadás a raktárba**.</span><span class="sxs-lookup"><span data-stu-id="52dda-122">Go to **Warehouse management \> Release to warehouse \> Release to warehouse**.</span></span>
1. <span data-ttu-id="52dda-123">A felső panelen válassza ki az ehhez az esethez létrehozott első értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="52dda-123">In the upper pane, select the first sales order that you created for this scenario.</span></span>
1. <span data-ttu-id="52dda-124">Válassza a **Hozzáadás** gombot, hogy a sort kiadja a raktárba.</span><span class="sxs-lookup"><span data-stu-id="52dda-124">Select **Add** to add the line to the release to the warehouse.</span></span> <span data-ttu-id="52dda-125">Figyelje meg, hogy az alsó panelre az *Alapértelmezett* szállítmánykonszolidációs irányelv vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="52dda-125">Notice that the *Default* shipment consolidation policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="52dda-126">Az alsó panelen válassza az **Új szállítmánykonszolidációs irányelv kiválasztása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52dda-126">In the bottom pane, select **Select new shipment consolidation policy**.</span></span>
1. <span data-ttu-id="52dda-127">Válasszon ki egy olyan irányelvet, amely lehetővé teszi a konszolidációt ugyanazon irányelv egyéb nyitott szállítmányai esetében.</span><span class="sxs-lookup"><span data-stu-id="52dda-127">Select a policy that allows for consolidation with other open shipments of the same policy.</span></span> <span data-ttu-id="52dda-128">Például válassza ki a *CustomerOrderNo* irányelvet.</span><span class="sxs-lookup"><span data-stu-id="52dda-128">For example, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="52dda-129">Válassza ki a **Kiadás a raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52dda-129">Select **Release to warehouse**.</span></span>
1. <span data-ttu-id="52dda-130">Válassza ki az ehhez az esethez létrehozott második és harmadik értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="52dda-130">Select the second and third sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="52dda-131">Válassza a **Hozzáadás** gombot, hogy a sort kiadja a raktárba.</span><span class="sxs-lookup"><span data-stu-id="52dda-131">Select **Add** to add the lines to the release to the warehouse.</span></span> <span data-ttu-id="52dda-132">Figyelje meg, hogy az alsó panelre az *Alapértelmezett* irányelv vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="52dda-132">Notice that the *Default* policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="52dda-133">Válassza ki a második sort, majd az **Új szállítmánykonszolidációs irányelv kiválasztása** mezőben válassza ki a *CustomerOrderNo* irányelvet.</span><span class="sxs-lookup"><span data-stu-id="52dda-133">Select the second line, and then, in the **Select new shipment consolidation policy** field, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="52dda-134">Mindkét sor esetében válassza a **Kiadás a raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="52dda-134">Select **Release to warehouse** for both lines.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="52dda-135">Szállítmányok ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="52dda-135">Verify the shipments</span></span>

<span data-ttu-id="52dda-136">Két szállítmányt kellett létrehozni:</span><span class="sxs-lookup"><span data-stu-id="52dda-136">Two shipments should have been created:</span></span>

- <span data-ttu-id="52dda-137">Az első szállítmány két sort tartalmaz, és a *CustomerOrderNo* szállítmánykonszolidációs irányelv használatával jött létre.</span><span class="sxs-lookup"><span data-stu-id="52dda-137">The first shipment contains two lines and was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>
- <span data-ttu-id="52dda-138">A második szállítmány egy sort tartalmaz, és az *Alapértelmezett* szállítmánykonszolidációs irányelv használatával jött létre.</span><span class="sxs-lookup"><span data-stu-id="52dda-138">The second shipment contains one line and was created by using the *Default* shipment consolidation policy.</span></span>

<span data-ttu-id="52dda-139">A létrehozott szállítmányok áttekintéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="52dda-139">Follow these steps to review the shipments that were created.</span></span>

1. <span data-ttu-id="52dda-140">Lépjen a **Raktárkezelés \> Szállítmányok \> Minden szállítmány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="52dda-140">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="52dda-141">Keresse meg és válassza ki a kívánt szállítmányt.</span><span class="sxs-lookup"><span data-stu-id="52dda-141">Find and select the required shipment.</span></span>
1. <span data-ttu-id="52dda-142">A **Szállítmánykonszolidációs rányelv** mezőjében ellenőrizze a szállítmány létrehozásakor használt konszolidációs irányelvet.</span><span class="sxs-lookup"><span data-stu-id="52dda-142">In the **Shipment consolidation policy** field, review the consolidation policy that was used when the shipment was created.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52dda-143">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="52dda-143">Additional resources</span></span>

- [<span data-ttu-id="52dda-144">Szállítmánykonszolidációs irányelvek</span><span class="sxs-lookup"><span data-stu-id="52dda-144">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="52dda-145">Szállítmánykonszolidációs irányelvek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="52dda-145">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
