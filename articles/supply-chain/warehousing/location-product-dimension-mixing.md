---
title: Hely és termékdimenzió kombinálása
description: Ez a témakör a helyi termékdimenziók kombinálásával kapcsolatban tartalmaz tájékoztatást. Ez a helyprofil funkció segít a helykezelés javításában, ha a termékváltozat vagy dimenziókkal rendelkező termékek kerülnek felhasználásra, például a divatiparban. Ez lehetővé teszi annak eldöntését, hogy a konfigurációk, színek, stílusok és méretek egy adott helyprofil esetében kombinálva vannak-e, illetve hogy csak az ilyen dimenziók egyikét vagy ezek kombinációját lehet ugyanazon a helyen elhelyezni.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSReservationHierarchy, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 73519f3fe79d3d7d917d3044255f735640b8ccfd
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4429841"
---
# <a name="location-product-dimension-mixing"></a><span data-ttu-id="7d049-105">Hely és termékdimenzió kombinálása</span><span class="sxs-lookup"><span data-stu-id="7d049-105">Location product dimension mixing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7d049-106">A helyi termékdimenziók kombinálása helyprofilfunkció segít a helykezelés javításában, ha a termékváltozat vagy dimenziókkal rendelkező termékek kerülnek felhasználásra, például a divatiparban.</span><span class="sxs-lookup"><span data-stu-id="7d049-106">Location product dimension mixing is location profile functionality that helps improve location management when product variants or products that have dimensions are used, such as in the fashion industry.</span></span> <span data-ttu-id="7d049-107">Ez lehetővé teszi annak eldöntését, hogy a konfigurációk, színek, stílusok és méretek egy adott helyprofil esetében kombinálva vannak-e, illetve hogy csak az ilyen dimenziók egyikét vagy ezek kombinációját lehet ugyanazon a helyen elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="7d049-107">It lets you decide whether configurations, colors, styles, and sizes can be mixed for a specific location profile, or whether just one of these dimensions or a combination of them can be put to the same location.</span></span>

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a><span data-ttu-id="7d049-108">A helyi termékdimenzió-kombinálás funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="7d049-108">Turn on the Location product dimension mixing feature</span></span>

<span data-ttu-id="7d049-109">A helyi termékdimenzió-kombinálás használata előtt a funkciót be kall kapcsolni a rendszerében.</span><span class="sxs-lookup"><span data-stu-id="7d049-109">Before you can use location product dimension mixing, the feature must be turned on in your system.</span></span> <span data-ttu-id="7d049-110">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="7d049-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="7d049-111">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="7d049-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="7d049-112">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="7d049-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="7d049-113">**Funkció neve:** *Helyi termékdimenzió-kombinálás*</span><span class="sxs-lookup"><span data-stu-id="7d049-113">**Feature name:** *Location product dimension mixing*</span></span>

## <a name="setup"></a><span data-ttu-id="7d049-114">Beállítás</span><span class="sxs-lookup"><span data-stu-id="7d049-114">Setup</span></span>

<span data-ttu-id="7d049-115">A raktárban minden helyhez társítani kell egy helyprofilt, amely leírja a hely tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="7d049-115">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location.</span></span> <span data-ttu-id="7d049-116">Ennek megfelelően minden olyan hely, amely ugyanazt a helyprofilt használja, lehetővé teheti a cikkdimenziók kombinálását annak beállítása után.</span><span class="sxs-lookup"><span data-stu-id="7d049-116">Therefore, all locations that use the same location profile will be able to allow product dimension mixing after it has been set up.</span></span>

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a><span data-ttu-id="7d049-117">A termékdimenzió-kombinálást lehetővé tevő helyprofilok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="7d049-117">Configure location profiles to allow product dimension mixing</span></span>

1. <span data-ttu-id="7d049-118">Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.</span><span class="sxs-lookup"><span data-stu-id="7d049-118">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="7d049-119">A helyprofilok listáján válassza az **ÖMLESZTETT** elemet.</span><span class="sxs-lookup"><span data-stu-id="7d049-119">In the list of location profiles, select **BULK**.</span></span>
1. <span data-ttu-id="7d049-120">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-120">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="7d049-121">Az **Általános** gyorslapon adja meg a **Helyi termékdimenziók specifikus kombinálásának engedélyezése** beállítását *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="7d049-121">On the **General** FastTab, set the **Enable location product dimension specific mixing** option to *Yes*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d049-122">Ez a beállítás csak akkor állítható *Igen* értékűre, ha a **Vegyes cikkek engedélyezése** beállítás *Nem* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="7d049-122">You can set this option to *Yes* only if the **Allow mixed items** option is set to *No*.</span></span>

