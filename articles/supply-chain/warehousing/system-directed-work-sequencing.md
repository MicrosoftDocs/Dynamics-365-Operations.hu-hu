---
title: Rendszer által irányított munka sorrendbe állítása
description: Ez a témakör a rendszer által irányított munka sorrendbe állítással kapcsolatban tartalmaz tájékoztatást. Ez a funkció lehetővé teszi a rendszer által a felhasználóknak a végrehajtásra bemutatott munkarendelések rendezését és szűrését. Ez olyan esetekben hasznos, amikor további feltételek szükségesek a raktári kitárolási folyamat vezetéséhez.
author: Mirzaab
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 5387aaf5a5e0d20ac22595fbea86a25fdf38a771
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831122"
---
# <a name="system-directed-work-sequencing"></a><span data-ttu-id="6484e-105">Rendszer által irányított munka sorrendbe állítása</span><span class="sxs-lookup"><span data-stu-id="6484e-105">System-directed work sequencing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6484e-106">A rendszer által irányított munka sorrendbe állítás lehetővé teszi a rendszer által a felhasználóknak a végrehajtásra bemutatott munkarendelések rendezését és szűrését.</span><span class="sxs-lookup"><span data-stu-id="6484e-106">System-directed work sequencing lets you sort and filter the work orders that the system presents to users for execution.</span></span> <span data-ttu-id="6484e-107">Ez olyan esetekben hasznos, amikor további feltételek szükségesek (például a szállítás időpontja, a kitárolási zóna, a hely profilja, illetve a különböző feltételek kombinációja) a raktár kitárolási folyamatának vezetéséhez.</span><span class="sxs-lookup"><span data-stu-id="6484e-107">It's helpful in scenarios where additional criteria (such as the time of shipping, the picking zone, the location profile, or a combination of various criteria) are required to drive the warehouse picking process.</span></span>

<span data-ttu-id="6484e-108">Ez a funkció kiterjeszti a rendszer által irányított kitárolási funkciót egy rendszer által irányított lekérdezési rendelés hozzáadásával, ahol a felhasználók megadhatnak egy sorrendet és egy vagy több lekérdezést, amely minden létrehozott munkarendelést értékelni fog.</span><span class="sxs-lookup"><span data-stu-id="6484e-108">This functionality extends the current system-directed picking functionality by adding a system-directed query order, where users can set up a sequence and one or more queries that will evaluate all work orders that are created.</span></span> <span data-ttu-id="6484e-109">Csak olyan munkarendelések kerülnek rögzítésre és megjelenítésre, amelyek megfelelnek a mobileszköz menüelemének beállításában meghatározott feltételeknek.</span><span class="sxs-lookup"><span data-stu-id="6484e-109">Only work orders that meet the criteria that are specified in the setup of the mobile device menu item will be captured and presented.</span></span>

<span data-ttu-id="6484e-110">Ez a funkció lehetővé teszi a raktári kitárolási folyamatok további optimalizálását, mivel meghatározza a megadott feltételeknek megfelelő munkarendeléseket, hozzárendeli őket a megfelelő mobileszköz-menüelemhez, majd bemutatja őket egy dolgozónak egy meghatározott szakértelmi készlet, kitárolási eszköz vagy egyéb követelmény alapján.</span><span class="sxs-lookup"><span data-stu-id="6484e-110">Therefore, this functionality allows for further optimization of warehouse picking processes as it identifies work orders that match the specified criteria, assigns them to the correct mobile device menu item, and then presents them to a worker, based on a specific skill set, picking equipment, or other requirement.</span></span>

> [!NOTE]
> <span data-ttu-id="6484e-111">Ha különböző feltételek szükségesek, akkor több mobileszköz-menüelemet kell használni.</span><span class="sxs-lookup"><span data-stu-id="6484e-111">If different criteria are needed, multiple mobile device menu items must be used.</span></span>

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a><span data-ttu-id="6484e-112">Kapcsolja be a Szervezeti szintű rendszer által irányított munka sorrendbe állítása funkciót</span><span class="sxs-lookup"><span data-stu-id="6484e-112">Turn on the Organization-wide system directed work sequencing feature</span></span>

<span data-ttu-id="6484e-113">A rendszer által irányított munka sorrendbe állításának használata előtt be kell kapcsolni azt a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="6484e-113">Before you can use system-directed work sequencing, the feature must be turned on in your system.</span></span> <span data-ttu-id="6484e-114">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="6484e-114">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6484e-115">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="6484e-115">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6484e-116">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="6484e-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6484e-117">**Szolgáltatás neve:** *Szervezeti szintű rendszer által irányított munka sorrendbe állítása*</span><span class="sxs-lookup"><span data-stu-id="6484e-117">**Feature name:** *Organization-wide system directed work sequencing*</span></span>

## <a name="setup"></a><span data-ttu-id="6484e-118">Beállítás</span><span class="sxs-lookup"><span data-stu-id="6484e-118">Setup</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="6484e-119">A bemutató adatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="6484e-119">Make demo data available</span></span>

