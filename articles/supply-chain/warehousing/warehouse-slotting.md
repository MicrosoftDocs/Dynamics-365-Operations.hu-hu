---
title: Raktári időközökre bontás
description: Ez a témakör a raktári időközökre bontással kapcsolatban tartalmaz információkat. A raktári időközökre bontás lehetővé teszi a kereslet cikkek és mértékegységek szerinti konszolidációját a rendelésekből, amelyek Megrendelt, Lefoglalt vagy Kiadott állapottal rendelkeznek. A raktári kezelők számára intelligens módon segít kitárolási helyeket tervezni, mielőtt a rendeléseket a raktárba kiadnák, és kitárolási munkát hoznának létre.
author: mirzaab
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0dd1f42b7bb337ccb65b7e4bdd9d307d074ae0d0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838154"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="64ee5-105">Raktári időközökre bontás</span><span class="sxs-lookup"><span data-stu-id="64ee5-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64ee5-106">A számos raktári időközökre bontási funkció elérhető a kezelők számára, hogy intelligens módon segítsen kitárolási helyeket tervezni, mielőtt a rendeléseket a raktárba kiadnák, és kitárolási munkát hoznának létre.</span><span class="sxs-lookup"><span data-stu-id="64ee5-106">Several warehouse slotting features are available to help warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

<span data-ttu-id="64ee5-107">A *Raktári időközökre bontási funkció* lehetővé teszi a kereslet cikkek és mértékegységek szerinti konszolidációját a rendelésekből, amelyek *Megrendelt*, *Lefoglalt* vagy *Kiadott* állapottal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="64ee5-107">The *Warehouse slotting feature* lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="64ee5-108">A létrejövő igény ezután alkalmazható a kitárolásra használt helyekre, mennyiség, egység, fizikai méretek, rögzített helyek és egyebek alapján.</span><span class="sxs-lookup"><span data-stu-id="64ee5-108">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="64ee5-109">Az időközökre bontási terv létrehozását követően létrehozható a feltöltési munka, hogy a megfelelő mennyiségű készletet helyezze el minden helyen.</span><span class="sxs-lookup"><span data-stu-id="64ee5-109">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="64ee5-110">A *Raktári időközökre bontás átmozgatási rendelésekhez* funkció lehetővé teszi a raktári vezetőknek, hogy feltöltsék a kitárolási helyeket az olyan rendelések áthelyezése alapján, amelyeket még nem adtak ki a raktárnak.</span><span class="sxs-lookup"><span data-stu-id="64ee5-110">The *Warehouse slotting for transfer orders* feature lets warehouse managers replenish picking locations, based on demand from transfer orders that aren't yet released to the warehouse.</span></span> <span data-ttu-id="64ee5-111">Ez biztosítja, hogy a kitárolási helyek tartalmazzák az áthelyezési rendelésekhez szükséges összes cikket, miután kiadták őket a raktárba.</span><span class="sxs-lookup"><span data-stu-id="64ee5-111">It ensures that picking locations will include all the items that are required for the transfer orders after they are released to warehouse.</span></span> <span data-ttu-id="64ee5-112">Ehhez a funkcióhoz be kell kapcsolnia a *Raktár időközökre bontás* funkciót is.</span><span class="sxs-lookup"><span data-stu-id="64ee5-112">This feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span>

<span data-ttu-id="64ee5-113">A *Raktári időközökre bontás felosztási fejlesztései* funkció lehetőséget ad a *Raktár időközökre bontási funkció* által használt sablonsorokhoz.</span><span class="sxs-lookup"><span data-stu-id="64ee5-113">The *Warehouse slotting allocation enhancements* feature adds an option for the template lines that are used by the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="64ee5-114">Ez a beállítás lehetővé teszi a rendszer számára, hogy a célhelyen meglévő aktuális készletet vegye figyelembe.</span><span class="sxs-lookup"><span data-stu-id="64ee5-114">The option enables the system to consider existing on-hand inventory at a target location.</span></span> <span data-ttu-id="64ee5-115">Ezért kevesebb feltöltés keletkezik az időközökre bontáshoz.</span><span class="sxs-lookup"><span data-stu-id="64ee5-115">Therefore, fewer replenishments might be generated for slotting.</span></span> <span data-ttu-id="64ee5-116">A *Raktári időközökre bontás felosztási fejlesztései* funkcióhoz a *Raktár időközökre bontási funkciót* is be kell kapcsolnia.</span><span class="sxs-lookup"><span data-stu-id="64ee5-116">The *Warehouse slotting allocation enhancements* feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="64ee5-117">Opcionálisan használható a *Raktári időközökre bontás átmozgatási rendelésekhez* funkcióhoz.</span><span class="sxs-lookup"><span data-stu-id="64ee5-117">It can optionally be used together with the *Warehouse slotting for transfer orders* feature.</span></span>

## <a name="turn-on-the-warehouse-slotting-features"></a><span data-ttu-id="64ee5-118">A raktári időközökre bontási funkciók bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="64ee5-118">Turn on the warehouse slotting features</span></span>

<span data-ttu-id="64ee5-119">A funkciók használata előtt be kell azokat kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="64ee5-119">Before you can use these features, they must be turned on in your system.</span></span> <span data-ttu-id="64ee5-120">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat ezen funkciók állapotának ellenőrzéséhez, és szükség esetén a bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="64ee5-120">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="64ee5-121">Szükség szerint kapcsolja be a következő szolgáltatásokat:</span><span class="sxs-lookup"><span data-stu-id="64ee5-121">Turn on the following features as required:</span></span>

- <span data-ttu-id="64ee5-122">Raktári időközökre bontási funkció</span><span class="sxs-lookup"><span data-stu-id="64ee5-122">Warehouse slotting feature</span></span>
- <span data-ttu-id="64ee5-123">Raktári időközökre bontás átmozgatási rendelésekhez</span><span class="sxs-lookup"><span data-stu-id="64ee5-123">Warehouse slotting for transfer orders</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="64ee5-124">A *Raktári időközökre bontás* funkciót be kell kapcsolni a funkció előtt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-124">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