1. <span data-ttu-id="7d049-123">Az **Termékdimenzió-kombinálás engedélyezett** gyorslapon adja meg a **Méret** beállítását *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="7d049-123">On the **Allowed product dimension mixing** FastTab, set the **Size** option to *Yes*.</span></span> <span data-ttu-id="7d049-124">Az ebben a témakörben leírt esetben a kombinálás csak olyan termékek esetében hajtható végre, amelyeknél különböző **Méret** dimenziók vannak.</span><span class="sxs-lookup"><span data-stu-id="7d049-124">In the scenario that is described in this topic, mixing can be done only for products that have different **Size** dimensions.</span></span> <span data-ttu-id="7d049-125">Más beállítások is elérhetők azonban.</span><span class="sxs-lookup"><span data-stu-id="7d049-125">However, other options are also available.</span></span>
1. <span data-ttu-id="7d049-126">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-126">Select **Save**.</span></span>

### <a name="create-a-new-product-master-and-product-variants"></a><span data-ttu-id="7d049-127">Új alaptermék és termékváltozatok létrehozása</span><span class="sxs-lookup"><span data-stu-id="7d049-127">Create a new product master and product variants</span></span>

1. <span data-ttu-id="7d049-128">Ugorjon a **Termékinformációk kezelése \> Termékek \> Alaptermékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7d049-128">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="7d049-129">Jelölje be a műveleti ablakban az **Új** lehetőséget az alaptermék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7d049-129">On the Action Pane, select **New** to create a product master.</span></span>
1. <span data-ttu-id="7d049-130">Az **Új termék** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-130">In the **New product** dialog box, set the following values:</span></span>

    - <span data-ttu-id="7d049-131">**Terméktípus:** *Cikk*</span><span class="sxs-lookup"><span data-stu-id="7d049-131">**Product type:** *Item*</span></span>
    - <span data-ttu-id="7d049-132">**Termék altípusa:** *Alaptermék*</span><span class="sxs-lookup"><span data-stu-id="7d049-132">**Product subtype:** *Product master*</span></span>
    - <span data-ttu-id="7d049-133">**Termék száma:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="7d049-133">**Product number:** *B0001*</span></span>
    - <span data-ttu-id="7d049-134">**Termék neve:** *B0001 Méret*</span><span class="sxs-lookup"><span data-stu-id="7d049-134">**Product name:** *B0001 Size*</span></span>
    - <span data-ttu-id="7d049-135">**Termékdimenzió-csoport:** *Méret*</span><span class="sxs-lookup"><span data-stu-id="7d049-135">**Product dimension group:** *Size*</span></span>
    - <span data-ttu-id="7d049-136">**Konfigurálási technológia:** *Előre megadott változat*</span><span class="sxs-lookup"><span data-stu-id="7d049-136">**Configuration technology:** *Predefined variant*</span></span>

1. <span data-ttu-id="7d049-137">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-137">Select **OK**.</span></span>
1. <span data-ttu-id="7d049-138">A **Termék részletei** oldalon, az **Általános** gyorslapon adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-138">On the **Product details** page, on the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="7d049-139">**Változatok automatikus létrehozása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="7d049-139">**Generate variants automatically:** *Yes*</span></span>
    - <span data-ttu-id="7d049-140">**Méret csoport:** *CASUALDHIR*</span><span class="sxs-lookup"><span data-stu-id="7d049-140">**Size group:** *CASUALDHIR*</span></span>

1. <span data-ttu-id="7d049-141">Ha meg szeretné tekinteni az előre megadott változatokat, a Művelet ablaktáblán válassza ki a **Termékváltozatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-141">To view the predefined variants, on the Action Pane, select **Product variants**.</span></span>

    <span data-ttu-id="7d049-142">Megjelenik a **Termékváltozatok** lap, amelyen megtekintheti a méretcsoport konfigurációjától származó változatok listáját.</span><span class="sxs-lookup"><span data-stu-id="7d049-142">The **Product variants** page appears and shows a list of variants from the configuration of the size group.</span></span>

### <a name="release-products-to-the-usmf-company"></a><span data-ttu-id="7d049-143">Termékek kiadása az USMF vállalatnak</span><span class="sxs-lookup"><span data-stu-id="7d049-143">Release products to the USMF company</span></span>

