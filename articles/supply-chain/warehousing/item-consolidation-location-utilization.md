---
title: Cikk-konszolidáció – hely kihasználtsága
description: Ez a témakör olyan funkcióról tartalmaz információkat, amely megkönnyítik a raktárvezetők számára hogy megtekintsék és szűrje a raktáraknak a raktáron belüli térfogat-kihasználását. A menedzserek kiválaszthatnak helyeket, és a cikkek konszolidálásához közvetlenül a cikk-összesítés lapon hozhatnak létre készletmozgatási munkát, és így jobban ki tudják használni a raktári helyet.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6a328b20c1cfb2fc376ab4656c64cf585a5aa015
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017184"
---
# <a name="item-consolidation---location-utilization"></a><span data-ttu-id="2f308-104">Cikk-konszolidáció – hely kihasználtsága</span><span class="sxs-lookup"><span data-stu-id="2f308-104">Item consolidation - location utilization</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2f308-105">Ez a témakör olyan funkcióról tartalmaz információkat, amely megkönnyítik a raktárvezetők számára hogy megtekintsék és szűrje a raktáraknak a raktáron belüli térfogat-kihasználását.</span><span class="sxs-lookup"><span data-stu-id="2f308-105">This topic provides information about functionality that makes it easy for warehouse managers to view and filter the volumetric utilization of locations across the warehouse.</span></span> <span data-ttu-id="2f308-106">A menedzserek kiválaszthatnak helyeket, és a cikkek konszolidálásához közvetlenül a **Cikk-konszolidáció** lapon hozhatnak létre készletmozgatási munkát, és így jobban ki tudják használni a raktári helyet.</span><span class="sxs-lookup"><span data-stu-id="2f308-106">Managers can select locations and create inventory movement work directly from the **Item Consolidation** page to consolidate items and therefore make better use of warehouse space.</span></span>

## <a name="turn-on-the-features"></a><span data-ttu-id="2f308-107">A funkciók bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="2f308-107">Turn on the features</span></span>

<span data-ttu-id="2f308-108">Az ebben a témakörben ismertetett szolgáltatások használata előtt be kell kapcsolni azokat a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="2f308-108">Before you can use the features that are described in this topic, you must turn them on in your system.</span></span> <span data-ttu-id="2f308-109">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet e funkciók állapotának ellenőrzéséhez, és szükség esetén a bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="2f308-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="2f308-110">A következő szolgáltatásokat kapcsolja be a listán szereplő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="2f308-110">Turn on both the following features, in the order that they are listed in.</span></span> <span data-ttu-id="2f308-111">(Mindkét funkció a **Raktárkezelés** modulhoz tartozik.)</span><span class="sxs-lookup"><span data-stu-id="2f308-111">(Both features are for the **Warehouse management** module.)</span></span>

1. <span data-ttu-id="2f308-112">Raktár helyállapota</span><span class="sxs-lookup"><span data-stu-id="2f308-112">Warehouse location status</span></span>
2. <span data-ttu-id="2f308-113">Cikk-konszolidáció helyének kihasználtsága</span><span class="sxs-lookup"><span data-stu-id="2f308-113">Item consolidation location utilization</span></span>

## <a name="warehouse-location-status"></a><span data-ttu-id="2f308-114">Raktár helyállapota</span><span class="sxs-lookup"><span data-stu-id="2f308-114">Warehouse location status</span></span>

<span data-ttu-id="2f308-115">A *Raktár helyállapota* funkció négy új mezőt ad hozzá a **Helyek** oldalhoz a hely aktuális állapotával kapcsolatos további információk nyomon követése céljából:</span><span class="sxs-lookup"><span data-stu-id="2f308-115">The *Warehouse location status* feature adds four new fields to the **Locations** page to track additional information about the current state of the location:</span></span>

