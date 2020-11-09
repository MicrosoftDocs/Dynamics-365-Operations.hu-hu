---
title: Raktári időközökre bontás
description: Ez a témakör a raktári időközökre bontással kapcsolatban tartalmaz információkat. A raktári időközökre bontás lehetővé teszi a kereslet cikkek és mértékegységek szerinti konszolidációját a rendelésekből, amelyek Megrendelt, Lefoglalt vagy Kiadott állapottal rendelkeznek. A raktári kezelők számára intelligens módon segít kitárolási helyeket tervezni, mielőtt a rendeléseket a raktárba kiadnák, és kitárolási munkát hoznának létre.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: ed9e6eae2ecc8de8d5eeef4699678e93dd74f193
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017414"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="6df61-105">Raktári időközökre bontás</span><span class="sxs-lookup"><span data-stu-id="6df61-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6df61-106">A raktári időközökre bontás lehetővé teszi a kereslet cikkek és mértékegységek szerinti konszolidációját a rendelésekből, amelyek *Megrendelt* , *Lefoglalt* vagy *Kiadott* állapottal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="6df61-106">Warehouse slotting lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered* , *Reserved* , or *Released*.</span></span> <span data-ttu-id="6df61-107">A létrejövő igény ezután alkalmazható a kitárolásra használt helyekre, mennyiség, egység, fizikai méretek, rögzített helyek és egyebek alapján.</span><span class="sxs-lookup"><span data-stu-id="6df61-107">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="6df61-108">Az időközökre bontási terv létrehozását követően létrehozható a feltöltési munka, hogy a megfelelő mennyiségű készletet helyezze el minden helyen.</span><span class="sxs-lookup"><span data-stu-id="6df61-108">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="6df61-109">Ez a funkció a raktári kezelők számára intelligens módon segít kitárolási helyeket tervezni, mielőtt a rendeléseket a raktárba kiadnák, és kitárolási munkát hoznának létre.</span><span class="sxs-lookup"><span data-stu-id="6df61-109">This functionality helps warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

## <a name="turn-on-the-warehouse-slotting-feature"></a><span data-ttu-id="6df61-110">A raktári időközökre bontási funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="6df61-110">Turn on the warehouse slotting feature</span></span>

<span data-ttu-id="6df61-111">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="6df61-111">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="6df61-112">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="6df61-112">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6df61-113">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="6df61-113">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6df61-114">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="6df61-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6df61-115">**Funkció neve:** *Raktári időközökre bontási funkció*</span><span class="sxs-lookup"><span data-stu-id="6df61-115">**Feature name:** *Warehouse slotting feature*</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="6df61-116">Raktári időközökre bontás beállítása</span><span class="sxs-lookup"><span data-stu-id="6df61-116">Set up warehouse slotting</span></span>

<span data-ttu-id="6df61-117">A raktári időközökre bontási használatához a következő elemeket kell beállítania a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="6df61-117">To use warehouse slotting, you must set up the following elements in your system.</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="6df61-118">Mértékegységszintek létrehozása az időközökre bontáshoz</span><span class="sxs-lookup"><span data-stu-id="6df61-118">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="6df61-119">A mértékegységszintek lehetővé teszik a különböző mértékegységek csoportosítását az időközökre bontás céljából.</span><span class="sxs-lookup"><span data-stu-id="6df61-119">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="6df61-120">Ha például több dobozméret van kiválasztva ugyanarról a dobozkitárolási területről, akkor az összes mérethez létrehozható egy szint.</span><span class="sxs-lookup"><span data-stu-id="6df61-120">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="6df61-121">**Minden mértékegységhez létre kell hozni egy sort, amely a szint része.**</span><span class="sxs-lookup"><span data-stu-id="6df61-121">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="6df61-122">Lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Mértékegységszintek időközökre bontása**.</span><span class="sxs-lookup"><span data-stu-id="6df61-122">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="6df61-123">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6df61-123">Select **New**.</span></span>
1. <span data-ttu-id="6df61-124">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-124">In the header, set the following values:</span></span>

    - <span data-ttu-id="6df61-125">**Mértékegységszint:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="6df61-125">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="6df61-126">**Leírás:** *Minden doboz raklap*</span><span class="sxs-lookup"><span data-stu-id="6df61-126">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="6df61-127">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6df61-127">Select **Save**.</span></span>
