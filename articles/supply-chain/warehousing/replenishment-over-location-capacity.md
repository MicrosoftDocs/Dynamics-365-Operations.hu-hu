---
title: Feltöltés a hely kapacitása alapján
description: Ez a témakör a hely kapacitásainak feltöltésével kapcsolatban tartalmaz tájékoztatást. Ez a funkció lehetővé tesz minden olyan feltöltési munkát, amely a nap létrehozásához szükséges, illetve a feltöltési munka elérhetőségét kezeli annak érdekében, hogy a kitárolási hely ne fogyjon ki a készletből, és ne haladja meg a kapacitást sem.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 8e9ae16fea892d1d6b6a6b5d06137576623e7f5b
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429908"
---
# <a name="replenishment-over-location-capacity"></a><span data-ttu-id="c1529-104">Feltöltés a hely kapacitása alapján</span><span class="sxs-lookup"><span data-stu-id="c1529-104">Replenishment over location capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1529-105">Néhány nagy vagy korlátozott hellyel rendelkező raktárnak egy adott cikkből nagyobb mennyiséget kell szállítania, mint amennyi a kitárolási helyen el fog férni.</span><span class="sxs-lookup"><span data-stu-id="c1529-105">Some high-volume or space-constrained warehouses must ship more quantity of an item in a day than will fit in the picking location.</span></span> <span data-ttu-id="c1529-106">A *Feltöltés a hely kapacitása alapján* funkció lehetővé tesz minden olyan feltöltési munkát, amely a nap létrehozásához szükséges, illetve a feltöltési munka elérhetőségét kezeli annak érdekében, hogy a kitárolási hely ne fogyjon ki a készletből, és ne haladja meg a kapacitást sem.</span><span class="sxs-lookup"><span data-stu-id="c1529-106">The *Replenishment over location capacity* feature enables all replenishment work that will be required for the day to be created and manages availability of that replenishment work to ensure that the picking location neither runs out of inventory nor goes above capacity.</span></span>

<span data-ttu-id="c1529-107">Ez a funkció több feltöltési munka létrehozását teszi lehetővé, mint amennyi egy helyen elfér, és a hely megtelése esetén blokkolja a feltöltési munka befejezését.</span><span class="sxs-lookup"><span data-stu-id="c1529-107">The feature enables more replenishment work to be created than will fit in a location, and it blocks replenishment work from being completed when the location is full.</span></span> <span data-ttu-id="c1529-108">Mivel a kitárolási helyen lévő készlet egy konfigurálható küszöbérték alá esik, több feltöltési munka is elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="c1529-108">As inventory in the picking location drops below a configurable threshold, more replenishment work is made available.</span></span>

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a><span data-ttu-id="c1529-109">Kapcsolja be a Feltöltés a hely kapacitása alapján funkciót</span><span class="sxs-lookup"><span data-stu-id="c1529-109">Turn on the Replenishment over location capacity feature</span></span>

<span data-ttu-id="c1529-110">A funkció elérhetővé tétele érdekében kapcsolja be a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) modulban a következő szolgáltatásokat (ebben a sorrendben):</span><span class="sxs-lookup"><span data-stu-id="c1529-110">To make this feature available, turn on the following features in [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in this order):</span></span>

1. <span data-ttu-id="c1529-111">Szervezeti szintű munkazárolás</span><span class="sxs-lookup"><span data-stu-id="c1529-111">Organization-wide work blocking</span></span>
1. <span data-ttu-id="c1529-112">Feltöltés a hely kapacitása alapján</span><span class="sxs-lookup"><span data-stu-id="c1529-112">Replenishment over location capacity</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="c1529-113">A funkció beállítása a példaforgatókönyvhöz</span><span class="sxs-lookup"><span data-stu-id="c1529-113">Set up the feature for the example scenario</span></span>

<span data-ttu-id="c1529-114">Ez a szakasz iránymutatásokat és egy példát mutat be azzal kapcsolatban, hogy hogyan kell beállítani ezt a funkciót, illetve hogyan kell előkészíteni mintaadatokat a témakörben később bemutatott példaforgatókönyvben.</span><span class="sxs-lookup"><span data-stu-id="c1529-114">This section provides guidelines and an example that shows how to set up this feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="enable-sample-data"></a><span data-ttu-id="c1529-115">Mintaadatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c1529-115">Enable sample data</span></span>

