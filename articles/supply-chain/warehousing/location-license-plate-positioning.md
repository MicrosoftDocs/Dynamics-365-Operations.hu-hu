---
title: Hely és azonosítótábla pozicionálása
description: Az azonosítótábla elhelyezésével megtekintheti, hogy hol található az azonosítótábla egy több raklapos helyen, például olyan helyen, amely dupla mélységű raklapállványt használ.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: e5fd7a9a9703f9ab6802def0aac096e29aa04f1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831386"
---
# <a name="location-license-plate-positioning"></a><span data-ttu-id="924fd-103">Hely és azonosítótábla pozicionálása</span><span class="sxs-lookup"><span data-stu-id="924fd-103">Location license plate positioning</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="924fd-104">Az azonosítótábla elhelyezésével megtekintheti, hogy hol található az azonosítótábla egy több raklapos helyen, például olyan helyen, amely dupla mélységű raklapállványt használ.</span><span class="sxs-lookup"><span data-stu-id="924fd-104">License plate location positioning lets you see where a license plate is located in a multi-pallet location, such as a location that uses double-deep pallet racking.</span></span>

<span data-ttu-id="924fd-105">A szolgáltatás sorozatszámot ad minden olyan azonosítótáblához, amely tárolási helyre kerül.</span><span class="sxs-lookup"><span data-stu-id="924fd-105">The feature adds a sequence number to each license plate that is put into a storage location.</span></span> <span data-ttu-id="924fd-106">Ez a sorozatszám az azonosítótáblák rendezésére szolgál a tárolási helyen.</span><span class="sxs-lookup"><span data-stu-id="924fd-106">This sequence number is used to order the license plates in the storage location.</span></span> <span data-ttu-id="924fd-107">Ennélfogva a funkció intelligens módon támogatja azokat a helyzeteket, amelyekben a vevők gravitációs állványrendszert használnak, és a kitárolás céljából ismerniük kell, hogy az azonosítótáblák közül melyik van elöl.</span><span class="sxs-lookup"><span data-stu-id="924fd-107">Therefore, the feature intelligently supports scenarios where customers are using a gravity racking system and must know, for picking purposes, which license plate is front-facing.</span></span>

<span data-ttu-id="924fd-108">Ez a témakör azt mutatja be, hogyan lehet beállítani és használni a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="924fd-108">This topic presents a scenario that shows how to set up and use the feature.</span></span>

## <a name="turn-on-the-location-license-plate-positioning-feature"></a><span data-ttu-id="924fd-109">A helyazonosító tábla elhelyezési funkciójának bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="924fd-109">Turn on the Location license plate positioning feature</span></span>

<span data-ttu-id="924fd-110">Az azonosítótábla-elhelyezés használata előtt a funkciót be kall kapcsolni a rendszerében.</span><span class="sxs-lookup"><span data-stu-id="924fd-110">Before you can use license plate location positioning, the feature must be turned on in your system.</span></span> <span data-ttu-id="924fd-111">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="924fd-111">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="924fd-112">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="924fd-112">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="924fd-113">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="924fd-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="924fd-114">**Funkció neve:** *Helyazonosító tábla elhelyezése*</span><span class="sxs-lookup"><span data-stu-id="924fd-114">**Feature name:** *Location license plate positioning*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="924fd-115">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="924fd-115">Example scenario</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="924fd-116">A mintaadatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="924fd-116">Make sample data available</span></span>

<span data-ttu-id="924fd-117">Ha ezt a forgatókönyvet az itt javasolt mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszeren kell dolgoznia, amelynél a mintaadatok telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="924fd-117">To work through this scenario by using the values that are suggested here, you must work on a system where sample data is installed.</span></span> <span data-ttu-id="924fd-118">Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="924fd-118">Additionally, you must select the **USMF** legal entity before you start.</span></span>

### <a name="set-up-the-feature-for-this-scenario"></a><span data-ttu-id="924fd-119">A funkció beállítása ehhez a helyzethez</span><span class="sxs-lookup"><span data-stu-id="924fd-119">Set up the feature for this scenario</span></span>

<span data-ttu-id="924fd-120">Hajtsa végre a következő lépéseket az ebben a témakörben bemutatott *Helyazonosító tábla elhelyezése* funkció beállításához.</span><span class="sxs-lookup"><span data-stu-id="924fd-120">Complete the following procedures to set up the *Location license plate positioning* feature for the scenario that is presented in this topic.</span></span>

#### <a name="location-profiles"></a><span data-ttu-id="924fd-121">Helyprofilok</span><span class="sxs-lookup"><span data-stu-id="924fd-121">Location profiles</span></span>

<span data-ttu-id="924fd-122">A funkciót minden olyan hely helyprofiljában be kell kapcsolni, ahol használatban lesz.</span><span class="sxs-lookup"><span data-stu-id="924fd-122">The feature must be turned on in the location profile for every location where it will be used.</span></span>

