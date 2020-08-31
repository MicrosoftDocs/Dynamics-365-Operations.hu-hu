---
title: Munkagyűjtő módosítása a munkán
description: Ez a témakör azt mutatja be, hogy hogyan lehet módosítani a Munkagyűjtő módosítása gombot a munkaelemekhez a meglévő munka munkagyűjtőjének módosításához.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 344918b77334f9aca11f799f8c031047ad229ee0
ms.sourcegitcommit: d25d0feb3f8a5a760eba50ba5f46e1db02737d25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/10/2020
ms.locfileid: "3677362"
---
# <a name="change-work-pool-on-work"></a><span data-ttu-id="5650a-103">Munkagyűjtő módosítása a munkán</span><span class="sxs-lookup"><span data-stu-id="5650a-103">Change work pool on work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5650a-104">Munkagyűjtők segítségével a munkát csoportokba rendezheti.</span><span class="sxs-lookup"><span data-stu-id="5650a-104">You can use work pools to organize work into groups.</span></span> <span data-ttu-id="5650a-105">Például létrehozhat egy munkagyűjtőt, hogy osztályozza azt a munkát, amelyet egy adott raktárhelyen történik.</span><span class="sxs-lookup"><span data-stu-id="5650a-105">For example, you can create a work pool to classify work that occurs in a specific warehouse location.</span></span>

<span data-ttu-id="5650a-106">A *Munka munkagyűjtőjének módosítása* funkció hozzáadja a **Munkagyűjtő módosítása** gombot a munkaelemek műveleti ablaktáblájához.</span><span class="sxs-lookup"><span data-stu-id="5650a-106">The *Change work pool on work* feature adds a **Change work pool** button to the Action Pane for work items.</span></span> <span data-ttu-id="5650a-107">Így a raktárkezelők egyszerűen módosíthatják a meglévő munka munkagyűjtőjét.</span><span class="sxs-lookup"><span data-stu-id="5650a-107">Therefore, warehouse managers can easily change the work pool of existing work.</span></span> <span data-ttu-id="5650a-108">Ez a funkció lehetővé teszi a vezetők gyors reagálását a raktári üzem szintjén, és javítja a változó helyzetekhez való alkalmazkodás képességét, valamint a munka másik munkagyűjtőbe történő áthelyezését.</span><span class="sxs-lookup"><span data-stu-id="5650a-108">This feature lets managers react quickly to changes on the warehouse shop floor, and it helps improve their ability to adapt to changing situations and the need to transfer work to another work pool.</span></span>

## <a name="turn-on-the-change-work-pool-on-work-feature"></a><span data-ttu-id="5650a-109">A Munkagyűjtő módosítása a munkán funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="5650a-109">Turn on the Change work pool on work feature</span></span>

<span data-ttu-id="5650a-110">Mielőtt elkezdené a funkció beállítását vagy használatát, győződjön meg arról, hogy az elérhető a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="5650a-110">Before you begin to set up or use this feature, you must make sure that it's available in your system.</span></span> <span data-ttu-id="5650a-111">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="5650a-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="5650a-112">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="5650a-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="5650a-113">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="5650a-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="5650a-114">**Funkció neve:** *Munkagyűjtő módosítása a munkán*</span><span class="sxs-lookup"><span data-stu-id="5650a-114">**Feature name:** *Change work pool on work*</span></span>

## <a name="set-up-the-change-work-pool-on-work-feature"></a><span data-ttu-id="5650a-115">A Munkagyűjtő módosítása a munkán funkció beállítása</span><span class="sxs-lookup"><span data-stu-id="5650a-115">Set up the Change work pool on work feature</span></span>

<span data-ttu-id="5650a-116">Ez a funkció csak akkor használható, ha be van állítva néhány munkagyűjtő.</span><span class="sxs-lookup"><span data-stu-id="5650a-116">To use this feature, you must have some work pools set up.</span></span> <span data-ttu-id="5650a-117">A munkasablonokat úgy is be lehet állítani, hogy automatikusan társítson egy gyűjtőt.</span><span class="sxs-lookup"><span data-stu-id="5650a-117">You might also set up your work templates so that they automatically assign a pool.</span></span> <span data-ttu-id="5650a-118">Ha szeretne végighaladni a jelen témakörben később megadott példákon, állítsa be a rendszert az ebben a szakaszban ismertetett módon.</span><span class="sxs-lookup"><span data-stu-id="5650a-118">If you want to work through the example scenario that is provided later in this topic, set up your system as described in this section.</span></span>