1. <span data-ttu-id="7d049-144">A Művelet ablaktáblán válassza ki a **Termékek kiadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="7d049-144">On the Action Pane, select **Release products**.</span></span>
1. <span data-ttu-id="7d049-145">A **Kiadandó termékek kiválasztása** oldalon ellenőrizze, hogy a *B0001* termékszám szerepel-e a listán, majd válassza a **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-145">On the **Select products to release** page, confirm that product number *B0001* is in the list, and then select **Next**.</span></span>
1. <span data-ttu-id="7d049-146">A kiadandó termékváltozatok megerősítéséhez válassza a **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-146">Select **Next** to confirm the product variants to release.</span></span>
1. <span data-ttu-id="7d049-147">A **Kiadási célként jelölt vállalatok** oldalon válassza ki az *USMF* elemet, majd válassza a **Következő** lehetőséget a kiválasztás jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="7d049-147">On the **Select companies to release to** page, select *USMF*, and then select **Next** to confirm the selection.</span></span>
1. <span data-ttu-id="7d049-148">A **Kiválasztás jóváhagyása** oldalon válassza a **Befejezés** parancsot a kiadás befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="7d049-148">On the **Confirm selection** page, select **Finish** to complete the release.</span></span>

    <span data-ttu-id="7d049-149">A „Művelet befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="7d049-149">You receive an "Operation completed" message.</span></span>

### <a name="update-a-released-product-in-the-usmf-company"></a><span data-ttu-id="7d049-150">Kiadott termék frissítése az USMF vállalatban</span><span class="sxs-lookup"><span data-stu-id="7d049-150">Update a released product in the USMF company</span></span>

1. <span data-ttu-id="7d049-151">Győződjön meg róla, hogy be van jelentkezve az **USMF** vállalatba.</span><span class="sxs-lookup"><span data-stu-id="7d049-151">Make sure that you're signed in to the **USMF** company.</span></span>
1. <span data-ttu-id="7d049-152">Lépjen a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre a kiadott termék létrehozásának befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="7d049-152">Go to **Product information management \> Products \> Released products** to finish creating the released product.</span></span>
1. <span data-ttu-id="7d049-153">Keresse meg, és válassza ki a *B0001* cikkszámot a **Kiadott termék részletei** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7d049-153">Find and select item number *B0001* to open the **Released product details** page.</span></span>
1. <span data-ttu-id="7d049-154">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-154">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="7d049-155">Győződjön meg arról, hogy az **Általános** gyorslapon a **Cikkmodellcsoport** mező értéke *FIFO*.</span><span class="sxs-lookup"><span data-stu-id="7d049-155">On the **General** FastTab, make sure that the **Item model group** field is set to *FIFO*.</span></span>
1. <span data-ttu-id="7d049-156">A Művelet panel **Termék** lapján, a **Beállítás** csoportban válassza a **Dimenziócsoportok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-156">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Dimension groups**.</span></span>
1. <span data-ttu-id="7d049-157">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-157">Set the following values:</span></span>

    - <span data-ttu-id="7d049-158">**Tárolásidimenzió-csoport:** *Áru*</span><span class="sxs-lookup"><span data-stu-id="7d049-158">**Storage dimension group:** *Ware*</span></span>
    - <span data-ttu-id="7d049-159">**Nyomonkövetésidimenzió-csoport:** *Nincs*</span><span class="sxs-lookup"><span data-stu-id="7d049-159">**Tracking dimension group:** *None*</span></span>

