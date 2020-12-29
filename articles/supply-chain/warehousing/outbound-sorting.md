---
title: Kimenő rendezés
description: Ez a témakör a kimenő rendezéssel kapcsolatban tartalmaz információkat. Ez a funkció megkönnyíti a kis tárolók kezelését, és segíti a raktári dolgozóknak a raklap-kapacitás jobb rendezését a kamionban.
author: Mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 84c4ec83ed16762e6c3c1a22425cf60e5b3ae8da
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429938"
---
# <a name="outbound-sorting"></a><span data-ttu-id="683be-104">Kimenő rendezés</span><span class="sxs-lookup"><span data-stu-id="683be-104">Outbound sorting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="683be-105">Ez a funkció megkönnyíti a kis tárolók kezelését, és segíti a raktári dolgozóknak a raklap-kapacitás jobb rendezését a kamionban.</span><span class="sxs-lookup"><span data-stu-id="683be-105">This functionality makes it easier to handle small containers and helps warehouse workers better plan and organize pallet capacity in the truck.</span></span> <span data-ttu-id="683be-106">Ha a kimenő rendezést használja, akkor a csomagolt tárolókat a megfelelő raklapra rendezheti, miután áthaladtak a csomagolóállomáson.</span><span class="sxs-lookup"><span data-stu-id="683be-106">When you use outbound sorting, you can sort packed containers to the correct pallet after they have been at a packing station.</span></span> <span data-ttu-id="683be-107">A csomagolási hierarchiát is létre lehet hozni.</span><span class="sxs-lookup"><span data-stu-id="683be-107">You can also build a packing hierarchy.</span></span>

<span data-ttu-id="683be-108">Ez a funkció lehetővé teszi raklapok összeállítását a csomagolási funkcióval csomagolt tárolókból.</span><span class="sxs-lookup"><span data-stu-id="683be-108">This functionality lets you build pallets from containers that are packed through the packing functionality.</span></span> <span data-ttu-id="683be-109">A tároló nem lesz elküldve a végső szállítási helyre, mivel az eredeti csomagolási folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="683be-109">The container isn't sent to the final shipping location as it is in the original packing flow.</span></span> <span data-ttu-id="683be-110">Helyette a dolgozók le tudják zárni a tárolót, és át lehet helyezni egy rendezés típusú helyre.</span><span class="sxs-lookup"><span data-stu-id="683be-110">Instead, workers can close the container and move it to a sort type location.</span></span> <span data-ttu-id="683be-111">Ezután a konténereket a pozíciókra rendezhetik, amelyek mindegyikének van egy azonosítótáblája (AT).</span><span class="sxs-lookup"><span data-stu-id="683be-111">They can then sort containers to positions, each of which has a license plate (LP).</span></span> <span data-ttu-id="683be-112">Miután a tárolók rendezése megtörtént, a munka létrehozható úgy, hogy az egész azonosítótáblát elküldje a végső szállítási dokknak vagy fázishelyeknek a helyutasítások vagy a saját követelményei alapján.</span><span class="sxs-lookup"><span data-stu-id="683be-112">After the containers have been sorted, work can be created to send the whole LP to the final shipping dock or stage locations, based on location directives or your own requirements.</span></span> <span data-ttu-id="683be-113">Ezenkívül a rendezési pozíció lezárásának művelete azonnal áthelyezheti a készletet a végső szállítási helyre, és kitárolhatja a rendelésbe.</span><span class="sxs-lookup"><span data-stu-id="683be-113">Additionally, the action of closing of the sort position can immediately move the inventory to the final shipping location and pick it to the order.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="683be-114">A Kimenő rendezés funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="683be-114">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="683be-115">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="683be-115">Before you can use the feature, it must be turned on in your system.</span></span> <span data-ttu-id="683be-116">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="683be-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="683be-117">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="683be-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="683be-118">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="683be-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="683be-119">**Szolgáltatás neve:** *Kimenő rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-119">**Feature name:** *Outbound sorting*</span></span>

## <a name="setup"></a><span data-ttu-id="683be-120">Beállítás</span><span class="sxs-lookup"><span data-stu-id="683be-120">Setup</span></span>

<span data-ttu-id="683be-121">Ehhez a helyzethez normál **USMF** demóadatokat és a *62-es* raktárat kell használni.</span><span class="sxs-lookup"><span data-stu-id="683be-121">For this scenario, you must use standard **USMF** demo data and warehouse *62*.</span></span> <span data-ttu-id="683be-122">A következő alszakaszokban ismertetett beállításokat is végre kell hajtania.</span><span class="sxs-lookup"><span data-stu-id="683be-122">You must also complete the setup that is described in the following subsections.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="683be-123">Állítsa be a hullámsablon lehetőséget</span><span class="sxs-lookup"><span data-stu-id="683be-123">Set up a wave template</span></span>

<span data-ttu-id="683be-124">Ez a beállítás automatikusan feldolgozza a hullámot és létrehozza a munkát, valahányszor egy sor kiadásra kerül a raktárba.</span><span class="sxs-lookup"><span data-stu-id="683be-124">This setup automatically processes the wave and creates work when a line is released to the warehouse.</span></span>

1. <span data-ttu-id="683be-125">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="683be-125">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="683be-126">A sablonban válassza ki a **62-es raktárat**.</span><span class="sxs-lookup"><span data-stu-id="683be-126">In the template list, select **Warehouse 62**.</span></span>
1. <span data-ttu-id="683be-127">Győződjön meg arról , hogy az **Általános** gyorslapon a **Hullám feldolgozása a raktárba történő kiadáskor** beállítás értéke *Igen* legyen.</span><span class="sxs-lookup"><span data-stu-id="683be-127">On the **General** FastTab, make sure that the **Process wave at release to warehouse** option is set to *Yes*.</span></span>

### <a name="set-up-a-worker"></a><span data-ttu-id="683be-128">Dolgozó beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-128">Set up a worker</span></span>

<span data-ttu-id="683be-129">A csomagoló állomás helynek számít.</span><span class="sxs-lookup"><span data-stu-id="683be-129">The packing station is considered a location.</span></span> <span data-ttu-id="683be-130">Azok a raktári dolgozók, akik bejelentkeznek a csomagolóállomáson, csak az adott csomagolási helyen tervezett szállítmányokat és tárolókat láthatják, és csak azokon dolgoznak.</span><span class="sxs-lookup"><span data-stu-id="683be-130">Warehouse workers who sign in at the packing station see and work on only shipments and containers that are planned at that specific packing location.</span></span> <span data-ttu-id="683be-131">Azt a felhasználót, aki bejelentkezik a Microsoft Dynamics 365-be dolgozóként kell beállítani a Raktárkezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="683be-131">A user who signs in to Microsoft Dynamics 365 must be set up as a worker in Warehouse management.</span></span> <span data-ttu-id="683be-132">Ha a felhasználó neve nem jelenik meg a dolgozó felhasználók listájában, a következő eljárással adja hozzá.</span><span class="sxs-lookup"><span data-stu-id="683be-132">If the user's name doesn't appear in the list of work users, use the following procedure to add it.</span></span>

> [!NOTE]
> <span data-ttu-id="683be-133">A lépések feltételezik, hogy a felhasználó már létezik a rendszerben, és a **Humán erőforrás** modulban alkalmazottként vagy dolgozóként van társítva.</span><span class="sxs-lookup"><span data-stu-id="683be-133">These steps assume that the user already exists in the system and has been associated as an employee or worker in the **Human Resources** module.</span></span>

1. <span data-ttu-id="683be-134">Ugrás a **Raktárkezelés \> Beállítás \> Dolgozó** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-134">Go to **Warehouse management \> Setup \> Worker**.</span></span>
1. <span data-ttu-id="683be-135">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-135">Select **New**.</span></span>
1. <span data-ttu-id="683be-136">A **Dolgozó** mezőben válassza ki a célfelhasználót az alkalmazottak listájából.</span><span class="sxs-lookup"><span data-stu-id="683be-136">In the **Worker** field, select the target user in the list of employees.</span></span>
1. <span data-ttu-id="683be-137">Válassza ki a **Kiválasztás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-137">Select **Select**.</span></span>
1. <span data-ttu-id="683be-138">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-138">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="683be-139">A **Felhasználók** gyorslap **Új** elemét választva, hozzon létre egy mobileszköz-fiókot, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-139">On the **Users** FastTab, select **New** to create a mobile device account, and set the following values for it:</span></span>

    - <span data-ttu-id="683be-140">**Felhasználó azonosítója:** Adjon meg egy egyedi azonosítót.</span><span class="sxs-lookup"><span data-stu-id="683be-140">**User ID:** Enter a unique ID.</span></span>
    - <span data-ttu-id="683be-141">**Felhasználónév:** Adja meg az azonosító nevét.</span><span class="sxs-lookup"><span data-stu-id="683be-141">**User name:** Enter a name for the ID.</span></span>
    - <span data-ttu-id="683be-142">**Alapértelmezett raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="683be-142">**Default warehouse:** *62*</span></span>
    - <span data-ttu-id="683be-143">**Menü neve:** *Fő*</span><span class="sxs-lookup"><span data-stu-id="683be-143">**Menu name:** *Main*</span></span>

1. <span data-ttu-id="683be-144">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-144">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="683be-145">Megjelenik a **Jelszó beállítása** párbeszédpanel, amelyen létrehozhatja azt az egyszerű jelszót, amellyel a felhasználó bejelentkezhet a mobilalkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="683be-145">The **Set password** dialog box appears, where you can create a simple password that the user can use to sign in to the mobile app.</span></span> <span data-ttu-id="683be-146">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-146">Set the following values:</span></span>

    - <span data-ttu-id="683be-147">**Jelszó:** Adjon meg egy egyszerű jelszót.</span><span class="sxs-lookup"><span data-stu-id="683be-147">**Password:** Enter a simple password.</span></span>
    - <span data-ttu-id="683be-148">**Jelszó megerősítése:** Adja meg újra ugyanazt a jelszót.</span><span class="sxs-lookup"><span data-stu-id="683be-148">**Confirm password:** Enter the same password again.</span></span>

1. <span data-ttu-id="683be-149">Válassza ki a **Jelszó beállítása** opciót.</span><span class="sxs-lookup"><span data-stu-id="683be-149">Select **Set password**.</span></span>

    <span data-ttu-id="683be-150">A Műveletközpont értesítése tájékoztatja arról, hogy a jelszó be van állítva a létrehozott felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="683be-150">A notification in the Action Center informs you that the password has been set for the user that you created.</span></span>

### <a name="create-a-location-type"></a><span data-ttu-id="683be-151">Helytípus létrehozása</span><span class="sxs-lookup"><span data-stu-id="683be-151">Create a location type</span></span>