- <span data-ttu-id="64ee5-125">Raktári időközökre bontási felosztás fejlesztései</span><span class="sxs-lookup"><span data-stu-id="64ee5-125">Warehouse slotting allocation enhancements</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="64ee5-126">A *Raktári időközökre bontás* funkciót be kell kapcsolni a funkció előtt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-126">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="64ee5-127">Raktári időközökre bontás beállítása</span><span class="sxs-lookup"><span data-stu-id="64ee5-127">Set up warehouse slotting</span></span>

<span data-ttu-id="64ee5-128">A raktári időközökre bontási használatához a következő elemeket kell beállítania a rendszerben:</span><span class="sxs-lookup"><span data-stu-id="64ee5-128">To use warehouse slotting, you must set up the following elements in your system:</span></span>

- <span data-ttu-id="64ee5-129">Időközökre bontás mértékegységszintjei</span><span class="sxs-lookup"><span data-stu-id="64ee5-129">Slotting unit of measure tiers</span></span>
- <span data-ttu-id="64ee5-130">Utasításkódok</span><span class="sxs-lookup"><span data-stu-id="64ee5-130">Directive codes</span></span>
- <span data-ttu-id="64ee5-131">Időközökre bontási sablonok</span><span class="sxs-lookup"><span data-stu-id="64ee5-131">Slotting templates</span></span>
- <span data-ttu-id="64ee5-132">Helyutasítások</span><span class="sxs-lookup"><span data-stu-id="64ee5-132">Location directives</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="64ee5-133">Mértékegységszintek létrehozása az időközökre bontáshoz</span><span class="sxs-lookup"><span data-stu-id="64ee5-133">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="64ee5-134">A mértékegységszintek lehetővé teszik a különböző mértékegységek csoportosítását az időközökre bontás céljából.</span><span class="sxs-lookup"><span data-stu-id="64ee5-134">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="64ee5-135">Ha például több dobozméret van kiválasztva ugyanarról a dobozkitárolási területről, akkor az összes mérethez létrehozható egy szint.</span><span class="sxs-lookup"><span data-stu-id="64ee5-135">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="64ee5-136">**Minden mértékegységhez létre kell hozni egy sort, amely a szint része.**</span><span class="sxs-lookup"><span data-stu-id="64ee5-136">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="64ee5-137">Lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Mértékegységszintek időközökre bontása**.</span><span class="sxs-lookup"><span data-stu-id="64ee5-137">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="64ee5-138">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64ee5-138">Select **New**.</span></span>
1. <span data-ttu-id="64ee5-139">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-139">In the header, set the following values:</span></span>

    - <span data-ttu-id="64ee5-140">**Mértékegységszint:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="64ee5-140">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="64ee5-141">**Leírás:** *Minden doboz raklap*</span><span class="sxs-lookup"><span data-stu-id="64ee5-141">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="64ee5-142">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64ee5-142">Select **Save**.</span></span>
1. <span data-ttu-id="64ee5-143">A **Mértékegységek** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="64ee5-143">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="64ee5-144">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="64ee5-145">**Egység:** *Doboz*</span><span class="sxs-lookup"><span data-stu-id="64ee5-145">**Unit:** *Box*</span></span>
    - <span data-ttu-id="64ee5-146">**Leírás:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-146">**Description:** Leave this field blank.</span></span> <span data-ttu-id="64ee5-147">A módosítások mentésekor a program automatikusan kitölti ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-147">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="64ee5-148">**Egységosztály:** *Mennyiség*</span><span class="sxs-lookup"><span data-stu-id="64ee5-148">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="64ee5-149">Válassza az **Új** lehetőséget egy második sor rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="64ee5-149">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="64ee5-150">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-150">On the new line, set the following values:</span></span>

    - <span data-ttu-id="64ee5-151">**Egység:** *ea*</span><span class="sxs-lookup"><span data-stu-id="64ee5-151">**Unit:** *ea*</span></span>
    - <span data-ttu-id="64ee5-152">**Leírás:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-152">**Description:** Leave this field blank.</span></span> <span data-ttu-id="64ee5-153">A módosítások mentésekor a program automatikusan kitölti ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-153">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="64ee5-154">**Egységosztály:** *Mennyiség*</span><span class="sxs-lookup"><span data-stu-id="64ee5-154">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="64ee5-155">Válassza az **Új** lehetőséget egy harmadik sor rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="64ee5-155">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="64ee5-156">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-156">On the new line, set the following values:</span></span>

    - <span data-ttu-id="64ee5-157">**Egység:** *PL*</span><span class="sxs-lookup"><span data-stu-id="64ee5-157">**Unit:** *PL*</span></span>
    - <span data-ttu-id="64ee5-158">**Leírás:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-158">**Description:** Leave this field blank.</span></span> <span data-ttu-id="64ee5-159">A módosítások mentésekor a program automatikusan kitölti ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-159">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="64ee5-160">**Egységosztály:** *Mennyiség*</span><span class="sxs-lookup"><span data-stu-id="64ee5-160">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="64ee5-161">A szint mentéséhez válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="64ee5-161">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="64ee5-162">Utasításkód létrehozása az időközökre bontáshoz</span><span class="sxs-lookup"><span data-stu-id="64ee5-162">Create a directive code for slotting</span></span>

<span data-ttu-id="64ee5-163">Ki kell választania a sablonhoz társítani kívánt utasításkódot.</span><span class="sxs-lookup"><span data-stu-id="64ee5-163">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="64ee5-164">Ugrás a **Raktárkezelés \> Beállítás \> Utasítskódok** elemre.</span><span class="sxs-lookup"><span data-stu-id="64ee5-164">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="64ee5-165">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="64ee5-165">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="64ee5-166">Az **irányelv kódja** mezőbe írja be az *Időközökre bontás* értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-166">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="64ee5-167">Az **Utasítás leírása** mezőbe írja be az *Időközökre bontás* értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-167">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="64ee5-168">Időközökre bontás sablonok beállítása</span><span class="sxs-lookup"><span data-stu-id="64ee5-168">Set up slotting templates</span></span>