1. <span data-ttu-id="924fd-123">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.</span><span class="sxs-lookup"><span data-stu-id="924fd-123">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="924fd-124">A bal oldali ablaktáblán a helyprofilok listáján válassza a **BULK-06** értéket.</span><span class="sxs-lookup"><span data-stu-id="924fd-124">In the list of location profiles in the left pane, select **BULK-06**.</span></span>
1. <span data-ttu-id="924fd-125">Az **Általános** gyorslapon két új beállítás van hozzáadva a funkció által.</span><span class="sxs-lookup"><span data-stu-id="924fd-125">On the **General** FastTab, two new options have been added by the feature.</span></span> <span data-ttu-id="924fd-126">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="924fd-126">Set the following values:</span></span>

    - <span data-ttu-id="924fd-127">**Azonosítótábla-elhelyezés engedélyezése:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="924fd-127">**Enable license plate position:** *Yes*</span></span>

        <span data-ttu-id="924fd-128">Ha ez a beállítás *Igen* értékre van állítva, akkor a rendszer az azonosítótábla pozícióját fogja fenntartani a helyhez tartozó azonosítótábla esetében.</span><span class="sxs-lookup"><span data-stu-id="924fd-128">When this option is set to *Yes*, the license plate position will be maintained for license plates in the location.</span></span>

    - <span data-ttu-id="924fd-129">**Mobileszköz azonosítótábla-helyének megjelenítése:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="924fd-129">**Display mobile device LP position:** *Yes*</span></span>

        <span data-ttu-id="924fd-130">Ha ez a beállítás *Igen* értékre van állítva, akkor az azonosítótábla helye jelenik meg a mobileszköz-felhasználók számára a módosítás és a leltározás során.</span><span class="sxs-lookup"><span data-stu-id="924fd-130">When this option is set to *Yes*, the license plate position will be shown to mobile device users during adjustment and counting.</span></span> <span data-ttu-id="924fd-131">Ez a beállítás csak akkor módosítható, ha a funkció be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="924fd-131">You can change the setting of this option only when the feature is turned on.</span></span>

1. <span data-ttu-id="924fd-132">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-132">Select **Save**.</span></span>

#### <a name="location-directives"></a><span data-ttu-id="924fd-133">Helyutasítások</span><span class="sxs-lookup"><span data-stu-id="924fd-133">Location directives</span></span>

1. <span data-ttu-id="924fd-134">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="924fd-134">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="924fd-135">A bal oldali ablaktáblában győződjön meg arról, hogy a **Munkarendelés típusa** mező *Értékesítési rendelések* értékre van-e beállítva.</span><span class="sxs-lookup"><span data-stu-id="924fd-135">In the left pane, make sure that the **Work order type** field is set to *Sales orders*.</span></span>
1. <span data-ttu-id="924fd-136">Az irányelvek listáiban válassza a **61 SO kitárolási rendelés** elemet.</span><span class="sxs-lookup"><span data-stu-id="924fd-136">In the list of location directives, select **61 SO Pick order**.</span></span>
1. <span data-ttu-id="924fd-137">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-137">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="924fd-138">A **Sorok** gyorslapon válassza ki azt a sort, amelynél a **Sorozatszám** értéke *2*.</span><span class="sxs-lookup"><span data-stu-id="924fd-138">On the **Lines** FastTab, select the line that has a **Sequence number** value of *2*.</span></span>
1. <span data-ttu-id="924fd-139">A **Helyutasítás műveletei** gyorslapon válassza ki azt a sort, amely a *Kitárolás raklapnál kevesebbhez* (ennek kell az egyedüli sornak lennie) **Név** értékkel rendelkezik, és módosítsa a **Sorszám** beállítás a *2* értékre.</span><span class="sxs-lookup"><span data-stu-id="924fd-139">On the **Location Directive Actions** FastTab, select the line that has a **Name** value of *Pick for less than pallet* (it should be the only line), and change its **Sequence number** value to *2*.</span></span>
1. <span data-ttu-id="924fd-140">Válassza ki a rács fölötti **Új** lehetőséget, és hozzon létre egy új sort egy helyutasítási művelethez.</span><span class="sxs-lookup"><span data-stu-id="924fd-140">Select **New** above the grid to add a line for a new location directive action.</span></span>
1. <span data-ttu-id="924fd-141">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="924fd-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="924fd-142">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="924fd-142">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="924fd-143">**Név:** *1. kitárolási hely*</span><span class="sxs-lookup"><span data-stu-id="924fd-143">**Name:** *Pick position 1*</span></span>