<span data-ttu-id="6484e-120">Ha ezt a forgatókönyvet az ebben a témakörben megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszeren kell dolgoznia, amelynél a szokásos demóadatok telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="6484e-120">To work through the scenario by using the values that are presented in this topic, you must work on a system where the standard demo data is installed.</span></span> <span data-ttu-id="6484e-121">Ezenkívül ki kell választania az **USMF** jogi személyt.</span><span class="sxs-lookup"><span data-stu-id="6484e-121">Additionally, you must select the **USMF** legal entity.</span></span> <span data-ttu-id="6484e-122">A forgatókönyv az *51*-es raktárt használja a demóadatokból.</span><span class="sxs-lookup"><span data-stu-id="6484e-122">The scenario uses warehouse *51* from the demo data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6484e-123">Mielőtt kiadja a rendeléseket a raktárba, győződjön meg arról, hogy a kitárolási helyek elegendő készlettel rendelkeznek a rendelések minden cikkéhez.</span><span class="sxs-lookup"><span data-stu-id="6484e-123">Before you release the orders to the warehouse, make sure that the pick locations have enough inventory for all the items on the orders.</span></span>
>
> <span data-ttu-id="6484e-124">Az alapértelmezett USMF-adatoknak támogatniuk kell ezt a forgatókönyvet.</span><span class="sxs-lookup"><span data-stu-id="6484e-124">Default USMF data should support this scenario.</span></span> <span data-ttu-id="6484e-125">Ha nem demóadatokat használ, a **Helyutasítás** beállítás áttekintésével ismerje meg, hogy melyik kitárolási helyeket használja a rendszer az értékesítési rendelések kitároláshoz.</span><span class="sxs-lookup"><span data-stu-id="6484e-125">If you aren't using demo data, review the **Location directive** setting to learn which picking locations are used for sales order picking.</span></span> <span data-ttu-id="6484e-126">Ha módosítania kell a készletet, akkor manuális mozgásokat hozhat létre, felhasználhatja a feltöltést, vagy bármilyen egyéb folyamatot alkalmazhat.</span><span class="sxs-lookup"><span data-stu-id="6484e-126">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span>

### <a name="set-up-a-mobile-device-menu-item"></a><span data-ttu-id="6484e-127">Mobileszköz-menüelem beállítása</span><span class="sxs-lookup"><span data-stu-id="6484e-127">Set up a mobile device menu item</span></span>

1. <span data-ttu-id="6484e-128">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="6484e-128">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6484e-129">A mobileszköz-menüelemek listáján válassza az **Értékesítési kitárolás – rendszer** elemet.</span><span class="sxs-lookup"><span data-stu-id="6484e-129">In the list of mobile device menu items, select **Sales Picking – System**.</span></span> <span data-ttu-id="6484e-130">A szükséges menüelemnek már léteznie kell.</span><span class="sxs-lookup"><span data-stu-id="6484e-130">The required menu item should already exist.</span></span> 
1. <span data-ttu-id="6484e-131">Erősítse meg a következő beállításokat:</span><span class="sxs-lookup"><span data-stu-id="6484e-131">Confirm the following settings:</span></span>

    - <span data-ttu-id="6484e-132">Az **Általános** gyorslapon az **Irányító** mezőt *Rendszer által irányított* értékre kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="6484e-132">On the **General** FastTab, the **Directed by** field should be set to *System directed*.</span></span>
    - <span data-ttu-id="6484e-133">A **Munkaosztályok** gyorslap a következő beállításokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="6484e-133">The **Work classes** FastTab should show the following settings.</span></span>

        | <span data-ttu-id="6484e-134">Munkaosztály azonosítója</span><span class="sxs-lookup"><span data-stu-id="6484e-134">Work class ID</span></span> | <span data-ttu-id="6484e-135">Munkarendelés típusa</span><span class="sxs-lookup"><span data-stu-id="6484e-135">Work order type</span></span> |
        |---|---|
        | <span data-ttu-id="6484e-136">Értékesítés</span><span class="sxs-lookup"><span data-stu-id="6484e-136">Sales</span></span> | <span data-ttu-id="6484e-137">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="6484e-137">Sales orders</span></span> |
        | <span data-ttu-id="6484e-138">SO kitárolás</span><span class="sxs-lookup"><span data-stu-id="6484e-138">SO Pick</span></span> | <span data-ttu-id="6484e-139">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="6484e-139">Sales orders</span></span> |

1. <span data-ttu-id="6484e-140">A Művelet panelen válassza ki a **Rendszer által irányított munka sorrendbe állítás lekérdezései** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6484e-140">On the Action Pane, select **System directed work sequence queries**.</span></span>
1. <span data-ttu-id="6484e-141">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="6484e-141">Select **Edit**.</span></span>
1. <span data-ttu-id="6484e-142">Törölje a meglévő sort, majd az **Igen** gombra kattintva hagyja jóvá a műveletet.</span><span class="sxs-lookup"><span data-stu-id="6484e-142">Delete the existing line, and then confirm the action by selecting **Yes**.</span></span>
1. <span data-ttu-id="6484e-143">Jelölje be a műveleti ablakban az **Új** lehetőséget az új sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6484e-143">On the Action Pane, select **New** to create a line.</span></span>
1. <span data-ttu-id="6484e-144">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6484e-145">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="6484e-145">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="6484e-146">**Leírás mező:** *20-nál kisebb munkamennyiség és csökkenő*</span><span class="sxs-lookup"><span data-stu-id="6484e-146">**Description field:** *Work quantity less than 20 and Descending*</span></span>

