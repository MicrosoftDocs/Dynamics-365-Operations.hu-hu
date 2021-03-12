---
title: Falhoz helyez – üzletbe helyez
description: Ez a témakör Falhoz helyez – üzletbe helyez funkciót ismerteti. Ez a funkció lehetővé teszi olyan esetek kezelését, amikor konfigurálható feltételek alapján kell konszolidálni egy termékeket egy előrecsomagolt előkészítő területre. Segít csökkenteni a kitárolási időt, mivel ez lehetővé teszi a kitárolást egyetlen cél azonosítótáblára, és a fürtök kitárolásánál több betárolási pozíciót is alkalmazhat.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 3f2ae63758fcb6247c5e56433645d9252576c755
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996275"
---
# <a name="put-to-wall---put-to-store"></a><span data-ttu-id="97c1c-105">Falhoz helyez – üzletbe helyez</span><span class="sxs-lookup"><span data-stu-id="97c1c-105">Put to wall - put to store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97c1c-106">A *Falhoz helyez – üzletbe helyez* funkció lehetővé teszi olyan esetek kezelését, amikor konfigurálható feltételek alapján kell konszolidálni egy termékeket egy előrecsomagolt előkészítő területre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-106">The *Put to wall - put to store* functionality lets you handle scenarios where you must consolidate a product to a prepack staging area, based on configurable criteria.</span></span> <span data-ttu-id="97c1c-107">Mivel ez a funkció lehetővé teszi a kitárolást egyetlen cél azonosítótáblára, és több betárolási pozíciót is alkalmazhat, mint a fürtök kitárolása esetén, az üzletekbe szállító vagy kis cikkeket kezelő vállalatok számára előnyös a lecsökkent kitárolási idő.</span><span class="sxs-lookup"><span data-stu-id="97c1c-107">Because this functionality allows for picking to a single target license plate and can use more put positions than cluster picking, companies that ship to stores or handle small items will benefit from decreased picking time.</span></span>

<span data-ttu-id="97c1c-108">A funkció munkafolyamata egy rendezési helyre irányítja a kitárolt terméket a különböző típusú tárolókba történő elosztásra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-108">The workflow for this functionality directs picked product to a sorting location for distribution into various types of containers.</span></span> <span data-ttu-id="97c1c-109">A rendezési helyek általában több különböző rendezési pozíciót is tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="97c1c-109">Generally, each sorting location includes multiple sort positions.</span></span> <span data-ttu-id="97c1c-110">Minden rendezési pozíció az üzleti folyamat által meghatározott feltételek szerint van hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="97c1c-110">Each sort position is assigned according to the criteria that are set by the business process.</span></span> <span data-ttu-id="97c1c-111">A jellemző feltételek a végső rendeltetési hely, szállítmány vagy rakomány.</span><span class="sxs-lookup"><span data-stu-id="97c1c-111">Typical criteria are the final destination, shipment, or load.</span></span> <span data-ttu-id="97c1c-112">A termék beérkezésekor az el lesz osztva az egyes rendezési pozíciókhoz a rendeléshez társított mennyiség, a célállomás, a szállítmány vagy rakomány alapján.</span><span class="sxs-lookup"><span data-stu-id="97c1c-112">After a product arrives, it's distributed to each sort position, based on the quantity that is associated with the order, destination, shipment, or load.</span></span> <span data-ttu-id="97c1c-113">Ha egy tároló megtelt vagy teljes, akkor a program az üzleti folyamattól függően egy előkészítési helyre vagy egy szállítási helyre helyezi át a további kezelésre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-113">When a container is full or complete, it's moved to a staging location or a shipping location for further handling, depending on the business process.</span></span>

<span data-ttu-id="97c1c-114">Ezt a raktározási funkciót más néven is említik, például „pu-to-light” vagy „break opens”.</span><span class="sxs-lookup"><span data-stu-id="97c1c-114">This warehousing functionality is also referred to by other names, such as put-to-light and break opens.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="97c1c-115">A Kimenő rendezés funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="97c1c-115">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="97c1c-116">A *Falhoz helyez – üzletbe helyez* funkció használata előtt be kell kapcsolni a *Kimenő rendezés* funkciót a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="97c1c-116">Before you can use the *Put to wall - put to store* functionality, the *Outbound sorting* feature must be turned on in your system.</span></span> <span data-ttu-id="97c1c-117">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="97c1c-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="97c1c-118">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="97c1c-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="97c1c-119">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="97c1c-120">**Szolgáltatás neve:** *Kimenő rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-120">**Feature name:** *Outbound sorting*</span></span>

<span data-ttu-id="97c1c-121">Ha be van kapcsolva, a *Kimenő rendezés* funkció együtt használható a *Szervezeti szintű hullámlépéskód* funkcióval.</span><span class="sxs-lookup"><span data-stu-id="97c1c-121">The *Outbound sorting* feature can be used in conjunction with the *Organization wide wave step code* feature if it's turned on.</span></span> <span data-ttu-id="97c1c-122">Akkor is be kell kapcsolnia ezt a funkciót, ha a hullámlépéskódokban található előre meghatározott lépéskódokat fogja használni.</span><span class="sxs-lookup"><span data-stu-id="97c1c-122">You must also turn on this feature if you will use predefined codes that are set up in wave step codes.</span></span> <span data-ttu-id="97c1c-123">A **Funkció kezelése** munkaterületen ez a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="97c1c-123">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="97c1c-124">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="97c1c-125">**Funkció neve:** *Szervezeti szintű hullámlépéskód*</span><span class="sxs-lookup"><span data-stu-id="97c1c-125">**Feature name:** *Organization wide wave step code*</span></span>

## <a name="setup"></a><span data-ttu-id="97c1c-126">Beállítás</span><span class="sxs-lookup"><span data-stu-id="97c1c-126">Setup</span></span>

<span data-ttu-id="97c1c-127">Ehhez a demóhoz a szabványos Contoso-adatok és a *62-es* raktár használatos.</span><span class="sxs-lookup"><span data-stu-id="97c1c-127">For this demo, standard Contoso data and warehouse *62* are used.</span></span> <span data-ttu-id="97c1c-128">Néhány később említett kiegészítő is használatban van.</span><span class="sxs-lookup"><span data-stu-id="97c1c-128">Some additions that are noted later are also used.</span></span>

### <a name="location-type"></a><span data-ttu-id="97c1c-129">Hely típusa</span><span class="sxs-lookup"><span data-stu-id="97c1c-129">Location type</span></span>

1. <span data-ttu-id="97c1c-130">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helytípusok** pontra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-130">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="97c1c-131">A művelet ablaktáblán válassza az **Új** parancsot a rendezéshez használandó új helytípus létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="97c1c-131">On the Action Pane, select **New** to create a location type for sorting.</span></span>
1. <span data-ttu-id="97c1c-132">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-132">Set the following values:</span></span>

    - <span data-ttu-id="97c1c-133">**Hely típusa:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="97c1c-133">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="97c1c-134">**Leírás:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-134">**Description:** *Sort*</span></span>

1. <span data-ttu-id="97c1c-135">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-135">Select **Save**.</span></span>

### <a name="warehouse-management-parameters"></a><span data-ttu-id="97c1c-136">Raktárkezelési paraméterek</span><span class="sxs-lookup"><span data-stu-id="97c1c-136">Warehouse management parameters</span></span>

1. <span data-ttu-id="97c1c-137">Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-137">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="97c1c-138">Az **Általános** lap **Helytípusok** gyorslapján állítsa be a **Rendezési hely típusa** mezőt *SORT* értékre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-138">On the **General** tab, on the **Location types** FastTab, in the **Sorting location type** field, enter *SORT*.</span></span>
1. <span data-ttu-id="97c1c-139">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-139">Select **Save**.</span></span>

### <a name="location-profile"></a><span data-ttu-id="97c1c-140">Helyprofil</span><span class="sxs-lookup"><span data-stu-id="97c1c-140">Location profile</span></span>

1. <span data-ttu-id="97c1c-141">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-141">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="97c1c-142">A művelet ablaktáblán válassza az **Új** parancsot a rendezési hely új helyprofiljának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="97c1c-142">On the Action Pane, select **New** to create a location profile for the sorting location.</span></span>
1. <span data-ttu-id="97c1c-143">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-143">In the header, set the following values:</span></span>

    - <span data-ttu-id="97c1c-144">**Helyprofil azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-144">**Location profile ID:** *Sort*</span></span>
    - <span data-ttu-id="97c1c-145">**Név:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-145">**Name:** *Sort*</span></span>

1. <span data-ttu-id="97c1c-146">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-146">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="97c1c-147">**Helyformátum:** *PACK*</span><span class="sxs-lookup"><span data-stu-id="97c1c-147">**Location format:** *PACK*</span></span>
    - <span data-ttu-id="97c1c-148">**Hely típusa:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="97c1c-148">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="97c1c-149">**Azonosítótábla-követés használata:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="97c1c-149">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="97c1c-150">**Vegyes cikkek engedélyezése:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="97c1c-150">**Allow mixed items:** *Yes*</span></span>
    - <span data-ttu-id="97c1c-151">**Vegyes készletállapotok engedélyezése:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="97c1c-151">**Allow mixed inventory statuses:** *Yes*</span></span>

1. <span data-ttu-id="97c1c-152">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-152">Select **Save**.</span></span>

### <a name="locations"></a><span data-ttu-id="97c1c-153">Helyek</span><span class="sxs-lookup"><span data-stu-id="97c1c-153">Locations</span></span>