### <a name="set-up-work-pools"></a><span data-ttu-id="5650a-119">Munkagyűjtők beállítása</span><span class="sxs-lookup"><span data-stu-id="5650a-119">Set up work pools</span></span>

<span data-ttu-id="5650a-120">A munkagyűjtők a munkatételek típus szerinti rendszerezését teszik lehetővé.</span><span class="sxs-lookup"><span data-stu-id="5650a-120">Work pools let you organize work items by type.</span></span> <span data-ttu-id="5650a-121">Ha a *Munkagyűjtő módosítása a munkán* funkcióban szeretne dolgozni, legalább két munkagyűjtőnek elérhetőnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="5650a-121">To work with the *Change work pool on work* feature, you must have at least two work pools available.</span></span> <span data-ttu-id="5650a-122">A Munkagyűjtő megtekintéséhez és hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5650a-122">To view and add work pools, follow these steps.</span></span>

1. <span data-ttu-id="5650a-123">Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkagyűjtők** pontra.</span><span class="sxs-lookup"><span data-stu-id="5650a-123">Go to **Warehouse management \> Setup \> Work \> Work pools**.</span></span>
1. <span data-ttu-id="5650a-124">Ha az **USMF** vállalattól származó demóadatokkal dolgozik , és a jelen témakörben később elvégzi a példát, vegyen fel két olyan munkagyűjtőt, amelyeknek a következő beállításai vannak:</span><span class="sxs-lookup"><span data-stu-id="5650a-124">If you're working with demo data from the **USMF** company and will work through the example scenario later in this topic, add two work pools that have the following settings:</span></span>

    - <span data-ttu-id="5650a-125">1. munkagyűjtő:</span><span class="sxs-lookup"><span data-stu-id="5650a-125">Work pool 1:</span></span>

        - <span data-ttu-id="5650a-126">**Munkagyűjtő azonosítója:** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="5650a-126">**Work pool ID:** *Webshop*</span></span>
        - <span data-ttu-id="5650a-127">**Leírás:** *Webáruház*</span><span class="sxs-lookup"><span data-stu-id="5650a-127">**Description:** *Web Shop*</span></span>

    - <span data-ttu-id="5650a-128">2. munkagyűjtő:</span><span class="sxs-lookup"><span data-stu-id="5650a-128">Work pool 2:</span></span>

        - <span data-ttu-id="5650a-129">**Munkagyűjtő azonosítója:** *CallCenter*</span><span class="sxs-lookup"><span data-stu-id="5650a-129">**Work pool ID:** *CallCenter*</span></span>
        - <span data-ttu-id="5650a-130">**Leírás:** *Hívásközpont*</span><span class="sxs-lookup"><span data-stu-id="5650a-130">**Description:** *Call Center*</span></span>

1. <span data-ttu-id="5650a-131">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5650a-131">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="5650a-132">Munkasablonok beállítása</span><span class="sxs-lookup"><span data-stu-id="5650a-132">Set up work templates</span></span>

<span data-ttu-id="5650a-133">A munkasablonok mindegyikéhez beállíthat egy alapértelmezett munkagyűjtőt, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="5650a-133">For each of your work templates, you can set a default work pool, as you require.</span></span> <span data-ttu-id="5650a-134">Minden megfelelő sablonhoz társítani kell egy munkagyűjtőt a **munkagyűjtő azonosítója** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="5650a-134">For each relevant template, you assign a work pool in the **Work pool ID** column.</span></span> <span data-ttu-id="5650a-135">Ebben az esetben az adott sablon használatával létrejövő összes munkaelem automatikusan örökli a hozzárendelt munkagyűjtőt.</span><span class="sxs-lookup"><span data-stu-id="5650a-135">In this case, all work items that are generated by using a given template automatically inherit the assigned work pool.</span></span> <span data-ttu-id="5650a-136">Ha az **USMF** vállalattól származó demóadatokkal dolgozik , és a jelen témakörben később elvégzi a példát, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5650a-136">If you're working with the demo data from the **USMF** company and will work through the example scenario later in this topic, follow these steps.</span></span>

