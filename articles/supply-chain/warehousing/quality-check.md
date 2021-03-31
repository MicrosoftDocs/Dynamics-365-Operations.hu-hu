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
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 31afcfcb9d8dbb91f4ea4e3e7a7282c2a87328d4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228465"
---
# <a name="quality-check"></a><span data-ttu-id="a336d-104">Minőség-ellenőrzés</span><span class="sxs-lookup"><span data-stu-id="a336d-104">Quality check</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a336d-105">A *Minőségellenőrzés* funkció lehetővé teszi a raktári dolgozók számára, hogy minőséggel kapcsolatos villámellenőrzést végezzenek, miközben átveszik a cikkeket a bejövő dokkoló területen.</span><span class="sxs-lookup"><span data-stu-id="a336d-105">The *Quality check* feature lets warehouse workers do quick spot checks for quality while they receive items to the inbound dock area.</span></span> <span data-ttu-id="a336d-106">Ezek a villámellenőrzések akkor hasznosak, amikor a dolgozók a csomagolást vagy a cikk más könnyen felismerhető részeit ellenőrzik.</span><span class="sxs-lookup"><span data-stu-id="a336d-106">These spot checks are beneficial when workers inspect packaging or other easily recognizable parts of an item.</span></span> <span data-ttu-id="a336d-107">A funkció útmutatást ad a dolgozókat, hogyan tudják egy pillantással eldönteni, hogy van-e valami szembetűnő hiba vagy sérülés, mielőtt a készletet az eltárolás helyére vinnék.</span><span class="sxs-lookup"><span data-stu-id="a336d-107">The feature guides workers to take a quick look to see whether anything is obviously faulty or damaged before they stock the inventory in its putaway location.</span></span>

<span data-ttu-id="a336d-108">Ez a funkció a szokásos minőségellenőrzési folyamat alternatívája.</span><span class="sxs-lookup"><span data-stu-id="a336d-108">This feature is an alternative to the standard quality check process.</span></span> <span data-ttu-id="a336d-109">Nagyobb rugalmasságot és gyorsabb feldolgozást kínál.</span><span class="sxs-lookup"><span data-stu-id="a336d-109">It offers more flexibility and faster processing.</span></span>

<span data-ttu-id="a336d-110">Amikor ezt a funkciót használja, a következő módon történik az érkezés és a minőség ellenőrzése:</span><span class="sxs-lookup"><span data-stu-id="a336d-110">When you use this feature, the arrival and quality check occur in the following way:</span></span>

1. <span data-ttu-id="a336d-111">Amikor egy szállítmány beérkezik, a raktári dolgozó feljegyzi az érkezést.</span><span class="sxs-lookup"><span data-stu-id="a336d-111">When a shipment arrives, a warehouse worker registers the arrival.</span></span> <span data-ttu-id="a336d-112">A dolgozó beszkenneli a rendszámtáblát a hely regisztrációjához.</span><span class="sxs-lookup"><span data-stu-id="a336d-112">The worker also scans a license plate to register the location.</span></span>
1. <span data-ttu-id="a336d-113">A dolgozó elvégez egy gyors minőségellenőrzést, és feljegyzi az adott rendszámtábla (megfelelt vagy nem felelt meg) eredményét.</span><span class="sxs-lookup"><span data-stu-id="a336d-113">The worker does a quick quality check and records the result (pass or fail) for that license plate.</span></span>
1. <span data-ttu-id="a336d-114">Az alábbi műveletek egyike történik:</span><span class="sxs-lookup"><span data-stu-id="a336d-114">One of the following actions occurs:</span></span>

    - <span data-ttu-id="a336d-115">Ha a minőségellenőrzésen megfelelt, akkor elfogadják a rendszámtáblát, és a szokásos módon egy bevételezési hely irányítják.</span><span class="sxs-lookup"><span data-stu-id="a336d-115">If the quality check is passed, the license plate is accepted and guided to a receiving location, as usual.</span></span>
    - <span data-ttu-id="a336d-116">Ha a minőségellenőrzésen nem felelt meg, akkor elutasítják a rendszámtáblát, és a meglévő eltárolási munkát átirányítják egy másik helyre további ellenőrzés céljából.</span><span class="sxs-lookup"><span data-stu-id="a336d-116">If the quality check is failed, the license plate is rejected, and existing putaway work for it is redirected to an alternate location for further inspection.</span></span> <span data-ttu-id="a336d-117">Létrejön egy új minőségi rendelés.</span><span class="sxs-lookup"><span data-stu-id="a336d-117">A new quality order is created.</span></span> <span data-ttu-id="a336d-118">Ha meg szeretné tekinteni a meg nem felelt minőségellenőrzésből létrehozott minőségi rendelést, menjen a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="a336d-118">To view the quality order that is created from the failed quality check, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="a336d-119">Ezt a folyamatot úgy is be lehet állítani, hogy az összes beolvasott rendszámtábla rögtön a minőségellenőrzési helyre kerüljön át.</span><span class="sxs-lookup"><span data-stu-id="a336d-119">This process can also be set up so that all scanned license plates are immediately diverted to the quality check location.</span></span>

## <a name="turn-on-the-quality-check-feature"></a><span data-ttu-id="a336d-120">A Minőségellenőrzési funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="a336d-120">Turn on the Quality check feature</span></span>

<span data-ttu-id="a336d-121">A funkció használata előtt be kell kapcsolnia a saját rendszerében a *Minőségellenőrzés* funkciót.</span><span class="sxs-lookup"><span data-stu-id="a336d-121">Before you can use the *Quality check* feature, it must be turned on in your system.</span></span> <span data-ttu-id="a336d-122">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="a336d-122">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="a336d-123">A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="a336d-123">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="a336d-124">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="a336d-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="a336d-125">**Funkció neve:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-125">**Feature name:** *Quality check*</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="a336d-126">A funkció beállítása a példaforgatókönyvhöz</span><span class="sxs-lookup"><span data-stu-id="a336d-126">Set up the feature for the example scenario</span></span>

<span data-ttu-id="a336d-127">Ez a szakasz iránymutatásokat és egy példát mutat be azzal kapcsolatban, hogy hogyan kell beállítani a *Minőségellenőrzés* funkciót, illetve hogyan kell előkészíteni mintaadatokat a témakörben később bemutatott példaforgatókönyvben.</span><span class="sxs-lookup"><span data-stu-id="a336d-127">This section provides guidelines and an example that shows how to set up the *Quality check* feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="a336d-128">A mintaadatok elérhetővé tétele</span><span class="sxs-lookup"><span data-stu-id="a336d-128">Make sample data available</span></span>

