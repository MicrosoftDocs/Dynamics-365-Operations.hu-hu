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
ms.openlocfilehash: 49807c90c145eee55fae2d515fd19925eb2d944c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810414"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="c4b2d-104">Tervezett áttárolás</span><span class="sxs-lookup"><span data-stu-id="c4b2d-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4b2d-105">Ez a témakör a speciális tervezett áttárolást mutatja be.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="c4b2d-106">Az áttárolás egy raktározási folyamat, ahol a rendeléshez szükséges készletmennyiség a fogadástól vagy létrehozástól egyenesen a megfelelő kimenő vagy előkészítő területre irányul.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="c4b2d-107">A program a bejövő forrásból származó összes fennmaradó készletet a megfelelő tárolóhelyre irányítja a rendszeres elraktározási folyamaton keresztül.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="c4b2d-108">Az áttárolás segítségével a dolgozók kihagyhatják a bejövő elraktározást és a készlet kimenő kitárolását, amely már ki van jelölve egy kimenő rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="c4b2d-109">Ezért a készlettel való tényleges munkavégzés száma ahol lehet minimalizálásra kerül.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="c4b2d-110">Ezenkívül, mivel kevesebb az interakció a rendszerrel, nagyobb idő- és területmegtakarítás érhető el a raktárban.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="c4b2d-111">Az áttárolás futtatása előtt a felhasználónak konfigurálnia kell egy új áttárolási sablont, ahol az ellátási forrás és az áttárolás egyéb követelményhalmazai meg vannak határozva.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="c4b2d-112">A kimenő rendelés létrehozásakor a sort egy olyan bejövő rendeléssel szemben kell megjelölni, amely ugyanazt a tételt tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="c4b2d-113">A bejövő rendelés bevételezése idején az áttárolási beállítás automatikusan azonosítja az áttárolási igényt, és létrehozza a szükséges mennyiséghez tartozó áthelyezési munkát a helyutasítás beállításai alapján.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="c4b2d-114">A készlettranzakciók **nem** frissülnek, ha az áttárolási munka érvénytelenítve van, még akkor sem, ha a raktárkezelési paraméterekben be van kapcsolva a beállítás ehhez a tulajdonsághoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="c4b2d-115">A tervezett áttárolási funkciók bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-115">Turn on the planned cross docking features</span></span>

<span data-ttu-id="c4b2d-116">Ha a rendszer még nem tartalmazza az ebben a témakörben leírt funkciókat, lépjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre, és a következő sorrendben kapcsolja be a következő funkciókat:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-116">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="c4b2d-117">*Tervezett áttárolás*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-117">*Planned cross docking*</span></span>
2. <span data-ttu-id="c4b2d-118">*Áttárolási sablonok helyutasításokkal*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-118">*Cross docking templates with location directives*</span></span>

## <a name="setup"></a><span data-ttu-id="c4b2d-119">Beállítás</span><span class="sxs-lookup"><span data-stu-id="c4b2d-119">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="c4b2d-120">A terhelésfeladási metódusok újragenerálása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-120">Regenerate load posting methods</span></span>

<span data-ttu-id="c4b2d-121">A tervezett áttárolás a rakományok feladási módjaként történik.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-121">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="c4b2d-122">A funkció bekapcsolását követően újra létre kell hoznia a metódusokat.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-122">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="c4b2d-123">Nyissa meg a **Raktárkezelés \> Beállítás \> Terhelésfeladási metódusok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-123">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="c4b2d-124">A Művelet ablaktáblán válassza ki a **Metódusok újragenerálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-124">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="c4b2d-125">Amikor a regenerálás befejeződött, olyan metódust kell látnia, amelynél a **Metódus neve** értéke *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-125">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="c4b2d-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-126">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="c4b2d-127">Áttárolási sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-127">Create a cross-docking template</span></span>

