---
title: Tervezett áttárolás
description: Ez a témakör a tervezett speciális áttárolást mutatja be, ahol a rendeléshez szükséges készletmennyiség a fogadástól vagy létrehozástól egyenesen a megfelelő kimenő vagy előkészítő területre irányul. A program a bejövő forrásból származó összes fennmaradó készletet a megfelelő tárolóhelyre irányítja a rendszeres elraktározási folyamaton keresztül.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 11e044e04e05c68af676bf97e6085e9975da5c1d
ms.sourcegitcommit: bef7bd2aac00d7eb837fd275d383b7a5c3f1c1ee
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/19/2021
ms.locfileid: "5911248"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="b69e6-104">Tervezett áttárolás</span><span class="sxs-lookup"><span data-stu-id="b69e6-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b69e6-105">Ez a témakör a speciális tervezett áttárolást mutatja be.</span><span class="sxs-lookup"><span data-stu-id="b69e6-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="b69e6-106">Az áttárolás egy raktározási folyamat, ahol a rendeléshez szükséges készletmennyiség a fogadástól vagy létrehozástól egyenesen a megfelelő kimenő vagy előkészítő területre irányul.</span><span class="sxs-lookup"><span data-stu-id="b69e6-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="b69e6-107">A program a bejövő forrásból származó összes fennmaradó készletet a megfelelő tárolóhelyre irányítja a rendszeres elraktározási folyamaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="b69e6-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="b69e6-108">Az áttárolás segítségével a dolgozók kihagyhatják a bejövő elraktározást és a készlet kimenő kitárolását, amely már ki van jelölve egy kimenő rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="b69e6-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="b69e6-109">Ezért a készlettel való tényleges munkavégzés száma ahol lehet minimalizálásra kerül.</span><span class="sxs-lookup"><span data-stu-id="b69e6-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="b69e6-110">Ezenkívül, mivel kevesebb az interakció a rendszerrel, nagyobb idő- és területmegtakarítás érhető el a raktárban.</span><span class="sxs-lookup"><span data-stu-id="b69e6-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="b69e6-111">Az áttárolás futtatása előtt konfigurálnia kell egy új áttárolási sablont, ahol az ellátási forrás és az áttárolás egyéb követelményhalmazai meg vannak határozva.</span><span class="sxs-lookup"><span data-stu-id="b69e6-111">Before you can run cross-docking, you must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="b69e6-112">A kimenő rendelés létrehozásakor a sort egy olyan bejövő rendeléssel szemben kell megjelölni, amely ugyanazt a tételt tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="b69e6-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span> <span data-ttu-id="b69e6-113">Az áttárolási sablonban kiválaszthatja az utasításkód mezőt, hasonlóan ahhoz, ahogyan a feltöltést és a beszerzési rendeléseket beállítja.</span><span class="sxs-lookup"><span data-stu-id="b69e6-113">You can select the directive code field on the cross-docking template, similar to the way you set up replenishment and purchase orders.</span></span>

<span data-ttu-id="b69e6-114">A bejövő rendelés bevételezése idején az áttárolási beállítás automatikusan azonosítja az áttárolási igényt, és létrehozza a szükséges mennyiséghez tartozó áthelyezési munkát a helyutasítás beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="b69e6-114">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="b69e6-115">A készlettranzakciók *nem* frissülnek, ha az áttárolási munka érvénytelenítve van, még akkor sem, ha a raktárkezelési paraméterekben be van kapcsolva a beállítás ehhez a tulajdonsághoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-115">Inventory transactions are *not* unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="b69e6-116">A tervezett áttárolási funkciók bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="b69e6-116">Turn on the planned cross docking features</span></span>

