---
title: Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki
description: Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f3ebd47ffc85d4ca257b404579d60d679f7929b6
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301305"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="a120b-103">Nem erősítheti meg a szállítmányt, mert a cikkeket nem tárolták ki</span><span class="sxs-lookup"><span data-stu-id="a120b-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="a120b-104">Hibakód: LoadNotPickedAndMrmedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="a120b-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="a120b-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="a120b-105">Symptoms</span></span>

<span data-ttu-id="a120b-106">Szállítmány megerősítésekor a rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="a120b-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="a120b-107">A(z) %1 rakományhoz szükséges egyes cikkek még nem lettek kitárolva és a végső szállítási helyre áthelyezve.</span><span class="sxs-lookup"><span data-stu-id="a120b-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="a120b-108">Ezért nem tudja megerősíteni a szállítmányt a betöltéshez.</span><span class="sxs-lookup"><span data-stu-id="a120b-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="a120b-109">Ok</span><span class="sxs-lookup"><span data-stu-id="a120b-109">Cause</span></span>

<span data-ttu-id="a120b-110">A rakomány vagy szállítmány jelenleg nem erősíthető meg, mert a következő feltételek valamelyike fennáll:</span><span class="sxs-lookup"><span data-stu-id="a120b-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="a120b-111">A kapcsolódó munkát még nem választották ki és nem helyezték át a végső szállítási helyre.</span><span class="sxs-lookup"><span data-stu-id="a120b-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="a120b-112">A kitárolt munkamennyiség nem egyezik meg a rakománysor létrehozott munkamennyiségével.</span><span class="sxs-lookup"><span data-stu-id="a120b-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="a120b-113">A helyutasítás úgy lett beállítva, hogy a csomagolási hely legyen a végleges kiszállítási hely a hullámsablon tárolóra bontása során.</span><span class="sxs-lookup"><span data-stu-id="a120b-113">The location directive has been configured with packing location as the final shipping location while using Wave template containerization.</span></span>

## <a name="resolution"></a><span data-ttu-id="a120b-114">Megoldás</span><span class="sxs-lookup"><span data-stu-id="a120b-114">Resolution</span></span>

<span data-ttu-id="a120b-115">A rakomány vagy szállítmány jelenleg olyan állapotban van, amelyben a szállítmány megerősítése sikertelen.</span><span class="sxs-lookup"><span data-stu-id="a120b-115">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="a120b-116">A probléma javításához végezze el a következő feladatok egyikét:</span><span class="sxs-lookup"><span data-stu-id="a120b-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="a120b-117">Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="a120b-117">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="a120b-118">Érvénytelenítse azt a munkaazonosítót, amelynél a csomagolási hely a végső szállítási hely, konfigurálja újra a helyutasítást, és adja ki újra a rakományt.</span><span class="sxs-lookup"><span data-stu-id="a120b-118">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="a120b-119">Ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek</span><span class="sxs-lookup"><span data-stu-id="a120b-119">Review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="a120b-120">Az alábbi módon ellenőrizze a rakomány sorait, és győződjön meg róla, hogy minden kapcsolódó munkát befejeztek a végleges kiszállítási helyen, és hogy a mennyiségek megegyeznek.</span><span class="sxs-lookup"><span data-stu-id="a120b-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="a120b-121">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="a120b-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="a120b-122">Válassza ki azt a rakományt, amelynél a szállítmányt nem lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="a120b-122">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="a120b-123">A **Rakománysorok** gyorslapon válassza ki a sor betöltése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a120b-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="a120b-124">Jegyezze fel a **Munka létrehozott mennyisége** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="a120b-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="a120b-125">A Művelet ablaktábla **Betöltések** lapjának **Kapcsolódó információk** csoportjában válassza a **Munka** elemet.</span><span class="sxs-lookup"><span data-stu-id="a120b-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="a120b-126">Ellenőrizze, hogy a munkát a végső kiszállítási helyen befejezték-e, és hogy a kitárolt munkamennyiség megegyezik-e a rakománysor létrehozott munkamennyiségével.</span><span class="sxs-lookup"><span data-stu-id="a120b-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="a120b-127">Ismételje meg ezt az eljárást minden rakománysorral annak érdekében, hogy minden feltétel teljesüljön.</span><span class="sxs-lookup"><span data-stu-id="a120b-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="cancel-the-work-ids-that-have-been-created-with-the-packing-location-as-the-final-shipping-location-reconfigure-the-location-directive-and-rerelease-the-load"></a><span data-ttu-id="a120b-128">Érvénytelenítse azt a munkaazonosítót, amelynél a csomagolási hely a végső szállítási hely, konfigurálja újra a helyutasítást, és adja ki újra a rakományt</span><span class="sxs-lookup"><span data-stu-id="a120b-128">Cancel the work IDs that have been created with the packing location as the final shipping location, reconfigure the location directive, and rerelease the load</span></span>

<span data-ttu-id="a120b-129">A következő módon érvénytelenítse az automatizált tárolóra bontással azt a munkaazonosítót, amelynél a csomagolási hely a végső szállítási hely.</span><span class="sxs-lookup"><span data-stu-id="a120b-129">Use the following procedure to cancel the work IDs that have the packing location as the final put location with automated containerization in place.</span></span>