1. <span data-ttu-id="683be-152">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helytípusok** pontra.</span><span class="sxs-lookup"><span data-stu-id="683be-152">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="683be-153">A műveleti ablaktáblán válassza az **Új** parancsot egy helytípus létrehozásához, és állítsa be a következő értékeket hozzá:</span><span class="sxs-lookup"><span data-stu-id="683be-153">On the Action Pane, select **New** to create a location type, and set the following values for it:</span></span>

    - <span data-ttu-id="683be-154">**Hely típusa:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="683be-154">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="683be-155">**Leírás:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-155">**Description:** *Sort*</span></span>

1. <span data-ttu-id="683be-156">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-156">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="683be-157">Raktárkezelési paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-157">Set up Warehouse management parameters</span></span>

1. <span data-ttu-id="683be-158">Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.</span><span class="sxs-lookup"><span data-stu-id="683be-158">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="683be-159">Az **Általános** lap **Helytípusok** gyorslapján állítsa be a **Rendezési hely típusa** mezőt *SORT* értékre.</span><span class="sxs-lookup"><span data-stu-id="683be-159">On the **General** tab, on the **Location types** FastTab, set the **Sorting location type** field to *SORT*.</span></span>
1. <span data-ttu-id="683be-160">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-160">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-location-profile"></a><span data-ttu-id="683be-161">Helyprofil beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-161">Set up a location profile</span></span>

1. <span data-ttu-id="683be-162">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.</span><span class="sxs-lookup"><span data-stu-id="683be-162">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="683be-163">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-163">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="683be-164">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-164">In the header, set the following values:</span></span>

    - <span data-ttu-id="683be-165">**Helyprofil azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-165">**Location profile ID:** *Sorting*</span></span>
    - <span data-ttu-id="683be-166">**Név:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-166">**Name:** *Sorting*</span></span>

