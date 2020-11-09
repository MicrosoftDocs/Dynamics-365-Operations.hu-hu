---
title: Feltöltés a zóna küszöbértéke alapján
description: A zónaalapú feltöltés a minimális/maximális (min/max) feltöltési stratégiát használja, de az egész raktári zónákat értékeli az egyes helyek helyett. Ezért a raktárkezelők gyorsabban megtudhatják, ha a kitárolási zónában további készlet szükséges.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e13b5fd895fca7f8fe77809348d63ed8867dea9e
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017322"
---
# <a name="zone-threshold-replenishment"></a><span data-ttu-id="7097c-104">Feltöltés a zóna küszöbértéke alapján</span><span class="sxs-lookup"><span data-stu-id="7097c-104">Zone threshold replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7097c-105">A zónaalapú feltöltés a minimális/maximális (min/max) [feltöltési](replenishment.md) stratégiát használja, de az egész raktári zónákat értékeli az egyes helyek helyett.</span><span class="sxs-lookup"><span data-stu-id="7097c-105">Zone-based replenishment uses a minimum/maximum (min/max) [replenishment](replenishment.md) strategy, but it evaluates whole warehouse zones instead of just individual locations.</span></span> <span data-ttu-id="7097c-106">Ezért a raktárkezelők gyorsabban megtudhatják, ha a kitárolási zónában további készlet szükséges.</span><span class="sxs-lookup"><span data-stu-id="7097c-106">Therefore, warehouse managers can more quickly learn when additional inventory is required in a picking zone.</span></span>

<span data-ttu-id="7097c-107">Ennek a funkciónak a beállítása a helyalapú feltöltés beállításához hasonlít.</span><span class="sxs-lookup"><span data-stu-id="7097c-107">The setup for this feature resembles the setup for location-based replenishment.</span></span> <span data-ttu-id="7097c-108">Ha azonban a minimális/maximális feltöltéshez beállítja a sablont, akkor megadhatja azt is, hogy a küszöböt egy helyenként vagy zónánként kell-e értékelni.</span><span class="sxs-lookup"><span data-stu-id="7097c-108">However, when you set up a template for min/max replenishment, you can also specify whether the threshold should be evaluated per location or per zone.</span></span> <span data-ttu-id="7097c-109">Ha zónákon alapuló értékelést állított be, akkor meghatározott zónákat kell hozzáadnia a zónák kiválasztása lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="7097c-109">If you set up evaluation that is based on zones, you must add specific zones to the zone selection query.</span></span>

<span data-ttu-id="7097c-110">A helyalapú min/max feltöltéshez hasonlóan a zóna alapú min/max feltöltés alapja a minimális készletküszöb beállítása, amely a kiválasztott cikkekre vonatkozó feltöltési munka létrehozását indítja.</span><span class="sxs-lookup"><span data-stu-id="7097c-110">Like location-based min/max replenishment, zone-based min/max replenishment is based the setup of a minimum inventory threshold that triggers the creation of replenishment work for selected items.</span></span> <span data-ttu-id="7097c-111">Ez a feltöltési munka növeli a készletet a zóna megadott maximális küszöbértékéig.</span><span class="sxs-lookup"><span data-stu-id="7097c-111">This replenishment work will increase inventory up to the specified maximum threshold for the zone.</span></span>

> [!NOTE]
> <span data-ttu-id="7097c-112">Az aktuális kiadásban nem használhatók a zónák feltöltési folyamatai a termékváltozatokhoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-112">Zone replenishment processes for product variants aren't supported in the current release.</span></span>


<span data-ttu-id="7097c-113">A hely alapú min/max feltöltéssel ellentétben a zónaalapú min/max feltöltés nem igényel fix helyeket annak kiértékeléséhez, hogy a helyeknek egy adott terméket tárolniuk kell-e.</span><span class="sxs-lookup"><span data-stu-id="7097c-113">Unlike location-based min/max replenishment, zone-based min/max replenishment doesn't require fixed locations to evaluate whether locations should store a specific item.</span></span> <span data-ttu-id="7097c-114">Ennélfogva a zónákon alapuló feltöltésnél a min/max feltöltés akkor is használható, ha a raktárban nincs minden egyes elemhez vagy elemvariánshoz rögzített hely.</span><span class="sxs-lookup"><span data-stu-id="7097c-114">Therefore, zone-based replenishment lets you use min/max replenishment even if you don't have fixed locations for each item or item variant in the warehouse.</span></span> <span data-ttu-id="7097c-115">Ha a zónában szereplő mennyiség a meghatározott minimális küszöbérték alá esik, akkor létrejön a feltöltési munka.</span><span class="sxs-lookup"><span data-stu-id="7097c-115">When a quantity in the zone falls below the specified minimum threshold, replenishment work is created.</span></span> <span data-ttu-id="7097c-116">A helyutasítások határozzák meg, hogy a készlet mely meghatározott helyen kerüljön elhelyezésre.</span><span class="sxs-lookup"><span data-stu-id="7097c-116">Location directives will determine which specific location the inventory should be put into.</span></span>

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a><span data-ttu-id="7097c-117">A Feltöltés a zóna küszöbértéke alapján funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="7097c-117">Turn on the Zone threshold replenishment feature</span></span>

<span data-ttu-id="7097c-118">A *Feltöltés a zóna küszöbértéke alapján* funkció használatához a rendszerben be kell azt kapcsolni.</span><span class="sxs-lookup"><span data-stu-id="7097c-118">Before you can use the *Zone threshold replenishment* feature, it must be turned on in your system.</span></span> <span data-ttu-id="7097c-119">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="7097c-119">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="7097c-120">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="7097c-120">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="7097c-121">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="7097c-121">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="7097c-122">**Funkció neve:** *Feltöltés a zóna küszöbértéke alapján*</span><span class="sxs-lookup"><span data-stu-id="7097c-122">**Feature name:** *Zone threshold replenishment*</span></span>

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a><span data-ttu-id="7097c-123">Zónaalapú feltöltés beállítása</span><span class="sxs-lookup"><span data-stu-id="7097c-123">Set up zone-based replenishment</span></span>

