---
title: Minőség-ellenőrzés
description: Ez a témakör a minőségellenőrzés funkcióról nyújt tájékoztatást. Ez a funkció lehetővé teszi a raktári dolgozók számára, hogy minőséggel kapcsolatos villámellenőrzést végezzenek, miközben átveszik a cikkeket a bejövő dokkoló területen.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c270426a228ac58652f1f60d6fe99d4886071fa6
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621438"
---
# <a name="quality-check"></a><span data-ttu-id="a7498-104">Minőség-ellenőrzés</span><span class="sxs-lookup"><span data-stu-id="a7498-104">Quality check</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7498-105">A *Minőségellenőrzés* funkció lehetővé teszi a raktári dolgozók számára, hogy minőséggel kapcsolatos villámellenőrzést végezzenek, miközben átveszik a cikkeket a bejövő dokkoló területen.</span><span class="sxs-lookup"><span data-stu-id="a7498-105">The *Quality check* feature lets warehouse workers do quick spot checks for quality while they receive items to the inbound dock area.</span></span> <span data-ttu-id="a7498-106">Ezek a villámellenőrzések akkor hasznosak, amikor a dolgozók a csomagolást vagy a cikk más könnyen felismerhető részeit ellenőrzik.</span><span class="sxs-lookup"><span data-stu-id="a7498-106">These spot checks are beneficial when workers inspect packaging or other easily recognizable parts of an item.</span></span> <span data-ttu-id="a7498-107">A funkció útmutatást ad a dolgozókat, hogyan tudják egy pillantással eldönteni, hogy van-e valami szembetűnő hiba vagy sérülés, mielőtt a készletet az eltárolás helyére vinnék.</span><span class="sxs-lookup"><span data-stu-id="a7498-107">The feature guides workers to take a quick look to see whether anything is obviously faulty or damaged before they stock the inventory in its putaway location.</span></span>

<span data-ttu-id="a7498-108">Ez a funkció a szokásos minőségellenőrzési folyamat alternatívája.</span><span class="sxs-lookup"><span data-stu-id="a7498-108">This feature is an alternative to the standard quality check process.</span></span> <span data-ttu-id="a7498-109">Nagyobb rugalmasságot és gyorsabb feldolgozást kínál.</span><span class="sxs-lookup"><span data-stu-id="a7498-109">It offers more flexibility and faster processing.</span></span>

<span data-ttu-id="a7498-110">Amikor ezt a funkciót használja, a következő módon történik az érkezés és a minőség ellenőrzése:</span><span class="sxs-lookup"><span data-stu-id="a7498-110">When you use this feature, the arrival and quality check occur in the following way:</span></span>

1. <span data-ttu-id="a7498-111">Amikor egy szállítmány beérkezik, a raktári dolgozó feljegyzi az érkezést.</span><span class="sxs-lookup"><span data-stu-id="a7498-111">When a shipment arrives, a warehouse worker registers the arrival.</span></span> <span data-ttu-id="a7498-112">A dolgozó beszkenneli a rendszámtáblát a hely regisztrációjához.</span><span class="sxs-lookup"><span data-stu-id="a7498-112">The worker also scans a license plate to register the location.</span></span>
1. <span data-ttu-id="a7498-113">A dolgozó elvégez egy gyors minőségellenőrzést, és feljegyzi az adott rendszámtábla (megfelelt vagy nem felelt meg) eredményét.</span><span class="sxs-lookup"><span data-stu-id="a7498-113">The worker does a quick quality check and records the result (pass or fail) for that license plate.</span></span>
1. <span data-ttu-id="a7498-114">Az alábbi műveletek egyike történik:</span><span class="sxs-lookup"><span data-stu-id="a7498-114">One of the following actions occurs:</span></span>

    - <span data-ttu-id="a7498-115">Ha a minőségellenőrzésen megfelelt, akkor elfogadják a rendszámtáblát, és a szokásos módon egy bevételezési hely irányítják.</span><span class="sxs-lookup"><span data-stu-id="a7498-115">If the quality check is passed, the license plate is accepted and guided to a receiving location, as usual.</span></span>
    - <span data-ttu-id="a7498-116">Ha a minőségellenőrzésen nem felelt meg, akkor elutasítják a rendszámtáblát, és a meglévő eltárolási munkát átirányítják egy másik helyre további ellenőrzés céljából.</span><span class="sxs-lookup"><span data-stu-id="a7498-116">If the quality check is failed, the license plate is rejected, and existing putaway work for it is redirected to an alternate location for further inspection.</span></span> <span data-ttu-id="a7498-117">Létrejön egy új minőségi rendelés.</span><span class="sxs-lookup"><span data-stu-id="a7498-117">A new quality order is created.</span></span> <span data-ttu-id="a7498-118">Ha meg szeretné tekinteni a meg nem felelt minőségellenőrzésből létrehozott minőségi rendelést, menjen a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="a7498-118">To view the quality order that is created from the failed quality check, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="a7498-119">Ezt a folyamatot úgy is be lehet állítani, hogy az összes beolvasott rendszámtábla rögtön a minőségellenőrzési helyre kerüljön át.</span><span class="sxs-lookup"><span data-stu-id="a7498-119">This process can also be set up so that all scanned license plates are immediately diverted to the quality check location.</span></span>

## <a name="turn-on-the-quality-check-feature"></a><span data-ttu-id="a7498-120">A Minőségellenőrzési funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="a7498-120">Turn on the Quality check feature</span></span>

<span data-ttu-id="a7498-121">A funkció használata előtt be kell kapcsolnia a saját rendszerében a *Minőségellenőrzés* funkciót.</span><span class="sxs-lookup"><span data-stu-id="a7498-121">Before you can use the *Quality check* feature, it must be turned on in your system.</span></span> <span data-ttu-id="a7498-122">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="a7498-122">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="a7498-123">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="a7498-123">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="a7498-124">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="a7498-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="a7498-125">**Funkció neve:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-125">**Feature name:** *Quality check*</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="a7498-126">A funkció beállítása a példaforgatókönyvhöz</span><span class="sxs-lookup"><span data-stu-id="a7498-126">Set up the feature for the example scenario</span></span>

<span data-ttu-id="a7498-127">Ez a szakasz iránymutatásokat és egy példát mutat be azzal kapcsolatban, hogy hogyan kell beállítani a *Minőségellenőrzés* funkciót, illetve hogyan kell előkészíteni mintaadatokat a témakörben később bemutatott példaforgatókönyvben.</span><span class="sxs-lookup"><span data-stu-id="a7498-127">This section provides guidelines and an example that shows how to set up the *Quality check* feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="a7498-128">A mintaadatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="a7498-128">Make sample data available</span></span>