<span data-ttu-id="b69e6-117">Ha a rendszer még nem tartalmazza az ebben a témakörben leírt funkciókat, lépjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre, és a következő sorrendben kapcsolja be a következő funkciókat:</span><span class="sxs-lookup"><span data-stu-id="b69e6-117">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="b69e6-118">*Tervezett áttárolás*</span><span class="sxs-lookup"><span data-stu-id="b69e6-118">*Planned cross docking*</span></span>
1. <span data-ttu-id="b69e6-119">*Áttárolási sablonok helyutasításokkal*</span><span class="sxs-lookup"><span data-stu-id="b69e6-119">*Cross docking templates with location directives*</span></span>
    > [!NOTE]
    > <span data-ttu-id="b69e6-120">Ez a funkció lehetővé teszi, hogy az áttárolási sablonban is meg legyen adva az **Irányelvkód** mező, hasonlóan ahhoz, ahogyan a feltöltési sablonokat beállítja.</span><span class="sxs-lookup"><span data-stu-id="b69e6-120">This feature enables the **Directive code** field to be specified on the cross-docking template, similar to the way you set up replenishment templates.</span></span> <span data-ttu-id="b69e6-121">A funkció engedélyezése megakadályozza, hogy a rendszer irányelvkódot ad hozzá az áttárolási munkasablonsorokhoz a végső *betárolási* sorhoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-121">Enabling this feature prevents you from adding a directive code on the cross-docking work template lines for the final *Put* line.</span></span> <span data-ttu-id="b69e6-122">Így garantálható, hogy a munkasablonok figyelembe vétele előtt meg lehet határozni a végső berakodandó helyet a munka létrehozása során.</span><span class="sxs-lookup"><span data-stu-id="b69e6-122">This ensures that the final put location can be determined during work creation before considering work templates.</span></span>

## <a name="setup"></a><span data-ttu-id="b69e6-123">Beállítás</span><span class="sxs-lookup"><span data-stu-id="b69e6-123">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="b69e6-124">A terhelésfeladási metódusok újragenerálása</span><span class="sxs-lookup"><span data-stu-id="b69e6-124">Regenerate load posting methods</span></span>

<span data-ttu-id="b69e6-125">A tervezett áttárolás a rakományok feladási módjaként történik.</span><span class="sxs-lookup"><span data-stu-id="b69e6-125">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="b69e6-126">A funkció bekapcsolását követően újra létre kell hoznia a metódusokat.</span><span class="sxs-lookup"><span data-stu-id="b69e6-126">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="b69e6-127">Nyissa meg a **Raktárkezelés \> Beállítás \> Terhelésfeladási metódusok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-127">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="b69e6-128">A Művelet ablaktáblán válassza ki a **Metódusok újragenerálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b69e6-128">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="b69e6-129">Amikor a regenerálás befejeződött, olyan metódust kell látnia, amelynél a **Metódus neve** értéke *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="b69e6-129">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="b69e6-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b69e6-130">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="b69e6-131">Áttárolási sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="b69e6-131">Create a cross-docking template</span></span>