1. <span data-ttu-id="683be-167">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-167">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="683be-168">**Hely formátuma:** *ASRB* (folyosó, állvány, polc és rekesz)</span><span class="sxs-lookup"><span data-stu-id="683be-168">**Location format:** *ASRB* (Aisle-Rack-Shelf-Bin)</span></span>
    - <span data-ttu-id="683be-169">**Hely típusa:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="683be-169">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="683be-170">**Azonosítótábla-követés használata:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="683be-170">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="683be-171">**Vegyes cikkek engedélyezése:** *Igen* (a beállítás *Igen* értékre állítása esetén a **Vegyes készlet kötegek engedélyezése** beállítás automatikusan *Igen* értékre van állítva, és nem lehet függetlenül módosítani.)</span><span class="sxs-lookup"><span data-stu-id="683be-171">**Allow mixed items:** *Yes* (When you set this option to *Yes*, the **Allow mixed inventory batches** option is automatically set to *Yes* and can't be changed independently.)</span></span>

1. <span data-ttu-id="683be-172">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-172">Select **Save**.</span></span>

### <a name="set-up-a-location"></a><span data-ttu-id="683be-173">Hely beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-173">Set up a location</span></span>

1. <span data-ttu-id="683be-174">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyek pontra**.</span><span class="sxs-lookup"><span data-stu-id="683be-174">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="683be-175">A fejlécben törölje a jelet az **Ellenőrző számjegyek létrehozása a helyhez** jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="683be-175">In the header, clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="683be-176">A műveleti ablaktáblán válassza az **Új** parancsot egy hely létrehozásához, és állítsa be a következő értékeket hozzá:</span><span class="sxs-lookup"><span data-stu-id="683be-176">On the Action Pane, select **New** to create a location, and set the following values for it:</span></span>

    - <span data-ttu-id="683be-177">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="683be-177">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="683be-178">**Hely:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="683be-178">**Location:** *SORT*</span></span>
    - <span data-ttu-id="683be-179">**Helyprofil azonosítója:** *SORTING*</span><span class="sxs-lookup"><span data-stu-id="683be-179">**Location profile ID:** *SORTING*</span></span>

1. <span data-ttu-id="683be-180">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-180">Select **Save**.</span></span>

### <a name="set-up-an-outbound-sorting-template"></a><span data-ttu-id="683be-181">Kimenő rendezési sablon beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-181">Set up an outbound sorting template</span></span>

<span data-ttu-id="683be-182">A kimenő rendezési sablon határozza meg, hogy a munka a rendezési hely alapján jön-e létre, és hogy a rendezés kézzel vagy automatikusan történik-e.</span><span class="sxs-lookup"><span data-stu-id="683be-182">The outbound sorting template determines whether work is created out of the sort location, and whether sorting is done manually or automatically.</span></span>

<span data-ttu-id="683be-183">Ehhez a forgatókönyvhöz létrehoz egy kimenő rendezési sablont, amely a raklapok összekészítéséhez szükséges a csomagolási állomás után.</span><span class="sxs-lookup"><span data-stu-id="683be-183">For this scenario, you will create an outbound sorting template to build pallets after the packing station.</span></span>

1. <span data-ttu-id="683be-184">Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Kimenő rendezési sablonok** helyre.</span><span class="sxs-lookup"><span data-stu-id="683be-184">Go to **Warehouse Management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="683be-185">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-185">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="683be-186">Az új sablon fejlécében adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-186">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="683be-187">**Kimenő rendezési sablon azonosítója:** *AutoWork*</span><span class="sxs-lookup"><span data-stu-id="683be-187">**Outbound sorting template ID:** *AutoWork*</span></span>
    - <span data-ttu-id="683be-188">**Leírás:** *Automatikus munkalétrehozás*</span><span class="sxs-lookup"><span data-stu-id="683be-188">**Description:** *Auto Work Creation*</span></span>
    - <span data-ttu-id="683be-189">**Kimenő rendezési sablon típusa:** *Tároló*</span><span class="sxs-lookup"><span data-stu-id="683be-189">**Outbound sorting template type:** *Container*</span></span>
    - <span data-ttu-id="683be-190">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="683be-190">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="683be-191">**Hely:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="683be-191">**Location:** *SORT*</span></span>

1. <span data-ttu-id="683be-192">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-192">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="683be-193">**Rendezés ellenőrzés:** *Pozíció beolvasása*</span><span class="sxs-lookup"><span data-stu-id="683be-193">**Sort verification:** *Position scan*</span></span>
    - <span data-ttu-id="683be-194">**Munka létrehozása a pozíció lezárásakor:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="683be-194">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="683be-195">Ha ennek a beállításnak az értéke *Igen* akkor munka jön létre, amikor a pozíció le van zárva, hogy a készletet a végső szállítási helyre mozgassák.</span><span class="sxs-lookup"><span data-stu-id="683be-195">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="683be-196">Ha *Nem* értékre van állítva, akkor a készletet azonnal kitárolják a rendeléshez a pozíció lezárásakor.</span><span class="sxs-lookup"><span data-stu-id="683be-196">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="683be-197">**Pozíció hozzárendelése:** *Automatikus*</span><span class="sxs-lookup"><span data-stu-id="683be-197">**Position assignment:** *Automatic*</span></span>

        <span data-ttu-id="683be-198">Ha a mező értéke *Manuális* akkor a felhasználónak mindig meg kell adnia, a készlet melyik pozíciójához kell rendezni.</span><span class="sxs-lookup"><span data-stu-id="683be-198">If this field is set to *Manual*, the user must always indicate which position the inventory should be sorted to.</span></span> <span data-ttu-id="683be-199">Ha értéke *Automatikus*, akkor a rendszer automatikusan egy pozícióhoz irányítja a készletet, ha lehetséges, a rendezési sablontörések alapján.</span><span class="sxs-lookup"><span data-stu-id="683be-199">If it's set to *Automatic*, the system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

1. <span data-ttu-id="683be-200">Válassza a **Mentés** parancsot, hogy a **Lekérdezés szerkesztése** gomb elérhető legyen a Műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="683be-200">Select **Save** to make the **Edit query** button on the Action Pane available.</span></span>
1. <span data-ttu-id="683be-201">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-201">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="683be-202">A lekérdezés-szerkesztőben, a **Rendezés** lapon adjon hozzá egy sort a következő értékekkel:</span><span class="sxs-lookup"><span data-stu-id="683be-202">In the query editor, on the **Sorting** tab, add a line that has the following values:</span></span>

    - <span data-ttu-id="683be-203">**Tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="683be-203">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="683be-204">**Származtatott tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="683be-204">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="683be-205">**Mező:** *Szállítmányozói szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="683be-205">**Field:** *Carrier service*</span></span>

        <span data-ttu-id="683be-206">Amikor kiválasztotta ezt az értéket, a következő üzenet jelenhet meg: „A Szállítmányozói szolgáltatás nem egy indexmező.</span><span class="sxs-lookup"><span data-stu-id="683be-206">When you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="683be-207">Szeretne rendezést hozzáadni?”</span><span class="sxs-lookup"><span data-stu-id="683be-207">Do you want to add sorting on this?"</span></span> <span data-ttu-id="683be-208">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-208">Select **Yes**.</span></span>

    - <span data-ttu-id="683be-209">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="683be-209">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="683be-210">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-210">Select **OK**.</span></span>
1. <span data-ttu-id="683be-211">A következő üzenet jelenhet meg: „A csoportosítás alaphelyzetbe kerül, folytatja?”</span><span class="sxs-lookup"><span data-stu-id="683be-211">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="683be-212">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-212">Select **Yes**.</span></span>

    <span data-ttu-id="683be-213">Elérhetővé válik a **A kimenő rendezési sablonok szünetei** gomb a műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="683be-213">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="683be-214">A műveleti ablaktáblán válassza ki a **Kimenő rendezési sablon szünetekei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-214">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="683be-215">Az **Kimenő rendezési kritérium** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-215">In the **Outbound sorting criteria** dialog box, set the following values:</span></span>

    - <span data-ttu-id="683be-216">**Hivatkozási tábla neve:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="683be-216">**Reference table name:** *Shipments*</span></span>
    - <span data-ttu-id="683be-217">**Hivatkozási mező neve:** *Szállítmányozó szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="683be-217">**Reference field name:** *Carrier service*</span></span>
    - <span data-ttu-id="683be-218">**Csoportosítás mező szerint:** Jelölje be ezt a jelölőnégyzetet, ha a szállításokat szállítmányozó szolgáltatás szerint szeretné csoportosítani.</span><span class="sxs-lookup"><span data-stu-id="683be-218">**Group by field:** Select this check box to group shipments by carrier service.</span></span>

1. <span data-ttu-id="683be-219">Az **OK** gombra kattintva mentse a beállításokat, és zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="683be-219">Select **OK** to save your settings and close the dialog box.</span></span>

### <a name="set-up-container-packing-policies"></a><span data-ttu-id="683be-220">Konténerek csomagolási házirendjeinek beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-220">Set up container packing policies</span></span>

1. <span data-ttu-id="683be-221">Ugorjon a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolócsomagolási házirendek** pontra.</span><span class="sxs-lookup"><span data-stu-id="683be-221">Go to **Warehouse management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="683be-222">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-222">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="683be-223">Az új házirend fejlécében adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-223">In the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="683be-224">**Konténer csomagolási irányelve:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-224">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="683be-225">**Leírás:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-225">**Description:** *Sort*</span></span>

1. <span data-ttu-id="683be-226">Az **Áttekintés** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-226">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="683be-227">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="683be-227">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="683be-228">**A rendezés alapértelmezett helye:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="683be-228">**Default location for sorting:** *SORT*</span></span>
    - <span data-ttu-id="683be-229">**Tömegegység:** *kg*</span><span class="sxs-lookup"><span data-stu-id="683be-229">**Weight unit:** *kg*</span></span>
    - <span data-ttu-id="683be-230">**Tároló záró irányelve:** *Automatikus kiadás*</span><span class="sxs-lookup"><span data-stu-id="683be-230">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="683be-231">**Tároló felszabadítási irányelve:** *Tároló hozzárendelése a kimenő rendezési pozícióhoz*</span><span class="sxs-lookup"><span data-stu-id="683be-231">**Container release policy:** *Assign container to outbound sorting position*</span></span>

1. <span data-ttu-id="683be-232">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-232">Select **Save**.</span></span>

### <a name="set-up-packing-profiles"></a><span data-ttu-id="683be-233">Csomagolási profilok beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-233">Set up packing profiles</span></span>

<span data-ttu-id="683be-234">Hozzon létre egy új csomagolási profilt, amelyet a rendezési funkcióval együtt használni fog.</span><span class="sxs-lookup"><span data-stu-id="683be-234">Create a new packing profile that will be used together with the sorting functionality.</span></span>

1. <span data-ttu-id="683be-235">Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Csomagolási profilok** pontra.</span><span class="sxs-lookup"><span data-stu-id="683be-235">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="683be-236">A műveleti ablaktáblán válassza az **Új** parancsot egy sor létrehozásához, és állítsa be a következő értékeket hozzá:</span><span class="sxs-lookup"><span data-stu-id="683be-236">On the Action Pane, select **New** to create a line, and set the following values for it:</span></span>

    - <span data-ttu-id="683be-237">**Csomagolási profil azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-237">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="683be-238">**Leírás:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-238">**Description:** *Sort*</span></span>
    - <span data-ttu-id="683be-239">**Konténer csomagolási irányelve:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-239">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="683be-240">**Tároló-azonosító mód:** *Automatikus*</span><span class="sxs-lookup"><span data-stu-id="683be-240">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="683be-241">**Tároló típusa:** *Nagyméretű doboz*</span><span class="sxs-lookup"><span data-stu-id="683be-241">**Container type:** *Box-Large*</span></span>
    - <span data-ttu-id="683be-242">**Tároló automatikus létrehozása a tároló lezárásakor:** Törölve (= *Nem*)</span><span class="sxs-lookup"><span data-stu-id="683be-242">**Auto create container at container close:** Cleared (= *No*)</span></span>

1. <span data-ttu-id="683be-243">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-243">Select **Save**.</span></span>

### <a name="set-up-work-classes"></a><span data-ttu-id="683be-244">Munkaosztályok beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-244">Set up work classes</span></span>

<span data-ttu-id="683be-245">A rendezéssel együtt használt munkaosztály beállítása.</span><span class="sxs-lookup"><span data-stu-id="683be-245">Set up a work class that will be used together with sorting.</span></span>

1. <span data-ttu-id="683be-246">Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.</span><span class="sxs-lookup"><span data-stu-id="683be-246">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="683be-247">A műveleti ablaktáblán válassza az **Új** parancsot egy munkaosztály létrehozásához a rendeléshez, és állítsa be a következő értékeket hozzá:</span><span class="sxs-lookup"><span data-stu-id="683be-247">On the Action Pane, select **New** to create a work class for sorting, and set the following values for it:</span></span>

    - <span data-ttu-id="683be-248">**Munkaosztály azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-248">**Work class ID:** *Sort*</span></span>
    - <span data-ttu-id="683be-249">**Leírás:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-249">**Description:** *Sort*</span></span>
    - <span data-ttu-id="683be-250">**Munkarendelés típusa:** *Rendezett készletkitárolás*</span><span class="sxs-lookup"><span data-stu-id="683be-250">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="683be-251">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-251">Select **Save**.</span></span>

### <a name="set-up-mobile-device-menu-items"></a><span data-ttu-id="683be-252">Mobileszköz-menüelemek beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-252">Set up mobile device menu items</span></span>

#### <a name="set-up-a-new-pallet-menu-item"></a><span data-ttu-id="683be-253">Új raklap menüelem beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-253">Set up a new pallet menu item</span></span>

<span data-ttu-id="683be-254">Hozzon létre egy mobileszköz menüelemet, amely a rendezés során felépíti a raklapokat.</span><span class="sxs-lookup"><span data-stu-id="683be-254">Create a mobile device menu item to build pallets during sorting.</span></span>

1. <span data-ttu-id="683be-255">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="683be-255">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="683be-256">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-256">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="683be-257">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-257">In the header, set the following values:</span></span>

    - <span data-ttu-id="683be-258">**Menüelem neve:** *Raklap-összeállítás*</span><span class="sxs-lookup"><span data-stu-id="683be-258">**Menu item name:** *Pallet build*</span></span>
    - <span data-ttu-id="683be-259">**Cím:** *Raklap-összeállítás*</span><span class="sxs-lookup"><span data-stu-id="683be-259">**Title:** *Pallet build*</span></span>
    - <span data-ttu-id="683be-260">**Mód:** *Közvetett*</span><span class="sxs-lookup"><span data-stu-id="683be-260">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="683be-261">**Meglévő munka használata:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="683be-261">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="683be-262">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-262">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="683be-263">**Tevékenységkód:** *Kimenő rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-263">**Activity code:** *Outbound sorting*</span></span>

        <span data-ttu-id="683be-264">Ha ez a mező *Kimenő rendezés* értékre van állítva, akkor a **Kimenő rendezési sablon azonosítója** mező jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="683be-264">When this field is set to *Outbound sorting*, the **Outbound sorting template ID** field is shown.</span></span>

    - <span data-ttu-id="683be-265">**Folyamat-útmutató használata:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="683be-265">**Use process guide:** *Yes*</span></span>

        <span data-ttu-id="683be-266">Ha a **Tevékenységkódja** mező a *Kimenő rendezés* értékre van állítva , akkor ez a beállítás automatikusan *Igen* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="683be-266">When the **Activity code** field is set to *Outbound sorting*, this option is automatically set to *Yes*.</span></span>

    - <span data-ttu-id="683be-267">**Kimenő rendezési sablon azonosítója:** *AutoWork*</span><span class="sxs-lookup"><span data-stu-id="683be-267">**Outbound sorting template ID:** *AutoWork*</span></span>

1. <span data-ttu-id="683be-268">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-268">Select **Save**.</span></span>

#### <a name="set-up-a-new-loading-menu-item"></a><span data-ttu-id="683be-269">Új rakodási menüelem beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-269">Set up a new loading menu item</span></span>

<span data-ttu-id="683be-270">Ezután hozzon létre egy menüelemet, amely lehetővé teszi, hogy a felhasználók a kiválasztott készletcikkeket áthelyezzék a szállítási helyre.</span><span class="sxs-lookup"><span data-stu-id="683be-270">Next, create a menu item that lets users move the sorted inventory items to the shipping location.</span></span>

1. <span data-ttu-id="683be-271">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="683be-271">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="683be-272">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-272">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="683be-273">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-273">In the header, set the following values:</span></span>

    - <span data-ttu-id="683be-274">**Menüelem neve:** *Rakomány rendezésből*</span><span class="sxs-lookup"><span data-stu-id="683be-274">**Menu item name:** *Load from Sorting*</span></span>
    - <span data-ttu-id="683be-275">**Cím:** *Rakomány rendezésből*</span><span class="sxs-lookup"><span data-stu-id="683be-275">**Title:** *Load from Sorting*</span></span>
    - <span data-ttu-id="683be-276">**Mód:** *Munka*</span><span class="sxs-lookup"><span data-stu-id="683be-276">**Mode:** *Work*</span></span>
    - <span data-ttu-id="683be-277">**Meglévő munka használata:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="683be-277">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="683be-278">Az **Általános** gyorslapon az **Irányító** mezőt *Felhasználó által irányított* értékre kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="683be-278">On the **General** FastTab, set the **Directed by** field to *User directed*.</span></span>
1. <span data-ttu-id="683be-279">Válassza a **Munkaosztályok** gyorslap **Új** elemét, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-279">On the **Work classes** FastTab, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="683be-280">**Munkaosztály azonosítója:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="683be-280">**Work class ID:** *SORT*</span></span>
    - <span data-ttu-id="683be-281">**Munkarendelés típusa:** *Rendezett készletkitárolás*</span><span class="sxs-lookup"><span data-stu-id="683be-281">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="683be-282">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-282">Select **Save**.</span></span>

### <a name="set-up-the-mobile-device-menu"></a><span data-ttu-id="683be-283">A Mobileszköz-menü beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-283">Set up the mobile device menu</span></span>

<span data-ttu-id="683be-284">Ezután az új menüelemeket fel kell venni a mobileszköz menüjébe.</span><span class="sxs-lookup"><span data-stu-id="683be-284">You must now add the new menu items to the mobile device menu.</span></span>

1. <span data-ttu-id="683be-285">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-285">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="683be-286">Válassza ki a **Kimenő** menüt.</span><span class="sxs-lookup"><span data-stu-id="683be-286">Select the **Outbound** menu.</span></span>
1. <span data-ttu-id="683be-287">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-287">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="683be-288">A **Választható menük és menüelemek** oszlopban keresse meg és válassza ki a **Raklap-összeállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-288">In the **Available menus and menu items** column, find and select **Pallet build**.</span></span>
1. <span data-ttu-id="683be-289">Válassza a jobbra mutató nyilat a **Raklap-összeállítás** áthelyezéséhez a **Menü struktúrája** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="683be-289">Select the right arrow button to move **Pallet build** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="683be-290">A fel és a le nyílgombokkal helyezheti a **Raklap összeállítása** menü elemet a mobileszköz menü kívánt pozíciójába.</span><span class="sxs-lookup"><span data-stu-id="683be-290">Use the up arrow and down arrow buttons to put the **Pallet build** menu item in the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="683be-291">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-291">Select **Save**.</span></span>
1. <span data-ttu-id="683be-292">Ennek az eljárásnak a megismétlésével adja hozzá a **Rakomány rendezésből** menü elemet a **Kimenő** menübe.</span><span class="sxs-lookup"><span data-stu-id="683be-292">Repeat this procedure to add the **Load from Sorting** menu item to the **Outbound** menu.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="683be-293">Helyutasítások beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-293">Set up location directives</span></span>

<span data-ttu-id="683be-294">A *helyutasítások* olyan szabályok, amik segítik a kitárolási és betárolási helyek meghatározását, készletmozgatás esetében.</span><span class="sxs-lookup"><span data-stu-id="683be-294">*Location directives* are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="683be-295">Ekkor létre kell hoznia egy szabályt a rendezési munka kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="683be-295">You must now create a rule to manage the sorting work.</span></span>

#### <a name="set-up-a-single-sku-directive"></a><span data-ttu-id="683be-296">Egyetlen Termékváltozatirányelv beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-296">Set up a single-SKU directive</span></span>

1. <span data-ttu-id="683be-297">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-297">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="683be-298">A bal oldali ablaktáblában módosítsa a **Munkarendelés típusa** mezőt *Rendezett készletkitárolás* értékre.</span><span class="sxs-lookup"><span data-stu-id="683be-298">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="683be-299">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-299">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="683be-300">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-300">In the header, set the following values:</span></span>

    - <span data-ttu-id="683be-301">**Sorozat:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-301">**Sequence:** *1*</span></span>
    - <span data-ttu-id="683be-302">**Név:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="683be-302">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="683be-303">A **Helyutasítások** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-303">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="683be-304">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="683be-304">**Work type:** *Put*</span></span>
    - <span data-ttu-id="683be-305">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="683be-305">**Site:** *6*</span></span>
    - <span data-ttu-id="683be-306">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="683be-306">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="683be-307">**Több termékváltozat:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="683be-307">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="683be-308">A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="683be-308">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="683be-309">Válassza a **Sorok** gyorslap **Új** elemét, majd állítsa be a következő értékeket az új soron:</span><span class="sxs-lookup"><span data-stu-id="683be-309">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="683be-310">Az összes többi mezőben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="683be-310">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="683be-311">**Sorozat:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-311">**Sequence:** *1*</span></span>
    - <span data-ttu-id="683be-312">**Kezdet:** *0*</span><span class="sxs-lookup"><span data-stu-id="683be-312">**From:** *0*</span></span>
    - <span data-ttu-id="683be-313">**Befejezés:** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="683be-313">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="683be-314">A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap az eszközsoron.</span><span class="sxs-lookup"><span data-stu-id="683be-314">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="683be-315">Válassza a **Helyutasítás-műveletek** gyorslap **Új** elemét, majd állítsa be a következő értékeket az új soron:</span><span class="sxs-lookup"><span data-stu-id="683be-315">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="683be-316">Az összes többi mezőben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="683be-316">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="683be-317">**Sorozat:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-317">**Sequence:** *1*</span></span>
    - <span data-ttu-id="683be-318">**Név:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="683be-318">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="683be-319">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-319">Select **Save**.</span></span>
1. <span data-ttu-id="683be-320">A **Helyutasítás műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-320">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="683be-321">A lekérdezési szerkesztő **Tartomány** lapján keresse meg azt a sort, amelynél a **Mező** mező értéke *Hely*.</span><span class="sxs-lookup"><span data-stu-id="683be-321">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="683be-322">Ennek a sornak a **Feltételek** mezőjét állítsa *Baydoor* értékre.</span><span class="sxs-lookup"><span data-stu-id="683be-322">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="683be-323">Az **OK** gombra kattintva mentse a beállításokat, és zárja be a lekérdezésszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="683be-323">Select **OK** to save your settings and close the query editor.</span></span>

#### <a name="set-up-a-multiple-sku-directive"></a><span data-ttu-id="683be-324">Egyetlen több termékváltozatirányelv beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-324">Set up a multiple-SKU directive</span></span>

1. <span data-ttu-id="683be-325">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-325">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="683be-326">A bal oldali ablaktáblában módosítsa a **Munkarendelés típusa** mezőt *Rendezett készletkitárolás* értékre.</span><span class="sxs-lookup"><span data-stu-id="683be-326">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="683be-327">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-327">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="683be-328">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-328">In the header, set the following values:</span></span>

    - <span data-ttu-id="683be-329">**Sorozat:** *2*</span><span class="sxs-lookup"><span data-stu-id="683be-329">**Sequence:** *2*</span></span>
    - <span data-ttu-id="683be-330">**Név:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="683be-330">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="683be-331">A **Helyutasítások** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-331">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="683be-332">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="683be-332">**Work type:** *Put*</span></span>
    - <span data-ttu-id="683be-333">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="683be-333">**Site:** *6*</span></span>
    - <span data-ttu-id="683be-334">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="683be-334">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="683be-335">**Több termékváltozat:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="683be-335">**Multiple SKU:** *Yes*</span></span>

1. <span data-ttu-id="683be-336">A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="683be-336">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="683be-337">Válassza a **Sorok** gyorslap **Új** elemét, majd állítsa be a következő értékeket az új soron:</span><span class="sxs-lookup"><span data-stu-id="683be-337">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="683be-338">Az összes többi mezőben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="683be-338">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="683be-339">**Sorozat:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-339">**Sequence:** *1*</span></span>
    - <span data-ttu-id="683be-340">**Kezdet:** *0*</span><span class="sxs-lookup"><span data-stu-id="683be-340">**From:** *0*</span></span>
    - <span data-ttu-id="683be-341">**Befejezés:** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="683be-341">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="683be-342">A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap az eszközsoron.</span><span class="sxs-lookup"><span data-stu-id="683be-342">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="683be-343">Válassza a **Helyutasítás-műveletek** gyorslap **Új** elemét, majd állítsa be a következő értékeket az új soron:</span><span class="sxs-lookup"><span data-stu-id="683be-343">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="683be-344">Az összes többi mezőben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="683be-344">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="683be-345">**Sorozat:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-345">**Sequence:** *1*</span></span>
    - <span data-ttu-id="683be-346">**Név:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="683be-346">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="683be-347">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-347">Select **Save**.</span></span>
1. <span data-ttu-id="683be-348">A **Helyutasítás műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-348">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="683be-349">A lekérdezési szerkesztő **Tartomány** lapján keresse meg azt a sort, amelynél a **Mező** mező értéke *Hely*.</span><span class="sxs-lookup"><span data-stu-id="683be-349">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="683be-350">Ennek a sornak a **Feltételek** mezőjét állítsa *Baydoor* értékre.</span><span class="sxs-lookup"><span data-stu-id="683be-350">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="683be-351">Az **OK** gombra kattintva mentse a beállításokat, és zárja be a lekérdezésszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="683be-351">Select **OK** to save your settings and close the query editor.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="683be-352">Munkasablonok beállítása</span><span class="sxs-lookup"><span data-stu-id="683be-352">Set up work templates</span></span>

1. <span data-ttu-id="683be-353">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-353">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="683be-354">Módosítsa a **Munkarendelés típusa** mezőt *Rendezett készletkitárolás* értékre.</span><span class="sxs-lookup"><span data-stu-id="683be-354">Change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="683be-355">Jelölje be a műveleti ablakban az **Új** lehetőséget a munkasablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="683be-355">On the Action Pane, select **New** to create a work template.</span></span>
1. <span data-ttu-id="683be-356">Az **Áttekintés** lapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-356">On the **Overview** tab, set the following values:</span></span>

    - <span data-ttu-id="683be-357">**Sorozat:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-357">**Sequence:** *1*</span></span>
    - <span data-ttu-id="683be-358">**Munkasablon:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-358">**Work template:** *Sort*</span></span>
    - <span data-ttu-id="683be-359">**Munkasablon leírása:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-359">**Work template description:** *Sort*</span></span>

1. <span data-ttu-id="683be-360">A **Mentés** gombra kattintva elérhetővé válik a **Munkasablon részletei** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="683be-360">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="683be-361">A **Munkasablon részletei** gyorslapon válassza az **Új** parancsot egy sor hozzáadásához, majd állítsa be a következő értékeket hozzá:</span><span class="sxs-lookup"><span data-stu-id="683be-361">On the **Work Template Details** FastTab, select **New** to add a line, and then set the following values for it:</span></span>

    - <span data-ttu-id="683be-362">**Munka típusa:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="683be-362">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="683be-363">**Munkaosztály azonosítója:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="683be-363">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="683be-364">Válassza ismét az **Új** lehetőséget egy második sor hozzáadásához, és állítsa be a következő értékeket hozzá:</span><span class="sxs-lookup"><span data-stu-id="683be-364">Select **New** again to add a second line, and then set the following values for it:</span></span>

    - <span data-ttu-id="683be-365">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="683be-365">**Work type:** *Put*</span></span>
    - <span data-ttu-id="683be-366">**Munkaosztály azonosítója:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="683be-366">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="683be-367">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-367">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="683be-368">Forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="683be-368">Scenario</span></span>

<span data-ttu-id="683be-369">Ez a forgatókönyv egy olyan állapotot szimulál, amikor a csomagolt tárolókat a szállítmányozói szolgáltatástól függően automatikusan különböző pozíciókra (raklapokra) kell rendezni.</span><span class="sxs-lookup"><span data-stu-id="683be-369">This scenario simulates a situation where packed containers should automatically be sorted to different positions (pallets) after the packing station, depending on the shipping carrier service.</span></span> <span data-ttu-id="683be-370">Miután a rakomány minden cikkét becsomagolták, és a cím szerint rendezték, a raklapok a raktárajtóhoz kerülnek.</span><span class="sxs-lookup"><span data-stu-id="683be-370">After all items from the load are packed and sorted by address, the pallets will be moved to the bay door.</span></span>

### <a name="create-sales-orders-and-picking-work"></a><span data-ttu-id="683be-371">Értékesítési rendelések és kitárolási munka létrehozása</span><span class="sxs-lookup"><span data-stu-id="683be-371">Create sales orders and picking work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="683be-372">1. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="683be-372">Create sales order 1</span></span>

1. <span data-ttu-id="683be-373">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="683be-373">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="683be-374">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-374">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="683be-375">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-375">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="683be-376">**Vevőkód** *US-005*</span><span class="sxs-lookup"><span data-stu-id="683be-376">**Customer account:** *US-005*</span></span>
    - <span data-ttu-id="683be-377">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="683be-377">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="683be-378">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="683be-378">Select **OK** to close the dialog box.</span></span>

    <span data-ttu-id="683be-379">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="683be-379">The new sales order is opened.</span></span>

1. <span data-ttu-id="683be-380">Váltson a **Fejléc** nézetre.</span><span class="sxs-lookup"><span data-stu-id="683be-380">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="683be-381">A **Szállítás** gyorslapon a **Szállítás** szakaszban adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-381">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="683be-382">**Szállítmányozó:** *Légitársaság*</span><span class="sxs-lookup"><span data-stu-id="683be-382">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="683be-383">**Szállítmányozói szolgáltatás:** *Légi*</span><span class="sxs-lookup"><span data-stu-id="683be-383">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="683be-384">Váltson a **Sorok** nézetre.</span><span class="sxs-lookup"><span data-stu-id="683be-384">Switch to the **Lines** view.</span></span>
1. <span data-ttu-id="683be-385">Az **Értékesítésirendelés-sor** gyorslapon válassza a **Sor hozzáadása** lehetőséget, ha nem ad hozzá új sort a program, és adja meg a következőt:</span><span class="sxs-lookup"><span data-stu-id="683be-385">If a new, empty line isn't automatically added to the grid on the **Sales order lines** FastTab, select **Add line** to add one.</span></span>
1. <span data-ttu-id="683be-386">A következő értékeket állítsa be az új rendeléssorhoz:</span><span class="sxs-lookup"><span data-stu-id="683be-386">On the new order line, set the following values:</span></span>

    - <span data-ttu-id="683be-387">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="683be-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="683be-388">**Mennyiség:** *2*</span><span class="sxs-lookup"><span data-stu-id="683be-388">**Quantity:** *2*</span></span>

1. <span data-ttu-id="683be-389">Miközben az **Értékesítésirendelés-sorok** gyorslapján az új rendelési sor továbbra is be van jelölve, akkor a rács fölötti **Készlet** menüben válassza a **Foglalás** elemet.</span><span class="sxs-lookup"><span data-stu-id="683be-389">While the new order line is still selected on the **Sales order lines** FastTab, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="683be-390">A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.</span><span class="sxs-lookup"><span data-stu-id="683be-390">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="683be-391">Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="683be-391">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="683be-392">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.</span><span class="sxs-lookup"><span data-stu-id="683be-392">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="683be-393">Egy tájékoztató üzenet jelenik meg, amely a rendelés szállítmányát és hullámát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="683be-393">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="683be-394">Jegyezze fel a hullám azonosítószámát és a szállítmány azonosítószámait.</span><span class="sxs-lookup"><span data-stu-id="683be-394">Make a note of the wave ID and shipment ID numbers.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="683be-395">2. értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="683be-395">Sales order 2</span></span>

1. <span data-ttu-id="683be-396">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="683be-396">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="683be-397">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-397">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="683be-398">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-398">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="683be-399">**Vevőkód** *US-006*</span><span class="sxs-lookup"><span data-stu-id="683be-399">**Customer account:** *US-006*</span></span>
    - <span data-ttu-id="683be-400">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="683be-400">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="683be-401">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="683be-401">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="683be-402">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="683be-402">The new sales order is opened.</span></span> <span data-ttu-id="683be-403">Tartalmaznia kell egy új, üres sort az **Értékesítési rendelés sorai** gyorslap rácsán.</span><span class="sxs-lookup"><span data-stu-id="683be-403">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="683be-404">A következő értékeket állítsa be ehhez a rendeléssorhoz:</span><span class="sxs-lookup"><span data-stu-id="683be-404">Set the following values on this order line:</span></span>

    - <span data-ttu-id="683be-405">**Cikk:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="683be-405">**Item:** *A0001*</span></span>
    - <span data-ttu-id="683be-406">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-406">**Quantity:** *1*</span></span>

1. <span data-ttu-id="683be-407">A **Sor részletei** gyorslap **Szállítás** lapján állítsa be a **Szállítási mód** mezőt *Flowe-STD* értékre.</span><span class="sxs-lookup"><span data-stu-id="683be-407">On the **Line details** FastTab, on the **Delivery** tab, set the **Mode of delivery** field to *Flowe-STD*.</span></span>
1. <span data-ttu-id="683be-408">Válassza az **Értékesítési rendelés sorai** gyorslap **Sor hozzáadása** elemét, majd állítsa be a következő értékeket a második értékesítési soron:</span><span class="sxs-lookup"><span data-stu-id="683be-408">On the **Sales order lines** FastTab, select **Add line**, and then set the following values on the second order line:</span></span>

    - <span data-ttu-id="683be-409">**Cikk:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="683be-409">**Item:** *A0002*</span></span>
    - <span data-ttu-id="683be-410">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-410">**Quantity:** *1*</span></span>

1. <span data-ttu-id="683be-411">A **Sor részletei** gyorslap **Szállítás** lapján módosítsa a **Szállítási mód** mezőt *Air C-Air* értékre.</span><span class="sxs-lookup"><span data-stu-id="683be-411">On the **Line details** FastTab, on the **Delivery** tab, change the value of the **Mode of delivery** field to *Air C-Air*.</span></span>
1. <span data-ttu-id="683be-412">Az **Értékesítési rendelés sorai** gyorslapon válassza az első rendeléssort.</span><span class="sxs-lookup"><span data-stu-id="683be-412">On the **Sales order lines** FastTab, select the first order line.</span></span> <span data-ttu-id="683be-413">Majd a rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.</span><span class="sxs-lookup"><span data-stu-id="683be-413">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="683be-414">A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.</span><span class="sxs-lookup"><span data-stu-id="683be-414">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="683be-415">Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="683be-415">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="683be-416">Az **Értékesítési rendelés sorai** gyorslapon válassza a második rendeléssort.</span><span class="sxs-lookup"><span data-stu-id="683be-416">On the **Sales order lines** FastTab, select the second order line.</span></span> <span data-ttu-id="683be-417">Majd a rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.</span><span class="sxs-lookup"><span data-stu-id="683be-417">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="683be-418">A **Foglalás** oldalon válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.</span><span class="sxs-lookup"><span data-stu-id="683be-418">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="683be-419">Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="683be-419">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="683be-420">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.</span><span class="sxs-lookup"><span data-stu-id="683be-420">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="683be-421">Egy tájékoztató üzenet jelenik meg, amely a rendelés szállítmányát és hullámát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="683be-421">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="683be-422">Figyelje meg, hogy az értékesítési rendelés soraiban két hullám-azonosító és két szállítási azonosító lett létrehozva egy-egy az egyes értékesítésirendelés-sorokhoz.</span><span class="sxs-lookup"><span data-stu-id="683be-422">Notice that two wave ID numbers and two shipment ID numbers have been created, one for each mode of delivery for the sales order lines.</span></span>

#### <a name="get-the-work-ids-from-the-work-details"></a><span data-ttu-id="683be-423">Munkaazonosítók beolvasása a munka részleteiből</span><span class="sxs-lookup"><span data-stu-id="683be-423">Get the work IDs from the work details</span></span>

1. <span data-ttu-id="683be-424">Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.</span><span class="sxs-lookup"><span data-stu-id="683be-424">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="683be-425">A lapon az értékesítési rendelésekből létrehozott munkaazonosítók láthatók.</span><span class="sxs-lookup"><span data-stu-id="683be-425">The page shows the work IDs that have been created from sales orders.</span></span> <span data-ttu-id="683be-426">Használja a hullámazonosítókat és szállítmányazonosítókat az értékesítési rendelésekből, amelyeket létrehozott az egyes hullámok és szállítmányok munkaazonosítójának megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="683be-426">Use the wave IDs and shipment IDs from the sales orders that you created to find the work ID for each wave and shipment.</span></span> <span data-ttu-id="683be-427">Jegyezze fel ezeket a munkaazonosítókat, mert a következő lépésekben szüksége lesz rájuk.</span><span class="sxs-lookup"><span data-stu-id="683be-427">Make a note of those work IDs, because you will need them in the next steps.</span></span> <span data-ttu-id="683be-428">Figyelje meg, hogy a második értékesítési rendeléshez két munkaazonosító jött létre.</span><span class="sxs-lookup"><span data-stu-id="683be-428">Notice that two work IDs were created for the second sales order.</span></span> <span data-ttu-id="683be-429">Ha különböző cikkek kitárolása különböző helyekről történik, akkor külön szavas azonosítók jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="683be-429">If different items are picked from different locations, separate word IDs are generated.</span></span>

### <a name="pick-items-for-the-sales-orders"></a><span data-ttu-id="683be-430">Cikkek kitárolása az értékesítési rendelésekhez</span><span class="sxs-lookup"><span data-stu-id="683be-430">Pick items for the sales orders</span></span>

<span data-ttu-id="683be-431">Végezze el a létrehozott munkát úgy, hogy a mobileszköz segítségével áthelyezi a cikkeket a csomagolási állomásra.</span><span class="sxs-lookup"><span data-stu-id="683be-431">Complete the created work by using the mobile device to move the items to the pack station.</span></span>

1. <span data-ttu-id="683be-432">A mobileszközön jelentkezzen be a *62-es* raktárba a forgatókönyvhöz létrehozott felhasználói azonosító (vagy egy meglévő demóadat-felhasználó) használatával.</span><span class="sxs-lookup"><span data-stu-id="683be-432">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="683be-433">Válassza a főmenü **Kimenő** elemét.</span><span class="sxs-lookup"><span data-stu-id="683be-433">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="683be-434">Válassza a **Kimenő** menü **Értékesítési kitárolás** elemét.</span><span class="sxs-lookup"><span data-stu-id="683be-434">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="683be-435">Az **Azonosító** mezőbe írja be az 1. értékesítési rendeléshez létrehozott munkaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="683be-435">In the **ID** field, enter the work ID that was created for sales order 1.</span></span>
1. <span data-ttu-id="683be-436">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-436">Select **OK**.</span></span>
1. <span data-ttu-id="683be-437">Az **Értékesítési rendelések – Kitárolás** oldalon adja meg az 1. értékesítési rendeléshez létrehozott azonosítótáblát.</span><span class="sxs-lookup"><span data-stu-id="683be-437">On the **Sales orders - Pick** page, enter a target LP that was created for sales order 1.</span></span> <span data-ttu-id="683be-438">Figyelje meg, hogy a kitárolási hely (*bulk-001*), a cikk (*A0001*) és a mennyiség (*2 db*) jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="683be-438">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*2 pcs*) are shown.</span></span>
1. <span data-ttu-id="683be-439">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-439">Select **OK**.</span></span>
1. <span data-ttu-id="683be-440">Tekintse át a **Beszerzési rendelések – Betárolás** oldalon látható információkat.</span><span class="sxs-lookup"><span data-stu-id="683be-440">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="683be-441">A **Hely** mezőnek jeleznie kell, hogy a kitárolt cikkek a *Csomagolás* helyre mennek.</span><span class="sxs-lookup"><span data-stu-id="683be-441">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="683be-442">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-442">Select **OK**.</span></span>

    <span data-ttu-id="683be-443">A **Munkaazonosító/azonosítótábla azonosítójának beolvasása** lapon egy „Elvégzett munka” üzenet jelenik meg, amely azt jelzi, hogy az 1. értékesítési rendelés munkaazonosítóját befejezték.</span><span class="sxs-lookup"><span data-stu-id="683be-443">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message, which indicates that the work ID from sales order 1 has been completed.</span></span>

    <span data-ttu-id="683be-444">Most kitárolhatja a 2. értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="683be-444">You will now pick sales order 2.</span></span>