1. <span data-ttu-id="6484e-147">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6484e-147">Select **Save**.</span></span>
1. <span data-ttu-id="6484e-148">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6484e-148">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="6484e-149">Az **illesztések** lapon bontsa ki az illesztési hierarchiát a **Munkasorok** tábla megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="6484e-149">On the **Joins** tab, expand the join hierarchy to show the **Work lines** table.</span></span>
1. <span data-ttu-id="6484e-150">Válassza ki a **Munkasorok** tábla illesztését.</span><span class="sxs-lookup"><span data-stu-id="6484e-150">Select the **Work lines** table join.</span></span>
1. <span data-ttu-id="6484e-151">Válassza a **Táblaillesztés hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6484e-151">Select **Add table join**.</span></span>
1. <span data-ttu-id="6484e-152">A megjelenő listában keresse meg és válassza ki azt a sort, amelynél a következő beállítások szerepelnek:</span><span class="sxs-lookup"><span data-stu-id="6484e-152">In the list that appears, find and select the row that has the following settings:</span></span>

    - <span data-ttu-id="6484e-153">**Illesztési mód:** *n:1*</span><span class="sxs-lookup"><span data-stu-id="6484e-153">**Join mode:** *n:1*</span></span>
    - <span data-ttu-id="6484e-154">**Kapcsolat:** *Helyek (hely)*</span><span class="sxs-lookup"><span data-stu-id="6484e-154">**Relation:** *Locations (Location)*</span></span>

1. <span data-ttu-id="6484e-155">Válassza ki a **Kiválasztás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6484e-155">Select **Select**.</span></span>

    <span data-ttu-id="6484e-156">A helyek hozzáadásra kerülnek a tábla illesztéséhez.</span><span class="sxs-lookup"><span data-stu-id="6484e-156">Locations are added to the table join.</span></span>

1. <span data-ttu-id="6484e-157">A **Rendezés** lapon válassza a **Hozzáadás** lehetőséget új sor hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="6484e-157">On the **Sorting** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="6484e-158">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6484e-159">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="6484e-159">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6484e-160">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="6484e-160">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6484e-161">**Mező:** *Munkamennyiség* (a megjelenő üzenetablakban válassza az **Igen** lehetőséget, ha hozzá szeretné adni a rendezést ehhez a mezőhöz.)</span><span class="sxs-lookup"><span data-stu-id="6484e-161">**Field:** *Work quantity* (In the message box that appears, select **Yes** to add sorting to this field.)</span></span>
    - <span data-ttu-id="6484e-162">**Keresés iránya:** *Csökkenő*</span><span class="sxs-lookup"><span data-stu-id="6484e-162">**Search direction:** *Descending*</span></span>

1. <span data-ttu-id="6484e-163">Válassza ki a **Tartomány** lapot.</span><span class="sxs-lookup"><span data-stu-id="6484e-163">Select the **Range** tab.</span></span>

    <span data-ttu-id="6484e-164">Ha csak meghatározott munkafeltételek szerepelhetnek a sorrendbe állításban, akkor megadhatja őket a **Tartomány** lapon. Ebben a példában csak azokat a munkát szeretné belefoglalni, amelyeknél a mennyiség 20 ea-nál kevesebb (a legalacsonyabb mértékegység).</span><span class="sxs-lookup"><span data-stu-id="6484e-164">If only specific work criteria should be included in the sequencing, you can specify them on the **Range** tab. In this example, you want to include only work where the quantity is less than 20 ea (the lowest unit of measure).</span></span>

    <span data-ttu-id="6484e-165">Figyelje meg, hogy egyes sorok már szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="6484e-165">Notice that some lines are already included.</span></span> <span data-ttu-id="6484e-166">Ezeket a sorokat nem szabad eltávolítani.</span><span class="sxs-lookup"><span data-stu-id="6484e-166">Those lines should not be removed.</span></span>

1. <span data-ttu-id="6484e-167">Sor hozzáadásához válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6484e-167">Select **Add** to add a line.</span></span>
1. <span data-ttu-id="6484e-168">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-168">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6484e-169">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="6484e-169">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6484e-170">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="6484e-170">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6484e-171">**Mező:** *Készlet munkamennyisége*</span><span class="sxs-lookup"><span data-stu-id="6484e-171">**Field:** *Inventory work quantity*</span></span>
    - <span data-ttu-id="6484e-172">**Feltételek:** *\<20* (kisebb, mint 20)</span><span class="sxs-lookup"><span data-stu-id="6484e-172">**Criteria:** *\<20* (less than 20)</span></span>

1. <span data-ttu-id="6484e-173">További sor hozzáadásához válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6484e-173">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="6484e-174">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6484e-175">**Táblázat:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="6484e-175">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="6484e-176">**Származtatott tábla:** *Munkasorok*</span><span class="sxs-lookup"><span data-stu-id="6484e-176">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="6484e-177">**Mező:** *Munkatípus*</span><span class="sxs-lookup"><span data-stu-id="6484e-177">**Field:** *Work type*</span></span>
    - <span data-ttu-id="6484e-178">**Feltételek:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="6484e-178">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="6484e-179">További sor hozzáadásához válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6484e-179">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="6484e-180">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="6484e-181">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="6484e-181">**Table:** *Locations*</span></span>
    - <span data-ttu-id="6484e-182">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="6484e-182">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="6484e-183">**Mező:** *Hely profilazonosítója*</span><span class="sxs-lookup"><span data-stu-id="6484e-183">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="6484e-184">**Feltételek:** *!FOKOZAT*</span><span class="sxs-lookup"><span data-stu-id="6484e-184">**Criteria:** *!STAGE*</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="6484e-185">Ügyeljen arra, hogy a felkiáltójel (*!*) szerepeljen a *FOKOZAT* előtt.</span><span class="sxs-lookup"><span data-stu-id="6484e-185">Be sure to include the exclamation point (*!*) in front of *STAGE*.</span></span>