1. <span data-ttu-id="5650a-137">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="5650a-137">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="5650a-138">A műveleti ablaktáblán válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.</span><span class="sxs-lookup"><span data-stu-id="5650a-138">On the Action Pane, select **Edit** to put the page into editing mode.</span></span>
1. <span data-ttu-id="5650a-139">A következő értékek beállításával módosítsa a sablont:</span><span class="sxs-lookup"><span data-stu-id="5650a-139">Edit the template by setting the following values:</span></span>

    - <span data-ttu-id="5650a-140">**Munkasablon:** *62 Kitárolástól csomagolásig*</span><span class="sxs-lookup"><span data-stu-id="5650a-140">**Work template:** *62 Pick to pack*</span></span>
    - <span data-ttu-id="5650a-141">**Munkagyűjtő azonosítója:** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="5650a-141">**Work pool ID:** *Webshop*</span></span>

1. <span data-ttu-id="5650a-142">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5650a-142">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="5650a-143">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="5650a-143">Example scenario</span></span>

<span data-ttu-id="5650a-144">Ez a példa azt mutatja be, hogyan lehet módosítani egy meglévő munkaelem feldolgozási folyamát a munkagyűjtők megváltoztatásával.</span><span class="sxs-lookup"><span data-stu-id="5650a-144">This scenario shows how to change the stream of processing for an existing work item by changing its work pool.</span></span> <span data-ttu-id="5650a-145">A program a **USMF** vállalattól származó demóadatokat, valamint a korábban a témakörben korábban javasolt beállításokat használja.</span><span class="sxs-lookup"><span data-stu-id="5650a-145">It uses demo data from the **USMF** company and the settings that were suggested earlier in this topic.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="5650a-146">Értékesítési rendelés létrehozása és kiadása a raktárba</span><span class="sxs-lookup"><span data-stu-id="5650a-146">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="5650a-147">Győződjön meg róla, hogy elegendő aktuális készlet van a *A0001* és *A0002* cikkekből a *62*. raktárban.</span><span class="sxs-lookup"><span data-stu-id="5650a-147">Confirm that there is enough on-hand inventory for items *A0001* and *A0002* in warehouse *62*.</span></span> <span data-ttu-id="5650a-148">Nyissa meg a következőt: **Készletkezelés \> Lekérdezések és jelentések \> Aktuális lista**, és szerkessze az alábbiak szerint a szűrőket:</span><span class="sxs-lookup"><span data-stu-id="5650a-148">Go to **Inventory management \> Inquiries and reports \> On-hand list**, and edit the filters as shown here:</span></span>

    - <span data-ttu-id="5650a-149">A **Raktár** érték *62* értékkel kezdődik.</span><span class="sxs-lookup"><span data-stu-id="5650a-149">The **Warehouse** value begins with *62*.</span></span>
    - <span data-ttu-id="5650a-150">A **Cikkszám** értéke vagy *A001* vagy *A002*.</span><span class="sxs-lookup"><span data-stu-id="5650a-150">The **Item number** value is either *A001* or *A002*.</span></span>

    <span data-ttu-id="5650a-151">A demóadatnak egyenként 10 darabnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="5650a-151">Demo data should have a quantity of 10 each.</span></span>

    <span data-ttu-id="5650a-152">Ezután létre kell hoznia egy értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="5650a-152">Next, you must create a sales order.</span></span>

1. <span data-ttu-id="5650a-153">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="5650a-153">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="5650a-154">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="5650a-154">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5650a-155">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="5650a-155">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="5650a-156">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="5650a-156">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="5650a-157">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="5650a-157">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="5650a-158">Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="5650a-158">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="5650a-159">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="5650a-159">The new sales order is opened.</span></span> <span data-ttu-id="5650a-160">Tartalmaznia kell egy új, üres sort az **Értékesítési rendelés sorai** gyorslap rácsán.</span><span class="sxs-lookup"><span data-stu-id="5650a-160">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="5650a-161">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="5650a-161">On this line, set the following values:</span></span>

    - <span data-ttu-id="5650a-162">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="5650a-162">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="5650a-163">**Mennyiség:** *2*</span><span class="sxs-lookup"><span data-stu-id="5650a-163">**Quantity:** *2*</span></span>