1. <span data-ttu-id="97c1c-154">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyek pontra**.</span><span class="sxs-lookup"><span data-stu-id="97c1c-154">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="97c1c-155">Törölje a jelet az **Ellenőrző számjegyek létrehozása a helyhez** jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="97c1c-155">Clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="97c1c-156">A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-156">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="97c1c-157">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="97c1c-157">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="97c1c-158">**Hely:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-158">**Location:** *Sort*</span></span>
    - <span data-ttu-id="97c1c-159">**Helyprofil azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-159">**Location profile ID:** *Sort*</span></span>

1. <span data-ttu-id="97c1c-160">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-160">Select **Save**.</span></span>

### <a name="packing-profiles"></a><span data-ttu-id="97c1c-161">Csomagolási profilok</span><span class="sxs-lookup"><span data-stu-id="97c1c-161">Packing profiles</span></span>

1. <span data-ttu-id="97c1c-162">Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Csomagolási profilok** pontra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-162">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="97c1c-163">A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-163">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="97c1c-164">**Csomagolási profil azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-164">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="97c1c-165">**Leírás:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-165">**Description:** *Sort*</span></span>
    - <span data-ttu-id="97c1c-166">**Tároló csomagolási házirendje:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="97c1c-166">**Container packing policy:** Leave this field blank.</span></span>
    - <span data-ttu-id="97c1c-167">**Tároló-azonosító mód:** *Automatikus*</span><span class="sxs-lookup"><span data-stu-id="97c1c-167">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="97c1c-168">**Tároló típusa:** *PALLET 48X48*</span><span class="sxs-lookup"><span data-stu-id="97c1c-168">**Container type:** *PALLET 48X48*</span></span>
    - <span data-ttu-id="97c1c-169">**Tároló automatikus létrehozása a tároló zárásakor:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="97c1c-169">**Autocreate container at container close:** Leave this field blank.</span></span>

1. <span data-ttu-id="97c1c-170">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-170">Select **Save**.</span></span>

### <a name="wave-step-codes"></a><span data-ttu-id="97c1c-171">Hullámlépéskódok</span><span class="sxs-lookup"><span data-stu-id="97c1c-171">Wave step codes</span></span>

<span data-ttu-id="97c1c-172">Ha be van kapcsolva a *Szervezeti szintű hullámlépéskód:* funkció, állítsa be a következő kódot.</span><span class="sxs-lookup"><span data-stu-id="97c1c-172">If you turned on the *Organization wide wave step code* feature, set up the following code.</span></span>

1. <span data-ttu-id="97c1c-173">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámlépéskódok** pontra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-173">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="97c1c-174">A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-174">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="97c1c-175">**Hullámlépés kódja:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-175">**Wave step code:** *Sort*</span></span>
    - <span data-ttu-id="97c1c-176">**Hullámlépés leírása:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-176">**Wave step description:** *Sort*</span></span>
    - <span data-ttu-id="97c1c-177">**Hullámlépés típusa:** *Rendezési sablon*</span><span class="sxs-lookup"><span data-stu-id="97c1c-177">**Wave step type:** *Sort template*</span></span>

1. <span data-ttu-id="97c1c-178">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-178">Select **Save**.</span></span>

### <a name="outbound-sorting-template"></a><span data-ttu-id="97c1c-179">Kimenő rendezési sablon</span><span class="sxs-lookup"><span data-stu-id="97c1c-179">Outbound sorting template</span></span>

<span data-ttu-id="97c1c-180">A rendezési sablon határozza meg, hogy a rendezési pozíciók létrejönnek-e, milyen feltételek vannak használatban, valamint a rendezési folyamat egyéb attribútumait.</span><span class="sxs-lookup"><span data-stu-id="97c1c-180">The sorting template controls whether sort positions are created, what criteria are used, and other attributes of the sorting process.</span></span>

1. <span data-ttu-id="97c1c-181">Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Kimenő rendezési sablonok** helyre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-181">Go to **Warehouse management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="97c1c-182">Jelölje be a műveleti ablakban az **Új** lehetőséget a rendezési sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="97c1c-182">On the Action Pane, select **New** to create a sorting template.</span></span>
1. <span data-ttu-id="97c1c-183">Az új sablon fejlécében adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-183">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="97c1c-184">**Kimenő rendezési sablon azonosítója:** *Hullámrendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-184">**Outbound sorting template ID:** *Wave Sort*</span></span>
    - <span data-ttu-id="97c1c-185">**Leírás:** *Hullámrendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-185">**Description:** *Wave sort*</span></span>
    - <span data-ttu-id="97c1c-186">**Rendezési sablon típusa:** *Hullámigény*</span><span class="sxs-lookup"><span data-stu-id="97c1c-186">**Sort template type:** *Wave demand*</span></span>

        <span data-ttu-id="97c1c-187">Ez a mező azt a folyamatot határozza meg, amelyhez a rendezési sablon használatban van.</span><span class="sxs-lookup"><span data-stu-id="97c1c-187">This field defines the process that the sorting template is used for.</span></span> <span data-ttu-id="97c1c-188">A következő értékek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="97c1c-188">The following values are available:</span></span>

        - <span data-ttu-id="97c1c-189">**Hullámigény** – Ez a rendezési sablon a *Falhoz helyez* folyamathoz használatos.</span><span class="sxs-lookup"><span data-stu-id="97c1c-189">**Wave demand** – The sorting template is used for the *Put to wall* process.</span></span> <span data-ttu-id="97c1c-190">Ez a sablontípus a csomagolási állomás kihagyására szolgál, és közvetlenül a hullámból dolgozza fel a készletet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-190">This template type is used to bypass the pack station and process inventory directly out of the wave.</span></span> <span data-ttu-id="97c1c-191">Ez a típus csak akkor használható, ha a hullámsablonban szerepel a **rendezés** hullámfeldolgozási mód.</span><span class="sxs-lookup"><span data-stu-id="97c1c-191">You can use this type only if the **sorting** wave process method is included in the wave template.</span></span>
        - <span data-ttu-id="97c1c-192">**Tároló** – A rendezési sablon, amely a *Raklapösszeállítás csomagolás után* folyamathoz használatos.</span><span class="sxs-lookup"><span data-stu-id="97c1c-192">**Container** – The sorting template is used for the *Pallet building after packing* process.</span></span> <span data-ttu-id="97c1c-193">Ezt a sablontípust olyan tárolók feldolgozására használják, amelyek az adott csomagolóhelyen le vannak zárva, és raklapokra kell rendezni őket.</span><span class="sxs-lookup"><span data-stu-id="97c1c-193">This template type is used to process containers that are closed at the pack station and must be sorted onto pallets.</span></span>

    - <span data-ttu-id="97c1c-194">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="97c1c-194">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="97c1c-195">**Hely:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-195">**Location:** *Sort*</span></span>

