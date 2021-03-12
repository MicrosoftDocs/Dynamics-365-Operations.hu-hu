---
title: Fürtpozíció tele
description: Ez a témakör a Fürtpozíció tele funkcióról nyújt tájékoztatást. Ez a funkció a munkamegszakítási szabályok szigorúbb végrehajtását teszi lehetővé a fürtkitárolás használata esetén, mivel nagyobb hibahatárt tesz lehetővé a tárolók és rakományok térfogatkorlátai tekintetében.
author: Mirzaab
manager: tfehr
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9c90380cb5d109e331a2552ba779525b66d10fa6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001099"
---
# <a name="cluster-position-full"></a><span data-ttu-id="fcee9-104">Fürtpozíció tele</span><span class="sxs-lookup"><span data-stu-id="fcee9-104">Cluster position full</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fcee9-105">A *Fürtpozíció tele* funkció a munkamegszakítási szabályok szigorúbb végrehajtását teszi lehetővé a fürtkitárolás használata esetén, mivel nagyobb hibahatárt tesz lehetővé a tárolók és rakományok térfogatkorlátai tekintetében.</span><span class="sxs-lookup"><span data-stu-id="fcee9-105">The *Cluster position full* feature offers an alternative to more rigid enforcement of work break rules when cluster picking is used, because it enables a larger margin of error in the volumetric constraints of containers or totes.</span></span> <span data-ttu-id="fcee9-106">Gyakori, hogy a munkarendelés minden cikke nem fér el a kiválasztott tárolóban.</span><span class="sxs-lookup"><span data-stu-id="fcee9-106">In a common scenario, not all items on a work order fit into a selected container.</span></span> <span data-ttu-id="fcee9-107">A fürtkitárolást végző raktári dolgozók csak néhány lehetőséggel rendelkeznek ebben a helyzetben: vagy egy nagyobb tárolóra váltanak, vagy a felettesükkel keresnek másik megoldást.</span><span class="sxs-lookup"><span data-stu-id="fcee9-107">Warehouse workers who are cluster picking have few options in this scenario: they must either change to a larger container size or work with their supervisor to come up with a different solution.</span></span>

<span data-ttu-id="fcee9-108">Ez a funkció bevezeti a **Megtelt** gomb futtatásának lehetőségét a fürt egyik munkaegységén.</span><span class="sxs-lookup"><span data-stu-id="fcee9-108">This feature introduces the ability to run the **Full** button on one of the work units in a cluster.</span></span> <span data-ttu-id="fcee9-109">A régebbi verziókban ez a lehetőség csak a szokásos rendeléskitároláskor volt elérhető, na fürtkitároláshoz nem.</span><span class="sxs-lookup"><span data-stu-id="fcee9-109">In older versions, this option was available only for regular order picking, not for cluster picking.</span></span> <span data-ttu-id="fcee9-110">Ez a funkció azonban különbözik a szokásos **Megtelt** gombtól, amely a hátralévő munkát érvényteleníti.</span><span class="sxs-lookup"><span data-stu-id="fcee9-110">However, this feature differs from the standard **Full** button in that it cancels the remaining work.</span></span> <span data-ttu-id="fcee9-111">Nem javasolja, hogy a felhasználó adjon hozzá egy másik tárolót ugyanahhoz a fürthöz, és nem hoz létre automatikusan új munkát.</span><span class="sxs-lookup"><span data-stu-id="fcee9-111">It doesn't suggest that the user add another bin to the same cluster, and it doesn't automatically create new work.</span></span>

## <a name="turn-on-the-cluster-position-full-feature"></a><span data-ttu-id="fcee9-112">A Fürtpozíció tele funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="fcee9-112">Turn on the Cluster position full feature</span></span>

<span data-ttu-id="fcee9-113">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="fcee9-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="fcee9-114">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="fcee9-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="fcee9-115">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="fcee9-115">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="fcee9-116">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="fcee9-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="fcee9-117">**Funkció neve:** *Fürtpozíció tele*</span><span class="sxs-lookup"><span data-stu-id="fcee9-117">**Feature name:** *Cluster position full*</span></span>

## <a name="setup"></a><span data-ttu-id="fcee9-118">Beállítás</span><span class="sxs-lookup"><span data-stu-id="fcee9-118">Setup</span></span>

<span data-ttu-id="fcee9-119">Ez a szakasz iránymutatásokat tartalmaz, és egy példán bemutatja, hogyan lehet beállítani és használni a *Fürtpozíció tele* funkciót.</span><span class="sxs-lookup"><span data-stu-id="fcee9-119">This section provides guidelines, and an example that shows how to set up and use the *Cluster position full* feature.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="fcee9-120">A mintaadatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="fcee9-120">Make sample data available</span></span>