1. <span data-ttu-id="6484e-186">Az **OK** gombra kattintva mentse és zárja be a lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="6484e-186">Select **OK** to save and close the query.</span></span>
1. <span data-ttu-id="6484e-187">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6484e-187">Select **Save**.</span></span>
1. <span data-ttu-id="6484e-188">Zárja be az oldalt, és térjen vissza a **Mobileszköz menüpontjai** oldalra.</span><span class="sxs-lookup"><span data-stu-id="6484e-188">Close the page to return to the **Mobile device menu items** page.</span></span>

> [!NOTE]
> <span data-ttu-id="6484e-189">Ez a beállítás határozza meg a feltételt, amely a választható munkát a mobileszköz menüelembe történő betöltéséhez fogja használni.</span><span class="sxs-lookup"><span data-stu-id="6484e-189">This setup defines the criteria that will be used to feed eligible work to the mobile device menu item.</span></span> <span data-ttu-id="6484e-190">Ha több feltételsort ad hozzá a lekérdezéshez, akkor a rendszer először a legalacsonyabb sorszámú lekérdezési sort fogja használni.</span><span class="sxs-lookup"><span data-stu-id="6484e-190">If you add more criteria lines to the query, the system will use the query line that has lowest sequence number first.</span></span> <span data-ttu-id="6484e-191">Más szóval az 1. sorszám összes támogatható munkáját kapja meg először a felhasználó, majd a 2. sorszám összes munkáját.</span><span class="sxs-lookup"><span data-stu-id="6484e-191">In other words, all eligible work for sequence number 1 will be presented to the user first, and then all work for sequence number 2.</span></span> <span data-ttu-id="6484e-192">Ezért ha egy meghatározott tartományt és rendezést együtt kell használni, akkor ugyanabban a rendszer által irányított munka sorrendbe állítási lekérdezésben kell megadni.</span><span class="sxs-lookup"><span data-stu-id="6484e-192">Therefore, if a specific range and sorting must be used together, they should be specified in the same system-directed work sequence query.</span></span>
>
> <span data-ttu-id="6484e-193">Ez a beállítás rögzíti azokat a munkafolyamatokat, amelyeknek legalább egy sora van, ahol a mennyiség kevesebb, mint 20 ea.</span><span class="sxs-lookup"><span data-stu-id="6484e-193">This setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="6484e-194">Ezért, ha a munka olyan sorral rendelkezik, ahol a mennyiség pontosan 20 ea vagy több, mint 20 ea, akkor érvényes, feltéve, hogy legalább egy olyan sor van, amelynél a mennyiség kevesebb, mint 20 ea.</span><span class="sxs-lookup"><span data-stu-id="6484e-194">Therefore, if the work has a line where the quantity is exactly 20 ea or more than 20 ea, it will be valid, provided that it also has at least one line where the quantity is less than 20 ea.</span></span>

### <a name="location-directives"></a><span data-ttu-id="6484e-195">Helyutasítások</span><span class="sxs-lookup"><span data-stu-id="6484e-195">Location directives</span></span>

<span data-ttu-id="6484e-196">Ha az alapértelmezett Contoso-adatokat használja, akkor a helyutasítás művelethez tartozó lekérdezés nem fog változtatásokat igényelni.</span><span class="sxs-lookup"><span data-stu-id="6484e-196">If you're using default Contoso data, the query for the location directive action won't require changes.</span></span> <span data-ttu-id="6484e-197">Azonban annak érdekében, hogy a szolgáltatás nem Contoso-környezetben történő alkalmazása esetén az értékesítési rendeléseken szereplő cikkeket a helyutasítások rögzítsék, új helyutasításokat kell létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="6484e-197">However, to make sure that the location directives will capture the items on the sales orders when you apply the feature in a non-Contoso environment, create a new location directive.</span></span> <span data-ttu-id="6484e-198">A beállítások ellenőrzéséhez a demókörnyezetben hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6484e-198">To verify the settings in the demo environment, follow these steps.</span></span>

1. <span data-ttu-id="6484e-199">Ugrás a **Raktárkezelés** \> **Beállítás** \> **Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="6484e-199">Go to **Warehouse management** \> **Setup** \> **Location directives**.</span></span>
1. <span data-ttu-id="6484e-200">A **Munkarendelés típusa** mezőben válassza ki az *Értékesítési rendelések* elemet.</span><span class="sxs-lookup"><span data-stu-id="6484e-200">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="6484e-201">Válassza ki az *51 kitárolás* nevű helyutasítást.</span><span class="sxs-lookup"><span data-stu-id="6484e-201">Select the location directive that is named *51 Pick*.</span></span>
1. <span data-ttu-id="6484e-202">A **Helyutasítás műveletei** gyorslapon válassza ki a **Kitárolás** művelet sorát.</span><span class="sxs-lookup"><span data-stu-id="6484e-202">On the **Location Directive Actions** FastTab, select the line for the **Pick** action.</span></span>
1. <span data-ttu-id="6484e-203">Válassza ki a **Lekérdezés szerkesztése** lehetőséget a rács fölött.</span><span class="sxs-lookup"><span data-stu-id="6484e-203">Select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="6484e-204">Tekintse át a **Tartomány** lekérdezést.</span><span class="sxs-lookup"><span data-stu-id="6484e-204">Review the **Range** query.</span></span>

    1. <span data-ttu-id="6484e-205">Keresse meg azt a sort, amelynél a **Mező** mező értéke *Hely*.</span><span class="sxs-lookup"><span data-stu-id="6484e-205">Find the line where the **Field** field is set to *Location*.</span></span>
    2. <span data-ttu-id="6484e-206">Győződjön meg róla, hogy a **Feltételek** mező üres (azaz nincsenek korlátozások).</span><span class="sxs-lookup"><span data-stu-id="6484e-206">Make sure that the **Criteria** field is blank (that is, there are no restrictions).</span></span>