<span data-ttu-id="64ee5-169">Minden időközökre bontási sablon azt vezérli, hogy a készlet milyen módon van hozzárendelve egy adott raktár helyeihez.</span><span class="sxs-lookup"><span data-stu-id="64ee5-169">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="64ee5-170">Minden sablonnak tartalmaznia kell egy sort mindegyik időközökre bontási specifikációból.</span><span class="sxs-lookup"><span data-stu-id="64ee5-170">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="64ee5-171">Az ebben a szakaszban található eljárások segítségével lehet beállítani az időközökre bontási sablonokat.</span><span class="sxs-lookup"><span data-stu-id="64ee5-171">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="64ee5-172">Ugorjon a **Raktárkezelés \> Beállítás \> Feltöltés \> Időközökre bontási sablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="64ee5-172">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="64ee5-173">Válassza az **Új** lehetőséget egy sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="64ee5-173">Select **New** to create a template.</span></span>

<span data-ttu-id="64ee5-174">Ezután be kell állítania a sablon fejlécét, az időközökre bontási specifikációkat és a helyutasításokat, ahogyan azt a következő alszakaszok részletezik.</span><span class="sxs-lookup"><span data-stu-id="64ee5-174">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span> <span data-ttu-id="64ee5-175">Az időközökre bontás átmozgatási rendelésekhez beállítása hasonlít az időközökre bontás értékesítési rendelések beállításaihoz, de a **Kereslet típusa** mező az *Értékesítési rendelés* helyett az *Átmozgatási rendelések* értékre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="64ee5-175">The setup for slotting for transfer orders resembles the setup for slotting for sales orders, but the **Demand type** field is set *Transfer orders* instead of *Sales order*.</span></span>

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a><span data-ttu-id="64ee5-176">Értékesítési rendelés időközökre bontási sablon fejlécének beállítása</span><span class="sxs-lookup"><span data-stu-id="64ee5-176">Set up the header for a sales order slotting template</span></span>

1. <span data-ttu-id="64ee5-177">A sablon fejlécében adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-177">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="64ee5-178">**Időközökre bontási sablon** _61_</span><span class="sxs-lookup"><span data-stu-id="64ee5-178">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="64ee5-179">**Leírás:** _61_</span><span class="sxs-lookup"><span data-stu-id="64ee5-179">**Description:** _61_</span></span>
    - <span data-ttu-id="64ee5-180">**Kereslet típusa:** *Értékesítési rendelés*</span><span class="sxs-lookup"><span data-stu-id="64ee5-180">**Demand type:** *Sales order*</span></span>

        > [!NOTE]
        > <span data-ttu-id="64ee5-181">Jelenleg az *Értékesítési rendelések* és az *Átmozgatási rendelések* az egyetlen támogatott kereslettípusok.</span><span class="sxs-lookup"><span data-stu-id="64ee5-181">Currently, *Sales orders* and *Transfer orders* are the only demand types that are supported.</span></span> <span data-ttu-id="64ee5-182">Csak akkor választhatja az *Átmozgatási rendeléseket,* ha az *Raktári időközökre bontás átmozgatási rendelésekhez* funkció be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="64ee5-182">You can select *Transfer orders* only if the *Warehouse Slotting for transfer orders* feature is turned on.</span></span>

    - <span data-ttu-id="64ee5-183">**Kereslet stratégia:** _Megrendelve_</span><span class="sxs-lookup"><span data-stu-id="64ee5-183">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="64ee5-184">A következő értékek állnak rendelkezésre ebben a mezőben:</span><span class="sxs-lookup"><span data-stu-id="64ee5-184">The following values are available in this field:</span></span>

        - <span data-ttu-id="64ee5-185">**Megrendelt** – Az értékesítési rendelés teljes megrendelt mennyiségét keresletnek kell tekinteni.</span><span class="sxs-lookup"><span data-stu-id="64ee5-185">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="64ee5-186">**Lefoglalva** – Csak az értékesítési rendelés sor lefoglalt (tényleges és rendelt) mennyiségét kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="64ee5-186">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>
        - <span data-ttu-id="64ee5-187">**Kiadott** – A kiadott mennyiséget keresletnek kell tekinteni.</span><span class="sxs-lookup"><span data-stu-id="64ee5-187">**Released** – The released quantity should be considered demand.</span></span>

    - <span data-ttu-id="64ee5-188">**Raktár:** _61_</span><span class="sxs-lookup"><span data-stu-id="64ee5-188">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="64ee5-189">**A hullám keresletének engedélyezése nem foglalt mennyiségek használatához:** _Igen_</span><span class="sxs-lookup"><span data-stu-id="64ee5-189">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="64ee5-190">Megadhat egy lekérdezést is a kiértékelt kereslet hatókörének leszűkítéséhez.</span><span class="sxs-lookup"><span data-stu-id="64ee5-190">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="64ee5-191">Időközökre bontási specifikációk beállítása ez egyes sablontípusokhoz</span><span class="sxs-lookup"><span data-stu-id="64ee5-191">Set up slotting specifications for each template</span></span>