1. <span data-ttu-id="b69e6-132">Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Áttárolási sablonok** helyre.</span><span class="sxs-lookup"><span data-stu-id="b69e6-132">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="b69e6-133">Jelölje be a műveleti ablakban az **Új** lehetőséget az új sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b69e6-133">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="b69e6-134">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-134">In the header, set the following values:</span></span>

    - <span data-ttu-id="b69e6-135">**Sorozat:** *1*</span><span class="sxs-lookup"><span data-stu-id="b69e6-135">**Sequence:** *1*</span></span>

        <span data-ttu-id="b69e6-136">Ez a mező határozza meg, hogy milyen sorrendben kell kiértékelni a sablonokat a képernyőn.</span><span class="sxs-lookup"><span data-stu-id="b69e6-136">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="b69e6-137">**Áttárolási sablon azonosítója:** *51*</span><span class="sxs-lookup"><span data-stu-id="b69e6-137">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="b69e6-138">**Leírás:** *Raktár 51*</span><span class="sxs-lookup"><span data-stu-id="b69e6-138">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="b69e6-139">**Igénykiadási irányelv:** *Beszerzési nyugta előtt*</span><span class="sxs-lookup"><span data-stu-id="b69e6-139">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="b69e6-140">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="b69e6-140">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b69e6-141">A **Tervezés** gyorslapon beállíthatja a sablon működését.</span><span class="sxs-lookup"><span data-stu-id="b69e6-141">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="b69e6-142">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-142">Set the following values:</span></span>

    - <span data-ttu-id="b69e6-143">**Igény követelményei:** *Nincs*</span><span class="sxs-lookup"><span data-stu-id="b69e6-143">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="b69e6-144">Ez a mező az igénykészlet követelményeit határozza meg.</span><span class="sxs-lookup"><span data-stu-id="b69e6-144">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="b69e6-145">Ha a kiadást megelőzően a szükségletet a készlethez kell kapcsolni, jelölje be a *Jelölés* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-145">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="b69e6-146">Ha az igényt a kiadás előtt rendeléssel le kell foglalni a készletből, válassza a *Rendelés foglalása* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-146">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="b69e6-147">**Keresés típusa:** *Szállítmány helyei*</span><span class="sxs-lookup"><span data-stu-id="b69e6-147">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="b69e6-148">Ez a mező határozza meg, hogy az áttárolási munka a szállítmány előkészítési/rakodási helyeit használja-e, illetve hogy a helyet tartalmazó irányelveket kell-e használni a saját előkészítési/rakodási helyek megtalálására.</span><span class="sxs-lookup"><span data-stu-id="b69e6-148">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="b69e6-149">**Munkasablon:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="b69e6-149">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="b69e6-150">Ez a mező határozza meg, hogy milyen munkasablont kell használni az áttárolási munka létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="b69e6-150">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="b69e6-151">**Újraérvényesítés készlet fogadásakor:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="b69e6-151">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="b69e6-152">Ez a beállítás határozza meg, hogy a készletet a bevételezés során újra kell-e érvényesíteni.</span><span class="sxs-lookup"><span data-stu-id="b69e6-152">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="b69e6-153">Ha ez a beállítás *Igen* értékre van állítva, akkor mind a maximális idő ablak, mind a lejárati napok tartománya be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="b69e6-153">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="b69e6-154">**Utasításkód:** Hagyja üresen ezt a mezőt</span><span class="sxs-lookup"><span data-stu-id="b69e6-154">**Directive code:** Leave this field blank</span></span>

        <span data-ttu-id="b69e6-155">Ezt a lehetőséget az *Áttárolási sablonok helyutasításokkal* funkció engedélyezi.</span><span class="sxs-lookup"><span data-stu-id="b69e6-155">This option is enabled by the *Cross docking templates with location directives* feature.</span></span> <span data-ttu-id="b69e6-156">A rendszer helyadatokat használ, hogy meghatározza az áttárolási készlet ideális helyét, amelybe áttárolási készletet lehet áthelyezni.</span><span class="sxs-lookup"><span data-stu-id="b69e6-156">The system uses location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="b69e6-157">Ezt úgy állíthatja be, hogy az egyes áttárolási sablonokhoz egy-egy műveletkódot rendel hozzá.</span><span class="sxs-lookup"><span data-stu-id="b69e6-157">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="b69e6-158">Ha egy utasításkód meg van adva, a munka létrehozásakor a rendszer helyutasításokat fog keresni az utasításkód alapján.</span><span class="sxs-lookup"><span data-stu-id="b69e6-158">If a directive code is set, the system will search location directives by directive code when work is generated.</span></span> <span data-ttu-id="b69e6-159">Ily módon korlátozhatja az adott áttárolási sablonhoz használt helyutasításokat.</span><span class="sxs-lookup"><span data-stu-id="b69e6-159">In this way, you can limit location directives that are used for a particular cross-docking template.</span></span>

    - <span data-ttu-id="b69e6-160">**Ellenőrzési időablak:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="b69e6-160">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="b69e6-161">Ez a beállítás határozza meg, hogy ki kell-e értékelni a maximális időablakot a beszerzési forrás kiválasztása alkalmával.</span><span class="sxs-lookup"><span data-stu-id="b69e6-161">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="b69e6-162">Ha ez a beállítás *Igen* értékre van állítva, akkor elérhetővé válnak a maximális és a minimális időablakhoz kapcsolódó mezők.</span><span class="sxs-lookup"><span data-stu-id="b69e6-162">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="b69e6-163">**Maximális időablak:** *5*</span><span class="sxs-lookup"><span data-stu-id="b69e6-163">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="b69e6-164">Ez a mező meghatározza a készlet beérkezése és az igény távozása közötti maximális megengedett időtartamot.</span><span class="sxs-lookup"><span data-stu-id="b69e6-164">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="b69e6-165">**Maximális időablak egysége:** *Nap*</span><span class="sxs-lookup"><span data-stu-id="b69e6-165">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="b69e6-166">**Minimális időablak:** *0*</span><span class="sxs-lookup"><span data-stu-id="b69e6-166">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="b69e6-167">Ez a mező meghatározza a készlet beérkezése és az igény távozása közötti minimális megengedett időtartamot.</span><span class="sxs-lookup"><span data-stu-id="b69e6-167">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="b69e6-168">**Minimális időablak egysége:** *Nap*</span><span class="sxs-lookup"><span data-stu-id="b69e6-168">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="b69e6-169">**Lejárati napok tartománya:** *0*</span><span class="sxs-lookup"><span data-stu-id="b69e6-169">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="b69e6-170">*Első lejárat első ki (FEFO) feltételek:* Ez a mező azt határozza meg, hogy legfeljebb hány nap lehet a jelenleg a raktárban található először lejáró köteg lejárati dátuma és a bevételezési kötegben lejárati dátuma között.</span><span class="sxs-lookup"><span data-stu-id="b69e6-170">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="b69e6-171">A **Beszerzési források** gyorslapon meghatározhatja, hogy milyen típusú készlet érvényes ehhez a sablonhoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-171">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="b69e6-172">Válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-172">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="b69e6-173">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="b69e6-173">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b69e6-174">**Beszerzési forrás:** *Beszerzési rendelés*</span><span class="sxs-lookup"><span data-stu-id="b69e6-174">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="b69e6-175">Munkaosztály létrehozása</span><span class="sxs-lookup"><span data-stu-id="b69e6-175">Create a work class</span></span>