<span data-ttu-id="a7498-129">Ha ezt a [példaforgatókönyvet](#example-scenario) az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="a7498-129">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="a7498-130">Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="a7498-130">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="quality-check-template"></a><a name="quality-template"></a><span data-ttu-id="a7498-131">Minőség-ellenőrzési sablon</span><span class="sxs-lookup"><span data-stu-id="a7498-131">Quality check template</span></span>

<span data-ttu-id="a7498-132">A minőségellenőrzési sablon határozza meg, hogy a beérkezéskor milyen szabályok vonatkoznak a minőséggel kapcsolatos villámellenőrzések során.</span><span class="sxs-lookup"><span data-stu-id="a7498-132">The quality check template defines the rules for doing quick spot checks for quality at the time of receiving.</span></span>

1. <span data-ttu-id="a7498-133">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Minőségellenőrzési sablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="a7498-133">Go to **Warehouse management \> Setup \> Work \> Quality check template**.</span></span>
1. <span data-ttu-id="a7498-134">Válassza az **Új** lehetőséget egy sablon rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="a7498-134">Select **New** to add a template to the grid.</span></span>
1. <span data-ttu-id="a7498-135">Állítsa be a következő értékeket az új sablon meghatározásához:</span><span class="sxs-lookup"><span data-stu-id="a7498-135">Set the following values to define the new template:</span></span>

    - <span data-ttu-id="a7498-136">**Minőségellenőrzési sablon neve:** *Dokkellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-136">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="a7498-137">Adjon meg egy nevet, amely azonosítja a sablonhoz alkalmazott szabályokat.</span><span class="sxs-lookup"><span data-stu-id="a7498-137">Enter a name that identifies the policies applied for this template.</span></span>

    - <span data-ttu-id="a7498-138">**Elfogadási irányelv:** *Felhasználó kérése*</span><span class="sxs-lookup"><span data-stu-id="a7498-138">**Acceptance policy:** *Prompt user*</span></span>

        <span data-ttu-id="a7498-139">Határozza meg, hogy a felhasználókat meg kell-e kérni a készlet minőségének elfogadására vagy elutasítsására, vagy a minőséget automatikusan el kell-e utasítani.</span><span class="sxs-lookup"><span data-stu-id="a7498-139">Specify whether users should be prompted to accept or reject the quality of the inventory while they process the work, or whether the quality should automatically be rejected.</span></span> <span data-ttu-id="a7498-140">A választható lehetőségek az *Automatikus elutasítás* és a *Felhasználó kérése*.</span><span class="sxs-lookup"><span data-stu-id="a7498-140">The available options are *Auto reject* and *Prompt user*.</span></span>

    - <span data-ttu-id="a7498-141">**Minőségfeldolgozási irányelv:** *Minőségi rendelés létrehozása*</span><span class="sxs-lookup"><span data-stu-id="a7498-141">**Quality processing policy:** *Create quality order*</span></span>

        <span data-ttu-id="a7498-142">Válassza ki a készlet minőségének elutasításakor használandó irányelvet.</span><span class="sxs-lookup"><span data-stu-id="a7498-142">Select the policy that should be used when the quality of the inventory is rejected.</span></span> <span data-ttu-id="a7498-143">Ehhez a következő lehetőségek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="a7498-143">The following options are available:</span></span>

        - <span data-ttu-id="a7498-144">*Csak munka létrehozása* – Hozzon létre csak munkát a készlet mozgatásának megkönnyítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a7498-144">*Create work only* – Just create work to facilitate inventory movement.</span></span>
        - <span data-ttu-id="a7498-145">*Minőségi rendelés létrehozása* – Hozzon létre minőségi rendelést a minőségi tesztek megkönnyítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a7498-145">*Create quality order* – Create a quality order to facilitate quality tests.</span></span>

    - <span data-ttu-id="a7498-146">**Tesztcsoport:** *Doboz*</span><span class="sxs-lookup"><span data-stu-id="a7498-146">**Test group:** *Enclosure*</span></span>

        <span data-ttu-id="a7498-147">Határozza meg a létrehozott minőségi rendelésben használandó tesztcsoportot.</span><span class="sxs-lookup"><span data-stu-id="a7498-147">Specify the test group that should be used in the quality order that is created.</span></span> <span data-ttu-id="a7498-148">A tesztcsoportok a **Készletkezelés** modulban állíthatók be.</span><span class="sxs-lookup"><span data-stu-id="a7498-148">Test groups are set up in the **Inventory management** module.</span></span>

        <span data-ttu-id="a7498-149">Hagyja kikapcsolva a **Romboló szöveg** lehetőséget a tesztcsoportnál.</span><span class="sxs-lookup"><span data-stu-id="a7498-149">Leave the **Destructive text** option turned off for the test group.</span></span> <span data-ttu-id="a7498-150">Ex a lehetőség határozza meg, hogy a tesztcsoportban szereplő tesztek eredményeként a mintát tönkreteszik-e vagy sem.</span><span class="sxs-lookup"><span data-stu-id="a7498-150">This option defines whether the sample will be destroyed as part of the tests in the test group.</span></span> <span data-ttu-id="a7498-151">Ha egy romboló tesztet használ, a rendszer létrehoz egy készlettranzakciót, ha a cikkhez létrehoznak egy minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="a7498-151">If a destructive test is used, the system generates an inventory transaction when a quality order is created for an item.</span></span> <span data-ttu-id="a7498-152">Az új készlettranzakció előrejelzi mennyiségi teszthez való készlet csökkenését.</span><span class="sxs-lookup"><span data-stu-id="a7498-152">The new inventory transaction predicts the inventory reduction for the test quantity.</span></span> <span data-ttu-id="a7498-153">Készletcsökkenés akkor megy végre, ha a minőségi rendelést az ellenőrzési lépéssel fejezi be.</span><span class="sxs-lookup"><span data-stu-id="a7498-153">The inventory reduction occurs when the quality order is completed through the validation step.</span></span> <span data-ttu-id="a7498-154">A készlettranzakciót minőségi rendelésként azonosítja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="a7498-154">The inventory transaction is identified as a quality order.</span></span>

### <a name="work-class--quality-check"></a><a name="work-class"></a><span data-ttu-id="a7498-155">Munkaosztály – Minőségellenőrzés</span><span class="sxs-lookup"><span data-stu-id="a7498-155">Work class – Quality check</span></span>

<span data-ttu-id="a7498-156">A munkaosztályokkal irányítható és/vagy korlátozható azon munkarendeléssorok típusa, amelyeket a raktári dolgozók feldolgozhatnak egy mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="a7498-156">Work classes are used to direct and/or limit the type of work order lines that warehouse workers can process on a mobile device.</span></span>

1. <span data-ttu-id="a7498-157">Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.</span><span class="sxs-lookup"><span data-stu-id="a7498-157">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="a7498-158">Válassza az **Új** lehetőséget egy munkaosztály létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a7498-158">Select **New** to create a work class.</span></span>
1. <span data-ttu-id="a7498-159">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a7498-159">In the header, set the following values:</span></span>

    - <span data-ttu-id="a7498-160">**Munkaosztály azonosítója:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-160">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="a7498-161">Adjon meg egy nevet, amely azonosítja a munkaosztályt.</span><span class="sxs-lookup"><span data-stu-id="a7498-161">Enter a name that identifies the work class.</span></span>

    - <span data-ttu-id="a7498-162">**Leírás:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-162">**Description:** *QC Check*</span></span>

        <span data-ttu-id="a7498-163">Adjon meg egy rövid leírást, amely jelzi, hogy mire használható a munkaosztály.</span><span class="sxs-lookup"><span data-stu-id="a7498-163">Enter a short description that indicates what the work class is used for.</span></span>

    - <span data-ttu-id="a7498-164">**Munkarendelés típusa:** *Minőség a minőségellenőrzésben*</span><span class="sxs-lookup"><span data-stu-id="a7498-164">**Work order type:** *Quality in quality check*</span></span>

        <span data-ttu-id="a7498-165">Válassza ki, hogy milyen típusú munkarendelést hoz létre a munkaosztály.</span><span class="sxs-lookup"><span data-stu-id="a7498-165">Select the type of work order that is created by the work class.</span></span> <span data-ttu-id="a7498-166">A minőségellenőrzési munka beállításakor mindig válassza a *Minőség a minőségellenőrzésben* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-166">When you set up quality control work, always select *Quality in quality check*.</span></span>

1. <span data-ttu-id="a7498-167">Az **Érvényes betárolási helytípusok** gyorslapon hagyja üresen a **Hely típusa** mezőt.</span><span class="sxs-lookup"><span data-stu-id="a7498-167">On the **Valid put location types** FastTab, leave the **Location type** field blank.</span></span>

    <span data-ttu-id="a7498-168">Ha kiválaszt egy helytípust, akkor korlátozza azon helyeket, ahol a cikkeket a betárolásuk után ki lehet tárolni.</span><span class="sxs-lookup"><span data-stu-id="a7498-168">If you select a location type, you limit the locations where items can be put after they are picked.</span></span> <span data-ttu-id="a7498-169">Akkor használja ezt a mezőt, ha egy helyutasítás a hely feloldására tesz kísérletet, vagy amikor egy raktári dolgozó manuálisan meghatározza a mobileszköz-menüpont helyét.</span><span class="sxs-lookup"><span data-stu-id="a7498-169">This field is used when a location directive tries to resolve the location, or when a warehouse worker manually specifies the location for the mobile device menu item.</span></span>

<span data-ttu-id="a7498-170">A munkaosztályokkal és azok létrehozásával kapcsolatos további tudnivalókat lásd: [Munkaosztály létrehozása](tasks/create-work-class.md).</span><span class="sxs-lookup"><span data-stu-id="a7498-170">For more information about work classes and how to create them, see [Create a work class](tasks/create-work-class.md).</span></span>

### <a name="work-template"></a><span data-ttu-id="a7498-171">Munkasablon</span><span class="sxs-lookup"><span data-stu-id="a7498-171">Work template</span></span>

<span data-ttu-id="a7498-172">A munkasablonokkal megadhatja a műveleteket, amiket el kell végezni a raktárban.</span><span class="sxs-lookup"><span data-stu-id="a7498-172">Work templates let you define the work operations that must be performed in the warehouse.</span></span> <span data-ttu-id="a7498-173">Általában a raktári műveletek két egymást követő műveletből állnak: egy raktári dolgozó felveszi az aktuális készletet az egyik helyen, majd lerakja a készletet egy másik helyen.</span><span class="sxs-lookup"><span data-stu-id="a7498-173">Typically, warehouse work operations consist of a pair of actions: a warehouse worker picks on-hand inventory up in one location and then puts the picked inventory down in another location.</span></span> <span data-ttu-id="a7498-174">A minőségellenőrzés munkasablonja meghatározza a minőségellenőrzések munkafolyamatait.</span><span class="sxs-lookup"><span data-stu-id="a7498-174">A work template for quality control defines the work operations for doing quality checks.</span></span>

#### <a name="purchase-orders"></a><span data-ttu-id="a7498-175">Beszerzési rendelések</span><span class="sxs-lookup"><span data-stu-id="a7498-175">Purchase orders</span></span>

1. <span data-ttu-id="a7498-176">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="a7498-176">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="a7498-177">A fejlécben állítsa át a **Munkarendelés típusa** mezőt *Beszerzési rendelések* értékre.</span><span class="sxs-lookup"><span data-stu-id="a7498-177">In the header, set the **Work order type** field to *Purchase orders*.</span></span>
1. <span data-ttu-id="a7498-178">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-178">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a7498-179">Olyan munkasablonr válasszon ki, amelynek tartalmaznia kell egy minőségellenőrzési lépést.</span><span class="sxs-lookup"><span data-stu-id="a7498-179">Select a work template that should include a quality check step.</span></span> <span data-ttu-id="a7498-180">Válassza az **Áttekintés** szakaszban a **Munkasablon** mezőben lévő *51 Igénylés, beszerzési rendelés* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-180">In the **Overview** section, in the **Work template** field, select *51 PO Receipt*.</span></span>
1. <span data-ttu-id="a7498-181">A **Munkasablon részletei** szakaszban figyelje meg, hogy a rácsnak két meglévő sora van: egy *Kitárolásra* és egy *Eltárolásra*.</span><span class="sxs-lookup"><span data-stu-id="a7498-181">In the **Work template details** section, notice that the grid has two existing lines: one for *Pick* and one for *Put*.</span></span>
1. <span data-ttu-id="a7498-182">A **Munkasablon részletei** szakaszban válassza ki az **Új** lehetőséget,ha a rácshoz hozzá szeretne adni egy sort a minőségellenőrzéshez.</span><span class="sxs-lookup"><span data-stu-id="a7498-182">In the **Work template details** section, select **New** to add a row for quality control to the grid.</span></span> <span data-ttu-id="a7498-183">Figyelje meg, hogy az új sor **Sorszám** mező *3* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="a7498-183">Notice that the **Line number** field for the new line is set to *3*.</span></span>
1. <span data-ttu-id="a7498-184">Az új sorban állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="a7498-184">On the new line, set the following values.</span></span> <span data-ttu-id="a7498-185">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="a7498-185">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="a7498-186">**Munkatípus:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-186">**Work type:** *Quality check*</span></span>
    - <span data-ttu-id="a7498-187">**Munkaosztály azonosítója:** *Beszerzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-187">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="a7498-188">**Minőségellenőrzési sablon neve:** *Dokkellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-188">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="a7498-189">Válasszon egy egyedi azonosítót a munkaosztályhoz.</span><span class="sxs-lookup"><span data-stu-id="a7498-189">Select the unique ID for the work class.</span></span> <span data-ttu-id="a7498-190">Ezt az értéket használja a menüelemek beállítására a mobileszközön, és azon munkatípusok beállításához, amelyeket azok a menüelemek fel tudnak dolgozni.</span><span class="sxs-lookup"><span data-stu-id="a7498-190">You use this value to configure the menu items on the mobile device and the types of work that those menu items can process.</span></span>

1. <span data-ttu-id="a7498-191">A Művelet ablaktáblában válassza a **Mentés** lehetőséget az elvégzett munka mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="a7498-191">On the Action Pane, select **Save** to save your work so far.</span></span>

    <span data-ttu-id="a7498-192">Egy tájékoztató üzenet jelenik meg: „Érvénytelen – A minőségellenőrzésnek közvetlenül a kitárolás után kell következnie”.</span><span class="sxs-lookup"><span data-stu-id="a7498-192">You receive an informational message that states, "Invalid - Quality check must come directly after a pick."</span></span> <span data-ttu-id="a7498-193">Ennek megfelelően módosítania kell az imént hozzáadott sor **Sorszám** értéket.</span><span class="sxs-lookup"><span data-stu-id="a7498-193">Therefore, you must change the **Line number** value for the line that you just added.</span></span>

1. <span data-ttu-id="a7498-194">Az új sor **Sorszám** értékének módosításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="a7498-194">Follow these steps to change the **Line number** value for the new line:</span></span>

    1. <span data-ttu-id="a7498-195">A **Munkasablon részletei** szakaszban válassza ki azt a sort, amelyben a **Munka típusa** mező *Minőségellenőrzés* lehetőségre van állítva.</span><span class="sxs-lookup"><span data-stu-id="a7498-195">In the **Work template details** section, select the line where the **Work type** field is set to *Quality check*.</span></span>
    2. <span data-ttu-id="a7498-196">Válassza a **Feljebb** vagy a **Lentebb** gombra a *Minőségellenőrzés* sor mozgatásához, hogy a *Kitárolás* sor után jöjjön.</span><span class="sxs-lookup"><span data-stu-id="a7498-196">Select the **Move up** or **Move down** button to move the *Quality check* line so that it's after the *Pick* line.</span></span>

1. <span data-ttu-id="a7498-197">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-197">On the Action Pane, select **Save**.</span></span>

#### <a name="quality-in-quality-check"></a><span data-ttu-id="a7498-198">Minőség a minőség-ellenőrzésnél</span><span class="sxs-lookup"><span data-stu-id="a7498-198">Quality in quality check</span></span>

<span data-ttu-id="a7498-199">Ezután hozzon létre egy munkasablont a minőségellenőrzéshez.</span><span class="sxs-lookup"><span data-stu-id="a7498-199">Next, create a work template for the quality check.</span></span>

1. <span data-ttu-id="a7498-200">A **Munkasablonok** lap fejlécében módosítsa a **Munkarendelés típusa** mező értékét a *Minőség a minőségellenőrzésben* lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a7498-200">In the header of the **Work templates** page, change the value of the **Work order type** field to *Quality in quality check*.</span></span>
1. <span data-ttu-id="a7498-201">A Művelet panelen válassza az **Új** lehetőséget egy sor **Áttekintés** szakaszban lévő rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="a7498-201">On the Action Pane, select **New** to add a row to the grid in the **Overview** section.</span></span>
1. <span data-ttu-id="a7498-202">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a7498-202">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a7498-203">**Munkasablon:** *51 Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-203">**Work template:** *51 Quality Check*</span></span>

        <span data-ttu-id="a7498-204">Írja be a sablon nevét.</span><span class="sxs-lookup"><span data-stu-id="a7498-204">Enter a name for the template.</span></span>

    - <span data-ttu-id="a7498-205">**Munkasablon leírása:** *51 Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-205">**Work template description:** *51 Quality Check*</span></span>

1. <span data-ttu-id="a7498-206">A Művelet ablaktáblán a **Mentés** gombra kattintva elérhetővé válik a **Munkasablon részletei** szakasz.</span><span class="sxs-lookup"><span data-stu-id="a7498-206">On the Action Pane, select **Save** to make the **Work template details** section available.</span></span>
1. <span data-ttu-id="a7498-207">Miközben az új sablon még ki van választva az **Áttekintés** szakaszban, válassza az **Új** lehetőséget a **Munkasablon részletei** szakaszban, így hozzáadhat egy sort a sablonban lévő rácshoz.</span><span class="sxs-lookup"><span data-stu-id="a7498-207">While the new template is still selected in the **Overview** section, select **New** in the **Work template details** section to add a row to the grid there.</span></span>
1. <span data-ttu-id="a7498-208">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a7498-208">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a7498-209">**Munka típusa:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="a7498-209">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="a7498-210">**Munkaosztály azonosítója:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-210">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="a7498-211">Válassza ki a [Munkaosztály](#work-class) nevét, amelyet korábban létrehozott a minőségellenőrzési munkához.</span><span class="sxs-lookup"><span data-stu-id="a7498-211">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="a7498-212">A **Munkasablon részletei** szakaszban válassza ki megint az **Új** lehetőséget, ha egy újabb sort szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="a7498-212">In the **Work template details** section, select **New** again to add another row.</span></span>
1. <span data-ttu-id="a7498-213">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a7498-213">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a7498-214">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="a7498-214">**Work type:** *Put*</span></span>
    - <span data-ttu-id="a7498-215">**Munkaosztály azonosítója:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-215">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="a7498-216">Válassza ki a [Munkaosztály](#work-class) nevét, amelyet korábban létrehozott a minőségellenőrzési munkához.</span><span class="sxs-lookup"><span data-stu-id="a7498-216">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="a7498-217">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-217">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="a7498-218">A Munkasablonokkal kapcsolatos további információkat lásd: [A raktári munka ellenőrzése munkasablonok és helyutasítások használatával](control-warehouse-location-directives.md)</span><span class="sxs-lookup"><span data-stu-id="a7498-218">For more information about work templates, see [Control warehouse work by using work templates and location directives](control-warehouse-location-directives.md)</span></span>

### <a name="location-directive--quality-failures"></a><span data-ttu-id="a7498-219">Helyutasítás – Minőségi hibák</span><span class="sxs-lookup"><span data-stu-id="a7498-219">Location directive – Quality failures</span></span>

<span data-ttu-id="a7498-220">A helyutasítások olyan szabályok, amik segítik a kitárolási és betárolási helyek meghatározását, készletmozgatás esetében.</span><span class="sxs-lookup"><span data-stu-id="a7498-220">Location directives are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="a7498-221">Például egy értékesítési rendelés tranzakciójába a helyutasítás azt határozza meg, ahol a cikkek kivétele történik, és ha a kitárolt cikkek kerülnek.</span><span class="sxs-lookup"><span data-stu-id="a7498-221">For example, in a sales order transaction, a location directive determines where the items will be picked and where the picked items will be put.</span></span> <span data-ttu-id="a7498-222">Meg kell adnia egy helyutasítást, amely meghatározza, hogy hogyan kezelje a program a sikertelen minőségellenőrzéseket.</span><span class="sxs-lookup"><span data-stu-id="a7498-222">You must configure a location directive rule to define how failed quality checks will be handled.</span></span>

1. <span data-ttu-id="a7498-223">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="a7498-223">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="a7498-224">A bal oldali ablaktáblában a **Munkarendelés típusa** mezőt állítsa *Beszerzési rendelések* értékre, hogy az adott típusú helyutasításokkal együttműködjön.</span><span class="sxs-lookup"><span data-stu-id="a7498-224">In the left pane, set the **Work order type** field to *Purchase orders* to work with location directives of that type.</span></span>
1. <span data-ttu-id="a7498-225">A művelet ablaktáblán válassza az **Új** parancsot a minőségellenőrzéshez használandó új helyutasítás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a7498-225">On the Action Pane, select **New** to create a location directive for quality checks.</span></span>
1. <span data-ttu-id="a7498-226">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a7498-226">In the header, set the following values:</span></span>

    - <span data-ttu-id="a7498-227">**Sorszám:** Fogadja el az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="a7498-227">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="a7498-228">**Név:** *51 Minőséghez*</span><span class="sxs-lookup"><span data-stu-id="a7498-228">**Name:** *51 To Quality*</span></span>

1. <span data-ttu-id="a7498-229">A **Helyutasítások** gyorslapon állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="a7498-229">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="a7498-230">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="a7498-230">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="a7498-231">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="a7498-231">**Work type:** *Put*</span></span>
    - <span data-ttu-id="a7498-232">**Telephely:** *5*</span><span class="sxs-lookup"><span data-stu-id="a7498-232">**Site:** *5*</span></span>
    - <span data-ttu-id="a7498-233">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="a7498-233">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="a7498-234">A Műveleti ablaktáblán a **Mentés** gombra kattintva mentheti az utasítást, és elérhetővé válik a **Sorok** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="a7498-234">On the Action Pane select **Save** to save your directive and make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="a7498-235">A **Sorok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="a7498-235">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="a7498-236">Az új sorban állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="a7498-236">On the new line, set the following values.</span></span> <span data-ttu-id="a7498-237">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="a7498-237">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="a7498-238">**Kezdő mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="a7498-238">**From quantity:** *1*</span></span>
    - <span data-ttu-id="a7498-239">**Záró mennyiség:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="a7498-239">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="a7498-240">A Műveleti ablaktáblán a **Mentés** gombra kattintva mentheti az új sort, és elérhetővé válik a **Helyutasítás műveletei** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="a7498-240">On the Action Pane, select **Save** to save the new line and make the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="a7498-241">Ha az új sor továbbra is be ki van választva a **Sorok** gyorslapon, akkor a **Helyutasítás műveletei** gyorslap **Új** elemét kiválasztva egy sort adhat a rácshoz, így beállíthat egy műveletet a sorhoz.</span><span class="sxs-lookup"><span data-stu-id="a7498-241">While the new line is still selected on the **Lines** FastTab, select **New** on the **Location directive actions** FastTab to add a row to the grid there, so that you can set up an action for the line.</span></span>
1. <span data-ttu-id="a7498-242">Az új sorban állítsa a **Név** mezőt a *Minőség* értékre.</span><span class="sxs-lookup"><span data-stu-id="a7498-242">In the new row, set the **Name** field to *Quality*.</span></span> <span data-ttu-id="a7498-243">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="a7498-243">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="a7498-244">A Műveleti ablaktáblán a **Mentés** gombra kattintva teheti elérhetővé a **Lekérdezés szerkesztése** gombot a **Helyutasítás műveletei** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="a7498-244">On the Action Pane, select **Save** to make the **Edit query** button on the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="a7498-245">Amíg az imént hozzáadott sor továbbra is ki van jelölve a **Helyutasítás műveletei** gyorslapon, válassza a **Lekérdezés szerkesztése** gombot, hogy megnyíljon egy párbeszédpanel, amelyen szerkesztheti a művelet lekérdezését.</span><span class="sxs-lookup"><span data-stu-id="a7498-245">While the line that you just added is still selected on the **Location directive actions** FastTab, select **Edit query** to open a dialog box where you can edit the query for the action.</span></span>
1. <span data-ttu-id="a7498-246">A **tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="a7498-246">On the **Range** tab, select **Add** to add a row to the query.</span></span>
1. <span data-ttu-id="a7498-247">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a7498-247">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a7498-248">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="a7498-248">**Table:** *Locations*</span></span>
    - <span data-ttu-id="a7498-249">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="a7498-249">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="a7498-250">**Mező:** *Hely*</span><span class="sxs-lookup"><span data-stu-id="a7498-250">**Field:** *Location*</span></span>
    - <span data-ttu-id="a7498-251">**Feltételek:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="a7498-251">**Criteria:** *QMS*</span></span>

    <span data-ttu-id="a7498-252">A *QMS* hely a minőséghez használandó raktári hely.</span><span class="sxs-lookup"><span data-stu-id="a7498-252">The *QMS* location is a warehouse location for quality.</span></span>

1. <span data-ttu-id="a7498-253">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="a7498-253">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="a7498-254">EKkor módosítania kell a beszerzési rendelés helyutasításokat az *51*-es raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="a7498-254">You must now change the sequence of purchase order location directives for warehouse *51*.</span></span> <span data-ttu-id="a7498-255">Mentse az új *51 Minőséghez* helyutasítást, frissítse a lapot, majd válassza ki a helyutasítást a listából.</span><span class="sxs-lookup"><span data-stu-id="a7498-255">Save the new *51 To Quality* location directive, refresh the page, and select the location directive in the list.</span></span> <span data-ttu-id="a7498-256">Ezután a Műveleti ablaktáblán lévő **Feljebb** és **Lejjebb** gombokkal helyezze át a helyutasítást az *51*-es raktárhoz a következő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="a7498-256">Then use the **Move up** and **Move down** buttons on the Action Pane to put the location directive for warehouse *51* in the following order.</span></span> <span data-ttu-id="a7498-257">(Mielőtt kiválasztja a **Feljebb** vagy **Lejjebb** gombot, ki kell választania egy helyutasítást a listából.)</span><span class="sxs-lookup"><span data-stu-id="a7498-257">(Before you select **Move up** or **Move down**, you must select a location directive in the list.)</span></span>

    1. <span data-ttu-id="a7498-258">51 Minőséghez</span><span class="sxs-lookup"><span data-stu-id="a7498-258">51 To Quality</span></span>
    2. <span data-ttu-id="a7498-259">51 közvetlen beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="a7498-259">51 PO Direct</span></span>
    3. <span data-ttu-id="a7498-260">51 QMS</span><span class="sxs-lookup"><span data-stu-id="a7498-260">51 QMS</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="a7498-261">Mobileszköz menüpontjai</span><span class="sxs-lookup"><span data-stu-id="a7498-261">Mobile device menu items</span></span>

<span data-ttu-id="a7498-262">A menüelemet úgy konfigurálhatja, hogy a mobileszköz végre tudja hajtani a **Minőségellenőrzés** funkciót.</span><span class="sxs-lookup"><span data-stu-id="a7498-262">Configure a menu item so that mobile devices can perform the **Quality Check** function.</span></span>

#### <a name="purchase-putaway"></a><span data-ttu-id="a7498-263">Beszerzés betárolása</span><span class="sxs-lookup"><span data-stu-id="a7498-263">Purchase putaway</span></span>

1. <span data-ttu-id="a7498-264">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="a7498-264">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="a7498-265">Válassza ki a listából a **Beszerzés eltárolása** menüelemet.</span><span class="sxs-lookup"><span data-stu-id="a7498-265">In the list, select the **Purchase put-away** menu item.</span></span>
1. <span data-ttu-id="a7498-266">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-266">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a7498-267">A **Munkaosztályok** szakaszban válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="a7498-267">In the **Work classes** section, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="a7498-268">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a7498-268">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a7498-269">**Munkaosztály azonosítója:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a7498-269">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="a7498-270">Adja meg a [Munkaosztály](#work-class) nevét, amelyet korábban létrehozott a minőségellenőrzési munkához.</span><span class="sxs-lookup"><span data-stu-id="a7498-270">Enter the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

    - <span data-ttu-id="a7498-271">**Munkarendelés típusa:** *Minőség a minőségellenőrzésben*</span><span class="sxs-lookup"><span data-stu-id="a7498-271">**Work order type:** *Quality in quality check*</span></span>

1. <span data-ttu-id="a7498-272">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-272">On the Action Pane, select **Save**.</span></span>

#### <a name="purchase-order-line-receiving"></a><span data-ttu-id="a7498-273">Beszerzésirendelés-sor bevételezése</span><span class="sxs-lookup"><span data-stu-id="a7498-273">Purchase order line receiving</span></span>

1. <span data-ttu-id="a7498-274">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="a7498-274">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="a7498-275">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="a7498-275">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a7498-276">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a7498-276">In the header, set the following values:</span></span>

    - <span data-ttu-id="a7498-277">**Menüelem neve:** *Beszerzési rendelési sor bevételezése*</span><span class="sxs-lookup"><span data-stu-id="a7498-277">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="a7498-278">**Cím:** *Beszerzési rendelési sor bevételezése*</span><span class="sxs-lookup"><span data-stu-id="a7498-278">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="a7498-279">**Mód:** *Munka*</span><span class="sxs-lookup"><span data-stu-id="a7498-279">**Mode:** *Work*</span></span>
    - <span data-ttu-id="a7498-280">**Meglévő munka használata:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="a7498-280">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="a7498-281">Az **Általános** gyorslapon állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="a7498-281">On the **General** FastTab, set the following values.</span></span> <span data-ttu-id="a7498-282">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="a7498-282">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="a7498-283">**Munkalétrehozási folyamat:** *Beszerzési rendelési sor bevételezése és eltárolása*</span><span class="sxs-lookup"><span data-stu-id="a7498-283">**Work creation process:** *Purchase order line receiving and put away*</span></span>
    - <span data-ttu-id="a7498-284">**Azonosítótábla létrehozása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="a7498-284">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="a7498-285">**Munkasablon:** *51 Igénylés, beszerzési rendelés*</span><span class="sxs-lookup"><span data-stu-id="a7498-285">**Work template:** *51 PO Receipt*</span></span>

1. <span data-ttu-id="a7498-286">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-286">On the Action Pane, select **Save**.</span></span>

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="a7498-287">A menüelem hozzáadása a mobileszköz menühöz</span><span class="sxs-lookup"><span data-stu-id="a7498-287">Add the menu item to a mobile device menu</span></span>

1. <span data-ttu-id="a7498-288">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.</span><span class="sxs-lookup"><span data-stu-id="a7498-288">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="a7498-289">A bal oldali ablaktáblán válassza a **Bejövő** menüt.</span><span class="sxs-lookup"><span data-stu-id="a7498-289">In the left pane, select the **Inbound** menu.</span></span>
1. <span data-ttu-id="a7498-290">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-290">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a7498-291">A **Rendelkezésre álló menük és menüelemek** oszlopban keresse meg és válassza ki az új **Beszerzési rendelési sor bevételezése** menüelemet.</span><span class="sxs-lookup"><span data-stu-id="a7498-291">In the **Available menus and menu items** column, select the new **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="a7498-292">Válassza a jobbra mutató nyilat a **Beszerzési rendelési sor bevételezése** áthelyezéséhez a **Menü struktúrája** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="a7498-292">Select the right arrow button to move **PO line receiving** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="a7498-293">A **Menü szerkezete** oszlopban válassza ki a **Beszerzési rendelési sor bevételezése** lehetőséget, majd a feljebb vagy lejjebb nyílra kattintva helyezze át a menüelemet a mobileszköz menüjének kívánt pontjára.</span><span class="sxs-lookup"><span data-stu-id="a7498-293">In the **Menu structure** column, select **PO line receiving**, and then select the up arrow or down arrow button to move the menu item to the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="a7498-294">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-294">On the Action Pane, select **Save**.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="a7498-295">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="a7498-295">Example scenario</span></span>

<span data-ttu-id="a7498-296">Miután elvégezte az összes korábban leírt mintaadatok elérhetővé tételét és beállítását, a forgatókönyvön keresztül kipróbálhatja a *Minőségellenőrzés* funkciót.</span><span class="sxs-lookup"><span data-stu-id="a7498-296">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Quality check* feature.</span></span> <span data-ttu-id="a7498-297">Az ebben a forgatókönyvben látható értékek feltételezik, hogy azokkal a szokásos bemutatóadatokkal dolgozik, amelyeket az **USMF** jogi személyt kiválasztott, és hogy előkészítette a témakör korábbi részében ismertetett mintarekordokat.</span><span class="sxs-lookup"><span data-stu-id="a7498-297">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="a7498-298">Ez a forgatókönyv példaként is szolgál, amely megmutatja, hogyan használható a funkció az üzemelési beállításban.</span><span class="sxs-lookup"><span data-stu-id="a7498-298">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="a7498-299">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="a7498-299">Create a purchase order</span></span>

1. <span data-ttu-id="a7498-300">Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="a7498-300">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="a7498-301">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="a7498-301">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a7498-302">Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a7498-302">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a7498-303">**Szállítói számla:** *104*</span><span class="sxs-lookup"><span data-stu-id="a7498-303">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="a7498-304">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="a7498-304">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="a7498-305">Válassza az **OK** gombot a párbeszédpanel bezárásához, és egy új beszerzési rendelés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a7498-305">Select **OK** to close the dialog box and open the new purchase order.</span></span>
1. <span data-ttu-id="a7498-306">A **Beszerzési rendelés sorai** gyorslapon a rács egy új, üres sort tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="a7498-306">On the **Purchase order lines** FastTab, the grid contains a new, blank line.</span></span> <span data-ttu-id="a7498-307">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a7498-307">On this line, set the following values:</span></span>

    - <span data-ttu-id="a7498-308">**Cikkszám:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="a7498-308">**Item number:** *M9203*</span></span>
    - <span data-ttu-id="a7498-309">**Mennyiség:** *3*</span><span class="sxs-lookup"><span data-stu-id="a7498-309">**Quantity:** *3*</span></span>
    - <span data-ttu-id="a7498-310">**Egység:** *PL*</span><span class="sxs-lookup"><span data-stu-id="a7498-310">**Unit:** *PL*</span></span>

1. <span data-ttu-id="a7498-311">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-311">On the Action Pane, select **Save**.</span></span>

### <a name="process-quality-check-receiving"></a><span data-ttu-id="a7498-312">Folyamat minőségellenőrzési bevételezése</span><span class="sxs-lookup"><span data-stu-id="a7498-312">Process quality check receiving</span></span>

<span data-ttu-id="a7498-313">A beszerzési rendelés létrehozása után a program a **Beszerzési rendelési sor bevételezése** menüelem és a *Minőségellenőrzés* funkció használatával szerezheti be.</span><span class="sxs-lookup"><span data-stu-id="a7498-313">After the purchase order has been created, it can be received by using the **PO line receiving** menu item and the functionality of the *Quality check* feature.</span></span>

#### <a name="receive-pallet-1"></a><span data-ttu-id="a7498-314">1. raklap fogadása</span><span class="sxs-lookup"><span data-stu-id="a7498-314">Receive pallet 1</span></span>

1. <span data-ttu-id="a7498-315">Jelentkezzen be az *51*-es raktár felhasználójaként a raktár alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a7498-315">Sign in to the warehouse app as a user for warehouse *51*.</span></span> <span data-ttu-id="a7498-316">(Írja be a felhasználói azonosítóhoz a *51*-et, a jelszóhoz pedig az *1*-et.)</span><span class="sxs-lookup"><span data-stu-id="a7498-316">(Enter *51* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="a7498-317">Menjen a **Bejövő \> Beszerzési rendelési sor bevételezése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a7498-317">Go to **Inbound \> PO line receiving**.</span></span>
1. <span data-ttu-id="a7498-318">A **PONUM** mezőbe adja meg a beszerzési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="a7498-318">In the **PONUM** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="a7498-319">Erősítse meg újra a beszerzési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="a7498-319">Confirm the purchase order number.</span></span>
1. <span data-ttu-id="a7498-320">A **LINENUM** mezőbe adja meg a bevételezett beszerzési rendelés sorszámát.</span><span class="sxs-lookup"><span data-stu-id="a7498-320">In the **LINENUM** field, enter the number of the purchase order line that is being received.</span></span> <span data-ttu-id="a7498-321">Mivel a rendelésnek ebben a forgatókönyvben csak egy sora van, ezért a **LINENUM** mezőbe az *1*-es értéket kell beírnia mindegyik bevételezési lépésnél.</span><span class="sxs-lookup"><span data-stu-id="a7498-321">Because the order has only one line in this scenario, you will enter *1* in the **LINENUM** field for each receiving step.</span></span>
1. <span data-ttu-id="a7498-322">A sor számának megerősítése.</span><span class="sxs-lookup"><span data-stu-id="a7498-322">Confirm the line number.</span></span>
1. <span data-ttu-id="a7498-323">A **Mennyiség** mezőbe írja be a bevételezett mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-323">In the **QTY** field, enter the quantity to receive.</span></span> <span data-ttu-id="a7498-324">Mivel ebben a forgatókönyvben a beszerzési rendelés három raklapra (*PL*) szól, és három bevételezési lépés van, ezért az *1*-es értéket kell megadnia a **MENNYISÉG** mezőben minden egyes bevételezési lépésnél.</span><span class="sxs-lookup"><span data-stu-id="a7498-324">Because the purchase order is for three pallets (*PL*) in this scenario, and there are three receiving steps, you will enter *1* in the **QTY** field for each receiving step.</span></span>
1. <span data-ttu-id="a7498-325">Nyugtázza a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-325">Confirm the quantity.</span></span>

    <span data-ttu-id="a7498-326">A megjelenő **Minőségellenőrzés** lap nem tartalmaz bejegyzési mezőket.</span><span class="sxs-lookup"><span data-stu-id="a7498-326">The **Quality check** page that appears has no entry fields.</span></span> <span data-ttu-id="a7498-327">Csak a megerősítés (pipa) gombot alul, és a Menü gombot (**≡**) felül.</span><span class="sxs-lookup"><span data-stu-id="a7498-327">It has only the confirmation (check mark) button at the bottom and the Menu button (**≡**) at the top.</span></span> <span data-ttu-id="a7498-328">(A Menü gombot néha hamburgernek vagy a hamburger gombnak is nevezik.) A minőségellenőrzési folyamat meggyorsításához – amikor a raklap átmegy a minőségellenőrzésen – a felhasználónak csak meg kell erősítenie a **Minőségellenőrzés** lapot.</span><span class="sxs-lookup"><span data-stu-id="a7498-328">(The Menu button is sometimes referred to as the hamburger or the hamburger button.) To expedite the quality check process, when the pallet passes the quality check, the user just confirms the **Quality check** page.</span></span>

    <span data-ttu-id="a7498-329">![Minőségellenőrzés lap](media/quality-check.png "Minőségellenőrzés lap")</span><span class="sxs-lookup"><span data-stu-id="a7498-329">![Quality check page](media/quality-check.png "Quality check page")</span></span>

1. <span data-ttu-id="a7498-330">Válassza ki a megerősítés gombot, ha az 1. sorban lévő 1. raklap átment a minőségellenőrzésen.</span><span class="sxs-lookup"><span data-stu-id="a7498-330">Select the confirmation button to pass the quality check for pallet 1 from line 1.</span></span>

    <span data-ttu-id="a7498-331">A megjelenő **Beszerzési rendelések: Eltárolás** lap az eltárolási munka részleteit jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="a7498-331">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="a7498-332">**LOC:** A rendszer által meghatározott hely</span><span class="sxs-lookup"><span data-stu-id="a7498-332">**LOC:** The system determined location</span></span>

        <span data-ttu-id="a7498-333">Ez a hely a beszerzési rendelés bevételezéséhez megadott eltárolási hely.</span><span class="sxs-lookup"><span data-stu-id="a7498-333">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="a7498-334">**LP:** A rendszer által létrehozott azonosítótábla azonosítója</span><span class="sxs-lookup"><span data-stu-id="a7498-334">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="a7498-335">**Cikk:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="a7498-335">**Item:** *M9203*</span></span>
    - <span data-ttu-id="a7498-336">**Mennyiség:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="a7498-336">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="a7498-337">A cíkk leírása is itt látható.</span><span class="sxs-lookup"><span data-stu-id="a7498-337">The item description is also shown.</span></span>

1. <span data-ttu-id="a7498-338">Erősítse meg a betárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="a7498-338">Confirm the putaway work.</span></span>

    <span data-ttu-id="a7498-339">A beszerzési rendeléssor **Feladat** lapján a „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a7498-339">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="a7498-340">A **LINENUM** mező elérhető, úgyhogy fogadhatja a következő raklapot.</span><span class="sxs-lookup"><span data-stu-id="a7498-340">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

#### <a name="receive-pallet-2"></a><span data-ttu-id="a7498-341">2. raklap fogadása</span><span class="sxs-lookup"><span data-stu-id="a7498-341">Receive pallet 2</span></span>

<span data-ttu-id="a7498-342">Ennél a forgatókönyvnél a 2. raklapot el fogja utasítani a program.</span><span class="sxs-lookup"><span data-stu-id="a7498-342">For this scenario, pallet 2 will be rejected.</span></span>

1. <span data-ttu-id="a7498-343">A **LINENUM** mezőbe írja be az *1* értéket , majd erősítse meg a sor számát.</span><span class="sxs-lookup"><span data-stu-id="a7498-343">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="a7498-344">A **MENNYISÉG** mező mostantól elérhető.</span><span class="sxs-lookup"><span data-stu-id="a7498-344">The **QTY** field is now available.</span></span> <span data-ttu-id="a7498-345">Adja meg az *1* értéket, majd erősítse meg a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-345">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="a7498-346">Megjelenik a **Minőségellenőrzés** oldal.</span><span class="sxs-lookup"><span data-stu-id="a7498-346">The **Quality check** page appears.</span></span> <span data-ttu-id="a7498-347">Ezen nyugta esetében a raklapot elutasítja a program a minősége miatt, és a *QMS* minőséghelyre kerül.</span><span class="sxs-lookup"><span data-stu-id="a7498-347">For this receipt, the pallet will be rejected for quality, and it will be put into the *QMS* quality location.</span></span>

1. <span data-ttu-id="a7498-348">Válassza ki a lap tetején látható Menü gombot (**≡**), majd válassza az **Elutasítás** lehetőséget a menüben.</span><span class="sxs-lookup"><span data-stu-id="a7498-348">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Reject**.</span></span>
1. <span data-ttu-id="a7498-349">A megjelenő **Feladat** oldalon adja meg a **QMS** éréket, mint *Betárolási* helyet, hogy a raklapot elküldhesse további ellenőrzésre.</span><span class="sxs-lookup"><span data-stu-id="a7498-349">On the **Task** page that appears, enter **QMS** as the *Put* location to send the pallet to for further inspection.</span></span>

    <span data-ttu-id="a7498-350">A megjelenő **Minőség a minőségellenőrzésben: Eltárolás** lap az eltárolási munka részleteit jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="a7498-350">The **Quality in quality check: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="a7498-351">**LOC:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="a7498-351">**LOC:** *QMS*</span></span>

        <span data-ttu-id="a7498-352">Ez a hely az elutasított minőség bevételezéséhez megadott eltárolási hely.</span><span class="sxs-lookup"><span data-stu-id="a7498-352">This location is the designated putaway location for rejected quality receiving.</span></span>

    - <span data-ttu-id="a7498-353">**LP:** A rendszer által létrehozott azonosítótábla azonosítója</span><span class="sxs-lookup"><span data-stu-id="a7498-353">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="a7498-354">**Cikk:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="a7498-354">**Item:** *M9203*</span></span>
    - <span data-ttu-id="a7498-355">**Mennyiség:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="a7498-355">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="a7498-356">A cíkk leírása is itt látható.</span><span class="sxs-lookup"><span data-stu-id="a7498-356">The item description is also shown.</span></span>

1. <span data-ttu-id="a7498-357">Erősítse meg a betárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="a7498-357">Confirm the putaway work.</span></span>

    <span data-ttu-id="a7498-358">A beszerzési rendeléssor **Feladat** lapján a „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a7498-358">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="a7498-359">A **LINENUM** mező elérhető, úgyhogy fogadhatja a következő raklapot.</span><span class="sxs-lookup"><span data-stu-id="a7498-359">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

<span data-ttu-id="a7498-360">Ezennel befejezte a minőségellenőrzést, és létrehozta a minőségi rendelést az elutasított raklaphoz.</span><span class="sxs-lookup"><span data-stu-id="a7498-360">You've now completed the quality check and created a quality order for the rejected pallet.</span></span> <span data-ttu-id="a7498-361">Ha meg szeretné tekinteni a létrehozott minőségi rendelést, menjen a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="a7498-361">To view the order that was created, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="a7498-362">A minőségi rendelés tesztelése most már feldolgozható.</span><span class="sxs-lookup"><span data-stu-id="a7498-362">Quality order testing can now be processed.</span></span> <span data-ttu-id="a7498-363">Ebben a témakörben nem szerepel minőségi tesztelés.</span><span class="sxs-lookup"><span data-stu-id="a7498-363">Quality testing isn't covered in this topic.</span></span>

<span data-ttu-id="a7498-364">A minőségkezeléssel kapcsolatos további tudnivalókat lásd: [Minőségkezelés áttekintése](../inventory/enable-quality-management.md)</span><span class="sxs-lookup"><span data-stu-id="a7498-364">For more information about quality management, see [Quality management overview](../inventory/enable-quality-management.md)</span></span>

#### <a name="receive-pallet-3"></a><span data-ttu-id="a7498-365">3. raklap fogadása</span><span class="sxs-lookup"><span data-stu-id="a7498-365">Receive pallet 3</span></span>

<span data-ttu-id="a7498-366">Ennél a forgatókönyvnél a 3. raklapot el fogja fogadni a program.</span><span class="sxs-lookup"><span data-stu-id="a7498-366">For this scenario, pallet 3 will be accepted.</span></span>

1. <span data-ttu-id="a7498-367">A **LINENUM** mezőbe írja be az *1* értéket , majd erősítse meg a sor számát.</span><span class="sxs-lookup"><span data-stu-id="a7498-367">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="a7498-368">A **MENNYISÉG** mező mostantól elérhető.</span><span class="sxs-lookup"><span data-stu-id="a7498-368">The **QTY** field is now available.</span></span> <span data-ttu-id="a7498-369">Adja meg az *1* értéket, majd erősítse meg a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="a7498-369">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="a7498-370">Megjelenik a **Minőségellenőrzés** oldal.</span><span class="sxs-lookup"><span data-stu-id="a7498-370">The **Quality check** page appears.</span></span> <span data-ttu-id="a7498-371">Ezen nyugta esetében a raklapot el fogja fogadni a program a minősége miatt, és egy ömlesztett eltárolási helyre kerül.</span><span class="sxs-lookup"><span data-stu-id="a7498-371">For this receipt, the pallet will be accepted for quality, and it will be put into a bulk putaway location.</span></span>

1. <span data-ttu-id="a7498-372">Válassza ki a megerősítés gombot, ha átment a minőségellenőrzésen.</span><span class="sxs-lookup"><span data-stu-id="a7498-372">Select the confirmation button to pass the quality check.</span></span>

    <span data-ttu-id="a7498-373">A megjelenő **Beszerzési rendelések: Eltárolás** lap az eltárolási munka részleteit jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="a7498-373">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="a7498-374">**LOC:** A rendszer által meghatározott hely</span><span class="sxs-lookup"><span data-stu-id="a7498-374">**LOC:** The system determined location</span></span>

        <span data-ttu-id="a7498-375">Ez a hely a beszerzési rendelés bevételezéséhez megadott eltárolási hely.</span><span class="sxs-lookup"><span data-stu-id="a7498-375">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="a7498-376">**LP:** A rendszer által létrehozott azonosítótábla azonosítója</span><span class="sxs-lookup"><span data-stu-id="a7498-376">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="a7498-377">**Cikk:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="a7498-377">**Item:** *M9203*</span></span>
    - <span data-ttu-id="a7498-378">**Mennyiség:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="a7498-378">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="a7498-379">A cíkk leírása is itt látható.</span><span class="sxs-lookup"><span data-stu-id="a7498-379">The item description is also shown.</span></span>

1. <span data-ttu-id="a7498-380">Erősítse meg a betárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="a7498-380">Confirm the putaway work.</span></span>

    <span data-ttu-id="a7498-381">A beszerzési rendeléssor **Feladat** lapján a „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a7498-381">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="a7498-382">A **LINENUM** mező elérhető, úgyhogy fogadhatja a következő raklapot.</span><span class="sxs-lookup"><span data-stu-id="a7498-382">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

1. <span data-ttu-id="a7498-383">Válassza ki a lap tetején látható Menü gombot (**≡**), majd válassza a **Mégsem** lehetőséget a menühöz való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="a7498-383">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Cancel** to return to the menu.</span></span>

<span data-ttu-id="a7498-384">Most már bezárhatja a mobilalkalmazást.</span><span class="sxs-lookup"><span data-stu-id="a7498-384">You can now close the mobile app.</span></span>