1. <span data-ttu-id="683be-445">Az **Azonosító** mezőbe írja be a 2. értékesítési rendeléshez létrehozott munkaazonosítót, ahol az 1. sor cikke *A0001*.</span><span class="sxs-lookup"><span data-stu-id="683be-445">In the **ID** field, enter the work ID that was created for sales order 2, where line 1 has item *A0001*.</span></span>
1. <span data-ttu-id="683be-446">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-446">Select **OK**.</span></span>
1. <span data-ttu-id="683be-447">Az **Értékesítési rendelések – Kitárolás** oldalon adja meg a cél azonosítótáblát.</span><span class="sxs-lookup"><span data-stu-id="683be-447">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="683be-448">Figyelje meg, hogy a kitárolási hely (*bulk-001*), a cikk (*A0001*) és a mennyiség (*1 db*) jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="683be-448">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="683be-449">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-449">Select **OK**.</span></span>
1. <span data-ttu-id="683be-450">Tekintse át a **Beszerzési rendelések – Betárolás** oldalon látható információkat.</span><span class="sxs-lookup"><span data-stu-id="683be-450">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="683be-451">A **Hely** mezőnek jeleznie kell, hogy a kitárolt cikkek a *Csomagolás* helyre mennek.</span><span class="sxs-lookup"><span data-stu-id="683be-451">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="683be-452">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-452">Select **OK**.</span></span>

    <span data-ttu-id="683be-453">A **Munkaazonosító/azonosítótábla azonosítójának beolvasása** oldalon egy „Munka elvégezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="683be-453">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="683be-454">Ez az üzenet azt jelzi, hogy a 2. értékesítési rendelés 1. sorának munkaazonosítója el lett végezve.</span><span class="sxs-lookup"><span data-stu-id="683be-454">This message indicates that the work ID from line 1 of sales order 2 has been completed.</span></span>