- <span data-ttu-id="2f308-116">**Cikkszám** – Az a cikk, amely jelenleg a helyen van.</span><span class="sxs-lookup"><span data-stu-id="2f308-116">**Item number** – The item that is currently in the location.</span></span> <span data-ttu-id="2f308-117">Ha a hely több cikket tartalmaz, akkor ez a mező üres lesz.</span><span class="sxs-lookup"><span data-stu-id="2f308-117">If the location contains multiple items, this field will be blank.</span></span>
- <span data-ttu-id="2f308-118">**Utolsó tevékenység dátuma és időpontja** – A helyen végrehajtott legutóbbi raktári tranzakció időbélyegzője.</span><span class="sxs-lookup"><span data-stu-id="2f308-118">**Last activity date and time** – The timestamp of the last warehouse transaction that was performed against the location.</span></span>
- <span data-ttu-id="2f308-119">**Korosítási dátum** – Az a dátum, amikor a helyen található készletet bevitték a raktárba.</span><span class="sxs-lookup"><span data-stu-id="2f308-119">**Aging date** – The date when the inventory in the location was brought into the warehouse.</span></span> <span data-ttu-id="2f308-120">Ezt az dátumot az azonosítótábla korosítási dátuma alapján számítja ki a program.</span><span class="sxs-lookup"><span data-stu-id="2f308-120">This date is calculated based on the license plate aging date.</span></span> <span data-ttu-id="2f308-121">Ugyan ez a dátum az azonosítótábla által nyomon követett helyek esetében pontos, de lehet, hogy nem pontos a nem azonosítótábla által nyomon követett helyek esetében.</span><span class="sxs-lookup"><span data-stu-id="2f308-121">Although this date is accurate for license plate–tracked locations, it might not be accurate for locations that aren't license plate–tracked.</span></span>
- <span data-ttu-id="2f308-122">**Hely állapota** – A hely állapota.</span><span class="sxs-lookup"><span data-stu-id="2f308-122">**Location status** – The status of the location.</span></span> <span data-ttu-id="2f308-123">Négy érték érhető el:</span><span class="sxs-lookup"><span data-stu-id="2f308-123">Four values are available:</span></span>

    - <span data-ttu-id="2f308-124">**Meghatározatlan** – A helyprofil nem követi nyomon az állapotot.</span><span class="sxs-lookup"><span data-stu-id="2f308-124">**Undetermined** – The location profile doesn't track status.</span></span> <span data-ttu-id="2f308-125">Ezért az aktuális állapot ismeretlen.</span><span class="sxs-lookup"><span data-stu-id="2f308-125">Therefore, the current status is unknown.</span></span>
    - <span data-ttu-id="2f308-126">**Üres** – Jelenleg nincs készletet a helyen.</span><span class="sxs-lookup"><span data-stu-id="2f308-126">**Empty** – No inventory is currently in the location.</span></span>
    - <span data-ttu-id="2f308-127">**Kitárolás** – Kimenő tranzakciókat hajtottak végre a helyen a legutóbbi üres állapot után.</span><span class="sxs-lookup"><span data-stu-id="2f308-127">**Picking** – Outbound transactions have been performed against the location after it was last empty.</span></span>
    - <span data-ttu-id="2f308-128">**Tárolás** – Csak bemenő tranzakciókat hajtottak végre a hellyel szemben a legutóbbi üres állapot óta.</span><span class="sxs-lookup"><span data-stu-id="2f308-128">**Storage** – Only inbound transactions have been performed since the location was last empty.</span></span>

<span data-ttu-id="2f308-129">Ezeknél a mezőknél a raktári vezetők jobb áttekintést kaphatnak a raktári helyek állapotáról.</span><span class="sxs-lookup"><span data-stu-id="2f308-129">These fields let warehouse managers get a better overview of the status of the locations in the warehouse.</span></span> <span data-ttu-id="2f308-130">Lehetővé teszik az összetettebb jelentéskészítést és szűrést is.</span><span class="sxs-lookup"><span data-stu-id="2f308-130">They also allow for more advanced reporting and filtering.</span></span>

## <a name="set-up-item-consolidation-and-location-utilization"></a><span data-ttu-id="2f308-131">Cikk-konszolidáció és helykihasználtság beállítása</span><span class="sxs-lookup"><span data-stu-id="2f308-131">Set up item consolidation and location utilization</span></span>

<span data-ttu-id="2f308-132">Ez a szakasz bemutatja, hogyan kell előkészíteni a rendszert a cikk-konszolidáció és a helykihasználtság használatára.</span><span class="sxs-lookup"><span data-stu-id="2f308-132">This section describes how to prepare your system to use item consolidation and location utilization.</span></span> <span data-ttu-id="2f308-133">Az eljárások a mintaértékeket a szokásos demóadatokból használják.</span><span class="sxs-lookup"><span data-stu-id="2f308-133">The procedures use sample values from the standard demo data.</span></span> <span data-ttu-id="2f308-134">Ha azt tervezi, hogy a jelen témakörben később ismertetett példaforgatókönyvvel dolgozik, válassza ki a **USMF** jogi személyt (amely tartalmazza a standard demóadatokat), és hozza létre azokat a rekordokat, amelyeket ebben a szakaszban ismertetve vannak.</span><span class="sxs-lookup"><span data-stu-id="2f308-134">If you plan to work through the example scenario that is provided later in this topic, select the **USMF** legal entity (which contains the standard demo data), and create each record that is described in this section.</span></span> <span data-ttu-id="2f308-135">Ha nem tervezi elvégezni a példaforgatókönyvet, akkor az itt megadott értékek példaként szolgálnak, hogy milyen típusú beállításokat kell végrehajtani a szolgáltatások használatához.</span><span class="sxs-lookup"><span data-stu-id="2f308-135">If you don't plan to work through the example scenario, the values that are provided here can be considered examples of the types of setup that you must complete to use the features.</span></span>