<span data-ttu-id="c1529-116">Ha ezt a [példaforgatókönyvet](#example-scenario) az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="c1529-116">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="c1529-117">Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="c1529-117">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="location-profile"></a><span data-ttu-id="c1529-118">Helyprofil</span><span class="sxs-lookup"><span data-stu-id="c1529-118">Location profile</span></span>

<span data-ttu-id="c1529-119">A Feltöltés a kapacitás szerint funkció engedélyezése a hely profilja alapján.</span><span class="sxs-lookup"><span data-stu-id="c1529-119">Enable the replenish over capacity functionality on the location profile.</span></span>

1. <span data-ttu-id="c1529-120">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyek profiljai** pontra.</span><span class="sxs-lookup"><span data-stu-id="c1529-120">Go to **Warehouse management \> Setup \> Warehouse \> Locations profiles**.</span></span>
1. <span data-ttu-id="c1529-121">A bal oldali ablaktáblában válassza ki a **PICK-06** elemet.</span><span class="sxs-lookup"><span data-stu-id="c1529-121">In the left pane, select **PICK-06**.</span></span>
1. <span data-ttu-id="c1529-122">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-122">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="c1529-123">A **Feltöltés** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c1529-123">On the **Replenishment** FastTab, set the following values:</span></span>

    - <span data-ttu-id="c1529-124">**Hely kapacitásának meghaladása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="c1529-124">**Exceed Location Capacity:** *Yes*</span></span>

        <span data-ttu-id="c1529-125">Ha engedélyezve van, a hely maximális kapacitását túllépheti a feltöltési munka.</span><span class="sxs-lookup"><span data-stu-id="c1529-125">When enabled, the maximum capacity of the location will be allowed to be exceeded by replenishment work.</span></span> <span data-ttu-id="c1529-126">Ez a **Feltöltés** gyorslap egyéb mezőit is engedélyezi.</span><span class="sxs-lookup"><span data-stu-id="c1529-126">This also enables other fields on the **Replenishment** FastTab.</span></span>

    - <span data-ttu-id="c1529-127">**Munka elérhetőségi küszöbértékének típusa:** *Mennyiség*</span><span class="sxs-lookup"><span data-stu-id="c1529-127">**Work availability threshold type:** *Quantity*</span></span>

        <span data-ttu-id="c1529-128">Ez a mező azt a módszert határozza meg, amellyel meghatározható, hogy mikor kell több munkát felszabadítani.</span><span class="sxs-lookup"><span data-stu-id="c1529-128">This field defines the method that is used to determine when more work should be released.</span></span> <span data-ttu-id="c1529-129">A kiadást végezheti százalék, összeg vagy mennyiség szerint is:</span><span class="sxs-lookup"><span data-stu-id="c1529-129">You can release by either quantity or a percentage:</span></span>

        - <span data-ttu-id="c1529-130">*Százalék* – Akkor válassza ezt a lehetőséget, ha a rakodási korlátozásokon vagy a térfogatmérésen alapuló százalékos kapacitást kívánja használni.</span><span class="sxs-lookup"><span data-stu-id="c1529-130">*Percent* – Select this option to use percentage capacity that is based on stocking limits or volumetrics.</span></span> <span data-ttu-id="c1529-131">Ha ezt a lehetőséget választja, akkor engedélyezi a **Túlcsordulási százalék** mezőt, és letiltja a két mennyiséggel kapcsolatos mezőt, a **Túlcsordulási mennyiséget** és a **Túlcsordulási egység** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-131">Selecting this option enables the **Overflow percentage** field, and disables the two quantity related fields,  **Overflow quantity** and **Overflow unit**.</span></span>

            <span data-ttu-id="c1529-132">Ezt a lehetőséget akkor használja, ha a kitárolási helyek térfogatmérést használnak.</span><span class="sxs-lookup"><span data-stu-id="c1529-132">You can use this option if the picking locations use volumetrics.</span></span>

            <span data-ttu-id="c1529-133">Ha ez a beállítás be van jelölve, akkor állítsa a **Túlcsordulási százalék** mezőt arra a százalékos értékre, amelyen több feltöltési munka is rendelkezésre fog állni.</span><span class="sxs-lookup"><span data-stu-id="c1529-133">If this option is selected, set the **Overflow percentage** field to the percentage at which more replenishment work will be made available.</span></span>

        - <span data-ttu-id="c1529-134">*Mennyiség* – Akkor válassza ezt a lehetőséget, ha az adott mennyiségi értéket kívánja használni.</span><span class="sxs-lookup"><span data-stu-id="c1529-134">*Quantity* – Select this option to use a specific quantity value.</span></span> <span data-ttu-id="c1529-135">Ha ezt a lehetőséget választja, akkor letiltja a **Túlcsordulási százalék** mezőt, és engedélyezi a **Túlcsordulási mennyiséget** és a **Túlcsordulási egység** mezőket.</span><span class="sxs-lookup"><span data-stu-id="c1529-135">Selecting this option disables the **Overflow percentage** field and enables **Overflow quantity** and **Overflow unit** fields.</span></span>

            <span data-ttu-id="c1529-136">Akkor használja ezt a beállítást, ha nem használ térfogatmérést a feltöltés alatt álló helyekhez, vagy ha olyan konzisztens mennyiségekkel rendelkezik, amelyekből több készletet szeretne a helyre vinni.</span><span class="sxs-lookup"><span data-stu-id="c1529-136">Use this option when you aren't using volumetrics for the locations that are being replenished, or when you have consistent quantities at which you want more inventory to be brought to the location.</span></span>

           <span data-ttu-id="c1529-137">Ha ez a beállítás be van jelölve, akkor állítsa a **Túlcsordulási mennyiség** és a **Túlcsordulási egység** mezőket annak a mennyiségnek és egységnek az értékére, amelyen több feltöltési munka fog rendelkezésre állni.</span><span class="sxs-lookup"><span data-stu-id="c1529-137">If this option is selected, set the **Overflow quantity** and **Overflow unit** fields to the quantity and unit at which more replenishment work will be made available.</span></span>

    - <span data-ttu-id="c1529-138">**Túlcsordulási mennyiség:** *0,65*</span><span class="sxs-lookup"><span data-stu-id="c1529-138">**Overflow quantity:** *0.65*</span></span>

        <span data-ttu-id="c1529-139">Ez a mező határozza meg a hely túlcsordulásának mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="c1529-139">This field defines the quantity at which the location overflows.</span></span>

        <span data-ttu-id="c1529-140">A munka rendelkezésre áll bármikor, amikor a hely aktuális mennyiségének összeg és munkamennyisége ez alatt az érték alatt van.</span><span class="sxs-lookup"><span data-stu-id="c1529-140">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this value.</span></span> <span data-ttu-id="c1529-141">A feltöltési munka azon része, amely meghaladja ezt az értéket, zárolva lesz, és manuálisan kell feloldani.</span><span class="sxs-lookup"><span data-stu-id="c1529-141">Any replenishment work above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="c1529-142">A hely rakodási korlátait a munkamennyiség számításakor kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="c1529-142">Location stocking limits are considered when the work quantity is calculated.</span></span>

    - <span data-ttu-id="c1529-143">**Túlcsordulási egység:** *PL*</span><span class="sxs-lookup"><span data-stu-id="c1529-143">**Overflow unit:** *PL*</span></span>

        <span data-ttu-id="c1529-144">Ez a mező azt a egységet határozza meg, amely a túlcsordulási mennyiséghez van társítva.</span><span class="sxs-lookup"><span data-stu-id="c1529-144">This field defines the unit that is associated with the overflow quantity.</span></span>

        <span data-ttu-id="c1529-145">Ebben az esetben több feltöltési munka lesz elérhető, ha a hely eléri a 0,65 raklapot (PL).</span><span class="sxs-lookup"><span data-stu-id="c1529-145">In this case, more replenishment work will be made available when the location gets down to 0.65 pallet (PL).</span></span>

    - <span data-ttu-id="c1529-146">**Túlcsordulási százalék**</span><span class="sxs-lookup"><span data-stu-id="c1529-146">**Overflow percentage**</span></span>

        <span data-ttu-id="c1529-147">Ez a mező határozza meg a hely túlcsordulásának százalékát.</span><span class="sxs-lookup"><span data-stu-id="c1529-147">This field defines the percentage at which the location overflows.</span></span>

        <span data-ttu-id="c1529-148">A munka rendelkezésre áll bármikor, amikor a hely aktuális mennyiségének összeg és munkamennyisége ez alatt a százalék alatt van.</span><span class="sxs-lookup"><span data-stu-id="c1529-148">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this percentage.</span></span> <span data-ttu-id="c1529-149">A feltöltési munka azon százaléka, amely meghaladja ezt az értéket, zárolva lesz, és manuálisan kell feloldani.</span><span class="sxs-lookup"><span data-stu-id="c1529-149">Any replenishment work quantity percentage above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="c1529-150">A hely rakodási korlátait a munkamennyiség százalékának számításakor kell figyelembe venni.</span><span class="sxs-lookup"><span data-stu-id="c1529-150">Location stocking limits are considered when the work quantity percentage is calculated.</span></span> <span data-ttu-id="c1529-151">Ha nincsenek meghatározva a hely készletezési korlátai, akkor a munkamennyiség százalékos értékét a program a mennyiség alapján határozza meg, ha mennyiségi megszorítások vannak meghatározva a hely profilján.</span><span class="sxs-lookup"><span data-stu-id="c1529-151">If no location stocking limits are defined, the work quantity percentage is calculated by volume if volume constraints are defined for the location profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1529-152">Ha az **USMF** jogi személy bemutatóadatait használja, és korábban bekapcsolta a *Hely és azonosítótábla pozicionálása* funkciót, akkor ki kell kapcsolni az **Azonosítótábla pozicionálásának engedélyezésebeállítást** a **BULK-06** hely profiljánál, hogy a példaforgatókönyvben használt mobillépéseket végre tudja hajtani.</span><span class="sxs-lookup"><span data-stu-id="c1529-152">If you're using the demo data for the **USMF** legal entity and previously turned on the *Location license plate positioning* feature, you must turn off the **Enable license plate positioning** setting for the **BULK-06** location profile to complete the mobile steps in the example scenario.</span></span>

### <a name="wave-step-code"></a><span data-ttu-id="c1529-153">Hullámlépés kódja</span><span class="sxs-lookup"><span data-stu-id="c1529-153">Wave step code</span></span>

> [!NOTE]
> <span data-ttu-id="c1529-154">Ha az itt leírtak szerint szeretné beállítani a hullámlépés kódját, akkor először a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőséget kell használnia a *Szervezeti szintű hullámlépéskód* nevű funkció bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="c1529-154">To set up a wave step code as described here, you might first have to use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named *Organization wide wave step code*.</span></span>

1. <span data-ttu-id="c1529-155">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámlépéskódok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c1529-155">Go to **Warehouse Management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="c1529-156">Válassza az **Új** lehetőséget, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c1529-156">Select **New**, and set the following values:</span></span>

    - <span data-ttu-id="c1529-157">**Hullámlépés kódja:** *Feltöltés*</span><span class="sxs-lookup"><span data-stu-id="c1529-157">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="c1529-158">**Hullámlépés leírása:** *Feltöltés*</span><span class="sxs-lookup"><span data-stu-id="c1529-158">**Wave step description:** *Replenishment*</span></span>
    - <span data-ttu-id="c1529-159">**Hullámlépés típusa:** *Feltöltés*</span><span class="sxs-lookup"><span data-stu-id="c1529-159">**Wave step type:** *Replenishment*</span></span>

1. <span data-ttu-id="c1529-160">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-160">Select **Save**.</span></span>

### <a name="replenishment-template"></a><span data-ttu-id="c1529-161">Feltöltési sablon</span><span class="sxs-lookup"><span data-stu-id="c1529-161">Replenishment template</span></span>

<span data-ttu-id="c1529-162">A feltöltési sablonokat olyan szabályok alkotják, amelyek megszabják, mikor és hogyan töltik fel a helyet.</span><span class="sxs-lookup"><span data-stu-id="c1529-162">Replenishment templates are a set of rules that control when and how a location is replenished.</span></span>

1. <span data-ttu-id="c1529-163">Ugorjon a **Raktárkezelés \> Beállítás \> Feltöltés \> Feltöltési sablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c1529-163">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="c1529-164">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-164">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="c1529-165">Az **Áttekintés** szakaszban válassza ki azt a sort, amelyben a **Feltöltési sablon** mező *Igény feltöltése* lehetőségként van beállítva.</span><span class="sxs-lookup"><span data-stu-id="c1529-165">In the **Overview** section, select the line where the **Replenish template** field is set to *Demand replenish*.</span></span>
1. <span data-ttu-id="c1529-166">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="c1529-166">Set the following values:</span></span>

    - <span data-ttu-id="c1529-167">**Hullámlépés kódja:** *Feltöltés*</span><span class="sxs-lookup"><span data-stu-id="c1529-167">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="c1529-168">**A hullám keresletének engedélyezése nem foglalt mennyiségek használatához:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="c1529-168">**Allow wave demand to use unreserved quantities:** *Yes*</span></span>

1. <span data-ttu-id="c1529-169">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-169">Select **Save**.</span></span>

### <a name="wave-template"></a><span data-ttu-id="c1529-170">Hullámsablon</span><span class="sxs-lookup"><span data-stu-id="c1529-170">Wave template</span></span>

1. <span data-ttu-id="c1529-171">Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c1529-171">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="c1529-172">A bal oldali ablaktáblában állítsa a **Hullámsablon típusa** mezőt a *Szállítás* értékre.</span><span class="sxs-lookup"><span data-stu-id="c1529-172">In the left pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="c1529-173">Válassza ki a sablont a **61 Szállítás** listából.</span><span class="sxs-lookup"><span data-stu-id="c1529-173">Select template **61 Shipping** in the list.</span></span>
1. <span data-ttu-id="c1529-174">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-174">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="c1529-175">Adja meg az **Általános** gyorslap **Feltöltési munka kiadásának automatizálása** beállítását *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="c1529-175">On the **General** FastTab, set the **Automate replenishment work release** option to *Yes*.</span></span>

    <span data-ttu-id="c1529-176">Állítsa ezt a lehetőséget *Igen* értékre, hogy a rendszer automatiksuan létrehozza és kiadja az igényalapú feltöltési munkát.</span><span class="sxs-lookup"><span data-stu-id="c1529-176">Set this option to *Yes* to create demand-based replenishment work and release it automatically.</span></span> <span data-ttu-id="c1529-177">Hozzá kell adnia az újratöltési hullámmódszert a hullámsablonhoz, majd létrehozni egy **Hullámigény** típusú újratöltési sablont.</span><span class="sxs-lookup"><span data-stu-id="c1529-177">You must add the replenishment wave method to the wave template and create a replenishment template of the **Wave demand** type.</span></span> <span data-ttu-id="c1529-178">**Feltöltési sablonok** lapjának feltöltési sablon beállítása.</span><span class="sxs-lookup"><span data-stu-id="c1529-178">Set up a replenishment template on the **Replenishment templates** page.</span></span> <span data-ttu-id="c1529-179">A feltöltési sablon beállításához a feltöltési módszert hozzá kell adnia a hullámsablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c1529-179">To set up a replenishment template, you must add the replenish method to the wave template.</span></span>

1. <span data-ttu-id="c1529-180">A **Módok** gyorslapon, a **Kiválasztott módok** oszlopban keresse meg a következő sort:</span><span class="sxs-lookup"><span data-stu-id="c1529-180">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="c1529-181">**Mód neve:** *Feltöltés*</span><span class="sxs-lookup"><span data-stu-id="c1529-181">**Method name:** *replenish*</span></span>
    - <span data-ttu-id="c1529-182">**Név:** *Feltöltés*</span><span class="sxs-lookup"><span data-stu-id="c1529-182">**Name:** *Replenishment*</span></span>

1. <span data-ttu-id="c1529-183">Ehhez a sorhoz állítsa a **Hullámlépés kód** mezőt a *Feltöltés* lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1529-183">Set the **Wave step code** field for this line to *Replen*.</span></span>
1. <span data-ttu-id="c1529-184">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-184">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="c1529-185">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="c1529-185">Example scenario</span></span>

<span data-ttu-id="c1529-186">Miután elvégezte az összes korábban leírt mintaadatok elérhetővé tételét és beállítását, a forgatókönyvön keresztül kipróbálhatja a *Feltöltés a hely kapacitása alapján* funkciót.</span><span class="sxs-lookup"><span data-stu-id="c1529-186">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Replenishment over location capacity* feature.</span></span> <span data-ttu-id="c1529-187">Az ebben a forgatókönyvben látható értékek feltételezik, hogy azokkal a szokásos bemutatóadatokkal dolgozik, amelyeket az **USMF** jogi személyt kiválasztott, és hogy előkészítette a témakör korábbi részében ismertetett mintarekordokat.</span><span class="sxs-lookup"><span data-stu-id="c1529-187">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="c1529-188">Ez a forgatókönyv példaként is szolgál, amely megmutatja, hogyan használható a funkció az üzemelési beállításban.</span><span class="sxs-lookup"><span data-stu-id="c1529-188">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-replenishment-work"></a><span data-ttu-id="c1529-189">Feltöltési munka létrehozása</span><span class="sxs-lookup"><span data-stu-id="c1529-189">Create replenishment work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="c1529-190">1. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c1529-190">Create sales order 1</span></span>

1. <span data-ttu-id="c1529-191">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c1529-191">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="c1529-192">A műveleti ablaktáblán kattintson az **Új** gombra az új értékesítési rendelés létrehozása párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c1529-192">On the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="c1529-193">A párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c1529-193">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="c1529-194">**Vevőkód** *US-007*</span><span class="sxs-lookup"><span data-stu-id="c1529-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="c1529-195">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="c1529-195">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="c1529-196">Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="c1529-196">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="c1529-197">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="c1529-197">The new sales order is opened.</span></span> <span data-ttu-id="c1529-198">Tartalmaz egy új, üres sort az **Értékesítési rendelés sorai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="c1529-198">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="c1529-199">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c1529-199">On this line, set the following values:</span></span>

    - <span data-ttu-id="c1529-200">**Cikkszám:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="c1529-200">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="c1529-201">**Mennyiség:** *40*</span><span class="sxs-lookup"><span data-stu-id="c1529-201">**Quantity:** *40*</span></span>

1. <span data-ttu-id="c1529-202">Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-202">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="c1529-203">A **Foglalás** lapon válassza ki az **Adag foglalása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c1529-203">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="c1529-204">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c1529-204">Close the page.</span></span>
1. <span data-ttu-id="c1529-205">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-205">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c1529-206">Olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítókat és szállítási azonosítókat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c1529-206">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="c1529-207">Egy feltöltési hullám is létrejön.</span><span class="sxs-lookup"><span data-stu-id="c1529-207">A replenishment wave is also created.</span></span>

    <span data-ttu-id="c1529-208">Figyelmeztető üzenet jelenik meg, amely jelzi, hogy a(z) „XXXX munkaazonosító nem zárolható, mert befejezetlen feltöltési munkával rendelkezik".</span><span class="sxs-lookup"><span data-stu-id="c1529-208">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="c1529-209">2. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c1529-209">Create sales order 2</span></span>

1. <span data-ttu-id="c1529-210">Az **Összes értékesítési rendelés** oldalon, a műveleti ablaktáblán kattintson az **Új** gombra az új értékesítési rendelés létrehozása párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c1529-210">On the **All sales orders**, page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="c1529-211">A párbeszédpanelen adja meg a következő értéket:</span><span class="sxs-lookup"><span data-stu-id="c1529-211">In the dialog box, set the following value:</span></span>

    - <span data-ttu-id="c1529-212">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c1529-212">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c1529-213">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="c1529-213">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="c1529-214">Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="c1529-214">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="c1529-215">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="c1529-215">The new sales order is opened.</span></span> <span data-ttu-id="c1529-216">Tartalmaz egy új, üres sort az **Értékesítési rendelés sorai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="c1529-216">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="c1529-217">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c1529-217">On this line, set the following values:</span></span>

    - <span data-ttu-id="c1529-218">**Cikkszám:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="c1529-218">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="c1529-219">**Mennyiség:** *60*</span><span class="sxs-lookup"><span data-stu-id="c1529-219">**Quantity:** *60*</span></span>

1. <span data-ttu-id="c1529-220">Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-220">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="c1529-221">A **Foglalás** lapon válassza ki az **Adag foglalása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c1529-221">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="c1529-222">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c1529-222">Close the page.</span></span>
1. <span data-ttu-id="c1529-223">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-223">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c1529-224">Olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítókat és szállítási azonosítókat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c1529-224">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="c1529-225">Egy feltöltési hullám is létrejön.</span><span class="sxs-lookup"><span data-stu-id="c1529-225">A replenishment wave is also created.</span></span>

    <span data-ttu-id="c1529-226">Figyelmeztető üzenet jelenik meg, amely jelzi, hogy a(z) „XXXX munkaazonosító nem zárolható, mert befejezetlen feltöltési munkával rendelkezik".</span><span class="sxs-lookup"><span data-stu-id="c1529-226">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="c1529-227">3. értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c1529-227">Create sales order 3</span></span>

1. <span data-ttu-id="c1529-228">Az **Összes értékesítési rendelés** oldalon, a műveleti ablaktáblán kattintson az **Új** gombra az új értékesítési rendelés létrehozása párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="c1529-228">On the **All sales orders** page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="c1529-229">A párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c1529-229">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="c1529-230">**Vevőkód** *US-004*</span><span class="sxs-lookup"><span data-stu-id="c1529-230">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="c1529-231">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="c1529-231">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="c1529-232">Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="c1529-232">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="c1529-233">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="c1529-233">The new sales order is opened.</span></span> <span data-ttu-id="c1529-234">Tartalmaz egy új, üres sort az **Értékesítési rendelés sorai** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="c1529-234">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="c1529-235">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c1529-235">On this line, set the following values:</span></span>

    - <span data-ttu-id="c1529-236">**Cikkszám:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="c1529-236">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="c1529-237">**Mennyiség:** *30*</span><span class="sxs-lookup"><span data-stu-id="c1529-237">**Quantity:** *30*</span></span>

1. <span data-ttu-id="c1529-238">Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-238">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="c1529-239">A **Foglalás** lapon válassza ki az **Adag foglalása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c1529-239">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="c1529-240">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c1529-240">Close the page.</span></span>
1. <span data-ttu-id="c1529-241">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-241">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c1529-242">Olyan tájékoztató üzenetek érkeznek, amelyek az adott kiadásból létrehozott hullámazonosítókat és szállítási azonosítókat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c1529-242">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="c1529-243">Egy feltöltési hullám is létrejön.</span><span class="sxs-lookup"><span data-stu-id="c1529-243">A replenishment wave is also created.</span></span>

    <span data-ttu-id="c1529-244">Figyelmeztető üzenet jelenik meg, amely jelzi, hogy a(z) „XXXX munkaazonosító nem zárolható, mert befejezetlen feltöltési munkával rendelkezik".</span><span class="sxs-lookup"><span data-stu-id="c1529-244">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="view-work-details"></a><span data-ttu-id="c1529-245">Munka részletes adatainak megtekintése</span><span class="sxs-lookup"><span data-stu-id="c1529-245">View work details</span></span>

1. <span data-ttu-id="c1529-246">Ugorjon a **Raktárkezelés \> Munka \> Munka részletei** pontra.</span><span class="sxs-lookup"><span data-stu-id="c1529-246">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="c1529-247">Az **Áttekintés** szakaszban szűrje a **Raktár** oszlopot a *61*-es raktár kereséséhez.</span><span class="sxs-lookup"><span data-stu-id="c1529-247">In the **Overview** section, filter the **Warehouse** column for warehouse *61*.</span></span>
1. <span data-ttu-id="c1529-248">Ekkor látnia kell, hogy a három igény értékesítési rendeléshez hét munkaazonosító jött létre.</span><span class="sxs-lookup"><span data-stu-id="c1529-248">You should see that seven work IDs were created for the three demand sales orders.</span></span>

    - <span data-ttu-id="c1529-249">A hét munkaazonosító közül háromnak van *Feltöltés* értékű **Munkarendelés típus** lehetősége, négynek pedig *Munkarendelés* értékű **Munkarendelés típus** értéke.</span><span class="sxs-lookup"><span data-stu-id="c1529-249">Three of the seven work IDs have a **Work order type** value of *Replenishment*, and four have a **Work order type** value of *Sales orders*.</span></span>
    - <span data-ttu-id="c1529-250">Mind a három munkaazonosító, amelynek *Feltöltés* értékű a **Munkarendelés típus** lehetősége, ugyanazzal a *Kitárolás* és *Eltárolás* helyekkel rendelkeznek a **Sorok** szakaszban:</span><span class="sxs-lookup"><span data-stu-id="c1529-250">All three work IDs that have a **Work order type** value of *Replenishment* have the same *Pick* and *Put* locations in the **Lines** section:</span></span>

        - <span data-ttu-id="c1529-251">**Kitárolás:** *02A01R5S1B*</span><span class="sxs-lookup"><span data-stu-id="c1529-251">**Pick:** *02A01R5S1B*</span></span>
        - <span data-ttu-id="c1529-252">**Eltárolás:** *06A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="c1529-252">**Put:** *06A01R2S1B*</span></span>

    - <span data-ttu-id="c1529-253">Az 1. értékesítési rendeléshez két munkaazonosító jött létre.</span><span class="sxs-lookup"><span data-stu-id="c1529-253">Two work IDs were created for sales order 1.</span></span>

1. <span data-ttu-id="c1529-254">Jegyezze fel az értékesítési rendelések munkaazonosítóit.</span><span class="sxs-lookup"><span data-stu-id="c1529-254">Make a note of the work IDs for the sales orders.</span></span>

<span data-ttu-id="c1529-255">A készleten lévő mennyiségtől függően a létrehozott munkamennyiségek kis mértékben különbözhetnek.</span><span class="sxs-lookup"><span data-stu-id="c1529-255">Depending on your on-hand quantities, the work quantities that are created might vary slightly.</span></span> <span data-ttu-id="c1529-256">Összességében azonban a létrehozott munkafejléceknek meg kell egyezniük ennek a forgatókönyvnek a példájával.</span><span class="sxs-lookup"><span data-stu-id="c1529-256">However, overall, the work headers that are created should match this scenario example.</span></span>

#### <a name="on-hand-inventory-license-plate-id"></a><span data-ttu-id="c1529-257">Aktuális készlet-azonosítótábla azonosítója</span><span class="sxs-lookup"><span data-stu-id="c1529-257">On-hand inventory license plate ID</span></span>

<span data-ttu-id="c1529-258">Később ebben a forgatókönyvben a raktári alkalmazást (vagy egy emulátort) fog használni, ahol be kell azonosítania az azonosítótáblát, hogy befejezhesse a kitárolási és feltöltési forgatókönyveket.</span><span class="sxs-lookup"><span data-stu-id="c1529-258">Later in this scenario, you will use the warehouse app (or an emulator), where you must identify the license plate to complete the picking and replenishment scenarios.</span></span>

<span data-ttu-id="c1529-259">A későbbiekben szükséges azonosítótábla-azonosítók megtalálásához, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c1529-259">To find the license plate IDs that you will need later, follow these steps.</span></span>

1. <span data-ttu-id="c1529-260">Menjen a **Készletkezelés \> Lekérdezések és jelentések \> Aktuális készletlista** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1529-260">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="c1529-261">A szűrő ablaktábla megnyitásához válassza ki a **Szűrők megjelenítése** gombot.</span><span class="sxs-lookup"><span data-stu-id="c1529-261">Select the **Show filters** button to open the filter pane.</span></span>
1. <span data-ttu-id="c1529-262">Adja meg az alábbi szűrési kritériumot a forgatókönyvhöz tartozó azonosítótábla beolvasásához.</span><span class="sxs-lookup"><span data-stu-id="c1529-262">Enter the following filtering criteria to get the license plates for the scenario.</span></span> <span data-ttu-id="c1529-263">Használja az *így kezdődik* szűrőt.</span><span class="sxs-lookup"><span data-stu-id="c1529-263">Use the *begins with* filter.</span></span>

    - <span data-ttu-id="c1529-264">**Cikkszám:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="c1529-264">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="c1529-265">**Raktár:** *61*</span><span class="sxs-lookup"><span data-stu-id="c1529-265">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="c1529-266">Válassza az **Alkalmazás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-266">Select **Apply**.</span></span>
1. <span data-ttu-id="c1529-267">A Műveleti ablaktáblán válassza a **Dimenziók** elemet.</span><span class="sxs-lookup"><span data-stu-id="c1529-267">On the Action Pane, select **Dimensions**.</span></span>
1. <span data-ttu-id="c1529-268">A **Dimenziók megjelenítése** párbeszédpanel **Tárolási dimenziók** szakaszában válassza ki az összes értéket.</span><span class="sxs-lookup"><span data-stu-id="c1529-268">In the **Dimensions display** dialog box, in the **Storage Dimensions** section, select all the values.</span></span>
1. <span data-ttu-id="c1529-269">A **Tranzakciók** szakaszban válassza ki a **Cikkszám** és a **Mennyiség \<\> 0** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-269">In the **Transactions** section, select **Item number** and **Quantity \<\> 0**.</span></span>
1. <span data-ttu-id="c1529-270">Ha befejezte a munkát, az **OK** gombra kattintva zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c1529-270">When you've finished, select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="c1529-271">Az **Aktuális** rács megjeleníti a *T0100* cikk egyes helyekhez tartozó azonosítótábla számait.</span><span class="sxs-lookup"><span data-stu-id="c1529-271">The **On-hand** grid shows the license plate numbers for item *T0100* in each location.</span></span> <span data-ttu-id="c1529-272">Jegyezze fel az egyes helyeken található azonosítótáblákat, mivel később szüksége lesz ezekre az információkra.</span><span class="sxs-lookup"><span data-stu-id="c1529-272">Make a note of the license plate that is in each location, because you will need this information later.</span></span>
1. <span data-ttu-id="c1529-273">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c1529-273">Close the page.</span></span>

### <a name="process-steps"></a><span data-ttu-id="c1529-274">Folyamat lépései</span><span class="sxs-lookup"><span data-stu-id="c1529-274">Process steps</span></span>

<span data-ttu-id="c1529-275">A raktárhely feltöltését az első két munkaazonosítónál fogja végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="c1529-275">You will perform the warehouse location replenishment for the first two work IDs.</span></span> <span data-ttu-id="c1529-276">A harmadik feltöltési munka során végzett munka mindaddig le lesz tiltva, amíg a kitárolási hely készletszintje nem éri el a küszöbértéket.</span><span class="sxs-lookup"><span data-stu-id="c1529-276">Work on the third replenishment work will be blocked until the inventory level in the picking location falls below the threshold.</span></span>

#### <a name="replenishment"></a><span data-ttu-id="c1529-277">Feltöltés</span><span class="sxs-lookup"><span data-stu-id="c1529-277">Replenishment</span></span>

1. <span data-ttu-id="c1529-278">Jelentkezzen be az *61*-es raktárban lévő felhasználóként a raktár alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="c1529-278">Sign in to the warehouse app as a user in warehouse *61*.</span></span> <span data-ttu-id="c1529-279">(Írja be a felhasználói azonosítóhoz a *61*-et, a jelszóhoz pedig az *1*-et.)</span><span class="sxs-lookup"><span data-stu-id="c1529-279">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="c1529-280">Lépjen a **Készlet \> Feltöltés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1529-280">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="c1529-281">A program megkérdezi, hogy befejezi-e az első feltöltési munkát.</span><span class="sxs-lookup"><span data-stu-id="c1529-281">You're prompted to complete the first replenishment work.</span></span> <span data-ttu-id="c1529-282">Megjelenik a kiválasztható cikkszám, mennyiség, és hely.</span><span class="sxs-lookup"><span data-stu-id="c1529-282">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="c1529-283">Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.</span><span class="sxs-lookup"><span data-stu-id="c1529-283">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="c1529-284">Válassza az **OK** gombot (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="c1529-284">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="c1529-285">A rendszer létrehoz egy cél-azonosítótábla-számot az új azonosítótábla számára a kitárolt cikkhez.</span><span class="sxs-lookup"><span data-stu-id="c1529-285">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="c1529-286">Az érték megerősítséséhez kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1529-286">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="c1529-287">A betárolási munka azt mutatja, hogy a felhasználónak a cél-azonosítótáblát a feltöltési helyre kell helyeznie.</span><span class="sxs-lookup"><span data-stu-id="c1529-287">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="c1529-288">A *Betárolás* helynek **06A01R2S1B** kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c1529-288">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="c1529-289">Erősítse meg a betárolás részleteit, és válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="c1529-289">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="c1529-290">„Munka befejezve” üzenet jelenik meg, és a következő feltöltési kitárolási feladat részletei jelennek meg: a választható cikkszám, mennyiség és helyet.</span><span class="sxs-lookup"><span data-stu-id="c1529-290">You receive a "Work Completed" message, and the details of the next replenishment pick task are shown: the item number, quantity, and location to pick from.</span></span> <span data-ttu-id="c1529-291">A kitárolási hely ugyanaz lesz, mint az első feltöltési hely.</span><span class="sxs-lookup"><span data-stu-id="c1529-291">The picking location will be the same as the first replenishment location.</span></span> <span data-ttu-id="c1529-292">Ezért az azonosítótáblának ugyanaz lesz az azonosítótábla-azonosítója, mint az első feltöltési munkafeladaté.</span><span class="sxs-lookup"><span data-stu-id="c1529-292">Therefore, the license plate will have the same license plate ID that was used for the first replenishment work task.</span></span>

1. <span data-ttu-id="c1529-293">A második munkafeladathoz tartozó feltöltési munka befejezéséhez ismételje meg a fenti lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c1529-293">Repeat the preceding steps to complete the replenishment work for the second work task.</span></span> <span data-ttu-id="c1529-294">A mennyiség és a cél azonosítótábla különbözni fog az első munkafeladat mennyiségétől és a cél azonosítótáblától.</span><span class="sxs-lookup"><span data-stu-id="c1529-294">The quantity and target license plate will differ from the quantity and target license plate for the first work task.</span></span>

<span data-ttu-id="c1529-295">A második feltöltési munka befejezése után a „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c1529-295">After the second replenishment work is completed, you receive a "Work Completed" message.</span></span> <span data-ttu-id="c1529-296">A mobileszköz arról is tájékoztatja, hogy nem érhető el a munka, még akkor is, ha a feltöltési munka továbbra is folyik.</span><span class="sxs-lookup"><span data-stu-id="c1529-296">The mobile device also informs you that there is no work available, even though some replenishment work remains.</span></span> <span data-ttu-id="c1529-297">Ez a viselkedés akkor fordul elő, ha a feltöltési munka elérhetőségi állapota *Visszatartva*, és ezért **Zárolva** értékkel lesz megjelölve.</span><span class="sxs-lookup"><span data-stu-id="c1529-297">This behavior occurs because the replenishment work has an availability status of *Held* and is therefore marked as **Blocked**.</span></span>

<span data-ttu-id="c1529-298">A *Visszatartva* állapotot az váltja ki, hogy a munkához társított kitárolási hely helyprofil **Túlcsordulási mennyiség** értéke *0,65 PL*.</span><span class="sxs-lookup"><span data-stu-id="c1529-298">The *Held* status was triggered because the location profile for the picking location that the work is being assigned to has an **Overflow quantity** value of *0.65 PL*.</span></span> <span data-ttu-id="c1529-299">A két korábbi feltöltési munkafeladat majdnem túllépte a hely *T0100* cikkének túlcsordulási korlátját.</span><span class="sxs-lookup"><span data-stu-id="c1529-299">The two previous replenishment work tasks filled the location almost to its overflow limit for item *T0100*.</span></span> <span data-ttu-id="c1529-300">(A cikk mértékegység-átváltása *1 PL = 100 ea*.) Ennélfogva a hátralévő feltöltési munka túllépné a hely túlcsordulási korlátját.</span><span class="sxs-lookup"><span data-stu-id="c1529-300">(The unit conversion for the item is *1 PL = 100 ea*.) Therefore, the remaining replenishment work would cause the location to exceed its overflow limit.</span></span>

<span data-ttu-id="c1529-301">Addig, amíg a raktárból elég készletet ki nem tárolnak ahhoz, hogy a mobileszköz menücikk a munkakiadási küszöbérték alá kerüljön, a feltöltési munka továbbra is zárolva marad.</span><span class="sxs-lookup"><span data-stu-id="c1529-301">Until enough inventory is picked from the location to bring it below the work release threshold on the mobile device menu item, this replenishment work will remain blocked.</span></span>

#### <a name="sales-order-pick"></a><span data-ttu-id="c1529-302">Értékesítési rendelés kitárolása</span><span class="sxs-lookup"><span data-stu-id="c1529-302">Sales order pick</span></span>

<span data-ttu-id="c1529-303">Mielőtt befejezhetné a hátralévő feltöltési munkafeladatot, a kitárolási helyen a készletek olyan szintre kell csökkennie, hogy a hátralévő feltöltési munka feloldhatóvá váljon.</span><span class="sxs-lookup"><span data-stu-id="c1529-303">Before the remaining replenishment work task can be completed, the picking location must be depleted of inventory to a level where the remaining replenishment work can be unblocked.</span></span> <span data-ttu-id="c1529-304">Más szóval a raktárban lévő aktuális készlet mennyiségének és a feltöltési mennyiségnek az összege nem haladhatja meg a **Túlcsordulási mennyiség** értékét.</span><span class="sxs-lookup"><span data-stu-id="c1529-304">In other words, the sum of the quantity of on-hand inventory in the location and the replenishment quantity can't exceed the **Overflow quantity** value.</span></span> <span data-ttu-id="c1529-305">Ha ez az összeg kevesebb, mint a túlcsorduló mennyiség, akkor feloldódik a hátralévő feltöltési munka.</span><span class="sxs-lookup"><span data-stu-id="c1529-305">When this sum is less than the overflow quantity, the remaining replenishment work will be unblocked.</span></span>

1. <span data-ttu-id="c1529-306">Jelentkezzen be az *61*-es raktárban lévő felhasználóként a raktár alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="c1529-306">Sign in to the warehouse app as a user in warehouse *61*.</span></span> <span data-ttu-id="c1529-307">(Írja be a felhasználói azonosítóhoz a *61*-et, a jelszóhoz pedig az *1*-et.)</span><span class="sxs-lookup"><span data-stu-id="c1529-307">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="c1529-308">Lépjen a **Kimenő \> Értékesítési kitárolás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1529-308">Go to **Outbound \> Sales Picking**.</span></span>
1. <span data-ttu-id="c1529-309">Adja meg az 1. értékesítési rendelés első munkaazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="c1529-309">Enter the first work ID for sales order 1.</span></span>

    <span data-ttu-id="c1529-310">A **Munkarészletek** lapon tekintse át a korábban feljegyzett értékesítési rendelések munkaazonosítóit.</span><span class="sxs-lookup"><span data-stu-id="c1529-310">Refer to the work IDs for sales orders that you made a note of earlier, on the **Work details** page.</span></span> <span data-ttu-id="c1529-311">Az itt megadott munkaazonosító egy 10 ea mennyiségre vonatkozó, két különböző helyről bejövő kitárolási munkát fog létrehozni.</span><span class="sxs-lookup"><span data-stu-id="c1529-311">The work ID that you enter here will generate pick work for a quantity of 10 ea from two separate locations.</span></span>

1. <span data-ttu-id="c1529-312">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-312">Select **OK**.</span></span>

    <span data-ttu-id="c1529-313">Az **Értékesítési rendelések: Kitárolás** feladat lapon fogja megjeleníti az első helyhez kiválasztható cikkszámot, mennyiséget és helyet.</span><span class="sxs-lookup"><span data-stu-id="c1529-313">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the first location.</span></span>

1. <span data-ttu-id="c1529-314">Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.</span><span class="sxs-lookup"><span data-stu-id="c1529-314">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="c1529-315">Válassza az **OK** gombot (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="c1529-315">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="c1529-316">Az **Értékesítési rendelések: Kitárolás** feladat lapon fogja megjeleníti a következő helyhez kiválasztható cikkszámot, mennyiséget és helyet.</span><span class="sxs-lookup"><span data-stu-id="c1529-316">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the next location.</span></span>

1. <span data-ttu-id="c1529-317">Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.</span><span class="sxs-lookup"><span data-stu-id="c1529-317">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="c1529-318">Válassza az **OK** gombot (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="c1529-318">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="c1529-319">Az **Értékesítési rendelések: Eltárolás** lap utasítja, hogy tárolja el a befejezett kitárolási munkákat a kimenő előkészítési helyre.</span><span class="sxs-lookup"><span data-stu-id="c1529-319">The **Sales orders: Put** page instructs you to put away both the completed picking works to the outbound staging location.</span></span>

1. <span data-ttu-id="c1529-320">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-320">Select **OK**.</span></span>

    <span data-ttu-id="c1529-321">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c1529-321">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="c1529-322">Adja meg az 1. értékesítési rendelés második munkaazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="c1529-322">Enter the second work ID for sales order 1.</span></span>

    <span data-ttu-id="c1529-323">Ehhez a munkaazonosítóhoz csak egy kitárolási feladat tartozik.</span><span class="sxs-lookup"><span data-stu-id="c1529-323">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="c1529-324">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-324">Select **OK**.</span></span>

    <span data-ttu-id="c1529-325">Az **Értékesítési rendelések: Kitárolás** feladat lapon fogja megjeleníti a kiválasztható cikkszámot, mennyiséget és helyet.</span><span class="sxs-lookup"><span data-stu-id="c1529-325">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="c1529-326">Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.</span><span class="sxs-lookup"><span data-stu-id="c1529-326">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="c1529-327">A feltöltési munkafeladatok közül a meghatározott azonosítótábla lesz az egyik rendszer által előállított azonosítótábla.</span><span class="sxs-lookup"><span data-stu-id="c1529-327">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="c1529-328">Annak érdekében, hogy rögzítse a helyes azonosítótábla-azonosítót, ellenőrizze a készletet a cikk, hely és mennyiség **Aktuális lista** lapján.</span><span class="sxs-lookup"><span data-stu-id="c1529-328">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="c1529-329">Válassza az **OK** gombot (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="c1529-329">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="c1529-330">Erősítse meg a kimenő előkészítési hely betárolási feladatának utasításait.</span><span class="sxs-lookup"><span data-stu-id="c1529-330">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="c1529-331">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-331">Select **OK**.</span></span>

    <span data-ttu-id="c1529-332">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c1529-332">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="c1529-333">A 2. értékesítési rendelés zárolva van a kitárolásból, mert az ezzel összekapcsolt feltöltési feladat nem fejeződött be.</span><span class="sxs-lookup"><span data-stu-id="c1529-333">Sales order 2 is blocked from picking because the replenishment task that it's linked to isn't completed.</span></span> <span data-ttu-id="c1529-334">Jelenleg még mindig van 30 ea mennyiség van a kitárolási helyen, és a 2. értékesítési rendelés feltöltési mennyisége 60 ea.</span><span class="sxs-lookup"><span data-stu-id="c1529-334">Currently, there is still a quantity of 30 ea in the picking location, and the replenishment quantity for sales order 2 is 60 ea.</span></span> <span data-ttu-id="c1529-335">Az aktuális készlet és a feltöltési készlet (90 ea) összege meghaladja a 0,65 PL (vagy 65 ea) túlcsordulási mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-335">The sum of the on-hand inventory and the replenishment inventory (90 ea) exceeds the overflow quantity of 0.65 PL (or 65 ea).</span></span> <span data-ttu-id="c1529-336">A feltöltési munka befejezése előtt a 3. értékesítési rendelést ki kell választani.</span><span class="sxs-lookup"><span data-stu-id="c1529-336">Before the replenishment work can be completed, sales order 3 must be picked.</span></span>

1. <span data-ttu-id="c1529-337">Adja meg a 3. értékesítési rendelés munkaazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="c1529-337">Enter the work ID for sales order 3.</span></span>

    <span data-ttu-id="c1529-338">Ehhez a munkaazonosítóhoz csak egy kitárolási feladat tartozik.</span><span class="sxs-lookup"><span data-stu-id="c1529-338">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="c1529-339">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-339">Select **OK**.</span></span>

    <span data-ttu-id="c1529-340">Az **Értékesítési rendelések: Kitárolás** feladat lapon fogja megjeleníti a kiválasztható cikkszámot, mennyiséget és helyet.</span><span class="sxs-lookup"><span data-stu-id="c1529-340">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="c1529-341">Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.</span><span class="sxs-lookup"><span data-stu-id="c1529-341">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="c1529-342">A feltöltési munkafeladatok közül a meghatározott azonosítótábla lesz az egyik rendszer által előállított azonosítótábla.</span><span class="sxs-lookup"><span data-stu-id="c1529-342">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="c1529-343">Annak érdekében, hogy rögzítse a helyes azonosítótábla-azonosítót, ellenőrizze a készletet a cikk, hely és mennyiség **Aktuális lista** lapján.</span><span class="sxs-lookup"><span data-stu-id="c1529-343">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="c1529-344">Válassza az **OK** gombot (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="c1529-344">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="c1529-345">Erősítse meg a kimenő előkészítési hely betárolási feladatának utasításait.</span><span class="sxs-lookup"><span data-stu-id="c1529-345">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="c1529-346">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-346">Select **OK**.</span></span>

    <span data-ttu-id="c1529-347">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c1529-347">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="c1529-348">Amint a kitárolási helyen található aktuális készlet és a feltöltési mennyiség összege már nem éri el a küszöböt, a hátralévő feltöltési munka feldolgozhatóvá válik.</span><span class="sxs-lookup"><span data-stu-id="c1529-348">As soon as the sum of the on-hand quantity in the picking location and the replenishment quantity is below the threshold, you will be able to process the remaining replenishment work.</span></span>

<span data-ttu-id="c1529-349">Térjen vissza a **Munkarészletek** lapra, és figyelje meg, hogy a feltöltés utolsó részének feltöltési munka elérhetősége (2. értékesítési rendelés) *Nyitva* van-e, mivel már van elég hely a feltöltés elfogadásához.</span><span class="sxs-lookup"><span data-stu-id="c1529-349">Return to the **Work details** page, and notice that the replenishment work availability for the final piece of replenishment (for sales order 2) is *Open*, because there is now enough space in the location to accept the replenishment.</span></span>

<span data-ttu-id="c1529-350">A feltöltési munka most már feldolgozható a mobileszközön keresztül.</span><span class="sxs-lookup"><span data-stu-id="c1529-350">You can now process this replenishment work via the mobile device.</span></span>

1. <span data-ttu-id="c1529-351">Lépjen a **Készlet \> Feltöltés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1529-351">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="c1529-352">A program megkérdezi, hogy befejezi-e a fennmaradó feltöltési munkát.</span><span class="sxs-lookup"><span data-stu-id="c1529-352">You're prompted to complete the remaining replenishment work.</span></span> <span data-ttu-id="c1529-353">Megjelenik a kiválasztható cikkszám, mennyiség, és hely.</span><span class="sxs-lookup"><span data-stu-id="c1529-353">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="c1529-354">Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.</span><span class="sxs-lookup"><span data-stu-id="c1529-354">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="c1529-355">Válassza az **OK** gombot (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="c1529-355">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="c1529-356">A rendszer létrehoz egy cél-azonosítótábla-számot az új azonosítótábla számára a kitárolt cikkhez.</span><span class="sxs-lookup"><span data-stu-id="c1529-356">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="c1529-357">Az érték megerősítséséhez kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c1529-357">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="c1529-358">A betárolási munka azt mutatja, hogy a felhasználónak a cél-azonosítótáblát a feltöltési helyre kell helyeznie.</span><span class="sxs-lookup"><span data-stu-id="c1529-358">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="c1529-359">A *Betárolás* helynek **06A01R2S1B** kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c1529-359">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="c1529-360">Erősítse meg a betárolás részleteit, és válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="c1529-360">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="c1529-361">„Munka befejezve” és „Nem érhető el munka” üzenetek jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="c1529-361">You receive "Work Completed" and "No Work Available" messages.</span></span>

<span data-ttu-id="c1529-362">Most már kitárolhatja a 2. értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="c1529-362">You can now pick sales order 2.</span></span> <span data-ttu-id="c1529-363">A zárolás feloldása akkor történik meg, amikor az értékesítési rendeléshez kapcsolódó feltöltési munka be lett fejezve.</span><span class="sxs-lookup"><span data-stu-id="c1529-363">It became unblocked when the replenishment work that is linked to the sales order was completed.</span></span>

1. <span data-ttu-id="c1529-364">Adja meg a 2. értékesítési rendelés munkaazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="c1529-364">Enter the work ID for sales order 2.</span></span>

    <span data-ttu-id="c1529-365">Ehhez a munkaazonosítóhoz csak egy kitárolási feladat tartozik.</span><span class="sxs-lookup"><span data-stu-id="c1529-365">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="c1529-366">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-366">Select **OK**.</span></span>

    <span data-ttu-id="c1529-367">Az **Értékesítési rendelések: Kitárolás** feladat lapon fogja megjeleníti a kiválasztható cikkszámot, mennyiséget és helyet.</span><span class="sxs-lookup"><span data-stu-id="c1529-367">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="c1529-368">Az **LP** mezőbe írja be a helyen található elemhez megjelenített azonosítótábla számát.</span><span class="sxs-lookup"><span data-stu-id="c1529-368">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="c1529-369">A feltöltési munkafeladatból a meghatározott azonosítótábla lesz a rendszer által előállított azonosítótábla.</span><span class="sxs-lookup"><span data-stu-id="c1529-369">The license plate that you specify will be the system-generated license plate from the replenishment work task.</span></span> <span data-ttu-id="c1529-370">Annak érdekében, hogy rögzítse a helyes azonosítótábla-azonosítót, ellenőrizze a készletet a cikk, hely és mennyiség **Aktuális lista** lapján.</span><span class="sxs-lookup"><span data-stu-id="c1529-370">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="c1529-371">Válassza az **OK** gombot (pipa szimbólum).</span><span class="sxs-lookup"><span data-stu-id="c1529-371">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="c1529-372">Erősítse meg a kimenő előkészítési hely betárolási feladatának utasításait.</span><span class="sxs-lookup"><span data-stu-id="c1529-372">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="c1529-373">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c1529-373">Select **OK**.</span></span>

    <span data-ttu-id="c1529-374">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c1529-374">You receive a "Work Completed" message.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="c1529-375">Megjegyzések és tippek</span><span class="sxs-lookup"><span data-stu-id="c1529-375">Notes and tips</span></span>

- <span data-ttu-id="c1529-376">Ez a funkció minden feltöltési típussal együtt használható: hullámigény, min/max, terhelési igény és időközökre bontás.</span><span class="sxs-lookup"><span data-stu-id="c1529-376">This functionality works with all types of replenishment: wave demand, min/max, load demand, and slotting.</span></span>
- <span data-ttu-id="c1529-377">Szükség szerint manuálisan is felülbírálhatja az egyes munkafejlécekhez tartozó feltöltési munka elérhetőségét a **Munkarészletek** lapon.</span><span class="sxs-lookup"><span data-stu-id="c1529-377">You can manually override the replenishment work availability for each work header from the **Work details** page if you want.</span></span>
- <span data-ttu-id="c1529-378">Amikor a rendszer beállítja a feltöltési munka elérhetőségét, minden olyan készletet figyelembe veszi, amely már a helyen van a munka befejezése előtt</span><span class="sxs-lookup"><span data-stu-id="c1529-378">When the system sets the replenishment work availability, it considers any inventory that is already in the location before any work is completed</span></span>
- <span data-ttu-id="c1529-379">Minden értékesítési rendelés munka egy adott feltöltési munkához kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="c1529-379">Each piece of sales order work is linked to a specific replenishment work.</span></span> <span data-ttu-id="c1529-380">Nincs kapcsolódó értékesítési munka elérhetőségi funkció.</span><span class="sxs-lookup"><span data-stu-id="c1529-380">There is no corresponding sales work availability functionality.</span></span>