1. <span data-ttu-id="924fd-144">Az új sort továbbra is kijelölve, válassza a rács fölötti **Lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="924fd-144">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="924fd-145">A lekérdezéstervezőben válassza az **Illesztések** lapot.</span><span class="sxs-lookup"><span data-stu-id="924fd-145">In the query editor, select the **Joins** tab.</span></span>
1. <span data-ttu-id="924fd-146">Bontsa ki a **Helyek** táblájának illesztéseit a **Készletdimenziók** táblával való kapcsolat megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="924fd-146">Expand the **Locations** table join to show the join to the **Inventory dimensions** table.</span></span>
1. <span data-ttu-id="924fd-147">Bontsa ki a **Készletdimenziók** táblájának illesztését az **Aktuális készlet** táblával való kapcsolat megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="924fd-147">Expand the **Inventory dimensions** table join to show the join to the **On-hand inventory** table.</span></span>
1. <span data-ttu-id="924fd-148">Válassza ki a **Készletdimenziók** lehetőséget, majd a , majd válassza a **Táblaillesztés hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-148">Select **Inventory dimensions**, and then select **Add table join**.</span></span>
1. <span data-ttu-id="924fd-149">A megjelenő táblák listáján, a **Kapcsolat** oszlopban válassza ki az **Azonosítótábla (Azonosítótábla)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-149">In the list of tables that appears, in the **Relation** column, select **License plate (License plate)**.</span></span> <span data-ttu-id="924fd-150">Ezután válassza a **Kiválasztás** lehetőséget **Azonosítótábla** hozzáadásához a **Készletdimenziók** táblaillesztéshez.</span><span class="sxs-lookup"><span data-stu-id="924fd-150">Then select **Select** to add **License plate** to the **Inventory dimensions** table join.</span></span>
1. <span data-ttu-id="924fd-151">Miközben az **Azonosítótábla** továbbra is be van jelölve, válassza a **Táblaillesztés hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-151">While **License plate** is still selected, select **Add table join**.</span></span>
1. <span data-ttu-id="924fd-152">A megjelenő táblák listáján, a **Kapcsolat** oszlopban válassza ki a **Helyazonosító tábla elhelyezése (Azonosítótábla)** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-152">In the list of tables that appears, in the **Relation** column, select **Location license plate positioning (License plate)**.</span></span> <span data-ttu-id="924fd-153">Ezután válassza a **Kiválasztás** lehetőséget **Helyazonosító tábla elhelyezése** elem hozzáadásához a **Készletdimenziók** táblaillesztéshez.</span><span class="sxs-lookup"><span data-stu-id="924fd-153">Then select **Select** to add **Location license plate positioning** to the **Inventory dimensions** table join.</span></span>

    <span data-ttu-id="924fd-154">![Táblaillesztések](media/LpTableJoin.png "Táblaillesztések")</span><span class="sxs-lookup"><span data-stu-id="924fd-154">![Table joins](media/LpTableJoin.png "Table joins")</span></span>

1. <span data-ttu-id="924fd-155">Az **OK** lehetőséget kiválasztva erősítse meg a frissített összekapcsolt táblákat, és zárja be a lekérdezésszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="924fd-155">Select **OK** to confirm the updated joined tables and close the query editor.</span></span>
1. <span data-ttu-id="924fd-156">A **Helyutasítások műveletei** gyorslapon válassza ismét a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő ismételt megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="924fd-156">On the **Location Directive Actions** FastTab, select **Edit query** again to reopen to the query editor.</span></span>
1. <span data-ttu-id="924fd-157">A **Tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="924fd-157">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="924fd-158">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="924fd-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="924fd-159">**Táblázat:** *Helyazonosító tábla elhelyezése*</span><span class="sxs-lookup"><span data-stu-id="924fd-159">**Table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="924fd-160">**Származtatott tábla:** *Helyazonosító tábla elhelyezése*</span><span class="sxs-lookup"><span data-stu-id="924fd-160">**Derived table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="924fd-161">**Mező:** *LP pozíció*</span><span class="sxs-lookup"><span data-stu-id="924fd-161">**Field:** *LP Position*</span></span>
    - <span data-ttu-id="924fd-162">**Feltételek:** *1*</span><span class="sxs-lookup"><span data-stu-id="924fd-162">**Criteria:** *1*</span></span>

    <span data-ttu-id="924fd-163">![Új tartomány](media/LpPositionCriteria.png "Új tartomány")</span><span class="sxs-lookup"><span data-stu-id="924fd-163">![New range](media/LpPositionCriteria.png "New range")</span></span>

1. <span data-ttu-id="924fd-164">Az **OK** gombra kattintva erősítse meg a változtatásokat, és zárja be a lekérdezésszerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="924fd-164">Select **OK** to confirm your changes and close the query editor.</span></span>

### <a name="set-up-sample-data-for-this-scenario"></a><span data-ttu-id="924fd-165">A mintaadatok beállítása ehhez a helyzethez</span><span class="sxs-lookup"><span data-stu-id="924fd-165">Set up sample data for this scenario</span></span>

<span data-ttu-id="924fd-166">Ennél a helyzetnél a felhasználónak be kell jelentkeznie a raktározási mobilalkalmazásba egy olyan dolgozóval, aki a *61*-es raktárhoz be van állítva munkavégzéshez.</span><span class="sxs-lookup"><span data-stu-id="924fd-166">For this scenario, the user must sign in to the warehousing mobile app by using a worker who is set up for warehouse *61* to perform work.</span></span> <span data-ttu-id="924fd-167">A felhasználónak is végre kell hajtania a tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="924fd-167">The user must also complete transactions.</span></span>