### <a name="released-product"></a><span data-ttu-id="2f308-136">Kiadott termék</span><span class="sxs-lookup"><span data-stu-id="2f308-136">Released product</span></span>

1. <span data-ttu-id="2f308-137">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2f308-137">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="2f308-138">A **Cikkszám** mezőben válassza ki az *M9201* elemet, majd nyissa meg a részletek lapot.</span><span class="sxs-lookup"><span data-stu-id="2f308-138">In the **Item number** field, select *M9201* , and open the details page.</span></span>
1. <span data-ttu-id="2f308-139">A Műveleti panelen, a **Készletkezelés lapon** a **Raktár** csoportban válassza ki a **Tényleges dimenziók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-139">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="2f308-140">A **Tényleges méret** lap műveleti paneljén válassza ki az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="2f308-140">On the **Physical dimension** page, on the Action Pane, select **New**.</span></span>

    <span data-ttu-id="2f308-141">A program új sort ad hozzá a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="2f308-141">A new line is added to the grid.</span></span> <span data-ttu-id="2f308-142">A **Cikkszám** mező előőre be van állítva.</span><span class="sxs-lookup"><span data-stu-id="2f308-142">The **Item number** field is preset.</span></span>

1. <span data-ttu-id="2f308-143">Válassza ki az **Egység** mezőben az *ea* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-143">In the **Unit** field, select *ea*.</span></span> <span data-ttu-id="2f308-144">A program automatikusan beállítja a sor fennmaradó mezőit.</span><span class="sxs-lookup"><span data-stu-id="2f308-144">The remaining fields on the line are automatically set.</span></span>
1. <span data-ttu-id="2f308-145">Válassza a **Mentés** gombot, és zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="2f308-145">Select **Save** , and close the page.</span></span>

### <a name="location-profile"></a><span data-ttu-id="2f308-146">Helyprofil</span><span class="sxs-lookup"><span data-stu-id="2f308-146">Location profile</span></span>

1. <span data-ttu-id="2f308-147">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.</span><span class="sxs-lookup"><span data-stu-id="2f308-147">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="2f308-148">A helyprofilok listáján válassza az **5. EMELET** elemet.</span><span class="sxs-lookup"><span data-stu-id="2f308-148">In the list of location profiles, select **FLOOR-05**.</span></span>
1. <span data-ttu-id="2f308-149">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-149">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="2f308-150">Győződjön meg arról , hogy az **Általános** gyorslapon a következő beállítások közül mindkettő az *Igen* értérek van beállítva:</span><span class="sxs-lookup"><span data-stu-id="2f308-150">On the **General** FastTab, make sure that both the following options are set to *Yes* :</span></span>

    - <span data-ttu-id="2f308-151">Helyen levő cikk engedélyezése</span><span class="sxs-lookup"><span data-stu-id="2f308-151">Enable item in location</span></span>
    - <span data-ttu-id="2f308-152">Helyállapot engedélyezése</span><span class="sxs-lookup"><span data-stu-id="2f308-152">Enable location status</span></span>

1. <span data-ttu-id="2f308-153">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-153">Select **Save**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2f308-154">Ha a **Cikk engedélyezése helyen** , és a **Hely állapotának engedélyezése** beállítás már *Igen* értékre van állítva , ugorjon a **Dimenziók** gyorslap beállításával kapcsolatosa utasításokra a 10. lépésben.</span><span class="sxs-lookup"><span data-stu-id="2f308-154">If the **Enable item in location** and **Enable location status** options were already set to *Yes* , skip ahead to the instructions for setting up the **Dimensions** FastTab in step 10.</span></span> <span data-ttu-id="2f308-155">Ha a lehetőségek nem lettek volna beállítva *Igen* értékre , akkor a kézi beállítás után futtatnia kell a **Raktárkezelési modul** konzisztenciavizsgálatát.</span><span class="sxs-lookup"><span data-stu-id="2f308-155">If the options weren't already set to *Yes* , you must run a consistency check for the **Warehouse management** module after you manually set them.</span></span> <span data-ttu-id="2f308-156">Ebben az esetben folytassa a következő lépéssel.</span><span class="sxs-lookup"><span data-stu-id="2f308-156">In this case, continue to the next step.</span></span>