1. <span data-ttu-id="7d049-160">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-160">Select **OK**.</span></span>
1. <span data-ttu-id="7d049-161">A Művelet panel **Termék** lapján, a **Beállítás** csoportban válassza a **Foglalási hierarchia** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-161">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Reservation hierarchy**.</span></span>
1. <span data-ttu-id="7d049-162">Állítsa be a **Foglalási hierarchia** mezőt az *Alapértelmezett* értékre, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="7d049-162">Set the **Reservation hierarchy** field to *Default*, and then select **OK**.</span></span>
1. <span data-ttu-id="7d049-163">Az **Általános** gyorslap **Adminisztráció** részében figyelje meg, hogy a kiválasztások frissítve lettek-e.</span><span class="sxs-lookup"><span data-stu-id="7d049-163">On the **General** FastTab, in the **Administration** section, notice that your selections have been updated.</span></span>
1. <span data-ttu-id="7d049-164">A **Beszerzés** gyorslap **Ár** mezőjébe írja be a *10* értéket.</span><span class="sxs-lookup"><span data-stu-id="7d049-164">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="7d049-165">A **Költségek kezelése** gyorslapon, a **Cikkcsoport** mezőben adja meg az *Audio* értéket.</span><span class="sxs-lookup"><span data-stu-id="7d049-165">On the **Manage costs** FastTab, in the **Item group** field, enter *Audio*.</span></span>
1. <span data-ttu-id="7d049-166">A **Beszerzés** gyorslap **Ár** mezőjébe írja be a *10* értéket.</span><span class="sxs-lookup"><span data-stu-id="7d049-166">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="7d049-167">A **Raktár** gyorslap **Egységszekvenciacsoport-azonosító** mezőjében adja meg az *ea* értéket.</span><span class="sxs-lookup"><span data-stu-id="7d049-167">On the **Warehouse** FastTab, in the **Unit sequence group ID** field, enter *ea*.</span></span>
1. <span data-ttu-id="7d049-168">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-168">Select **Save**.</span></span>

### <a name="create-a-location-directive"></a><span data-ttu-id="7d049-169">Helyutasítási műveletek</span><span class="sxs-lookup"><span data-stu-id="7d049-169">Create a location directive</span></span>

1. <span data-ttu-id="7d049-170">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="7d049-170">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="7d049-171">A bal oldali ablaktáblában állítsa a **Munkarendelés típusa** mezőt a *Munkarendelések* értékre.</span><span class="sxs-lookup"><span data-stu-id="7d049-171">In the left pane, in the **Work order type** field, select *Purchase orders*.</span></span>
1. <span data-ttu-id="7d049-172">A listából válassza ki azt a helyutasítást, amely a *24 PO Közvetlen* névvel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="7d049-172">In the list, select the location directive that is named *24 PO Direct*.</span></span>
1. <span data-ttu-id="7d049-173">A **Helyutasítások műveletei** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7d049-173">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="7d049-174">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="7d049-175">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="7d049-175">**Sequence number:** *1*</span></span>

        <span data-ttu-id="7d049-176">Az új sornak a korábban meglévő sor előtt kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7d049-176">The new line should be in front of the previously existing line.</span></span> <span data-ttu-id="7d049-177">A módosításhoz használja a **Mozgatás felfelé** és **Mozgatás lefelé** gombokat az eszköztáron, vagy módosítsa a meglévő sor **Sorszám** beállítását *2* értékre.</span><span class="sxs-lookup"><span data-stu-id="7d049-177">To make the change, use the **Move up** and **Move down** buttons on the toolbar, or change the existing line's **Sequence number** value to *2*.</span></span>

    - <span data-ttu-id="7d049-178">**Név:** *Betárolás az ÖMLESZTETT helyprofilhoz*</span><span class="sxs-lookup"><span data-stu-id="7d049-178">**Name:** *Put to BULK Location profile*</span></span>
    - <span data-ttu-id="7d049-179">**Rögzített hely használata:** *Rögzített és nem rögzített helyek*</span><span class="sxs-lookup"><span data-stu-id="7d049-179">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>
    - <span data-ttu-id="7d049-180">**Negatív készlet engedélyezése:** *Törölje a jelet a jelölőnégyzetből (=No)*</span><span class="sxs-lookup"><span data-stu-id="7d049-180">**Allow negative inventory:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="7d049-181">**Köteg engedélyezve:** *Törölje a jelet a jelölőnégyzetből (=No)*</span><span class="sxs-lookup"><span data-stu-id="7d049-181">**Batch enabled:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="7d049-182">**Stratégia:** *Nincs*</span><span class="sxs-lookup"><span data-stu-id="7d049-182">**Strategy:** *None*</span></span>

1. <span data-ttu-id="7d049-183">Az új sort továbbra is kijelölve, válassza a rács fölötti **Lekérdezés szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="7d049-183">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="7d049-184">A lekérdezés párbeszédpanelen, a **Tartomány** lapon a **Hozzáadás** gombbal adjon hozzá egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="7d049-184">In the query dialog box, on the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="7d049-185">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-185">On the new line, set the following values:</span></span>

    - <span data-ttu-id="7d049-186">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="7d049-186">**Table:** *Locations*</span></span>
    - <span data-ttu-id="7d049-187">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="7d049-187">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="7d049-188">**Mező:** *Hely profilazonosítója*</span><span class="sxs-lookup"><span data-stu-id="7d049-188">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="7d049-189">**Feltételek:** *BULK*</span><span class="sxs-lookup"><span data-stu-id="7d049-189">**Criteria:** *BULK*</span></span>