1. <span data-ttu-id="c4b2d-128">Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Áttárolási sablonok** helyre.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-128">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="c4b2d-129">Jelölje be a műveleti ablakban az **Új** lehetőséget az új sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-129">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="c4b2d-130">A fejlécben állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-130">In the header, set the following values:</span></span>

    - <span data-ttu-id="c4b2d-131">**Sorozat:** *1*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-131">**Sequence:** *1*</span></span>

        <span data-ttu-id="c4b2d-132">Ez a mező határozza meg, hogy milyen sorrendben kell kiértékelni a sablonokat a képernyőn.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-132">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="c4b2d-133">**Áttárolási sablon azonosítója:** *51*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-133">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="c4b2d-134">**Leírás:** *Raktár 51*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-134">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="c4b2d-135">**Igénykiadási irányelv:** *Beszerzési nyugta előtt*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-135">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="c4b2d-136">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-136">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="c4b2d-137">A **Tervezés** gyorslapon beállíthatja a sablon működését.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-137">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="c4b2d-138">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-138">Set the following values:</span></span>

    - <span data-ttu-id="c4b2d-139">**Igény követelményei:** *Nincs*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-139">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="c4b2d-140">Ez a mező az igénykészlet követelményeit határozza meg.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-140">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="c4b2d-141">Ha a kiadást megelőzően a szükségletet a készlethez kell kapcsolni, jelölje be a *Jelölés* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-141">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="c4b2d-142">Ha az igényt a kiadás előtt rendeléssel le kell foglalni a készletből, válassza a *Rendelés foglalása* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-142">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="c4b2d-143">**Keresés típusa:** *Szállítmány helyei*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-143">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="c4b2d-144">Ez a mező határozza meg, hogy az áttárolási munka a szállítmány előkészítési/rakodási helyeit használja-e, illetve hogy a helyet tartalmazó irányelveket kell-e használni a saját előkészítési/rakodási helyek megtalálására.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-144">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="c4b2d-145">**Munkasablon:** Hagyja üresen ezt a mezőt.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-145">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="c4b2d-146">Ez a mező határozza meg, hogy milyen munkasablont kell használni az áttárolási munka létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-146">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="c4b2d-147">**Újraérvényesítés készlet fogadásakor:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-147">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="c4b2d-148">Ez a beállítás határozza meg, hogy a készletet a bevételezés során újra kell-e érvényesíteni.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-148">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="c4b2d-149">Ha ez a beállítás *Igen* értékre van állítva, akkor mind a maximális idő ablak, mind a lejárati napok tartománya be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-149">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="c4b2d-150">**Utasításkód** Hagyja üresen ezt a mezőt</span><span class="sxs-lookup"><span data-stu-id="c4b2d-150">**Directive code** Leave this field blank</span></span>

        <span data-ttu-id="c4b2d-151">Ez a beállítás lehetővé teszi, hogy a rendszer helyadatokat használjon, hogy meghatározza az áttárolási készlet ideális helyét, amelybe áttárolási készletet lehet áthelyezni.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-151">This option enables the system to use location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="c4b2d-152">Ezt úgy állíthatja be, hogy az egyes áttárolási sablonokhoz egy-egy műveletkódot rendel hozzá.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-152">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="c4b2d-153">Minden egyes műveletkód egyedi helyutasítási műveletet azonosít.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-153">Each directive code identifies a unique location directive.</span></span>

    - <span data-ttu-id="c4b2d-154">**Ellenőrzési időablak:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-154">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="c4b2d-155">Ez a beállítás határozza meg, hogy ki kell-e értékelni a maximális időablakot a beszerzési forrás kiválasztása alkalmával.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-155">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="c4b2d-156">Ha ez a beállítás *Igen* értékre van állítva, akkor elérhetővé válnak a maximális és a minimális időablakhoz kapcsolódó mezők.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-156">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="c4b2d-157">**Maximális időablak:** *5*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-157">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="c4b2d-158">Ez a mező meghatározza a készlet beérkezése és az igény távozása közötti maximális megengedett időtartamot.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-158">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="c4b2d-159">**Maximális időablak egysége:** *Nap*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-159">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="c4b2d-160">**Minimális időablak:** *0*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-160">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="c4b2d-161">Ez a mező meghatározza a készlet beérkezése és az igény távozása közötti minimális megengedett időtartamot.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-161">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="c4b2d-162">**Minimális időablak egysége:** *Nap*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-162">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="c4b2d-163">**Lejárati napok tartománya:** *0*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-163">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="c4b2d-164">*Első lejárat első ki (FEFO) feltételek:* Ez a mező azt határozza meg, hogy legfeljebb hány nap lehet a jelenleg a raktárban található először lejáró köteg lejárati dátuma és a bevételezési kötegben lejárati dátuma között.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-164">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="c4b2d-165">A **Beszerzési források** gyorslapon meghatározhatja, hogy milyen típusú készlet érvényes ehhez a sablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-165">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="c4b2d-166">Válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-166">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="c4b2d-167">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-167">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="c4b2d-168">**Beszerzési forrás:** *Beszerzési rendelés*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-168">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="c4b2d-169">Munkaosztály létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-169">Create a work class</span></span>