1. <span data-ttu-id="2f308-157">A konzisztencia-ellenőrzés futtatásához nyissa meg a **Rendszeradminisztráció \> Ismétlődő feladatok \> Adatbázis \> Konzisztenciaellenőrzés** lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="2f308-157">To run the consistency check, go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="2f308-158">Az **Konzisztenciaellenőrzés** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="2f308-158">In the **Consistency check** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2f308-159">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="2f308-159">**Module:** *Warehouse management*</span></span>
    - <span data-ttu-id="2f308-160">**Ellenőrzés/javítás:** *Ellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="2f308-160">**Check/Fix:** *Check*</span></span>
    - <span data-ttu-id="2f308-161">**Kezdő dátum:** hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="2f308-161">**From date:** Leave this field blank.</span></span>
    - <span data-ttu-id="2f308-162">**A raktár helyállapotának konzisztencia-ellenőrzése:** Jelölje be ezt a jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="2f308-162">**Warehouse location status consistency check:** Select this check box.</span></span>

1. <span data-ttu-id="2f308-163">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-163">Select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="2f308-164">Üzenet jelenik meg, ha a konzisztenciaellenőrzés befejeződött.</span><span class="sxs-lookup"><span data-stu-id="2f308-164">When the consistency check is completed, you receive a notification.</span></span> <span data-ttu-id="2f308-165">Az üzenet megtekintéséhez nyissa meg a [Műveletközpontot](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications).</span><span class="sxs-lookup"><span data-stu-id="2f308-165">Open the [Action Center](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) to view the message.</span></span> <span data-ttu-id="2f308-166">A részletek megjelenítéséhez kattintson az **Üzenet részletei** gombra.</span><span class="sxs-lookup"><span data-stu-id="2f308-166">Select **Message details** to view the details.</span></span>
    >
    > <span data-ttu-id="2f308-167">Ha a konzisztencia-ellenőrzés üzenete a következőt mondja: „Helytelen hely állapot információ található a (z) XXXX helyen az XX raktárban,” újra kell futtatnia a konzisztencia-ellenőrzést.</span><span class="sxs-lookup"><span data-stu-id="2f308-167">If the message for the consistency check states, "Incorrect location status information found for location XXXX in warehouse XX," you must run the consistency check again.</span></span> <span data-ttu-id="2f308-168">Ez alkalommal állítsa be a **Ellenőrzés/javítás** mezőt *Hiba javítása* értékre.</span><span class="sxs-lookup"><span data-stu-id="2f308-168">This time, set the **Check/Fix** field to *Fix error*.</span></span> <span data-ttu-id="2f308-169">Tekintse meg az üzeneteket, hogy meggyőződjön arról, hogy a rendszer nem talált hibát.</span><span class="sxs-lookup"><span data-stu-id="2f308-169">View the messages to make sure that no errors were found.</span></span>

1. <span data-ttu-id="2f308-170">Most be kell fejeznie a helyprofil beállítását.</span><span class="sxs-lookup"><span data-stu-id="2f308-170">You must now finish setting up the location profile.</span></span> <span data-ttu-id="2f308-171">Térjen vissza a **Raktárkezelés \> Beállítások \> Raktár \> Helyprofilok** menübe, válassza ki az **5. EMELET** helyprofilt majd kattintson a műveleti panel **Szerkesztés** elemére.</span><span class="sxs-lookup"><span data-stu-id="2f308-171">Go back to **Warehouse management \> Setup \> Warehouse \> Location profiles** , select location profile **FLOOR-05** , and then, on the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="2f308-172">Az **Dimenziók** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="2f308-172">On the **Dimensions** FastTab, set the following values:</span></span>

    - <span data-ttu-id="2f308-173">**Térfogat-kihasználtság százalékos aránya:** *100*</span><span class="sxs-lookup"><span data-stu-id="2f308-173">**Volume utilization percentage:** *100*</span></span>
    - <span data-ttu-id="2f308-174">**A készlethelyhez használt térfogat-meghatározási mód:** *Hely térfogatának használata*</span><span class="sxs-lookup"><span data-stu-id="2f308-174">**Volumetric method used for inventory location:** *Use location volume*</span></span>
    - <span data-ttu-id="2f308-175">**Hely tényleges magassága:** *10*</span><span class="sxs-lookup"><span data-stu-id="2f308-175">**Actual location height:** *10*</span></span>
    - <span data-ttu-id="2f308-176">**Hely tényleges szélessége:** *10*</span><span class="sxs-lookup"><span data-stu-id="2f308-176">**Actual location width:** *10*</span></span>
    - <span data-ttu-id="2f308-177">**Hely tényleges mélysége:** *10*</span><span class="sxs-lookup"><span data-stu-id="2f308-177">**Actual location depth:** *10*</span></span>
    - <span data-ttu-id="2f308-178">**Maximális súly:** *100*</span><span class="sxs-lookup"><span data-stu-id="2f308-178">**Maximum weight:** *100*</span></span>