<span data-ttu-id="924fd-168">Mivel a *Helyazonosító tábla elhelyezése* funkció új azonosítót ad hozzá az azonosítótábla helyhez egy adott helyen, először létre kell hoznia néhány adatot a forgatókönyv támogatásához.</span><span class="sxs-lookup"><span data-stu-id="924fd-168">Because the *Location license plate positioning* feature adds a new identifier for license plate positions in a location, you must first create some data to support the scenario.</span></span>

#### <a name="spot-count-the-first-location"></a><span data-ttu-id="924fd-169">Az első hely eseti leltározása</span><span class="sxs-lookup"><span data-stu-id="924fd-169">Spot-count the first location</span></span>

1. <span data-ttu-id="924fd-170">Nyissa meg a raktározási alkalmazást, és jelentkezzen be a *61*-es raktárba.</span><span class="sxs-lookup"><span data-stu-id="924fd-170">Open the warehousing mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="924fd-171">Lépjen a **Készlet \> Eseti leltár** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="924fd-171">Go to **Inventory \> Spot Counting**.</span></span>
1. <span data-ttu-id="924fd-172">Az **Eseti leltár** oldalon adja meg a **Hely** mezőt a *01A01R1S1B* értékkel.</span><span class="sxs-lookup"><span data-stu-id="924fd-172">On the **Spot Counting** page, set the **Location** field to *01A01R1S1B*.</span></span>
1. <span data-ttu-id="924fd-173">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-173">Select **OK**.</span></span>

    <span data-ttu-id="924fd-174">A lap megjeleníti a megadott helyet.</span><span class="sxs-lookup"><span data-stu-id="924fd-174">The page shows the location that you entered.</span></span> <span data-ttu-id="924fd-175">Ezenkívül a következő üzenet jelenik meg: „Hely kész, új LP vagy cikk hozzáadása?”</span><span class="sxs-lookup"><span data-stu-id="924fd-175">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="924fd-176">Válassza a **Frissítés** lehetőséget, ha egy leltárfelvételt szeretne hozzáadni a helyhez.</span><span class="sxs-lookup"><span data-stu-id="924fd-176">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="924fd-177">A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki a **Cikk** mezőt, majd írja be az *A0001* értéket.</span><span class="sxs-lookup"><span data-stu-id="924fd-177">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0001*.</span></span>
1. <span data-ttu-id="924fd-178">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-178">Select **OK**.</span></span>
1. <span data-ttu-id="924fd-179">A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki az **LP** mezőt, majd írja be az *LP1001* (vagy a kiválasztott egyéb azonosítótábla) értékét.</span><span class="sxs-lookup"><span data-stu-id="924fd-179">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1001* (or any other license plate number of your choice).</span></span>

    <span data-ttu-id="924fd-180">A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldal megjeleníti az **1. azonosítótábla helye** értéket.</span><span class="sxs-lookup"><span data-stu-id="924fd-180">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="924fd-181">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-181">Select **OK**.</span></span>

    <span data-ttu-id="924fd-182">Ezután meg kell adnia az azonosítótáblán megszámlált cikkek mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="924fd-182">You must now specify the quantity of the item that is counted on the license plate.</span></span>

1. <span data-ttu-id="924fd-183">Állítsa a **Mennyiség** mezőt *10* értékre.</span><span class="sxs-lookup"><span data-stu-id="924fd-183">Set the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="924fd-184">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-184">Select **OK**.</span></span>

    <span data-ttu-id="924fd-185">A lap megjeleníti a megadott helyet.</span><span class="sxs-lookup"><span data-stu-id="924fd-185">The page shows the location that you entered.</span></span> <span data-ttu-id="924fd-186">Ezenkívül a következő üzenet jelenik meg: „Hely kész, új LP vagy cikk hozzáadása?”</span><span class="sxs-lookup"><span data-stu-id="924fd-186">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="924fd-187">Válassza a **Frissítés** lehetőséget, ha egy további leltárfelvételt szeretne hozzáadni a helyhez.</span><span class="sxs-lookup"><span data-stu-id="924fd-187">Select **Refresh** to add another count in the location.</span></span>