<span data-ttu-id="a336d-129">Ha ezt a [példaforgatókönyvet](#example-scenario) az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [bemutatóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak.</span><span class="sxs-lookup"><span data-stu-id="a336d-129">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="a336d-130">Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.</span><span class="sxs-lookup"><span data-stu-id="a336d-130">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="quality-check-template"></a><a name="quality-template"></a><span data-ttu-id="a336d-131">Minőség-ellenőrzési sablon</span><span class="sxs-lookup"><span data-stu-id="a336d-131">Quality check template</span></span>

<span data-ttu-id="a336d-132">A minőségellenőrzési sablon határozza meg, hogy a beérkezéskor milyen szabályok vonatkoznak a minőséggel kapcsolatos villámellenőrzések során.</span><span class="sxs-lookup"><span data-stu-id="a336d-132">The quality check template defines the rules for doing quick spot checks for quality at the time of receiving.</span></span>

1. <span data-ttu-id="a336d-133">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Minőségellenőrzési sablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="a336d-133">Go to **Warehouse management \> Setup \> Work \> Quality check template**.</span></span>
1. <span data-ttu-id="a336d-134">Válassza az **Új** lehetőséget egy sablon rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="a336d-134">Select **New** to add a template to the grid.</span></span>
1. <span data-ttu-id="a336d-135">Állítsa be a következő értékeket az új sablon meghatározásához:</span><span class="sxs-lookup"><span data-stu-id="a336d-135">Set the following values to define the new template:</span></span>

    - <span data-ttu-id="a336d-136">**Minőségellenőrzési sablon neve:** *Dokkellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-136">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="a336d-137">Adjon meg egy nevet, amely azonosítja a sablonhoz alkalmazott szabályokat.</span><span class="sxs-lookup"><span data-stu-id="a336d-137">Enter a name that identifies the policies applied for this template.</span></span>

    - <span data-ttu-id="a336d-138">**Elfogadási irányelv:** *Felhasználó kérése*</span><span class="sxs-lookup"><span data-stu-id="a336d-138">**Acceptance policy:** *Prompt user*</span></span>

        <span data-ttu-id="a336d-139">Határozza meg, hogy a felhasználókat meg kell-e kérni a készlet minőségének elfogadására vagy elutasítsására, vagy a minőséget automatikusan el kell-e utasítani.</span><span class="sxs-lookup"><span data-stu-id="a336d-139">Specify whether users should be prompted to accept or reject the quality of the inventory while they process the work, or whether the quality should automatically be rejected.</span></span> <span data-ttu-id="a336d-140">A választható lehetőségek az *Automatikus elutasítás* és a *Felhasználó kérése*.</span><span class="sxs-lookup"><span data-stu-id="a336d-140">The available options are *Auto reject* and *Prompt user*.</span></span>

    - <span data-ttu-id="a336d-141">**Minőségfeldolgozási irányelv:** *Minőségi rendelés létrehozása*</span><span class="sxs-lookup"><span data-stu-id="a336d-141">**Quality processing policy:** *Create quality order*</span></span>

        <span data-ttu-id="a336d-142">Válassza ki a készlet minőségének elutasításakor használandó irányelvet.</span><span class="sxs-lookup"><span data-stu-id="a336d-142">Select the policy that should be used when the quality of the inventory is rejected.</span></span> <span data-ttu-id="a336d-143">Ehhez a következő lehetőségek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="a336d-143">The following options are available:</span></span>

        - <span data-ttu-id="a336d-144">*Csak munka létrehozása* – Hozzon létre csak munkát a készlet mozgatásának megkönnyítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a336d-144">*Create work only* – Just create work to facilitate inventory movement.</span></span>
        - <span data-ttu-id="a336d-145">*Minőségi rendelés létrehozása* – Hozzon létre minőségi rendelést a minőségi tesztek megkönnyítéséhez.</span><span class="sxs-lookup"><span data-stu-id="a336d-145">*Create quality order* – Create a quality order to facilitate quality tests.</span></span>

    - <span data-ttu-id="a336d-146">**Tesztcsoport:** *Doboz*</span><span class="sxs-lookup"><span data-stu-id="a336d-146">**Test group:** *Enclosure*</span></span>

        <span data-ttu-id="a336d-147">Határozza meg a létrehozott minőségi rendelésben használandó tesztcsoportot.</span><span class="sxs-lookup"><span data-stu-id="a336d-147">Specify the test group that should be used in the quality order that is created.</span></span> <span data-ttu-id="a336d-148">A tesztcsoportok a **Készletkezelés** modulban állíthatók be.</span><span class="sxs-lookup"><span data-stu-id="a336d-148">Test groups are set up in the **Inventory management** module.</span></span>

        <span data-ttu-id="a336d-149">Hagyja kikapcsolva a **Romboló szöveg** lehetőséget a tesztcsoportnál.</span><span class="sxs-lookup"><span data-stu-id="a336d-149">Leave the **Destructive text** option turned off for the test group.</span></span> <span data-ttu-id="a336d-150">Ex a lehetőség határozza meg, hogy a tesztcsoportban szereplő tesztek eredményeként a mintát tönkreteszik-e vagy sem.</span><span class="sxs-lookup"><span data-stu-id="a336d-150">This option defines whether the sample will be destroyed as part of the tests in the test group.</span></span> <span data-ttu-id="a336d-151">Ha egy romboló tesztet használ, a rendszer létrehoz egy készlettranzakciót, ha a cikkhez létrehoznak egy minőségi rendelést.</span><span class="sxs-lookup"><span data-stu-id="a336d-151">If a destructive test is used, the system generates an inventory transaction when a quality order is created for an item.</span></span> <span data-ttu-id="a336d-152">Az új készlettranzakció előrejelzi mennyiségi teszthez való készlet csökkenését.</span><span class="sxs-lookup"><span data-stu-id="a336d-152">The new inventory transaction predicts the inventory reduction for the test quantity.</span></span> <span data-ttu-id="a336d-153">Készletcsökkenés akkor megy végre, ha a minőségi rendelést az ellenőrzési lépéssel fejezi be.</span><span class="sxs-lookup"><span data-stu-id="a336d-153">The inventory reduction occurs when the quality order is completed through the validation step.</span></span> <span data-ttu-id="a336d-154">A készlettranzakciót minőségi rendelésként azonosítja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="a336d-154">The inventory transaction is identified as a quality order.</span></span>

### <a name="work-class--quality-check"></a><a name="work-class"></a><span data-ttu-id="a336d-155">Munkaosztály – Minőségellenőrzés</span><span class="sxs-lookup"><span data-stu-id="a336d-155">Work class – Quality check</span></span>

<span data-ttu-id="a336d-156">A munkaosztályokkal irányítható és/vagy korlátozható azon munkarendeléssorok típusa, amelyeket a raktári dolgozók feldolgozhatnak egy mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="a336d-156">Work classes are used to direct and/or limit the type of work order lines that warehouse workers can process on a mobile device.</span></span>

1. <span data-ttu-id="a336d-157">Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.</span><span class="sxs-lookup"><span data-stu-id="a336d-157">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="a336d-158">Válassza az **Új** lehetőséget egy munkaosztály létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a336d-158">Select **New** to create a work class.</span></span>
1. <span data-ttu-id="a336d-159">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a336d-159">In the header, set the following values:</span></span>

    - <span data-ttu-id="a336d-160">**Munkaosztály azonosítója:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-160">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="a336d-161">Adjon meg egy nevet, amely azonosítja a munkaosztályt.</span><span class="sxs-lookup"><span data-stu-id="a336d-161">Enter a name that identifies the work class.</span></span>

    - <span data-ttu-id="a336d-162">**Leírás:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-162">**Description:** *QC Check*</span></span>

        <span data-ttu-id="a336d-163">Adjon meg egy rövid leírást, amely jelzi, hogy mire használható a munkaosztály.</span><span class="sxs-lookup"><span data-stu-id="a336d-163">Enter a short description that indicates what the work class is used for.</span></span>

    - <span data-ttu-id="a336d-164">**Munkarendelés típusa:** *Minőség a minőségellenőrzésben*</span><span class="sxs-lookup"><span data-stu-id="a336d-164">**Work order type:** *Quality in quality check*</span></span>

        <span data-ttu-id="a336d-165">Válassza ki, hogy milyen típusú munkarendelést hoz létre a munkaosztály.</span><span class="sxs-lookup"><span data-stu-id="a336d-165">Select the type of work order that is created by the work class.</span></span> <span data-ttu-id="a336d-166">A minőségellenőrzési munka beállításakor mindig válassza a *Minőség a minőségellenőrzésben* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-166">When you set up quality control work, always select *Quality in quality check*.</span></span>

1. <span data-ttu-id="a336d-167">Az **Érvényes betárolási helytípusok** gyorslapon hagyja üresen a **Hely típusa** mezőt.</span><span class="sxs-lookup"><span data-stu-id="a336d-167">On the **Valid put location types** FastTab, leave the **Location type** field blank.</span></span>

    <span data-ttu-id="a336d-168">Ha kiválaszt egy helytípust, akkor korlátozza azon helyeket, ahol a cikkeket a betárolásuk után ki lehet tárolni.</span><span class="sxs-lookup"><span data-stu-id="a336d-168">If you select a location type, you limit the locations where items can be put after they are picked.</span></span> <span data-ttu-id="a336d-169">Akkor használja ezt a mezőt, ha egy helyutasítás a hely feloldására tesz kísérletet, vagy amikor egy raktári dolgozó manuálisan meghatározza a mobileszköz-menüpont helyét.</span><span class="sxs-lookup"><span data-stu-id="a336d-169">This field is used when a location directive tries to resolve the location, or when a warehouse worker manually specifies the location for the mobile device menu item.</span></span>

<span data-ttu-id="a336d-170">A munkaosztályokkal és azok létrehozásával kapcsolatos további tudnivalókat lásd: [Munkaosztály létrehozása](tasks/create-work-class.md).</span><span class="sxs-lookup"><span data-stu-id="a336d-170">For more information about work classes and how to create them, see [Create a work class](tasks/create-work-class.md).</span></span>

### <a name="work-template"></a><span data-ttu-id="a336d-171">Munkasablon</span><span class="sxs-lookup"><span data-stu-id="a336d-171">Work template</span></span>

<span data-ttu-id="a336d-172">A munkasablonokkal megadhatja a műveleteket, amiket el kell végezni a raktárban.</span><span class="sxs-lookup"><span data-stu-id="a336d-172">Work templates let you define the work operations that must be performed in the warehouse.</span></span> <span data-ttu-id="a336d-173">Általában a raktári műveletek két egymást követő műveletből állnak: egy raktári dolgozó felveszi az aktuális készletet az egyik helyen, majd lerakja a készletet egy másik helyen.</span><span class="sxs-lookup"><span data-stu-id="a336d-173">Typically, warehouse work operations consist of a pair of actions: a warehouse worker picks on-hand inventory up in one location and then puts the picked inventory down in another location.</span></span> <span data-ttu-id="a336d-174">A minőségellenőrzés munkasablonja meghatározza a minőségellenőrzések munkafolyamatait.</span><span class="sxs-lookup"><span data-stu-id="a336d-174">A work template for quality control defines the work operations for doing quality checks.</span></span>

#### <a name="purchase-orders"></a><span data-ttu-id="a336d-175">Beszerzési rendelések</span><span class="sxs-lookup"><span data-stu-id="a336d-175">Purchase orders</span></span>

1. <span data-ttu-id="a336d-176">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="a336d-176">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="a336d-177">A fejlécben állítsa át a **Munkarendelés típusa** mezőt *Beszerzési rendelések* értékre.</span><span class="sxs-lookup"><span data-stu-id="a336d-177">In the header, set the **Work order type** field to *Purchase orders*.</span></span>
1. <span data-ttu-id="a336d-178">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-178">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a336d-179">Olyan munkasablonr válasszon ki, amelynek tartalmaznia kell egy minőségellenőrzési lépést.</span><span class="sxs-lookup"><span data-stu-id="a336d-179">Select a work template that should include a quality check step.</span></span> <span data-ttu-id="a336d-180">Válassza az **Áttekintés** szakaszban a **Munkasablon** mezőben lévő *51 Igénylés, beszerzési rendelés* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-180">In the **Overview** section, in the **Work template** field, select *51 PO Receipt*.</span></span>
1. <span data-ttu-id="a336d-181">A **Munkasablon részletei** szakaszban figyelje meg, hogy a rácsnak két meglévő sora van: egy *Kitárolásra* és egy *Eltárolásra*.</span><span class="sxs-lookup"><span data-stu-id="a336d-181">In the **Work template details** section, notice that the grid has two existing lines: one for *Pick* and one for *Put*.</span></span>
1. <span data-ttu-id="a336d-182">A **Munkasablon részletei** szakaszban válassza ki az **Új** lehetőséget,ha a rácshoz hozzá szeretne adni egy sort a minőségellenőrzéshez.</span><span class="sxs-lookup"><span data-stu-id="a336d-182">In the **Work template details** section, select **New** to add a row for quality control to the grid.</span></span> <span data-ttu-id="a336d-183">Figyelje meg, hogy az új sor **Sorszám** mező *3* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="a336d-183">Notice that the **Line number** field for the new line is set to *3*.</span></span>
1. <span data-ttu-id="a336d-184">Az új sorban állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="a336d-184">On the new line, set the following values.</span></span> <span data-ttu-id="a336d-185">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="a336d-185">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="a336d-186">**Munkatípus:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-186">**Work type:** *Quality check*</span></span>
    - <span data-ttu-id="a336d-187">**Munkaosztály azonosítója:** *Beszerzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-187">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="a336d-188">**Minőségellenőrzési sablon neve:** *Dokkellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-188">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="a336d-189">Válasszon egy egyedi azonosítót a munkaosztályhoz.</span><span class="sxs-lookup"><span data-stu-id="a336d-189">Select the unique ID for the work class.</span></span> <span data-ttu-id="a336d-190">Ezt az értéket használja a menüelemek beállítására a mobileszközön, és azon munkatípusok beállításához, amelyeket azok a menüelemek fel tudnak dolgozni.</span><span class="sxs-lookup"><span data-stu-id="a336d-190">You use this value to configure the menu items on the mobile device and the types of work that those menu items can process.</span></span>

1. <span data-ttu-id="a336d-191">A Művelet ablaktáblában válassza a **Mentés** lehetőséget az elvégzett munka mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="a336d-191">On the Action Pane, select **Save** to save your work so far.</span></span>

    <span data-ttu-id="a336d-192">Egy tájékoztató üzenet jelenik meg: „Érvénytelen – A minőségellenőrzésnek közvetlenül a kitárolás után kell következnie”.</span><span class="sxs-lookup"><span data-stu-id="a336d-192">You receive an informational message that states, "Invalid - Quality check must come directly after a pick."</span></span> <span data-ttu-id="a336d-193">Ennek megfelelően módosítania kell az imént hozzáadott sor **Sorszám** értéket.</span><span class="sxs-lookup"><span data-stu-id="a336d-193">Therefore, you must change the **Line number** value for the line that you just added.</span></span>

1. <span data-ttu-id="a336d-194">Az új sor **Sorszám** értékének módosításához kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="a336d-194">Follow these steps to change the **Line number** value for the new line:</span></span>

    1. <span data-ttu-id="a336d-195">A **Munkasablon részletei** szakaszban válassza ki azt a sort, amelyben a **Munka típusa** mező *Minőségellenőrzés* lehetőségre van állítva.</span><span class="sxs-lookup"><span data-stu-id="a336d-195">In the **Work template details** section, select the line where the **Work type** field is set to *Quality check*.</span></span>
    2. <span data-ttu-id="a336d-196">Válassza a **Feljebb** vagy a **Lentebb** gombra a *Minőségellenőrzés* sor mozgatásához, hogy a *Kitárolás* sor után jöjjön.</span><span class="sxs-lookup"><span data-stu-id="a336d-196">Select the **Move up** or **Move down** button to move the *Quality check* line so that it's after the *Pick* line.</span></span>

1. <span data-ttu-id="a336d-197">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-197">On the Action Pane, select **Save**.</span></span>

#### <a name="quality-in-quality-check"></a><span data-ttu-id="a336d-198">Minőség a minőség-ellenőrzésnél</span><span class="sxs-lookup"><span data-stu-id="a336d-198">Quality in quality check</span></span>

<span data-ttu-id="a336d-199">Ezután hozzon létre egy munkasablont a minőségellenőrzéshez.</span><span class="sxs-lookup"><span data-stu-id="a336d-199">Next, create a work template for the quality check.</span></span>

1. <span data-ttu-id="a336d-200">A **Munkasablonok** lap fejlécében módosítsa a **Munkarendelés típusa** mező értékét a *Minőség a minőségellenőrzésben* lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a336d-200">In the header of the **Work templates** page, change the value of the **Work order type** field to *Quality in quality check*.</span></span>
1. <span data-ttu-id="a336d-201">A Művelet panelen válassza az **Új** lehetőséget egy sor **Áttekintés** szakaszban lévő rácshoz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="a336d-201">On the Action Pane, select **New** to add a row to the grid in the **Overview** section.</span></span>
1. <span data-ttu-id="a336d-202">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a336d-202">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a336d-203">**Munkasablon:** *51 Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-203">**Work template:** *51 Quality Check*</span></span>

        <span data-ttu-id="a336d-204">Írja be a sablon nevét.</span><span class="sxs-lookup"><span data-stu-id="a336d-204">Enter a name for the template.</span></span>

    - <span data-ttu-id="a336d-205">**Munkasablon leírása:** *51 Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-205">**Work template description:** *51 Quality Check*</span></span>

1. <span data-ttu-id="a336d-206">A Művelet ablaktáblán a **Mentés** gombra kattintva elérhetővé válik a **Munkasablon részletei** szakasz.</span><span class="sxs-lookup"><span data-stu-id="a336d-206">On the Action Pane, select **Save** to make the **Work template details** section available.</span></span>
1. <span data-ttu-id="a336d-207">Miközben az új sablon még ki van választva az **Áttekintés** szakaszban, válassza az **Új** lehetőséget a **Munkasablon részletei** szakaszban, így hozzáadhat egy sort a sablonban lévő rácshoz.</span><span class="sxs-lookup"><span data-stu-id="a336d-207">While the new template is still selected in the **Overview** section, select **New** in the **Work template details** section to add a row to the grid there.</span></span>
1. <span data-ttu-id="a336d-208">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a336d-208">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a336d-209">**Munka típusa:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="a336d-209">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="a336d-210">**Munkaosztály azonosítója:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-210">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="a336d-211">Válassza ki a [Munkaosztály](#work-class) nevét, amelyet korábban létrehozott a minőségellenőrzési munkához.</span><span class="sxs-lookup"><span data-stu-id="a336d-211">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="a336d-212">A **Munkasablon részletei** szakaszban válassza ki megint az **Új** lehetőséget, ha egy újabb sort szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="a336d-212">In the **Work template details** section, select **New** again to add another row.</span></span>
1. <span data-ttu-id="a336d-213">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a336d-213">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a336d-214">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="a336d-214">**Work type:** *Put*</span></span>
    - <span data-ttu-id="a336d-215">**Munkaosztály azonosítója:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-215">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="a336d-216">Válassza ki a [Munkaosztály](#work-class) nevét, amelyet korábban létrehozott a minőségellenőrzési munkához.</span><span class="sxs-lookup"><span data-stu-id="a336d-216">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="a336d-217">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-217">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="a336d-218">A Munkasablonokkal kapcsolatos további információkat lásd: [A raktári munka ellenőrzése munkasablonok és helyutasítások használatával](control-warehouse-location-directives.md)</span><span class="sxs-lookup"><span data-stu-id="a336d-218">For more information about work templates, see [Control warehouse work by using work templates and location directives](control-warehouse-location-directives.md)</span></span>

### <a name="location-directive--quality-failures"></a><span data-ttu-id="a336d-219">Helyutasítás – Minőségi hibák</span><span class="sxs-lookup"><span data-stu-id="a336d-219">Location directive – Quality failures</span></span>

<span data-ttu-id="a336d-220">A helyutasítások olyan szabályok, amik segítik a kitárolási és betárolási helyek meghatározását, készletmozgatás esetében.</span><span class="sxs-lookup"><span data-stu-id="a336d-220">Location directives are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="a336d-221">Például egy értékesítési rendelés tranzakciójába a helyutasítás azt határozza meg, ahol a cikkek kivétele történik, és ha a kitárolt cikkek kerülnek.</span><span class="sxs-lookup"><span data-stu-id="a336d-221">For example, in a sales order transaction, a location directive determines where the items will be picked and where the picked items will be put.</span></span> <span data-ttu-id="a336d-222">Meg kell adnia egy helyutasítást, amely meghatározza, hogy hogyan kezelje a program a sikertelen minőségellenőrzéseket.</span><span class="sxs-lookup"><span data-stu-id="a336d-222">You must configure a location directive rule to define how failed quality checks will be handled.</span></span>

1. <span data-ttu-id="a336d-223">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="a336d-223">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="a336d-224">A bal oldali ablaktáblában a **Munkarendelés típusa** mezőt állítsa *Beszerzési rendelések* értékre, hogy az adott típusú helyutasításokkal együttműködjön.</span><span class="sxs-lookup"><span data-stu-id="a336d-224">In the left pane, set the **Work order type** field to *Purchase orders* to work with location directives of that type.</span></span>
1. <span data-ttu-id="a336d-225">A művelet ablaktáblán válassza az **Új** parancsot a minőségellenőrzéshez használandó új helyutasítás létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a336d-225">On the Action Pane, select **New** to create a location directive for quality checks.</span></span>
1. <span data-ttu-id="a336d-226">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a336d-226">In the header, set the following values:</span></span>

    - <span data-ttu-id="a336d-227">**Sorszám:** Fogadja el az alapértelmezett értéket.</span><span class="sxs-lookup"><span data-stu-id="a336d-227">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="a336d-228">**Név:** *51 Minőséghez*</span><span class="sxs-lookup"><span data-stu-id="a336d-228">**Name:** *51 To Quality*</span></span>

1. <span data-ttu-id="a336d-229">A **Helyutasítások** gyorslapon állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="a336d-229">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="a336d-230">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="a336d-230">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="a336d-231">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="a336d-231">**Work type:** *Put*</span></span>
    - <span data-ttu-id="a336d-232">**Telephely:** *5*</span><span class="sxs-lookup"><span data-stu-id="a336d-232">**Site:** *5*</span></span>
    - <span data-ttu-id="a336d-233">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="a336d-233">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="a336d-234">A Műveleti ablaktáblán a **Mentés** gombra kattintva mentheti az utasítást, és elérhetővé válik a **Sorok** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="a336d-234">On the Action Pane select **Save** to save your directive and make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="a336d-235">A **Sorok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="a336d-235">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="a336d-236">Az új sorban állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="a336d-236">On the new line, set the following values.</span></span> <span data-ttu-id="a336d-237">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="a336d-237">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="a336d-238">**Kezdő mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="a336d-238">**From quantity:** *1*</span></span>
    - <span data-ttu-id="a336d-239">**Záró mennyiség:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="a336d-239">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="a336d-240">A Műveleti ablaktáblán a **Mentés** gombra kattintva mentheti az új sort, és elérhetővé válik a **Helyutasítás műveletei** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="a336d-240">On the Action Pane, select **Save** to save the new line and make the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="a336d-241">Ha az új sor továbbra is be ki van választva a **Sorok** gyorslapon, akkor a **Helyutasítás műveletei** gyorslap **Új** elemét kiválasztva egy sort adhat a rácshoz, így beállíthat egy műveletet a sorhoz.</span><span class="sxs-lookup"><span data-stu-id="a336d-241">While the new line is still selected on the **Lines** FastTab, select **New** on the **Location directive actions** FastTab to add a row to the grid there, so that you can set up an action for the line.</span></span>
1. <span data-ttu-id="a336d-242">Az új sorban állítsa a **Név** mezőt a *Minőség* értékre.</span><span class="sxs-lookup"><span data-stu-id="a336d-242">In the new row, set the **Name** field to *Quality*.</span></span> <span data-ttu-id="a336d-243">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="a336d-243">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="a336d-244">A Műveleti ablaktáblán a **Mentés** gombra kattintva teheti elérhetővé a **Lekérdezés szerkesztése** gombot a **Helyutasítás műveletei** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="a336d-244">On the Action Pane, select **Save** to make the **Edit query** button on the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="a336d-245">Amíg az imént hozzáadott sor továbbra is ki van jelölve a **Helyutasítás műveletei** gyorslapon, válassza a **Lekérdezés szerkesztése** gombot, hogy megnyíljon egy párbeszédpanel, amelyen szerkesztheti a művelet lekérdezését.</span><span class="sxs-lookup"><span data-stu-id="a336d-245">While the line that you just added is still selected on the **Location directive actions** FastTab, select **Edit query** to open a dialog box where you can edit the query for the action.</span></span>
1. <span data-ttu-id="a336d-246">A **tartomány** lapon válassza a **Hozzáadás** lehetőséget sor hozzáadásához a lekérdezéshez.</span><span class="sxs-lookup"><span data-stu-id="a336d-246">On the **Range** tab, select **Add** to add a row to the query.</span></span>
1. <span data-ttu-id="a336d-247">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a336d-247">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a336d-248">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="a336d-248">**Table:** *Locations*</span></span>
    - <span data-ttu-id="a336d-249">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="a336d-249">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="a336d-250">**Mező:** *Hely*</span><span class="sxs-lookup"><span data-stu-id="a336d-250">**Field:** *Location*</span></span>
    - <span data-ttu-id="a336d-251">**Feltételek:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="a336d-251">**Criteria:** *QMS*</span></span>

    <span data-ttu-id="a336d-252">A *QMS* hely a minőséghez használandó raktári hely.</span><span class="sxs-lookup"><span data-stu-id="a336d-252">The *QMS* location is a warehouse location for quality.</span></span>

1. <span data-ttu-id="a336d-253">Az **OK** gombbal zárja be a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="a336d-253">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="a336d-254">EKkor módosítania kell a beszerzési rendelés helyutasításokat az *51*-es raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="a336d-254">You must now change the sequence of purchase order location directives for warehouse *51*.</span></span> <span data-ttu-id="a336d-255">Mentse az új *51 Minőséghez* helyutasítást, frissítse a lapot, majd válassza ki a helyutasítást a listából.</span><span class="sxs-lookup"><span data-stu-id="a336d-255">Save the new *51 To Quality* location directive, refresh the page, and select the location directive in the list.</span></span> <span data-ttu-id="a336d-256">Ezután a Műveleti ablaktáblán lévő **Feljebb** és **Lejjebb** gombokkal helyezze át a helyutasítást az *51*-es raktárhoz a következő sorrendben.</span><span class="sxs-lookup"><span data-stu-id="a336d-256">Then use the **Move up** and **Move down** buttons on the Action Pane to put the location directive for warehouse *51* in the following order.</span></span> <span data-ttu-id="a336d-257">(Mielőtt kiválasztja a **Feljebb** vagy **Lejjebb** gombot, ki kell választania egy helyutasítást a listából.)</span><span class="sxs-lookup"><span data-stu-id="a336d-257">(Before you select **Move up** or **Move down**, you must select a location directive in the list.)</span></span>

    1. <span data-ttu-id="a336d-258">51 Minőséghez</span><span class="sxs-lookup"><span data-stu-id="a336d-258">51 To Quality</span></span>
    2. <span data-ttu-id="a336d-259">51 közvetlen beszerzési rendelés</span><span class="sxs-lookup"><span data-stu-id="a336d-259">51 PO Direct</span></span>
    3. <span data-ttu-id="a336d-260">51 QMS</span><span class="sxs-lookup"><span data-stu-id="a336d-260">51 QMS</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="a336d-261">Mobileszköz menüpontjai</span><span class="sxs-lookup"><span data-stu-id="a336d-261">Mobile device menu items</span></span>

<span data-ttu-id="a336d-262">A menüelemet úgy konfigurálhatja, hogy a mobileszköz végre tudja hajtani a **Minőségellenőrzés** funkciót.</span><span class="sxs-lookup"><span data-stu-id="a336d-262">Configure a menu item so that mobile devices can perform the **Quality Check** function.</span></span>

#### <a name="purchase-putaway"></a><span data-ttu-id="a336d-263">Beszerzés betárolása</span><span class="sxs-lookup"><span data-stu-id="a336d-263">Purchase putaway</span></span>

1. <span data-ttu-id="a336d-264">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="a336d-264">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="a336d-265">Válassza ki a listából a **Beszerzés eltárolása** menüelemet.</span><span class="sxs-lookup"><span data-stu-id="a336d-265">In the list, select the **Purchase put-away** menu item.</span></span>
1. <span data-ttu-id="a336d-266">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-266">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a336d-267">A **Munkaosztályok** szakaszban válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="a336d-267">In the **Work classes** section, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="a336d-268">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a336d-268">In the new row, set the following values:</span></span>

    - <span data-ttu-id="a336d-269">**Munkaosztály azonosítója:** *Minőségellenőrzés*</span><span class="sxs-lookup"><span data-stu-id="a336d-269">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="a336d-270">Adja meg a [Munkaosztály](#work-class) nevét, amelyet korábban létrehozott a minőségellenőrzési munkához.</span><span class="sxs-lookup"><span data-stu-id="a336d-270">Enter the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

    - <span data-ttu-id="a336d-271">**Munkarendelés típusa:** *Minőség a minőségellenőrzésben*</span><span class="sxs-lookup"><span data-stu-id="a336d-271">**Work order type:** *Quality in quality check*</span></span>

1. <span data-ttu-id="a336d-272">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-272">On the Action Pane, select **Save**.</span></span>

#### <a name="purchase-order-line-receiving"></a><span data-ttu-id="a336d-273">Beszerzésirendelés-sor bevételezése</span><span class="sxs-lookup"><span data-stu-id="a336d-273">Purchase order line receiving</span></span>

1. <span data-ttu-id="a336d-274">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="a336d-274">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="a336d-275">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="a336d-275">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a336d-276">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a336d-276">In the header, set the following values:</span></span>

    - <span data-ttu-id="a336d-277">**Menüelem neve:** *Beszerzési rendelési sor bevételezése*</span><span class="sxs-lookup"><span data-stu-id="a336d-277">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="a336d-278">**Cím:** *Beszerzési rendelési sor bevételezése*</span><span class="sxs-lookup"><span data-stu-id="a336d-278">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="a336d-279">**Mód:** *Munka*</span><span class="sxs-lookup"><span data-stu-id="a336d-279">**Mode:** *Work*</span></span>
    - <span data-ttu-id="a336d-280">**Meglévő munka használata:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="a336d-280">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="a336d-281">Az **Általános** gyorslapon állítsa be a következő értékeket.</span><span class="sxs-lookup"><span data-stu-id="a336d-281">On the **General** FastTab, set the following values.</span></span> <span data-ttu-id="a336d-282">Az fennmaradó mezőkben hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="a336d-282">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="a336d-283">**Munkalétrehozási folyamat:** *Beszerzési rendelési sor bevételezése és eltárolása*</span><span class="sxs-lookup"><span data-stu-id="a336d-283">**Work creation process:** *Purchase order line receiving and put away*</span></span>
    - <span data-ttu-id="a336d-284">**Azonosítótábla létrehozása:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="a336d-284">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="a336d-285">**Munkasablon:** *51 Igénylés, beszerzési rendelés*</span><span class="sxs-lookup"><span data-stu-id="a336d-285">**Work template:** *51 PO Receipt*</span></span>

1. <span data-ttu-id="a336d-286">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-286">On the Action Pane, select **Save**.</span></span>

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="a336d-287">A menüelem hozzáadása a mobileszköz menühöz</span><span class="sxs-lookup"><span data-stu-id="a336d-287">Add the menu item to a mobile device menu</span></span>

1. <span data-ttu-id="a336d-288">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.</span><span class="sxs-lookup"><span data-stu-id="a336d-288">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="a336d-289">A bal oldali ablaktáblán válassza a **Bejövő** menüt.</span><span class="sxs-lookup"><span data-stu-id="a336d-289">In the left pane, select the **Inbound** menu.</span></span>
1. <span data-ttu-id="a336d-290">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-290">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a336d-291">A **Rendelkezésre álló menük és menüelemek** oszlopban keresse meg és válassza ki az új **Beszerzési rendelési sor bevételezése** menüelemet.</span><span class="sxs-lookup"><span data-stu-id="a336d-291">In the **Available menus and menu items** column, select the new **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="a336d-292">Válassza a jobbra mutató nyilat a **Beszerzési rendelési sor bevételezése** áthelyezéséhez a **Menü struktúrája** oszlopba.</span><span class="sxs-lookup"><span data-stu-id="a336d-292">Select the right arrow button to move **PO line receiving** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="a336d-293">A **Menü szerkezete** oszlopban válassza ki a **Beszerzési rendelési sor bevételezése** lehetőséget, majd a feljebb vagy lejjebb nyílra kattintva helyezze át a menüelemet a mobileszköz menüjének kívánt pontjára.</span><span class="sxs-lookup"><span data-stu-id="a336d-293">In the **Menu structure** column, select **PO line receiving**, and then select the up arrow or down arrow button to move the menu item to the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="a336d-294">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-294">On the Action Pane, select **Save**.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="a336d-295">Példaforgatókönyv</span><span class="sxs-lookup"><span data-stu-id="a336d-295">Example scenario</span></span>

<span data-ttu-id="a336d-296">Miután elvégezte az összes korábban leírt mintaadatok elérhetővé tételét és beállítását, a forgatókönyvön keresztül kipróbálhatja a *Minőségellenőrzés* funkciót.</span><span class="sxs-lookup"><span data-stu-id="a336d-296">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Quality check* feature.</span></span> <span data-ttu-id="a336d-297">Az ebben a forgatókönyvben látható értékek feltételezik, hogy azokkal a szokásos bemutatóadatokkal dolgozik, amelyeket az **USMF** jogi személyt kiválasztott, és hogy előkészítette a témakör korábbi részében ismertetett mintarekordokat.</span><span class="sxs-lookup"><span data-stu-id="a336d-297">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="a336d-298">Ez a forgatókönyv példaként is szolgál, amely megmutatja, hogyan használható a funkció az üzemelési beállításban.</span><span class="sxs-lookup"><span data-stu-id="a336d-298">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="a336d-299">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="a336d-299">Create a purchase order</span></span>

1. <span data-ttu-id="a336d-300">Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="a336d-300">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="a336d-301">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="a336d-301">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a336d-302">Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a336d-302">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a336d-303">**Szállítói számla:** *104*</span><span class="sxs-lookup"><span data-stu-id="a336d-303">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="a336d-304">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="a336d-304">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="a336d-305">Válassza az **OK** gombot a párbeszédpanel bezárásához, és egy új beszerzési rendelés megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a336d-305">Select **OK** to close the dialog box and open the new purchase order.</span></span>
1. <span data-ttu-id="a336d-306">A **Beszerzési rendelés sorai** gyorslapon a rács egy új, üres sort tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="a336d-306">On the **Purchase order lines** FastTab, the grid contains a new, blank line.</span></span> <span data-ttu-id="a336d-307">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="a336d-307">On this line, set the following values:</span></span>

    - <span data-ttu-id="a336d-308">**Cikkszám:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="a336d-308">**Item number:** *M9203*</span></span>
    - <span data-ttu-id="a336d-309">**Mennyiség:** *3*</span><span class="sxs-lookup"><span data-stu-id="a336d-309">**Quantity:** *3*</span></span>
    - <span data-ttu-id="a336d-310">**Egység:** *PL*</span><span class="sxs-lookup"><span data-stu-id="a336d-310">**Unit:** *PL*</span></span>

1. <span data-ttu-id="a336d-311">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-311">On the Action Pane, select **Save**.</span></span>

### <a name="process-quality-check-receiving"></a><span data-ttu-id="a336d-312">Folyamat minőségellenőrzési bevételezése</span><span class="sxs-lookup"><span data-stu-id="a336d-312">Process quality check receiving</span></span>

<span data-ttu-id="a336d-313">A beszerzési rendelés létrehozása után a program a **Beszerzési rendelési sor bevételezése** menüelem és a *Minőségellenőrzés* funkció használatával szerezheti be.</span><span class="sxs-lookup"><span data-stu-id="a336d-313">After the purchase order has been created, it can be received by using the **PO line receiving** menu item and the functionality of the *Quality check* feature.</span></span>

#### <a name="receive-pallet-1"></a><span data-ttu-id="a336d-314">1. raklap fogadása</span><span class="sxs-lookup"><span data-stu-id="a336d-314">Receive pallet 1</span></span>

1. <span data-ttu-id="a336d-315">Jelentkezzen be az *51*-es raktár felhasználójaként a raktár alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a336d-315">Sign in to the warehouse app as a user for warehouse *51*.</span></span> <span data-ttu-id="a336d-316">(Írja be a felhasználói azonosítóhoz a *51*-et, a jelszóhoz pedig az *1*-et.)</span><span class="sxs-lookup"><span data-stu-id="a336d-316">(Enter *51* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="a336d-317">Menjen a **Bejövő \> Beszerzési rendelési sor bevételezése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a336d-317">Go to **Inbound \> PO line receiving**.</span></span>
1. <span data-ttu-id="a336d-318">A **PONUM** mezőbe adja meg a beszerzési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="a336d-318">In the **PONUM** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="a336d-319">Erősítse meg újra a beszerzési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="a336d-319">Confirm the purchase order number.</span></span>
1. <span data-ttu-id="a336d-320">A **LINENUM** mezőbe adja meg a bevételezett beszerzési rendelés sorszámát.</span><span class="sxs-lookup"><span data-stu-id="a336d-320">In the **LINENUM** field, enter the number of the purchase order line that is being received.</span></span> <span data-ttu-id="a336d-321">Mivel a rendelésnek ebben a forgatókönyvben csak egy sora van, ezért a **LINENUM** mezőbe az *1*-es értéket kell beírnia mindegyik bevételezési lépésnél.</span><span class="sxs-lookup"><span data-stu-id="a336d-321">Because the order has only one line in this scenario, you will enter *1* in the **LINENUM** field for each receiving step.</span></span>
1. <span data-ttu-id="a336d-322">A sor számának megerősítése.</span><span class="sxs-lookup"><span data-stu-id="a336d-322">Confirm the line number.</span></span>
1. <span data-ttu-id="a336d-323">A **Mennyiség** mezőbe írja be a bevételezett mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-323">In the **QTY** field, enter the quantity to receive.</span></span> <span data-ttu-id="a336d-324">Mivel ebben a forgatókönyvben a beszerzési rendelés három raklapra (*PL*) szól, és három bevételezési lépés van, ezért az *1*-es értéket kell megadnia a **MENNYISÉG** mezőben minden egyes bevételezési lépésnél.</span><span class="sxs-lookup"><span data-stu-id="a336d-324">Because the purchase order is for three pallets (*PL*) in this scenario, and there are three receiving steps, you will enter *1* in the **QTY** field for each receiving step.</span></span>
1. <span data-ttu-id="a336d-325">Nyugtázza a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-325">Confirm the quantity.</span></span>

    <span data-ttu-id="a336d-326">A megjelenő **Minőségellenőrzés** lap nem tartalmaz bejegyzési mezőket.</span><span class="sxs-lookup"><span data-stu-id="a336d-326">The **Quality check** page that appears has no entry fields.</span></span> <span data-ttu-id="a336d-327">Csak a megerősítés (pipa) gombot alul, és a Menü gombot (**≡**) felül.</span><span class="sxs-lookup"><span data-stu-id="a336d-327">It has only the confirmation (check mark) button at the bottom and the Menu button (**≡**) at the top.</span></span> <span data-ttu-id="a336d-328">(A Menü gombot néha hamburgernek vagy a hamburger gombnak is nevezik.) A minőségellenőrzési folyamat meggyorsításához – amikor a raklap átmegy a minőségellenőrzésen – a felhasználónak csak meg kell erősítenie a **Minőségellenőrzés** lapot.</span><span class="sxs-lookup"><span data-stu-id="a336d-328">(The Menu button is sometimes referred to as the hamburger or the hamburger button.) To expedite the quality check process, when the pallet passes the quality check, the user just confirms the **Quality check** page.</span></span>

    <span data-ttu-id="a336d-329">![Minőségellenőrzés lap](media/quality-check.png "Minőségellenőrzés lap")</span><span class="sxs-lookup"><span data-stu-id="a336d-329">![Quality check page](media/quality-check.png "Quality check page")</span></span>

1. <span data-ttu-id="a336d-330">Válassza ki a megerősítés gombot, ha az 1. sorban lévő 1. raklap átment a minőségellenőrzésen.</span><span class="sxs-lookup"><span data-stu-id="a336d-330">Select the confirmation button to pass the quality check for pallet 1 from line 1.</span></span>

    <span data-ttu-id="a336d-331">A megjelenő **Beszerzési rendelések: Eltárolás** lap az eltárolási munka részleteit jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="a336d-331">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="a336d-332">**LOC:** A rendszer által meghatározott hely</span><span class="sxs-lookup"><span data-stu-id="a336d-332">**LOC:** The system determined location</span></span>

        <span data-ttu-id="a336d-333">Ez a hely a beszerzési rendelés bevételezéséhez megadott eltárolási hely.</span><span class="sxs-lookup"><span data-stu-id="a336d-333">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="a336d-334">**LP:** A rendszer által létrehozott azonosítótábla azonosítója</span><span class="sxs-lookup"><span data-stu-id="a336d-334">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="a336d-335">**Cikk:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="a336d-335">**Item:** *M9203*</span></span>
    - <span data-ttu-id="a336d-336">**Mennyiség:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="a336d-336">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="a336d-337">A cíkk leírása is itt látható.</span><span class="sxs-lookup"><span data-stu-id="a336d-337">The item description is also shown.</span></span>

1. <span data-ttu-id="a336d-338">Erősítse meg a betárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="a336d-338">Confirm the putaway work.</span></span>

    <span data-ttu-id="a336d-339">A beszerzési rendeléssor **Feladat** lapján a „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a336d-339">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="a336d-340">A **LINENUM** mező elérhető, úgyhogy fogadhatja a következő raklapot.</span><span class="sxs-lookup"><span data-stu-id="a336d-340">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

#### <a name="receive-pallet-2"></a><span data-ttu-id="a336d-341">2. raklap fogadása</span><span class="sxs-lookup"><span data-stu-id="a336d-341">Receive pallet 2</span></span>

<span data-ttu-id="a336d-342">Ennél a forgatókönyvnél a 2. raklapot el fogja utasítani a program.</span><span class="sxs-lookup"><span data-stu-id="a336d-342">For this scenario, pallet 2 will be rejected.</span></span>

1. <span data-ttu-id="a336d-343">A **LINENUM** mezőbe írja be az *1* értéket , majd erősítse meg a sor számát.</span><span class="sxs-lookup"><span data-stu-id="a336d-343">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="a336d-344">A **MENNYISÉG** mező mostantól elérhető.</span><span class="sxs-lookup"><span data-stu-id="a336d-344">The **QTY** field is now available.</span></span> <span data-ttu-id="a336d-345">Adja meg az *1* értéket, majd erősítse meg a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-345">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="a336d-346">Megjelenik a **Minőségellenőrzés** oldal.</span><span class="sxs-lookup"><span data-stu-id="a336d-346">The **Quality check** page appears.</span></span> <span data-ttu-id="a336d-347">Ezen nyugta esetében a raklapot elutasítja a program a minősége miatt, és a *QMS* minőséghelyre kerül.</span><span class="sxs-lookup"><span data-stu-id="a336d-347">For this receipt, the pallet will be rejected for quality, and it will be put into the *QMS* quality location.</span></span>

1. <span data-ttu-id="a336d-348">Válassza ki a lap tetején látható Menü gombot (**≡**), majd válassza az **Elutasítás** lehetőséget a menüben.</span><span class="sxs-lookup"><span data-stu-id="a336d-348">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Reject**.</span></span>
1. <span data-ttu-id="a336d-349">A megjelenő **Feladat** oldalon adja meg a **QMS** éréket, mint *Betárolási* helyet, hogy a raklapot elküldhesse további ellenőrzésre.</span><span class="sxs-lookup"><span data-stu-id="a336d-349">On the **Task** page that appears, enter **QMS** as the *Put* location to send the pallet to for further inspection.</span></span>

    <span data-ttu-id="a336d-350">A megjelenő **Minőség a minőségellenőrzésben: Eltárolás** lap az eltárolási munka részleteit jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="a336d-350">The **Quality in quality check: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="a336d-351">**LOC:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="a336d-351">**LOC:** *QMS*</span></span>

        <span data-ttu-id="a336d-352">Ez a hely az elutasított minőség bevételezéséhez megadott eltárolási hely.</span><span class="sxs-lookup"><span data-stu-id="a336d-352">This location is the designated putaway location for rejected quality receiving.</span></span>

    - <span data-ttu-id="a336d-353">**LP:** A rendszer által létrehozott azonosítótábla azonosítója</span><span class="sxs-lookup"><span data-stu-id="a336d-353">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="a336d-354">**Cikk:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="a336d-354">**Item:** *M9203*</span></span>
    - <span data-ttu-id="a336d-355">**Mennyiség:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="a336d-355">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="a336d-356">A cíkk leírása is itt látható.</span><span class="sxs-lookup"><span data-stu-id="a336d-356">The item description is also shown.</span></span>

1. <span data-ttu-id="a336d-357">Erősítse meg a betárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="a336d-357">Confirm the putaway work.</span></span>

    <span data-ttu-id="a336d-358">A beszerzési rendeléssor **Feladat** lapján a „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a336d-358">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="a336d-359">A **LINENUM** mező elérhető, úgyhogy fogadhatja a következő raklapot.</span><span class="sxs-lookup"><span data-stu-id="a336d-359">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

<span data-ttu-id="a336d-360">Ezennel befejezte a minőségellenőrzést, és létrehozta a minőségi rendelést az elutasított raklaphoz.</span><span class="sxs-lookup"><span data-stu-id="a336d-360">You've now completed the quality check and created a quality order for the rejected pallet.</span></span> <span data-ttu-id="a336d-361">Ha meg szeretné tekinteni a létrehozott minőségi rendelést, menjen a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="a336d-361">To view the order that was created, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="a336d-362">A minőségi rendelés tesztelése most már feldolgozható.</span><span class="sxs-lookup"><span data-stu-id="a336d-362">Quality order testing can now be processed.</span></span> <span data-ttu-id="a336d-363">Ebben a témakörben nem szerepel minőségi tesztelés.</span><span class="sxs-lookup"><span data-stu-id="a336d-363">Quality testing isn't covered in this topic.</span></span>

<span data-ttu-id="a336d-364">A minőségkezeléssel kapcsolatos további tudnivalókat lásd: [Minőségkezelés áttekintése](../inventory/enable-quality-management.md)</span><span class="sxs-lookup"><span data-stu-id="a336d-364">For more information about quality management, see [Quality management overview](../inventory/enable-quality-management.md)</span></span>

#### <a name="receive-pallet-3"></a><span data-ttu-id="a336d-365">3. raklap fogadása</span><span class="sxs-lookup"><span data-stu-id="a336d-365">Receive pallet 3</span></span>

<span data-ttu-id="a336d-366">Ennél a forgatókönyvnél a 3. raklapot el fogja fogadni a program.</span><span class="sxs-lookup"><span data-stu-id="a336d-366">For this scenario, pallet 3 will be accepted.</span></span>

1. <span data-ttu-id="a336d-367">A **LINENUM** mezőbe írja be az *1* értéket , majd erősítse meg a sor számát.</span><span class="sxs-lookup"><span data-stu-id="a336d-367">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="a336d-368">A **MENNYISÉG** mező mostantól elérhető.</span><span class="sxs-lookup"><span data-stu-id="a336d-368">The **QTY** field is now available.</span></span> <span data-ttu-id="a336d-369">Adja meg az *1* értéket, majd erősítse meg a mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="a336d-369">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="a336d-370">Megjelenik a **Minőségellenőrzés** oldal.</span><span class="sxs-lookup"><span data-stu-id="a336d-370">The **Quality check** page appears.</span></span> <span data-ttu-id="a336d-371">Ezen nyugta esetében a raklapot el fogja fogadni a program a minősége miatt, és egy ömlesztett eltárolási helyre kerül.</span><span class="sxs-lookup"><span data-stu-id="a336d-371">For this receipt, the pallet will be accepted for quality, and it will be put into a bulk putaway location.</span></span>

1. <span data-ttu-id="a336d-372">Válassza ki a megerősítés gombot, ha átment a minőségellenőrzésen.</span><span class="sxs-lookup"><span data-stu-id="a336d-372">Select the confirmation button to pass the quality check.</span></span>

    <span data-ttu-id="a336d-373">A megjelenő **Beszerzési rendelések: Eltárolás** lap az eltárolási munka részleteit jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="a336d-373">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="a336d-374">**LOC:** A rendszer által meghatározott hely</span><span class="sxs-lookup"><span data-stu-id="a336d-374">**LOC:** The system determined location</span></span>

        <span data-ttu-id="a336d-375">Ez a hely a beszerzési rendelés bevételezéséhez megadott eltárolási hely.</span><span class="sxs-lookup"><span data-stu-id="a336d-375">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="a336d-376">**LP:** A rendszer által létrehozott azonosítótábla azonosítója</span><span class="sxs-lookup"><span data-stu-id="a336d-376">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="a336d-377">**Cikk:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="a336d-377">**Item:** *M9203*</span></span>
    - <span data-ttu-id="a336d-378">**Mennyiség:** *1 PL: 100 ea*</span><span class="sxs-lookup"><span data-stu-id="a336d-378">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="a336d-379">A cíkk leírása is itt látható.</span><span class="sxs-lookup"><span data-stu-id="a336d-379">The item description is also shown.</span></span>

1. <span data-ttu-id="a336d-380">Erősítse meg a betárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="a336d-380">Confirm the putaway work.</span></span>

    <span data-ttu-id="a336d-381">A beszerzési rendeléssor **Feladat** lapján a „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a336d-381">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="a336d-382">A **LINENUM** mező elérhető, úgyhogy fogadhatja a következő raklapot.</span><span class="sxs-lookup"><span data-stu-id="a336d-382">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

1. <span data-ttu-id="a336d-383">Válassza ki a lap tetején látható Menü gombot (**≡**), majd válassza a **Mégsem** lehetőséget a menühöz való visszatéréshez.</span><span class="sxs-lookup"><span data-stu-id="a336d-383">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Cancel** to return to the menu.</span></span>

<span data-ttu-id="a336d-384">Most már bezárhatja a mobilalkalmazást.</span><span class="sxs-lookup"><span data-stu-id="a336d-384">You can now close the mobile app.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]