<span data-ttu-id="7097c-124">A zónaalapú feltöltés beállításához a rendszer több részét kell konfigurálnia.</span><span class="sxs-lookup"><span data-stu-id="7097c-124">To set up zone-based replenishment, you must configure several parts of the system.</span></span> <span data-ttu-id="7097c-125">Ez a szakasz bemutatja a különböző beállításokat, valamint a bemutató adatértékeket biztosít, amelyeket meg lehet adni, ha végig akar haladni a témakör végén található forgatókönyvön.</span><span class="sxs-lookup"><span data-stu-id="7097c-125">This section introduces the various settings and provides demo data values that you can enter if you want to work through the scenario at the end of this topic.</span></span>

### <a name="set-up-directive-codes"></a><span data-ttu-id="7097c-126">Utasításkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="7097c-126">Set up directive codes</span></span>

<span data-ttu-id="7097c-127">Az [utasításkódok](control-warehouse-location-directives.md) segítségével a munkasablonban használt helysablon meghatározásakor pontosabban járhat el.</span><span class="sxs-lookup"><span data-stu-id="7097c-127">[Directive codes](control-warehouse-location-directives.md) let you be more specific when you define the location template that is used in a work template.</span></span> <span data-ttu-id="7097c-128">Mindegyik kód egy olyan közös értéket hoz létre, amelyre hivatkozhat, amikor az egyes típusú sablonokat konfigurálja.</span><span class="sxs-lookup"><span data-stu-id="7097c-128">Each code establishes a common value that you can refer to when you configure each type of template.</span></span>

#### <a name="view-and-edit-directive-codes"></a><span data-ttu-id="7097c-129">Utasításkódok megtekintése és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="7097c-129">View and edit directive codes</span></span>

<span data-ttu-id="7097c-130">Az utasításkódok megtekintéséhez vagy szerkesztéséhez nyissa meg a **Raktárkezelés \> Beállítás \> Utasításkódok** elemet.</span><span class="sxs-lookup"><span data-stu-id="7097c-130">To view or edit your directive codes, go to **Warehouse management \> Setup \> Directive codes**.</span></span>

#### <a name="prepare-demo-data-directive-codes"></a><span data-ttu-id="7097c-131">A bemutatóadatok utasításkódjainak előkészítése</span><span class="sxs-lookup"><span data-stu-id="7097c-131">Prepare demo data directive codes</span></span>

<span data-ttu-id="7097c-132">Ez a példa azt mutatja be, hogyan kell előkészíteni az utasításkódot.</span><span class="sxs-lookup"><span data-stu-id="7097c-132">This example shows how to prepare a directive code.</span></span> <span data-ttu-id="7097c-133">Ha azt tervezi, hogy végighalad a téma végén található forgatókönyvön, használja az itt megadott bemutatóértékeket.</span><span class="sxs-lookup"><span data-stu-id="7097c-133">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="7097c-134">Ellenkező esetben használja a saját értékeit.</span><span class="sxs-lookup"><span data-stu-id="7097c-134">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="7097c-135">Válassza ki az **USMF** jogi személyt a bemutatóadatok kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="7097c-135">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="7097c-136">Ugrás a **Raktárkezelés \> Beállítás \> Utasítskódok** elemre.</span><span class="sxs-lookup"><span data-stu-id="7097c-136">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="7097c-137">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="7097c-138">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-138">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7097c-139">**Utasításkód:** _Zóna felt_</span><span class="sxs-lookup"><span data-stu-id="7097c-139">**Directive code:** _Zone replen_</span></span>
    - <span data-ttu-id="7097c-140">**Utasítás leírása:** _Zóna feltöltése_</span><span class="sxs-lookup"><span data-stu-id="7097c-140">**Directive description:** _Zone replenishment_</span></span>

1. <span data-ttu-id="7097c-141">Az új kód mentéséhez válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7097c-141">Select **Save** to save the new code.</span></span>

### <a name="set-up-replenishment-templates"></a><span data-ttu-id="7097c-142">Feltöltési sablonok beállítása</span><span class="sxs-lookup"><span data-stu-id="7097c-142">Set up replenishment templates</span></span>

<span data-ttu-id="7097c-143">[A min/max feltöltési sablonok](tasks/set-up-min-max-replenishment-process.md) a legfontosabbak a megfelelő szintek megtartásához a kitárolási helyeken.</span><span class="sxs-lookup"><span data-stu-id="7097c-143">[Min/max replenishment templates](tasks/set-up-min-max-replenishment-process.md) are the primary mechanism for maintaining optimal levels in picking locations.</span></span> <span data-ttu-id="7097c-144">Ezekben a sablonokban be kell állítania azokat a szabályokat, amelyek a készletnek a raktárban történő feltöltésekor használatosak.</span><span class="sxs-lookup"><span data-stu-id="7097c-144">In these templates, you must set up the rules that will be used to replenish inventory in the warehouse.</span></span> <span data-ttu-id="7097c-145">Az a feltöltés, amellyel a sablonok használhatók, zónaalapú feltöltést tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="7097c-145">The replenishment that the templates can be used for includes zone-based replenishment.</span></span>

#### <a name="view-and-edit-replenishment-templates"></a><span data-ttu-id="7097c-146">Feltöltési sablonok megtekintése és szerkesztése.</span><span class="sxs-lookup"><span data-stu-id="7097c-146">View and edit replenishment templates</span></span>

<span data-ttu-id="7097c-147">A feltöltési sablont olyan szabályok alkotják, amelyek megszabják, mikor és hogyan töltik fel a helyet.</span><span class="sxs-lookup"><span data-stu-id="7097c-147">A replenishment template is a set of rules that control when and how a location is replenished.</span></span> <span data-ttu-id="7097c-148">Kiválaszthatja azt a sablont, amely meghatározza, hogy mikor és hogyan történik a feltöltés.</span><span class="sxs-lookup"><span data-stu-id="7097c-148">You select a template to control when and how replenishment is done.</span></span> <span data-ttu-id="7097c-149">A feltöltési sablonjai megtekintéséhez és szerkesztéséhez lépjen a **Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="7097c-149">To view or edit your replenishment templates, go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>

#### <a name="prepare-a-demo-data-replenishment-template"></a><span data-ttu-id="7097c-150">Bemutatóadatokból álló feltöltési sablon előkészítése</span><span class="sxs-lookup"><span data-stu-id="7097c-150">Prepare a demo data replenishment template</span></span>