1. <span data-ttu-id="b69e6-176">Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.</span><span class="sxs-lookup"><span data-stu-id="b69e6-176">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="b69e6-177">Jelölje be a műveleti ablakban az **Új** lehetőséget a munkaosztály létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b69e6-177">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="b69e6-178">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-178">Set the following values:</span></span>

    - <span data-ttu-id="b69e6-179">**Munkaosztály azonosítója:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b69e6-179">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="b69e6-180">**Leírás:** *Áttárolás*</span><span class="sxs-lookup"><span data-stu-id="b69e6-180">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="b69e6-181">**Munkarendelés típusa:** *Áttárolás*</span><span class="sxs-lookup"><span data-stu-id="b69e6-181">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="b69e6-182">Munkasablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="b69e6-182">Create a work template</span></span>

1. <span data-ttu-id="b69e6-183">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="b69e6-183">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="b69e6-184">A **Munka rendeléstípusa** mezőben válassza ki az *Áttárolás* elemet.</span><span class="sxs-lookup"><span data-stu-id="b69e6-184">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="b69e6-185">A Művelet panelen válassza az **Új** lehetőséget egy sor hozzáadásához az **Áttekintés** laphoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-185">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="b69e6-186">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b69e6-187">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="b69e6-187">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b69e6-188">**Munkasablon:** *51 Áttárolás*</span><span class="sxs-lookup"><span data-stu-id="b69e6-188">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="b69e6-189">**Munkasablon leríása:** *51 Áttárolás*</span><span class="sxs-lookup"><span data-stu-id="b69e6-189">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="b69e6-190">A **Mentés** gombra kattintva elérhetővé válik a **Munkasablon részletei** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="b69e6-190">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="b69e6-191">A **Munkasablon részletei** gyorslapon válassza az **Új** parancsot, és adjon hozzá egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-191">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b69e6-192">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-192">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b69e6-193">**Munka típusa:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="b69e6-193">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="b69e6-194">**Munkaosztály azonosítója:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b69e6-194">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="b69e6-195">Válassza ki az **Új** lehetőséget egy további sor hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-195">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="b69e6-196">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="b69e6-196">**Work type:** *Put*</span></span>
    - <span data-ttu-id="b69e6-197">**Munkaosztály azonosítója:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b69e6-197">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="b69e6-198">Válassza a **Mentés** lehetőséget, és győződjön meg arról, hogy az **Érvényes** jelölőnégyzet be van jelölve az *51 Áttárolás* sablonhoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-198">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="b69e6-199">A *Kitárolás* és a *Betárolás* munkatípusok munkaosztályainak azonosnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="b69e6-199">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="b69e6-200">Helyutasítások létrehozása</span><span class="sxs-lookup"><span data-stu-id="b69e6-200">Create location directives</span></span>