1. <span data-ttu-id="683be-455">Az **Azonosító** mezőbe írja be a 2. értékesítési rendeléshez létrehozott munkaazonosítót, ahol az 2. sor cikke *A0002*.</span><span class="sxs-lookup"><span data-stu-id="683be-455">In the **ID** field, enter the work ID that was created for sales order 2, where line 2 has item *A0002*.</span></span>
1. <span data-ttu-id="683be-456">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-456">Select **OK**.</span></span>
1. <span data-ttu-id="683be-457">Az **Értékesítési rendelések – Kitárolás** oldalon adja meg a cél azonosítótáblát.</span><span class="sxs-lookup"><span data-stu-id="683be-457">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="683be-458">Figyelje meg, hogy a kitárolási hely (*bulk-002*), a cikk (*A0001*) és a mennyiség (*1 db*) jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="683be-458">Notice that the picking location (*bulk-002*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="683be-459">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-459">Select **OK**.</span></span>
1. <span data-ttu-id="683be-460">Tekintse át a **Beszerzési rendelések – Betárolás** oldalon látható információkat.</span><span class="sxs-lookup"><span data-stu-id="683be-460">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="683be-461">A **Hely** mezőnek jeleznie kell, hogy a kitárolt cikkek a *Csomagolás* helyre mennek.</span><span class="sxs-lookup"><span data-stu-id="683be-461">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="683be-462">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-462">Select **OK**.</span></span>

    <span data-ttu-id="683be-463">A **Munkaazonosító/azonosítótábla azonosítójának beolvasása** oldalon egy „Munka elvégezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="683be-463">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="683be-464">Ez az üzenet azt jelzi, hogy a 2. értékesítési rendelés 2. sorának munkaazonosítója el lett végezve.</span><span class="sxs-lookup"><span data-stu-id="683be-464">This message indicates that the work ID from line 2 of sales order 2 has been completed.</span></span>

### <a name="pack-sales-orders-into-containers"></a><span data-ttu-id="683be-465">Értékesítési rendelések csomagolása tárolókba</span><span class="sxs-lookup"><span data-stu-id="683be-465">Pack sales orders into containers</span></span>

#### <a name="pack-sales-order-1-into-containers"></a><span data-ttu-id="683be-466">Az 1. értékesítési rendelés csomagolása tárolókba</span><span class="sxs-lookup"><span data-stu-id="683be-466">Pack sales order 1 into containers</span></span>

1. <span data-ttu-id="683be-467">Nyissa meg a **Raktárkezelés \> Csomagolási és tárolólétrehozás \> Csomagolás** menüt.</span><span class="sxs-lookup"><span data-stu-id="683be-467">Go to **Warehouse management \> Packing and containerization \> Pack**.</span></span>

    <span data-ttu-id="683be-468">Megjelenik a **Csomagolóállomás kiválasztása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="683be-468">The **Select packing station** dialog box appears.</span></span> <span data-ttu-id="683be-469">Alapértelmezés szerint a **Dolgozó** mezőt a korábban beállított dolgozó nevére kell állítani.</span><span class="sxs-lookup"><span data-stu-id="683be-469">By default, the **Worker** field should be set to the name of the worker that you set up earlier.</span></span>

1. <span data-ttu-id="683be-470">Állítsa be a következő értékeket az adott csomagolásai helyen tervezett szállítmányok és tárolók megtekintéséhez és az azokkal történő munkához:</span><span class="sxs-lookup"><span data-stu-id="683be-470">Set the following values to view and work on shipments and containers that are planned at the specific packing location:</span></span>

    - <span data-ttu-id="683be-471">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="683be-471">**Site:** *6*</span></span>
    - <span data-ttu-id="683be-472">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="683be-472">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="683be-473">**Hely:** *Csomag*</span><span class="sxs-lookup"><span data-stu-id="683be-473">**Location:** *Pack*</span></span>
    - <span data-ttu-id="683be-474">**Csomagolási profil azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="683be-474">**Packing profile ID:** *Sort*</span></span>

1. <span data-ttu-id="683be-475">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="683be-475">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="683be-476">A **Csomag** lap **Azonosítótábla vagy szállítmány** mezőjébe írja be az 1. értékesítési rendelés cél azonosítótábláját.</span><span class="sxs-lookup"><span data-stu-id="683be-476">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for sales order 1.</span></span> <span data-ttu-id="683be-477">Ezután a billentyűzet **Tab** vagy **Enter** gombjával lépjen ki a mezőből.</span><span class="sxs-lookup"><span data-stu-id="683be-477">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="683be-478">A műveleti ablaktáblán kattintson az **Új tároló** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-478">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="683be-479">Fogadja el az alapértelmezett beállításokat, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="683be-479">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="683be-480">Jegyezze fel a tárolóazonosítót.</span><span class="sxs-lookup"><span data-stu-id="683be-480">Make a note of the container ID.</span></span>
1. <span data-ttu-id="683be-481">A **Cikkcsomagolás** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-481">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="683be-482">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-482">**Quantity:** *1*</span></span>
    - <span data-ttu-id="683be-483">**Azonosító:** Cikk *A0001*</span><span class="sxs-lookup"><span data-stu-id="683be-483">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="683be-484">A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-484">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="683be-485">A **Tároló lezárása** párbeszédpanelen válassza a **Rendszertömeg beolvasása lehetőséget**, ha szeretné, hogy a rendszer frissítse a **Bruttó súly** mezőt.</span><span class="sxs-lookup"><span data-stu-id="683be-485">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="683be-486">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-486">Select **OK**.</span></span> <span data-ttu-id="683be-487">A program áthelyezi a tárolót a *SORT* helyre, és készen áll a rendezésre.</span><span class="sxs-lookup"><span data-stu-id="683be-487">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="683be-488">Hozzon létre egy másik tárolót, és adja hozzá a második elemet az 1. értékesítési rendelés azonosítótáblájáról egy új tárolóhoz.</span><span class="sxs-lookup"><span data-stu-id="683be-488">Create a second container to add the second item from the LP for sales order 1 to a new container.</span></span>
1. <span data-ttu-id="683be-489">A műveleti ablaktáblán kattintson az **Új tároló** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-489">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="683be-490">Fogadja el az alapértelmezett beállításokat, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="683be-490">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="683be-491">Jegyezze fel a tárolóazonosítót.</span><span class="sxs-lookup"><span data-stu-id="683be-491">Make a note of the container ID.</span></span>
1. <span data-ttu-id="683be-492">A **Cikkcsomagolás** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-492">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="683be-493">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-493">**Quantity:** *1*</span></span>
    - <span data-ttu-id="683be-494">**Azonosító:** Cikk *A0001*</span><span class="sxs-lookup"><span data-stu-id="683be-494">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="683be-495">A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-495">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="683be-496">A **Tároló lezárása** párbeszédpanelen válassza a **Rendszertömeg beolvasása lehetőséget**, ha szeretné, hogy a rendszer frissítse a **Bruttó súly** mezőt.</span><span class="sxs-lookup"><span data-stu-id="683be-496">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="683be-497">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-497">Select **OK**.</span></span> <span data-ttu-id="683be-498">A program áthelyezi a tárolót a *SORT* helyre, és készen áll a rendezésre.</span><span class="sxs-lookup"><span data-stu-id="683be-498">The container is moved to the *SORT* location and is ready for sorting.</span></span>

#### <a name="pack-sales-order-2-into-containers"></a><span data-ttu-id="683be-499">Az 2. értékesítési rendelés csomagolása tárolókba</span><span class="sxs-lookup"><span data-stu-id="683be-499">Pack sales order 2 into containers</span></span>

1. <span data-ttu-id="683be-500">A **Csomag** lap **Azonosítótábla vagy szállítmány** mezőjébe írja be a 2.. értékesítési rendelés első sorának cél azonosítótábláját.</span><span class="sxs-lookup"><span data-stu-id="683be-500">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for line 1 of sales order 2.</span></span> <span data-ttu-id="683be-501">Ezután a billentyűzet **Tab** vagy **Enter** gombjával lépjen ki a mezőből.</span><span class="sxs-lookup"><span data-stu-id="683be-501">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="683be-502">A műveleti ablaktáblán kattintson az **Új tároló** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-502">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="683be-503">Fogadja el az alapértelmezett beállításokat, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="683be-503">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="683be-504">Jegyezze fel a tárolóazonosítót.</span><span class="sxs-lookup"><span data-stu-id="683be-504">Make a note of the container ID.</span></span>
1. <span data-ttu-id="683be-505">A **Cikkcsomagolás** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-505">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="683be-506">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-506">**Quantity:** *1*</span></span>
    - <span data-ttu-id="683be-507">**Azonosító:** Cikk *A0001*</span><span class="sxs-lookup"><span data-stu-id="683be-507">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="683be-508">A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-508">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="683be-509">A **Tároló lezárása** párbeszédpanelen válassza a **Rendszertömeg beolvasása lehetőséget**, ha szeretné, hogy a rendszer frissítse a **Bruttó súly** mezőt.</span><span class="sxs-lookup"><span data-stu-id="683be-509">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="683be-510">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-510">Select **OK**.</span></span> <span data-ttu-id="683be-511">A program áthelyezi a tárolót a *SORT* helyre, és készen áll a rendezésre.</span><span class="sxs-lookup"><span data-stu-id="683be-511">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="683be-512">Az **Azonosítótábla vagy szállítmány** mezőbe írja be a 2. értékesítési rendelés második sorának cél azonosítótábláját.</span><span class="sxs-lookup"><span data-stu-id="683be-512">In the **License plate or shipment** field, enter the target LP for line 2 of the sales order 2.</span></span> <span data-ttu-id="683be-513">Ezután a billentyűzet **Tab** vagy **Enter** gombjával lépjen ki a mezőből.</span><span class="sxs-lookup"><span data-stu-id="683be-513">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="683be-514">A műveleti ablaktáblán kattintson az **Új tároló** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-514">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="683be-515">Fogadja el az alapértelmezett beállításokat, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="683be-515">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="683be-516">Jegyezze fel a tárolóazonosítót.</span><span class="sxs-lookup"><span data-stu-id="683be-516">Make a note of the container ID.</span></span>
1. <span data-ttu-id="683be-517">A **Cikkcsomagolás** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="683be-517">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="683be-518">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="683be-518">**Quantity:** *1*</span></span>
    - <span data-ttu-id="683be-519">**Azonosító mező:** Cikk *A0002*</span><span class="sxs-lookup"><span data-stu-id="683be-519">**Identifier field:** Item *A0002*</span></span>

1. <span data-ttu-id="683be-520">A műveleti ablaktáblán kattintson az **Tároló bezárása** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-520">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="683be-521">A **Tároló lezárása** párbeszédpanelen válassza a **Rendszertömeg beolvasása lehetőséget**, ha szeretné, hogy a rendszer frissítse a **Bruttó súly** mezőt.</span><span class="sxs-lookup"><span data-stu-id="683be-521">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="683be-522">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-522">Select **OK**.</span></span> <span data-ttu-id="683be-523">A program áthelyezi a tárolót a *SORT* helyre, és készen áll a rendezésre.</span><span class="sxs-lookup"><span data-stu-id="683be-523">The container is moved to the *SORT* location and is ready for sorting.</span></span>

<span data-ttu-id="683be-524">A tároló adatainak megtekintéséhez nyissa meg a **Raktárkezelés \> Csomagolás és tárolólétrehozás \> Tárolók** lehetőséget, és keresse meg a csomagolás során létrehozott tárolóazonosítókat.</span><span class="sxs-lookup"><span data-stu-id="683be-524">To view the container details, go to **Warehouse management \> Packing and containerization \> Containers**, and search for the container IDs that were created during packing.</span></span>

### <a name="sort-the-containers"></a><span data-ttu-id="683be-525">A tárolók rendezése</span><span class="sxs-lookup"><span data-stu-id="683be-525">Sort the containers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="683be-526">Amikor a mobilalkalmazás **Raklap összeállítása** menüjét megnyitja a kimenő rendszerezéshez, akkor egy **Teljes** feliratú gombot fog látni.</span><span class="sxs-lookup"><span data-stu-id="683be-526">When you access the **Pallet build** menu item on the mobile app to do outbound sorting, you will see a button that is labeled **Full**.</span></span> <span data-ttu-id="683be-527">*Ne használja a **Teljes** gombot a pozíció rendezéséhez vagy lezárásához.*</span><span class="sxs-lookup"><span data-stu-id="683be-527">*Don't use the **Full** button to sort or close the position.*</span></span>
>
> <span data-ttu-id="683be-528">A **Teljes** gomb alapértelmezésben elérhető, és nem lehet letiltani vagy eltávolítani a lapról.</span><span class="sxs-lookup"><span data-stu-id="683be-528">The **Full** button is provided by default and can't be disabled or removed from the page.</span></span> <span data-ttu-id="683be-529">Ez a beállítás nem lehet a *Kimenő rendezés* funkcióhoz használni.</span><span class="sxs-lookup"><span data-stu-id="683be-529">It isn't used for the *Outbound sorting* feature.</span></span>

#### <a name="sort-the-first-container"></a><span data-ttu-id="683be-530">Az első tároló rendezése</span><span class="sxs-lookup"><span data-stu-id="683be-530">Sort the first container</span></span>

1. <span data-ttu-id="683be-531">A mobileszközön jelentkezzen be a *62-es* raktárba a forgatókönyvhöz létrehozott felhasználói azonosító (vagy egy meglévő demóadat-felhasználó) használatával.</span><span class="sxs-lookup"><span data-stu-id="683be-531">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="683be-532">Válassza a főmenü **Kimenő** elemét.</span><span class="sxs-lookup"><span data-stu-id="683be-532">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="683be-533">Válassza a **Kimenő** menü **Raklap összeállítása** elemét.</span><span class="sxs-lookup"><span data-stu-id="683be-533">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="683be-534">Az **Azonosítótábla/con** mezőbe írja be az 1. értékesítési rendeléshez társított tárolóazonosítót.</span><span class="sxs-lookup"><span data-stu-id="683be-534">In the **LP/Con** field, enter the first container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="683be-535">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-535">Select **OK**.</span></span>
1. <span data-ttu-id="683be-536">Mivel jelenleg nem léteznek rendezési pozíciók, meg kell adnia egyet.</span><span class="sxs-lookup"><span data-stu-id="683be-536">Because no sort positions currently exist, you must specify one.</span></span> <span data-ttu-id="683be-537">A **Rendezési pozíció azonosítója** mezőbe írja be az *SP01* értéket.</span><span class="sxs-lookup"><span data-stu-id="683be-537">In the **Sort position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="683be-538">Mivel jelenleg nincs azonosítótábla társítva az *SP01* rendezési pozícióhoz, meg kell adnia egy értéket.</span><span class="sxs-lookup"><span data-stu-id="683be-538">Because no LP is currently associated with sort position *SP01*, you must specify one.</span></span> <span data-ttu-id="683be-539">Az **Azonosítótábla** mezőben adja meg a *PLP01* értéket.</span><span class="sxs-lookup"><span data-stu-id="683be-539">In the **LP** field, enter *PLP01*.</span></span>
1. <span data-ttu-id="683be-540">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-540">Select **OK**.</span></span>
1. <span data-ttu-id="683be-541">Mivel a rendezési pozíció ellenőrzése be van kapcsolva, újra meg kell adnia a rendezési pozíció azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="683be-541">Because sort position validation is turned on, you must enter the sort position ID again.</span></span> <span data-ttu-id="683be-542">A **Rendezési pozíció azonosítója** mezőbe írja be az *SP01* értéket.</span><span class="sxs-lookup"><span data-stu-id="683be-542">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="683be-543">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-543">Select **OK**.</span></span>

    <span data-ttu-id="683be-544">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="683be-544">You receive a "Work completed" message.</span></span>

> [!TIP]
> <span data-ttu-id="683be-545">Ha meg szeretné tekinteni a rendezési pozíciót és a benne lévő azonosítótáblát nyissa meg a **Raktárkezelés \> Csomagolás és tárolólétrehozás \> Kimenő rendezésipozíció-hozzárendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-545">To view the sort position and the LP in it, go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
>
> <span data-ttu-id="683be-546">A **Kimenő rendezésipozíció-hozzárendelések** lap megjeleníti a jelenleg aktív összes rendezési pozíciót.</span><span class="sxs-lookup"><span data-stu-id="683be-546">The **Outbound sorting position assignments** page shows all the sort positions that are currently active.</span></span> <span data-ttu-id="683be-547">A **Rendezésipozíció-tranzakciók** mező megjeleníti az egyes pozíciókhoz társított azonosítótáblákat és a rendezési pozícióban lévő tárolókat.</span><span class="sxs-lookup"><span data-stu-id="683be-547">The **Sort position transactions** field shows the LP that is associated with each sort position, and the containers that are in the sort position.</span></span> <span data-ttu-id="683be-548">Figyelje meg, hogy jelenleg egy rendezési beosztás létezik, és a **Rendezési pozíció feltételei** gyorslap a **Szállítmány – Szállítmányozói szolgáltatás – Légi** kritériumot jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="683be-548">Notice that one sort position currently exists, and that the **Sort position criteria** FastTab shows a criterion of **Shipment – Carrier service - Air**.</span></span>

#### <a name="sort-the-remaining-containers"></a><span data-ttu-id="683be-549">A fennmaradó tárolók rendezése</span><span class="sxs-lookup"><span data-stu-id="683be-549">Sort the remaining containers</span></span>

1. <span data-ttu-id="683be-550">A mobileszközön jelentkezzen be a *62-es* raktárba a forgatókönyvhöz létrehozott felhasználói azonosító (vagy egy meglévő demóadat-felhasználó) használatával.</span><span class="sxs-lookup"><span data-stu-id="683be-550">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="683be-551">Válassza a főmenü **Kimenő** elemét.</span><span class="sxs-lookup"><span data-stu-id="683be-551">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="683be-552">Válassza a **Kimenő** menü **Raklap összeállítása** elemét.</span><span class="sxs-lookup"><span data-stu-id="683be-552">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="683be-553">Az **Azonosítótábla/con** mezőbe írja be az 1. értékesítési rendeléshez társított második tárolóazonosítót.</span><span class="sxs-lookup"><span data-stu-id="683be-553">In the **LP/Con** field, enter the second container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="683be-554">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-554">Select **OK**.</span></span> <span data-ttu-id="683be-555">Mivel a rendezési sablon automatikus rendezésre van beállítva, és létezik egy megfelelő kritériumokkal rendelkező rendezési pozíció, automatikusn át lesz irányítva a helyes rendezési pozícióhoz.</span><span class="sxs-lookup"><span data-stu-id="683be-555">Because the sorting template is set up to sort automatically, and a sort position that has matching criteria already exists, you're automatically directed to the correct sort position.</span></span>
1. <span data-ttu-id="683be-556">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-556">Select **OK**.</span></span>
1. <span data-ttu-id="683be-557">Erősítse meg a rendezési pozíció azonosítóját, hogy jelezze, hogy a készlet a megfelelő helyen van.</span><span class="sxs-lookup"><span data-stu-id="683be-557">Confirm the sort position ID to indicate that the inventory is in the correct place.</span></span> <span data-ttu-id="683be-558">A **Rendezési pozíció azonosítója** mezőbe írja be az *SP01* értéket.</span><span class="sxs-lookup"><span data-stu-id="683be-558">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="683be-559">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-559">Select **OK**.</span></span>

    <span data-ttu-id="683be-560">A munka az 1. értékesítési rendelés második tárolóján végezhető el.</span><span class="sxs-lookup"><span data-stu-id="683be-560">Work is completed on the second container from sales order 1.</span></span> <span data-ttu-id="683be-561">Ezután a fennmaradó tárolókat a 2. értékesítési rendelésből rendezzük.</span><span class="sxs-lookup"><span data-stu-id="683be-561">You will now sort the remaining containers from sales order 2.</span></span>

1. <span data-ttu-id="683be-562">Az **Azononsítótábla/Con** mezőbe írja be annak a tárolónak az azonosítóját, amelybe a 2. értékesítési rendelés *A0001* cikkét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="683be-562">In the **LP/Con** field, enter the container ID of the container from sales order 2 that holds item *A0001*.</span></span> <span data-ttu-id="683be-563">Mivel a szállítmányozói szolgáltatás különbözik, a program kéri, hogy írjon be egy új rendezési pozíciót, és adjon hozzá egy azonosítótáblát ahhoz a pozícióhoz.</span><span class="sxs-lookup"><span data-stu-id="683be-563">Because the carrier service differs, you're prompted to enter a new sort position and assign an LP to that position.</span></span> <span data-ttu-id="683be-564">Használja az *SP02* rendezési pozíciót és a *PLP02* azonosítótáblát.</span><span class="sxs-lookup"><span data-stu-id="683be-564">Use sort position *SP02* and LP *PLP02*.</span></span>
1. <span data-ttu-id="683be-565">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-565">Select **OK**.</span></span>
1. <span data-ttu-id="683be-566">A rendezési pozíció jóváhagyásához írja be az *SP02* értéket a **Rendezési pozíció azonosítója** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="683be-566">Confirm the sort position by entering *SP02* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="683be-567">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-567">Select **OK**.</span></span>

    <span data-ttu-id="683be-568">A munka a tárolón fejeződik be.</span><span class="sxs-lookup"><span data-stu-id="683be-568">Work is completed on the container.</span></span>

1. <span data-ttu-id="683be-569">Az **Azononsítótábla/Con** mezőbe írja be a megmaradt tárolónak az azonosítóját, amelybe a 2. értékesítési rendelés *A0002* cikkét tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="683be-569">In the **LP/Con** field, enter the container ID for the remaining container from sales order 2 that holds item *A0002*.</span></span> <span data-ttu-id="683be-570">Mivel a szállítmányozói szolgáltatás ugyanaz, mint az 1. értékesítési rendelés szállítmányozói szolgáltatása, a rendszer a megfelelő feltételekkel rendelkező meglévő rendezési pozíciót jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="683be-570">Because the carrier service is the same as the carrier service for sales order 1, the system shows the existing sort position that has matching criteria.</span></span>
1. <span data-ttu-id="683be-571">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-571">Select **OK**.</span></span>
1. <span data-ttu-id="683be-572">A rendezési pozíció jóváhagyásához írja be az *SP01* értéket a **Rendezési pozíció azonosítója** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="683be-572">Confirm the sort position by entering *SP01* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="683be-573">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-573">Select **OK**.</span></span>

    <span data-ttu-id="683be-574">A munka a tárolón fejeződik be.</span><span class="sxs-lookup"><span data-stu-id="683be-574">Work is completed on the container.</span></span>

### <a name="close-the-outbound-sorting-positions"></a><span data-ttu-id="683be-575">A kimenő rendezési pozíciók lezárása</span><span class="sxs-lookup"><span data-stu-id="683be-575">Close the outbound sorting positions</span></span>

<span data-ttu-id="683be-576">Ha minden készletet rendeztek, akkor a pozíciót a munka létrehozása előtt le kell zárni.</span><span class="sxs-lookup"><span data-stu-id="683be-576">When all inventory has been sorted, the position must be closed before work can be created.</span></span> <span data-ttu-id="683be-577">A program létrehoz egy rendezett készletkitárolási-munkát, hogy a készletet a raktárajtóhoz vigye.</span><span class="sxs-lookup"><span data-stu-id="683be-577">Sorted inventory picking work will be created to take the inventory to the bay door.</span></span>

#### <a name="close-a-position-from-the-mobile-device"></a><span data-ttu-id="683be-578">Pozíció lezárása a mobileszközből</span><span class="sxs-lookup"><span data-stu-id="683be-578">Close a position from the mobile device</span></span>

1. <span data-ttu-id="683be-579">A mobileszközön jelentkezzen be a *62-es* raktárba a forgatókönyvhöz létrehozott felhasználói azonosító (vagy egy meglévő demóadat-felhasználó) használatával.</span><span class="sxs-lookup"><span data-stu-id="683be-579">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="683be-580">Válassza a főmenü **Kimenő** elemét.</span><span class="sxs-lookup"><span data-stu-id="683be-580">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="683be-581">Válassza a **Kimenő** menü **Raklap összeállítása** elemét.</span><span class="sxs-lookup"><span data-stu-id="683be-581">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="683be-582">Az **Azonosítótábla/Con** mezőbe írja be azt a tároló-azonosítót, amelyet az *SP01* rendezési pozícióhoz rendeltek.</span><span class="sxs-lookup"><span data-stu-id="683be-582">In the **LP/Con** field, enter a container ID that was sorted to sort position *SP01*.</span></span>
1. <span data-ttu-id="683be-583">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-583">Select **OK**.</span></span>
1. <span data-ttu-id="683be-584">A következő üzenet jelenik meg: „A tároló már hozzá van rendelve az SP01 pozícióhoz.</span><span class="sxs-lookup"><span data-stu-id="683be-584">You receive the following message: "The container is already sorted to position SP01.</span></span> <span data-ttu-id="683be-585">Lezárja a pozíciót?”</span><span class="sxs-lookup"><span data-stu-id="683be-585">Close the position?"</span></span> <span data-ttu-id="683be-586">Válassza **Bezárás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-586">Select **Close**.</span></span>

    <span data-ttu-id="683be-587">A munka befejeződött.</span><span class="sxs-lookup"><span data-stu-id="683be-587">Work is completed.</span></span>

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a><span data-ttu-id="683be-588">Pozíció lezárása a kimenő rendezési pozíció hozzárendeléseiből</span><span class="sxs-lookup"><span data-stu-id="683be-588">Close a position from outbound sorting position assignments</span></span>

1. <span data-ttu-id="683be-589">Nyissa meg a **Raktárkezelés \> Csomagolás és tárolólétrehozás \> Kimenő rendezésipozíció-hozzárendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-589">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="683be-590">A bal oldali oszlopban válassza ki az **SP02** elemet.</span><span class="sxs-lookup"><span data-stu-id="683be-590">In the left column, select **SP02**.</span></span> <span data-ttu-id="683be-591">Ez a kimenő rendezési pozíció sora az, amelyet le fog zárni.</span><span class="sxs-lookup"><span data-stu-id="683be-591">This outbound sorting position row is the one that you will close.</span></span>
1. <span data-ttu-id="683be-592">A műveleti ablaktáblán kattintson az **Pozíció lezárása** elemre.</span><span class="sxs-lookup"><span data-stu-id="683be-592">On the Action Pane, select **Close position**.</span></span> <span data-ttu-id="683be-593">A rendezési pozíció rekordja le van zárva, és már nem jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="683be-593">The sorting position record is closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="683be-594">Ha minden lezárt pozíció rekordját meg szeretné jeleníteni, jelölje be a **Lezártak megjelenítése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="683be-594">To show all closed position records, select the **Show closed** check box.</span></span>

### <a name="sorted-inventory-picking"></a><span data-ttu-id="683be-595">Sorba rendezett készletkitárolás</span><span class="sxs-lookup"><span data-stu-id="683be-595">Sorted inventory picking</span></span>

<span data-ttu-id="683be-596">El kell végeznie a rendezett készlet kitárolási munkafolyamatát.</span><span class="sxs-lookup"><span data-stu-id="683be-596">You must complete the sorted inventory picking work.</span></span> <span data-ttu-id="683be-597">Amikor ez befejeződött a készlet ki lesz tárolva az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="683be-597">When it's completed, the inventory will be picked to the sales order.</span></span> <span data-ttu-id="683be-598">Ekkor minden egyéb raktári folyamat érvényes.</span><span class="sxs-lookup"><span data-stu-id="683be-598">At that point, all other warehouse processes apply.</span></span>

1. <span data-ttu-id="683be-599">A mobileszközön jelentkezzen be a *62-es* raktárba a forgatókönyvhöz létrehozott felhasználói azonosító (vagy egy meglévő demóadat-felhasználó) használatával.</span><span class="sxs-lookup"><span data-stu-id="683be-599">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="683be-600">Válassza a főmenü **Kimenő** elemét.</span><span class="sxs-lookup"><span data-stu-id="683be-600">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="683be-601">Válassza a **Kimenő** menü **Rakomány rendezésből** elemét.</span><span class="sxs-lookup"><span data-stu-id="683be-601">On the **Outbound** menu, select **Load from Sorting**.</span></span>
1. <span data-ttu-id="683be-602">Adja meg a cél Azonosítótábla azonosítóját az első rendezési pozícióból, az *SP01*-ből.</span><span class="sxs-lookup"><span data-stu-id="683be-602">Enter the target LP ID from the first sort position, *SP01*.</span></span> <span data-ttu-id="683be-603">Állítsa az **Azonosító** mezőt *PLP01* értékre.</span><span class="sxs-lookup"><span data-stu-id="683be-603">Set the **ID** field to *PLP01*.</span></span>
1. <span data-ttu-id="683be-604">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-604">Select **OK**.</span></span>
1. <span data-ttu-id="683be-605">A **Rendezett készlet kitárolása: kitárolás** lap megjeleníti a kitárolási munkát, amelyet el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="683be-605">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="683be-606">Válassza ki a *SORT* helyet, és a cél *PLP01* azonosítótáblát, amely több cikket és *3* mennyiséget tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="683be-606">Pick from the *SORT* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="683be-607">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-607">Select **OK**.</span></span>
1. <span data-ttu-id="683be-608">A **Rendezett készlet kitárolása: betárolás** lap megjeleníti a betárolási munkát, amelyet el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="683be-608">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="683be-609">Tároljon be a *Baydoor* helyre, és a cél *PLP01* azonosítótáblát, amely több cikket és *3* mennyiséget tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="683be-609">Put to the *Baydoor* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="683be-610">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-610">Select **OK**.</span></span>

    <span data-ttu-id="683be-611">A munka befejeződött.</span><span class="sxs-lookup"><span data-stu-id="683be-611">Work is completed.</span></span>

1. <span data-ttu-id="683be-612">Adja meg a cél azonosítótábla azonosítóját a második rendezési pozícióból, az *SP02*-ből.</span><span class="sxs-lookup"><span data-stu-id="683be-612">Enter the target license plate ID from the second sort position, *SP02*.</span></span> <span data-ttu-id="683be-613">Állítsa az **Azonosító** mezőt *PLP02* értékre.</span><span class="sxs-lookup"><span data-stu-id="683be-613">Set the **ID** field to *PLP02*.</span></span>
1. <span data-ttu-id="683be-614">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-614">Select **OK**.</span></span>
1. <span data-ttu-id="683be-615">A **Rendezett készlet kitárolása: kitárolás** lap megjeleníti a kitárolási munkát, amelyet el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="683be-615">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="683be-616">Válassza ki a *SORT* helyet, és a cél *PLP02* azonosítótáblát, amely több cikket és *1* mennyiséget tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="683be-616">Pick from the *SORT* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="683be-617">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-617">Select **OK**.</span></span>
1. <span data-ttu-id="683be-618">A **Rendezett készlet kitárolása: betárolás** lap megjeleníti a betárolási munkát, amelyet el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="683be-618">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="683be-619">Tároljon be a *Baydoor* helyre, és a cél *PLP02* azonosítótáblát, amely több cikket és *1* mennyiséget tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="683be-619">Put to the *Baydoor* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="683be-620">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="683be-620">Select **OK**.</span></span>

    <span data-ttu-id="683be-621">A munka befejeződött.</span><span class="sxs-lookup"><span data-stu-id="683be-621">Work is completed.</span></span>

<span data-ttu-id="683be-622">Ekkortól minden egyéb raktári folyamat érvényes.</span><span class="sxs-lookup"><span data-stu-id="683be-622">From this point forward, all other warehouse processes apply.</span></span>