1. <span data-ttu-id="97c1c-196">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-196">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="97c1c-197">**Rendezés ellenőrzés:** *Pozíció beolvasása*</span><span class="sxs-lookup"><span data-stu-id="97c1c-197">**Sort verification:** *Position scan*</span></span>

        <span data-ttu-id="97c1c-198">Ez a mező határozza meg a rendezés során szükséges ellenőrzést.</span><span class="sxs-lookup"><span data-stu-id="97c1c-198">This field defines the verification that is required during sorting.</span></span> <span data-ttu-id="97c1c-199">A következő értékek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="97c1c-199">The following values are available:</span></span>

        - <span data-ttu-id="97c1c-200">None</span><span class="sxs-lookup"><span data-stu-id="97c1c-200">None</span></span>
        - <span data-ttu-id="97c1c-201">Azonosítótábla beolvasása</span><span class="sxs-lookup"><span data-stu-id="97c1c-201">License plate scan</span></span>
        - <span data-ttu-id="97c1c-202">Pozíció beolvasása</span><span class="sxs-lookup"><span data-stu-id="97c1c-202">Position scan</span></span>

    - <span data-ttu-id="97c1c-203">**Munka létrehozása a pozíció lezárásakor:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="97c1c-203">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="97c1c-204">Ha ennek a beállításnak az értéke *Igen* akkor munka jön létre, amikor a pozíció le van zárva, hogy a készletet a végső szállítási helyre mozgassák.</span><span class="sxs-lookup"><span data-stu-id="97c1c-204">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="97c1c-205">Ha *Nem* értékre van állítva, akkor a készletet azonnal kitárolják a rendeléshez a pozíció lezárásakor.</span><span class="sxs-lookup"><span data-stu-id="97c1c-205">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="97c1c-206">**Pozíció hozzárendelése:** *Manuális*</span><span class="sxs-lookup"><span data-stu-id="97c1c-206">**Position assignment:** *Manual*</span></span>

        <span data-ttu-id="97c1c-207">Ez a mező a pozíció-hozzárendelés típusát határozza meg.</span><span class="sxs-lookup"><span data-stu-id="97c1c-207">This field defines the type of position assignment.</span></span> <span data-ttu-id="97c1c-208">A következő értékek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="97c1c-208">The following values are available:</span></span>

        - <span data-ttu-id="97c1c-209">**Manuális** – A felhasználónak mindig meg kell adnia, a készlet melyik pozíciójához kell rendezni.</span><span class="sxs-lookup"><span data-stu-id="97c1c-209">**Manual** – The user must always indicate which position the inventory should be sorted to.</span></span>
        - <span data-ttu-id="97c1c-210">**Automatikus** – A rendszer automatikusan egy pozícióhoz irányítja a készletet, ha lehetséges, a rendezési sablontörések alapján.</span><span class="sxs-lookup"><span data-stu-id="97c1c-210">**Automatic** – The system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

    - <span data-ttu-id="97c1c-211">**Rendezésipozíció-feltétel hozzárendelése:** *Csak üres pozíció használata*</span><span class="sxs-lookup"><span data-stu-id="97c1c-211">**Assign sort position criteria:** *Only use empty position*</span></span>

        <span data-ttu-id="97c1c-212">Ez a mező azt szabályozza, hogy a rendezési pozícióknál már meglévő készletet figyelembe kell-e venni egy pozíció igényhez való hozzárendelésekor.</span><span class="sxs-lookup"><span data-stu-id="97c1c-212">This field controls whether inventory that is already present on sort positions is taken into account when a position is assigned for the demand.</span></span> <span data-ttu-id="97c1c-213">A következő értékek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="97c1c-213">The following values are available:</span></span>

        - <span data-ttu-id="97c1c-214">**Csak üres pozíció használata** – Az olyan pozíciók, amelyekhez már van készlet társítva figyelembe lesznek véve</span><span class="sxs-lookup"><span data-stu-id="97c1c-214">**Only use empty position** – Positions that already have inventory associated with them will be taken into account</span></span>
        - <span data-ttu-id="97c1c-215">**Ürespozíció feltételezése** – A pozícióban már szereplő összes készletet figyelmen kívül hagyja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="97c1c-215">**Assume position empty** – Any inventory that is already on the position will be disregarded during assignment.</span></span> <span data-ttu-id="97c1c-216">Minden rendelkezésre álló pozíció használva lesz.</span><span class="sxs-lookup"><span data-stu-id="97c1c-216">All available positions will be used.</span></span>

    - <span data-ttu-id="97c1c-217">**Hullámlépés kódja:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-217">**Wave step code:** *Sort*</span></span>

        <span data-ttu-id="97c1c-218">Ha be van kapcsolva a *Szervezeti szintű hullámlépéskód* funkció, akkor a *Rendezés* hullámlépéskódot is be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="97c1c-218">If the *Organization wide wave step code* feature is turned on, the *Sort* wave step code must also be set up in wave step codes.</span></span>

    - <span data-ttu-id="97c1c-219">**Rendezési pozíció automatikus lezárása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="97c1c-219">**Auto close sort position:** *Yes*</span></span>

        <span data-ttu-id="97c1c-220">Ha ez a beállítás *Igen* értékre van állítva akkor a program automatikusan lezárja a rendezési pozíciót, amikor a pozícióhoz érkező összes munka be van fejezve.</span><span class="sxs-lookup"><span data-stu-id="97c1c-220">If this option is set to *Yes*, the sort position will automatically be closed when all work that comes to the position has been completed.</span></span>

    - <span data-ttu-id="97c1c-221">**Rendezési pozíciók száma:** *3*</span><span class="sxs-lookup"><span data-stu-id="97c1c-221">**Number of sort positions:** *3*</span></span>

        <span data-ttu-id="97c1c-222">Ez a mező határozza meg a rendszer által létrehozott rendezési pozíciók maximális számát.</span><span class="sxs-lookup"><span data-stu-id="97c1c-222">This field defines the maximum number of sort positions that the system will create.</span></span>

    - <span data-ttu-id="97c1c-223">**Rendezési pozíció előtagja:** *SP-*</span><span class="sxs-lookup"><span data-stu-id="97c1c-223">**Sort position prefix:** *SP-*</span></span>

        <span data-ttu-id="97c1c-224">Ez a mező határozza meg, hogy melyik előtagot rendeli hozzá a rendszer a pozíció száma elé.</span><span class="sxs-lookup"><span data-stu-id="97c1c-224">This field defines the prefix that the system assigns before the position number.</span></span>

    - <span data-ttu-id="97c1c-225">**Rendezési pozíció automatikus csomagolása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="97c1c-225">**Auto pack sort position:** *Yes*</span></span>

        <span data-ttu-id="97c1c-226">Ha ez a beállítás *Igen* értékre van állítva, akkor a program a rendezési pozíció készletét egy tárolóba csomagolja, amikor a pozíció le van zárva.</span><span class="sxs-lookup"><span data-stu-id="97c1c-226">If this option is set to *Yes*, the inventory on the sort position will be packed into a container when the position is closed.</span></span>

    - <span data-ttu-id="97c1c-227">**Csomagolási profil azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-227">**Packing profile ID:** *Sort*</span></span>

        <span data-ttu-id="97c1c-228">Ez a mező határozza meg a csomagolási profilt, amelyet akkor kell használni, amikor a rendezési pozíciót egy tárolóba csomagolják.</span><span class="sxs-lookup"><span data-stu-id="97c1c-228">This field defines the packing profile that will be used when the sort position is packed into a container.</span></span>

1. <span data-ttu-id="97c1c-229">A művelet ablaktáblán válassza a **Lekérdezés szerkesztése** elemet a rendezési sablonhoz használt feltételek megadásához.</span><span class="sxs-lookup"><span data-stu-id="97c1c-229">On the Action Pane, select **Edit query** to specify the criteria that are used for this sorting template.</span></span>
1. <span data-ttu-id="97c1c-230">A lekérdezés párbeszédpanel **Rendezés** lapján válassza az **Új** parancsot egy sor hozzáadásához, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-230">In the query dialog box, on the **Sorting** tab, select **New** to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="97c1c-231">**Tábla:** *Rakomány részletei*</span><span class="sxs-lookup"><span data-stu-id="97c1c-231">**Table:** *Load details*</span></span>
    - <span data-ttu-id="97c1c-232">**Származtatott tábla:** *Rakomány részletei*</span><span class="sxs-lookup"><span data-stu-id="97c1c-232">**Derived table:** *Load details*</span></span>
    - <span data-ttu-id="97c1c-233">**Mező:** *Szállítmány azonosítója*</span><span class="sxs-lookup"><span data-stu-id="97c1c-233">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="97c1c-234">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="97c1c-234">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="97c1c-235">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-235">Select **OK**.</span></span>
1. <span data-ttu-id="97c1c-236">A következő üzenet jelenhet meg: „A csoportosítás alaphelyzetbe kerül, folytatja?”</span><span class="sxs-lookup"><span data-stu-id="97c1c-236">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="97c1c-237">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-237">Select **Yes**.</span></span>

    <span data-ttu-id="97c1c-238">Elérhetővé válik a **A kimenő rendezési sablonok szünetei** gomb a műveleti panelen.</span><span class="sxs-lookup"><span data-stu-id="97c1c-238">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="97c1c-239">A műveleti ablaktáblán válassza ki a **Kimenő rendezési sablon szünetekei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-239">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="97c1c-240">Válassza ki a **Csoportosítás mező szerint** mezőt a csoportosításhoz szállítmányazonosító szerint.</span><span class="sxs-lookup"><span data-stu-id="97c1c-240">Select the **Group by field** check box to group by shipment ID.</span></span>

    <span data-ttu-id="97c1c-241">Ez a beállítás szállítmányként egy rendezési pozíciót hoz létre, amely a hullámban tárolóként jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="97c1c-241">This setting will create one sort position per shipment that is a container in the wave.</span></span>

1. <span data-ttu-id="97c1c-242">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-242">Select **OK**.</span></span>

### <a name="wave-process-methods"></a><span data-ttu-id="97c1c-243">Hullámfeldolgozási módok</span><span class="sxs-lookup"><span data-stu-id="97c1c-243">Wave process methods</span></span>

1. <span data-ttu-id="97c1c-244">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-244">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="97c1c-245">A Művelet ablaktáblán válassza ki a **Metódusok újragenerálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-245">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="97c1c-246">A **rendezési** módszert a program hozzáadta a választható metódusok listájához, és *Szállítás* hullámsablontípus van kiválasztva hozzá.</span><span class="sxs-lookup"><span data-stu-id="97c1c-246">The **sorting** method is added to the list of available methods, and the *Shipping* wave template type is selected for it.</span></span>

### <a name="wave-templates"></a><span data-ttu-id="97c1c-247">Hullámsablonok</span><span class="sxs-lookup"><span data-stu-id="97c1c-247">Wave templates</span></span>

<span data-ttu-id="97c1c-248">A hullámigény rendezéséhez használt hullámsablon szerkesztése.</span><span class="sxs-lookup"><span data-stu-id="97c1c-248">Edit the wave template that is used for wave demand sorting.</span></span>

1. <span data-ttu-id="97c1c-249">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-249">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="97c1c-250">A **Hullámsablontípus** mezőt állítsa *Szállítás* értékre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-250">In the **Wave template type** field, select *Shipping*.</span></span>
1. <span data-ttu-id="97c1c-251">Válassza ki a meglévő **62 Szállítási alapértelmezett** sablont.</span><span class="sxs-lookup"><span data-stu-id="97c1c-251">Select the existing **62 Shipping default** template.</span></span>
1. <span data-ttu-id="97c1c-252">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-252">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="97c1c-253">Az **Általános** gyorslapon végezze el a következő módosításokat:</span><span class="sxs-lookup"><span data-stu-id="97c1c-253">On the **General** FastTab, make the following changes:</span></span>

    - <span data-ttu-id="97c1c-254">Állítsa a **Hullám feldolgozása a raktárba történő kiadáskor** lehetőséget *Nem* értékre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-254">Set the **Process wave at release to warehouse** option to *No*.</span></span>
    - <span data-ttu-id="97c1c-255">Állítsa a **Hozzárendelés nyitott hullámokhoz** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-255">Set the **Assign to open waves** option to *Yes*.</span></span>