<span data-ttu-id="7097c-151">Ez a példa azt mutatja be, hogyan kell előkészíteni egy feltöltési sablont.</span><span class="sxs-lookup"><span data-stu-id="7097c-151">This example shows how to prepare a replenishment template.</span></span> <span data-ttu-id="7097c-152">Ha azt tervezi, hogy végighalad a téma végén található forgatókönyvön, használja az itt megadott bemutatóértékeket.</span><span class="sxs-lookup"><span data-stu-id="7097c-152">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="7097c-153">Ellenkező esetben használja a saját értékeit.</span><span class="sxs-lookup"><span data-stu-id="7097c-153">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="7097c-154">Válassza ki az **USMF** jogi személyt a bemutatóadatok kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="7097c-154">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="7097c-155">Ugorjon a **Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="7097c-155">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="7097c-156">Válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.</span><span class="sxs-lookup"><span data-stu-id="7097c-156">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="7097c-157">A Művelet panelen válassza az **Új** lehetőséget egy sor hozzáadásához az **Áttekintés** rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-157">On the Action Pane, select **New** to add a row to the **Overview** grid.</span></span>
1. <span data-ttu-id="7097c-158">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-158">In the new row, set the following values.</span></span> <span data-ttu-id="7097c-159">Az összes többi mezőben hagyja meg az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-159">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="7097c-160">**Feltöltésisablon:** _Zóna min/max felt_</span><span class="sxs-lookup"><span data-stu-id="7097c-160">**Replenish template:** _Zone min/max replen_</span></span>
    - <span data-ttu-id="7097c-161">**Leírás:** _Zóna min/max feltöltése_</span><span class="sxs-lookup"><span data-stu-id="7097c-161">**Description:** _Zone min/max replenishment_</span></span>
    - <span data-ttu-id="7097c-162">**Feltöltés típusa:** _Minimális vagy maximális_</span><span class="sxs-lookup"><span data-stu-id="7097c-162">**Replenishment type:** _Minimum or maximum_</span></span>

1. <span data-ttu-id="7097c-163">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-163">Select **Save**.</span></span>
1. <span data-ttu-id="7097c-164">Miközben az új sor továbbra is be van jelölve az **Áttekintés** rácsban, válassza ki az **Új** lehetőséget a **Feltöltési sablon részletei** rács felett a most létrehozott *Zóna min/max feltöltése* feltöltési sablonhoz társított sor hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="7097c-164">While the new row is still selected in the **Overview** grid, select **New** above the **Replenishment Template Details** grid to add a row that is associated with the *Zone Min/Max replen* replenishment template that you just created.</span></span>
1. <span data-ttu-id="7097c-165">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-165">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7097c-166">**Sorozatszám:** Adja meg az _1_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-166">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="7097c-167">**Leírás:** Adja meg a _Ktárolási zóna feltöltése_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-167">**Description:** Enter _Pick zone replenishment_.</span></span>
    - <span data-ttu-id="7097c-168">**Feltöltési egység:** Válassza az _ea_ elemet.</span><span class="sxs-lookup"><span data-stu-id="7097c-168">**Replenishment unit:** Select _ea_.</span></span>
    - <span data-ttu-id="7097c-169">**Kérés típusa:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="7097c-169">**Request type:** Leave this field blank.</span></span>
    - <span data-ttu-id="7097c-170">**Utasításkód** : Ez a mező hozzákapcsolja a helyutasításokat a feltöltési sablonhoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-170">**Directive code:** This field links the replenishment template with a location directive.</span></span> <span data-ttu-id="7097c-171">Válassza ki a korábban létrehozott bemutatóadat utasításkódot ( _Zóne felt_ ).</span><span class="sxs-lookup"><span data-stu-id="7097c-171">Select the demo data directive code that you created earlier ( _Zone replen_ ).</span></span>
    - <span data-ttu-id="7097c-172">**Munkasablon:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="7097c-172">**Work template:** Leave this field blank.</span></span>
    - <span data-ttu-id="7097c-173">**Minimális mennyiség:** Ez a mező azt a mennyiséget adja meg, amelynél a feltöltés aktiválódik.</span><span class="sxs-lookup"><span data-stu-id="7097c-173">**Minimum quantity:** This field sets the quantity that replenishment will be triggered at.</span></span> <span data-ttu-id="7097c-174">Adja meg az _50_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-174">Enter _50_.</span></span>
    - <span data-ttu-id="7097c-175">**Maximális mennyiség:** Ez a mező azt a maximális mennyiséget állítja be, amennyi egy adott cikkből egy zónában jelen lehet.</span><span class="sxs-lookup"><span data-stu-id="7097c-175">**Maximum quantity:** This field sets the maximum quantity of an item that can be present in a zone.</span></span> <span data-ttu-id="7097c-176">A létrejövő feltöltési munka növeli a készletet erre a mennyiségre.</span><span class="sxs-lookup"><span data-stu-id="7097c-176">Generated replenishment work will increase inventory to this quantity.</span></span> <span data-ttu-id="7097c-177">Adja meg a _150_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-177">Enter _150_.</span></span>
    - <span data-ttu-id="7097c-178">**Egység:** Ez a mező a minimális és maximális értékek egységét határozza meg.</span><span class="sxs-lookup"><span data-stu-id="7097c-178">**Unit:** This field sets the unit for the minimum and maximum values.</span></span> <span data-ttu-id="7097c-179">Válassza ki az _ea_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-179">Select _ea_.</span></span>
    - <span data-ttu-id="7097c-180">**Igény növekménye:** Válassza a _Felfelé kerekítés_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-180">**Demand increment:** Select _Round up_.</span></span>
    - <span data-ttu-id="7097c-181">**Üres rögzített helyek feltöltése:** Jelölje be ezt a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="7097c-181">**Replenish empty fixed locations:** Select this check box.</span></span>
    - <span data-ttu-id="7097c-182">**Csak a rögzített helyek feltöltése:** Jelölje be ezt a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="7097c-182">**Replenish only fixed locations:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-183">**A termék lekérdezési módja:** Válassza ki a _Termék lekérdezése_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-183">**Product query mode:** Select _Product query_.</span></span>
    - <span data-ttu-id="7097c-184">**Feltöltési küszöbérték hatóköre:** Ez a mező határozza meg, hogy a sablonnak zónánként vagy adott helyenként kell-e kiértékelnie.</span><span class="sxs-lookup"><span data-stu-id="7097c-184">**Replenishment threshold scope:** This field defines whether the template should evaluate by zone or by specific location.</span></span> <span data-ttu-id="7097c-185">Válassza a _Zóna_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-185">Select _Zone_.</span></span>
    - <span data-ttu-id="7097c-186">**Raktár:** Válassza a _61_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-186">**Warehouse:** Select _61_.</span></span>