1. <span data-ttu-id="924fd-188">A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki a **Cikk** mezőt, majd írja be az *A0002* értéket.</span><span class="sxs-lookup"><span data-stu-id="924fd-188">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="924fd-189">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-189">Select **OK**.</span></span>
1. <span data-ttu-id="924fd-190">A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki az **LP** mezőt, majd adja meg az *LP1002* (vagy bármely egyéb kiválasztott azonosítótábla, feltéve, hogy az eltér a korábban megadott azonosítótáblától) értékét.</span><span class="sxs-lookup"><span data-stu-id="924fd-190">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1002* (or any other license plate number of your choice, provided that it differs from the license plate number that you specified earlier).</span></span>
1. <span data-ttu-id="924fd-191">Módosítsa az azonosítótábla pozícióját úgy, hogy az **LP hely** mező számára a *2* értéket állítja be.</span><span class="sxs-lookup"><span data-stu-id="924fd-191">Change the license plate position by setting the **LP Position** field to *2*.</span></span>
1. <span data-ttu-id="924fd-192">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-192">Select **OK**.</span></span>
1. <span data-ttu-id="924fd-193">Adja meg az azonosítótáblán megszámolt cikk mennyiségét a **Mennyiség** mezőt *10* értékre állítva.</span><span class="sxs-lookup"><span data-stu-id="924fd-193">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="924fd-194">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-194">Select **OK**.</span></span>

    <span data-ttu-id="924fd-195">A lap megjeleníti a megadott helyet.</span><span class="sxs-lookup"><span data-stu-id="924fd-195">The page shows the location that you entered.</span></span> <span data-ttu-id="924fd-196">Ezenkívül a következő üzenet jelenik meg: „Hely kész, új LP vagy cikk hozzáadása?”</span><span class="sxs-lookup"><span data-stu-id="924fd-196">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="924fd-197">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-197">Select **OK**.</span></span>

<span data-ttu-id="924fd-198">A munka ezzel befejeződött.</span><span class="sxs-lookup"><span data-stu-id="924fd-198">Work is now completed.</span></span>

#### <a name="spot-count-the-second-location"></a><span data-ttu-id="924fd-199">A második hely eseti leltározása</span><span class="sxs-lookup"><span data-stu-id="924fd-199">Spot-count the second location</span></span>

1. <span data-ttu-id="924fd-200">Az **Eseti leltár** oldalon adja meg a **Hely** mezőt a *01A01R1S2B* értékkel.</span><span class="sxs-lookup"><span data-stu-id="924fd-200">On the **Spot Counting** page, set the **Location** field to *01A01R1S2B*.</span></span>
1. <span data-ttu-id="924fd-201">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-201">Select **OK**.</span></span>

    <span data-ttu-id="924fd-202">A lap megjeleníti a megadott helyet.</span><span class="sxs-lookup"><span data-stu-id="924fd-202">The page shows the location that you entered.</span></span> <span data-ttu-id="924fd-203">Ezenkívül a következő üzenet jelenik meg: „Hely kész, új LP vagy cikk hozzáadása?”</span><span class="sxs-lookup"><span data-stu-id="924fd-203">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="924fd-204">Válassza a **Frissítés** lehetőséget, ha egy leltárfelvételt szeretne hozzáadni a helyhez.</span><span class="sxs-lookup"><span data-stu-id="924fd-204">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="924fd-205">A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki a **Cikk** mezőt, majd írja be az *A0002* értéket.</span><span class="sxs-lookup"><span data-stu-id="924fd-205">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="924fd-206">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-206">Select **OK**.</span></span>
1. <span data-ttu-id="924fd-207">A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldalon válassza ki az **LP** mezőt, majd adja meg az *LP1003* (vagy bármely egyéb kiválasztott azonosítótábla, feltéve, hogy az eltér a korábbi eljárásban megadott mindkét azonosítótáblától) értékét.</span><span class="sxs-lookup"><span data-stu-id="924fd-207">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1003* (or any other license plate number of your choice, provided that it differs from the both the license plate numbers that you specified in the previous procedure).</span></span>

    <span data-ttu-id="924fd-208">A **Ciklikus leltározás: Új LP vagy cikk hozzáadása** oldal megjeleníti az **1. azonosítótábla helye** értéket.</span><span class="sxs-lookup"><span data-stu-id="924fd-208">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="924fd-209">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-209">Select **OK**.</span></span>
1. <span data-ttu-id="924fd-210">Adja meg az azonosítótáblán megszámolt cikk mennyiségét a **Mennyiség** mezőt *10* értékre állítva.</span><span class="sxs-lookup"><span data-stu-id="924fd-210">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="924fd-211">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-211">Select **OK**.</span></span>

    <span data-ttu-id="924fd-212">A lap megjeleníti a megadott helyet.</span><span class="sxs-lookup"><span data-stu-id="924fd-212">The page shows the location that you entered.</span></span> <span data-ttu-id="924fd-213">Ezenkívül a következő üzenet jelenik meg: „Hely kész, új LP vagy cikk hozzáadása?”</span><span class="sxs-lookup"><span data-stu-id="924fd-213">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="924fd-214">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-214">Select **OK**.</span></span>

<span data-ttu-id="924fd-215">A munka ezzel befejeződött.</span><span class="sxs-lookup"><span data-stu-id="924fd-215">Work is now completed.</span></span>

#### <a name="work-details"></a><span data-ttu-id="924fd-216">Munka részletes adatai</span><span class="sxs-lookup"><span data-stu-id="924fd-216">Work details</span></span>

