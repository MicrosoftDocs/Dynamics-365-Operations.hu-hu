---
title: Különböző dimenziók beállítása csomagoláshoz és tároláshoz
description: Ez a témakör bemutatja, hogyan adhatja meg, hogy az egyes megadott dimenziókat mely folyamathoz (csomagolás, tárolás vagy beágyazott csomagolás) használják.
author: mirzaab
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: aa5cbf807e809238489c539d3ad8c0bc34421774
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501294"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a><span data-ttu-id="c9c78-103">Különböző dimenziók beállítása csomagoláshoz és tároláshoz</span><span class="sxs-lookup"><span data-stu-id="c9c78-103">Set different dimensions for packing and storage</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="c9c78-104">Egyes cikkek csomagolása és tárolása olyan módon történik, hogy különböző folyamatoknál különböző módon kell nyomon követni a fizikai méreteket.</span><span class="sxs-lookup"><span data-stu-id="c9c78-104">Some items are packed or stored in such a way that you may need to track physical dimensions differently for each of several different processes.</span></span> <span data-ttu-id="c9c78-105">A *Csomagolótermék-dimenziók* funkcióval termékenként egy vagy több dimenziótípust állíthat be.</span><span class="sxs-lookup"><span data-stu-id="c9c78-105">The *Packaging product dimensions* feature lets you set up one or several types of dimensions for each product.</span></span> <span data-ttu-id="c9c78-106">Minden dimenziótípus fizikai mértékek (súly, szélesség, mélység és magasság) sorozatát biztosítja, és meghatározza azt a folyamatot, amelyben ezek a fizikai mértékegységek érvényesek.</span><span class="sxs-lookup"><span data-stu-id="c9c78-106">Each dimension type provides a set of physical measurements (weight, width, depth, and height), and establishes the process where those physical measurement values apply.</span></span> <span data-ttu-id="c9c78-107">Ha ez a funkció engedélyezve van, a rendszer a következő dimenziótípusokat támogatja:</span><span class="sxs-lookup"><span data-stu-id="c9c78-107">When this feature is enabled, your system will support the following types of dimensions:</span></span>

- <span data-ttu-id="c9c78-108">*Tárolás* – a tárolási dimenziók a helyi térfogatméréssel együtt használatosak annak meghatározására, hogy az egyes cikkek mekkora része tárolható különböző raktározási helyeken.</span><span class="sxs-lookup"><span data-stu-id="c9c78-108">*Storage* - Storage dimensions are used along with location volumetrics to determine how many of each item can be stored in various warehouse locations.</span></span>
- <span data-ttu-id="c9c78-109">*Csomagolás* – a csomagolási dimenziók a tárolóra bontás és a kézi csomagolási folyamat során használatosak annak meghatározására, hogy az egyes cikkek mekkora része fér el a különböző tárolótípusokban.</span><span class="sxs-lookup"><span data-stu-id="c9c78-109">*Packing* - Packing dimensions are used during containerization and the manual packing process to determine how many of each item will fit in various container types.</span></span>
- <span data-ttu-id="c9c78-110">*Beágyazott csomagolás* – a beágyazott csomagolási dimenziók akkor használatosak, ha a csomagolási folyamat több szintet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="c9c78-110">*Nested packing* - Nested packing dimensions are used when the packing process contains multiple levels.</span></span>

<span data-ttu-id="c9c78-111">A *Tárolás* dimenziók akkor is támogatottak, ha a *Csomagolótermék-dimenziók* funkció nincs engedélyezve.</span><span class="sxs-lookup"><span data-stu-id="c9c78-111">*Storage* dimensions are supported even when the *Packaging product dimensions* feature isn't enabled.</span></span> <span data-ttu-id="c9c78-112">Ezeket a **Fizikai dimenzió** lapon állíthatja be a Supply Chain Management eszközben.</span><span class="sxs-lookup"><span data-stu-id="c9c78-112">You set these up using the **Physical dimension** page in Supply Chain Management.</span></span> <span data-ttu-id="c9c78-113">Ezeket a dimenziókat minden olyan folyamat használja, ahol nincs megadva a csomagolás és a beágyazott csomagolási dimenzió.</span><span class="sxs-lookup"><span data-stu-id="c9c78-113">These dimensions are used by all processes where the packing and nested packing dimensions aren't specified.</span></span>