1. <span data-ttu-id="97c1c-256">A **Metódusok** gyorslapon állítsa be a **rendezés** metódust:</span><span class="sxs-lookup"><span data-stu-id="97c1c-256">On the **Methods** FastTab, set up the **sorting** method:</span></span>

    1. <span data-ttu-id="97c1c-257">A **Fennmaradó metódusok** rácsban válassza a **rendezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-257">In the **Remaining Methods** grid, select **sorting**.</span></span>
    2. <span data-ttu-id="97c1c-258">Válassza ki a jobbra nyíl gombot, hogy a **rendezés** elemet áthelyezze a **Kiválasztott metódusok** rácsra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-258">Select the right arrow button to move **sorting** to the **Selected Methods** grid.</span></span>
    3. <span data-ttu-id="97c1c-259">A **Kiválasztott metódusok** rácsban válassza a **rendezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-259">In the **Selected Methods** grid, select **sorting**.</span></span>
    4. <span data-ttu-id="97c1c-260">A **Hullámlépéskód** mezőt állítsa *Rendezés* értékre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-260">Set the **Wave step code** field to *Sort*.</span></span>

1. <span data-ttu-id="97c1c-261">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-261">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="97c1c-262">Mobileszköz menüpontjai</span><span class="sxs-lookup"><span data-stu-id="97c1c-262">Mobile device menu items</span></span>

1. <span data-ttu-id="97c1c-263">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-263">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="97c1c-264">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-264">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="97c1c-265">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-265">In the header, set the following values:</span></span>

    - <span data-ttu-id="97c1c-266">**Menüelem neve:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-266">**Menu item name:** *Sort*</span></span>
    - <span data-ttu-id="97c1c-267">**Cím:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-267">**Title:** *Sort*</span></span>
    - <span data-ttu-id="97c1c-268">**Mód:** *Közvetett*</span><span class="sxs-lookup"><span data-stu-id="97c1c-268">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="97c1c-269">**Meglévő munka használata:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="97c1c-269">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="97c1c-270">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-270">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="97c1c-271">**Tevékenységkód:** *Kimenő rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-271">**Activity code:** *Outbound sorting*</span></span>
    - <span data-ttu-id="97c1c-272">**Feldolgozási útmutató használata:** *Igen* (alapértelmezett érték)</span><span class="sxs-lookup"><span data-stu-id="97c1c-272">**Use process guide:** *Yes* (default value)</span></span>
    - <span data-ttu-id="97c1c-273">**Kimenő rendezési sablon azonosítója:** *Hullámrendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-273">**Outbound sorting template ID:** *Wave Sort*</span></span>

1. <span data-ttu-id="97c1c-274">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-274">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="97c1c-275">Mobileszköz menü</span><span class="sxs-lookup"><span data-stu-id="97c1c-275">Mobile device menu</span></span>

1. <span data-ttu-id="97c1c-276">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-276">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="97c1c-277">A menük listáján válassza a **Kimenő** elemet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-277">In the list of menus, select **Outbound**.</span></span>
1. <span data-ttu-id="97c1c-278">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-278">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="97c1c-279">A **Rendelkezésre álló menük és menüelemek** rácsban keresse meg és válassza ki az imént létrehozott **Rendezés** menüelemet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-279">In the **Available Menus And Menu Items** grid, find and select the **Sort** menu item that you just created.</span></span>
1. <span data-ttu-id="97c1c-280">Válassza a jobbra mutató nyilat a **Rendezés** áthelyezéséhez a **Menü struktúra** rácsba.</span><span class="sxs-lookup"><span data-stu-id="97c1c-280">Select the right arrow button to move **Sort** to the **Menu Structure** grid.</span></span> <span data-ttu-id="97c1c-281">Ily módon hozzáadja az új menüelemet a **Kimenő** menühöz.</span><span class="sxs-lookup"><span data-stu-id="97c1c-281">In this way, you add the menu item to the **Outbound** menu.</span></span>
1. <span data-ttu-id="97c1c-282">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-282">Select **Save**.</span></span>

### <a name="location-directives"></a><span data-ttu-id="97c1c-283">Helyutasítások</span><span class="sxs-lookup"><span data-stu-id="97c1c-283">Location directives</span></span>

<span data-ttu-id="97c1c-284">Létre kell hoznia egy helyirányelvet a rendezés befejezését követően létrejövő munka irányításához.</span><span class="sxs-lookup"><span data-stu-id="97c1c-284">You must create location directives to guide the work that is created after the sorting is completed.</span></span>

1. <span data-ttu-id="97c1c-285">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-285">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="97c1c-286">A **Munkarendelés típusa** mezőben válassza ki a *Rendezett készletkitárolás* elemet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-286">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="97c1c-287">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-287">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="97c1c-288">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-288">In the header, set the following values:</span></span>

    - <span data-ttu-id="97c1c-289">**Sorozat:** *1*</span><span class="sxs-lookup"><span data-stu-id="97c1c-289">**Sequence:** *1*</span></span>
    - <span data-ttu-id="97c1c-290">**Név:** *Kitárolás raktárajtóhoz*</span><span class="sxs-lookup"><span data-stu-id="97c1c-290">**Name:** *Put to Baydoor*</span></span>

1. <span data-ttu-id="97c1c-291">A **Helyutasítások** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-291">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="97c1c-292">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="97c1c-292">**Work type:** *Put*</span></span>
    - <span data-ttu-id="97c1c-293">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="97c1c-293">**Site:** *6*</span></span>
    - <span data-ttu-id="97c1c-294">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="97c1c-294">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="97c1c-295">**Utasításkód:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="97c1c-295">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="97c1c-296">**Több termékváltozat:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="97c1c-296">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="97c1c-297">A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="97c1c-297">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="97c1c-298">Válassza a **Sorok** gyorslap **Új** elemét, majd állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="97c1c-298">On the **Lines** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="97c1c-299">Az összes többi mezőben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="97c1c-299">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="97c1c-300">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="97c1c-300">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="97c1c-301">**Kezdő mennyiség:** *0*</span><span class="sxs-lookup"><span data-stu-id="97c1c-301">**From quantity:** *0*</span></span>
    - <span data-ttu-id="97c1c-302">**Záró mennyiség:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="97c1c-302">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="97c1c-303">A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="97c1c-303">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="97c1c-304">Válassza a **Helyutasítás-műveletek** gyorslap **Új** elemét, majd állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="97c1c-304">On the **Location Directive Actions** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="97c1c-305">Az összes többi mezőben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="97c1c-305">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="97c1c-306">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="97c1c-306">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="97c1c-307">**Név:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="97c1c-307">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="97c1c-308">A **Mentés** gombra kattintva teheti elérhetővé a **Lekérdezés szerkesztése** gombot a **Helyutasítások műveletei** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="97c1c-308">Select **Save** to make the **Edit query** button on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="97c1c-309">A **Helyutasítás műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-309">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="97c1c-310">A lekérdezési párbeszédpanel **Tartomány** lapján keresse meg azt a sort, amelynél a **Mező** mező értéke *Hely*.</span><span class="sxs-lookup"><span data-stu-id="97c1c-310">In the query dialog box, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="97c1c-311">Ennek a sornak a **Feltételek** mezőjét állítsa *Baydoor* értékre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-311">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="97c1c-312">A szerkesztés megerősítséséhez kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-312">Select **OK** to confirm the edit.</span></span>

### <a name="work-classes"></a><span data-ttu-id="97c1c-313">Munkaosztályok</span><span class="sxs-lookup"><span data-stu-id="97c1c-313">Work classes</span></span>

1. <span data-ttu-id="97c1c-314">Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-314">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="97c1c-315">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-315">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="97c1c-316">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-316">In the header, set the following values:</span></span>

    - <span data-ttu-id="97c1c-317">**Munkaosztály azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-317">**Work class ID:** *Sorting*</span></span>
    - <span data-ttu-id="97c1c-318">**Leírás:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-318">**Description:** *Sorting*</span></span>
    - <span data-ttu-id="97c1c-319">**Munkarendelés típusa:** *Rendezett készletkitárolás*</span><span class="sxs-lookup"><span data-stu-id="97c1c-319">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="97c1c-320">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-320">Select **Save**.</span></span>

### <a name="work-templates"></a><span data-ttu-id="97c1c-321">Munkasablonok</span><span class="sxs-lookup"><span data-stu-id="97c1c-321">Work templates</span></span>

1. <span data-ttu-id="97c1c-322">Lépjen ide: **Raktárkezelés \> Munka \> Munkasablonok**.</span><span class="sxs-lookup"><span data-stu-id="97c1c-322">Go to **Warehouse management \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="97c1c-323">A **Munkarendelés típusa** mezőben válassza ki az *Értékesítési rendelések* elemet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-323">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="97c1c-324">A rácsban válassza ki a **62 kitárolás csomagoláshoz** munkasablont.</span><span class="sxs-lookup"><span data-stu-id="97c1c-324">In the grid, select the **62 Pick to pack** work template.</span></span>
1. <span data-ttu-id="97c1c-325">A Műveleti ablaktáblán kattintson a **Munkafejléc-törések** elemre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-325">On the Action Pane, select **Work header breaks**.</span></span>
1. <span data-ttu-id="97c1c-326">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-326">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="97c1c-327">Törölje a jelet a **Csoportosítás ezen mező szerint** jelölőnégyzetből abban a sorban, amelyen a **Mezőnév** mező be van állítva a *szállítmány azonosítójára*.</span><span class="sxs-lookup"><span data-stu-id="97c1c-327">On the line where the **Field name** field is set to *Shipment ID*, clear the **Group by this field** check box.</span></span>
1. <span data-ttu-id="97c1c-328">Válassza a **Mentés** parancsot , majd zárja be a **Munkafejléc-törések** párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="97c1c-328">Select **Save**, and then close the **Work header breaks** dialog box.</span></span>
1. <span data-ttu-id="97c1c-329">A **Munkarendelés típusa** mezőben válassza ki a *Rendezett készletkitárolás* elemet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-329">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="97c1c-330">Válassza az **Új** lehetőséget egy munkasablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="97c1c-330">Select **New** to create a work template.</span></span>
1. <span data-ttu-id="97c1c-331">Az **Áttekintés** szakaszban állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="97c1c-331">In the **Overview** section, set the following values.</span></span> <span data-ttu-id="97c1c-332">Az összes többi mezőben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="97c1c-332">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="97c1c-333">**Munkasablon:** *Rendezett kitárolás*</span><span class="sxs-lookup"><span data-stu-id="97c1c-333">**Work template:** *Sorted picking*</span></span>
    - <span data-ttu-id="97c1c-334">**Munkasablon leírása:** *Rendezett kitárolás*</span><span class="sxs-lookup"><span data-stu-id="97c1c-334">**Work template description:** *Sorted picking*</span></span>