> [!NOTE]
> <span data-ttu-id="924fd-217">Az eseti leltár a mobilalkalmazásból ciklikus leltározási feladatot hoz létre a Microsoft Dynamics 365 alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="924fd-217">Spot counts from the mobile app create cycle counting work in Microsoft Dynamics 365.</span></span> <span data-ttu-id="924fd-218">A munka megköveteli, hogy a leltárt a program a készletbe történő feladás előtt elfogadja.</span><span class="sxs-lookup"><span data-stu-id="924fd-218">The work requires that the counts be accepted before they are posted to inventory.</span></span>

1. <span data-ttu-id="924fd-219">Jelentkezzen be a Dynamics 365 Supply Chain Management alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="924fd-219">Sign in to Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="924fd-220">Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.</span><span class="sxs-lookup"><span data-stu-id="924fd-220">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="924fd-221">Az **Áttekintés** lapon keressük meg azokat a sorokat, amelyek a következő értékeket jelentik:</span><span class="sxs-lookup"><span data-stu-id="924fd-221">On the **Overview** tab, look for the lines that have the following values:</span></span>

    - <span data-ttu-id="924fd-222">**Munkarendelés típusa:** *Ciklikus leltározás*</span><span class="sxs-lookup"><span data-stu-id="924fd-222">**Work order type:** *Cycle counting*</span></span>
    - <span data-ttu-id="924fd-223">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="924fd-223">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="924fd-224">**Munka állapota:** *Ellenőrzésre vár*</span><span class="sxs-lookup"><span data-stu-id="924fd-224">**Work status:** *Pending review*</span></span>

    <span data-ttu-id="924fd-225">Ezekhez a sorokhoz két munkaazonosítónak kellett létrejönnie.</span><span class="sxs-lookup"><span data-stu-id="924fd-225">Two work IDs should have been created for these lines.</span></span> <span data-ttu-id="924fd-226">Mindkét munkaazonosító számát el kell fogadni.</span><span class="sxs-lookup"><span data-stu-id="924fd-226">The counts for both these work IDs must be accepted.</span></span>

1. <span data-ttu-id="924fd-227">A rácsban válassza ki a *Ciklikus leltározás* munkarendelés-típus első munkaazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="924fd-227">In the grid, select the first work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="924fd-228">A Művelet ablaktábla **Munka** lapjának **Munka** csoportjában válassza a **Ciklikus leltározás** elemet.</span><span class="sxs-lookup"><span data-stu-id="924fd-228">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="924fd-229">Két sor látható, egy-egy a cikkek és az azonosítótábla számára.</span><span class="sxs-lookup"><span data-stu-id="924fd-229">Two lines are shown, one for each item and license plate.</span></span> <span data-ttu-id="924fd-230">A **Megszámlált mennyiség**, a **Hely**, az **Azonosítótábla** és a **Cikk** mező értékeinek meg kell egyezniük a mobileszköz által létrehozott leltárbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="924fd-230">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span> <span data-ttu-id="924fd-231">Ha ezek a mezők nem láthatók, akkor válassza a **Dimenziók megjelenítése** lehetőséget a Művelet panelen a rácshoz való hozzáadásukhoz.</span><span class="sxs-lookup"><span data-stu-id="924fd-231">If any of these fields aren't visible, select **Display dimensions** on the Action Pane to add them to the grid.</span></span>

1. <span data-ttu-id="924fd-232">Válassza ki mindkét sort.</span><span class="sxs-lookup"><span data-stu-id="924fd-232">Select both lines.</span></span>
1. <span data-ttu-id="924fd-233">A Művelet ablaktáblán válassza ki a **Számlálás elfogadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="924fd-233">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="924fd-234">A „Feladás - Napló” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="924fd-234">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="924fd-235">Válassza az **Üzenet részletei** lehetőséget a feladott napló számának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="924fd-235">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="924fd-236">Zárja be az üzenet részleteit.</span><span class="sxs-lookup"><span data-stu-id="924fd-236">Close the message details.</span></span>
1. <span data-ttu-id="924fd-237">Frissítse a **Munka** oldalt.</span><span class="sxs-lookup"><span data-stu-id="924fd-237">Refresh the **Work** page.</span></span>

    <span data-ttu-id="924fd-238">A program lezárta az első munkaazonosítót, és már nem jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="924fd-238">The first work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="924fd-239">Ha meg szeretné tekinteni a lezárt munkát, jelölje be a **Lezárt megjelenítése** jelölőnégyzetet a rács felett.</span><span class="sxs-lookup"><span data-stu-id="924fd-239">To view closed work, select the **Show closed** check box above the grid.</span></span>

    <span data-ttu-id="924fd-240">Ezt követően elfogadja a *01A01R1S2B* helyen található azonosítótáblára vonatkozó munkát.</span><span class="sxs-lookup"><span data-stu-id="924fd-240">You will now accept the work for the license plate in the *01A01R1S2B* location.</span></span>