1. <span data-ttu-id="7d049-190">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-190">Select **OK**.</span></span>
1. <span data-ttu-id="7d049-191">A **Helyutasítások** oldalon, a műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-191">On the **Location directives** page, on the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="7d049-192">Ha a **Helyutasítási műveletek** gyorslap **Stratégia** mezőjében, ha a *Konszolidáció* helystratégiát használja, a **Termékdimenzió-kombinálás engedélyezett** gyorslap beállítását a **Helyprofilok** részen a rendszer felülbírálja, és a cikkek ugyanazon a helyen kerülnek elhelyezésre akkor is, ha ezt a viselkedést a beállítás nem engedélyezi.</span><span class="sxs-lookup"><span data-stu-id="7d049-192">On the **Location Directive Actions** FastTab **Strategy** field, if you use the *Consolidate* location strategy, the setup of the **Allowed product dimension mixing** FastTab on the **Location profiles** will be overridden, and items will be put to the same location even if this behavior isn't allowed by the setup.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="7d049-193">Mobileszköz-menüpont létrehozása</span><span class="sxs-lookup"><span data-stu-id="7d049-193">Create a mobile device menu item</span></span>

1. <span data-ttu-id="7d049-194">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="7d049-194">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="7d049-195">A művelet ablaktáblán válassza az **Új** parancsot a rendezéshez használandó menüelem létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7d049-195">On the Action Pane, select **New** to create a menu item to use for sorting.</span></span>
1. <span data-ttu-id="7d049-196">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-196">In the header, set the following values:</span></span>

    - <span data-ttu-id="7d049-197">**Menüelem neve:** *Beszerzési rendelési sor bevételezése*</span><span class="sxs-lookup"><span data-stu-id="7d049-197">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="7d049-198">**Cím:** *Beszerzési rendelési sor bevételezése*</span><span class="sxs-lookup"><span data-stu-id="7d049-198">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="7d049-199">**Mód:** *Munka*</span><span class="sxs-lookup"><span data-stu-id="7d049-199">**Mode:** *Work*</span></span>
    - <span data-ttu-id="7d049-200">**Meglévő munka használata:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="7d049-200">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="7d049-201">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-201">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="7d049-202">**Munkalétrehozási folyamat:** *Beszerzési rendelési sor bevételezése és eltárolása*</span><span class="sxs-lookup"><span data-stu-id="7d049-202">**Work creation process:** *Purchase order line receiving and putaway*</span></span>
    - <span data-ttu-id="7d049-203">**Azonosítótábla létrehozása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="7d049-203">**Generate license plate:** *Yes*</span></span>

1. <span data-ttu-id="7d049-204">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-204">Select **Save**.</span></span>

### <a name="configure-the-mobile-device-menu"></a><span data-ttu-id="7d049-205">A mobileszköz menüjének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="7d049-205">Configure the mobile device menu</span></span>

1. <span data-ttu-id="7d049-206">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.</span><span class="sxs-lookup"><span data-stu-id="7d049-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="7d049-207">A menük listáján válassza a **Bejövő** elemet.</span><span class="sxs-lookup"><span data-stu-id="7d049-207">In the list of menus, select **Inbound**.</span></span>
1. <span data-ttu-id="7d049-208">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-208">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="7d049-209">A **Rendelkezésre álló menük és menüelemek** listájában keresse meg és válassza ki a **Beszerzési rendelési sor bevételezése** menüelemet.</span><span class="sxs-lookup"><span data-stu-id="7d049-209">In the **Available Menus And Menu Items** list, find and select the **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="7d049-210">Válassza a jobbra mutató nyílgombot a **Beszerzési rendelési sor bevételezése** menüelem **Menüstruktúra** listában való elhelyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="7d049-210">Select the right arrow button to move the **PO line receiving** menu item to the **Menu Structure** list.</span></span> <span data-ttu-id="7d049-211">Ily módon hozzáadja az új menüelemet a kijelölt menühöz.</span><span class="sxs-lookup"><span data-stu-id="7d049-211">In this way, you add your new menu item to the selected menu.</span></span>
1. <span data-ttu-id="7d049-212">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-212">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="7d049-213">Forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="7d049-213">Scenario</span></span>