1. <span data-ttu-id="b69e6-201">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="b69e6-201">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="b69e6-202">A bal oldali ablaktáblában állítsa a **Munkarendelés típusa** mezőt az *Áttárolás* értékre.</span><span class="sxs-lookup"><span data-stu-id="b69e6-202">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="b69e6-203">A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-203">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="b69e6-204">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="b69e6-204">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b69e6-205">**Név:** *51 Áttárolási betárolás*</span><span class="sxs-lookup"><span data-stu-id="b69e6-205">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="b69e6-206">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="b69e6-206">**Work type:** *Put*</span></span>
    - <span data-ttu-id="b69e6-207">**Telephely:** *5*</span><span class="sxs-lookup"><span data-stu-id="b69e6-207">**Site:** *5*</span></span>
    - <span data-ttu-id="b69e6-208">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="b69e6-208">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b69e6-209">A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="b69e6-209">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="b69e6-210">A **Sorok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-210">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b69e6-211">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-211">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b69e6-212">**Kezdő mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="b69e6-212">**From quantity:** *1*</span></span>
    - <span data-ttu-id="b69e6-213">**Záró mennyiség:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="b69e6-213">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="b69e6-214">A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="b69e6-214">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="b69e6-215">A **Helyutasítások műveletei** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-215">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b69e6-216">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-216">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b69e6-217">**Név:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="b69e6-217">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="b69e6-218">**Rögzített hely használata:** *Rögzített és nem rögzített helyek*</span><span class="sxs-lookup"><span data-stu-id="b69e6-218">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="b69e6-219">A **Mentés** gombra kattintva teheti elérhetővé a **Lekérdezés szerkesztése** gombot a **Helyutasítások műveletei** eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="b69e6-219">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="b69e6-220">A lekérdezéstervező szerkesztéséhez válassza a **Lekérdezés szerkesztése** parancsot.</span><span class="sxs-lookup"><span data-stu-id="b69e6-220">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="b69e6-221">Győződjön meg arról, hogy a **Tartomány** lapon a következő két sor konfigurálva van:</span><span class="sxs-lookup"><span data-stu-id="b69e6-221">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="b69e6-222">1. sor:</span><span class="sxs-lookup"><span data-stu-id="b69e6-222">Line 1:</span></span>

        - <span data-ttu-id="b69e6-223">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="b69e6-223">**Table:** *Locations*</span></span>
        - <span data-ttu-id="b69e6-224">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="b69e6-224">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="b69e6-225">**Mező:** *Raktár*</span><span class="sxs-lookup"><span data-stu-id="b69e6-225">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="b69e6-226">**Feltételek:** *51*</span><span class="sxs-lookup"><span data-stu-id="b69e6-226">**Criteria:** *51*</span></span>

    - <span data-ttu-id="b69e6-227">2. sor:</span><span class="sxs-lookup"><span data-stu-id="b69e6-227">Line 2:</span></span>

        - <span data-ttu-id="b69e6-228">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="b69e6-228">**Table:** *Locations*</span></span>
        - <span data-ttu-id="b69e6-229">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="b69e6-229">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="b69e6-230">**Mező:** *Hely*</span><span class="sxs-lookup"><span data-stu-id="b69e6-230">**Field:** *Location*</span></span>
        - <span data-ttu-id="b69e6-231">**Feltételek:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="b69e6-231">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="b69e6-232">Az lekérdezésszerkesztő bezárásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b69e6-232">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="b69e6-233">Mobileszköz-menüpont létrehozása</span><span class="sxs-lookup"><span data-stu-id="b69e6-233">Create a mobile device menu item</span></span>