1. <span data-ttu-id="7097c-187">Válassza a **Termékek kiválasztása** lehetőséget a **Feltöltési sablon részletei** rács fölött.</span><span class="sxs-lookup"><span data-stu-id="7097c-187">Select **Select products** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="7097c-188">A **Terméklekérdezés** párbeszédpanelen, a **Tartomány** lapon a **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-188">In the **Product query** dialog box, on the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="7097c-189">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-189">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7097c-190">**Tábla:** _Cikkek_</span><span class="sxs-lookup"><span data-stu-id="7097c-190">**Table:** _Items_</span></span>
    - <span data-ttu-id="7097c-191">**Származtatott tábla:** _Cikkek_</span><span class="sxs-lookup"><span data-stu-id="7097c-191">**Derived table:** _Items_</span></span>
    - <span data-ttu-id="7097c-192">**Mező:** _Cikkszám_</span><span class="sxs-lookup"><span data-stu-id="7097c-192">**Field:** _Item number_</span></span>
    - <span data-ttu-id="7097c-193">**Feltételek:** _A0001_</span><span class="sxs-lookup"><span data-stu-id="7097c-193">**Criteria:** _A0001_</span></span>

1. <span data-ttu-id="7097c-194">Az **OK** gombra kattintva mentse a lekérdezését, és zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="7097c-194">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="7097c-195">Válassza a **Feltöltendő zónák kiválasztása** lehetőséget a **Feltöltési sablon részletei** rács fölött.</span><span class="sxs-lookup"><span data-stu-id="7097c-195">Select **Select zones to replenish** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="7097c-196">A **Zónalekérdezés** párbeszédpanelen, a **Tartomány** lapon adjon hozzá egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-196">In the **Zone query** dialog box, on the **Range** tab, add a row to the grid.</span></span>
1. <span data-ttu-id="7097c-197">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-197">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7097c-198">**Tábla:** _Raktári zóna_</span><span class="sxs-lookup"><span data-stu-id="7097c-198">**Table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="7097c-199">**Származtatott tábla:** _Raktári zóna_</span><span class="sxs-lookup"><span data-stu-id="7097c-199">**Derived table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="7097c-200">**Mező:** _Zóna azonosítója_</span><span class="sxs-lookup"><span data-stu-id="7097c-200">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="7097c-201">**Feltételek:** _EMELET_</span><span class="sxs-lookup"><span data-stu-id="7097c-201">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="7097c-202">Az **OK** gombra kattintva mentse a lekérdezését, és zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="7097c-202">Select **OK** to save your query and close the dialog box.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="7097c-203">Helyutasítások beállítása</span><span class="sxs-lookup"><span data-stu-id="7097c-203">Set up location directives</span></span>

<span data-ttu-id="7097c-204">A helyalapú min/max feltöltéssel ellentétben a zónákon alapuló min/max feltöltéshez mind a kitárolási helyutasítást, mind az elhelyezési helyutasítást be kell állítani, mivel a rendszer csak a kimenő munka kitárolási helye helyett az egész zónát kiértékeli.</span><span class="sxs-lookup"><span data-stu-id="7097c-204">Unlike location-based min/max replenishment, zone-based min/max replenishment requires that you set up both pick location directives and put location directives, because the system evaluates the whole zone instead of just the pick location for outbound work.</span></span>

#### <a name="view-and-edit-location-directives"></a><span data-ttu-id="7097c-205">Helyutasítások megtekintése és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="7097c-205">View and edit location directives</span></span>

<span data-ttu-id="7097c-206">A helyutasítások megtekintéséhez vagy szerkesztéséhez nyissa meg a **Raktárkezelés \> Beállítás \> Helyutasítások** elemet.</span><span class="sxs-lookup"><span data-stu-id="7097c-206">To view or edit your location directives, go to **Warehouse management \> Setup \> Location directives**.</span></span>

<span data-ttu-id="7097c-207">A szükséges kitárolási helyutasítások és elhelyezési helyutasítások létrehozására vonatkozó beállítások használatával kapcsolatban tekintse meg a következő szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7097c-207">For examples that show how to use the settings to create the required pick location directives and put location directives, see the next section.</span></span>

#### <a name="prepare-demo-data-location-directives"></a><span data-ttu-id="7097c-208">A bemutatóadatok helyutasításainak előkészítése</span><span class="sxs-lookup"><span data-stu-id="7097c-208">Prepare demo data location directives</span></span>

<span data-ttu-id="7097c-209">A bemutatóadatok előkészítéséhez, hogy a témakör végén felhasználhatók legyenek a forgatókönyvben, két helyutasítást kell létrehoznia, amelyek egyike a kitárolásra, a másik pedig az elhelyezésre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="7097c-209">To prepare demo data so that it can be used in the scenario at the end of this topic, you must create two location directives: one for pick and one for put.</span></span>

##### <a name="create-a-replenishment-pick-directive"></a><span data-ttu-id="7097c-210">Feltöltési kitárolási utasítás létrehozása</span><span class="sxs-lookup"><span data-stu-id="7097c-210">Create a replenishment pick directive</span></span>