## <a name="scenario"></a><span data-ttu-id="6484e-207">Forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="6484e-207">Scenario</span></span>

### <a name="create-sales-order-picking-work"></a><span data-ttu-id="6484e-208">Értékesítési rendelés kitárolási munkájának létrehozása</span><span class="sxs-lookup"><span data-stu-id="6484e-208">Create sales order picking work</span></span>

<span data-ttu-id="6484e-209">A rendszer által irányított kitárolás futtatása előtt létre kell hozni néhány kimenő munkát.</span><span class="sxs-lookup"><span data-stu-id="6484e-209">Before system-directed picking is run, some outbound work should be created.</span></span> <span data-ttu-id="6484e-210">Ehhez a helyzethez négy olyan értékesítési rendelést hoz létre, amelyek a megadott rendszer által irányított munka sorrendbe állítási lekérdezéseken alapulnak.</span><span class="sxs-lookup"><span data-stu-id="6484e-210">For this scenario, you will create four sales orders that are based on the specified system-directed work sequence queries.</span></span>

<span data-ttu-id="6484e-211">A program minden értékesítési rendeléshez lefoglalja a készletmennyiséget.</span><span class="sxs-lookup"><span data-stu-id="6484e-211">You will reserve inventory quantities for each sales order.</span></span> <span data-ttu-id="6484e-212">Ezért a foglalt készletet nem lehet kivenni a raktárból más rendelésekhez a készletfoglalás (legalább részleges) visszavonásáig.</span><span class="sxs-lookup"><span data-stu-id="6484e-212">Therefore, reserved inventory can't be withdrawn from the warehouse for other orders unless the inventory reservation, or part of the inventory reservation, is canceled.</span></span>

<span data-ttu-id="6484e-213">Ezt követően minden értékesítési rendelést kiad a raktárba, hogy létrehozza a kimenő munkát.</span><span class="sxs-lookup"><span data-stu-id="6484e-213">You will then release each sales order to the warehouse to create the outbound work.</span></span>

#### <a name="sales-order-1"></a><span data-ttu-id="6484e-214">1. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="6484e-214">Sales order 1</span></span>

1. <span data-ttu-id="6484e-215">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="6484e-215">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="6484e-216">Jelölje be a műveleti ablakban az **Új** lehetőséget az 1. értékesítési rendelés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6484e-216">On the Action Pane, select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="6484e-217">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-217">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6484e-218">A **Vevő** szakaszban adja meg a **Vevőfiók** mezőt az *US-004* számára.</span><span class="sxs-lookup"><span data-stu-id="6484e-218">In the **Customer** section, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="6484e-219">Az **Általános** szakaszban állítsa a **Raktár** mezőt az *51* értékre.</span><span class="sxs-lookup"><span data-stu-id="6484e-219">In the **General** section, set the **Warehouse** field to *51*.</span></span>

1. <span data-ttu-id="6484e-220">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6484e-220">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="6484e-221">Jegyezze fel az értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="6484e-221">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="6484e-222">Adjon hozzá egy sort az új értékesítési rendeléshez, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-222">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="6484e-223">**Cikkszám:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="6484e-223">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="6484e-224">**Mennyiség:** *20*</span><span class="sxs-lookup"><span data-stu-id="6484e-224">**Quantity:** *20*</span></span>

1. <span data-ttu-id="6484e-225">A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.</span><span class="sxs-lookup"><span data-stu-id="6484e-225">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="6484e-226">A **Foglalás** oldalon válassza ki a **Készlet foglalása** elemet a készlet lefoglalásához.</span><span class="sxs-lookup"><span data-stu-id="6484e-226">On the **Reservation** page, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="6484e-227">Zárja be a **Foglalás** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="6484e-227">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="6484e-228">Válassza ki a művelet ablaktáblán a **Raktár** lapon a válassza a **Kiadás raktárba** parancsot munka létrehozásához a raktár számára.</span><span class="sxs-lookup"><span data-stu-id="6484e-228">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse** to create work for the warehouse.</span></span>

    <span data-ttu-id="6484e-229">Olyan tájékoztató üzenetek érkeznek, amelyek az értékesítési rendeléshez létrehozott hullámazonosítókat és szállítási azonosítókat jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="6484e-229">You receive informational messages that show the wave ID and shipment IDs that were created for the sales order.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="6484e-230">2. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="6484e-230">Sales order 2</span></span>

1. <span data-ttu-id="6484e-231">Jelölje be a műveleti ablakban az **Új** lehetőséget a 2. értékesítési rendelés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6484e-231">On the Action Pane, select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="6484e-232">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-232">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6484e-233">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="6484e-233">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="6484e-234">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="6484e-234">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6484e-235">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6484e-235">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="6484e-236">Jegyezze fel az értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="6484e-236">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="6484e-237">Adjon hozzá egy sort az új értékesítési rendeléshez, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-237">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="6484e-238">**Cikkszám:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="6484e-238">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="6484e-239">**Mennyiség:** *5*</span><span class="sxs-lookup"><span data-stu-id="6484e-239">**Quantity:** *5*</span></span>

1. <span data-ttu-id="6484e-240">Válassza ki a **Sor hozzáadása** lehetőséget egy második sort hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-240">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="6484e-241">**Cikkszám:** *M9201*</span><span class="sxs-lookup"><span data-stu-id="6484e-241">**Item number:** *M9201*</span></span>
    - <span data-ttu-id="6484e-242">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="6484e-242">**Quantity:** *1*</span></span>

