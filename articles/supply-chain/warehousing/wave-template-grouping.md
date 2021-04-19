---
title: Hullámsablon csoportosítása
description: A hullámsablon csoportosítása lehetővé teszi a rendszer számára, hogy hullámsablon-beállítások használatával határozza meg, az Ön által megadott feltételek alapján, hogy hogyan kell megosztani a kiadott sorokat, és hozzárendelni azokat az új vagy meglévő hullámokhoz. Ez a funkció jól használható olyan raktárakban, ahol a hullámok meghatározott feltételek alapján jönnek létre, de a vezetők a kézi helyett az automatikus hullámlétrehozást részesítik előnyben.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: a591624f6611148abe4888e67d8d3a9bbea9cd27
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838034"
---
# <a name="wave-template-grouping"></a><span data-ttu-id="b9728-104">Hullámsablon csoportosítása</span><span class="sxs-lookup"><span data-stu-id="b9728-104">Wave template grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b9728-105">A hullámsablon csoportosítása lehetővé teszi a rendszer számára, hogy [hullámsablon](tasks/configure-wave-processing.md)-beállítások használatával határozza meg, az Ön által megadott feltételek alapján, hogy hogyan kell megosztani a kiadott sorokat, és hozzárendelni azokat az új vagy meglévő hullámokhoz.</span><span class="sxs-lookup"><span data-stu-id="b9728-105">Wave template grouping enables the system to use [wave template](tasks/configure-wave-processing.md) setups to determine, based on criteria that you define, how it should split released lines and assign them to new or existing waves.</span></span> <span data-ttu-id="b9728-106">Ez a funkció jól használható olyan raktárakban, ahol a hullámok meghatározott feltételek alapján jönnek létre, de a vezetők a kézi helyett az automatikus hullámlétrehozást részesítik előnyben.</span><span class="sxs-lookup"><span data-stu-id="b9728-106">This feature can be useful in warehouses where waves are created based on specific criteria, but where managers prefer to create waves automatically instead of manually.</span></span> <span data-ttu-id="b9728-107">Ez lehetővé teszi a rendszer számára, hogy minden újonnan kiadott szállítmányt hozzáadjon az első hullámhoz, amelyeknél megállapítja, hogy megfelelő csoportosítási mezőértékeket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="b9728-107">It enables the system to add each newly released shipment to the first wave that it finds that has matching grouping field values.</span></span> <span data-ttu-id="b9728-108">Ha nem talál egyezést, akkor a rendszer új hullámot hoz létre az új szállítmányhoz.</span><span class="sxs-lookup"><span data-stu-id="b9728-108">If no match is found, the system creates a new wave for the new shipment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9728-109">A hullámsablon csoportosítása nem támogatott a *termelési nyersanyag-kitárolás* vagy *Kanban-kitárolás* típusok esetében.</span><span class="sxs-lookup"><span data-stu-id="b9728-109">Wave template grouping isn't supported for the work types *production raw material picking* or *Kanban picking*.</span></span> <span data-ttu-id="b9728-110">Ennek az az oka, hogy a hullámcsoportosítás a szállítmányokon alapul, és ezek a munkatípusok nem használnak szállítmányokat.</span><span class="sxs-lookup"><span data-stu-id="b9728-110">This is because wave grouping is based on shipments and these work types don't use shipments.</span></span>

## <a name="turn-on-the-wave-template-grouping-feature"></a><span data-ttu-id="b9728-111">A Hullámsablon-csoportosítás funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="b9728-111">Turn on the Wave template grouping feature</span></span>

<span data-ttu-id="b9728-112">A *Hullámsablon-csoportosítás* funkciót használata előtt be kell kapcsolni a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="b9728-112">Before you can use the *Wave template grouping* feature, it must be turned on in your system.</span></span> <span data-ttu-id="b9728-113">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="b9728-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="b9728-114">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="b9728-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b9728-115">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="b9728-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b9728-116">**Funkció neve:** *Hullámsablon-csoportosítás*</span><span class="sxs-lookup"><span data-stu-id="b9728-116">**Feature name:** *Wave template grouping*</span></span>

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a><span data-ttu-id="b9728-117">Hullámsablon beállítása a hullámsablon-csoportosítás használatára</span><span class="sxs-lookup"><span data-stu-id="b9728-117">Set a wave template to use wave template grouping</span></span>