<span data-ttu-id="fcee9-121">Ha ezt a [példaforgatókönyvet](#example-scenario) az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="fcee9-121">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="fcee9-122">Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="fcee9-122">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="fcee9-123">A példaforgatókönyvet a gyártási rendszerben végzett munka során a funkció használatához útmutatásként is használhatja.</span><span class="sxs-lookup"><span data-stu-id="fcee9-123">You can also use the example scenario as guidance for working with this feature on a production system.</span></span> <span data-ttu-id="fcee9-124">Ebben az esetben azonban az itt leírt beállítás esetében be kell helyettesítenie a saját értékeit.</span><span class="sxs-lookup"><span data-stu-id="fcee9-124">However, in that case, you must substitute your own values for the settings that are described here.</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="fcee9-125">Fürtprofilok</span><span class="sxs-lookup"><span data-stu-id="fcee9-125">Cluster profiles</span></span>

<span data-ttu-id="fcee9-126">Meg kell adnia, hogy a rendszer automatikusan generálja-e a fürtazonosítókat, hány pozíciót használ, amikor a fürtök megszakadnak, valamint a kitárolási munka sorrendjének és ellenőrzésének módját.</span><span class="sxs-lookup"><span data-stu-id="fcee9-126">You must specify whether cluster IDs are automatically generated, how many positions are used, when clusters are broken, and how the picking work is sequenced and verified.</span></span>

1. <span data-ttu-id="fcee9-127">Kattintson a **Raktárkezelés \> Beállítás \> Mobileszköz \> Fürtprofilok** elemre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-127">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="fcee9-128">A lista ablaktáblán válassza ki a **Fürt létrehozása** rekordot.</span><span class="sxs-lookup"><span data-stu-id="fcee9-128">In the list pane, select the **Create Cluster** record.</span></span>
1. <span data-ttu-id="fcee9-129">Az **Általános** gyorslapon ellenőrizze a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="fcee9-129">On the **General** FastTab, verify the following values:</span></span>

    - <span data-ttu-id="fcee9-130">**Fürtazonosító létrehozása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="fcee9-130">**Generate cluster ID:** *Yes*</span></span>
    - <span data-ttu-id="fcee9-131">**Pozíciók aktiválása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="fcee9-131">**Activate positions:** *Yes*</span></span>
    - <span data-ttu-id="fcee9-132">**Pozíciók száma:** *2*</span><span class="sxs-lookup"><span data-stu-id="fcee9-132">**Number of positions:** *2*</span></span>
    - <span data-ttu-id="fcee9-133">**Pozíció neve:** *Numerikus*</span><span class="sxs-lookup"><span data-stu-id="fcee9-133">**Position name:** *Numeric*</span></span>
    - <span data-ttu-id="fcee9-134">**Fürt felbontása ennél:** *Betárolás*</span><span class="sxs-lookup"><span data-stu-id="fcee9-134">**Break cluster at:** *Put*</span></span>
    - <span data-ttu-id="fcee9-135">**Rendezés ellenőrzési típusa:** *Pozíció beolvasása*</span><span class="sxs-lookup"><span data-stu-id="fcee9-135">**Sort verification type:** *Position scan*</span></span>

1. <span data-ttu-id="fcee9-136">A **Fürtrendezés** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="fcee9-136">In the **Cluster sorting** FastTab.</span></span> <span data-ttu-id="fcee9-137">A rácsnak üresnek kell lennie (azaz nem tartalmazhat sort).</span><span class="sxs-lookup"><span data-stu-id="fcee9-137">The grid should be blank (that is, it should contain no lines).</span></span>

### <a name="work-templates"></a><span data-ttu-id="fcee9-138">Munkasablonok</span><span class="sxs-lookup"><span data-stu-id="fcee9-138">Work templates</span></span>

<span data-ttu-id="fcee9-139">Definiálnia kell, hogyan jön létre a kitárolása munka a fürtkitároláshoz.</span><span class="sxs-lookup"><span data-stu-id="fcee9-139">You must define how the picking work for cluster picking is created.</span></span>

1. <span data-ttu-id="fcee9-140">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-140">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="fcee9-141">A lap tetején állítsa a **Munkarendelés típusa** mezőt az *Értékesítési rendelések* értékre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-141">At the top of the page, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="fcee9-142">Győződjön meg róla, hogy a bemutató adatok közül a következő munkasablonok szerepelnek a listában.</span><span class="sxs-lookup"><span data-stu-id="fcee9-142">Make sure that the following work templates from the demo data are listed.</span></span> <span data-ttu-id="fcee9-143">Ha nem állnak rendelkezésre, akkor nem tudja elvégezni a forgatókönyvet.</span><span class="sxs-lookup"><span data-stu-id="fcee9-143">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="fcee9-144">61 SO Állapor</span><span class="sxs-lookup"><span data-stu-id="fcee9-144">61 SO Stage</span></span>
    - <span data-ttu-id="fcee9-145">61 SO Fürt kitárolása</span><span class="sxs-lookup"><span data-stu-id="fcee9-145">61 SO Cluster pick</span></span>

### <a name="location-directives"></a><span data-ttu-id="fcee9-146">Helyutasítások</span><span class="sxs-lookup"><span data-stu-id="fcee9-146">Location directives</span></span>

<span data-ttu-id="fcee9-147">Meg kell adnia, hogy a cikkek honnan lesznek kitárolva, és hová kerülnek.</span><span class="sxs-lookup"><span data-stu-id="fcee9-147">You must specify where items are picked from and where they are put.</span></span>

1. <span data-ttu-id="fcee9-148">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-148">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="fcee9-149">A listafejlécben állítsa át a **Munkarendelés típusa** mezőt *Értékesítési rendelések* értékre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-149">In the list header, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="fcee9-150">Győződjön meg róla, hogy a bemutató adatok közül a következő értékesítésirendelés-utasítások szerepelnek a listában.</span><span class="sxs-lookup"><span data-stu-id="fcee9-150">Make sure that the following sales order directives from the demo data are listed.</span></span> <span data-ttu-id="fcee9-151">Ha nem állnak rendelkezésre, akkor nem tudja elvégezni a forgatókönyvet.</span><span class="sxs-lookup"><span data-stu-id="fcee9-151">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="fcee9-152">61 Fürt kitárolása</span><span class="sxs-lookup"><span data-stu-id="fcee9-152">61 Cluster pick</span></span>
    - <span data-ttu-id="fcee9-153">61 SO Kitárolása sorrendje</span><span class="sxs-lookup"><span data-stu-id="fcee9-153">61 SO Pick order</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="fcee9-154">Mobileszköz menüpontjai</span><span class="sxs-lookup"><span data-stu-id="fcee9-154">Mobile device menu items</span></span>

<span data-ttu-id="fcee9-155">A folyamatban lévő munkát, hogy fürtkitárolás által használandó mobileszköz menü elemeinek beállítása szükséges.</span><span class="sxs-lookup"><span data-stu-id="fcee9-155">You must configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="fcee9-156">A fürtök kitárolásához használható mobileszköz menüpontban be kell kapcsolni a **Munka felosztásának engedélyezése** paramétert, és az *SO kitárolás* munkaosztályt hozzá kell adni.</span><span class="sxs-lookup"><span data-stu-id="fcee9-156">In the mobile device menu item for cluster picking, the **Allow splitting of work** parameter must be turned on, and the *SO Pick* work class must be added.</span></span>

1. <span data-ttu-id="fcee9-157">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-157">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="fcee9-158">A lista ablaktáblán válassza ki a **Fürtkitárolás létrehozása** rekordot.</span><span class="sxs-lookup"><span data-stu-id="fcee9-158">In the list pane, select the **Cluster Pick Create** record.</span></span>
1. <span data-ttu-id="fcee9-159">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-159">Select **Edit** in the Action pane.</span></span>
1. <span data-ttu-id="fcee9-160">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="fcee9-160">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fcee9-161">**Elrendelte:** *Fürtkitárolás*</span><span class="sxs-lookup"><span data-stu-id="fcee9-161">**Directed by:** *Cluster picking*</span></span>
    - <span data-ttu-id="fcee9-162">**Azonosítótábla létrehozása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="fcee9-162">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="fcee9-163">**Munka felosztásának engedélyezése:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="fcee9-163">**Allow splitting of work:** *Yes*</span></span>
    - <span data-ttu-id="fcee9-164">**Fürt profil azonosítója:** *Fürt létrehozása*</span><span class="sxs-lookup"><span data-stu-id="fcee9-164">**Cluster profile ID:** *Create Cluster*</span></span>

    <span data-ttu-id="fcee9-165">Az összes többi mezőben hagyja meg az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="fcee9-165">Accept the default values for all other fields.</span></span>

1. <span data-ttu-id="fcee9-166">A **Munkaosztályok** gyorslapon szükség szerint adja meg a következő két sort:</span><span class="sxs-lookup"><span data-stu-id="fcee9-166">On the **Work classes** FastTab, add the following two lines, as required:</span></span>

    - <span data-ttu-id="fcee9-167">1. sor (általában a demó adatokban szerepel):</span><span class="sxs-lookup"><span data-stu-id="fcee9-167">Line 1 (usually present in demo data):</span></span>

        - <span data-ttu-id="fcee9-168">**Munkaosztály azonosítója:** *Értékesítés*</span><span class="sxs-lookup"><span data-stu-id="fcee9-168">**Work class ID:** *Sales*</span></span> 
        - <span data-ttu-id="fcee9-169">**Munkarendelés típusa:** *Értékesítési rendelések*</span><span class="sxs-lookup"><span data-stu-id="fcee9-169">**Work order type:** *Sales orders*</span></span>

    - <span data-ttu-id="fcee9-170">2. sor (A demó adatokban valószínűleg nem szerepel):</span><span class="sxs-lookup"><span data-stu-id="fcee9-170">Line 2 (probably not present in demo data):</span></span>

        - <span data-ttu-id="fcee9-171">**Munkaosztály azonosítója:** *SO Pick*</span><span class="sxs-lookup"><span data-stu-id="fcee9-171">**Work class ID:** *SO Pick*</span></span>
        - <span data-ttu-id="fcee9-172">**Munkarendelés típusa:** *Értékesítési rendelések*</span><span class="sxs-lookup"><span data-stu-id="fcee9-172">**Work order type:** *Sales orders*</span></span>

1. <span data-ttu-id="fcee9-173">Nyissa meg a Műveleti panelen a **Munka visszaigazolásának beállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-173">Go to **Work confirmation setup** in the Action pane.</span></span>
1. <span data-ttu-id="fcee9-174">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="fcee9-174">Select **Edit**.</span></span>
1. <span data-ttu-id="fcee9-175">Adja meg a következő értékeket a soron a rácsban.</span><span class="sxs-lookup"><span data-stu-id="fcee9-175">Enter the following values on the line in grid.</span></span>
    - <span data-ttu-id="fcee9-176">**Munka típusa** - *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="fcee9-176">**Work type** - *Pick*</span></span>
    - <span data-ttu-id="fcee9-177">**Termék visszaigazolása** - *Jelölje be a jelölőnégyzetet*</span><span class="sxs-lookup"><span data-stu-id="fcee9-177">**Product confirmation** - *Select the check box*</span></span>

1. <span data-ttu-id="fcee9-178">Válassza a műveleti ablaktábla **Mentés** elemét, majd zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fcee9-178">Select **Save** in the Action pane and close the page.</span></span>

## <a name="create-picking-work"></a><span data-ttu-id="fcee9-179">Kitárolási munka létrehozása</span><span class="sxs-lookup"><span data-stu-id="fcee9-179">Create picking work</span></span>

<span data-ttu-id="fcee9-180">A fürtök kitárolásának elkezdése előtt létre kell hoznia egy kimenő munkát.</span><span class="sxs-lookup"><span data-stu-id="fcee9-180">Before you can start cluster picking, you must create some outbound work.</span></span> <span data-ttu-id="fcee9-181">A korábban létrehozott fürtprofil két fürtpozíciót határoz meg.</span><span class="sxs-lookup"><span data-stu-id="fcee9-181">The cluster profile that you created earlier specifies two cluster positions.</span></span> <span data-ttu-id="fcee9-182">Emiatt legalább két munkaazonosítót kell létrehozni az értékesítési rendelés kitárolásához.</span><span class="sxs-lookup"><span data-stu-id="fcee9-182">Therefore, at least two work IDs must be created for sales order picking.</span></span> <span data-ttu-id="fcee9-183">Ehhez a helyzethez tranzakciók történnek a *61-es* raktárban , és ezek az *L0101* és *T0100* cikkeket fogják használni.</span><span class="sxs-lookup"><span data-stu-id="fcee9-183">For this scenario, transactions will occur in warehouse *61*, and they will use items *L0101* and *T0100*.</span></span> <span data-ttu-id="fcee9-184">A demó adatoknak elég aktuális készlettel kell rendelkezniük ezekből a cikkekből.</span><span class="sxs-lookup"><span data-stu-id="fcee9-184">The demo data should have enough on-hand inventory of these items.</span></span> <span data-ttu-id="fcee9-185">Győződjön meg róla, hogy elegendő készlet van a tranzakciók befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="fcee9-185">Make sure that you have enough inventory to complete the transactions.</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="fcee9-186">1. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="fcee9-186">Create sales order 1</span></span>

1. <span data-ttu-id="fcee9-187">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="fcee9-187">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="fcee9-188">Az 1. értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-188">Select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="fcee9-189">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="fcee9-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fcee9-190">**Vevőkód** *US-010*</span><span class="sxs-lookup"><span data-stu-id="fcee9-190">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="fcee9-191">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="fcee9-191">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="fcee9-192">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-192">Select **OK**.</span></span>
1. <span data-ttu-id="fcee9-193">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="fcee9-193">The new sales order is opened.</span></span> <span data-ttu-id="fcee9-194">Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy sort, amely a következő beállításokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="fcee9-194">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="fcee9-195">**Cikkszám:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="fcee9-195">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="fcee9-196">**Mennyiség:** *5*</span><span class="sxs-lookup"><span data-stu-id="fcee9-196">**Quantity:** *5*</span></span>

1. <span data-ttu-id="fcee9-197">A dátum a **Sor részletei** gyorslapon a **Szállítás** lapjának, a **Visszaigazolt szállítási dátum** mezőjében jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="fcee9-197">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="fcee9-198">Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy második sort, amely a következő beállításokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="fcee9-198">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="fcee9-199">**Cikkszám:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="fcee9-199">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="fcee9-200">**Mennyiség:** *20*</span><span class="sxs-lookup"><span data-stu-id="fcee9-200">**Quantity:** *20*</span></span>

1. <span data-ttu-id="fcee9-201">A dátum a **Sor részletei** gyorslapon a **Szállítás** lapjának, a **Visszaigazolt szállítási dátum** mezőjében jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="fcee9-201">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="fcee9-202">Minden újonnan hozzáadott sorhoz kövesse az alábbi lépéseket a készlet foglalásához:</span><span class="sxs-lookup"><span data-stu-id="fcee9-202">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="fcee9-203">Válassza ki azt a sort, amelyet le szeretne foglalni.</span><span class="sxs-lookup"><span data-stu-id="fcee9-203">Select the line to reserve.</span></span>
    2. <span data-ttu-id="fcee9-204">Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-204">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="fcee9-205">A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.</span><span class="sxs-lookup"><span data-stu-id="fcee9-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="fcee9-206">Zárja be a **Foglalás** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="fcee9-206">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="fcee9-207">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-207">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="fcee9-208">Amikor a feloldás elkészült, olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítót rakományazonosítót jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="fcee9-208">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="fcee9-209">2. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="fcee9-209">Create sales order 2</span></span>

1. <span data-ttu-id="fcee9-210">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="fcee9-210">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="fcee9-211">Az 2. értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-211">Select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="fcee9-212">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="fcee9-212">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fcee9-213">**Vevőkód** *US-011*</span><span class="sxs-lookup"><span data-stu-id="fcee9-213">**Customer account:** *US-011*</span></span>
    - <span data-ttu-id="fcee9-214">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="fcee9-214">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="fcee9-215">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-215">Select **OK**.</span></span>
1. <span data-ttu-id="fcee9-216">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="fcee9-216">The new sales order is opened.</span></span> <span data-ttu-id="fcee9-217">Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy sort, amely a következő beállításokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="fcee9-217">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="fcee9-218">**Cikkszám:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="fcee9-218">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="fcee9-219">**Mennyiség:** *20*</span><span class="sxs-lookup"><span data-stu-id="fcee9-219">**Quantity:** *20*</span></span>

1. <span data-ttu-id="fcee9-220">A dátum a **Sor részletei** gyorslapon a **Szállítás** lapjának, a **Visszaigazolt szállítási dátum** mezőjében jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="fcee9-220">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="fcee9-221">Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy második sort, amely a következő beállításokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="fcee9-221">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="fcee9-222">**Cikkszám:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="fcee9-222">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="fcee9-223">**Mennyiség:** *2*</span><span class="sxs-lookup"><span data-stu-id="fcee9-223">**Quantity:** *2*</span></span>

1. <span data-ttu-id="fcee9-224">A dátum a **Sor részletei** gyorslapon a **Szállítás** lapjának, a **Visszaigazolt szállítási dátum** mezőjében jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="fcee9-224">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="fcee9-225">Minden újonnan hozzáadott sorhoz kövesse az alábbi lépéseket a készlet foglalásához:</span><span class="sxs-lookup"><span data-stu-id="fcee9-225">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="fcee9-226">Válassza ki azt a sort, amelyet le szeretne foglalni.</span><span class="sxs-lookup"><span data-stu-id="fcee9-226">Select the line to reserve.</span></span>
    2. <span data-ttu-id="fcee9-227">Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-227">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="fcee9-228">A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.</span><span class="sxs-lookup"><span data-stu-id="fcee9-228">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="fcee9-229">Zárja be a **Foglalás** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="fcee9-229">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="fcee9-230">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-230">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="fcee9-231">Amikor a feloldás elkészült, olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítót rakományazonosítót jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="fcee9-231">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="get-work-ids-and-license-plate-numbers"></a><span data-ttu-id="fcee9-232">Munkaazonosítók és azonosítótábla-számok beolvasása</span><span class="sxs-lookup"><span data-stu-id="fcee9-232">Get work IDs and license plate numbers</span></span>

<span data-ttu-id="fcee9-233">Két munkaazonosítót kellett létrehozni, amelyek mindegyikében két kitárolási sor van.</span><span class="sxs-lookup"><span data-stu-id="fcee9-233">Two work IDs should have been created, each of which has two pick lines.</span></span> <span data-ttu-id="fcee9-234">A munkaazonosítók és az azonosítótábla-hozzárendelések megkereséséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="fcee9-234">Follow these steps to find the work IDs and license plate assignments.</span></span>

1. <span data-ttu-id="fcee9-235">Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.</span><span class="sxs-lookup"><span data-stu-id="fcee9-235">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="fcee9-236">Az **Áttekintés** rácsban keresse meg az imént létrehozott két értékesítési **Rendelési szám** oszlopát.</span><span class="sxs-lookup"><span data-stu-id="fcee9-236">In the **Overview** grid, search the **Order number** column for the two sales orders that you just created.</span></span> <span data-ttu-id="fcee9-237">Jegyezze fel az egyes értékesítési rendelések kapcsolódó munkaazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="fcee9-237">For each sales order, make a note of the corresponding work ID.</span></span>
1. <span data-ttu-id="fcee9-238">Válassza ki az egyes értékesítési rendelések sorát a **Sorok** rácsban.</span><span class="sxs-lookup"><span data-stu-id="fcee9-238">Select the row for each sales order to show related information in the **Lines** grid.</span></span> <span data-ttu-id="fcee9-239">Jegyezze fel azt a helyet, ahonnan a cikkek kitárolása történik.</span><span class="sxs-lookup"><span data-stu-id="fcee9-239">Make a note of the location that each item will be picked from.</span></span>
1. <span data-ttu-id="fcee9-240">Menjen a **Készletkezelés \> Lekérdezések és jelentések \> Aktuális készletlista** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-240">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="fcee9-241">A műveleti ablaktáblán kattintson a **Dimenziók** gombra a **Dimenziók megjelenítése** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="fcee9-241">On the Action Pane, select **Dimensions** to open the **Dimension display** dialog box.</span></span>
1. <span data-ttu-id="fcee9-242">Győződjön meg róla, hogy be van jelölve az **Azonosítótábla** a **Raktár** és a **Cikkszám** jelölőnégyzet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="fcee9-242">Make sure that the **License plate**, **Warehouse**, and **Item number** check boxes are selected, and then select **OK**.</span></span>
1. <span data-ttu-id="fcee9-243">A **Szűrő** ablaktáblában adja meg a következő szűrőket:</span><span class="sxs-lookup"><span data-stu-id="fcee9-243">In the **Filter** pane, set the following filters:</span></span>

    - <span data-ttu-id="fcee9-244">**Cikkszám** – **egyike a következőknek** – *L0101* és *T100*</span><span class="sxs-lookup"><span data-stu-id="fcee9-244">**Item number** – **is one of** – *L0101* and *T100*</span></span>
    - <span data-ttu-id="fcee9-245">**Raktár** – **így kezdődik** – *61*</span><span class="sxs-lookup"><span data-stu-id="fcee9-245">**Warehouse** – **begins with** – *61*</span></span>

1. <span data-ttu-id="fcee9-246">Jegyezze fel a megjelenő **Azonosítótábla** értékeket.</span><span class="sxs-lookup"><span data-stu-id="fcee9-246">Make a note of the **License plate** values that are shown.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="fcee9-247">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="fcee9-247">Example scenario</span></span>

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a><span data-ttu-id="fcee9-248">Mobileszköz-folyamat végrehajtása – A termékre vonatkozó munka-visszaigazolás beállítása</span><span class="sxs-lookup"><span data-stu-id="fcee9-248">Mobile device flow execution – Work confirmation setup for the product</span></span>

1. <span data-ttu-id="fcee9-249">Jelentkezzen be az *61*-es raktárban lévő felhasználóként a raktár alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="fcee9-249">Sign in to the warehouse app as a user in warehouse *61*.</span></span>
1. <span data-ttu-id="fcee9-250">Menjen a **Kimenő \> Fürtkitárolás létrehozása** helyre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-250">Go to **Outbound \> Cluster pick create**.</span></span>

    <span data-ttu-id="fcee9-251">Megjelenik a **Feladat: Munka hozzárendelése a fürthöz** lap.</span><span class="sxs-lookup"><span data-stu-id="fcee9-251">The **TASK: Assign work to Cluster** page appears.</span></span>

1. <span data-ttu-id="fcee9-252">Adja meg az 1. értékesítési rendelés munkaazonosítóját az 1. fürtcsoporthoz való hozzárendeléséhez.</span><span class="sxs-lookup"><span data-stu-id="fcee9-252">Enter the work ID for sales order 1 to assign it to cluster position 1.</span></span>
1. <span data-ttu-id="fcee9-253">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-253">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="fcee9-254">Adja meg az 2. értékesítési rendelés munkaazonosítóját az 2. fürtcsoporthoz való hozzárendeléséhez.</span><span class="sxs-lookup"><span data-stu-id="fcee9-254">Enter the work ID for sales order 2 to assign it to cluster position 2.</span></span>
1. <span data-ttu-id="fcee9-255">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-255">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="fcee9-256">A **FELADAT: Fürtkitárolás létrehozása: kitárolás** oldal jelenik meg, és a *Item L0101 2 PL cikk* értéket jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="fcee9-256">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item L0101 2 PL*.</span></span>

<span data-ttu-id="fcee9-257">Mivel a fürtprofilban a pozíciók száma 2, a rendszer automatikusan átirányítja az első konszolidáló kitárolásához: két raklap (PL) az *L0101* cikkből.</span><span class="sxs-lookup"><span data-stu-id="fcee9-257">Because the cluster profile set the number of positions to 2, the system automatically directs you to the first consolidate pick: two pallets (PL) of item *L0101*.</span></span>

<span data-ttu-id="fcee9-258">A következő lépések során bármikor a **Részletek** lapon megtekintheti a feladattal kapcsolatos további adatokat, például a kitárolási helyet.</span><span class="sxs-lookup"><span data-stu-id="fcee9-258">At any time during the following steps, you can select the **Details** tab to view additional information about the task, such as the picking location.</span></span>

1. <span data-ttu-id="fcee9-259">Állítsa a **CIKK** mezőt *L0101* értékre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-259">Set the **ITEM** field to *L0101*.</span></span> <span data-ttu-id="fcee9-260">Ez megerősíti a cikkszámot, amely szükséges ehhez a menüelemhez (ezt a beállítást korábban konfigurálta a **Munka-visszaigazolás beállítása** helyen a **Mobileszköz menüelem** oldalon, amikor létrehozta ezt a menüelemet).</span><span class="sxs-lookup"><span data-stu-id="fcee9-260">This confirms the item number, which is required for this menu item (you configured this earlier by selecting **Work confirmation setup**  from the **Mobile device menu item** page when you created this menu item).</span></span>
1. <span data-ttu-id="fcee9-261">Adja meg, hogy milyen azonosítótábla van társítva a cikkhez a kitárolás alatt álló helyen.</span><span class="sxs-lookup"><span data-stu-id="fcee9-261">Enter the license plate number that is associated with the item in the location that is being picked.</span></span> <span data-ttu-id="fcee9-262">Két raklapot fog kitárolni.</span><span class="sxs-lookup"><span data-stu-id="fcee9-262">You will pick two pallets.</span></span>
1. <span data-ttu-id="fcee9-263">Állítsa az **LP** mezőt *LP\_KITÁROLÁS\_01* értékre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-263">Set the **LP** field to *LP\_PICK\_01*.</span></span>
1. <span data-ttu-id="fcee9-264">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-264">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="fcee9-265">Megjelenik **FELADAT: Rendezés: Fürtkitárolás létrehozása** oldal.</span><span class="sxs-lookup"><span data-stu-id="fcee9-265">The **TASK: Sort: Cluster Pick Create** page appears.</span></span> <span data-ttu-id="fcee9-266">Itt rendezni fogja a két kitárolt raklapot egy kitárolási pozícióba.</span><span class="sxs-lookup"><span data-stu-id="fcee9-266">Here, you will sort the two picked pallets into a pick position.</span></span> <span data-ttu-id="fcee9-267">Ez a beosztás olyan ládát vagy tároló lehet, amely a kitárolt készlet értékesítési rendelés szerinti elkülönítésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="fcee9-267">This position might be a tote or container that is used to separate the picked inventory by sales order.</span></span>

1. <span data-ttu-id="fcee9-268">A cikkhez (*L0101*) és mennyiséghez (*20* ea) megjelenített részletek megjelenítésem amelyek az 1-es pozícióba lesznek rendezve (az 1. értékesítési rendeléshez).</span><span class="sxs-lookup"><span data-stu-id="fcee9-268">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="fcee9-269">Állítsa a **POZÍCIÓ NA** mezőt *1* értékre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-269">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="fcee9-270">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-270">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="fcee9-271">A cikkhez (*L0101*) és mennyiséghez (*20* ea) megjelenített részletek megjelenítésem amelyek az 2-es pozícióba lesznek rendezve (az 2. értékesítési rendeléshez).</span><span class="sxs-lookup"><span data-stu-id="fcee9-271">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="fcee9-272">Állítsa a **POZÍCIÓ NA** mezőt *2* értékre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-272">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="fcee9-273">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-273">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="fcee9-274">A **FELADAT: Fürtkitárolás létrehozása: kitárolás** oldal jelenik meg, és a *Item T0100 7 ea* értéket jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="fcee9-274">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item T0100 7 ea*.</span></span>

<span data-ttu-id="fcee9-275">Ebben az esetben az 1. pozíció nem fogadja el a cikkek teljes mennyiségét, amelyet ki kell tárolni az 1. értékesítési rendelés teljesítéséhez.</span><span class="sxs-lookup"><span data-stu-id="fcee9-275">In this scenario, position 1 can't accept the full quantity of items that must be picked to fulfill sales order 1.</span></span> <span data-ttu-id="fcee9-276">A pozíciót telinek kell megjelölni.</span><span class="sxs-lookup"><span data-stu-id="fcee9-276">A position must be marked as full.</span></span> <span data-ttu-id="fcee9-277">Ebben a helyzetben a második elem részleges kitárolását fogja elvégezni.</span><span class="sxs-lookup"><span data-stu-id="fcee9-277">In this scenario, you will do a partial pick of the second item.</span></span> <span data-ttu-id="fcee9-278">A második cikk részben kitárolásra kerül az 1. pozícióban, és új munka jön létre, hogy kitárolja a rendelés teljesítéséhez szükséges maradék mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-278">The second item will be partially picked for position 1, and new work will be created to pick the remaining quantity to fulfill the order.</span></span>

1. <span data-ttu-id="fcee9-279">Válassza ki a lap tetején látható Menü gombot (néha hamburgernek vagy a hamburgergombnak is nevezik), majd válassza ki a **Pozíció tele** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-279">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Position full**.</span></span>
1. <span data-ttu-id="fcee9-280">Azonosítsa a teli beosztást, és válassza az *1* értéket.</span><span class="sxs-lookup"><span data-stu-id="fcee9-280">Identify the position that is full, and select *1*.</span></span>
1. <span data-ttu-id="fcee9-281">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-281">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="fcee9-282">Adja meg a kitárolási mennyiséget, amely az 1. pozícióba továbbra is kitárolható.</span><span class="sxs-lookup"><span data-stu-id="fcee9-282">Enter the pick quantity that can still be picked into position 1.</span></span> <span data-ttu-id="fcee9-283">A rendszer meghatározhatja, hogy mely cikkszám van kitárolva.</span><span class="sxs-lookup"><span data-stu-id="fcee9-283">The system can determine which item number is being picked.</span></span>
1. <span data-ttu-id="fcee9-284">Adja meg az *2* értéket.</span><span class="sxs-lookup"><span data-stu-id="fcee9-284">Enter *2*.</span></span>
1. <span data-ttu-id="fcee9-285">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-285">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="fcee9-286">A cikkszám jóváhagyása a fennmaradó cikkek kitárolásának a 2. pozícióba művelet befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="fcee9-286">Confirm the item number to complete the pick of the remaining item into position 2.</span></span>
1. <span data-ttu-id="fcee9-287">Állítsa a **CIKK** mezőt *T0100* értékre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-287">Set the **ITEM** field to *T0100*.</span></span>
1. <span data-ttu-id="fcee9-288">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-288">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="fcee9-289">Adja meg azt az azonosítótáblát, amelyből az elem ki lesz tárolva, ehhez az **LP** mezőt *LPREPL04* értékre kell állítani.</span><span class="sxs-lookup"><span data-stu-id="fcee9-289">Enter the license plate that the item is being picked from by setting the **LP** field to *LPREPL04*.</span></span>
1. <span data-ttu-id="fcee9-290">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-290">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="fcee9-291">A cikkhez (*T0100*) és mennyiséghez (*2* ea) megjelenített részletek megjelenítésem amelyek az 2-es pozícióba lesznek rendezve (az 2. értékesítési rendeléshez).</span><span class="sxs-lookup"><span data-stu-id="fcee9-291">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="fcee9-292">Állítsa a **POZÍCIÓ NA** mezőt *2* értékre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-292">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="fcee9-293">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-293">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="fcee9-294">A cikkhez (*T0100*) és mennyiséghez (*2* ea) megjelenített részletek megjelenítésem amelyek az 1-es pozícióba lesznek rendezve (az 1. értékesítési rendeléshez).</span><span class="sxs-lookup"><span data-stu-id="fcee9-294">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="fcee9-295">Állítsa a **POZÍCIÓ NA** mezőt *1* értékre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-295">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="fcee9-296">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-296">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="fcee9-297">Megjelenik **FELADAT: Rendezés: Betárolás létrehozása** oldal.</span><span class="sxs-lookup"><span data-stu-id="fcee9-297">The **TASK: Cluster Pick Create: Put** page appears.</span></span>

<span data-ttu-id="fcee9-298">Ebben a helyzetben a fürt kitárolása kész, és a felhasználó azt az utasítást kapja, hogy tárolja el a kitárolt cikkeket az 1. pozícióból és a 2. pozícióból a *STAGE01* előkészítő területre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-298">In this scenario, the cluster pick has been completed, and the user is directed to put away the picked items from position 1 and position 2 into staging location *STAGE01*.</span></span>

1. <span data-ttu-id="fcee9-299">Tekintse át a lap adatait.</span><span class="sxs-lookup"><span data-stu-id="fcee9-299">Review the information on the page.</span></span> <span data-ttu-id="fcee9-300">Azt jelzi, hogy a *44* a teljes mennyiség, ami az előkészítési helyre kerül.</span><span class="sxs-lookup"><span data-stu-id="fcee9-300">It shows that a total quantity of *44* will be put to the staging location.</span></span>
1. <span data-ttu-id="fcee9-301">Jelölje be az **OK** lehetőséget (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="fcee9-301">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="fcee9-302">Megjelenik a „Fürt befejezve” üzenet.</span><span class="sxs-lookup"><span data-stu-id="fcee9-302">You receive a "Cluster Completed" message.</span></span>

<span data-ttu-id="fcee9-303">Ezután az **Értékesítési kitárolás** menüelemmel kitárolhatja a fennmaradó mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="fcee9-303">You can now use the **Sales Picking** menu item to pick the remaining quantity.</span></span> <span data-ttu-id="fcee9-304">Ezután az **Értékesítési rakodása** menüelemmel mozgathatja a cikkeket az előkészítési helyről a rakodási helyre.</span><span class="sxs-lookup"><span data-stu-id="fcee9-304">You can then use the **Sales loading** menu item to move the items from the staging location to the loading dock.</span></span>