1. <span data-ttu-id="924fd-241">Az **Áttekintés** lapon válassza ki a *Ciklikus leltározás* munkarendelés-típus második munkaazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="924fd-241">On the **Overview** tab, select the second work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="924fd-242">A Művelet ablaktábla **Munka** lapjának **Munka** csoportjában válassza a **Ciklikus leltározás** elemet.</span><span class="sxs-lookup"><span data-stu-id="924fd-242">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="924fd-243">Egy sor jelenik meg a cikk és az azonosítótábla esetében.</span><span class="sxs-lookup"><span data-stu-id="924fd-243">One line is shown, for the item and license plate.</span></span> <span data-ttu-id="924fd-244">A **Megszámlált mennyiség**, a **Hely**, az **Azonosítótábla** és a **Cikk** mező értékeinek meg kell egyezniük a mobileszköz által létrehozott leltárbejegyzésekkel.</span><span class="sxs-lookup"><span data-stu-id="924fd-244">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span>

1. <span data-ttu-id="924fd-245">Jelölje ki a sort.</span><span class="sxs-lookup"><span data-stu-id="924fd-245">Select the line.</span></span>
1. <span data-ttu-id="924fd-246">A Művelet ablaktáblán válassza ki a **Számlálás elfogadása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="924fd-246">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="924fd-247">A „Feladás - Napló” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="924fd-247">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="924fd-248">Válassza az **Üzenet részletei** lehetőséget a feladott napló számának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="924fd-248">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="924fd-249">Zárja be az üzenet részleteit.</span><span class="sxs-lookup"><span data-stu-id="924fd-249">Close the message details.</span></span>
1. <span data-ttu-id="924fd-250">Frissítse a **Munka** oldalt.</span><span class="sxs-lookup"><span data-stu-id="924fd-250">Refresh the **Work** page.</span></span>

    <span data-ttu-id="924fd-251">A program lezárta a második munkaazonosítót, és már nem jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="924fd-251">The second work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="924fd-252">Ha meg szeretné tekinteni a lezárt munkát, jelölje be a **Lezárt megjelenítése** jelölőnégyzetet a rács felett.</span><span class="sxs-lookup"><span data-stu-id="924fd-252">To view closed work, select the **Show closed** check box above the grid.</span></span>

#### <a name="on-hand-by-location"></a><span data-ttu-id="924fd-253">Aktuális készlet hely szerint</span><span class="sxs-lookup"><span data-stu-id="924fd-253">On-hand by location</span></span>

1. <span data-ttu-id="924fd-254">Nyissa meg a következőt: **Raktárkezelés \> Lekérdezések és jelentések \> Aktuális helyenként**.</span><span class="sxs-lookup"><span data-stu-id="924fd-254">Go to **Warehouse management \> Inquiries and reports \> On-hand by location**.</span></span>
1. <span data-ttu-id="924fd-255">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="924fd-255">Set the following values:</span></span>

    - <span data-ttu-id="924fd-256">**Telephely:** *6*</span><span class="sxs-lookup"><span data-stu-id="924fd-256">**Site:** *6*</span></span>
    - <span data-ttu-id="924fd-257">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="924fd-257">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="924fd-258">**Frissítés helyek között:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="924fd-258">**Refresh across locations:** *Yes*</span></span>

1. <span data-ttu-id="924fd-259">Figyelje meg, hogy a *01A01R1S1B* hely kétféle azonosítótáblával rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="924fd-259">Notice that location *01A01R1S1B* has two license plates:</span></span>

    - <span data-ttu-id="924fd-260">**A0001**, ahol az **LP hely** mező értéke *1.*</span><span class="sxs-lookup"><span data-stu-id="924fd-260">**A0001**, where the **LP Position** field is set to *1*</span></span>
    - <span data-ttu-id="924fd-261">**A0002**, ahol az **LP hely** mező értéke *2.*</span><span class="sxs-lookup"><span data-stu-id="924fd-261">**A0002**, where the **LP Position** field is set to *2*</span></span>

1. <span data-ttu-id="924fd-262">Figyelje meg, hogy a *01A01R1S2B* hely egyféle azonosítótáblával rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="924fd-262">Notice that location *01A01R1S2B* has one license plate:</span></span>

    - <span data-ttu-id="924fd-263">**A0002**, ahol az **LP hely** mező értéke *1.*</span><span class="sxs-lookup"><span data-stu-id="924fd-263">**A0002**, where the **LP Position** field is set to *1*</span></span>

### <a name="sales-order-scenario"></a><span data-ttu-id="924fd-264">Értékesítési rendelés forgatókönyve</span><span class="sxs-lookup"><span data-stu-id="924fd-264">Sales order scenario</span></span>

<span data-ttu-id="924fd-265">Most, hogy a *Helyazonosító tábla elhelyezése* funkció be van állítva, és a készlet már elő van készítve, létre kell hozni egy értékesítési rendelést, amely olyan kitárolási munkákat generál, amelyek a raktári dolgozót az *A0002* cikk készlethelyről való kitárolására utasítják, ahol a raklapazonosító az *1*. helyen található.</span><span class="sxs-lookup"><span data-stu-id="924fd-265">Now that the *Location license plate positioning* feature has been set up, and the inventory has been staged, you must create a sales order to generate picking work that will direct the warehouse worker to pick item *A0002* from the inventory location where the pallet ID is in position *1*.</span></span>