1. <span data-ttu-id="97c1c-335">A **Mentés** gombra kattintva elérhetővé válik a **Munkasablon részletei** szakasz.</span><span class="sxs-lookup"><span data-stu-id="97c1c-335">Select **Save** to make the **Work Template Details** section available.</span></span>
1. <span data-ttu-id="97c1c-336">A **Munkasablon részletei** részben két sort fog létrehozni.</span><span class="sxs-lookup"><span data-stu-id="97c1c-336">In the **Work Template Details** section, you will create two lines.</span></span> <span data-ttu-id="97c1c-337">Válassza az **Új** lehetőséget, majd állítsa be a következő értékeket az 1. sorhoz:</span><span class="sxs-lookup"><span data-stu-id="97c1c-337">Select **New**, and then set the following values for line 1:</span></span>

    - <span data-ttu-id="97c1c-338">**Munka típusa:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="97c1c-338">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="97c1c-339">**Kötelező:** Kiválasztva (= *Igen*)</span><span class="sxs-lookup"><span data-stu-id="97c1c-339">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="97c1c-340">**Munkaosztály azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-340">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="97c1c-341">Válassza ismét az **Új** lehetőséget, majd állítsa be a következő értékeket az 2. sorhoz:</span><span class="sxs-lookup"><span data-stu-id="97c1c-341">Select **New** again, and then set the following values for line 2:</span></span>

    - <span data-ttu-id="97c1c-342">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="97c1c-342">**Work type:** *Put*</span></span>
    - <span data-ttu-id="97c1c-343">**Kötelező:** Kiválasztva (= *Igen*)</span><span class="sxs-lookup"><span data-stu-id="97c1c-343">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="97c1c-344">**Munkaosztály azonosítója:** *Rendezés*</span><span class="sxs-lookup"><span data-stu-id="97c1c-344">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="97c1c-345">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-345">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="97c1c-346">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="97c1c-346">Example scenario</span></span>

<span data-ttu-id="97c1c-347">Ez a forgatókönyv szimulálja azt a helyzetet, amikor a raktár kis cikkeket tárol helyeken, és ezeket a csomagolás előtt dobozokba kell csomagolni, és a csomagolási állomás funkciói nem megfelelő.</span><span class="sxs-lookup"><span data-stu-id="97c1c-347">This scenario simulates a situation where the warehouse stores small items in locations and must pack them into boxes before they are shipped, and where packing station functionality isn't really suitable.</span></span> <span data-ttu-id="97c1c-348">A dolgozók a kitárolási sebesség növelése érdekében egyszerre több vevőhöz és különböző címekhez tartozó rendeléseket vesznek fel.</span><span class="sxs-lookup"><span data-stu-id="97c1c-348">Workers pick orders for multiple customers and different addresses at the same time to increase the picking speed.</span></span> <span data-ttu-id="97c1c-349">A kitárolás befejezése után a dolgozók megérkeznek a rendezési helyre, ahol a kitárolt cikkek a szükséges feltételek alapján rendezhetők a megfelelő dobozokba.</span><span class="sxs-lookup"><span data-stu-id="97c1c-349">After picking has been completed, the workers arrive at the sorting location, where the picked items can be sorted to the correct box, based on required criteria.</span></span> <span data-ttu-id="97c1c-350">Ebben a példában a szállítmányazonosító a megfelelő mező meghatározására szolgál, mivel minden szállítmányhoz más cím tartozik.</span><span class="sxs-lookup"><span data-stu-id="97c1c-350">In this example, the shipment ID will be used to determine the correct box, because each shipment has a different address.</span></span> <span data-ttu-id="97c1c-351">Miután a rakomány minden cikkét becsomagolták és szállítmány szerint rendezték, a dobozok átkerülnek az előkészítő területre, majd egy teherautóra rakodják azokat.</span><span class="sxs-lookup"><span data-stu-id="97c1c-351">After all items from the load are packed and sorted by shipment, the boxes will be moved to the staging area and eventually loaded onto a truck.</span></span>

<span data-ttu-id="97c1c-352">A forgatókönyv elkezdése előtt győződjön meg arról, hogy az összes standard raktári funkció helyesen van beállítva a raktárban.</span><span class="sxs-lookup"><span data-stu-id="97c1c-352">Before you start the scenario, make sure that all standard warehouse functionality is set up correctly for your warehouse.</span></span> <span data-ttu-id="97c1c-353">Erre a célra a *62-es* szabványos Contoso raktár használatos.</span><span class="sxs-lookup"><span data-stu-id="97c1c-353">Standard Contoso warehouse *62* is used for this purpose.</span></span> <span data-ttu-id="97c1c-354">A szokásos konfigurációk nem változtak a beállításban ismertetetteken kívül.</span><span class="sxs-lookup"><span data-stu-id="97c1c-354">Standard configurations haven't been changed, besides what is described in the setup.</span></span>

### <a name="create-demand"></a><span data-ttu-id="97c1c-355">Igény létrehozása</span><span class="sxs-lookup"><span data-stu-id="97c1c-355">Create demand</span></span>

<span data-ttu-id="97c1c-356">A funkcionalitás bemutatása előtt létre kell hoznia igényt.</span><span class="sxs-lookup"><span data-stu-id="97c1c-356">Before the functionality can be demonstrated, you must create some demand.</span></span> <span data-ttu-id="97c1c-357">Ehhez a forgatókönyvhöz három értékesítési rendelést hoz létre három különböző vevő számára, hogy szimulálja a különböző szállítási címeket.</span><span class="sxs-lookup"><span data-stu-id="97c1c-357">For this scenario, you will create three sales orders for three different customers to simulate different delivery addresses.</span></span> <span data-ttu-id="97c1c-358">Ily módon három külön szállítmányt fog létrehozni.</span><span class="sxs-lookup"><span data-stu-id="97c1c-358">In this way, you will create three separate shipments.</span></span>

<span data-ttu-id="97c1c-359">Az értékesítési rendelések és szállítmányok létrehozása előtt meg kell győződnie arról, hogy a kitárolási helyek elegendő készlettel rendelkeznek az értékelési rendelésekben található minden cikkhez.</span><span class="sxs-lookup"><span data-stu-id="97c1c-359">Before you create sales orders and shipments, make sure that the pick locations have enough inventory for all the items on the orders.</span></span> <span data-ttu-id="97c1c-360">A helyutasítás beállítás áttekintésével erősítse meg, hogy melyik kitárolási helyeket használja az értékesítési rendelések kitároláshoz.</span><span class="sxs-lookup"><span data-stu-id="97c1c-360">Review the location directive settings to confirm the picking locations that are used for sales order picking.</span></span> <span data-ttu-id="97c1c-361">Ha módosítania kell a készletet, akkor manuális mozgásokat hozhat létre, felhasználhatja a feltöltést, vagy bármilyen egyéb folyamatot alkalmazhat.</span><span class="sxs-lookup"><span data-stu-id="97c1c-361">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span> <span data-ttu-id="97c1c-362">Majd foglalja le a készletet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-362">Then reserve the inventory.</span></span>

1. <span data-ttu-id="97c1c-363">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-363">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="97c1c-364">Értékesítési rendelés létrehozásához az 1. rendeléshez kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-364">Select **New** to create a sales order for order 1.</span></span>
1. <span data-ttu-id="97c1c-365">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-365">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="97c1c-366">**Vevő:** *USA-001*</span><span class="sxs-lookup"><span data-stu-id="97c1c-366">**Customer:** *US-001*</span></span>
    - <span data-ttu-id="97c1c-367">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="97c1c-367">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="97c1c-368">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-368">Select **OK**.</span></span>
1. <span data-ttu-id="97c1c-369">A program új sort ad hozzá az **Értékesítési rendelés sorai** gyorslaphoz.</span><span class="sxs-lookup"><span data-stu-id="97c1c-369">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="97c1c-370">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-370">Set the following values:</span></span>

    - <span data-ttu-id="97c1c-371">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="97c1c-371">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="97c1c-372">**Mennyiség:** *5*</span><span class="sxs-lookup"><span data-stu-id="97c1c-372">**Quantity:** *5*</span></span>

1. <span data-ttu-id="97c1c-373">Válassza ki a **Sor hozzáadása** lehetőséget egy második sort hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-373">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="97c1c-374">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="97c1c-374">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="97c1c-375">**Mennyiség:** *10*</span><span class="sxs-lookup"><span data-stu-id="97c1c-375">**Quantity:** *10*</span></span>

1. <span data-ttu-id="97c1c-376">A következő lépések ismételje meg a rendelés minden értékesítési sorához, hogy készletet foglaljon azokhoz:</span><span class="sxs-lookup"><span data-stu-id="97c1c-376">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="97c1c-377">Az **Értékesítési rendelés sorai** gyorslap **Készlet** menüjében válassza a **Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-377">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="97c1c-378">A **Foglalás** lapon válassza ki az **Adag foglalása** elemet, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="97c1c-378">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="97c1c-379">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-379">Select **Save**.</span></span>