1. <span data-ttu-id="6df61-128">A **Mértékegységek** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="6df61-128">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="6df61-129">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-129">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6df61-130">**Egység:** *Doboz*</span><span class="sxs-lookup"><span data-stu-id="6df61-130">**Unit:** *Box*</span></span>
    - <span data-ttu-id="6df61-131">**Leírás:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="6df61-131">**Description:** Leave this field blank.</span></span> <span data-ttu-id="6df61-132">A módosítások mentésekor a program automatikusan kitölti ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="6df61-132">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="6df61-133">**Egységosztály:** *Mennyiség*</span><span class="sxs-lookup"><span data-stu-id="6df61-133">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="6df61-134">Válassza az **Új** lehetőséget egy második sor rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="6df61-134">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="6df61-135">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6df61-136">**Egység:** *ea*</span><span class="sxs-lookup"><span data-stu-id="6df61-136">**Unit:** *ea*</span></span>
    - <span data-ttu-id="6df61-137">**Leírás:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="6df61-137">**Description:** Leave this field blank.</span></span> <span data-ttu-id="6df61-138">A módosítások mentésekor a program automatikusan kitölti ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="6df61-138">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="6df61-139">**Egységosztály:** *Mennyiség*</span><span class="sxs-lookup"><span data-stu-id="6df61-139">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="6df61-140">Válassza az **Új** lehetőséget egy harmadik sor rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="6df61-140">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="6df61-141">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6df61-142">**Egység:** *PL*</span><span class="sxs-lookup"><span data-stu-id="6df61-142">**Unit:** *PL*</span></span>
    - <span data-ttu-id="6df61-143">**Leírás:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="6df61-143">**Description:** Leave this field blank.</span></span> <span data-ttu-id="6df61-144">A módosítások mentésekor a program automatikusan kitölti ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="6df61-144">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="6df61-145">**Egységosztály:** *Mennyiség*</span><span class="sxs-lookup"><span data-stu-id="6df61-145">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="6df61-146">A szint mentéséhez válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="6df61-146">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="6df61-147">Utasításkód létrehozása az időközökre bontáshoz</span><span class="sxs-lookup"><span data-stu-id="6df61-147">Create a directive code for slotting</span></span>

<span data-ttu-id="6df61-148">Ki kell választania a sablonhoz társítani kívánt utasításkódot.</span><span class="sxs-lookup"><span data-stu-id="6df61-148">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="6df61-149">Ugrás a **Raktárkezelés \> Beállítás \> Utasítskódok** elemre.</span><span class="sxs-lookup"><span data-stu-id="6df61-149">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="6df61-150">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="6df61-150">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6df61-151">Az **irányelv kódja** mezőbe írja be az *Időközökre bontás* értéket.</span><span class="sxs-lookup"><span data-stu-id="6df61-151">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="6df61-152">Az **Utasítás leírása** mezőbe írja be az *Időközökre bontás* értéket.</span><span class="sxs-lookup"><span data-stu-id="6df61-152">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="6df61-153">Időközökre bontás sablonok beállítása</span><span class="sxs-lookup"><span data-stu-id="6df61-153">Set up slotting templates</span></span>

<span data-ttu-id="6df61-154">Minden időközökre bontási sablon azt vezérli, hogy a készlet milyen módon van hozzárendelve egy adott raktár helyeihez.</span><span class="sxs-lookup"><span data-stu-id="6df61-154">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="6df61-155">Minden sablonnak tartalmaznia kell egy sort mindegyik időközökre bontási specifikációból.</span><span class="sxs-lookup"><span data-stu-id="6df61-155">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="6df61-156">Az ebben a szakaszban található eljárások segítségével lehet beállítani az időközökre bontási sablonokat.</span><span class="sxs-lookup"><span data-stu-id="6df61-156">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="6df61-157">Ugorjon a **Raktárkezelés \> Beállítás \> Feltöltés \> Időközökre bontási sablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="6df61-157">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="6df61-158">Válassza az **Új** lehetőséget egy sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6df61-158">Select **New** to create a template.</span></span>

<span data-ttu-id="6df61-159">Ezután be kell állítania a sablon fejlécét, az időközökre bontási specifikációkat és a helyutasításokat, ahogyan azt a következő alszakaszok részletezik.</span><span class="sxs-lookup"><span data-stu-id="6df61-159">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span>

#### <a name="set-up-a-slotting-template-header"></a><span data-ttu-id="6df61-160">Időközökre bontási sablon fejlécének beállítása</span><span class="sxs-lookup"><span data-stu-id="6df61-160">Set up a slotting template header</span></span>