<span data-ttu-id="b9728-118">A hullámsablon-csoportosítás elérhetővé tételéhez hajtsa végre az alábbi lépéseket a [hullámsablon](tasks/configure-wave-processing.md) beállításához.</span><span class="sxs-lookup"><span data-stu-id="b9728-118">To make wave template grouping available, follow these steps to set up your [wave template](tasks/configure-wave-processing.md).</span></span>

1. <span data-ttu-id="b9728-119">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="b9728-119">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="b9728-120">A bal oldali ablaktáblában válassza ki a beállítani kívánt hullámsablont.</span><span class="sxs-lookup"><span data-stu-id="b9728-120">In the left pane, select the wave template to set up.</span></span> <span data-ttu-id="b9728-121">Ha a bemutató adatainak felhasználásával készül a témakörben később a forgatókönyvvel dolgozni, válassza ki a **62 Szállítási alapértelmezett** sablont.</span><span class="sxs-lookup"><span data-stu-id="b9728-121">If you're preparing to work through the scenario later in this topic by using demo data, select the **62 Shipping default** template.</span></span>
1. <span data-ttu-id="b9728-122">Válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.</span><span class="sxs-lookup"><span data-stu-id="b9728-122">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="b9728-123">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b9728-123">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="b9728-124">**Hullámlétrehozás automatizálása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="b9728-124">**Automate wave creation:** *Yes*</span></span>
    - <span data-ttu-id="b9728-125">**Hozzárendelés nyitott hullámokhoz:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="b9728-125">**Assign to open waves:** *Yes*</span></span>
    - <span data-ttu-id="b9728-126">**Hullám feldolgozása a raktárba történő kiadáskor:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="b9728-126">**Process wave at release to warehouse:** *No*</span></span>

1. <span data-ttu-id="b9728-127">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget a lekérdezés párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b9728-127">On the Action Pane, select **Edit query** to open the query dialog box.</span></span>
1. <span data-ttu-id="b9728-128">A lekérdezés párbeszédpanel **Rendezés** lapján tekintse át a rendezési feltételeket, és győződjön meg arról, hogy van olyan szabály, amely tartalmazza a hullámok csoportosítására használni kívánt mezőt.</span><span class="sxs-lookup"><span data-stu-id="b9728-128">In the query dialog box, on the **Sorting** tab, review the sorting criteria, and make sure that there is a rule that includes the field that you want to use to group your waves.</span></span>

    <span data-ttu-id="b9728-129">Ha a bemutató adatainak felhasználásával készül a forgatókönyv alapján dolgozni, vegyen fel egy sort, amely a következő értékeket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="b9728-129">If you're preparing to work through the scenario by using demo data, add a row that has the following values:</span></span>

    - <span data-ttu-id="b9728-130">**Tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="b9728-130">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="b9728-131">**Származtatott tábla:** *Szállítmányok*</span><span class="sxs-lookup"><span data-stu-id="b9728-131">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="b9728-132">**Mező:** *Szállítmányozói szolgáltatás*</span><span class="sxs-lookup"><span data-stu-id="b9728-132">**Field:** *Carrier service*</span></span>

        > [!NOTE]
        > <span data-ttu-id="b9728-133">Miután kiválasztotta ezt az értéket, a következő üzenet jelenhet meg: „A Szállítmányozói szolgáltatás nem egy indexmező.</span><span class="sxs-lookup"><span data-stu-id="b9728-133">After you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="b9728-134">Szeretne rendezést hozzáadni?”</span><span class="sxs-lookup"><span data-stu-id="b9728-134">Do you want to add sorting on this?"</span></span> <span data-ttu-id="b9728-135">Válassza az **Igen** lehetőséget a rendezés hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="b9728-135">Select **Yes** to add sorting.</span></span>

    - <span data-ttu-id="b9728-136">**Keresés iránya:** *Növekvő*</span><span class="sxs-lookup"><span data-stu-id="b9728-136">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="b9728-137">Az **OK** gombra kattintva mentse a változtatásokat, és zárja be a lekérdezés párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b9728-137">Select **OK** to save your changes and close the query dialog box.</span></span>