1. <span data-ttu-id="97c1c-380">Értékesítési rendelés létrehozásához az 2. rendeléshez kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-380">Select **New** to create a sales order for order 2.</span></span>
1. <span data-ttu-id="97c1c-381">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-381">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="97c1c-382">**Vevő:** *USA-004*</span><span class="sxs-lookup"><span data-stu-id="97c1c-382">**Customer:** *US-004*</span></span>
    - <span data-ttu-id="97c1c-383">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="97c1c-383">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="97c1c-384">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-384">Select **OK**.</span></span>
1. <span data-ttu-id="97c1c-385">A program új sort ad hozzá az **Értékesítési rendelés sorai** gyorslaphoz.</span><span class="sxs-lookup"><span data-stu-id="97c1c-385">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="97c1c-386">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-386">Set the following values:</span></span>

    - <span data-ttu-id="97c1c-387">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="97c1c-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="97c1c-388">**Mennyiség:** *7*</span><span class="sxs-lookup"><span data-stu-id="97c1c-388">**Quantity:** *7*</span></span>

1. <span data-ttu-id="97c1c-389">Válassza ki a **Sor hozzáadása** lehetőséget egy második sort hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-389">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="97c1c-390">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="97c1c-390">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="97c1c-391">**Mennyiség:** *3*</span><span class="sxs-lookup"><span data-stu-id="97c1c-391">**Quantity:** *3*</span></span>

1. <span data-ttu-id="97c1c-392">A következő lépések ismételje meg a rendelés minden értékesítési sorához, hogy készletet foglaljon azokhoz:</span><span class="sxs-lookup"><span data-stu-id="97c1c-392">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="97c1c-393">Az **Értékesítési rendelés sorai** gyorslap **Készlet** menüjében válassza a **Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-393">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="97c1c-394">A **Foglalás** lapon válassza ki az **Adag foglalása** elemet, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="97c1c-394">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="97c1c-395">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-395">Select **Save**.</span></span>

1. <span data-ttu-id="97c1c-396">Értékesítési rendelés létrehozásához az 3. rendeléshez kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-396">Select **New** to create a sales order for order 3.</span></span>
1. <span data-ttu-id="97c1c-397">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-397">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="97c1c-398">**Vevő:** *USA-007*</span><span class="sxs-lookup"><span data-stu-id="97c1c-398">**Customer:** *US-007*</span></span>
    - <span data-ttu-id="97c1c-399">**Raktár:** *62*</span><span class="sxs-lookup"><span data-stu-id="97c1c-399">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="97c1c-400">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-400">Select **OK**.</span></span>
1. <span data-ttu-id="97c1c-401">A program új sort ad hozzá az **Értékesítési rendelés sorai** gyorslaphoz.</span><span class="sxs-lookup"><span data-stu-id="97c1c-401">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="97c1c-402">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-402">Set the following values:</span></span>

    - <span data-ttu-id="97c1c-403">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="97c1c-403">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="97c1c-404">**Mennyiség:** *8*</span><span class="sxs-lookup"><span data-stu-id="97c1c-404">**Quantity:** *8*</span></span>

1. <span data-ttu-id="97c1c-405">Készlet foglalásához értékesítési sorhoz kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="97c1c-405">Follow these steps to reserve inventory for the sales line:</span></span>

    1. <span data-ttu-id="97c1c-406">Az **Értékesítési rendelés sorai** gyorslap **Készlet** menüjében válassza a **Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-406">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="97c1c-407">A **Foglalás** lapon válassza ki az **Adag foglalása** elemet, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="97c1c-407">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="97c1c-408">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-408">Select **Save**.</span></span>

<span data-ttu-id="97c1c-409">Hajtsa végre a következő eljárást, hogy minden értékesítési rendelést a raktárba bocsásson.</span><span class="sxs-lookup"><span data-stu-id="97c1c-409">Complete the following procedure to release each sales order to the warehouse.</span></span> <span data-ttu-id="97c1c-410">Három különböző szállítmány jön létre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-410">Three different shipments will be created.</span></span> <span data-ttu-id="97c1c-411">Ezt követően mindhárom szállítmányt egy új hullámba fogja hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="97c1c-411">You will then add all three shipments to one new wave.</span></span>

1. <span data-ttu-id="97c1c-412">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-412">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="97c1c-413">Válassza ki a rácsban az elsőként létrehozott értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="97c1c-413">In the grid, select the first sales order that you created.</span></span>
1. <span data-ttu-id="97c1c-414">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-414">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="97c1c-415">Olyan tájékoztató üzenet érkezik, amely az adott kiadásból létrehozott hullámazonosítót és szállítási azonosítót jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="97c1c-415">You receive an informational message that shows the wave ID and shipment ID that were created.</span></span>

1. <span data-ttu-id="97c1c-416">Ismételje meg a korábbi lépéseket a 2. és 3. értékesítési rendeléseknek a raktárba történő kiadásához.</span><span class="sxs-lookup"><span data-stu-id="97c1c-416">Repeat the previous steps to release sales orders 2 and 3 to the warehouse.</span></span> <span data-ttu-id="97c1c-417">Figyelje meg, hogy a kapott tájékoztató üzenet azt jelzi, hogy a 1. értékesítési rendelés létrehozásakor létrehozott hullámhoz szállítmány lett hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="97c1c-417">Notice that the informational message that you receive indicates that a shipment has been added to the wave that was created when you released sales order 1.</span></span>
1. <span data-ttu-id="97c1c-418">Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.</span><span class="sxs-lookup"><span data-stu-id="97c1c-418">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="97c1c-419">Válassza ki azt a hullámazonosítót, amelyet az értékesítési rendelések kiadásával hoztak létre a **Hullámok** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="97c1c-419">Select the wave ID that was created from the release of the sales orders to open the **Waves** page.</span></span> <span data-ttu-id="97c1c-420">Ez a lap a hullám részleteit jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="97c1c-420">This page shows the wave details.</span></span> <span data-ttu-id="97c1c-421">A **Hullámsorok** gyorslap a létrehozott szállítmányokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="97c1c-421">The **Wave lines** FastTab shows the shipments that were created.</span></span>

    <span data-ttu-id="97c1c-422">Most létre kell hoznia azt a munkát, amellyel a cikkeket a kitárolási helyekről a rendezési helyre viszi.</span><span class="sxs-lookup"><span data-stu-id="97c1c-422">You must now create work to bring items from the picking locations to the sorting location.</span></span>

1. <span data-ttu-id="97c1c-423">A Művelet ablaktáblán válassza ki a **Folyamat** elemet.</span><span class="sxs-lookup"><span data-stu-id="97c1c-423">On the Action Pane, select **Process**.</span></span>

    <span data-ttu-id="97c1c-424">A hullám feldolgozásakor a rendezési metódus a rendezési sablon alapján rendeli hozzá a készletet a rendezési pozíciókhoz.</span><span class="sxs-lookup"><span data-stu-id="97c1c-424">During wave processing, the sorting method will use the sorting template to assign the inventory to sort positions.</span></span> <span data-ttu-id="97c1c-425">A hullám feldolgozásának befejezését követően egy tájékoztató üzenetet kap, jelezve, hogy a rendszer létrehozta a munkát, és feladta a hullámot.</span><span class="sxs-lookup"><span data-stu-id="97c1c-425">When wave processing is completed, you receive an informational message that states that the wave has been posted and work has been created.</span></span>

1. <span data-ttu-id="97c1c-426">A műveleti ablaktábla **Hullám** lapján a **Kapcsolódó információ** csoportban válassza ki a **Munka** elemet a létrehozott munka megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="97c1c-426">On the Action Pane, on the **Wave** tab, in the **Related information** group, select **Work** to view the work that was created.</span></span> <span data-ttu-id="97c1c-427">Jegyezze fel a munkaazonosítót</span><span class="sxs-lookup"><span data-stu-id="97c1c-427">Make a note of the work ID.</span></span>
1. <span data-ttu-id="97c1c-428">Nyissa meg a **Raktárkezelés \> Csomagolás és tárolólétrehozás \> Kimenő rendezésipozíció-hozzárendelések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-428">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="97c1c-429">A bal oldali oszlopban megtekinthetők az egyes szállítmányokhoz létrehozott kimenő rendezésbeosztások.</span><span class="sxs-lookup"><span data-stu-id="97c1c-429">In the left column, you can view the outbound sorting position that was created for each shipment.</span></span>
1. <span data-ttu-id="97c1c-430">A **Rendezési pozíció feltételei** gyorslapon megtekintheti a pozícióhoz tartozó szállítmányazonosítót.</span><span class="sxs-lookup"><span data-stu-id="97c1c-430">On the **Sort position criteria** FastTab, you can view the shipment ID for that position.</span></span>

<span data-ttu-id="97c1c-431">Egy munkaazonosító lett létrehozva amely a cikkeket a kitárolási helyekről a rendezési helyre viszi.</span><span class="sxs-lookup"><span data-stu-id="97c1c-431">One work ID has been created to bring inventory from the picking locations to the sorting location.</span></span> <span data-ttu-id="97c1c-432">A munka befejezéséhez szüksége lesz a hullámfeldolgozás során létrehozott munkaazonosítóra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-432">To complete the work, you will need the work ID that was created during wave processing.</span></span>

### <a name="sales-order-picking-to-the-sorting-location"></a><span data-ttu-id="97c1c-433">Értékesítési rendelés kitárolása a rendezési helyre</span><span class="sxs-lookup"><span data-stu-id="97c1c-433">Sales order picking to the sorting location</span></span>