1. <span data-ttu-id="6df61-161">A sablon fejlécében adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-161">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="6df61-162">**Időközökre bontási sablon** _61_</span><span class="sxs-lookup"><span data-stu-id="6df61-162">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="6df61-163">**Leírás:** _61_</span><span class="sxs-lookup"><span data-stu-id="6df61-163">**Description:** _61_</span></span>
    - <span data-ttu-id="6df61-164">**Kereslet típusa:** *Értékesítési rendelés*</span><span class="sxs-lookup"><span data-stu-id="6df61-164">**Demand type:** *Sales order*</span></span>

        <span data-ttu-id="6df61-165">Az egyedüli támogatott kereslettípus jelenleg az *Értékesítési rendelés*.</span><span class="sxs-lookup"><span data-stu-id="6df61-165">Currently, *Sales order* is the only demand type that is supported.</span></span>

    - <span data-ttu-id="6df61-166">**Kereslet stratégia:** _Megrendelve_</span><span class="sxs-lookup"><span data-stu-id="6df61-166">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="6df61-167">A következő értékek állnak rendelkezésre ebben a mezőben:</span><span class="sxs-lookup"><span data-stu-id="6df61-167">The following values are available in this field:</span></span>

        - <span data-ttu-id="6df61-168">**Megrendelt** – Az értékesítési rendelés teljes megrendelt mennyiségét keresletnek kell tekinteni.</span><span class="sxs-lookup"><span data-stu-id="6df61-168">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="6df61-169">**Lefoglalva** – Csak az értékesítési rendelés sor lefoglalt (tényleges és rendelt) mennyiségét kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="6df61-169">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>

    - <span data-ttu-id="6df61-170">**Raktár:** _61_</span><span class="sxs-lookup"><span data-stu-id="6df61-170">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="6df61-171">**A hullám keresletének engedélyezése nem foglalt mennyiségek használatához:** _Igen_</span><span class="sxs-lookup"><span data-stu-id="6df61-171">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="6df61-172">Megadhat egy lekérdezést is a kiértékelt kereslet hatókörének leszűkítéséhez.</span><span class="sxs-lookup"><span data-stu-id="6df61-172">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="6df61-173">Időközökre bontási specifikációk beállítása ez egyes sablontípusokhoz</span><span class="sxs-lookup"><span data-stu-id="6df61-173">Set up slotting specifications for each template</span></span>