1. <span data-ttu-id="2f308-179">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-179">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="2f308-180">Mobileszköz menüpontjai</span><span class="sxs-lookup"><span data-stu-id="2f308-180">Mobile device menu items</span></span>

1. <span data-ttu-id="2f308-181">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="2f308-181">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="2f308-182">A művelet ablaktáblán válassza az **Új** parancsot a rendezéshez használandó menüelem létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2f308-182">On the Action Pane, select **New** to create a menu item for sorting.</span></span>
1. <span data-ttu-id="2f308-183">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="2f308-183">In the header, set the following values:</span></span>

    - <span data-ttu-id="2f308-184">**Menüelem neve:** *Korrigálás be*</span><span class="sxs-lookup"><span data-stu-id="2f308-184">**Menu item name:** *Adjust In*</span></span>
    - <span data-ttu-id="2f308-185">**Cím:** *Korrigálás be*</span><span class="sxs-lookup"><span data-stu-id="2f308-185">**Title:** *Adjust In*</span></span>
    - <span data-ttu-id="2f308-186">**Mód:** *Munka*</span><span class="sxs-lookup"><span data-stu-id="2f308-186">**Mode:** *Work*</span></span>
    - <span data-ttu-id="2f308-187">**Meglévő munka használata:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="2f308-187">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="2f308-188">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="2f308-188">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="2f308-189">**Munkalétrehozási folyamat:** *Korrigálás be*</span><span class="sxs-lookup"><span data-stu-id="2f308-189">**Work creation process:** *Adjustment in*</span></span>
    - <span data-ttu-id="2f308-190">**Készlet-helyesbítési típusok:** *Korrigálás be*</span><span class="sxs-lookup"><span data-stu-id="2f308-190">**Inventory adjustment types:** *Adjust in*</span></span>

1. <span data-ttu-id="2f308-191">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-191">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="2f308-192">Mobileszköz menü</span><span class="sxs-lookup"><span data-stu-id="2f308-192">Mobile device menu</span></span>

1. <span data-ttu-id="2f308-193">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.</span><span class="sxs-lookup"><span data-stu-id="2f308-193">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="2f308-194">A menük listáján válassza a **Készlet** elemet.</span><span class="sxs-lookup"><span data-stu-id="2f308-194">In the list of menus, select **Inventory**.</span></span>
1. <span data-ttu-id="2f308-195">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-195">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="2f308-196">A **Rendelkezésre álló menük és menüelemek** listájában keresse meg és válassza ki a **Korrigálás be** menüelemet.</span><span class="sxs-lookup"><span data-stu-id="2f308-196">In the **Available Menus And Menu Items** list, find and select the **Adjust In** menu item.</span></span>
1. <span data-ttu-id="2f308-197">Válassza a jobbra mutató nyilat a **Korrigálás be** áthelyezéséhez a **Menü struktúra** listába.</span><span class="sxs-lookup"><span data-stu-id="2f308-197">Select the right arrow button to move **Adjust In** to the **Menu Structure** list.</span></span> <span data-ttu-id="2f308-198">Ily módon hozzáadja az új menüelemet a kijelölt menühöz.</span><span class="sxs-lookup"><span data-stu-id="2f308-198">In this way, you add the new menu item to the selected menu.</span></span>
1. <span data-ttu-id="2f308-199">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-199">Select **Save**.</span></span>