1. <span data-ttu-id="b69e6-234">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="b69e6-234">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="b69e6-235">A bal oldali ablaktáblán látható menüelemek listájában válassza a **Beszerzés eltárolása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b69e6-235">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="b69e6-236">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="b69e6-236">Select **Edit**.</span></span>
1. <span data-ttu-id="b69e6-237">A **Munkaosztályok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-237">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b69e6-238">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-238">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b69e6-239">**Munkaosztály azonosítója:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b69e6-239">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="b69e6-240">**Munkarendelés típusa:** *Áttárolás*</span><span class="sxs-lookup"><span data-stu-id="b69e6-240">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="b69e6-241">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-241">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="b69e6-242">Forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="b69e6-242">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="b69e6-243">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="b69e6-243">Create a purchase order</span></span>

<span data-ttu-id="b69e6-244">A következő lépések szerint hozzon létre egy beszerzési rendelést a beszerzés forrásaként.</span><span class="sxs-lookup"><span data-stu-id="b69e6-244">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="b69e6-245">Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="b69e6-245">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="b69e6-246">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b69e6-246">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b69e6-247">Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-247">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b69e6-248">**Szállítói számla:** *104*</span><span class="sxs-lookup"><span data-stu-id="b69e6-248">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="b69e6-249">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="b69e6-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b69e6-250">Az **OK** gombra kattintva jegyezze fel a rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="b69e6-250">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="b69e6-251">A program új sort ad hozzá a **Beszerzési rendelés sorai** gyorslaphoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-251">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="b69e6-252">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-252">On this line, set the following values:</span></span>

    - <span data-ttu-id="b69e6-253">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b69e6-253">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b69e6-254">**Mennyiség:** *5*</span><span class="sxs-lookup"><span data-stu-id="b69e6-254">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="b69e6-255">Értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="b69e6-255">Create a sales order</span></span>

<span data-ttu-id="b69e6-256">A következő lépések szerint hozzon létre egy értékesítési rendelést a kereslet forrásaként.</span><span class="sxs-lookup"><span data-stu-id="b69e6-256">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="b69e6-257">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="b69e6-257">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b69e6-258">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="b69e6-258">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b69e6-259">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-259">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b69e6-260">**Vevőkód** *US-002*</span><span class="sxs-lookup"><span data-stu-id="b69e6-260">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="b69e6-261">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="b69e6-261">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b69e6-262">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-262">Select **OK**.</span></span>
1. <span data-ttu-id="b69e6-263">A program új sort ad hozzá az **Értékesítési rendelés sorai** gyorslaphoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-263">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b69e6-264">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="b69e6-264">On this line, set the following values:</span></span>

    - <span data-ttu-id="b69e6-265">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b69e6-265">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b69e6-266">**Mennyiség:** *3*</span><span class="sxs-lookup"><span data-stu-id="b69e6-266">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="b69e6-267">Tervezett áttárolás létrehozása</span><span class="sxs-lookup"><span data-stu-id="b69e6-267">Create planned cross-docking</span></span>