1. <span data-ttu-id="97c1c-434">Jelentkezzen be a *62*-es raktárba felhasználóként a mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="97c1c-434">Sign in to the mobile app as a worker in warehouse *62*.</span></span>
1. <span data-ttu-id="97c1c-435">Válassza a főmenü **Kimenő** elemét.</span><span class="sxs-lookup"><span data-stu-id="97c1c-435">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="97c1c-436">Válassza a **Kimenő** menü **Értékesítési kitárolás** elemét.</span><span class="sxs-lookup"><span data-stu-id="97c1c-436">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="97c1c-437">Válassza ki az **Azonosító** mezőt, majd írja be a munkaazonosítót a hullámfeldolgozásból.</span><span class="sxs-lookup"><span data-stu-id="97c1c-437">Select the **ID** field, and then enter the work ID from the wave processing.</span></span>
1. <span data-ttu-id="97c1c-438">Hagyja jóvá a bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="97c1c-438">Confirm your entry.</span></span>

    <span data-ttu-id="97c1c-439">Ezután a program megkérdezi, hogy meg szeretné-e adni a cél azonosítótáblát (AT).</span><span class="sxs-lookup"><span data-stu-id="97c1c-439">Next, you're prompted to enter a target license plate (LP).</span></span> <span data-ttu-id="97c1c-440">Figyelje meg, hogy az 1. értékesítési rendelés 1. sorát kell kitárolni és hozzáadni a cél azonosítótáblához.</span><span class="sxs-lookup"><span data-stu-id="97c1c-440">Notice that line 1 from sales order 1 is what must be picked and added to the target license plate.</span></span> <span data-ttu-id="97c1c-441">Megjelenik a cikkszám, a mennyiség, a cikk leírása és a kitárolási hely.</span><span class="sxs-lookup"><span data-stu-id="97c1c-441">The item number, quantity, item description, and pick location are shown.</span></span>

1. <span data-ttu-id="97c1c-442">A **Cél AT** mezőben adja meg a cél azonosítótábla-számát.</span><span class="sxs-lookup"><span data-stu-id="97c1c-442">In the **Target LP** field, enter a license plate number.</span></span>

    <span data-ttu-id="97c1c-443">A feldolgozott hullámban létrehozott összes sort ugyanarra a cél azonosítótáblára tárolja ki.</span><span class="sxs-lookup"><span data-stu-id="97c1c-443">You will pick all lines that were created from the processed wave onto the same target license plate.</span></span>

1. <span data-ttu-id="97c1c-444">Hagyja jóvá a bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="97c1c-444">Confirm your entry.</span></span>

    <span data-ttu-id="97c1c-445">A mobilalkalmazás most egy sor olyan **Kitárolási** lapot jelenít meg, amelyek a kitárolási helyre irányítják, és a cikkre és a mennyiségre, amelyet ki kell tárolni.</span><span class="sxs-lookup"><span data-stu-id="97c1c-445">The mobile app now presents a series of **Pick** pages that point you to the picking location, and to the item and quantity that must be picked.</span></span> <span data-ttu-id="97c1c-446">A kitárolt cikk az azonosítótáblához történő hozzáadása után jóváhagyja a kitárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="97c1c-446">After the picked item is added to the license plate, you will confirm the pick work.</span></span> <span data-ttu-id="97c1c-447">Az utolsó oldal az a munka, amellyel a kitárolt elemeket a rendezési helyre helyezi.</span><span class="sxs-lookup"><span data-stu-id="97c1c-447">The last page will be the work to put the picked items into the sorting location.</span></span>

1. <span data-ttu-id="97c1c-448">Erősítse meg az első kitárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="97c1c-448">Confirm the first pick work.</span></span>
1. <span data-ttu-id="97c1c-449">Megjelenik a következő kitárolási munka.</span><span class="sxs-lookup"><span data-stu-id="97c1c-449">The next pick work is shown.</span></span> <span data-ttu-id="97c1c-450">Erősítse meg a kitárolást.</span><span class="sxs-lookup"><span data-stu-id="97c1c-450">Confirm the pick.</span></span>
1. <span data-ttu-id="97c1c-451">Folytassa a hátralévő kitárolási munka jóváhagyásával.</span><span class="sxs-lookup"><span data-stu-id="97c1c-451">Continue to confirm the remaining pick work.</span></span>
1. <span data-ttu-id="97c1c-452">Az utolsó lépés a kitárolási munka végrehajtása.</span><span class="sxs-lookup"><span data-stu-id="97c1c-452">The last step is to complete the put work.</span></span> <span data-ttu-id="97c1c-453">Nyugtázza az elraktározást a rendezési helyre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-453">Confirm the put-away to the sorting location.</span></span>

    <span data-ttu-id="97c1c-454">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="97c1c-454">You receive a "Work completed" message.</span></span>

1. <span data-ttu-id="97c1c-455">Lépjen ki az **Értékesítési kitárolásból** a mobilalkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="97c1c-455">Exit **Sales Picking** on the mobile app.</span></span>

### <a name="sortingput-to-wall"></a><span data-ttu-id="97c1c-456">Rendezés/falra helyezés</span><span class="sxs-lookup"><span data-stu-id="97c1c-456">Sorting/put-to-wall</span></span>

<span data-ttu-id="97c1c-457">Most, hogy az összes készletet áthelyezték a rendezési helyre, azt a helyes rendezési pozícióba kell rendezni.</span><span class="sxs-lookup"><span data-stu-id="97c1c-457">Now that all inventory has been put to the sorting location, it must be sorted to the correct sort position.</span></span>

1. <span data-ttu-id="97c1c-458">Jelentkezzen be a mobilalkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="97c1c-458">Sign in to the mobile app.</span></span>
1. <span data-ttu-id="97c1c-459">Válassza a főmenü **Kimenő** elemét.</span><span class="sxs-lookup"><span data-stu-id="97c1c-459">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="97c1c-460">Válassza a **Kimenő** menü **Rendezés** parancsát a cikkek rendezésének megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="97c1c-460">On the **Outbound** menu, select **Sort** to start to sort the items.</span></span>
1. <span data-ttu-id="97c1c-461">Az **Azonosítótábla/CON** mezőbe írja be a kitárolt értékesítési rendelési munka cél azonosítótábláját.</span><span class="sxs-lookup"><span data-stu-id="97c1c-461">In the **LP/CON** field, enter the target license plate of the picked sales order work.</span></span>
1. <span data-ttu-id="97c1c-462">Hagyja jóvá a bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="97c1c-462">Confirm your entry.</span></span>
1. <span data-ttu-id="97c1c-463">Adja meg az először rendezendő cikkszámot.</span><span class="sxs-lookup"><span data-stu-id="97c1c-463">Enter the item number to sort first.</span></span>
1. <span data-ttu-id="97c1c-464">A rendszer határozza meg a megjelenítendő első rendezési pozíciót.</span><span class="sxs-lookup"><span data-stu-id="97c1c-464">The system determines the first sort position that should be shown.</span></span> <span data-ttu-id="97c1c-465">A rendezési pozíció jóváhagyása.</span><span class="sxs-lookup"><span data-stu-id="97c1c-465">Confirm the sort position.</span></span>
1. <span data-ttu-id="97c1c-466">A program megkéri, hogy rendeljen-e hozzá egy azonosítótáblát a rendezési pozícióhoz.</span><span class="sxs-lookup"><span data-stu-id="97c1c-466">You're prompted to assign a license plate to the sort position.</span></span> <span data-ttu-id="97c1c-467">Válassza ki az **Azonosítótábla** mezőt, adja meg az azonosítótábla számát, majd hagyja jóvá a bevitelt.</span><span class="sxs-lookup"><span data-stu-id="97c1c-467">Select the **LP** field, enter a license plate number, and then confirm your entry.</span></span>

    <span data-ttu-id="97c1c-468">Mivel a rendezési pozíció a szállítmány azonosítójához kapcsolódik, a kitárolt cikkeket a kimenő szállítmányhoz és értékesítési rendeléshez kapcsolódó azonosítótáblára tárolja ki.</span><span class="sxs-lookup"><span data-stu-id="97c1c-468">Because the sort position is related to the shipment ID, you will sort the picked items into a license plate that is specific to the outbound shipment and sales order.</span></span>

    <span data-ttu-id="97c1c-469">A következő oldalon látható a cikkazonosító, a mennyiség, a rendezési pozíció azonosítója, valamint az „innen” (kitárolás) és a „ide” (rendezés) azonosítótábla azonosítója.</span><span class="sxs-lookup"><span data-stu-id="97c1c-469">The next page shows the item ID, quantity, sort position ID, and the "from" (picking) and "to" (sorting) license plate IDs.</span></span> <span data-ttu-id="97c1c-470">A lapon található információk alapján a megadott cikk és mennyiségek rendezhetők a kitárolási azonosítótáblából a rendezési azonosítótáblára.</span><span class="sxs-lookup"><span data-stu-id="97c1c-470">The information on this page instructs you to sort the specified item and quantities from the picking license plate into the sorting license plate.</span></span>