<span data-ttu-id="c9c78-114">A *Csomagolás* és a *Beágyazott csomagolás* dimenziók beállítása a **Tényleges termékdimenziók** lapon történik, amelyet a rendszer a *Csomagolótermék-dimenziók* funkció engedélyezésekor ad hozzá.</span><span class="sxs-lookup"><span data-stu-id="c9c78-114">*Packing* and *nested packing* dimensions are set up using the **Physical product dimensions** page, which is added when you enable the *Packaging product dimensions* feature.</span></span>
<span data-ttu-id="c9c78-115">Ez a témakör egy olyan forgatókönyvet tartalmaz, amely bemutatja a funkció használatát.</span><span class="sxs-lookup"><span data-stu-id="c9c78-115">This topic provides a scenario that illustrates how to use this feature.</span></span>

## <a name="turn-on-the-packaging-product-dimensions-feature"></a><span data-ttu-id="c9c78-116">Kapcsolja be a Csomagolótermék-dimenziók funkciót</span><span class="sxs-lookup"><span data-stu-id="c9c78-116">Turn on the packaging product dimensions feature</span></span>

<span data-ttu-id="c9c78-117">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="c9c78-117">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="c9c78-118">A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="c9c78-118">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="c9c78-119">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="c9c78-119">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c9c78-120">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="c9c78-120">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="c9c78-121">**Funkció neve:** *Csomagolótermék-dimenziók*</span><span class="sxs-lookup"><span data-stu-id="c9c78-121">**Feature name:** *Packaging product dimensions*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="c9c78-122">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="c9c78-122">Example scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="c9c78-123">Forgatókönyv beállítása</span><span class="sxs-lookup"><span data-stu-id="c9c78-123">Set up the scenario</span></span>

<span data-ttu-id="c9c78-124">A példahelyzet futtatása előtt elő kell készítenie a rendszert az ebben a részben leírt módon.</span><span class="sxs-lookup"><span data-stu-id="c9c78-124">Before you can run the example scenario, you must prepare your system as described in this section.</span></span>

#### <a name="enable-demo-data"></a><span data-ttu-id="c9c78-125">Bemutatóadatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="c9c78-125">Enable demo data</span></span>

<span data-ttu-id="c9c78-126">Ha ezt a forgatókönyvet az itt megadott bemutatórekordok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="c9c78-126">To work through this scenario using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="c9c78-127">Emellett az *USMF* jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="c9c78-127">Additionally, you must select the *USMF* legal entity before you begin.</span></span>

#### <a name="add-a-new-physical-dimension-to-a-product"></a><span data-ttu-id="c9c78-128">Új fizikai dimenzió hozzáadása egy termékhez</span><span class="sxs-lookup"><span data-stu-id="c9c78-128">Add a new physical dimension to a product</span></span>

<span data-ttu-id="c9c78-129">Adjon hozzá új fizikai dimenziót egy termékhez a következő lépések alapján:</span><span class="sxs-lookup"><span data-stu-id="c9c78-129">Add a new physical dimension for a product by doing the following:</span></span>