1. <span data-ttu-id="b9728-138">A műveleti ablaktáblán válassza ki a **Hullámsablon-csoportosítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b9728-138">On the Action Pane, select **Wave template grouping**.</span></span>
1. <span data-ttu-id="b9728-139">A **Hullámsablon-csoportosítás** oldalon jelölje be a **Csoportosítás** jelölőnégyzetet minden olyan sor esetében, amelyet alkalmazni szeretne a rendeléssorok hullámokba történő csoportosításához.</span><span class="sxs-lookup"><span data-stu-id="b9728-139">On the **Wave template grouping** page, select the **Group by** check box for each row that you want to use to group your order lines into waves, as required.</span></span> <span data-ttu-id="b9728-140">Ha a bemutató adatainak felhasználásával készül a forgatókönyvön keresztül dolgozni, akkor jelölje be a **Csoportosítás alapja** jelölőnégyzetet a *Szállítmányozói szolgáltatás* sorában.</span><span class="sxs-lookup"><span data-stu-id="b9728-140">If you're preparing to work through the scenario by using demo data, select the **Group by** check box for the *Carrier service* row.</span></span>
1. <span data-ttu-id="b9728-141">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b9728-141">Select **Save**.</span></span>
1. <span data-ttu-id="b9728-142">Zárja be a **Hullámsablon-csoportosítás** lapot.</span><span class="sxs-lookup"><span data-stu-id="b9728-142">Close the **Wave template grouping** page.</span></span>
1. <span data-ttu-id="b9728-143">A sablon mentéséhez válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="b9728-143">Select **Save** to save your template.</span></span>

## <a name="scenario"></a><span data-ttu-id="b9728-144">Forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="b9728-144">Scenario</span></span>

<span data-ttu-id="b9728-145">Ez a szakasz egy olyan szkriptet mutat be, amellyel megtudhatja, hogy a funkció milyen módon működik, és hogyan kell használni.</span><span class="sxs-lookup"><span data-stu-id="b9728-145">This section provides a script that you can work through to learn what this feature does and how to work with it.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="b9728-146">A mintaadatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="b9728-146">Make sample data available</span></span>

<span data-ttu-id="b9728-147">Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="b9728-147">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="b9728-148">Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="b9728-148">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="b9728-149">A forgatókönyvet a gyártási rendszerben végzett munka során a funkció használatához útmutatásként is használhatja.</span><span class="sxs-lookup"><span data-stu-id="b9728-149">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="b9728-150">Ebben az esetben azonban a saját értékeit kell helyettesítenie, és előfordulhat, hogy bizonyos típusú kötelező rekordok hiányoznak, amelyeket a szabvány demóadatok biztosítanak.</span><span class="sxs-lookup"><span data-stu-id="b9728-150">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="scenario-wave-template-grouping"></a><span data-ttu-id="b9728-151">Forgatókönyv: Hullámsablon-csoportosítás</span><span class="sxs-lookup"><span data-stu-id="b9728-151">Scenario: Wave template grouping</span></span>

<span data-ttu-id="b9728-152">Ez a példa azt mutatja be, hogyan kell használni a hullámsablon-csoportosítást több hullámnak a hullámsablonban definiált feltételek alapján történő automatikus létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b9728-152">This scenario shows how to use wave template grouping to automatically create multiple waves, based on grouping criteria that are defined in a wave template.</span></span> <span data-ttu-id="b9728-153">Ebben a forgatókönyvben a hullámsablon úgy van beállítva a rendszerben, hogy szállítmányozói szolgáltatásonként egy hullámot hozzon létre.</span><span class="sxs-lookup"><span data-stu-id="b9728-153">In this scenario, the wave template is set up in the system to create one wave per carrier service.</span></span>