1. <span data-ttu-id="c4b2d-170">Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-170">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="c4b2d-171">Jelölje be a műveleti ablakban az **Új** lehetőséget a munkaosztály létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-171">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="c4b2d-172">Adja meg az alábbi értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-172">Set the following values:</span></span>

    - <span data-ttu-id="c4b2d-173">**Munkaosztály azonosítója:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-173">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="c4b2d-174">**Leírás:** *Áttárolás*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-174">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="c4b2d-175">**Munkarendelés típusa:** *Áttárolás*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-175">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="c4b2d-176">Munkasablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-176">Create a work template</span></span>

1. <span data-ttu-id="c4b2d-177">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-177">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="c4b2d-178">A **Munka rendeléstípusa** mezőben válassza ki az *Áttárolás* elemet.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-178">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="c4b2d-179">A Művelet panelen válassza az **Új** lehetőséget egy sor hozzáadásához az **Áttekintés** laphoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-179">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="c4b2d-180">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c4b2d-181">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-181">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="c4b2d-182">**Munkasablon:** *51 Áttárolás*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-182">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="c4b2d-183">**Munkasablon leríása:** *51 Áttárolás*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-183">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="c4b2d-184">A **Mentés** gombra kattintva elérhetővé válik a **Munkasablon részletei** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-184">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="c4b2d-185">A **Munkasablon részletei** gyorslapon válassza az **Új** parancsot, és adjon hozzá egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-185">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="c4b2d-186">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c4b2d-187">**Munka típusa:** *Kitárolás*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-187">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="c4b2d-188">**Munkaosztály azonosítója:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-188">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="c4b2d-189">Válassza ki az **Új** lehetőséget egy további sor hozzáadásához, és állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-189">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="c4b2d-190">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-190">**Work type:** *Put*</span></span>
    - <span data-ttu-id="c4b2d-191">**Munkaosztály azonosítója:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-191">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="c4b2d-192">Válassza a **Mentés** lehetőséget, és győződjön meg arról, hogy az **Érvényes** jelölőnégyzet be van jelölve az *51 Áttárolás* sablonhoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-192">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="c4b2d-193">A *Kitárolás* és a *Betárolás* munkatípusok munkaosztályainak azonosnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-193">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="c4b2d-194">Helyutasítások létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-194">Create location directives</span></span>