1. <span data-ttu-id="c9c78-130">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9c78-130">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="c9c78-131">Válassza ki az *A0001* **Cikkszámú** terméket.</span><span class="sxs-lookup"><span data-stu-id="c9c78-131">Select the product with **Item number** *A0001*.</span></span>
1. <span data-ttu-id="c9c78-132">A Műveleti panelen nyissa meg a **Készletkezelés** lapot és a **Raktár** csoportban válassza ki a **Tényleges termékdimenziók** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9c78-132">On the Action Pane, open the **Manage inventory** tab and, from the **Warehouse** group, select **Physical product dimensions**.</span></span>
1. <span data-ttu-id="c9c78-133">Megnyílik a **Tényleges termékdimenziók** lap.</span><span class="sxs-lookup"><span data-stu-id="c9c78-133">The **Physical product dimensions** page opens.</span></span> <span data-ttu-id="c9c78-134">A Művelet panelen válassza az **Új** lehetőséget egy új dimenzió rácshoz való hozzáadásához a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="c9c78-134">On the Action Pane, select **New** to add a new dimension to the grid with the following settings:</span></span>
    - <span data-ttu-id="c9c78-135">**Tényleges dimenziótípus** - *Csomagolás*</span><span class="sxs-lookup"><span data-stu-id="c9c78-135">**Physical dimension type** - *Packing*</span></span>
    - <span data-ttu-id="c9c78-136">**Fizikai egység** - *db*</span><span class="sxs-lookup"><span data-stu-id="c9c78-136">**Physical unit** - *pcs*</span></span>
    - <span data-ttu-id="c9c78-137">**Tömeg** - *4*</span><span class="sxs-lookup"><span data-stu-id="c9c78-137">**Weight** - *4*</span></span>
    - <span data-ttu-id="c9c78-138">**Tömegegység** - *kg*</span><span class="sxs-lookup"><span data-stu-id="c9c78-138">**Weight unit** - *kg*</span></span>
    - <span data-ttu-id="c9c78-139">**Mélység** - *3*</span><span class="sxs-lookup"><span data-stu-id="c9c78-139">**Depth** - *3*</span></span>
    - <span data-ttu-id="c9c78-140">**Magasság** - *4*</span><span class="sxs-lookup"><span data-stu-id="c9c78-140">**Height** - *4*</span></span>
    - <span data-ttu-id="c9c78-141">**Szélesség** - *3*</span><span class="sxs-lookup"><span data-stu-id="c9c78-141">**Width** - *3*</span></span>
    - <span data-ttu-id="c9c78-142">**Hossz** - *cm*</span><span class="sxs-lookup"><span data-stu-id="c9c78-142">**Length** - *cm*</span></span>
    - <span data-ttu-id="c9c78-143">**Térfogategység** - *cm3*</span><span class="sxs-lookup"><span data-stu-id="c9c78-143">**Volume unit** - *cm3*</span></span>

<span data-ttu-id="c9c78-144">A rendszer automatikusan kiszámítja a **Térfogat** mezőt a **Mélység**, a **Magasság** és a **Szélesség** beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="c9c78-144">The **Volume** field is automatically calculated based on your **Depth**, **Height**, and **Width** settings.</span></span>

#### <a name="create-a-new-container-type"></a><span data-ttu-id="c9c78-145">Új tárolótípus létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9c78-145">Create a new container type</span></span>

<span data-ttu-id="c9c78-146">Lépjen a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolótípusok** lehetőségre, és hozzon létre egy új rekordot a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="c9c78-146">Go to **Warehouse management \> Setup \> Containers \> Container types** and create a new record with the following settings:</span></span>

- <span data-ttu-id="c9c78-147">**Tároló típuskódja** - *Kis méretű doboz*</span><span class="sxs-lookup"><span data-stu-id="c9c78-147">**Container type code** - *Short Box*</span></span>
- <span data-ttu-id="c9c78-148">**Leírás** - *Kis méretű doboz*</span><span class="sxs-lookup"><span data-stu-id="c9c78-148">**Description** - *Short Box*</span></span>
- <span data-ttu-id="c9c78-149">**Maximális nettó tömeg** - *50*</span><span class="sxs-lookup"><span data-stu-id="c9c78-149">**Maximum net weight** - *50*</span></span>
- <span data-ttu-id="c9c78-150">**Térfogat** - *144*</span><span class="sxs-lookup"><span data-stu-id="c9c78-150">**Volume** - *144*</span></span>
- <span data-ttu-id="c9c78-151">**Hossz** - *6*</span><span class="sxs-lookup"><span data-stu-id="c9c78-151">**Length** - *6*</span></span>
- <span data-ttu-id="c9c78-152">**Szélesség** - *6*</span><span class="sxs-lookup"><span data-stu-id="c9c78-152">**Width** - *6*</span></span>
- <span data-ttu-id="c9c78-153">**Magasság** - *4*</span><span class="sxs-lookup"><span data-stu-id="c9c78-153">**Height** - *4*</span></span>