1. <span data-ttu-id="5650a-164">A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.</span><span class="sxs-lookup"><span data-stu-id="5650a-164">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="5650a-165">A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.</span><span class="sxs-lookup"><span data-stu-id="5650a-165">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="5650a-166">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5650a-166">Close the page.</span></span>
1. <span data-ttu-id="5650a-167">Az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Sor hozzáadása** lehetőséget, ha másik sort szeretne hozzáadni az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="5650a-167">On the **Sales order lines** FastTab, select **Add line** to add another line to your sales order.</span></span> <span data-ttu-id="5650a-168">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="5650a-168">On this line, set the following values:</span></span>

    - <span data-ttu-id="5650a-169">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="5650a-169">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="5650a-170">**Mennyiség:** *2*</span><span class="sxs-lookup"><span data-stu-id="5650a-170">**Quantity:** *2*</span></span>

1. <span data-ttu-id="5650a-171">A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.</span><span class="sxs-lookup"><span data-stu-id="5650a-171">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="5650a-172">A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.</span><span class="sxs-lookup"><span data-stu-id="5650a-172">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="5650a-173">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5650a-173">Close the page.</span></span>
1. <span data-ttu-id="5650a-174">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5650a-174">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="5650a-175">Olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítót és szállítási azonosítót jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="5650a-175">You receive informational messages that show the wave ID and shipment ID that were created from the release.</span></span> <span data-ttu-id="5650a-176">Jegyezze fel a hullámazonosítót.</span><span class="sxs-lookup"><span data-stu-id="5650a-176">Make a note of the wave ID.</span></span>

### <a name="review-the-outbound-wave"></a><span data-ttu-id="5650a-177">A kimenő hullám felülvizsgálata</span><span class="sxs-lookup"><span data-stu-id="5650a-177">Review the outbound wave</span></span>

1. <span data-ttu-id="5650a-178">Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.</span><span class="sxs-lookup"><span data-stu-id="5650a-178">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="5650a-179">A rácsban keresse meg azt a hullámazonosítót, amelyet az értékesítési rendelés kiadásával hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="5650a-179">In the grid, search for the wave ID that was created from the release of the sales order.</span></span>
1. <span data-ttu-id="5650a-180">A részletek megtekintéséhez válassza ki a hullámazonosítót.</span><span class="sxs-lookup"><span data-stu-id="5650a-180">Select the wave ID to view the details.</span></span>
1. <span data-ttu-id="5650a-181">A **Hullámsorok** gyorslapon győződjön meg róla, hogy az értékesítési rendeléshez meg van jelenítve a szállítási azonosító.</span><span class="sxs-lookup"><span data-stu-id="5650a-181">On the **Wave lines** FastTab, make sure that a shipment ID is shown for the sales order.</span></span>

    > [!TIP]
    > <span data-ttu-id="5650a-182">Ha a **Hullám feldolgozása a raktárba történő kiadáskor** beállítás értéke *Nem* a szállítási hullámsablon beállításaiban, manuálisan kell feldolgoznia a hullámot úgy, hogy a munka létrehozásához a műveleti ablaktábla **Hullám** lapjáról a **Feldolgozás** elemet választja.</span><span class="sxs-lookup"><span data-stu-id="5650a-182">If the **Process wave at release to warehouse** option is set to *No* in the setup for the shipping wave template, you must manually process the wave by selecting **Process** from the **Wave** tab on the Action Pane to create work.</span></span>

1. <span data-ttu-id="5650a-183">Győződjön meg róla, hogy a hullám feldolgozása megtörtént.</span><span class="sxs-lookup"><span data-stu-id="5650a-183">Make sure that the wave has been processed.</span></span> <span data-ttu-id="5650a-184">Ez a feldolgozás létrehozza a szükséges munkát.</span><span class="sxs-lookup"><span data-stu-id="5650a-184">This processing creates the required work.</span></span>

### <a name="view-work-details-and-change-the-work-pool"></a><span data-ttu-id="5650a-185">Munka részleteinek megtekintése és a munkagyűjtők módosítása</span><span class="sxs-lookup"><span data-stu-id="5650a-185">View work details and change the work pool</span></span>