1. <span data-ttu-id="7097c-211">Válassza ki az **USMF** jogi személyt a bemutatóadatok kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="7097c-211">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="7097c-212">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="7097c-212">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="7097c-213">A bal oldali ablaktáblában állítsa a **Munkarendelés típusa** mezőt a _Feltöltés_ értékre.</span><span class="sxs-lookup"><span data-stu-id="7097c-213">In the left pane, set the **Work order type** field to _Replenishment_.</span></span>
1. <span data-ttu-id="7097c-214">Jelölje be a műveleti ablakban az **Új** lehetőséget az új utasítás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7097c-214">On the Action Pane, select **New** to create a new directive.</span></span>
1. <span data-ttu-id="7097c-215">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-215">Set the following values:</span></span>

    - <span data-ttu-id="7097c-216">**Sorszám:** Fogadja el az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-216">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="7097c-217">**Név:** Adja meg a _Zóna kitárolás_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-217">**Name:** Enter _Zone pick_.</span></span>
    - <span data-ttu-id="7097c-218">**Munka típusa:** Válassza a _Kitárolás_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-218">**Work type:** Select _Pick_.</span></span>
    - <span data-ttu-id="7097c-219">**Hely:** Válassza a _6_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-219">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="7097c-220">**Raktár:** Válassza a _61_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-220">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="7097c-221">**Utasításkód:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="7097c-221">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="7097c-222">**Több raktározási egység:** Állítsa a beállítást _Nem_ értékre.</span><span class="sxs-lookup"><span data-stu-id="7097c-222">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="7097c-223">A **Mentés** gombra kattintva hozzon létre egy olyan irányelvet, amely az eddig beállított beállításokat tartalmazta.</span><span class="sxs-lookup"><span data-stu-id="7097c-223">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="7097c-224">A **Sorok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-224">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="7097c-225">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-225">On the new line, set the following values:</span></span>

    - <span data-ttu-id="7097c-226">**Sorozatszám:** Adja meg az _1_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-226">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="7097c-227">**Kezdő mennyiség:** Adja meg a _0_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-227">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="7097c-228">**Cél mennyiség:** Adja meg a _10000000_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-228">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="7097c-229">**Egység:** Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="7097c-229">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="7097c-230">**Mennyiség megkeresése:** Válassza a _Nincs_ beállítást.</span><span class="sxs-lookup"><span data-stu-id="7097c-230">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="7097c-231">**Korlátozás egység szerint:** Törölje a jelölőnégyzet kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="7097c-231">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-232">**Felkerekítés az egységhez:** Törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="7097c-232">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-233">**Csomagolási mennyiség keresése:** Törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="7097c-233">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-234">**Felosztás engedélyezése:** Válassza ki ezt a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="7097c-234">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="7097c-235">Az új sor mentéséhez válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7097c-235">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="7097c-236">Ha az új sor továbbra is a **Sorok** rácsban van kiválasztva, akkor a **Helyutasítás műveletei** gyorslap **Új** elemét választva adhat hozzá egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-236">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="7097c-237">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-237">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7097c-238">**Sorozatszám:** Adja meg az _1_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-238">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="7097c-239">**Név:** Adja meg az _Ömlesztett kitárolás_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-239">**Name:** Enter _Pick from bulk_.</span></span>
    - <span data-ttu-id="7097c-240">**Helyhez kötött használat:** Válassza a _Rögzített és nem rögzített helyek_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-240">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="7097c-241">**Negatív készlet engedélyezése:** Törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="7097c-241">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-242">**Köteg engedélyezve:** Törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="7097c-242">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-243">**Stratégia:** Válassza a _Nincs_ beállítást.</span><span class="sxs-lookup"><span data-stu-id="7097c-243">**Strategy:** Select _None_.</span></span>

1. <span data-ttu-id="7097c-244">Az új művelet mentéséhez válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7097c-244">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="7097c-245">Miközben az új művelet továbbra is be van jelölve, jelölje be a **Lekérdezés szerkesztése** elemet a **Helyutasítás műveletei** rács felett.</span><span class="sxs-lookup"><span data-stu-id="7097c-245">While your new action still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="7097c-246">Megjelenik egy lekérdezési párbeszédpanel, amelyen megadhatja, hogy milyen helyekről kell elvégeznie a feltöltést.</span><span class="sxs-lookup"><span data-stu-id="7097c-246">A query dialog box appears, where you can select the locations to replenish from.</span></span> <span data-ttu-id="7097c-247">A **tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-247">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="7097c-248">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-248">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7097c-249">**Tábla:** _Helyek_</span><span class="sxs-lookup"><span data-stu-id="7097c-249">**Table:** _Locations_</span></span>
    - <span data-ttu-id="7097c-250">**Származtatott tábla:** _Helyek_</span><span class="sxs-lookup"><span data-stu-id="7097c-250">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="7097c-251">**Mező:** _Zóna azonosítója_</span><span class="sxs-lookup"><span data-stu-id="7097c-251">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="7097c-252">**Feltételek:** _BULK_</span><span class="sxs-lookup"><span data-stu-id="7097c-252">**Criteria:** _BULK_</span></span>

1. <span data-ttu-id="7097c-253">Az **OK** gombra kattintva mentse a lekérdezését, és zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="7097c-253">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="7097c-254">A helyutasítás mentéséhez válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="7097c-254">Select **Save** to save your location directive.</span></span>

##### <a name="create-a-replenishment-put-directive"></a><span data-ttu-id="7097c-255">Feltöltési elhelyezési utasítás létrehozása</span><span class="sxs-lookup"><span data-stu-id="7097c-255">Create a replenishment put directive</span></span>

1. <span data-ttu-id="7097c-256">A **Helyutasítások** lap bal oldali panelén győződjön meg róla, hogy a **Munkarendelés típusa** mező továbbra is a _Feltöltés_ értékre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="7097c-256">On the **Location directives** page, in the left pane, make sure that the **Work order type** field is still set to _Replenishment_.</span></span>
1. <span data-ttu-id="7097c-257">Jelölje be a műveleti ablakban az **Új** lehetőséget az új utasítás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7097c-257">On the Action Pane, select **New** to create another new directive.</span></span>
1. <span data-ttu-id="7097c-258">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-258">Set the following values:</span></span>

    - <span data-ttu-id="7097c-259">**Sorszám:** Fogadja el az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-259">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="7097c-260">**Név:** Adja meg a _Zóna elhelyezés_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-260">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="7097c-261">**Munkarendelés típusa:** Válassza az _Elhelyezés_ elemet.</span><span class="sxs-lookup"><span data-stu-id="7097c-261">**Work order type:** Select _Put_.</span></span>
    - <span data-ttu-id="7097c-262">**Hely:** Válassza a _6_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-262">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="7097c-263">**Raktár:** Válassza a _61_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-263">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="7097c-264">**Utasításkód:** Válassza ki a _Zóna felt_ lehetőséget, hogy ezt a helyutasítást a korábban létrehozott kód alapján a korábban létrehozott feltöltési sablonnal kapcsolja.</span><span class="sxs-lookup"><span data-stu-id="7097c-264">**Directive code:** Select _Zone replen_ to link this location directive with the replenishment template that you created earlier by using the code that you created earlier.</span></span>
    - <span data-ttu-id="7097c-265">**Több raktározási egység:** Állítsa a beállítást _Nem_ értékre.</span><span class="sxs-lookup"><span data-stu-id="7097c-265">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="7097c-266">A **Mentés** gombra kattintva hozzon létre egy olyan irányelvet, amely az eddig beállított beállításokat tartalmazta.</span><span class="sxs-lookup"><span data-stu-id="7097c-266">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="7097c-267">A **Sorok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-267">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="7097c-268">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-268">On the new line, set the following values:</span></span>

    - <span data-ttu-id="7097c-269">**Sorozatszám:** Adja meg az _1_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-269">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="7097c-270">**Kezdő mennyiség:** Adja meg a _0_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-270">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="7097c-271">**Cél mennyiség:** Adja meg a _10000000_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-271">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="7097c-272">**Egység:** Ezt a mezőt hagyja üresen.</span><span class="sxs-lookup"><span data-stu-id="7097c-272">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="7097c-273">**Mennyiség megkeresése:** Válassza a _Nincs_ beállítást.</span><span class="sxs-lookup"><span data-stu-id="7097c-273">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="7097c-274">**Korlátozás egység szerint:** Törölje a jelölőnégyzet kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="7097c-274">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-275">**Felkerekítés az egységhez:** Törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="7097c-275">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-276">**Csomagolási mennyiség keresése:** Törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="7097c-276">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-277">**Felosztás engedélyezése:** Válassza ki ezt a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="7097c-277">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="7097c-278">Az új sor mentéséhez válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7097c-278">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="7097c-279">Ha az új sor továbbra is a **Sorok** rácsban van kiválasztva, akkor a **Helyutasítás műveletei** gyorslap **Új** elemét választva adhat hozzá egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-279">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="7097c-280">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-280">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7097c-281">**Sorozatszám:** Adja meg az _1_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-281">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="7097c-282">**Név:** Adja meg a _Zóna elhelyezés_ értéket.</span><span class="sxs-lookup"><span data-stu-id="7097c-282">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="7097c-283">**Helyhez kötött használat:** Válassza a _Rögzített és nem rögzített helyek_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-283">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="7097c-284">**Negatív készlet engedélyezése:** Törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="7097c-284">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-285">**Köteg engedélyezve:** Törölje a jelet a jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="7097c-285">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="7097c-286">**Stratégia:** Válassza a _Konszolidáció_ elemet.</span><span class="sxs-lookup"><span data-stu-id="7097c-286">**Strategy:** Select _Consolidate_.</span></span>