1. <span data-ttu-id="6484e-243">Készlet foglalása mindkét sorhoz.</span><span class="sxs-lookup"><span data-stu-id="6484e-243">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="6484e-244">Adja ki a rendeléseket a raktárba.</span><span class="sxs-lookup"><span data-stu-id="6484e-244">Release the order to the warehouse.</span></span>

#### <a name="sales-order-3"></a><span data-ttu-id="6484e-245">3. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="6484e-245">Sales order 3</span></span>

1. <span data-ttu-id="6484e-246">Jelölje be a műveleti ablakban az **Új** lehetőséget a 3. értékesítési rendelés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6484e-246">On the Action Pane, select **New** to create sales order 3.</span></span>
1. <span data-ttu-id="6484e-247">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-247">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6484e-248">**Vevőkód** *US-009*</span><span class="sxs-lookup"><span data-stu-id="6484e-248">**Customer account:** *US-009*</span></span>
    - <span data-ttu-id="6484e-249">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="6484e-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6484e-250">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6484e-250">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="6484e-251">Jegyezze fel az értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="6484e-251">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="6484e-252">Adjon hozzá egy sort az új értékesítési rendeléshez, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-252">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="6484e-253">**Cikkszám:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="6484e-253">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="6484e-254">**Mennyiség:** *7*</span><span class="sxs-lookup"><span data-stu-id="6484e-254">**Quantity:** *7*</span></span>

1. <span data-ttu-id="6484e-255">Válassza ki a **Sor hozzáadása** lehetőséget egy második sort hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-255">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="6484e-256">**Cikkszám:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="6484e-256">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="6484e-257">**Mennyiség:** *8*</span><span class="sxs-lookup"><span data-stu-id="6484e-257">**Quantity:** *8*</span></span>

1. <span data-ttu-id="6484e-258">Készlet foglalása mindkét sorhoz.</span><span class="sxs-lookup"><span data-stu-id="6484e-258">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="6484e-259">Adja ki a rendeléseket a raktárba.</span><span class="sxs-lookup"><span data-stu-id="6484e-259">Release the order to the warehouse.</span></span>

#### <a name="sales-order-4"></a><span data-ttu-id="6484e-260">4. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="6484e-260">Sales order 4</span></span>

1. <span data-ttu-id="6484e-261">Jelölje be a műveleti ablakban az **Új** lehetőséget a 4. értékesítési rendelés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="6484e-261">On the Action Pane, select **New** to create sales order 4.</span></span>
1. <span data-ttu-id="6484e-262">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-262">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6484e-263">**Vevőkód** *US-010*</span><span class="sxs-lookup"><span data-stu-id="6484e-263">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="6484e-264">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="6484e-264">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="6484e-265">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="6484e-265">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="6484e-266">Jegyezze fel az értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="6484e-266">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="6484e-267">Adjon hozzá egy sort az új értékesítési rendeléshez, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-267">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="6484e-268">**Cikkszám:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="6484e-268">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="6484e-269">**Mennyiség:** *25*</span><span class="sxs-lookup"><span data-stu-id="6484e-269">**Quantity:** *25*</span></span>

1. <span data-ttu-id="6484e-270">Válassza ki a **Sor hozzáadása** lehetőséget egy második sort hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="6484e-270">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="6484e-271">**Cikkszám:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="6484e-271">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="6484e-272">**Mennyiség:** *10*</span><span class="sxs-lookup"><span data-stu-id="6484e-272">**Quantity:** *10*</span></span>

1. <span data-ttu-id="6484e-273">Készlet foglalása mindkét sorhoz.</span><span class="sxs-lookup"><span data-stu-id="6484e-273">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="6484e-274">Adja ki a rendeléseket a raktárba.</span><span class="sxs-lookup"><span data-stu-id="6484e-274">Release the order to the warehouse.</span></span>

### <a name="get-work-ids-for-the-work-that-was-created"></a><span data-ttu-id="6484e-275">Munkaazonosítók beolvasása a létrehozott munkához</span><span class="sxs-lookup"><span data-stu-id="6484e-275">Get work IDs for the work that was created</span></span>

1. <span data-ttu-id="6484e-276">Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.</span><span class="sxs-lookup"><span data-stu-id="6484e-276">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="6484e-277">Szűrjön a **Raktár** mezőre úgy, hogy csak az *51*-es raktárban lévő munka jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="6484e-277">Filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="6484e-278">Négy munkaazonosítónak kellett létrejönnie.</span><span class="sxs-lookup"><span data-stu-id="6484e-278">Four work IDs should have been created.</span></span> <span data-ttu-id="6484e-279">Jegyezze fel az egyes értékesítési rendelések munkaazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="6484e-279">Make a note of the work ID for each sales order.</span></span>

    | <span data-ttu-id="6484e-280">Értékesítési rendelés azonosítója</span><span class="sxs-lookup"><span data-stu-id="6484e-280">Sales order ID</span></span> | <span data-ttu-id="6484e-281">Munkaazonosító</span><span class="sxs-lookup"><span data-stu-id="6484e-281">Work ID</span></span> | <span data-ttu-id="6484e-282">Munkakészlet</span><span class="sxs-lookup"><span data-stu-id="6484e-282">Work quantity</span></span> |
    |---|---|---|
    | <span data-ttu-id="6484e-283">1. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="6484e-283">Sales Order 1</span></span> | <span data-ttu-id="6484e-284">1. munkaazonosító</span><span class="sxs-lookup"><span data-stu-id="6484e-284">Work ID 1</span></span> | <span data-ttu-id="6484e-285">20 ea</span><span class="sxs-lookup"><span data-stu-id="6484e-285">20 ea</span></span> |
    | <span data-ttu-id="6484e-286">2. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="6484e-286">Sales Order 2</span></span> | <span data-ttu-id="6484e-287">2. munkaazonosító</span><span class="sxs-lookup"><span data-stu-id="6484e-287">Work ID 2</span></span> | <span data-ttu-id="6484e-288">6 ea (mindkét sor összege)</span><span class="sxs-lookup"><span data-stu-id="6484e-288">6 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="6484e-289">3. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="6484e-289">Sales Order 3</span></span> | <span data-ttu-id="6484e-290">3. munkaazonosító</span><span class="sxs-lookup"><span data-stu-id="6484e-290">Work ID 3</span></span> | <span data-ttu-id="6484e-291">15 ea (mindkét sor összege)</span><span class="sxs-lookup"><span data-stu-id="6484e-291">15 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="6484e-292">4. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="6484e-292">Sales Order 4</span></span> | <span data-ttu-id="6484e-293">4. munkaazonosító</span><span class="sxs-lookup"><span data-stu-id="6484e-293">Work ID 4</span></span> | <span data-ttu-id="6484e-294">35 ea (mindkét sor összege)</span><span class="sxs-lookup"><span data-stu-id="6484e-294">35 ea (sum of both lines)</span></span> |