<span data-ttu-id="b69e6-268">Hajtsa végre az alábbi lépéseket az értékesítési rendelés tervezett áttárolásának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b69e6-268">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="b69e6-269">Válassza ki az imént létrehozott értékesítési rendelés **Értékesítési rendelés részletei** oldalán, a Művelet ablaktábla **Raktár** lapjának **Műveletek** csoportjában válassza a **Kiadás a raktárba** parancsot.</span><span class="sxs-lookup"><span data-stu-id="b69e6-269">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="b69e6-270">A raktári kiadási művelet létrehozza az értékesítési rendelés sorának szállítmányát és terhelési sorát, és megpróbálja lefoglalni a készletet.</span><span class="sxs-lookup"><span data-stu-id="b69e6-270">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="b69e6-271">Tájékoztató üzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="b69e6-271">You receive an informational message.</span></span> <span data-ttu-id="b69e6-272">A következő figyelmeztető üzenet is megjelenik: „Nem jött létre munka a(z) XXXX. hullámhoz.</span><span class="sxs-lookup"><span data-stu-id="b69e6-272">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="b69e6-273">A részleteket lásd a munkakészítési előzmények naplójában.”</span><span class="sxs-lookup"><span data-stu-id="b69e6-273">See the work creation history log for details."</span></span> <span data-ttu-id="b69e6-274">Ez a viselkedés várható, mert nincs készlet a raktárban.</span><span class="sxs-lookup"><span data-stu-id="b69e6-274">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="b69e6-275">Az **Értékesítési rendelés sorai** gyorslap **Raktár** menüjében válassza a **Szállítás részletes adatai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-275">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="b69e6-276">Megjelenik a **Szállítmány adatai** oldal, és az értékesítési rendeléshez létrehozott szállítmányt jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b69e6-276">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="b69e6-277">A **Terhelési sorok** gyorslapon figyelje meg, hogy a **Tervezett áttárolási mennyiség** mező értéke *3*.</span><span class="sxs-lookup"><span data-stu-id="b69e6-277">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="b69e6-278">Mivel a raktárban nem állt rendelkezésre készlet, de az áttárolási sablonban megadott időablakon belül egy érvényes beszerzési forrás fog megérkezni, a program létrehozta az áttárolási mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-278">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="b69e6-279">A **Terhelési sorok** gyorslapon válassza a **Tervezett áttárolás** lehetőséget, hogy megtekintse a létrehozott áttárolási részleteket.</span><span class="sxs-lookup"><span data-stu-id="b69e6-279">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="b69e6-280">Áttárolás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="b69e6-280">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="b69e6-281">Beszerzési rendelés fogadása a raktározási mobilalkalmazásban</span><span class="sxs-lookup"><span data-stu-id="b69e6-281">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="b69e6-282">A rendszer az 5 mennyiséget a beszerzési rendelésből a fogadó helyre fogja bevételezni, és két munkát hoz létre.</span><span class="sxs-lookup"><span data-stu-id="b69e6-282">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="b69e6-283">A létrehozott első munkaazonosítónak van egy *Áttárolás* értékű **Munkarendelés típusa** eleme, amely az értékesítési rendeléshez van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="b69e6-283">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="b69e6-284">A mennyiség 3, és a végső szállítási helyre van irányítva, így azonnal le lehet szállítani.</span><span class="sxs-lookup"><span data-stu-id="b69e6-284">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="b69e6-285">A létrehozott második munkaazonosítónak van egy *Beszerzési rendelések* értékű **Munkarendelés típusa** eleme, amely a beszerzési rendeléshez van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="b69e6-285">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="b69e6-286">A fennmaradó 2 mennyiséget nem lehetett áttárolni, és a rendszer az elraktározásra irányítja.</span><span class="sxs-lookup"><span data-stu-id="b69e6-286">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="b69e6-287">Jelentkezzen be a *51*-es raktárban lévő felhasználóként a mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="b69e6-287">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="b69e6-288">Lépjen a **Bejövő \> Beszerzés fogadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="b69e6-288">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="b69e6-289">A **PONum** mezőbe adja meg a beszerzési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="b69e6-289">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="b69e6-290">Írja be az *5* értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b69e6-290">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="b69e6-291">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-291">Select **OK**.</span></span>
1. <span data-ttu-id="b69e6-292">A következő lapon adja meg a **Cikk** mező számára az *A0001* értéket.</span><span class="sxs-lookup"><span data-stu-id="b69e6-292">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="b69e6-293">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-293">Select **OK**.</span></span>
1. <span data-ttu-id="b69e6-294">A következő oldalon hagyja jóvá a **PONum**, a **Cikk** és a **Mennyiség** értékét az **OK** gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="b69e6-294">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="b69e6-295">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="b69e6-295">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="b69e6-296">A kilépéshez válassza a **Mégse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-296">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="b69e6-297">Elraktározás az áttároláshoz és az ömlesztetthez</span><span class="sxs-lookup"><span data-stu-id="b69e6-297">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="b69e6-298">Jelenleg mindkét munkaazonosítónak ugyanaz a cél azonosítótáblája.</span><span class="sxs-lookup"><span data-stu-id="b69e6-298">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="b69e6-299">A következő lépések befejezéséhez be kell szereznie a munkaazonosítót és a cél azonosítótábla azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="b69e6-299">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="b69e6-300">Ezt az információt a beszerzési rendelés sorának és az értékesítési rendelés sorának munkaadataiból kaphatja meg.</span><span class="sxs-lookup"><span data-stu-id="b69e6-300">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="b69e6-301">Alternatív megoldásként felkeresheti a **Raktárkezelés \> Munka \> Munka részletei** pontot, és szűrhet a munkára, ahol a **Raktár** értéke *51*.</span><span class="sxs-lookup"><span data-stu-id="b69e6-301">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="b69e6-302">A mobileszközön nyissa meg a **Bejövő \> Beszerzés eltárolása** lehetőséget, és írja be a cél azonosítótáblát a munkából.</span><span class="sxs-lookup"><span data-stu-id="b69e6-302">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="b69e6-303">Az **Azonosító** mezőbe írja be a cél azonosítótábla azonosítóját a munka részleteiből.</span><span class="sxs-lookup"><span data-stu-id="b69e6-303">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="b69e6-304">Az áttárolási kitárolás oldalon megjeleníti a kitárolási helyet (*RECV*), a cél azonosítótáblát (*azonosítótábla*), a cikket (*A0001*) és a mennyiséget (*3*).</span><span class="sxs-lookup"><span data-stu-id="b69e6-304">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="b69e6-305">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-305">Select **OK**.</span></span>
1. <span data-ttu-id="b69e6-306">A **Cél LP** mezőbe írja be annak az azonosítótábla-azonosítónak a cél azonosítótábláját, amelyet a szállítási helyen el kell helyezni (áttárolni).</span><span class="sxs-lookup"><span data-stu-id="b69e6-306">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="b69e6-307">Tetszőleges azonosítótábla-azonosítót választhat.</span><span class="sxs-lookup"><span data-stu-id="b69e6-307">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="b69e6-308">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-308">Select **OK**.</span></span>
1. <span data-ttu-id="b69e6-309">A következő oldalon az **Azonosító** mezőbe írja be a cél azonosítótábla azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="b69e6-309">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="b69e6-310">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-310">Select **OK**.</span></span>
1. <span data-ttu-id="b69e6-311">Erősítse meg a munkát a fennmaradó 2 mennyiség kitárolásához, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b69e6-311">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="b69e6-312">A következő lapon válassza a **Kész** lehetőséget a kitárolási folyamat befejezéséhez, és az elraktározási folyamat megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="b69e6-312">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="b69e6-313">A mobilalkalmazás bemutatja a helyet és az azonosítótáblát, ahol a cikket el kell helyezni.</span><span class="sxs-lookup"><span data-stu-id="b69e6-313">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="b69e6-314">Az **OK** gombra kattintva erősítse meg az **Eltárolás** ömlesztett tárolóhelyet.</span><span class="sxs-lookup"><span data-stu-id="b69e6-314">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="b69e6-315">A következő lapon hagyja jóvá az **Eltárolás** áttárolást az **OK** gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="b69e6-315">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="b69e6-316">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="b69e6-316">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="b69e6-317">A kilépéshez válassza a **Mégse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b69e6-317">Select **Cancel** to exit.</span></span>

<span data-ttu-id="b69e6-318">A következő ábra bemutatja, hogy hogyan jelenhet meg a teljesített áttárolási munka a Microsoft Dynamics 365 Supply Chain Management rendszerben.</span><span class="sxs-lookup"><span data-stu-id="b69e6-318">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="b69e6-319">![Áttárolási munka befejezve](media/PlannedCrossDockingWork.png "Áttárolási munka befejezve")</span><span class="sxs-lookup"><span data-stu-id="b69e6-319">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]