1. <span data-ttu-id="c4b2d-195">Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-195">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="c4b2d-196">A bal oldali ablaktáblában állítsa a **Munkarendelés típusa** mezőt az *Áttárolás* értékre.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-196">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="c4b2d-197">A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-197">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="c4b2d-198">**Sorszám:** *1*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-198">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="c4b2d-199">**Név:** *51 Áttárolási betárolás*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-199">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="c4b2d-200">**Munka típusa:** *Eltárolás*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-200">**Work type:** *Put*</span></span>
    - <span data-ttu-id="c4b2d-201">**Telephely:** *5*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-201">**Site:** *5*</span></span>
    - <span data-ttu-id="c4b2d-202">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-202">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="c4b2d-203">A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-203">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="c4b2d-204">A **Sorok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-204">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="c4b2d-205">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-205">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c4b2d-206">**Kezdő mennyiség:** *1*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-206">**From quantity:** *1*</span></span>
    - <span data-ttu-id="c4b2d-207">**Záró mennyiség:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-207">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="c4b2d-208">A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-208">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="c4b2d-209">A **Helyutasítások műveletei** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-209">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="c4b2d-210">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-210">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c4b2d-211">**Név:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-211">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="c4b2d-212">**Rögzített hely használata:** *Rögzített és nem rögzített helyek*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-212">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="c4b2d-213">A **Mentés** gombra kattintva teheti elérhetővé a **Lekérdezés szerkesztése** gombot a **Helyutasítások műveletei** eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-213">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="c4b2d-214">A lekérdezéstervező szerkesztéséhez válassza a **Lekérdezés szerkesztése** parancsot.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-214">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="c4b2d-215">Győződjön meg arról, hogy a **Tartomány** lapon a következő két sor konfigurálva van:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-215">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="c4b2d-216">1. sor:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-216">Line 1:</span></span>

        - <span data-ttu-id="c4b2d-217">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-217">**Table:** *Locations*</span></span>
        - <span data-ttu-id="c4b2d-218">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-218">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="c4b2d-219">**Mező:** *Raktár*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-219">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="c4b2d-220">**Feltételek:** *51*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-220">**Criteria:** *51*</span></span>

    - <span data-ttu-id="c4b2d-221">2. sor:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-221">Line 2:</span></span>

        - <span data-ttu-id="c4b2d-222">**Tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-222">**Table:** *Locations*</span></span>
        - <span data-ttu-id="c4b2d-223">**Származtatott tábla:** *Helyek*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-223">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="c4b2d-224">**Mező:** *Hely*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-224">**Field:** *Location*</span></span>
        - <span data-ttu-id="c4b2d-225">**Feltételek:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-225">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="c4b2d-226">Az lekérdezésszerkesztő bezárásához kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-226">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="c4b2d-227">Mobileszköz-menüpont létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-227">Create a mobile device menu item</span></span>

1. <span data-ttu-id="c4b2d-228">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-228">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="c4b2d-229">A bal oldali ablaktáblán látható menüelemek listájában válassza a **Beszerzés eltárolása** elemet.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-229">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="c4b2d-230">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-230">Select **Edit**.</span></span>
1. <span data-ttu-id="c4b2d-231">A **Munkaosztályok** gyorslapon válassza az **Új** parancsot, ha egy sort szeretne hozzáadni a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-231">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="c4b2d-232">Az új sorban állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c4b2d-233">**Munkaosztály azonosítója:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-233">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="c4b2d-234">**Munkarendelés típusa:** *Áttárolás*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-234">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="c4b2d-235">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-235">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="c4b2d-236">Forgatókönyv</span><span class="sxs-lookup"><span data-stu-id="c4b2d-236">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="c4b2d-237">Beszerzési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-237">Create a purchase order</span></span>

<span data-ttu-id="c4b2d-238">A következő lépések szerint hozzon létre egy beszerzési rendelést a beszerzés forrásaként.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-238">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="c4b2d-239">Menjen a **Beszerzés és forrás \> Beszerzési rendelés \> Összes beszerzési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-239">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="c4b2d-240">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-240">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c4b2d-241">Az **Beszerzési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-241">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c4b2d-242">**Szállítói számla:** *104*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-242">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="c4b2d-243">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-243">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="c4b2d-244">Az **OK** gombra kattintva jegyezze fel a rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-244">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="c4b2d-245">A program új sort ad hozzá a **Beszerzési rendelés sorai** gyorslaphoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-245">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="c4b2d-246">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-246">On this line, set the following values:</span></span>

    - <span data-ttu-id="c4b2d-247">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-247">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="c4b2d-248">**Mennyiség:** *5*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-248">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="c4b2d-249">Értékesítési rendelés létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-249">Create a sales order</span></span>

<span data-ttu-id="c4b2d-250">A következő lépések szerint hozzon létre egy értékesítési rendelést a kereslet forrásaként.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-250">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="c4b2d-251">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-251">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="c4b2d-252">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-252">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c4b2d-253">Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-253">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c4b2d-254">**Vevőkód** *US-002*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-254">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="c4b2d-255">**Raktár:** *51*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-255">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="c4b2d-256">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-256">Select **OK**.</span></span>
1. <span data-ttu-id="c4b2d-257">A program új sort ad hozzá az **Értékesítési rendelés sorai** gyorslaphoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-257">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="c4b2d-258">Ezen a soron állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="c4b2d-258">On this line, set the following values:</span></span>

    - <span data-ttu-id="c4b2d-259">**Cikkszám:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-259">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="c4b2d-260">**Mennyiség:** *3*</span><span class="sxs-lookup"><span data-stu-id="c4b2d-260">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="c4b2d-261">Tervezett áttárolás létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-261">Create planned cross-docking</span></span>