#### <a name="create-a-container-group"></a><span data-ttu-id="c9c78-154">Tárolócsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9c78-154">Create a container group</span></span>

<span data-ttu-id="c9c78-155">Lépjen a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolócsoportok** lehetőségre, és hozzon létre egy új rekordot a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="c9c78-155">Go to **Warehouse management \> Setup \> Containers \> Container groups** and create a new record with the following settings:</span></span>

- <span data-ttu-id="c9c78-156">**Tárolócsoport azonosítója** - *Kis méretű doboz*</span><span class="sxs-lookup"><span data-stu-id="c9c78-156">**Container group ID** - *Short Box*</span></span>
- <span data-ttu-id="c9c78-157">**Leírás** - *Kis méretű doboz*</span><span class="sxs-lookup"><span data-stu-id="c9c78-157">**Description** - *Short Box*</span></span>

<span data-ttu-id="c9c78-158">Adjon hozzá új sort adjon a **Részletek** részhez.</span><span class="sxs-lookup"><span data-stu-id="c9c78-158">Add a new line to the **Details** section.</span></span> <span data-ttu-id="c9c78-159">Állítsa a **Tárolótípus** lehetőséget *Kis méretű doboz* típusúra.</span><span class="sxs-lookup"><span data-stu-id="c9c78-159">Set the **Container type** to *Short Box*.</span></span>

#### <a name="set-up-a-container-build-template"></a><span data-ttu-id="c9c78-160">Tárolóépítési sablon beállítása</span><span class="sxs-lookup"><span data-stu-id="c9c78-160">Set up a container build template</span></span>

<span data-ttu-id="c9c78-161">Lépjen a **Raktárkezelés \> Beállítás \> Tárolók \> Tárolóépítési sablonok** lehetőségre, és válassza ki a **Dobozok** pontot.</span><span class="sxs-lookup"><span data-stu-id="c9c78-161">Go to **Warehouse management \> Setup \> Containers \> Container build templates** and select **Boxes**.</span></span> <span data-ttu-id="c9c78-162">Módosítsa **Tárolócsoport azonosítója** értékét *Kis méretű doboz* értékre.</span><span class="sxs-lookup"><span data-stu-id="c9c78-162">Change the **Container group ID** to *Short Box*.</span></span>

### <a name="run-the-scenario"></a><span data-ttu-id="c9c78-163">Forgatókönyv futtatása</span><span class="sxs-lookup"><span data-stu-id="c9c78-163">Run the scenario</span></span>

<span data-ttu-id="c9c78-164">Miután az előző szakaszban leírtak szerint előkészítette a rendszert, készen áll a forgatókönyv futtatására a következő szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="c9c78-164">After you have prepared your system as described in the previous section, you are ready to run the scenario as described in the next section.</span></span>

#### <a name="create-a-sales-order-and-create-a-shipment"></a><span data-ttu-id="c9c78-165">Értékesítési rendelés létrehozása és szállítmány létrehozása</span><span class="sxs-lookup"><span data-stu-id="c9c78-165">Create a sales order and create a shipment</span></span>

<span data-ttu-id="c9c78-166">Ebben a folyamatban szállítmányt hoz létre a cikk *csomagolási* dimenziói alapján, amelynek magassága 3-nál kisebb.</span><span class="sxs-lookup"><span data-stu-id="c9c78-166">In this process you will create a shipment based on the item *packing* dimensions, for which the height is less than 3.</span></span>