<span data-ttu-id="6484e-295">Mielőtt futtatná a folyamatot a mobileszközön, győződjön meg arról, hogy csak az imént létrehozott munka van *Nyitva* állapotban van az *51*-es raktár és az *Értékesítési rendelés* munkarendelés-típus esetében.</span><span class="sxs-lookup"><span data-stu-id="6484e-295">Before you run the flow on the mobile device, make sure that only the work that you just created is in *Open* status for warehouse *51* and the *Sales order* work order type.</span></span> <span data-ttu-id="6484e-296">Ellenkező esetben a teszt eredményei eltérőek lehetnek, mivel a rendszer által irányított kitárolás az összes alkalmas munkát tartalmazni fogja.</span><span class="sxs-lookup"><span data-stu-id="6484e-296">Otherwise, the results of the test might vary, because the system-direct picking will include all eligible work.</span></span>

1. <span data-ttu-id="6484e-297">Lépjen a **Raktárkezelés \> Munka \> Kimenő \> Nyitott értékesítési munka** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6484e-297">Go to **Warehouse management \> Work \> Outbound \> Open sales work**.</span></span>
1. <span data-ttu-id="6484e-298">A **Nyitott értékesítési munka** rácsban szűrjön a **Raktár** mezőre úgy, hogy csak az *51*-es raktárban lévő munka jelenjen meg.</span><span class="sxs-lookup"><span data-stu-id="6484e-298">In the **Open sales work** grid, filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="6484e-299">Győződjön meg róla, hogy csak a korábban létrehozott négy munkaazonosító jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6484e-299">Confirm that only the four work IDs that you created earlier are shown.</span></span>
1. <span data-ttu-id="6484e-300">Zárja be a **Munka** oldalt.</span><span class="sxs-lookup"><span data-stu-id="6484e-300">Close the **Work** page.</span></span>

### <a name="mobile-device-flow-execution"></a><span data-ttu-id="6484e-301">Mobileszköz folyamat végrehajtása</span><span class="sxs-lookup"><span data-stu-id="6484e-301">Mobile device flow execution</span></span>

<span data-ttu-id="6484e-302">A beállítás alapján a rendszer a munkasorban szereplő legmagasabb mennyiségtől a legalacsonyabbig rendezett munkát fogja betölteni a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="6484e-302">Based on the setup, the system will feed the user work that is sorted from the highest work line quantity to the lowest.</span></span> <span data-ttu-id="6484e-303">Az összes sorban szereplő mennyiség kisebb lesz, mint 20 ea.</span><span class="sxs-lookup"><span data-stu-id="6484e-303">The quantity on every line will be less than 20 ea.</span></span>

<span data-ttu-id="6484e-304">Ne feledje, hogy ez a beállítás rögzíti azokat a munkafolyamatokat, amelyeknek legalább egy sora van, ahol a mennyiség kevesebb, mint 20 ea.</span><span class="sxs-lookup"><span data-stu-id="6484e-304">Remember that this setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="6484e-305">Ha tehát a munka rendelkezik egy másik sorral, ahol a mennyiség pontosan 20 ea vagy több, mint 20 ea, akkor is érvényes lesz.</span><span class="sxs-lookup"><span data-stu-id="6484e-305">Therefore, if the work has another line where the quantity is exactly 20 ea or more than 20 ea, it will also be valid.</span></span>

#### <a name="mobile-app"></a><span data-ttu-id="6484e-306">Mobilalkalmazás</span><span class="sxs-lookup"><span data-stu-id="6484e-306">Mobile app</span></span>

1. <span data-ttu-id="6484e-307">Jelentkezzen be az *51*-es raktárban lévő felhasználóként a raktárkezelési alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="6484e-307">Sign in to the warehousing app as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="6484e-308">Lépjen a **Kimenő \> Értékesítési kitárolás – Rendszer** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6484e-308">Go to **Outbound \> Sales Picking - System**.</span></span>

    <span data-ttu-id="6484e-309">Megjelenik a *4*. munkaazonosító kitárolási lépése.</span><span class="sxs-lookup"><span data-stu-id="6484e-309">The pick step for work ID *4* is presented.</span></span> <span data-ttu-id="6484e-310">Ezt a munkaazonosítót először a rendszer által irányított lekérdezési rendelés beállítása miatt jelenik meg, ahol megadhatja, hogy a munkát csökkenő munkasormennyiség alapján kell sorba állítani.</span><span class="sxs-lookup"><span data-stu-id="6484e-310">This work ID is presented first because of the setup of the system-directed query order, where you specified that work should be sequenced based on descending work line quantity.</span></span>