<span data-ttu-id="c4b2d-262">Hajtsa végre az alábbi lépéseket az értékesítési rendelés tervezett áttárolásának létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-262">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="c4b2d-263">Válassza ki az imént létrehozott értékesítési rendelés **Értékesítési rendelés részletei** oldalán, a Művelet ablaktábla **Raktár** lapjának **Műveletek** csoportjában válassza a **Kiadás a raktárba** parancsot.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-263">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c4b2d-264">A raktári kiadási művelet létrehozza az értékesítési rendelés sorának szállítmányát és terhelési sorát, és megpróbálja lefoglalni a készletet.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-264">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="c4b2d-265">Tájékoztató üzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-265">You receive an informational message.</span></span> <span data-ttu-id="c4b2d-266">A következő figyelmeztető üzenet is megjelenik: „Nem jött létre munka a(z) XXXX. hullámhoz.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-266">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="c4b2d-267">A részleteket lásd a munkakészítési előzmények naplójában.”</span><span class="sxs-lookup"><span data-stu-id="c4b2d-267">See the work creation history log for details."</span></span> <span data-ttu-id="c4b2d-268">Ez a viselkedés várható, mert nincs készlet a raktárban.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-268">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="c4b2d-269">Az **Értékesítési rendelés sorai** gyorslap **Raktár** menüjében válassza a **Szállítás részletes adatai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-269">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="c4b2d-270">Megjelenik a **Szállítmány adatai** oldal, és az értékesítési rendeléshez létrehozott szállítmányt jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-270">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="c4b2d-271">A **Terhelési sorok** gyorslapon figyelje meg, hogy a **Tervezett áttárolási mennyiség** mező értéke *3*.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-271">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="c4b2d-272">Mivel a raktárban nem állt rendelkezésre készlet, de az áttárolási sablonban megadott időablakon belül egy érvényes beszerzési forrás fog megérkezni, a program létrehozta az áttárolási mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-272">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="c4b2d-273">A **Terhelési sorok** gyorslapon válassza a **Tervezett áttárolás** lehetőséget, hogy megtekintse a létrehozott áttárolási részleteket.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-273">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="c4b2d-274">Áttárolás feldolgozása</span><span class="sxs-lookup"><span data-stu-id="c4b2d-274">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="c4b2d-275">Beszerzési rendelés fogadása a raktározási mobilalkalmazásban</span><span class="sxs-lookup"><span data-stu-id="c4b2d-275">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="c4b2d-276">A rendszer az 5 mennyiséget a beszerzési rendelésből a fogadó helyre fogja bevételezni, és két munkát hoz létre.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-276">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="c4b2d-277">A létrehozott első munkaazonosítónak van egy *Áttárolás* értékű **Munkarendelés típusa** eleme, amely az értékesítési rendeléshez van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-277">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="c4b2d-278">A mennyiség 3, és a végső szállítási helyre van irányítva, így azonnal le lehet szállítani.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-278">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="c4b2d-279">A létrehozott második munkaazonosítónak van egy *Beszerzési rendelések* értékű **Munkarendelés típusa** eleme, amely a beszerzési rendeléshez van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-279">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="c4b2d-280">A fennmaradó 2 mennyiséget nem lehetett áttárolni, és a rendszer az elraktározásra irányítja.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-280">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="c4b2d-281">Jelentkezzen be a *51*-es raktárban lévő felhasználóként a mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-281">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="c4b2d-282">Lépjen a **Bejövő \> Beszerzés fogadása** elemre.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-282">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="c4b2d-283">A **PONum** mezőbe adja meg a beszerzési rendelés számát.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-283">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="c4b2d-284">Írja be az *5* értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-284">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="c4b2d-285">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-285">Select **OK**.</span></span>
1. <span data-ttu-id="c4b2d-286">A következő lapon adja meg a **Cikk** mező számára az *A0001* értéket.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-286">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="c4b2d-287">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-287">Select **OK**.</span></span>
1. <span data-ttu-id="c4b2d-288">A következő oldalon hagyja jóvá a **PONum**, a **Cikk** és a **Mennyiség** értékét az **OK** gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-288">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="c4b2d-289">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-289">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="c4b2d-290">A kilépéshez válassza a **Mégse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-290">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="c4b2d-291">Elraktározás az áttároláshoz és az ömlesztetthez</span><span class="sxs-lookup"><span data-stu-id="c4b2d-291">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="c4b2d-292">Jelenleg mindkét munkaazonosítónak ugyanaz a cél azonosítótáblája.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-292">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="c4b2d-293">A következő lépések befejezéséhez be kell szereznie a munkaazonosítót és a cél azonosítótábla azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-293">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="c4b2d-294">Ezt az információt a beszerzési rendelés sorának és az értékesítési rendelés sorának munkaadataiból kaphatja meg.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-294">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="c4b2d-295">Alternatív megoldásként felkeresheti a **Raktárkezelés \> Munka \> Munka részletei** pontot, és szűrhet a munkára, ahol a **Raktár** értéke *51*.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-295">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="c4b2d-296">A mobileszközön nyissa meg a **Bejövő \> Beszerzés eltárolása** lehetőséget, és írja be a cél azonosítótáblát a munkából.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-296">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="c4b2d-297">Az **Azonosító** mezőbe írja be a cél azonosítótábla azonosítóját a munka részleteiből.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-297">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="c4b2d-298">Az áttárolási kitárolás oldalon megjeleníti a kitárolási helyet (*RECV*), a cél azonosítótáblát (*azonosítótábla*), a cikket (*A0001*) és a mennyiséget (*3*).</span><span class="sxs-lookup"><span data-stu-id="c4b2d-298">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="c4b2d-299">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-299">Select **OK**.</span></span>
1. <span data-ttu-id="c4b2d-300">A **Cél LP** mezőbe írja be annak az azonosítótábla-azonosítónak a cél azonosítótábláját, amelyet a szállítási helyen el kell helyezni (áttárolni).</span><span class="sxs-lookup"><span data-stu-id="c4b2d-300">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="c4b2d-301">Tetszőleges azonosítótábla-azonosítót választhat.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-301">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="c4b2d-302">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-302">Select **OK**.</span></span>
1. <span data-ttu-id="c4b2d-303">A következő oldalon az **Azonosító** mezőbe írja be a cél azonosítótábla azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-303">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="c4b2d-304">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-304">Select **OK**.</span></span>
1. <span data-ttu-id="c4b2d-305">Erősítse meg a munkát a fennmaradó 2 mennyiség kitárolásához, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-305">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="c4b2d-306">A következő lapon válassza a **Kész** lehetőséget a kitárolási folyamat befejezéséhez, és az elraktározási folyamat megkezdéséhez.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-306">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="c4b2d-307">A mobilalkalmazás bemutatja a helyet és az azonosítótáblát, ahol a cikket el kell helyezni.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-307">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="c4b2d-308">Az **OK** gombra kattintva erősítse meg az **Eltárolás** ömlesztett tárolóhelyet.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-308">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="c4b2d-309">A következő lapon hagyja jóvá az **Eltárolás** áttárolást az **OK** gombra kattintva.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-309">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="c4b2d-310">A „Munka befejezve” üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-310">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="c4b2d-311">A kilépéshez válassza a **Mégse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-311">Select **Cancel** to exit.</span></span>

<span data-ttu-id="c4b2d-312">A következő ábra bemutatja, hogy hogyan jelenhet meg a teljesített áttárolási munka a Microsoft Dynamics 365 Supply Chain Management rendszerben.</span><span class="sxs-lookup"><span data-stu-id="c4b2d-312">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="c4b2d-313">![Áttárolási munka befejezve](media/PlannedCrossDockingWork.png "Áttárolási munka befejezve")</span><span class="sxs-lookup"><span data-stu-id="c4b2d-313">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]