<span data-ttu-id="b9728-154">A kezdés előtt készítse elő a hullámsablont a témakör korábbi [Hullámsablon beállítása a hullámsablon-csoportosítás használatára](#set-up-template) szakaszában leírtak alapján.</span><span class="sxs-lookup"><span data-stu-id="b9728-154">Before you begin, prepare your wave template as described in the [Set a wave template to use wave template grouping](#set-up-template) section earlier in this topic.</span></span> <span data-ttu-id="b9728-155">Ha ebben a helyzetben a bemutatóadatokkal dolgozik, ügyeljen arra, hogy az adott eljárásban javasolt bemutatóadat-értékeket használja.</span><span class="sxs-lookup"><span data-stu-id="b9728-155">If you will be working with demo data for this scenario, be sure to use the demo data values that are suggested in that procedure.</span></span> <span data-ttu-id="b9728-156">Ez a beállítás az egyes értékesítési rendelésekhez megadott szállítmányozói szolgáltatás alapján csoportosítja a hullámokat.</span><span class="sxs-lookup"><span data-stu-id="b9728-156">This setup will group your waves according to the carrier service that is set for each sales order.</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="b9728-157">1. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="b9728-157">Create sales order 1</span></span>

1. <span data-ttu-id="b9728-158">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="b9728-158">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b9728-159">Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b9728-159">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="b9728-160">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b9728-160">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b9728-161">A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-004* számára.</span><span class="sxs-lookup"><span data-stu-id="b9728-161">On the **Customer** FastTab, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="b9728-162">Az **Általános** gyorslap **Raktár** mezőjében állítsa be az *62* értéket.</span><span class="sxs-lookup"><span data-stu-id="b9728-162">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="b9728-163">Válassza az **OK** gombot az új beszerzési rendelés létrehozásához és az **Értékesítési rendelés létrehozása** párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="b9728-163">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="b9728-164">Az új értékesítési rendelést a **Sorok** nézetben nyitja meg a program.</span><span class="sxs-lookup"><span data-stu-id="b9728-164">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="b9728-165">Jegyezze fel az értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="b9728-165">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="b9728-166">Váltson a **Fejléc** nézetre.</span><span class="sxs-lookup"><span data-stu-id="b9728-166">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="b9728-167">A **Szállítás** gyorslapon a **Szállítás** szakaszban adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b9728-167">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="b9728-168">**Szállítmányozó:** *Légitársaság*</span><span class="sxs-lookup"><span data-stu-id="b9728-168">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="b9728-169">**Szállítmányozói szolgáltatás:** *Légi*</span><span class="sxs-lookup"><span data-stu-id="b9728-169">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="b9728-170">Váltson vissza a **Sorok** nézetre.</span><span class="sxs-lookup"><span data-stu-id="b9728-170">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="b9728-171">Az **Értékesítési rendelés sorai** szakaszban válassza ki a **Sor hozzáadása** elemet egy sor rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="b9728-171">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="b9728-172">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b9728-172">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b9728-173">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="b9728-173">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="b9728-174">**Mennyiség:** *2*</span><span class="sxs-lookup"><span data-stu-id="b9728-174">**Quantity:** *2*</span></span>

1. <span data-ttu-id="b9728-175">Válassza ki az új rendelési sort, majd a **Készlet** menüben, a rács felett válassza a **Foglalás** pontot.</span><span class="sxs-lookup"><span data-stu-id="b9728-175">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="b9728-176">A **Foglalás** oldalon, a Művelet panelen válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.</span><span class="sxs-lookup"><span data-stu-id="b9728-176">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="b9728-177">Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="b9728-177">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="b9728-178">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.</span><span class="sxs-lookup"><span data-stu-id="b9728-178">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="b9728-179">Egy tájékoztató üzenet jelenik meg, amely a rendelés szállítmányát és hullámát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b9728-179">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="b9728-180">Jegyezze fel a hullám azonosítószámát és a szállítmány azonosítószámait.</span><span class="sxs-lookup"><span data-stu-id="b9728-180">Make a note of the wave ID number and the shipment ID numbers.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a><span data-ttu-id="b9728-181">Az 1. értékesítési rendelésből létrehozott hullám megtekintése</span><span class="sxs-lookup"><span data-stu-id="b9728-181">View the wave that was created from sales order 1</span></span>

1. <span data-ttu-id="b9728-182">Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.</span><span class="sxs-lookup"><span data-stu-id="b9728-182">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="b9728-183">Válassza ki az értékesítési rendelésből létrehozott hullám azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="b9728-183">Select the wave ID that was created from the sales order.</span></span>
1. <span data-ttu-id="b9728-184">A hullám részletei lap megnyitásához válassza a hullámazonosító hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="b9728-184">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="b9728-185">Figyelje meg, hogy a szállítmány hozzá lett adva a **Hullámsorok** gyorslaphoz.</span><span class="sxs-lookup"><span data-stu-id="b9728-185">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="b9728-186">2. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="b9728-186">Create sales order 2</span></span>

1. <span data-ttu-id="b9728-187">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="b9728-187">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b9728-188">Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b9728-188">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="b9728-189">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b9728-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b9728-190">A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-005* számára.</span><span class="sxs-lookup"><span data-stu-id="b9728-190">On the **Customer** FastTab, set the **Customer account** field to *US-005*.</span></span>
    - <span data-ttu-id="b9728-191">Az **Általános** gyorslap **Raktár** mezőjében állítsa be az *62* értéket.</span><span class="sxs-lookup"><span data-stu-id="b9728-191">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="b9728-192">Válassza az **OK** gombot az új beszerzési rendelés létrehozásához és az **Értékesítési rendelés létrehozása** párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="b9728-192">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="b9728-193">Az új értékesítési rendelést a **Sorok** nézetben nyitja meg a program.</span><span class="sxs-lookup"><span data-stu-id="b9728-193">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="b9728-194">Jegyezze fel az értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="b9728-194">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="b9728-195">Váltson a **Fejléc** nézetre.</span><span class="sxs-lookup"><span data-stu-id="b9728-195">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="b9728-196">A **Szállítás** gyorslapon a **Szállítás** szakaszban adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b9728-196">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="b9728-197">**Szállítmányozó:** *Virágszállító*</span><span class="sxs-lookup"><span data-stu-id="b9728-197">**Shipping carrier:** *Flower moving*</span></span>
    - <span data-ttu-id="b9728-198">**Szállítmányozói szolgáltatás:** *Std*</span><span class="sxs-lookup"><span data-stu-id="b9728-198">**Carrier service:** *Std*</span></span>

1. <span data-ttu-id="b9728-199">Váltson vissza a **Sorok** nézetre.</span><span class="sxs-lookup"><span data-stu-id="b9728-199">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="b9728-200">Az **Értékesítési rendelés sorai** szakaszban válassza ki a **Sor hozzáadása** elemet egy sor rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="b9728-200">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="b9728-201">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b9728-201">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b9728-202">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b9728-202">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b9728-203">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="b9728-203">**Quantity:** *1*</span></span>

1. <span data-ttu-id="b9728-204">Válassza ki az új rendelési sort, majd a **Készlet** menüben, a rács felett válassza a **Foglalás** pontot.</span><span class="sxs-lookup"><span data-stu-id="b9728-204">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="b9728-205">A **Foglalás** oldalon, a Művelet panelen válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.</span><span class="sxs-lookup"><span data-stu-id="b9728-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="b9728-206">Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="b9728-206">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="b9728-207">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.</span><span class="sxs-lookup"><span data-stu-id="b9728-207">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="b9728-208">Egy tájékoztató üzenet jelenik meg, amely a rendelés szállítmányát és hullámát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b9728-208">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="b9728-209">Jegyezze fel a hullám azonosítószámát és a szállítmány azonosítószámait.</span><span class="sxs-lookup"><span data-stu-id="b9728-209">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="b9728-210">Figyelje meg, hogy a hullámazonosító eltér az első értékesítési rendelés hullámazonosítójától.</span><span class="sxs-lookup"><span data-stu-id="b9728-210">Notice that the wave ID differs from the wave ID of the first sales order.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a><span data-ttu-id="b9728-211">A 2. értékesítési rendelésből létrehozott hullám megtekintése</span><span class="sxs-lookup"><span data-stu-id="b9728-211">View the wave that was created from sales order 2</span></span>

1. <span data-ttu-id="b9728-212">Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.</span><span class="sxs-lookup"><span data-stu-id="b9728-212">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="b9728-213">Válassza ki a második értékesítési rendelésből létrehozott hullám azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="b9728-213">Select the wave ID that was created from the second sales order.</span></span>
1. <span data-ttu-id="b9728-214">A hullám részletei lap megnyitásához válassza a hullámazonosító hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="b9728-214">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="b9728-215">Figyelje meg, hogy a szállítmány hozzá lett adva a **Hullámsorok** gyorslaphoz.</span><span class="sxs-lookup"><span data-stu-id="b9728-215">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

<span data-ttu-id="b9728-216">Új hullám jött létre ehhez a szállítmányhoz, mert az első értékesítési rendeléstől eltérő szállítmányozói szolgáltatásokat alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="b9728-216">A new wave was created for this shipment, because it uses a different carrier service than the first sales order.</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="b9728-217">3. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="b9728-217">Create sales order 3</span></span>

1. <span data-ttu-id="b9728-218">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="b9728-218">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b9728-219">Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b9728-219">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="b9728-220">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b9728-220">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b9728-221">A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-006* számára.</span><span class="sxs-lookup"><span data-stu-id="b9728-221">On the **Customer** FastTab, set the **Customer account** field to *US-006*.</span></span>
    - <span data-ttu-id="b9728-222">Az **Általános** gyorslap **Raktár** mezőjében állítsa be az *62* értéket.</span><span class="sxs-lookup"><span data-stu-id="b9728-222">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="b9728-223">Válassza az **OK** gombot az új beszerzési rendelés létrehozásához és az **Értékesítési rendelés létrehozása** párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="b9728-223">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="b9728-224">Az új értékesítési rendelést a **Sorok** nézetben nyitja meg a program.</span><span class="sxs-lookup"><span data-stu-id="b9728-224">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="b9728-225">Jegyezze fel az értékesítési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="b9728-225">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="b9728-226">Váltson a **Fejléc** nézetre.</span><span class="sxs-lookup"><span data-stu-id="b9728-226">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="b9728-227">A **Szállítás** gyorslapon a **Szállítás** szakaszban adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b9728-227">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="b9728-228">**Szállítmányozó:** *Légitársaság*</span><span class="sxs-lookup"><span data-stu-id="b9728-228">**Shipping carrier:** *Air Cargo*</span></span>
    - <span data-ttu-id="b9728-229">**Szállítmányozói szolgáltatás:** *Légi*</span><span class="sxs-lookup"><span data-stu-id="b9728-229">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="b9728-230">Váltson vissza a **Sorok** nézetre.</span><span class="sxs-lookup"><span data-stu-id="b9728-230">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="b9728-231">Az **Értékesítési rendelés sorai** szakaszban válassza ki a **Sor hozzáadása** elemet egy sor rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="b9728-231">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="b9728-232">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b9728-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b9728-233">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b9728-233">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b9728-234">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="b9728-234">**Quantity:** *1*</span></span>

1. <span data-ttu-id="b9728-235">Válassza ki az új rendelési sort, majd a **Készlet** menüben, a rács felett válassza a **Foglalás** pontot.</span><span class="sxs-lookup"><span data-stu-id="b9728-235">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="b9728-236">A **Foglalás** oldalon, a Művelet panelen válassza ki az **Adag foglalása** lehetőséget, hogy lefoglalja a kiválasztott sor teljes mennyiségét a raktárban.</span><span class="sxs-lookup"><span data-stu-id="b9728-236">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="b9728-237">Zárja be a **Foglalás** lapot, hogy visszatérjen az értékesítési rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="b9728-237">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="b9728-238">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.</span><span class="sxs-lookup"><span data-stu-id="b9728-238">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="b9728-239">Egy tájékoztató üzenet jelenik meg, amely a rendelés szállítmányát és hullámát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b9728-239">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="b9728-240">Jegyezze fel a hullám azonosítószámát és a szállítmány azonosítószámait.</span><span class="sxs-lookup"><span data-stu-id="b9728-240">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="b9728-241">A szállítmány már hozzá van rendelve a meglévő hullámhoz az első értékesítési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="b9728-241">The shipment has been assigned to the existing wave from the first sales order.</span></span>

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a><span data-ttu-id="b9728-242">Az 1. és 3. értékesítési rendelések hullámának megtekintése</span><span class="sxs-lookup"><span data-stu-id="b9728-242">View the wave for sales orders 1 and 3</span></span>

1. <span data-ttu-id="b9728-243">Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.</span><span class="sxs-lookup"><span data-stu-id="b9728-243">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="b9728-244">Válassza ki a harmadik értékesítési rendelésből létrehozott hullám azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="b9728-244">Select the wave ID that was created from the third sales order.</span></span>
1. <span data-ttu-id="b9728-245">A hullám részletei lap megnyitásához válassza a hullámazonosító hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="b9728-245">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="b9728-246">Figyelje meg, hogy a szállítmány hozzá van-e rendelve a **Hullámsorok** gyorslaphoz az első értékesítési rendeléshez tartozó szállítmánnyal együtt.</span><span class="sxs-lookup"><span data-stu-id="b9728-246">Notice that the shipment has been added to the **Wave lines** FastTab, together with the shipment for the first sales order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]