1. <span data-ttu-id="7097c-287">Az új művelet mentéséhez válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7097c-287">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="7097c-288">Miközben az új művelet továbbra is be van jelölve, jelölje be a **Lekérdezés szerkesztése** elemet a **Helyutasítás műveletei** rács felett.</span><span class="sxs-lookup"><span data-stu-id="7097c-288">While your new action is still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="7097c-289">Megjelenik egy lekérdezési párbeszédpanel, amelyen megadhatja, hogy milyen zónákat kell feltölteni.</span><span class="sxs-lookup"><span data-stu-id="7097c-289">A query dialog box appears, where you can select the zone to replenish to.</span></span> <span data-ttu-id="7097c-290">Ennek a zónának meg kell egyeznie a feltöltési sablonban megadott zónával.</span><span class="sxs-lookup"><span data-stu-id="7097c-290">This zone should be the same zone that is specified in the replenishment template.</span></span> <span data-ttu-id="7097c-291">A **tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7097c-291">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="7097c-292">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7097c-292">In the new row, set the following values:</span></span>

    - <span data-ttu-id="7097c-293">**Tábla:** _Helyek_</span><span class="sxs-lookup"><span data-stu-id="7097c-293">**Table:** _Locations_</span></span>
    - <span data-ttu-id="7097c-294">**Származtatott tábla:** _Helyek_</span><span class="sxs-lookup"><span data-stu-id="7097c-294">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="7097c-295">**Mező:** _Zóna azonosítója_</span><span class="sxs-lookup"><span data-stu-id="7097c-295">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="7097c-296">**Feltételek:** _EMELET_</span><span class="sxs-lookup"><span data-stu-id="7097c-296">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="7097c-297">Az **OK** gombra kattintva mentse a lekérdezését, és zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="7097c-297">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="7097c-298">A helyutasítás mentéséhez válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="7097c-298">Select **Save** to save your location directive.</span></span>

## <a name="scenario"></a><span data-ttu-id="7097c-299">Forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="7097c-299">Scenario</span></span>

<span data-ttu-id="7097c-300">Ez a szakasz egy példaesetet tartalmaz, amely bemutatja a funkció kezelését.</span><span class="sxs-lookup"><span data-stu-id="7097c-300">This section provides a sample scenario that shows how to work with the feature.</span></span>

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a><span data-ttu-id="7097c-301">Készítse elő a mintaesethez szükséges mintaadatokat</span><span class="sxs-lookup"><span data-stu-id="7097c-301">Prepare the sample data that is required for the sample scenario</span></span>

<span data-ttu-id="7097c-302">Mielőtt elkezdené a munkafolyamatot, aktiválni kell a mintaadatokat, és be kell állítania a szolgáltatást az ebben a szakaszban és a témakör korábbi szakaszaiban ismertetett módon.</span><span class="sxs-lookup"><span data-stu-id="7097c-302">Before you start to work through the scenario, you must activate sample data and set up the feature as described in this section and in the previous sections of this topic.</span></span>

#### <a name="use-the-usmf-legal-entity"></a><span data-ttu-id="7097c-303">Az USMF jogi személy használata</span><span class="sxs-lookup"><span data-stu-id="7097c-303">Use the USMF legal entity</span></span>

<span data-ttu-id="7097c-304">Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="7097c-304">To work through the scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="7097c-305">Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="7097c-305">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="prepare-additional-sample-data"></a><span data-ttu-id="7097c-306">További mintaadatok előkészítése</span><span class="sxs-lookup"><span data-stu-id="7097c-306">Prepare additional sample data</span></span>