### <a name="movement-types"></a><span data-ttu-id="2f308-200">Mozgástípusok</span><span class="sxs-lookup"><span data-stu-id="2f308-200">Movement types</span></span>

1. <span data-ttu-id="2f308-201">Ugorjon a **Raktárkezelés \> Beállítás \> Készlet \> Áthelyezés-típusok** pontra.</span><span class="sxs-lookup"><span data-stu-id="2f308-201">Go to **Warehouse management \> Setup \> Inventory \> Movement types**.</span></span>
1. <span data-ttu-id="2f308-202">A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="2f308-202">On the Action Pane, select **New** , and then set the following values:</span></span>

    - <span data-ttu-id="2f308-203">**Áthelyezés típuskódja:** *KONSZOLIDÁCIÓ*</span><span class="sxs-lookup"><span data-stu-id="2f308-203">**Movement type code:** *CONSOLIDATE*</span></span>
    - <span data-ttu-id="2f308-204">**Leírás:** *Helyek konszolidációja*</span><span class="sxs-lookup"><span data-stu-id="2f308-204">**Description:** *Consolidate locations*</span></span>
    - <span data-ttu-id="2f308-205">**Munkaosztály azonosítója:** *InvMov*</span><span class="sxs-lookup"><span data-stu-id="2f308-205">**Work class ID:** *InvMov*</span></span>

1. <span data-ttu-id="2f308-206">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-206">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="2f308-207">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="2f308-207">Example scenario</span></span>

<span data-ttu-id="2f308-208">A következő eset egy mobileszköz raktári alkalmazásával végez készlet *korrigálást* a raktárban lévő két helyre.</span><span class="sxs-lookup"><span data-stu-id="2f308-208">The following scenario uses the warehouse app on a mobile device to make an inventory *adjustment in* to two locations in the warehouse.</span></span>

### <a name="add-inventory-to-locations"></a><span data-ttu-id="2f308-209">Készlet hozzáadása helyekhez</span><span class="sxs-lookup"><span data-stu-id="2f308-209">Add inventory to locations</span></span>

1. <span data-ttu-id="2f308-210">Jelentkezzen be a mobileszközbe olyan felhasználóként, aki a *51*. raktárban be van állítva.</span><span class="sxs-lookup"><span data-stu-id="2f308-210">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="2f308-211">Ugrás a **Készlet \> Korrigálás be** helyre.</span><span class="sxs-lookup"><span data-stu-id="2f308-211">Go to **Inventory \> Adjust In**.</span></span>

    <span data-ttu-id="2f308-212">Ezt követően megadhatja az első helyhelyesbítést.</span><span class="sxs-lookup"><span data-stu-id="2f308-212">You will now enter the first location adjustment.</span></span>

1. <span data-ttu-id="2f308-213">Válassza ki a **Helyesbítés be** feladatot, válassza ki a helyez, amelyhez elvégzi a készlethelyesbítést.</span><span class="sxs-lookup"><span data-stu-id="2f308-213">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="2f308-214">A **HELY** mezőben válassza az *AT-001* elemet.</span><span class="sxs-lookup"><span data-stu-id="2f308-214">In the **LOC** field, select *LP-001*.</span></span>
1. <span data-ttu-id="2f308-215">Hagyja jóvá a helyet.</span><span class="sxs-lookup"><span data-stu-id="2f308-215">Confirm the location.</span></span>
1. <span data-ttu-id="2f308-216">Hozzon létre egy azonosító-azonosítót a helyhez adandó cikkhez.</span><span class="sxs-lookup"><span data-stu-id="2f308-216">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="2f308-217">Az **Azonosítótábla** mezőben adja meg a *LP00101* értéket.</span><span class="sxs-lookup"><span data-stu-id="2f308-217">In the **LP** field, enter *LP00101*.</span></span>
1. <span data-ttu-id="2f308-218">Az azonosítótábla jóváhagyása.</span><span class="sxs-lookup"><span data-stu-id="2f308-218">Confirm the license plate.</span></span>
1. <span data-ttu-id="2f308-219">Az azonosítótáblához hozzáadandó elem megadása.</span><span class="sxs-lookup"><span data-stu-id="2f308-219">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="2f308-220">Az **ITEM** mezőben adja meg a *M9201* értéket.</span><span class="sxs-lookup"><span data-stu-id="2f308-220">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="2f308-221">Erősítse meg a cikket.</span><span class="sxs-lookup"><span data-stu-id="2f308-221">Confirm the item.</span></span>
1. <span data-ttu-id="2f308-222">Az azonosítótáblához hozzáadandó mennyiség megadása.</span><span class="sxs-lookup"><span data-stu-id="2f308-222">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="2f308-223">A **MENNY** mezőben adja meg a *10* értéket.</span><span class="sxs-lookup"><span data-stu-id="2f308-223">In the **QTY** field, enter *10*.</span></span>
1. <span data-ttu-id="2f308-224">Nyugtázza a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-224">Confirm the quantity.</span></span>

    <span data-ttu-id="2f308-225">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="2f308-225">You receive a "Work Completed" message.</span></span> <span data-ttu-id="2f308-226">Ezt követően megadhatja a második helyhelyesbítést.</span><span class="sxs-lookup"><span data-stu-id="2f308-226">You will now enter the second location adjustment.</span></span>