1. <span data-ttu-id="97c1c-471">A rendezési pozíció jóváhagyása.</span><span class="sxs-lookup"><span data-stu-id="97c1c-471">Confirm the sort position.</span></span>
1. <span data-ttu-id="97c1c-472">Rendezze a cikkeket az első rendezési pozícióba.</span><span class="sxs-lookup"><span data-stu-id="97c1c-472">Sort the items in the first sort position.</span></span> <span data-ttu-id="97c1c-473">Ha befejezte a munkát, a rendszer irányítja a következő rendezési pozícióra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-473">When you've finished, the system directs you to the next sort position.</span></span>
1. <span data-ttu-id="97c1c-474">Ismételje meg ezt a műveletet a munkarendelésen szereplő összes kitárolt sorhoz.</span><span class="sxs-lookup"><span data-stu-id="97c1c-474">Repeat this process for all picked lines on the work order.</span></span> <span data-ttu-id="97c1c-475">Akkor is ezt a folyamatot kell használni, ha több olyan kitárolási sor van, amelyeknek ugyanaz a cikkszáma.</span><span class="sxs-lookup"><span data-stu-id="97c1c-475">You should also use this process when there are multiple pick lines that have the same item number.</span></span>

    <span data-ttu-id="97c1c-476">Amikor ezt a folyamatot minden cikkre megismétli, a rendszer kiértékeli a feltételt a következő beolvasott cikkből (munkasor), és meghatározza, hogy milyen rendezési pozícióra kell azt eltárolni,</span><span class="sxs-lookup"><span data-stu-id="97c1c-476">As you repeat this process for all items, the system evaluates the criteria from the next scanned item (work line) and determines which sorting position it should be put to.</span></span> <span data-ttu-id="97c1c-477">A program automatikusan a megfelelő rendezési pozícióba helyezi a cikket.</span><span class="sxs-lookup"><span data-stu-id="97c1c-477">You're automatically directed to put the item to the correct sort position.</span></span> <span data-ttu-id="97c1c-478">A visszaigazolási beállításoktól függően a rendszer megkéri, hogy hagyja jóvá ezt a műveletet a pozíciószám vagy az azonosítótábla azonosítójának megadásával.</span><span class="sxs-lookup"><span data-stu-id="97c1c-478">Depending on the confirmation setup, you're also directed to confirm this action by entering the position number or license plate ID.</span></span>

    > [!NOTE]
    > <span data-ttu-id="97c1c-479">Ha az automatikus rendezés be van kapcsolva, akkor a manuális felülbírálás nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="97c1c-479">If automatic sorting is turned on, manual override isn't available.</span></span>

1. <span data-ttu-id="97c1c-480">Amikor befejezte a munkát, a Microsoft Dynamics 365 Supply Chain Management alkalmazásban nyissa meg a **Kimenő sorba rendezési pozíció-hozzárendelések** lapot a pozíciók állapotának ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="97c1c-480">When you've finished, in Microsoft Dynamics 365 Supply Chain Management, open the **Outbound sorting position assignments** page to review the status of the positions.</span></span>

    - <span data-ttu-id="97c1c-481">Ha a beosztások automatikusan le vannak zárva, akkor a lezárt beosztások megjelenítéséhez válassza a **Lezártak megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c1c-481">If positions are closed automatically, select **Show closed** to show the closed positions.</span></span>
    - <span data-ttu-id="97c1c-482">Figyelje meg, hogy a rendezési pozíció tranzakciói láthatók.</span><span class="sxs-lookup"><span data-stu-id="97c1c-482">Notice that sort position transactions are shown.</span></span> <span data-ttu-id="97c1c-483">Megjelenik a pozíción keresztül feldolgozott cikk és mennyiség.</span><span class="sxs-lookup"><span data-stu-id="97c1c-483">The item and quantity that were processed through the position are shown.</span></span>

    <span data-ttu-id="97c1c-484">A kimenő rendezési sablon beállítása során, akkor a **Rendezési pozíció automatikus lezárása** beállítást állítsa *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="97c1c-484">When you set up the outbound sorting template, you set the **Auto close sort position** option to *Yes*.</span></span> <span data-ttu-id="97c1c-485">Ennek megfelelően a program automatikusan lezárja a pozíciót, miután a várt tervezett készletet belehelyezik.</span><span class="sxs-lookup"><span data-stu-id="97c1c-485">Therefore, the position is automatically closed after the last expected inventory is put to it.</span></span> <span data-ttu-id="97c1c-486">A rendezési pozíciók **Lezárt** állapotban vannak, és a rendszer létrehozta a munkát úgy, hogy a rendezett készletet *Raktárajtó* helyre helyezte.</span><span class="sxs-lookup"><span data-stu-id="97c1c-486">The sort positions are in **Closed** status, and work has been created to move the sorted inventory to *Baydoor* location.</span></span>

1. <span data-ttu-id="97c1c-487">Végezze el a rendezett készletkitárolási munkafolyamatot, hogy a készletet a szállítási helyre vigye.</span><span class="sxs-lookup"><span data-stu-id="97c1c-487">Complete the sorted inventory picking work to move the inventory to the shipping location.</span></span> <span data-ttu-id="97c1c-488">Ha a készlet készen áll, akkor a szállítás-visszaigazolja.</span><span class="sxs-lookup"><span data-stu-id="97c1c-488">When the inventory is ready, ship-confirm it.</span></span>

> [!NOTE]
> <span data-ttu-id="97c1c-489">A kiválasztott készlet-kitárolási munka helyes feldolgozásához a mozgatási és berakodási folyamathoz egy olyan mobileszköz-menüelemet kell használni, amely rendelkezik olyan munkaosztály-azonosítóval, amelyben a **Munkarendelés típusa** mező *Kiválasztott készlet kitárolására* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="97c1c-489">For sorted inventory picking work to be processed correctly, a mobile device menu item that has a work class ID where the **Work order type** field is set to *Sorted inventory picking* should be used for the movement and loading process.</span></span>

### <a name="manually-close-a-position-optional"></a><span data-ttu-id="97c1c-490">Pozíció manuális lezárása (nem kötelező)</span><span class="sxs-lookup"><span data-stu-id="97c1c-490">Manually close a position (optional)</span></span>

<span data-ttu-id="97c1c-491">Ha a rendezési pozíciókat manuálisan kell lezárni, akkor a **Rendezési pozíció automatikus lezárása** beállítást *Nem* értékre kell beállítani , és a zárást végre kell hajtani, mielőtt az árukészletet át lehetne helyezni a raktárajtó területére.</span><span class="sxs-lookup"><span data-stu-id="97c1c-491">If sort positions should be closed manually, the **Auto close sort position** option for the outbound sorting template must be set to *No*, and closing must be done before inventory can be moved to the bay door area.</span></span> <span data-ttu-id="97c1c-492">A pozíciók a különböző módokon zárhatók le:</span><span class="sxs-lookup"><span data-stu-id="97c1c-492">Positions can be closed in various ways:</span></span>

- <span data-ttu-id="97c1c-493">A raktári alkalmazáson keresztül:</span><span class="sxs-lookup"><span data-stu-id="97c1c-493">Via the warehouse app:</span></span>

    - <span data-ttu-id="97c1c-494">A felhasználó beolvashatja a pozícióban lévő cikkek valamelyikét, majd a beosztást lezárhatja a **Lezárás** lehetőséggel.</span><span class="sxs-lookup"><span data-stu-id="97c1c-494">The user can scan one of the items that are already on the position and then select **Close** to close the position.</span></span>
    - <span data-ttu-id="97c1c-495">Ha a felhasználó egy már rendezett tárolót olvas be, akkor egy hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="97c1c-495">If the user scans a container that has already been sorted container, an error message is shown.</span></span> <span data-ttu-id="97c1c-496">Ugyanakkor a felhasználó továbbra is folytathatja a beosztás lezárását.</span><span class="sxs-lookup"><span data-stu-id="97c1c-496">However, the user can still continue to close the position.</span></span>

- <span data-ttu-id="97c1c-497">A Microsoft Dynamics 365 Supply Chain Management **Kimenő rendezési pozíció-hozzárendelések** lapján:</span><span class="sxs-lookup"><span data-stu-id="97c1c-497">From the Microsoft Dynamics 365 Supply Chain Management **Outbound sorting position assignments** page:</span></span>

    - <span data-ttu-id="97c1c-498">A felhasználó kiválaszthatja a kimenő rendezési pozíció rekordját, majd kiválaszthatja a **Pozíció lezárása** lehetőséget a műveleti ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="97c1c-498">The user can select the outbound sorting position record and then select **Close position** on the Action Pane.</span></span>

## <a name="tips"></a><span data-ttu-id="97c1c-499">Tippek</span><span class="sxs-lookup"><span data-stu-id="97c1c-499">Tips</span></span>

- <span data-ttu-id="97c1c-500">A cikkek nem helyezhetők át a pozíciók között, miután hozzárendelték őket egyhez.</span><span class="sxs-lookup"><span data-stu-id="97c1c-500">Items can't be moved between positions after they have been assigned to one.</span></span> <span data-ttu-id="97c1c-501">A rendszer kiértékeli, hogy az egyes cikkekből hány darabnak kell egy adott pozícióhoz kerülnie.</span><span class="sxs-lookup"><span data-stu-id="97c1c-501">The system evaluates how many of each item should go to a specific position.</span></span>
- <span data-ttu-id="97c1c-502">A rendezési sablon beállítható úgy, hogy a pozíciók lezárása esetén automatikusan létrehozza a tárolókat.</span><span class="sxs-lookup"><span data-stu-id="97c1c-502">Sorts template can be configured to automatically create containers when positions are closed.</span></span> <span data-ttu-id="97c1c-503">Ez a módszer a megadott csomagolási profilon alapuló normál tárolóazonosító-struktúrát fog létrehozni.</span><span class="sxs-lookup"><span data-stu-id="97c1c-503">This approach will create standard container ID structure that is based on the specified packing profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97c1c-504">Miután a mozgatási munka létrejött a rendezési helyről, nem szabad érvényteleníteni a munkát.</span><span class="sxs-lookup"><span data-stu-id="97c1c-504">After movement work has been created from the sorting location, you must not cancel the work.</span></span> <span data-ttu-id="97c1c-505">Ellenkező esetben a pozíciót és a konténereket törli a rendszerből, és nem lesznek elérhetők további feldolgozásra.</span><span class="sxs-lookup"><span data-stu-id="97c1c-505">Otherwise, the position and the containers in it will be deleted from the system and unavailable for further processing.</span></span> <span data-ttu-id="97c1c-506">A készletet is eltávolítja a program.</span><span class="sxs-lookup"><span data-stu-id="97c1c-506">The inventory will also be removed.</span></span>