<span data-ttu-id="6df61-174">Minden létrehozott sablon esetében hajtsa végre az alábbi lépéseket egy sor hozzáadásához az egyes időközökre bontási specifikációkhoz.</span><span class="sxs-lookup"><span data-stu-id="6df61-174">For each template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="6df61-175">Az **Időközökre bontási részletek** gyorslapján válassza az **Új** parancsot, és hozzon létre egy sablonfájlt.</span><span class="sxs-lookup"><span data-stu-id="6df61-175">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="6df61-176">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-176">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6df61-177">**Sorozat:** _1_</span><span class="sxs-lookup"><span data-stu-id="6df61-177">**Sequence:** _1_</span></span>
    - <span data-ttu-id="6df61-178">**Leírás:** _Rögzített hely_</span><span class="sxs-lookup"><span data-stu-id="6df61-178">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="6df61-179">**Minimális mennyiség:** _1_</span><span class="sxs-lookup"><span data-stu-id="6df61-179">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="6df61-180">Ez a mező azt a minimális keresleti mennyiséget határozza meg, amely a sorhoz szükséges.</span><span class="sxs-lookup"><span data-stu-id="6df61-180">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="6df61-181">**Maximális mennyiség:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="6df61-181">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="6df61-182">Ez a mező azt a maximális keresleti mennyiséget határozza meg, amely a sorhoz érvényes.</span><span class="sxs-lookup"><span data-stu-id="6df61-182">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="6df61-183">**Egység:** Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="6df61-183">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="6df61-184">Ez a mező azt a mértékegységet határozza meg, amelyre a minimális és maximális mennyiségek utalnak.</span><span class="sxs-lookup"><span data-stu-id="6df61-184">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="6df61-185">**Mértékegységszint:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="6df61-185">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="6df61-186">Ez a mező azt a keresleti mértékegységet határozza meg, amely a sorhoz érvényes.</span><span class="sxs-lookup"><span data-stu-id="6df61-186">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="6df61-187">(További információt a [Mértékegységszintek beállítása időközökre bontáshoz](#unit-tiers) című részben talál, a téma korábbi részében.)</span><span class="sxs-lookup"><span data-stu-id="6df61-187">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="6df61-188">**Időköz-hozzárendelési feltétel társítása:** _Figyelembe vett mennyiség_</span><span class="sxs-lookup"><span data-stu-id="6df61-188">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="6df61-189">A következő értékek állnak rendelkezésre ebben a mezőben:</span><span class="sxs-lookup"><span data-stu-id="6df61-189">The following values are available in this field:</span></span>

        - <span data-ttu-id="6df61-190">**Üresen hagyott** – Ez a rendszer feltételezi, hogy a kitárolási terület minden helye üres, és a készlethez tartozó helyeket nem szabad ellenőrizni.</span><span class="sxs-lookup"><span data-stu-id="6df61-190">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="6df61-191">**Figyelembe vett mennyiség** – Ennek a rendszernek ellenőriznie kell a helyeket a készlet kitárolási területein, és ki kell hagynia minden nem üres helyet.</span><span class="sxs-lookup"><span data-stu-id="6df61-191">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>

    - <span data-ttu-id="6df61-192">**Irányelv kódja:** _Időközökre bontási_</span><span class="sxs-lookup"><span data-stu-id="6df61-192">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="6df61-193">Ez a mező határozza meg a feltöltési munka kitárolási helyének megtalálásához használt helyutasítást.</span><span class="sxs-lookup"><span data-stu-id="6df61-193">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="6df61-194">**Túlcsordulási hely:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="6df61-194">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="6df61-195">Ez a mező azt a helyet határozza meg, ahová a készletet elhelyezik, ha a sor feldolgozásakor nem található hely a mennyiséghez.</span><span class="sxs-lookup"><span data-stu-id="6df61-195">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="6df61-196">**Felengedés engedélyezése:** _Igen_</span><span class="sxs-lookup"><span data-stu-id="6df61-196">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="6df61-197">Ha ez a beállítás *Igen* értékre van állítva, akkor ha a kereslet nem bontható időközökre, létrejön munka a készlet felvételéhez olyan készlettel rendelkező helyekről, ahol nincs időközökre bontás.</span><span class="sxs-lookup"><span data-stu-id="6df61-197">When this option is set to *Yes* , if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="6df61-198">Ezután a sablon újra futni fog.</span><span class="sxs-lookup"><span data-stu-id="6df61-198">The template is then run again.</span></span> <span data-ttu-id="6df61-199">Ez alkalommal figyelmen kívül hagyja a készletet a helyeken.</span><span class="sxs-lookup"><span data-stu-id="6df61-199">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="6df61-200">Ez a funkció a legjobban akkor működik, ha a **Időköz-hozzárendelési feltétel társítása** mező _Figyelembe vett mennyiség_ értékkel van megadva.</span><span class="sxs-lookup"><span data-stu-id="6df61-200">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="6df61-201">**Rögzített hely használata:** _Csak a termék rögzített helyei_</span><span class="sxs-lookup"><span data-stu-id="6df61-201">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="6df61-202">A következő értékek állnak rendelkezésre ebben a mezőben:</span><span class="sxs-lookup"><span data-stu-id="6df61-202">The following values are available in this field:</span></span>

        - <span data-ttu-id="6df61-203">**Rögzített és nem rögzített helyek** – A rendszer nem korlátozható csak a rögzített helyek használatára.</span><span class="sxs-lookup"><span data-stu-id="6df61-203">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="6df61-204">**Csak a termék rögzített helyei** – A rendszer csak a termék rögzített helyeit tartalmazó tárolóhelyeket rögzít.</span><span class="sxs-lookup"><span data-stu-id="6df61-204">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="6df61-205">**Csak a termékváltozat rögzített helyei** – A rendszer csak a termékváltozat rögzített helyeit tartalmazó tárolóhelyeket rögzít.</span><span class="sxs-lookup"><span data-stu-id="6df61-205">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

1. <span data-ttu-id="6df61-206">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6df61-206">Select **Save**.</span></span>
1. <span data-ttu-id="6df61-207">Ha második sablonsort szeretne létrehozni, kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="6df61-207">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="6df61-208">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6df61-209">**Sorozat:** _2_</span><span class="sxs-lookup"><span data-stu-id="6df61-209">**Sequence:** _2_</span></span>
    - <span data-ttu-id="6df61-210">**Leírás:** _Egyéb_</span><span class="sxs-lookup"><span data-stu-id="6df61-210">**Description:** _Other_</span></span>
    - <span data-ttu-id="6df61-211">**Minimális mennyiség:** _1_</span><span class="sxs-lookup"><span data-stu-id="6df61-211">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="6df61-212">**Maximális mennyiség:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="6df61-212">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="6df61-213">**Egység:** Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="6df61-213">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="6df61-214">**Mértékegységszint:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="6df61-214">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="6df61-215">**Időköz-hozzárendelési feltétel társítása:** _Figyelembe vett mennyiség_</span><span class="sxs-lookup"><span data-stu-id="6df61-215">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="6df61-216">**Irányelv kódja:** _Időközökre bontási_</span><span class="sxs-lookup"><span data-stu-id="6df61-216">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="6df61-217">**Túlcsordulási hely:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="6df61-217">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="6df61-218">**Felengedés engedélyezése:** _Igen_</span><span class="sxs-lookup"><span data-stu-id="6df61-218">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="6df61-219">**Rögzített helyek használata:** _Rögzített és nem rögzített helyek_</span><span class="sxs-lookup"><span data-stu-id="6df61-219">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="6df61-220">A második sor lekérdezésében megadhatja azokat a feltételeket, amelyekkel meghatározhatja, hogy milyen helyeken lehet az adott sor igénye időközökre bontható.</span><span class="sxs-lookup"><span data-stu-id="6df61-220">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="6df61-221">Válassza ki azt a sort, amelynél a **Sorozat** mező értéke *2*.</span><span class="sxs-lookup"><span data-stu-id="6df61-221">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="6df61-222">Válassza ki a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6df61-222">Select **Edit query**.</span></span>
1. <span data-ttu-id="6df61-223">A **Tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="6df61-223">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="6df61-224">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-224">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6df61-225">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="6df61-225">**Table:** *Locations*</span></span>
    - <span data-ttu-id="6df61-226">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="6df61-226">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="6df61-227">**Mező:** *Hely profilazonosítója*</span><span class="sxs-lookup"><span data-stu-id="6df61-227">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="6df61-228">**Feltételek:** *Kitárolás-06* (Válassza ki a dupla plusz jelet \[**++**\] a mezőben a lista kibontásához, majd válassza a *Kitárolás-06* - *6. kitárolási hely* elemet.)</span><span class="sxs-lookup"><span data-stu-id="6df61-228">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="6df61-229">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6df61-229">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="6df61-230">Helyutasítások beállítása</span><span class="sxs-lookup"><span data-stu-id="6df61-230">Set up location directives</span></span>

<span data-ttu-id="6df61-231">A kitárolások időközökre bontásának támogatásához be kell állítani legalább egy helyutasítást.</span><span class="sxs-lookup"><span data-stu-id="6df61-231">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="6df61-232">Az ebben a szakaszban található eljárások segítségével beállíthatja a kitárolások időközökre bontásának új *feltöltési helyutasítását*.</span><span class="sxs-lookup"><span data-stu-id="6df61-232">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="6df61-233">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="6df61-233">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="6df61-234">A bal oldali ablaktáblában állítsa a **Munkarendelés típusa** mezőt a *Feltöltés* értékre.</span><span class="sxs-lookup"><span data-stu-id="6df61-234">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="6df61-235">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="6df61-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6df61-236">Az új helyutasítás fejlécében, a **Név** mezőbe írja be a *61 kitárolás időközökre bontása* értéket.</span><span class="sxs-lookup"><span data-stu-id="6df61-236">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="6df61-237">Konfigurálja a Helyutasítások gyorslapot</span><span class="sxs-lookup"><span data-stu-id="6df61-237">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="6df61-238">A **Helyutasítások** gyorslapon állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="6df61-238">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="6df61-239">Az összes többi mezőben hagyja meg az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="6df61-239">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="6df61-240">**Munka típusa:** _Kitárolás_</span><span class="sxs-lookup"><span data-stu-id="6df61-240">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="6df61-241">**Telephely:** _6_</span><span class="sxs-lookup"><span data-stu-id="6df61-241">**Site:** _6_</span></span>
    - <span data-ttu-id="6df61-242">**Raktár:** _61_</span><span class="sxs-lookup"><span data-stu-id="6df61-242">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="6df61-243">**Irányelv kódja:** _Időközökre bontási_</span><span class="sxs-lookup"><span data-stu-id="6df61-243">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="6df61-244">A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="6df61-244">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="6df61-245">A Sorok gyorslap konfigurálása</span><span class="sxs-lookup"><span data-stu-id="6df61-245">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="6df61-246">A **Sorok** gyorslapon kattintson az **Új** lehetőségre egy sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6df61-246">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="6df61-247">Az új sorban állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="6df61-247">On the new line, set the following values.</span></span> <span data-ttu-id="6df61-248">Az összes többi mezőben hagyja meg az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="6df61-248">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="6df61-249">**Kezdő mennyiség:** _0_</span><span class="sxs-lookup"><span data-stu-id="6df61-249">**From quantity:** _0_</span></span>
    - <span data-ttu-id="6df61-250">**Záró mennyiség:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="6df61-250">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="6df61-251">A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="6df61-251">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="6df61-252">Konfigurálja a Helyutasítási műveletek gyorslapot</span><span class="sxs-lookup"><span data-stu-id="6df61-252">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="6df61-253">A **Helyutasítási műveletek** gyorslapon kattintson az **Új** lehetőségre egy sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6df61-253">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="6df61-254">Az új sorban állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="6df61-254">On the new line, set the following values.</span></span> <span data-ttu-id="6df61-255">Az összes többi mezőben hagyja meg az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="6df61-255">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="6df61-256">**Név:** _Ömlesztett_</span><span class="sxs-lookup"><span data-stu-id="6df61-256">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="6df61-257">**Stratégia:** _Nincs_</span><span class="sxs-lookup"><span data-stu-id="6df61-257">**Strategy:** _None_</span></span>

1. <span data-ttu-id="6df61-258">Válassza a **Mentés** lehetőséget, ha elérhetővé szeretné tenni a **Lekérdezés szerkesztése** gombot.</span><span class="sxs-lookup"><span data-stu-id="6df61-258">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="6df61-259">A lekérdezés szerkesztése</span><span class="sxs-lookup"><span data-stu-id="6df61-259">Edit the query</span></span>

1. <span data-ttu-id="6df61-260">A **Helyutasítás műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6df61-260">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="6df61-261">A **Tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="6df61-261">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="6df61-262">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-262">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6df61-263">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="6df61-263">**Table:** *Locations*</span></span>
    - <span data-ttu-id="6df61-264">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="6df61-264">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="6df61-265">**Mező:** *Zóna azonosítója*</span><span class="sxs-lookup"><span data-stu-id="6df61-265">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="6df61-266">**Feltételek:** *Ömlesztett* (Válassza ki a dupla plusz jelet \[**++**\] a mezőben a lista kibontásához, majd válassza az *Ömlesztett* kitárolási hely elemet.)</span><span class="sxs-lookup"><span data-stu-id="6df61-266">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="6df61-267">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6df61-267">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="6df61-268">Forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="6df61-268">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="6df61-269">Forgatókönyv beállítása</span><span class="sxs-lookup"><span data-stu-id="6df61-269">Set up the scenario</span></span>

<span data-ttu-id="6df61-270">Ehhez a forgatókönyvhöz használja a beépített mintaadatokat, és hozza létre a szakaszban ismertetett rekordokat.</span><span class="sxs-lookup"><span data-stu-id="6df61-270">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="6df61-271">A USMF mintaadatok használata</span><span class="sxs-lookup"><span data-stu-id="6df61-271">Use the USMF sample data</span></span>

<span data-ttu-id="6df61-272">Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="6df61-272">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="6df61-273">Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="6df61-273">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="6df61-274">Igény létrehozása</span><span class="sxs-lookup"><span data-stu-id="6df61-274">Create demand</span></span>

<span data-ttu-id="6df61-275">Hajtsa végre az alábbi lépéseket, és hozza létre azt az igényt, amelyre alkalmazni fogja az időközökre bontást.</span><span class="sxs-lookup"><span data-stu-id="6df61-275">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="6df61-276">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="6df61-276">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="6df61-277">Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="6df61-277">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="6df61-278">Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőben válassza ki azt az _US-007_ értéket.</span><span class="sxs-lookup"><span data-stu-id="6df61-278">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="6df61-279">A **Raktár** mezőben válassza ki az _61_ értéket.</span><span class="sxs-lookup"><span data-stu-id="6df61-279">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="6df61-280">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6df61-280">Select **OK**.</span></span>
1. <span data-ttu-id="6df61-281">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="6df61-281">The new sales order is opened.</span></span> <span data-ttu-id="6df61-282">Tartalmaz egy üres sort az **Értékesítési rendelés sorai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="6df61-282">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="6df61-283">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-283">On this line, set the following values:</span></span>

    - <span data-ttu-id="6df61-284">**Cikk:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="6df61-284">**Item:** _L0101_</span></span>
    - <span data-ttu-id="6df61-285">**Mennyiség:** _20_</span><span class="sxs-lookup"><span data-stu-id="6df61-285">**Quantity:** _20_</span></span>

1. <span data-ttu-id="6df61-286">Válassza ki a **Sor hozzáadása** lehetőséget egy új sor hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-286">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="6df61-287">**Cikk:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="6df61-287">**Item:** _T0100_</span></span>
    - <span data-ttu-id="6df61-288">**Mennyiség:** _8_</span><span class="sxs-lookup"><span data-stu-id="6df61-288">**Quantity:** _8_</span></span>

1. <span data-ttu-id="6df61-289">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6df61-289">Select **Save**.</span></span>
1. <span data-ttu-id="6df61-290">Második értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="6df61-290">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="6df61-291">Az **Értékesítési rendelés létrehozása** párbeszédpanelen, a **Vevői számla** mezőben válassza ki azt az _US-008_ értéket.</span><span class="sxs-lookup"><span data-stu-id="6df61-291">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="6df61-292">A **Raktár** mezőben válassza ki az _61_ értéket.</span><span class="sxs-lookup"><span data-stu-id="6df61-292">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="6df61-293">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="6df61-293">The new sales order is opened.</span></span> <span data-ttu-id="6df61-294">Tartalmaz egy üres sort az **Értékesítési rendelés sorai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="6df61-294">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="6df61-295">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6df61-295">On this line, set the following values:</span></span>

    - <span data-ttu-id="6df61-296">**Cikk:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="6df61-296">**Item:** _T0100_</span></span>
    - <span data-ttu-id="6df61-297">**Mennyiség:** _1_</span><span class="sxs-lookup"><span data-stu-id="6df61-297">**Quantity:** _1_</span></span>

1. <span data-ttu-id="6df61-298">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6df61-298">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="6df61-299">Haladjon végig egy tipikus időközökre bontási forgatókönyvön</span><span class="sxs-lookup"><span data-stu-id="6df61-299">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="6df61-300">Miután az összes előfeltétel-elem a helyén van, ahogy azt az előző részben ismertették, készen áll a funkció kipróbálására a jelen szakasz minden egyes gyakorlatán keresztül.</span><span class="sxs-lookup"><span data-stu-id="6df61-300">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="6df61-301">Igény létrehozása</span><span class="sxs-lookup"><span data-stu-id="6df61-301">Generate demand</span></span>

1. <span data-ttu-id="6df61-302">Lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Időközökre bontási sablonok** pontra, és válassza ki a korábban létrehozott időközökre bontási sablont.</span><span class="sxs-lookup"><span data-stu-id="6df61-302">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates** , and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="6df61-303">A Művelet ablaktáblán válassza ki a **Kereslet generálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="6df61-303">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="6df61-304">Ez a parancs a rendszerben található összes igényt kiértékeli, és megfelel az időközökre bontási sablon lekérdezésének.</span><span class="sxs-lookup"><span data-stu-id="6df61-304">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="6df61-305">A program ezután összesíti az összes rendelésen szereplő teljes igényt, egy sorban/mértékegységben.</span><span class="sxs-lookup"><span data-stu-id="6df61-305">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="6df61-306">A folyamat befejezésekor egy tájékoztató üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6df61-306">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="6df61-307">Időközökre bontás igénye</span><span class="sxs-lookup"><span data-stu-id="6df61-307">Slotting demand</span></span>

<span data-ttu-id="6df61-308">Az *időközökre bontási igény* a keresletgenerálás eredményét jeleníti meg az időközökre bontási sablon beállítása alapján.</span><span class="sxs-lookup"><span data-stu-id="6df61-308">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="6df61-309">A Művelet panelen válassza az **Időközökre bontási igény** elemet a **Keresletgenerálás** parancsból származó eredmények megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="6df61-309">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="6df61-310">Az időközökre bontási igény sorai szerkeszthetők.</span><span class="sxs-lookup"><span data-stu-id="6df61-310">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="6df61-311">Lehetőség van egy sor törlésére, új sor hozzáadására vagy a sor részletes adatainak szerkesztésére.</span><span class="sxs-lookup"><span data-stu-id="6df61-311">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="6df61-312">A kereslet manuálisan is szerkeszthető, illetve a külső rendszerből is importálhatja az adatkezelés segítségével.</span><span class="sxs-lookup"><span data-stu-id="6df61-312">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="6df61-313">Bármi is szerepel az időközökre bontási igényben a következő lépésben, az kerül felhasználásra, függetlenül attól, hogy honnan érkezett.</span><span class="sxs-lookup"><span data-stu-id="6df61-313">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="6df61-314">Igény megkeresése</span><span class="sxs-lookup"><span data-stu-id="6df61-314">Locate demand</span></span>

<span data-ttu-id="6df61-315">Miután létrehozta a keresletet, az **Kereslet helyének megkeresése** paranccsal hozhat létre *időközökre bontási tervet*.</span><span class="sxs-lookup"><span data-stu-id="6df61-315">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="6df61-316">A Művelet ablaktáblán válassza ki a **Kereslet helyének megkeresése** elemet.</span><span class="sxs-lookup"><span data-stu-id="6df61-316">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="6df61-317">Az időközökre bontási folyamat fut.</span><span class="sxs-lookup"><span data-stu-id="6df61-317">The slotting process runs.</span></span> <span data-ttu-id="6df61-318">A folyamat befejezésekor egy tájékoztató üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6df61-318">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="6df61-319">Időközökre bontási terv</span><span class="sxs-lookup"><span data-stu-id="6df61-319">Slotting plan</span></span>

<span data-ttu-id="6df61-320">Az időközökre bontási terv azt a helyet jeleníti meg, amelyhez az egyes cikkek/mennyiségek hozzá vannak rendelve, hogy történt-e túlcsordulás, létrehozásra került-e felengedési munka, valamint a sablon felhasznált sorát.</span><span class="sxs-lookup"><span data-stu-id="6df61-320">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="6df61-321">**Minden olyan igényt, amelyet nem lehet időközökre bontani, piros színnel van kijelölve.**</span><span class="sxs-lookup"><span data-stu-id="6df61-321">**Any demand that could not be slotted is highlighted in red.**</span></span>

- <span data-ttu-id="6df61-322">Az eredmények megtekintéséhez válassza ki az **Időközökre bontási tervet** a Művelet ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="6df61-322">On the Action Pane, select **Slotting plan** to view the results.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="6df61-323">Feltöltés létrehozása</span><span class="sxs-lookup"><span data-stu-id="6df61-323">Create replenishment</span></span>

<span data-ttu-id="6df61-324">Miután létrehozta az időközökre bontási tervet, létre kell hoznia egy *feltöltési munkát* a terv alapján.</span><span class="sxs-lookup"><span data-stu-id="6df61-324">After the slotting plan has been created, you must create *replenishment work* , based on the plan.</span></span>

- <span data-ttu-id="6df61-325">A Műveleti ablaktáblán kattintson a **Feltöltés futtatása** elemre.</span><span class="sxs-lookup"><span data-stu-id="6df61-325">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="6df61-326">A folyamat befejezésekor egy tájékoztató üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6df61-326">An informational message appears when the process is completed.</span></span> <span data-ttu-id="6df61-327">Ez az üzenet a munka-összeállítási azonosítóhoz létrehozott fejlécek számát jelzi.</span><span class="sxs-lookup"><span data-stu-id="6df61-327">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="6df61-328">A rendszer az egyes sablonok sorában megadott utasításkód alapján határozza meg, hogy mely helyutasításokat kell használni.</span><span class="sxs-lookup"><span data-stu-id="6df61-328">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="6df61-329">Tippek</span><span class="sxs-lookup"><span data-stu-id="6df61-329">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="6df61-330">Automatikus időközökre bontás beállítása</span><span class="sxs-lookup"><span data-stu-id="6df61-330">Set up automatic slotting</span></span>

<span data-ttu-id="6df61-331">Miután minden szükséges elem be van állítva, beállíthatja, hogy az időközökre bontás automatikusan fusson a következő lépések követésével.</span><span class="sxs-lookup"><span data-stu-id="6df61-331">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="6df61-332">Ugorjon a **Raktárkezelés \> Feltöltés \> Időközökre bontás futtatása** pontra.</span><span class="sxs-lookup"><span data-stu-id="6df61-332">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="6df61-333">A futtatni kívánt időközökre bontási lépések megadása.</span><span class="sxs-lookup"><span data-stu-id="6df61-333">Specify the slotting steps to run.</span></span> <span data-ttu-id="6df61-334">Válasszon egy vagy több lépést a következő időközökre bontási lépések közül:</span><span class="sxs-lookup"><span data-stu-id="6df61-334">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="6df61-335">Igény létrehozása</span><span class="sxs-lookup"><span data-stu-id="6df61-335">Generate demand</span></span>
    - <span data-ttu-id="6df61-336">Igény megkeresése</span><span class="sxs-lookup"><span data-stu-id="6df61-336">Locate demand</span></span>
    - <span data-ttu-id="6df61-337">Feltöltési munka létrehozása</span><span class="sxs-lookup"><span data-stu-id="6df61-337">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="6df61-338">Az időközökre bontás lépései progresszívek.</span><span class="sxs-lookup"><span data-stu-id="6df61-338">The slotting steps are progressive.</span></span> <span data-ttu-id="6df61-339">Ha ki szeretné választani a *Kereslet helyének megkeresése* elemet, először ki kell választania a *Kereslet generálása* lépést.</span><span class="sxs-lookup"><span data-stu-id="6df61-339">If you want to select *Locate demand* , you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="6df61-340">Adja meg a használni időközökre bontási sablont.</span><span class="sxs-lookup"><span data-stu-id="6df61-340">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="6df61-341">Ha kívánja, a program automatikusan futtatja az ismétlődést.</span><span class="sxs-lookup"><span data-stu-id="6df61-341">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="6df61-342">A forgatókönyv gyakorlataihoz **ne** állítson be automatikus időközökre bontást.</span><span class="sxs-lookup"><span data-stu-id="6df61-342">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