<span data-ttu-id="7d049-214">Ez a forgatókönyv azt mutatja be, hogyan lehet ugyanazon a helyen két különböző termékváltozatot elhelyezni, amikor a helyprofil nem engedélyezi a vegyes cikkeket, de a *Helyi termékdimenzió-kombinálás* funkció engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="7d049-214">This demo scenario shows how two different product variants can be put to the same location when the location profile doesn't allow for mixed items, but the *Location product dimension mixing* feature is enabled.</span></span> <span data-ttu-id="7d049-215">Ebben az esetben a **Méret** változatot kell használni feltételként.</span><span class="sxs-lookup"><span data-stu-id="7d049-215">In this case, you will use the **Size** variant as the criterion.</span></span>

<span data-ttu-id="7d049-216">Kezdés előtt győződjön meg arról, hogy a *24*. raktárban üres helyek szerepelnek, amelyek az *ÖMLESZTETT* helyprofilt használják.</span><span class="sxs-lookup"><span data-stu-id="7d049-216">Before you begin, make sure that there are empty locations in warehouse *24* that use the *BULK* location profile.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="7d049-217">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="7d049-217">Create a purchase order</span></span>

<span data-ttu-id="7d049-218">Olyan beszerzési rendelést hoz létre, amelynek három sora van: két sor ugyanannak a termékazonosítónak, de eltérő **Méret** változatokhoz, és egy harmadik sor egy másik termékhez, amely nem tartalmaz változatokat.</span><span class="sxs-lookup"><span data-stu-id="7d049-218">You will create a purchase order that has three lines: two lines for the same product number but different **Size** variants, and a third line for a different product that has no variants.</span></span>

1. <span data-ttu-id="7d049-219">Nyissa meg a következőt: **Kötelezettségek \> Beszerzési rendelések \> Minden beszerzési rendelés**.</span><span class="sxs-lookup"><span data-stu-id="7d049-219">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="7d049-220">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="7d049-220">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7d049-221">Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-221">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="7d049-222">**Szállítói számla:** *1001*</span><span class="sxs-lookup"><span data-stu-id="7d049-222">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="7d049-223">**Raktár:** *24*</span><span class="sxs-lookup"><span data-stu-id="7d049-223">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="7d049-224">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-224">Select **OK**.</span></span>
1. <span data-ttu-id="7d049-225">A beszerzési rendelés létrejön, és a program új sort ad hozzá a **Beszerzésirendelés-sorok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="7d049-225">The purchase order is created, and a new line is added on the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="7d049-226">Jegyezze fel a beszerzési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="7d049-226">Make a note of the purchase order number.</span></span>
1. <span data-ttu-id="7d049-227">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-227">On the new line, set the following values:</span></span>

    - <span data-ttu-id="7d049-228">**Cikkszám:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="7d049-228">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="7d049-229">**Méret** *L*</span><span class="sxs-lookup"><span data-stu-id="7d049-229">**Size** *L*</span></span>
    - <span data-ttu-id="7d049-230">**Mennyiség:** *2*</span><span class="sxs-lookup"><span data-stu-id="7d049-230">**Quantity:** *2*</span></span>

1. <span data-ttu-id="7d049-231">Válassza ki a rács felett a **Sor hozzáadása** lehetőséget egy második beszerzési rendelési sor hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-231">Select **Add line** above the grid to add a second purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="7d049-232">**Cikkszám:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="7d049-232">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="7d049-233">**Méret** *XL*</span><span class="sxs-lookup"><span data-stu-id="7d049-233">**Size** *XL*</span></span>
    - <span data-ttu-id="7d049-234">**Mennyiség:** *2*</span><span class="sxs-lookup"><span data-stu-id="7d049-234">**Quantity:** *2*</span></span>

1. <span data-ttu-id="7d049-235">Válassza ki a **Sor hozzáadása** lehetőséget egy harmadik sor hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="7d049-235">Select **Add line** to add a third purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="7d049-236">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="7d049-236">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="7d049-237">**Mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="7d049-237">**Quantity:** *1*</span></span>

<span data-ttu-id="7d049-238">1. Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-238">1.Select **Save**.</span></span>

### <a name="receive-purchase-order-lines-in-the-warehouse-app"></a><span data-ttu-id="7d049-239">Beszerzési rendelési sorok fogadása a raktározási alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="7d049-239">Receive purchase order lines in the warehouse app</span></span>