<span data-ttu-id="7097c-307">Miután kiválasztotta az **USMF** jogi személyt, vegye fel a szükséges további mintaadattípusokat a témakör korábbi, [Zónaalapú feltöltés beállítása](#setup) című részében írtak szerint.</span><span class="sxs-lookup"><span data-stu-id="7097c-307">After you've selected the **USMF** legal entity, add the additional sample data that is required, as described in the [Set up zone-based replenishment](#setup) section earlier in this topic.</span></span>

#### <a name="check-your-on-hand-inventory"></a><span data-ttu-id="7097c-308">Ellenőrizze az aktuális készletet</span><span class="sxs-lookup"><span data-stu-id="7097c-308">Check your on-hand inventory</span></span>

<span data-ttu-id="7097c-309">Kövesse az alábbi lépéseket, és győződjön meg arról, hogy a rendszer elegendő készletet tartalmaz a mintaeset támogatására.</span><span class="sxs-lookup"><span data-stu-id="7097c-309">Follow these steps to make sure that your system includes enough inventory to support the sample scenario.</span></span>

1. <span data-ttu-id="7097c-310">Győződjön meg róla, hogy az *A0001* cikk esetében feltöltési sablonban megadott kitárolási zóna ( *EMELET* ) két különböző helyén is van aktuális készlet.</span><span class="sxs-lookup"><span data-stu-id="7097c-310">Make sure that there is on-hand inventory for item *A0001* at two different locations in the pick zone ( *FLOOR* ) that is specified in the replenishment template.</span></span> <span data-ttu-id="7097c-311">A teljes készletnek azonban kisebbnek kell lennie, mint a feltöltési sablonban megadott kötelező minimális mennyiség ( *50* ).</span><span class="sxs-lookup"><span data-stu-id="7097c-311">However, the total inventory should be less than the required minimum quantity ( *50* ) that is specified on the replenishment template.</span></span> <span data-ttu-id="7097c-312">Ily módon szimulálhatja, hogy hogyan történik a számítás az egész zónában, nem csak egy helyen.</span><span class="sxs-lookup"><span data-stu-id="7097c-312">In this way, you can simulate how the calculation occurs for the whole zone instead of just for a single location.</span></span> <span data-ttu-id="7097c-313">**A raktári folyamatokkal a szükséges módon módosíthatja a készletet.**</span><span class="sxs-lookup"><span data-stu-id="7097c-313">**Use any of the warehouse processes to adjust inventory as required.**</span></span>
1. <span data-ttu-id="7097c-314">Győződjön meg róla, hogy elegendő készlet van az *A0001* cikkből az ömlesztett tárolóhelyen, amely a zóna kitárolási helyutasításában meg van adva, ahonnan a feltöltési munkának ki kell tárolnia a cikkeket az *ÖMLESZTETT* zónaazonosítóból.</span><span class="sxs-lookup"><span data-stu-id="7097c-314">Make sure that there is enough inventory for item *A0001* at a bulk location that is specified in the zone pick location directive where the replenishment work should pick the items from zone ID *BULK*.</span></span> <span data-ttu-id="7097c-315">A teljes készletnek azonban többnek kell lennie, mint a feltöltési sablonban megadott kötelező maximális mennyiség ( *150* ).</span><span class="sxs-lookup"><span data-stu-id="7097c-315">The total inventory must be more than the required maximum quantity ( *150* ) that is specified in the replenishment template.</span></span>
1. <span data-ttu-id="7097c-316">Nem kötelező, de javasolt: Hajtsa végre a következő lépéseket egy készlethelyesbítési napló létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="7097c-316">Optional but recommended: Follow these steps to create an inventory adjustment journal:</span></span>

    1. <span data-ttu-id="7097c-317">Lépjen a **Készletgazdálkodás \> Naplóbejegyzések \> Cikkek \> Készlethelyesbítés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7097c-317">Go to **Inventory management \> Journal entries \> Items \> Inventory adjustment**.</span></span>
    1. <span data-ttu-id="7097c-318">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-318">Select **New**.</span></span>
    1. <span data-ttu-id="7097c-319">Válassza a **Készletnapló létrehozása** párbeszédpanel **Raktár** mezőjének *61* pontját.</span><span class="sxs-lookup"><span data-stu-id="7097c-319">In the **Create inventory journal** dialog box, in the **Warehouse** field, select *61*.</span></span>
    1. <span data-ttu-id="7097c-320">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-320">Select **OK**.</span></span>
    1. <span data-ttu-id="7097c-321">A **Naplósorok** gyorslapon az **Új** gombra kattintva adja hozzá a rácshoz a három sort, és adja meg a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="7097c-321">On the **Journal lines** FastTab, use the **New** button to add three lines to the grid, and set the following values.</span></span> <span data-ttu-id="7097c-322">Miután befejezte az egyes sorok beállítását, válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="7097c-322">After you've finished setting up each line, select **Save**.</span></span>

        - <span data-ttu-id="7097c-323">**1. sor:**</span><span class="sxs-lookup"><span data-stu-id="7097c-323">**Line 1:**</span></span>

            - <span data-ttu-id="7097c-324">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="7097c-324">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="7097c-325">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="7097c-325">**Site:** *6*</span></span>
            - <span data-ttu-id="7097c-326">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="7097c-326">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="7097c-327">**Hely:** *02A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="7097c-327">**Location:** *02A01R1S1B*</span></span>
            - <span data-ttu-id="7097c-328">**Azonosítótábla:** Válasszon ki egy meglévő azonosítótáblát a listából, vagy hozzon létre egy új azonosítótáblát.</span><span class="sxs-lookup"><span data-stu-id="7097c-328">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="7097c-329">**Mennyiség:** *1000*</span><span class="sxs-lookup"><span data-stu-id="7097c-329">**Quantity:** *1000*</span></span>

        - <span data-ttu-id="7097c-330">**2. sor:**</span><span class="sxs-lookup"><span data-stu-id="7097c-330">**Line 2:**</span></span>

            - <span data-ttu-id="7097c-331">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="7097c-331">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="7097c-332">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="7097c-332">**Site:** *6*</span></span>
            - <span data-ttu-id="7097c-333">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="7097c-333">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="7097c-334">**Hely:** *07A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="7097c-334">**Location:** *07A01R2S1B*</span></span>
            - <span data-ttu-id="7097c-335">**Azonosítótábla:** Válasszon ki egy meglévő azonosítótáblát a listából, vagy hozzon létre egy új azonosítótáblát.</span><span class="sxs-lookup"><span data-stu-id="7097c-335">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="7097c-336">**Mennyiség:** *15*</span><span class="sxs-lookup"><span data-stu-id="7097c-336">**Quantity:** *15*</span></span>

        - <span data-ttu-id="7097c-337">**3. sor:**</span><span class="sxs-lookup"><span data-stu-id="7097c-337">**Line 3:**</span></span>

            - <span data-ttu-id="7097c-338">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="7097c-338">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="7097c-339">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="7097c-339">**Site:** *6*</span></span>
            - <span data-ttu-id="7097c-340">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="7097c-340">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="7097c-341">**Hely:** *07A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="7097c-341">**Location:** *07A01R1S1B*</span></span>
            - <span data-ttu-id="7097c-342">**Azonosítótábla:** Válasszon ki egy meglévő azonosítótáblát a listából, vagy hozzon létre egy új azonosítótáblát.</span><span class="sxs-lookup"><span data-stu-id="7097c-342">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="7097c-343">**Mennyiség:** *10*</span><span class="sxs-lookup"><span data-stu-id="7097c-343">**Quantity:** *10*</span></span>

    1. <span data-ttu-id="7097c-344">A Művelet panelen válassza ki az **Érvényesítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-344">On the Action Pane, select **Validate**.</span></span> <span data-ttu-id="7097c-345">A következő lépéshez történő továbblépés előtt javítson minden talált hibát.</span><span class="sxs-lookup"><span data-stu-id="7097c-345">Address any errors that are found before you move on to the next step.</span></span>
    1. <span data-ttu-id="7097c-346">A Művelet panelen válassza a **Feladás** parancsot a készletnek a raktárba történő feladásához.</span><span class="sxs-lookup"><span data-stu-id="7097c-346">On the Action Pane, select **Post** to post the inventory to the warehouse.</span></span>

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a><span data-ttu-id="7097c-347">Mintaeset: Zónaalapú min/max feltöltés futtatása</span><span class="sxs-lookup"><span data-stu-id="7097c-347">Sample scenario: Run zone-based min/max replenishment</span></span>

<span data-ttu-id="7097c-348">Miután minden előfeltétel mintaadat a helyén van, a feltöltést a következő lépések végrehajtásával aktiválhatja.</span><span class="sxs-lookup"><span data-stu-id="7097c-348">After all the prerequisite sample data is in place, you can trigger replenishment by following these steps.</span></span>

1. <span data-ttu-id="7097c-349">Ugorjon a **Raktárkezelés \> Feltöltés \> Feltöltések** pontra.</span><span class="sxs-lookup"><span data-stu-id="7097c-349">Go to **Warehouse management \> Replenishment \> Replenishments**.</span></span>
1. <span data-ttu-id="7097c-350">A **Feltöltés** párbeszédpanelen, a **Szerepeltetni kívánt rekordok** gyorslapján válassza a **Szűrő** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7097c-350">In the **Replenishment** dialog box, on the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="7097c-351">A **Lekérdezés** párbeszédpanelben, a **Tartomány** lapon a következő módon szerkessze a táblázat alapértelmezett sorát:</span><span class="sxs-lookup"><span data-stu-id="7097c-351">In the **Inquiry** dialog box, on the **Range** tab, edit the default table row in the following way:</span></span>

    - <span data-ttu-id="7097c-352">**Tábla:** Válassza a _Feltöltési sablonok_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-352">**Table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="7097c-353">**Származtatott tábla:** Válassza a _Feltöltési sablonok_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-353">**Derived table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="7097c-354">**Mező:** Válassza a _Feltöltési sablon_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-354">**Field:** Select _Replenishment template_.</span></span>
    - <span data-ttu-id="7097c-355">**Feltételek:** Válassza ki a _Zóna min/max felt_ lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7097c-355">**Criteria:** Select _Zone min/max replen_.</span></span> <span data-ttu-id="7097c-356">Ez a feltöltési sablon az a feltöltési sablon, amelyet ehhez az esethez tartozó bemutatóadatok előkészítése során hozott létre.</span><span class="sxs-lookup"><span data-stu-id="7097c-356">This replenishment template is the replenishment template that you created while you were preparing the demo data for this scenario.</span></span>

1. <span data-ttu-id="7097c-357">Az **OK** gombra kattintva mentse a lekérdezést, és lépjen vissza a **Feltöltés** párbeszédpanelre.</span><span class="sxs-lookup"><span data-stu-id="7097c-357">Select **OK** to save the query and go back to the **Replenishment** dialog box.</span></span>
1. <span data-ttu-id="7097c-358">A feltöltési sablon futtatásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="7097c-358">Select **OK** to run the replenishment template.</span></span>

<span data-ttu-id="7097c-359">A feltöltési munka most létrejön, hogy kitárolja a készletet az *ÖMLESZTETT* zónából, és feltölti az *EMELET* zónába.</span><span class="sxs-lookup"><span data-stu-id="7097c-359">Replenishment work is now created to pick inventory from the *BULK* zone and replenish it to the *FLOOR* zone.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="7097c-360">Megjegyzések és tippek</span><span class="sxs-lookup"><span data-stu-id="7097c-360">Notes and tips</span></span>

<span data-ttu-id="7097c-361">Itt van néhány megjegyzés és tipp a funkció használatához:</span><span class="sxs-lookup"><span data-stu-id="7097c-361">Here are a few notes and tips for working with the feature:</span></span>

- <span data-ttu-id="7097c-362">A kívánt zónához vezető feltöltési munka beállításához a feltöltési sablon sorait és a helyutasításokat a következő módokon lehet összekapcsolni:</span><span class="sxs-lookup"><span data-stu-id="7097c-362">To set up replenishment work that goes to the desired zone, you can link the replenishment template lines and location directives in either of the following ways:</span></span>

    - <span data-ttu-id="7097c-363">Módosítsa a helyutasítás fejlécének lekérdezését, és szűrje a kiválasztott feltöltési sablon sorait.</span><span class="sxs-lookup"><span data-stu-id="7097c-363">Edit the location directive header query, and filter the selected replenishment template lines.</span></span>
    - <span data-ttu-id="7097c-364">Használjon egy utasításkódot a feltöltési sablon sorához, és egyeztesse az elhelyezési helyutasítással.</span><span class="sxs-lookup"><span data-stu-id="7097c-364">Use a directive code on the replenishment template line, and match it to the put location directive.</span></span>

- <span data-ttu-id="7097c-365">Ha dinamikus helyeket használ, akkor a feltöltési munka jön létre vagy az első elérhető helyen vagy egy olyan helyen, amely már tartalmaz készletet, ha a helyutasítás művelet be van állítva a **Konszolidáció** stratégia használatára.</span><span class="sxs-lookup"><span data-stu-id="7097c-365">If you're using dynamic locations, replenishment work will be created either for the first available location or for a location that already contains inventory, if the location directive action is set up to use the **Consolidate** strategy.</span></span>
- <span data-ttu-id="7097c-366">Ha a zónák helyett fix helyeket használ, akkor a [szabvány min/max feltöltést](tasks/set-up-min-max-replenishment-process.md) kell használni.</span><span class="sxs-lookup"><span data-stu-id="7097c-366">If you're using fixed locations instead of zones, you should use [standard min/max replenishment](tasks/set-up-min-max-replenishment-process.md).</span></span>