1. <span data-ttu-id="a120b-130">Menjen a **Raktárkezelés \> Időszakos feladatok \> Tisztítás \> Munka megszakítása** menühöz.</span><span class="sxs-lookup"><span data-stu-id="a120b-130">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="a120b-131">Megjelenik a **Munka érvénytelenítése** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="a120b-131">The **Cancel work** dialog opens.</span></span> <span data-ttu-id="a120b-132">A **Munkaazonosító** mezőben adja meg a megszakítani kívánt munka azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="a120b-132">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span> <span data-ttu-id="a120b-133">A kijelölt munkaazonosító esetében a **Munka állapota** beállításnál a *Nyitott*, a *Folyamatban*, az *Érvénytelenítve*, a *Kombinálva* vagy a *Lezárva* értéknek kell szerepelnie.</span><span class="sxs-lookup"><span data-stu-id="a120b-133">The selected work ID must have a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="a120b-134">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a120b-134">Select **OK**.</span></span>
1. <span data-ttu-id="a120b-135">Válassza az **Igen** lehetőséget a munka megszakításához.</span><span class="sxs-lookup"><span data-stu-id="a120b-135">Select **Yes** to confirm that you want to cancel the work.</span></span>
1. <span data-ttu-id="a120b-136">Ha szükséges, ismételje meg ezt az eljárást a többi munkaazonosítónál.</span><span class="sxs-lookup"><span data-stu-id="a120b-136">Repeat this procedure for the other work IDs as needed.</span></span>

<span data-ttu-id="a120b-137">További információ: [A kivétel kezelésére vonatkozó raktári munka visszavonása](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="a120b-137">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>

<span data-ttu-id="a120b-138">Az alábbi módon konfigurálja újra úgy a helyutasítást, hogy ne a csomagolási hely legyen a végleges kiszállítási hely, amikor a hullámsablonhoz be van állítva az automatikus tárolóra bontás.</span><span class="sxs-lookup"><span data-stu-id="a120b-138">Use the following procedure to reconfigure the location directive so it won't use the packing location as the final shipping location when automated containerization is set up for the wave template.</span></span>

1. <span data-ttu-id="a120b-139">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="a120b-139">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="a120b-140">A **Munkarendelés típusa** mezőben válassza ki az *Értékesítési rendelések* elemet.</span><span class="sxs-lookup"><span data-stu-id="a120b-140">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="a120b-141">Válassza ki az automatikus tárolóra bontáshoz használt helyutasítást.</span><span class="sxs-lookup"><span data-stu-id="a120b-141">Select the location directive you are using for automated containerization.</span></span>
1. <span data-ttu-id="a120b-142">A **Helyutasítási műveletek** gyorslap eszköztárán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a120b-142">On the **Location Directive Actions** FastTab toolbar, select **Edit query**.</span></span>
1. <span data-ttu-id="a120b-143">A Lekérdezésszerkesztő párbeszédpanel **Tartomány** lapján keresse meg azt a sort, ahol a **Mező** értéke *Helyprofil*, és ellenőrizze, hogy a sornál a **Feltételek** mező értéke ne olyan helyprofil legyen, amelynél a **Hely típusa** *Csomagolás*.</span><span class="sxs-lookup"><span data-stu-id="a120b-143">In the query editor dialog, on the **Range** tab, find the row where **Field** is set to *Location profile*, and verify that the **Criteria** field for that row is not set to a location profile that has a **Location type** of *Packing*.</span></span> <span data-ttu-id="a120b-144">A **Feltételek** mezőben javítsa ki a végső szállítási helyet.</span><span class="sxs-lookup"><span data-stu-id="a120b-144">Adjust the **Criteria** field to correct the final put location.</span></span>

<span data-ttu-id="a120b-145">Az alábbi módon adja ki újra a rakományt, és hozza létre a munkaazonosítókat a végső szállítási hellyel.</span><span class="sxs-lookup"><span data-stu-id="a120b-145">Use the following procedure to rerelease the load and create work IDs with the correct final shipping location.</span></span>

1. <span data-ttu-id="a120b-146">Ugorjon a **Raktárkezelés \> Rakományok \> Rakománytervező munkaterület** elemre.</span><span class="sxs-lookup"><span data-stu-id="a120b-146">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="a120b-147">A **Rakományok** szakaszban keresse meg a kiadandó rakományt.</span><span class="sxs-lookup"><span data-stu-id="a120b-147">In the **Loads** section, find the load that needs to be released.</span></span>
1. <span data-ttu-id="a120b-148">A **Rakományok** szakasz eszköztárán a **Kiadás \> Kiadás raktárba** beállítással adja ki a kiválasztott rakoményt a raktárba.</span><span class="sxs-lookup"><span data-stu-id="a120b-148">On the **Loads** section toolbar, select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="a120b-149">Ha szükséges, ismételje meg ezt az eljárást a többi rakománynál.</span><span class="sxs-lookup"><span data-stu-id="a120b-149">Repeat this procedure for the other loads as needed.</span></span>