1. <span data-ttu-id="7d049-240">Jelentkezzen be a raktározási alkalmazásba olyan felhasználóként, aki a *24*. raktárban engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="7d049-240">Sign in to the warehouse app as a user who is enabled for warehouse *24*.</span></span>
1. <span data-ttu-id="7d049-241">Válassza ki a **Bejövő** menüt.</span><span class="sxs-lookup"><span data-stu-id="7d049-241">Select the **Inbound** menu.</span></span>
1. <span data-ttu-id="7d049-242">Válassza ki a **Beszerzési rendelési sor bevételezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-242">Select **PO Line receiving**.</span></span>
1. <span data-ttu-id="7d049-243">Válassza ki a **PONUM** mezőt, majd adja meg a beszerzési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="7d049-243">Select the **PONUM** field, and then enter the purchase order number.</span></span>
1. <span data-ttu-id="7d049-244">Hagyja jóvá a bejegyzést a lap alján látható jóváhagyás gombra (✔) kattintva.</span><span class="sxs-lookup"><span data-stu-id="7d049-244">Confirm your entry by selecting the confirm button ( ✔ ) at the bottom of the page.</span></span>
1. <span data-ttu-id="7d049-245">Adja meg a sor számát a bevételezett beszerzési rendelésből.</span><span class="sxs-lookup"><span data-stu-id="7d049-245">Enter the line number from the purchase order that is being received.</span></span> <span data-ttu-id="7d049-246">Válassza ki a **LINENUM** mezőt, majd a számbillentyűzeten adja meg az *1* értéket.</span><span class="sxs-lookup"><span data-stu-id="7d049-246">Select the **LINENUM** field, and then use the number pad to enter *1*.</span></span>
1. <span data-ttu-id="7d049-247">Hagyja jóvá a bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="7d049-247">Confirm your entry.</span></span>
1. <span data-ttu-id="7d049-248">Írja be a fogadásra kerülő mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-248">Enter the quantity to receive.</span></span> <span data-ttu-id="7d049-249">Nyomja meg kétszer a pluszjelet (**+**) a **Mennyiség** mező értékének *2*-re.</span><span class="sxs-lookup"><span data-stu-id="7d049-249">Select the plus sign (**+**) button two times to increase the value in the **Qty** field to *2*.</span></span>
1. <span data-ttu-id="7d049-250">Regisztrálja a bejegyzését a lap alján látható (✔) gombot megnyomva, majd hagyja jóvá a bejegyzést ismét a (✔) gombot megnyomva.</span><span class="sxs-lookup"><span data-stu-id="7d049-250">Register your entry by selecting the button ( ✔ ) at the bottom of the page, and then confirm your entry by selecting the button ( ✔ ) again.</span></span>
1. <span data-ttu-id="7d049-251">Tekintse meg a **Beszerzési rendelések: Betárolás** oldalon látható információkat.</span><span class="sxs-lookup"><span data-stu-id="7d049-251">View the information on the **Purchase orders: Put** page.</span></span> <span data-ttu-id="7d049-252">Ez a lap az elraktározáshoz létrehozott munkát jeleníti meg (1. munka).</span><span class="sxs-lookup"><span data-stu-id="7d049-252">This page shows the work that has been created for the put-away (Work 1).</span></span>

    <span data-ttu-id="7d049-253">Az a hely, ahol a bevételezett cikkek eltárolásra kerülnek, az azonosítótábla, a cikk, a méret és az éppen befejezett **Beszerzési rendelési sor bevételezése** feladat mennyisége jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="7d049-253">The location where the received item will be put away, the license plate, the item, the size, and the quantity of the **PO Line receiving** task that you just completed are shown.</span></span>

1. <span data-ttu-id="7d049-254">Erősítse meg az elraktározási munkát.</span><span class="sxs-lookup"><span data-stu-id="7d049-254">Confirm the put-away work.</span></span>
1. <span data-ttu-id="7d049-255">Ismételje meg a 4–11. lépést a 2. beszerzésirendelés-sor esetében.</span><span class="sxs-lookup"><span data-stu-id="7d049-255">Repeat the steps 4 through 11 for the purchase order line 2.</span></span> <span data-ttu-id="7d049-256">A 8. lépésben azonban adja meg az *1* mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-256">However, in step 8, specify a quantity of *1*.</span></span>

    <span data-ttu-id="7d049-257">Az új elraktározási munka (2. munka) ugyanarra a helyre jön létre, mint az 1. munka.</span><span class="sxs-lookup"><span data-stu-id="7d049-257">New put-away work (Work 2) is created for the same location as Work 1.</span></span>