1. <span data-ttu-id="c9c78-167">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c9c78-167">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="c9c78-168">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="c9c78-168">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c9c78-169">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c9c78-169">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c9c78-170">**Vevőkód** *US-001*</span><span class="sxs-lookup"><span data-stu-id="c9c78-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="c9c78-171">**Raktár:** *63*</span><span class="sxs-lookup"><span data-stu-id="c9c78-171">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="c9c78-172">Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.</span><span class="sxs-lookup"><span data-stu-id="c9c78-172">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="c9c78-173">A program megnyitja az új értékesítési rendelést.</span><span class="sxs-lookup"><span data-stu-id="c9c78-173">The new sales order is opened.</span></span> <span data-ttu-id="c9c78-174">Tartalmaznia kell egy új, üres sort az **Értékesítési rendelés sorai** gyorslap rácsán.</span><span class="sxs-lookup"><span data-stu-id="c9c78-174">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="c9c78-175">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c9c78-175">On this line, set the following values:</span></span>

    - <span data-ttu-id="c9c78-176">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="c9c78-176">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="c9c78-177">**Mennyiség:** *5*</span><span class="sxs-lookup"><span data-stu-id="c9c78-177">**Quantity:** *5*</span></span>

1. <span data-ttu-id="c9c78-178">Az **Értékesítési rendelés sorai** gyorslapon válassza a **Készlet \> Foglalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9c78-178">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="c9c78-179">A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a készlet foglalásához.</span><span class="sxs-lookup"><span data-stu-id="c9c78-179">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="c9c78-180">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c9c78-180">Close the page.</span></span>
1. <span data-ttu-id="c9c78-181">A Művelet ablaktáblán nyissa meg a **Raktár** lapot, és válassza a **Kiadás raktárba** parancsot munka létrehozásához a raktár számára.</span><span class="sxs-lookup"><span data-stu-id="c9c78-181">On the Action Pane, open the **Warehouse** tab and select **Release to warehouse** to create work for the warehouse.</span></span>
1. <span data-ttu-id="c9c78-182">Az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Raktár \> Szállítmány részletes adatai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9c78-182">On the **Sales order lines** FastTab, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="c9c78-183">A Művelet ablakban nyissa meg a **Szállítás** lapot, és válassza a **Tárolók megtekintése** elemet.</span><span class="sxs-lookup"><span data-stu-id="c9c78-183">On the Action Pane, open the **Transportation** tab and select **View containers**.</span></span> <span data-ttu-id="c9c78-184">Győződjön meg arról, hogy a cikket a két *Kis méretű doboz* típusú tárolóba rakták.</span><span class="sxs-lookup"><span data-stu-id="c9c78-184">Confirm that the item was containerized into the two *Short Box* containers.</span></span>

#### <a name="place-an-item-into-storage"></a><span data-ttu-id="c9c78-185">Cikk tárolási helyre helyezése</span><span class="sxs-lookup"><span data-stu-id="c9c78-185">Place an item into storage</span></span>

1. <span data-ttu-id="c9c78-186">Nyissa meg a mobileszközt, jelentkezzen be a 63-as raktárba, és lépjen a **Készlet \> Korrigálás be** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c9c78-186">Open the mobile device, sign in to warehouse 63 and go to **Inventory \> Adjust In**.</span></span>
1. <span data-ttu-id="c9c78-187">Írja be a következőt: **Loc** = *SHORT-01*.</span><span class="sxs-lookup"><span data-stu-id="c9c78-187">Enter **Loc** = *SHORT-01*.</span></span> <span data-ttu-id="c9c78-188">Hozzon létre új azonosítótáblát a **Cikk** = *A0001* és a **Mennyiség** = *1 db* értékekkel.</span><span class="sxs-lookup"><span data-stu-id="c9c78-188">Make a new license plate with **Item** = *A0001* and **Quantity** = *1 pcs*.</span></span>
1. <span data-ttu-id="c9c78-189">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c9c78-189">Select **OK**.</span></span> <span data-ttu-id="c9c78-190">Megjelenik a következő hibaüzenet: A SHORT-01 hely sikertelen, mert az A0001 cikk nem fér bele a hely megadott dimenzióiba.</span><span class="sxs-lookup"><span data-stu-id="c9c78-190">You will receive the error "Location SHORT-01 failed because item A0001 does not fit in location's specified dimensions."</span></span> <span data-ttu-id="c9c78-191">Ennek az az oka, hogy a termék *Tárolási* típusának dimenziói nagyobbak, mint a helyprofilban megadott dimenziók.</span><span class="sxs-lookup"><span data-stu-id="c9c78-191">This is because the *Storage* type dimensions of the product are larger than the dimensions specified on the location profile.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]