1. <span data-ttu-id="6484e-311">Töltse ki a szükséges kitárolást és elhelyezést, és zárja be a munkaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="6484e-311">Complete the required pick and put to close the work ID.</span></span>

    <span data-ttu-id="6484e-312">Ezután a *3.* munkaazonosító jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6484e-312">Next, work ID *3* is presented.</span></span> <span data-ttu-id="6484e-313">Az egyik munkasora a sorban a következő a munkasor mennyisége alapján.</span><span class="sxs-lookup"><span data-stu-id="6484e-313">One of its work lines is next in the sequence, based on the work line quantity.</span></span>

1. <span data-ttu-id="6484e-314">Töltse ki a kitárolást és elhelyezést, és zárja be a munkaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="6484e-314">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="6484e-315">Ezután a *2.* munkaazonosító jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6484e-315">Next, work ID *2* is presented.</span></span> <span data-ttu-id="6484e-316">Ennek a munkának a kitárolási sora a következő a sorrendben.</span><span class="sxs-lookup"><span data-stu-id="6484e-316">This work's pick line is next in the sequence.</span></span>

1. <span data-ttu-id="6484e-317">Töltse ki a kitárolást és elhelyezést, és zárja be a munkaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="6484e-317">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="6484e-318">További munkának nem kell megjelennie.</span><span class="sxs-lookup"><span data-stu-id="6484e-318">No further work should be presented to you.</span></span> <span data-ttu-id="6484e-319">Az *1.* munkaazonosító nem jogosult ehhez a mobileszköz-menüelemhez, mert a lekérdezés azt határozza meg, hogy a munkafejlécek csak akkor vehetők figyelembe, ha a munkasorokban szereplő mennyiség kevesebb, mint 20 ea.</span><span class="sxs-lookup"><span data-stu-id="6484e-319">Work ID *1* isn't eligible for this mobile device menu item, because the query specifies that work headers are considered only if the quantity on the work lines is less than 20 ea.</span></span>

## <a name="tips"></a><span data-ttu-id="6484e-320">Tippek</span><span class="sxs-lookup"><span data-stu-id="6484e-320">Tips</span></span>

<span data-ttu-id="6484e-321">A rendszer által irányított munka sorrendbe állítás lekérdezések *inkluzívak*.</span><span class="sxs-lookup"><span data-stu-id="6484e-321">The system-directed work sequence queries are *inclusive*.</span></span> <span data-ttu-id="6484e-322">Fontos, hogy néhány beállítás esetében ne feledkezzen meg erről.</span><span class="sxs-lookup"><span data-stu-id="6484e-322">It's important that you remember this fact for some setups.</span></span> <span data-ttu-id="6484e-323">Például előfordulhat, hogy azt szeretné, hogy egy konkrét menüelem csak olyan munkát dolgozzon fel, ahol a munkaegység *ea*, és megadja ezt a korlátozást a lekérdezés **Tartomány** lapján.</span><span class="sxs-lookup"><span data-stu-id="6484e-323">For example, you want a specific menu item to process only work where the work unit is *ea*, and you specify that restriction on the **Range** tab of the query.</span></span> <span data-ttu-id="6484e-324">Ebben az esetben a dolgozó megkapja az összes olyan munkát, amelyben legalább egy munkasor az *ea* munkaegységgel van beállítva.</span><span class="sxs-lookup"><span data-stu-id="6484e-324">In this case, all work where at least one work line has the work unit set to *ea* will be fed to the worker.</span></span> <span data-ttu-id="6484e-325">Ennek megfelelően ez a munka olyan munkafolyamatot is tartalmazhat, amelyben a munkasorok nem az *ea* munkaegységgel rendelkeznek (például *doboz* vagy *raklap*).</span><span class="sxs-lookup"><span data-stu-id="6484e-325">Therefore, this work might also include work where work lines have a work unit other than *ea* (such as *box* or *pallet*).</span></span> <span data-ttu-id="6484e-326">A lekérdezés csak akkor zár ki munkát, ha nincs olyan munkasor, ahol a munkaegység *ea* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="6484e-326">The query will exclude only work where no work line has the work unit set to *ea*.</span></span>

<span data-ttu-id="6484e-327">Emiatt a forgatókönyv példájában a lekérdezés a *4.* munkaazonosítót is rögzítette.</span><span class="sxs-lookup"><span data-stu-id="6484e-327">Therefore, in the example from this scenario, work ID *4* was also captured by the query.</span></span> <span data-ttu-id="6484e-328">A létrehozásakor két sor lett hozzáadva: egy 25 ea-val, egy másik pedig 10 ea-val.</span><span class="sxs-lookup"><span data-stu-id="6484e-328">When it was created, two lines were added: one for 25 ea and another for 10 ea.</span></span> <span data-ttu-id="6484e-329">A munka továbbra is megjelenik a felhasználó számára, mert legalább egy munkasornak 20 ea-nál kisebb a mennyisége.</span><span class="sxs-lookup"><span data-stu-id="6484e-329">The work was still presented to the user, because at least one work line has a quantity of less than 20 ea.</span></span>

<span data-ttu-id="6484e-330">A forgatókönyvtől függően megakadályozhatja ezt a viselkedést munkaszünetek segítségével.</span><span class="sxs-lookup"><span data-stu-id="6484e-330">Depending on the scenario, you can prevent this behavior by using work breaks.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]