1. <span data-ttu-id="7d049-258">Ismételje meg a 4–11. lépést a 2. beszerzésirendelés-sor esetében.</span><span class="sxs-lookup"><span data-stu-id="7d049-258">Repeat the steps 4 through 11 again for purchase order line 2.</span></span> <span data-ttu-id="7d049-259">A 8. lépésben adja meg a fennmaradó *1* mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="7d049-259">In step 8, specify the remaining quantity of *1*.</span></span>

    <span data-ttu-id="7d049-260">Az új elraktározási munka (3. munka) ugyanarra a helyre jön létre, mint az 1. munka és a 2. munka.</span><span class="sxs-lookup"><span data-stu-id="7d049-260">New put-away work (Work 3) is created for the same location as Work 1 and Work 2.</span></span> <span data-ttu-id="7d049-261">Ennek oka az, hogy a rendszer a *Konszolidációs* helyutasítási stratégiát használja, és a **Termékdimenzió-kombinálás engedélyezett** gyorslap az *Ömlesztett* **Helyprofilok** beállításban lehetővé teszi a **Méret** változat kombinálását egy helyen.</span><span class="sxs-lookup"><span data-stu-id="7d049-261">This behavior occurs because the *Consolidate* location directive strategy is used, and the **Allowed product dimension mixing** FastTab on the *Bulk* **Location profiles** setup allows the **Size** variant to be mixed on a location.</span></span>

1. <span data-ttu-id="7d049-262">Ismételje meg a 4–11. lépést a 3. beszerzésirendelés-sor esetében.</span><span class="sxs-lookup"><span data-stu-id="7d049-262">Repeat the steps 4 through 11 for purchase order line 3.</span></span> <span data-ttu-id="7d049-263">A 8. lépésben adja meg az *1* mennyiséget az *A0001* cikkszámhoz.</span><span class="sxs-lookup"><span data-stu-id="7d049-263">In step 8, specify a quantity of *1* for item number *A0001*.</span></span>

    <span data-ttu-id="7d049-264">Az új elraktározási munka (4. munka) egy másik helyre jön létre, mint az 1. és 2. beszerzésirendelés-sorokhoz használt hely.</span><span class="sxs-lookup"><span data-stu-id="7d049-264">New put-away work (Work 4) is created for a different location than the location that is used for purchase order lines 1 and 2.</span></span> <span data-ttu-id="7d049-265">Ennek oka az, hogy a hely profilja nem engedélyezi a vegyes termékeket, de lehetővé teszi ugyanannak az alapterméknek a vegyes dimenzióit.</span><span class="sxs-lookup"><span data-stu-id="7d049-265">This behavior occurs because the location profile doesn't allow for mixed products, but it does allow for mixed dimensions of the same product master.</span></span>

1. <span data-ttu-id="7d049-266">Válassza ki a lap tetején látható Menü gombot (néha hamburgernek vagy a hamburgergombnak is nevezik), majd válassza ki a **Mégse** lehetőséget a **Beszerzési rendelési sor bevételezése** részből való kilépéshez.</span><span class="sxs-lookup"><span data-stu-id="7d049-266">Select the Menu button at the top of the page (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit **PO Line receiving**.</span></span>

> [!TIP]
> <span data-ttu-id="7d049-267">Ezt az esetet megismételheti, de ez alkalommal állítsa be a **Méret** - *Nem* értéket a **Termékdimenzió-kombinálás engedélyezése** gyorslapon, az *ÖMLESZTETT* **Helyprofilok** részen, hogy a cikkdimenziók egyikét se lehessen kombinálni.</span><span class="sxs-lookup"><span data-stu-id="7d049-267">You can repeat this scenario, but this time, set **Size** - *No* under the **Allow product dimension mixing** FastTab on the *BULK* **Location profiles**, so that none of the product dimensions can be mixed.</span></span> <span data-ttu-id="7d049-268">Ebben az esetben a beszerzési rendelés beérkezésekor a program az egyes termékváltozatokat új helyre helyezi.</span><span class="sxs-lookup"><span data-stu-id="7d049-268">In this case, when you receive the purchase order, each product variant will be put to a new location.</span></span>