<span data-ttu-id="5650a-186">A **munkarészletek** lapon megtekintheti a létrehozott munkát, és kezelheti a munkagyűjtőt.</span><span class="sxs-lookup"><span data-stu-id="5650a-186">You can use the **Work details** page to view the work that was created and to manage the work pool.</span></span>

1. <span data-ttu-id="5650a-187">Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.</span><span class="sxs-lookup"><span data-stu-id="5650a-187">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="5650a-188">Válassza ki az imént létrehozott munka sorát.</span><span class="sxs-lookup"><span data-stu-id="5650a-188">Select the row for the work that was just created.</span></span> <span data-ttu-id="5650a-189">A **Rendelésszám** oszlop megmutatja az értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="5650a-189">The **Order number** column will show the sales order number.</span></span>

    <span data-ttu-id="5650a-190">A **munkagyűjtő azonosítója** mező a munkasablonban beállított munkagyűjtői azonosítóra lesz beállítva.</span><span class="sxs-lookup"><span data-stu-id="5650a-190">The **Work pool ID** field will be set to the work pool ID that was set up in the work template.</span></span>

    > [!TIP]
    > <span data-ttu-id="5650a-191">Ha nem látja a **munkagyűjtő azonosítója** mezőt, adja hozzá az oszlopot a rácshoz, majd frissítse a lapot.</span><span class="sxs-lookup"><span data-stu-id="5650a-191">If you don't see the **Work pool ID** field, add the column to the grid, and then refresh the page.</span></span>

1. <span data-ttu-id="5650a-192">Ha módosítani szeretné a munkaazonosítóhoz társított munkagyűjtőt, akkor a műveleti ablaktábla **Munka** lapján válassza a **Munkagyűjtő-azonosító módosítása** elemet.</span><span class="sxs-lookup"><span data-stu-id="5650a-192">To change the work pool that is associated with the work ID, on the Action Pane, on the **Work** tab, select **Change Work pool ID**.</span></span>
1. <span data-ttu-id="5650a-193">A **Munkagyűjtő módosítása** párbeszédablakban a **Paraméterek** gyorslap **Munkagyűjtő-azonosító** mezőjében válassza a *CallCenter* értéket.</span><span class="sxs-lookup"><span data-stu-id="5650a-193">In the **Change work pool** dialog box, on the **Parameters** FastTab, in the **Work pool ID** field, select *CallCenter*.</span></span>
1. <span data-ttu-id="5650a-194">A módosítás alkalmazásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="5650a-194">Select **OK** to apply your change.</span></span>
1. <span data-ttu-id="5650a-195">Figyelje meg, hogy a **munkagyűjtő-azonosító** mező értéke most módosult *CallCenter* értékre.</span><span class="sxs-lookup"><span data-stu-id="5650a-195">Notice that the value of the **Work pool ID** field has now been changed to *CallCenter*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5650a-196">Ha megjelenik a **Munkagyűjtő módosítása** párbeszédpanel, előfordulhat, hogy a **Munkagyűjtő-azonosító** mező alapértelmezés szerint üres.</span><span class="sxs-lookup"><span data-stu-id="5650a-196">When the **Change work pool** dialog box appears, the **Work pool ID** field might be blank by default.</span></span> <span data-ttu-id="5650a-197">Ha a mező üres, ha az **OK** gombra kattint a módosítások alkalmazásához, akkor a munkagyűjtőt teljes egészében eltávolítja a program a munkából.</span><span class="sxs-lookup"><span data-stu-id="5650a-197">If the field is blank when you select **OK** to apply changes, you will remove the work pool completely from the work.</span></span>
>
> <span data-ttu-id="5650a-198">A munkagyűjtők váltásán kívül ezzel az eljárással munkagyűjtőt adhat hozzá a munkaelemekhez, amelyek nem rendelkeznek eggyel, vagy egy munkagyűjtőt távolíthat el az összes olyan munkaelemből, amely rendelkezik egy értékkel.</span><span class="sxs-lookup"><span data-stu-id="5650a-198">In addition to switching work pools, you can use this procedure to add a work pool to any work item that doesn't have one, or to remove a work pool from any work item that does have one.</span></span>