1. <span data-ttu-id="2f308-227">Válassza ki a **Helyesbítés be** feladatot, válassza ki a helyez, amelyhez elvégzi a készlethelyesbítést.</span><span class="sxs-lookup"><span data-stu-id="2f308-227">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="2f308-228">z **HELY** mezőben válassza az *AT-002* elemet.</span><span class="sxs-lookup"><span data-stu-id="2f308-228">In the **LOC** field, select *LP-002*.</span></span>
1. <span data-ttu-id="2f308-229">Hagyja jóvá a helyet.</span><span class="sxs-lookup"><span data-stu-id="2f308-229">Confirm the location.</span></span>
1. <span data-ttu-id="2f308-230">Hozzon létre egy azonosító-azonosítót a helyhez adandó cikkhez.</span><span class="sxs-lookup"><span data-stu-id="2f308-230">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="2f308-231">Az **Azonosítótábla** mezőben adja meg a *LP00201* értéket.</span><span class="sxs-lookup"><span data-stu-id="2f308-231">In the **LP** field, enter *LP00201*.</span></span>
1. <span data-ttu-id="2f308-232">Az azonosítótábla jóváhagyása.</span><span class="sxs-lookup"><span data-stu-id="2f308-232">Confirm the license plate.</span></span>
1. <span data-ttu-id="2f308-233">Az azonosítótáblához hozzáadandó elem megadása.</span><span class="sxs-lookup"><span data-stu-id="2f308-233">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="2f308-234">Az **ITEM** mezőben adja meg a *M9201* értéket.</span><span class="sxs-lookup"><span data-stu-id="2f308-234">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="2f308-235">Erősítse meg a cikket.</span><span class="sxs-lookup"><span data-stu-id="2f308-235">Confirm the item.</span></span>
1. <span data-ttu-id="2f308-236">Az azonosítótáblához hozzáadandó mennyiség megadása.</span><span class="sxs-lookup"><span data-stu-id="2f308-236">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="2f308-237">A **MENNY** mezőben adja meg a *15* értéket.</span><span class="sxs-lookup"><span data-stu-id="2f308-237">In the **QTY** field, enter *15*.</span></span>
1. <span data-ttu-id="2f308-238">Nyugtázza a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-238">Confirm the quantity.</span></span>

    <span data-ttu-id="2f308-239">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="2f308-239">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="2f308-240">Válassza ki a lap tetején látható Menü gombot (néha hamburgernek vagy a hamburgergombnak is nevezik), majd válassza ki a **Mégse** lehetőséget a **Korrekció itt:** feladatból való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="2f308-240">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit the **Adjustment in** task.</span></span>

### <a name="consolidate-locations"></a><span data-ttu-id="2f308-241">Helyek konszolidálása</span><span class="sxs-lookup"><span data-stu-id="2f308-241">Consolidate locations</span></span>

1. <span data-ttu-id="2f308-242">Ugrás a **Raktárkezelés \> Ismétlődő feladatok \> Cikkek konszolidációja** helyre.</span><span class="sxs-lookup"><span data-stu-id="2f308-242">Go to **Warehouse management \> Periodic tasks \> Item consolidation**.</span></span>
1. <span data-ttu-id="2f308-243">A fejlécben válassza ki azt a raktárt, amelybe a konszolidálást el szeretné végezni.</span><span class="sxs-lookup"><span data-stu-id="2f308-243">In the header, select a warehouse to do the consolidation for.</span></span> <span data-ttu-id="2f308-244">A **Raktár** mezőben adja meg az *51* értéket.</span><span class="sxs-lookup"><span data-stu-id="2f308-244">In the **Warehouse** field, enter *51*.</span></span>

    <span data-ttu-id="2f308-245">Egy rekord jelenik meg minden olyan helyen, ahol az *M9201* cikket helyesbítették.</span><span class="sxs-lookup"><span data-stu-id="2f308-245">A record is shown for each location where item *M9201* was adjusted.</span></span> <span data-ttu-id="2f308-246">A **Kihasználtság százalékos aránya** oszlopa az egyes helyek térfogat szerinti kihasználtságát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="2f308-246">The **Utilization percentage** column shows the volumetric utilization of each location.</span></span>