<span data-ttu-id="64ee5-192">Minden értékesítési rendelési sablon esetében hajtsa végre az alábbi lépéseket egy sor hozzáadásához az egyes időközökre bontási specifikációkhoz.</span><span class="sxs-lookup"><span data-stu-id="64ee5-192">For each sales order template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="64ee5-193">Az **Időközökre bontási részletek** gyorslapján válassza az **Új** parancsot, és hozzon létre egy sablonfájlt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-193">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="64ee5-194">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-194">On the new line, set the following values:</span></span>

    - <span data-ttu-id="64ee5-195">**Sorozat:** _1_</span><span class="sxs-lookup"><span data-stu-id="64ee5-195">**Sequence:** _1_</span></span>
    - <span data-ttu-id="64ee5-196">**Leírás:** _Rögzített hely_</span><span class="sxs-lookup"><span data-stu-id="64ee5-196">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="64ee5-197">**Minimális mennyiség:** _1_</span><span class="sxs-lookup"><span data-stu-id="64ee5-197">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="64ee5-198">Ez a mező azt a minimális keresleti mennyiséget határozza meg, amely a sorhoz szükséges.</span><span class="sxs-lookup"><span data-stu-id="64ee5-198">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="64ee5-199">**Maximális mennyiség:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="64ee5-199">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="64ee5-200">Ez a mező azt a maximális keresleti mennyiséget határozza meg, amely a sorhoz érvényes.</span><span class="sxs-lookup"><span data-stu-id="64ee5-200">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="64ee5-201">**Egység:** Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="64ee5-201">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="64ee5-202">Ez a mező azt a mértékegységet határozza meg, amelyre a minimális és maximális mennyiségek utalnak.</span><span class="sxs-lookup"><span data-stu-id="64ee5-202">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="64ee5-203">**Mértékegységszint:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="64ee5-203">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="64ee5-204">Ez a mező azt a keresleti mértékegységet határozza meg, amely a sorhoz érvényes.</span><span class="sxs-lookup"><span data-stu-id="64ee5-204">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="64ee5-205">(További információt a [Mértékegységszintek beállítása időközökre bontáshoz](#unit-tiers) című részben talál, a téma korábbi részében.)</span><span class="sxs-lookup"><span data-stu-id="64ee5-205">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="64ee5-206">**Időköz-hozzárendelési feltétel társítása:** _Figyelembe vett mennyiség_</span><span class="sxs-lookup"><span data-stu-id="64ee5-206">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="64ee5-207">A következő értékek állnak rendelkezésre ebben a mezőben:</span><span class="sxs-lookup"><span data-stu-id="64ee5-207">The following values are available in this field:</span></span>

        - <span data-ttu-id="64ee5-208">**Üresen hagyott** – Ez a rendszer feltételezi, hogy a kitárolási terület minden helye üres, és a készlethez tartozó helyeket nem szabad ellenőrizni.</span><span class="sxs-lookup"><span data-stu-id="64ee5-208">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="64ee5-209">**Figyelembe vett mennyiség** – Ennek a rendszernek ellenőriznie kell a helyeket a készlet kitárolási területein, és ki kell hagynia minden nem üres helyet.</span><span class="sxs-lookup"><span data-stu-id="64ee5-209">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>
        - <span data-ttu-id="64ee5-210">**Aktuálisan készleten lévők figyelembe vétele** – A rendszernek ellenőriznie kell, hogy a célhely tartalmaz-e nem foglalt mennyiségeket a kereslet sorban szereplő cikkhez.</span><span class="sxs-lookup"><span data-stu-id="64ee5-210">**Consider on-hand** – The system should check whether any target location contains unreserved quantities for the item on the demand line.</span></span> <span data-ttu-id="64ee5-211">Ha a mennyiség elég nagy ahhoz, hogy a kereslet sor legalább egy egységét kielégítsen, akkor a létrehozott időközökre bontási terv rekord az elérhető mennyiséggel csökken.</span><span class="sxs-lookup"><span data-stu-id="64ee5-211">If the quantity is large enough to satisfy at least one unit of the demand line, the generated slotting plan record is reduced by the available amount.</span></span> <span data-ttu-id="64ee5-212">Ha például a kereslet 10 eset, és egy eset kéznél van, a megtalált kereslet kilenc eset lesz.</span><span class="sxs-lookup"><span data-stu-id="64ee5-212">For example, if the demand is 10 cases, and one case is on hand, the located demand will be nine cases.</span></span> <span data-ttu-id="64ee5-213">Ha a kereslet 10 eset, és mindegyik eset kéznél van, a megtalált kereslet 10 eset lesz.</span><span class="sxs-lookup"><span data-stu-id="64ee5-213">If the demand is 10 cases, and one each is on hand, the located demand will be 10 cases.</span></span> <span data-ttu-id="64ee5-214">Ez az érték csak akkor érhető el , ha be van kapcsolva a *Raktári időközökre bontás felosztási fejlesztései* funkció.</span><span class="sxs-lookup"><span data-stu-id="64ee5-214">This value is available only when the *Warehouse slotting allocation enhancements* feature is turned on.</span></span>

    - <span data-ttu-id="64ee5-215">**Irányelv kódja:** _Időközökre bontási_</span><span class="sxs-lookup"><span data-stu-id="64ee5-215">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="64ee5-216">Ez a mező határozza meg a feltöltési munka kitárolási helyének megtalálásához használt helyutasítást.</span><span class="sxs-lookup"><span data-stu-id="64ee5-216">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="64ee5-217">**Túlcsordulási hely:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-217">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="64ee5-218">Ez a mező azt a helyet határozza meg, ahová a készletet elhelyezik, ha a sor feldolgozásakor nem található hely a mennyiséghez.</span><span class="sxs-lookup"><span data-stu-id="64ee5-218">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="64ee5-219">**Felengedés engedélyezése:** _Igen_</span><span class="sxs-lookup"><span data-stu-id="64ee5-219">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="64ee5-220">Ha ez a beállítás *Igen* értékre van állítva, akkor ha a kereslet nem bontható időközökre, létrejön munka a készlet felvételéhez olyan készlettel rendelkező helyekről, ahol nincs időközökre bontás.</span><span class="sxs-lookup"><span data-stu-id="64ee5-220">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="64ee5-221">Ezután a sablon újra futni fog.</span><span class="sxs-lookup"><span data-stu-id="64ee5-221">The template is then run again.</span></span> <span data-ttu-id="64ee5-222">Ez alkalommal figyelmen kívül hagyja a készletet a helyeken.</span><span class="sxs-lookup"><span data-stu-id="64ee5-222">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="64ee5-223">Ez a funkció a legjobban akkor működik, ha a **Időköz-hozzárendelési feltétel társítása** mező _Figyelembe vett mennyiség_ értékkel van megadva.</span><span class="sxs-lookup"><span data-stu-id="64ee5-223">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="64ee5-224">**Rögzített hely használata:** _Csak a termék rögzített helyei_</span><span class="sxs-lookup"><span data-stu-id="64ee5-224">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="64ee5-225">A következő értékek állnak rendelkezésre ebben a mezőben:</span><span class="sxs-lookup"><span data-stu-id="64ee5-225">The following values are available in this field:</span></span>

        - <span data-ttu-id="64ee5-226">**Rögzített és nem rögzített helyek** – A rendszer nem korlátozható csak a rögzített helyek használatára.</span><span class="sxs-lookup"><span data-stu-id="64ee5-226">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="64ee5-227">**Csak a termék rögzített helyei** – A rendszer csak a termék rögzített helyeit tartalmazó tárolóhelyeket rögzít.</span><span class="sxs-lookup"><span data-stu-id="64ee5-227">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="64ee5-228">**Csak a termékváltozat rögzített helyei** – A rendszer csak a termékváltozat rögzített helyeit tartalmazó tárolóhelyeket rögzít.</span><span class="sxs-lookup"><span data-stu-id="64ee5-228">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

> [!NOTE]
> <span data-ttu-id="64ee5-229">Ha az időközökre bontás sablon legalább egy olyan sort tartalmaz, ahol az **Időköz-hozzárendelési feltétel társítása** mező az *Aktuálisan készleten lévők figyelembe vétele* beállításra van állítva, akkor a sablon egyetlen sorához sem engedélyezettek a beállítások.</span><span class="sxs-lookup"><span data-stu-id="64ee5-229">If the slotting template contains at least one line where the **Assign slot criteria** field is set to *Consider on-hand*, let-ups are no longer allowed for any line in the template.</span></span>

1. <span data-ttu-id="64ee5-230">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64ee5-230">Select **Save**.</span></span>
1. <span data-ttu-id="64ee5-231">Ha második sablonsort szeretne létrehozni, kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="64ee5-231">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="64ee5-232">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="64ee5-233">**Sorozat:** _2_</span><span class="sxs-lookup"><span data-stu-id="64ee5-233">**Sequence:** _2_</span></span>
    - <span data-ttu-id="64ee5-234">**Leírás:** _Egyéb_</span><span class="sxs-lookup"><span data-stu-id="64ee5-234">**Description:** _Other_</span></span>
    - <span data-ttu-id="64ee5-235">**Minimális mennyiség:** _1_</span><span class="sxs-lookup"><span data-stu-id="64ee5-235">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="64ee5-236">**Maximális mennyiség:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="64ee5-236">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="64ee5-237">**Egység:** Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="64ee5-237">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="64ee5-238">**Mértékegységszint:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="64ee5-238">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="64ee5-239">**Időköz-hozzárendelési feltétel társítása:** _Figyelembe vett mennyiség_</span><span class="sxs-lookup"><span data-stu-id="64ee5-239">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="64ee5-240">**Irányelv kódja:** _Időközökre bontási_</span><span class="sxs-lookup"><span data-stu-id="64ee5-240">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="64ee5-241">**Túlcsordulási hely:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-241">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="64ee5-242">**Felengedés engedélyezése:** _Igen_</span><span class="sxs-lookup"><span data-stu-id="64ee5-242">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="64ee5-243">**Rögzített helyek használata:** _Rögzített és nem rögzített helyek_</span><span class="sxs-lookup"><span data-stu-id="64ee5-243">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="64ee5-244">A második sor lekérdezésében megadhatja azokat a feltételeket, amelyekkel meghatározhatja, hogy milyen helyeken lehet az adott sor igénye időközökre bontható.</span><span class="sxs-lookup"><span data-stu-id="64ee5-244">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="64ee5-245">Válassza ki azt a sort, amelynél a **Sorozat** mező értéke *2*.</span><span class="sxs-lookup"><span data-stu-id="64ee5-245">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="64ee5-246">Válassza ki a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64ee5-246">Select **Edit query**.</span></span>
1. <span data-ttu-id="64ee5-247">A **Tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="64ee5-247">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="64ee5-248">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-248">On the new line, set the following values:</span></span>

    - <span data-ttu-id="64ee5-249">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="64ee5-249">**Table:** *Locations*</span></span>
    - <span data-ttu-id="64ee5-250">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="64ee5-250">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="64ee5-251">**Mező:** *Hely profilazonosítója*</span><span class="sxs-lookup"><span data-stu-id="64ee5-251">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="64ee5-252">**Feltételek:** *Kitárolás-06* (Válassza ki a dupla plusz jelet \[**++**\] a mezőben a lista kibontásához, majd válassza a *Kitárolás-06* - *6. kitárolási hely* elemet.)</span><span class="sxs-lookup"><span data-stu-id="64ee5-252">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="64ee5-253">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64ee5-253">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="64ee5-254">Helyutasítások beállítása</span><span class="sxs-lookup"><span data-stu-id="64ee5-254">Set up location directives</span></span>

<span data-ttu-id="64ee5-255">A kitárolások időközökre bontásának támogatásához be kell állítani legalább egy helyutasítást.</span><span class="sxs-lookup"><span data-stu-id="64ee5-255">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="64ee5-256">Az ebben a szakaszban található eljárások segítségével beállíthatja a kitárolások időközökre bontásának új *feltöltési helyutasítását*.</span><span class="sxs-lookup"><span data-stu-id="64ee5-256">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="64ee5-257">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="64ee5-257">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="64ee5-258">A bal oldali ablaktáblában állítsa a **Munkarendelés típusa** mezőt a *Feltöltés* értékre.</span><span class="sxs-lookup"><span data-stu-id="64ee5-258">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="64ee5-259">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="64ee5-259">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="64ee5-260">Az új helyutasítás fejlécében, a **Név** mezőbe írja be a *61 kitárolás időközökre bontása* értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-260">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>
1. <span data-ttu-id="64ee5-261">A **Sorszám** mezőben fogadja el az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-261">In the **Sequence number** field, accept the default value.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="64ee5-262">Konfigurálja a Helyutasítások gyorslapot</span><span class="sxs-lookup"><span data-stu-id="64ee5-262">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="64ee5-263">A **Helyutasítások** gyorslapon állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-263">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="64ee5-264">Az összes többi mezőben hagyja meg az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-264">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="64ee5-265">**Munka típusa:** _Kitárolás_</span><span class="sxs-lookup"><span data-stu-id="64ee5-265">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="64ee5-266">**Telephely:** _6_</span><span class="sxs-lookup"><span data-stu-id="64ee5-266">**Site:** _6_</span></span>
    - <span data-ttu-id="64ee5-267">**Raktár:** _61_</span><span class="sxs-lookup"><span data-stu-id="64ee5-267">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="64ee5-268">**Irányelv kódja:** _Időközökre bontási_</span><span class="sxs-lookup"><span data-stu-id="64ee5-268">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="64ee5-269">A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="64ee5-269">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="64ee5-270">A Sorok gyorslap konfigurálása</span><span class="sxs-lookup"><span data-stu-id="64ee5-270">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="64ee5-271">A **Sorok** gyorslapon kattintson az **Új** lehetőségre egy sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="64ee5-271">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="64ee5-272">Az új sorban állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-272">On the new line, set the following values.</span></span>

    - <span data-ttu-id="64ee5-273">**Kezdő mennyiség:** _0_</span><span class="sxs-lookup"><span data-stu-id="64ee5-273">**From quantity:** _0_</span></span>
    - <span data-ttu-id="64ee5-274">**Záró mennyiség:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="64ee5-274">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="64ee5-275">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-275">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="64ee5-276">A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="64ee5-276">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="64ee5-277">Konfigurálja a Helyutasítási műveletek gyorslapot</span><span class="sxs-lookup"><span data-stu-id="64ee5-277">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="64ee5-278">A **Helyutasítási műveletek** gyorslapon kattintson az **Új** lehetőségre egy sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="64ee5-278">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="64ee5-279">Az új sorban állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-279">On the new line, set the following values.</span></span> <span data-ttu-id="64ee5-280">Az összes többi mezőben hagyja meg az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-280">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="64ee5-281">**Sorszám:** Fogadja el az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-281">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="64ee5-282">**Név:** _Ömlesztett_</span><span class="sxs-lookup"><span data-stu-id="64ee5-282">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="64ee5-283">**Stratégia:** _Nincs_</span><span class="sxs-lookup"><span data-stu-id="64ee5-283">**Strategy:** _None_</span></span>

1. <span data-ttu-id="64ee5-284">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-284">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="64ee5-285">Válassza a **Mentés** lehetőséget, ha elérhetővé szeretné tenni a **Lekérdezés szerkesztése** gombot.</span><span class="sxs-lookup"><span data-stu-id="64ee5-285">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="64ee5-286">A lekérdezés szerkesztése</span><span class="sxs-lookup"><span data-stu-id="64ee5-286">Edit the query</span></span>

1. <span data-ttu-id="64ee5-287">A **Helyutasítás műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64ee5-287">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="64ee5-288">A **Tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="64ee5-288">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="64ee5-289">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-289">On the new line, set the following values:</span></span>

    - <span data-ttu-id="64ee5-290">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="64ee5-290">**Table:** *Locations*</span></span>
    - <span data-ttu-id="64ee5-291">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="64ee5-291">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="64ee5-292">**Mező:** *Zóna azonosítója*</span><span class="sxs-lookup"><span data-stu-id="64ee5-292">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="64ee5-293">**Feltételek:** *Ömlesztett* (Válassza ki a dupla plusz jelet \[**++**\] a mezőben a lista kibontásához, majd válassza az *Ömlesztett* kitárolási hely elemet.)</span><span class="sxs-lookup"><span data-stu-id="64ee5-293">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="64ee5-294">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64ee5-294">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="64ee5-295">Forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="64ee5-295">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="64ee5-296">Forgatókönyv beállítása</span><span class="sxs-lookup"><span data-stu-id="64ee5-296">Set up the scenario</span></span>

<span data-ttu-id="64ee5-297">Ehhez a forgatókönyvhöz használja a beépített mintaadatokat, és hozza létre a szakaszban ismertetett rekordokat.</span><span class="sxs-lookup"><span data-stu-id="64ee5-297">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="64ee5-298">A USMF mintaadatok használata</span><span class="sxs-lookup"><span data-stu-id="64ee5-298">Use the USMF sample data</span></span>

<span data-ttu-id="64ee5-299">Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="64ee5-299">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="64ee5-300">Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="64ee5-300">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="64ee5-301">Igény létrehozása</span><span class="sxs-lookup"><span data-stu-id="64ee5-301">Create demand</span></span>

<span data-ttu-id="64ee5-302">Hajtsa végre az alábbi lépéseket, és hozza létre azt az igényt, amelyre alkalmazni fogja az időközökre bontást.</span><span class="sxs-lookup"><span data-stu-id="64ee5-302">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="64ee5-303">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="64ee5-303">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="64ee5-304">Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="64ee5-304">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="64ee5-305">Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőben válassza ki azt az _US-007_ értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-305">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="64ee5-306">A **Raktár** mezőben válassza ki az _61_ értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-306">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="64ee5-307">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64ee5-307">Select **OK**.</span></span>
1. <span data-ttu-id="64ee5-308">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="64ee5-308">The new sales order is opened.</span></span> <span data-ttu-id="64ee5-309">Tartalmaz egy üres sort az **Értékesítési rendelés sorai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="64ee5-309">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="64ee5-310">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-310">On this line, set the following values:</span></span>

    - <span data-ttu-id="64ee5-311">**Cikk:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="64ee5-311">**Item:** _L0101_</span></span>
    - <span data-ttu-id="64ee5-312">**Mennyiség:** _20_</span><span class="sxs-lookup"><span data-stu-id="64ee5-312">**Quantity:** _20_</span></span>

1. <span data-ttu-id="64ee5-313">Válassza ki a **Sor hozzáadása** lehetőséget egy új sor hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-313">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="64ee5-314">**Cikk:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="64ee5-314">**Item:** _T0100_</span></span>
    - <span data-ttu-id="64ee5-315">**Mennyiség:** _8_</span><span class="sxs-lookup"><span data-stu-id="64ee5-315">**Quantity:** _8_</span></span>

1. <span data-ttu-id="64ee5-316">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64ee5-316">Select **Save**.</span></span>
1. <span data-ttu-id="64ee5-317">Második értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="64ee5-317">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="64ee5-318">Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőben válassza ki azt az _US-008_ értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-318">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="64ee5-319">A **Raktár** mezőben válassza ki az _61_ értéket.</span><span class="sxs-lookup"><span data-stu-id="64ee5-319">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="64ee5-320">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="64ee5-320">The new sales order is opened.</span></span> <span data-ttu-id="64ee5-321">Tartalmaz egy üres sort az **Értékesítési rendelés sorai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="64ee5-321">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="64ee5-322">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="64ee5-322">On this line, set the following values:</span></span>

    - <span data-ttu-id="64ee5-323">**Cikk:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="64ee5-323">**Item:** _T0100_</span></span>
    - <span data-ttu-id="64ee5-324">**Mennyiség:** _1_</span><span class="sxs-lookup"><span data-stu-id="64ee5-324">**Quantity:** _1_</span></span>

1. <span data-ttu-id="64ee5-325">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="64ee5-325">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="64ee5-326">Haladjon végig egy tipikus időközökre bontási forgatókönyvön</span><span class="sxs-lookup"><span data-stu-id="64ee5-326">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="64ee5-327">Miután az összes előfeltétel-elem a helyén van, ahogy azt az előző részben ismertették, készen áll a funkció kipróbálására a jelen szakasz minden egyes gyakorlatán keresztül.</span><span class="sxs-lookup"><span data-stu-id="64ee5-327">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="64ee5-328">Igény létrehozása</span><span class="sxs-lookup"><span data-stu-id="64ee5-328">Generate demand</span></span>

1. <span data-ttu-id="64ee5-329">Lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Időközökre bontási sablonok** pontra, és válassza ki a korábban létrehozott időközökre bontási sablont.</span><span class="sxs-lookup"><span data-stu-id="64ee5-329">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="64ee5-330">A Művelet ablaktáblán válassza ki a **Kereslet generálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="64ee5-330">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="64ee5-331">Ez a parancs a rendszerben található összes igényt kiértékeli, és megfelel az időközökre bontási sablon lekérdezésének.</span><span class="sxs-lookup"><span data-stu-id="64ee5-331">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="64ee5-332">A program ezután összesíti az összes rendelésen szereplő teljes igényt, egy sorban/mértékegységben.</span><span class="sxs-lookup"><span data-stu-id="64ee5-332">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="64ee5-333">A folyamat befejezésekor egy tájékoztató üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="64ee5-333">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="64ee5-334">Időközökre bontás igénye</span><span class="sxs-lookup"><span data-stu-id="64ee5-334">Slotting demand</span></span>

<span data-ttu-id="64ee5-335">Az *időközökre bontási igény* a keresletgenerálás eredményét jeleníti meg az időközökre bontási sablon beállítása alapján.</span><span class="sxs-lookup"><span data-stu-id="64ee5-335">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="64ee5-336">A Művelet panelen válassza az **Időközökre bontási igény** elemet a **Keresletgenerálás** parancsból származó eredmények megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="64ee5-336">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="64ee5-337">Az időközökre bontási igény sorai szerkeszthetők.</span><span class="sxs-lookup"><span data-stu-id="64ee5-337">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="64ee5-338">Lehetőség van egy sor törlésére, új sor hozzáadására vagy a sor részletes adatainak szerkesztésére.</span><span class="sxs-lookup"><span data-stu-id="64ee5-338">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="64ee5-339">A kereslet manuálisan is szerkeszthető, illetve a külső rendszerből is importálhatja az adatkezelés segítségével.</span><span class="sxs-lookup"><span data-stu-id="64ee5-339">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="64ee5-340">Bármi is szerepel az időközökre bontási igényben a következő lépésben, az kerül felhasználásra, függetlenül attól, hogy honnan érkezett.</span><span class="sxs-lookup"><span data-stu-id="64ee5-340">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="64ee5-341">Igény megkeresése</span><span class="sxs-lookup"><span data-stu-id="64ee5-341">Locate demand</span></span>

<span data-ttu-id="64ee5-342">Miután létrehozta a keresletet, az **Kereslet helyének megkeresése** paranccsal hozhat létre *időközökre bontási tervet*.</span><span class="sxs-lookup"><span data-stu-id="64ee5-342">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="64ee5-343">A Művelet ablaktáblán válassza ki a **Kereslet helyének megkeresése** elemet.</span><span class="sxs-lookup"><span data-stu-id="64ee5-343">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="64ee5-344">Az időközökre bontási folyamat fut.</span><span class="sxs-lookup"><span data-stu-id="64ee5-344">The slotting process runs.</span></span> <span data-ttu-id="64ee5-345">A folyamat befejezésekor egy tájékoztató üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="64ee5-345">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="64ee5-346">Időközökre bontási terv</span><span class="sxs-lookup"><span data-stu-id="64ee5-346">Slotting plan</span></span>

<span data-ttu-id="64ee5-347">Az időközökre bontási terv azt a helyet jeleníti meg, amelyhez az egyes cikkek/mennyiségek hozzá vannak rendelve, hogy történt-e túlcsordulás, létrehozásra került-e felengedési munka, valamint a sablon felhasznált sorát.</span><span class="sxs-lookup"><span data-stu-id="64ee5-347">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="64ee5-348">*Minden olyan igényt, amelyet nem lehet időközökre bontani, piros színnel van kijelölve.*</span><span class="sxs-lookup"><span data-stu-id="64ee5-348">*Any demand that could not be slotted is highlighted in red.*</span></span>

- <span data-ttu-id="64ee5-349">Az eredmények megtekintéséhez válassza ki az **Időközökre bontási tervet** a Művelet ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="64ee5-349">On the Action Pane, select **Slotting plan** to view the results.</span></span>

> [!NOTE]
> - <span data-ttu-id="64ee5-350">A **Kereslet generálása**, a **Kereslet helyének megkeresése** és a **Feltöltés futtatása** mostantól egy tesztkörnyezetben fut.</span><span class="sxs-lookup"><span data-stu-id="64ee5-350">The **Generate demand**, **Locate demand**, and **Run replenishment** processes are now run in a sandbox.</span></span> <span data-ttu-id="64ee5-351">(Ezek a folyamatok a Művelet panelen érhetők el az **Időközökre bontási sablonok** oldalon.)</span><span class="sxs-lookup"><span data-stu-id="64ee5-351">(These processes are available from the Action Pane on the **Slotting templates** page.)</span></span>
> - <span data-ttu-id="64ee5-352">A **Kereslet generálása**, a **Kereslet helyének megkeresése**, és a **Feltöltés futtatása** zárolással rendelkezik, amely biztosítja, hogy nem lesznek egyszerre aktiválva.</span><span class="sxs-lookup"><span data-stu-id="64ee5-352">The **Generate demand**, **Locate demand**, and **Run replenishment** processes have a lock to ensure that they can't be triggered at the same time.</span></span> <span data-ttu-id="64ee5-353">Ellenkező esetben a felhasznált adatok törrlődhetnek.</span><span class="sxs-lookup"><span data-stu-id="64ee5-353">Otherwise, the data that is used could be deleted.</span></span>
> - <span data-ttu-id="64ee5-354">A **Kereslet generálása**, a **Kereslet helyének megkeresése** folyamatok figyelmeztetést jelenítenek meg, ha a futtatás nem hozott létre rekordokat, vagy ha a rekordokból hiányoznak az adatok.</span><span class="sxs-lookup"><span data-stu-id="64ee5-354">The **Generate demand** and **Locate demand** processes show a warning if the run didn't generate records, or if the records are missing information.</span></span>
> - <span data-ttu-id="64ee5-355">Ha az **Időközökre bontási terv** lehetőséget választja, a lapon nem található **Új**, **Szerkesztés** vagy **Törlés** gomb a Művelet panelen, mert az adatforrás nem szerkeszthető.</span><span class="sxs-lookup"><span data-stu-id="64ee5-355">When you select **Slotting plan**, the page doesn't have **New**, **Edit**, or **Delete** buttons on the Action Pane, because the data source can't be edited.</span></span>
> - <span data-ttu-id="64ee5-356">Ha a **Feltöltés futtatása lehetőséget** választja, a rendszer ellenőrzi a kijelölt időközsablont és folyamatokat.</span><span class="sxs-lookup"><span data-stu-id="64ee5-356">When you select **Run replenishment**, the system validates the selected slot template and processes.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="64ee5-357">Feltöltés létrehozása</span><span class="sxs-lookup"><span data-stu-id="64ee5-357">Create replenishment</span></span>

<span data-ttu-id="64ee5-358">Miután létrehozta az időközökre bontási tervet, létre kell hoznia egy *feltöltési munkát* a terv alapján.</span><span class="sxs-lookup"><span data-stu-id="64ee5-358">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="64ee5-359">A Műveleti ablaktáblán kattintson a **Feltöltés futtatása** elemre.</span><span class="sxs-lookup"><span data-stu-id="64ee5-359">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="64ee5-360">A folyamat befejezésekor egy tájékoztató üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="64ee5-360">An informational message appears when the process is completed.</span></span> <span data-ttu-id="64ee5-361">Ez az üzenet a munka-összeállítási azonosítóhoz létrehozott fejlécek számát jelzi.</span><span class="sxs-lookup"><span data-stu-id="64ee5-361">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="64ee5-362">A rendszer az egyes sablonok sorában megadott utasításkód alapján határozza meg, hogy mely helyutasításokat kell használni.</span><span class="sxs-lookup"><span data-stu-id="64ee5-362">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="64ee5-363">Tippek</span><span class="sxs-lookup"><span data-stu-id="64ee5-363">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="64ee5-364">Automatikus időközökre bontás beállítása</span><span class="sxs-lookup"><span data-stu-id="64ee5-364">Set up automatic slotting</span></span>

<span data-ttu-id="64ee5-365">Miután minden szükséges elem be van állítva, beállíthatja, hogy az időközökre bontás automatikusan fusson a következő lépések követésével.</span><span class="sxs-lookup"><span data-stu-id="64ee5-365">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="64ee5-366">Ugorjon a **Raktárkezelés \> Feltöltés \> Időközökre bontás futtatása** pontra.</span><span class="sxs-lookup"><span data-stu-id="64ee5-366">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="64ee5-367">A futtatni kívánt időközökre bontási lépések megadása.</span><span class="sxs-lookup"><span data-stu-id="64ee5-367">Specify the slotting steps to run.</span></span> <span data-ttu-id="64ee5-368">Válasszon egy vagy több lépést a következő időközökre bontási lépések közül:</span><span class="sxs-lookup"><span data-stu-id="64ee5-368">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="64ee5-369">Igény létrehozása</span><span class="sxs-lookup"><span data-stu-id="64ee5-369">Generate demand</span></span>
    - <span data-ttu-id="64ee5-370">Igény megkeresése</span><span class="sxs-lookup"><span data-stu-id="64ee5-370">Locate demand</span></span>
    - <span data-ttu-id="64ee5-371">Feltöltési munka létrehozása</span><span class="sxs-lookup"><span data-stu-id="64ee5-371">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="64ee5-372">Az időközökre bontás lépései progresszívek.</span><span class="sxs-lookup"><span data-stu-id="64ee5-372">The slotting steps are progressive.</span></span> <span data-ttu-id="64ee5-373">Ha ki szeretné választani a *Kereslet helyének megkeresése* elemet, először ki kell választania a *Kereslet generálása* lépést.</span><span class="sxs-lookup"><span data-stu-id="64ee5-373">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="64ee5-374">Adja meg a használni időközökre bontási sablont.</span><span class="sxs-lookup"><span data-stu-id="64ee5-374">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="64ee5-375">Ha kívánja, a program automatikusan futtatja az ismétlődést.</span><span class="sxs-lookup"><span data-stu-id="64ee5-375">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="64ee5-376">A forgatókönyv gyakorlataihoz **ne** állítson be automatikus időközökre bontást.</span><span class="sxs-lookup"><span data-stu-id="64ee5-376">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]