1. <span data-ttu-id="924fd-266">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="924fd-266">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="924fd-267">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="924fd-267">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="924fd-268">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="924fd-268">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="924fd-269">**Vevőkód** *US-004*</span><span class="sxs-lookup"><span data-stu-id="924fd-269">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="924fd-270">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="924fd-270">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="924fd-271">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-271">Select **OK**.</span></span>
1. <span data-ttu-id="924fd-272">A program új sort ad hozzá a rácshoz az **Értékesítési rendelés sorai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="924fd-272">A new line is added to the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="924fd-273">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="924fd-273">On this new line, set the following values:</span></span>

    - <span data-ttu-id="924fd-274">**Cikkszám:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="924fd-274">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="924fd-275">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="924fd-275">**Quantity:** *1*</span></span>

1. <span data-ttu-id="924fd-276">A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.</span><span class="sxs-lookup"><span data-stu-id="924fd-276">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="924fd-277">A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a rendelési sor készletének foglalásához.</span><span class="sxs-lookup"><span data-stu-id="924fd-277">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve inventory for the order line.</span></span>
1. <span data-ttu-id="924fd-278">Zárja be a **Foglalás** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="924fd-278">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="924fd-279">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát.</span><span class="sxs-lookup"><span data-stu-id="924fd-279">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="924fd-280">Olyan tájékoztató üzenet érkezik, amelyek az értékesítési rendeléshez létrehozott hullámazonosítót és szállítási azonosítót jelenítik meg.</span><span class="sxs-lookup"><span data-stu-id="924fd-280">You receive an informational message that indicates the wave ID and shipment ID that were created for the order.</span></span>

1. <span data-ttu-id="924fd-281">Az **Értékesítési rendelés sorai** gyorslap **Raktár** menüjében, a rács felett válassza a **Munka részletes adatai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="924fd-281">On the **Sales order lines** FastTab, on the **Warehouse** menu above the grid, select **Work details**.</span></span>
1. <span data-ttu-id="924fd-282">Megjelenik a **Munka** oldal, és az értékesítési sorhoz létrehozott munkát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="924fd-282">The **Work** page appears and shows the work that was created for the sales line.</span></span> <span data-ttu-id="924fd-283">Jegyezze fel a megjelenített munkaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="924fd-283">Make a note of the work ID that is shown.</span></span>

### <a name="sales-picking-scenario"></a><span data-ttu-id="924fd-284">Értékesítési kitárolási eset</span><span class="sxs-lookup"><span data-stu-id="924fd-284">Sales picking scenario</span></span>

1. <span data-ttu-id="924fd-285">Nyissa meg a mobilalkalmazást, és jelentkezzen be a *61*-es raktárba.</span><span class="sxs-lookup"><span data-stu-id="924fd-285">Open the mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="924fd-286">Lépjen a **Kimenő \> Értékesítési kitárolás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="924fd-286">Go to **Outbound \> Sales picking**.</span></span>
1. <span data-ttu-id="924fd-287">A **Munkaazonosító/azonosítótábla azonosítójának beolvasása** oldalon válassza ki az **Azonosító** mezőt, majd adja meg az értékesítési sor munkaazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="924fd-287">On the **Scan a work ID / license plate ID** page, select the **ID** field, and then enter the work ID from the sales line.</span></span>
1. <span data-ttu-id="924fd-288">Figyelje meg, hogy a kitárolási munka az *A0002* cikknek a *01A01R1S2B* helyről való kitárolására utasítja.</span><span class="sxs-lookup"><span data-stu-id="924fd-288">Notice that the picking work directs you to pick item *A0002* from location *01A01R1S2B*.</span></span> <span data-ttu-id="924fd-289">Ez az utasítás akkor jelenik meg, ha az *A0002* cikk olyan azonosítótáblán van, amely az adott helyen az *1*. pozícióban szerepel.</span><span class="sxs-lookup"><span data-stu-id="924fd-289">You receive this instruction because item *A0002* is on a license plate that is in position *1* in that location.</span></span>

    <span data-ttu-id="924fd-290">![1. pozíció helye](media/LocationLicensePlatePositioning.png "1. pozíció helye")</span><span class="sxs-lookup"><span data-stu-id="924fd-290">![Position 1 location](media/LocationLicensePlatePositioning.png "Position 1 location")</span></span>

1. <span data-ttu-id="924fd-291">Adja meg a helyhez létrehozott azonosítótábla-azonosítót, majd kövesse a figyelmeztetéseket az értékesítési rendelés kitárolásához.</span><span class="sxs-lookup"><span data-stu-id="924fd-291">Enter the license plate ID that you created for the location, and then follow the prompts to pick the sales order.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]