1. <span data-ttu-id="2f308-247">A készlet konszolidálásához válassza ki az összes olyan helyet, amelyet konszolidálni kell, majd a műveleti ablaktáblán válassza ki a **Készlet konszolidálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-247">To consolidate inventory, select all the locations that must be consolidated, and then, on the Action Pane, select **Consolidate Inventory**.</span></span>
1. <span data-ttu-id="2f308-248">A **Készlet konszolidálása** párbeszédpanelen adja meg azt a helyet és áthelyezési típust, amelyet a készlet-áthelyezési munka létrehozásához kell használni.</span><span class="sxs-lookup"><span data-stu-id="2f308-248">In the **Consolidate inventory** dialog box, specify the location and movement type that should be used to create the work for inventory movement.</span></span> <span data-ttu-id="2f308-249">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="2f308-249">Set the following values:</span></span>

    - <span data-ttu-id="2f308-250">**Hely:** *AT-001*</span><span class="sxs-lookup"><span data-stu-id="2f308-250">**Location:** *LP-001*</span></span>
    - <span data-ttu-id="2f308-251">**Áthelyezés típuskódja:** *KONSZOLIDÁCIÓ*</span><span class="sxs-lookup"><span data-stu-id="2f308-251">**Movement type code:** *CONSOLIDATE*</span></span>

1. <span data-ttu-id="2f308-252">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2f308-252">Select **OK**.</span></span>
1. <span data-ttu-id="2f308-253">Olyan tájékoztató üzenet érkezik, amely az adott kiadásból létrehozott áthelyezési munkát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="2f308-253">You receive an informational message that shows the movement work that was created.</span></span> <span data-ttu-id="2f308-254">Jegyezze fel az áthelyezési munka azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="2f308-254">Make a note of the movement work ID.</span></span>

### <a name="view-movement-work"></a><span data-ttu-id="2f308-255">Áthelyezési munka megtekintése</span><span class="sxs-lookup"><span data-stu-id="2f308-255">View movement work</span></span>

1. <span data-ttu-id="2f308-256">Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.</span><span class="sxs-lookup"><span data-stu-id="2f308-256">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="2f308-257">A létrehozott áthelyezési munka megtekintése.</span><span class="sxs-lookup"><span data-stu-id="2f308-257">View the work that was created.</span></span> <span data-ttu-id="2f308-258">A készlet-konszolidáció áthelyezésimunka-azonosítójának használatával szűrhet vagy kereshet a munkarácson.</span><span class="sxs-lookup"><span data-stu-id="2f308-258">Use the movement work ID from the inventory consolidation to filter or search the work grid.</span></span>

    <span data-ttu-id="2f308-259">Ebben a helyzetben egy létező, már készlettel rendelkező hely volt használva a készlet-konszolidáció helyének.</span><span class="sxs-lookup"><span data-stu-id="2f308-259">In this scenario, an existing location that had inventory was used as the inventory consolidation location.</span></span> <span data-ttu-id="2f308-260">Ennélfogva csak egy munkaazonosító jött létre.</span><span class="sxs-lookup"><span data-stu-id="2f308-260">Therefore, only one work ID was created.</span></span>

    > [!NOTE]
   > <span data-ttu-id="2f308-261">A rendszer minden lépéshez létrehoz egy munkaazonosítót, amelyet végre kell hajtani.</span><span class="sxs-lookup"><span data-stu-id="2f308-261">The system creates one work ID for each move that must be completed.</span></span> <span data-ttu-id="2f308-262">Ha olyan helyet ad meg, amely már tartalmaz készletet, csak egy munkaazonosító jön létre.</span><span class="sxs-lookup"><span data-stu-id="2f308-262">If you specify a location that already contains inventory, only one work ID is created.</span></span> <span data-ttu-id="2f308-263">Ha új helyet ad meg, akkor két munkaazonosító jön létre.</span><span class="sxs-lookup"><span data-stu-id="2f308-263">If you specify a new location, two work IDs are created.</span></span>
