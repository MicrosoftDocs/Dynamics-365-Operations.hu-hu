---
title: Raktár konfigurálása – Hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben konfigurálja a Microsoft Dynamics 365 Supply Chain Management szolgáltatást.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1fe285f05e5f1ddcb7bd206290b9954cbdaffc75
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2021
ms.locfileid: "5487097"
---
# <a name="troubleshoot-warehouse-configuration"></a><span data-ttu-id="689e5-103">Raktár konfigurálása – Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="689e5-103">Troubleshoot warehouse configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="689e5-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben konfigurálja a Microsoft Dynamics 365 Supply Chain Management szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="689e5-104">This topic describes how to fix common issues that you might encounter while you configure Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a><span data-ttu-id="689e5-105">A következő hibaüzenet jelenik meg: „Az azonosítótábla vagy hely nem érvényes”.</span><span class="sxs-lookup"><span data-stu-id="689e5-105">I receive the following error message: "The license plate or location is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="689e5-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="689e5-106">Issue description</span></span>

<span data-ttu-id="689e5-107">Ez a hibaüzenet jelenik meg, amikor beolvas egy azonosítótábla-azonosítót vagy egy helyet.</span><span class="sxs-lookup"><span data-stu-id="689e5-107">You receive this error message when you scan a license plate ID or location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="689e5-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="689e5-108">Issue resolution</span></span>

<span data-ttu-id="689e5-109">Győződjön meg róla, hogy az azonosítótábla azonosítója nincs máshoz lefoglalva.</span><span class="sxs-lookup"><span data-stu-id="689e5-109">Make sure that the license plate ID isn't reserved by something else.</span></span> <span data-ttu-id="689e5-110">Ez a probléma akkor szokott előfordulni, ha a raktári alkalmazásban a felhasználó által beolvasott érték egy érvényes hely és egy érvényes azonosítótábla-azonosító.</span><span class="sxs-lookup"><span data-stu-id="689e5-110">This issue used to occur when the value that a user scanned in the warehouse app was both a valid location and a valid license plate ID.</span></span> <span data-ttu-id="689e5-111">Ez a probléma azonban a 10.0.11 verzióban ki lett javítva.</span><span class="sxs-lookup"><span data-stu-id="689e5-111">However, this issue was resolved in version 10.0.11.</span></span>

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a><span data-ttu-id="689e5-112">A következő hibaüzenet jelenik meg: „Azonosítótáblát meg kell határozni ehhez a helyhez”.</span><span class="sxs-lookup"><span data-stu-id="689e5-112">I receive the following error message: "License plate must be specified for this location."</span></span>

### <a name="issue-description"></a><span data-ttu-id="689e5-113">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="689e5-113">Issue description</span></span>

<span data-ttu-id="689e5-114">Ez a hibaüzenet akkor jelenik meg, ha egy olyan raktárat hoz létre, amely engedélyezve van a speciális raktárkezelésnél (WMS), majd a munka befejezése után megpróbálja megerősíteni a szállítmányt.</span><span class="sxs-lookup"><span data-stu-id="689e5-114">You receive this error message if you create a transfer order by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="689e5-115">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="689e5-115">Issue resolution</span></span>

<span data-ttu-id="689e5-116">Az **Alapértelmezett bevételezési hely** mező üres a raktár tranzitraktár „érkezési” raktárában.</span><span class="sxs-lookup"><span data-stu-id="689e5-116">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="689e5-117">A probléma megoldásához adjon meg egy alapértelmezett bevételezési helyet a tranzitraktárban.</span><span class="sxs-lookup"><span data-stu-id="689e5-117">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="689e5-118">Győződjön meg arról, hogy ez a hely azonosítótábla-vezérelt.</span><span class="sxs-lookup"><span data-stu-id="689e5-118">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a><span data-ttu-id="689e5-119">A következő hibaüzenet jelenik meg: „Nem hozható létre munkasablonsor a Készletállapot módosításához, mert a munka típusa érvénytelen.</span><span class="sxs-lookup"><span data-stu-id="689e5-119">I receive the following error message: "You can't create a work template line for Inventory status change because the work type is not valid.</span></span> <span data-ttu-id="689e5-120">Válasszon másik munkatípust.”</span><span class="sxs-lookup"><span data-stu-id="689e5-120">Select a different work type."</span></span>

### <a name="issue-description"></a><span data-ttu-id="689e5-121">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="689e5-121">Issue description</span></span>

<span data-ttu-id="689e5-122">Egy munkasablon esetében nem lehet kiválasztani a *Készletállapot módosítás* lehetőséget a **Munkasablon részletei** szakasz **Munka típusa** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="689e5-122">For a work template, you can't select *Inventory status change* in the **Work type** column of the **Work template details** section.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="689e5-123">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="689e5-123">Issue resolution</span></span>

<span data-ttu-id="689e5-124">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="689e5-124">This behavior is by design.</span></span> <span data-ttu-id="689e5-125">A *Készletállapot módosítás* munkatípust csak rendszerfolyamatok használják.</span><span class="sxs-lookup"><span data-stu-id="689e5-125">The *Inventory status change* work type is used only by system processes.</span></span> <span data-ttu-id="689e5-126">Ezt nem lehet konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="689e5-126">It can't be configured.</span></span> <span data-ttu-id="689e5-127">Mivel a munkatípusok listája számbavételként van rögzítve, a program nem tudja kiszűrni a **Munka típusa** legördülő menüből a felesleges bejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="689e5-127">Because the list of work types is fixed as an enumeration, the extra entries can't be filtered out of the **Work type** drop-down menu.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="689e5-128">A következő hibaüzenet jelenik meg: „A mennyiség nem érvényes az 1% egységre”.</span><span class="sxs-lookup"><span data-stu-id="689e5-128">I receive the following error message: "The Quantity is not valid for unit 1%."</span></span>

### <a name="issue-description"></a><span data-ttu-id="689e5-129">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="689e5-129">Issue description</span></span>

<span data-ttu-id="689e5-130">A mennyiség nem érvényes az *ea* egységre, amikor olyan kitárolási munka van, amelynek egy helyén több azonosítótábla szerepel.</span><span class="sxs-lookup"><span data-stu-id="689e5-130">The quantity isn't valid for the *ea* unit when there is picking work that has multiple license plates in one location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="689e5-131">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="689e5-131">Issue resolution</span></span>

<span data-ttu-id="689e5-132">Ellenőrizze, hogy a kiadott termék vagy termék változatának **Egységszekvenciacsoport-azonosítója** és **Egységek átváltása** mezők helyesen vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="689e5-132">Verify that the **Unit sequence group ID** and **Unit conversions** fields on the released product or product variant are set correctly.</span></span>

<span data-ttu-id="689e5-133">Ne felejtse el, hogy a 10.0.15 (lásd: [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)) verzióban ki lett javítva a hibaüzenet.</span><span class="sxs-lookup"><span data-stu-id="689e5-133">Note that the error message has been improved in version 10.0.15 (see [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span></span> <span data-ttu-id="689e5-134">Az új hibaüzenet: „A mennyiség érvénytelen.</span><span class="sxs-lookup"><span data-stu-id="689e5-134">The new error message is, "The quantity is not valid.</span></span> <span data-ttu-id="689e5-135">Elvárt %1 %2.”</span><span class="sxs-lookup"><span data-stu-id="689e5-135">Expected %1 %2."</span></span>

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a><span data-ttu-id="689e5-136">Az értékesítési rendelés kitárolására szolgáló hely irányelveiben a több termékváltozat beállítás nem értékeli a több helyen utasítási műveleteket.</span><span class="sxs-lookup"><span data-stu-id="689e5-136">In location directives for sales order put work, the multiple SKU option doesn't evaluate multiple location directive actions.</span></span>

### <a name="issue-description"></a><span data-ttu-id="689e5-137">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="689e5-137">Issue description</span></span>

<span data-ttu-id="689e5-138">Az *Értékesítési rendelések* munkarendelési típusának és a *Kitárolás* munkatípusnak nem kell több helyre vonatkozó irányelv-műveleteket kiértékelnie, ha a **Több termékváltozat** beállítás van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="689e5-138">Location directives of the *Sales orders* work order type and the *Put* work type don't evaluate multiple location directive actions when the **Multiple SKU** option is selected.</span></span> <span data-ttu-id="689e5-139">Csak az első hely irányelv-művelet van kiértékelve.</span><span class="sxs-lookup"><span data-stu-id="689e5-139">Only the first location directive action is evaluated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="689e5-140">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="689e5-140">Issue resolution</span></span>

<span data-ttu-id="689e5-141">Egy új funkció, a *Több termékváltozatos helyirányelvek összes műveletének kiértékelése* hozzá lett adva a 10.0.15 verzióhoz (lásd: [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span><span class="sxs-lookup"><span data-stu-id="689e5-141">A new feature, *Evaluate all actions for Multi SKU location directives*, has been added in version 10.0.15 (see [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span></span> <span data-ttu-id="689e5-142">Ez a funkció kiértékeli a több termékváltozatos helyirányelvek összes műveletét.</span><span class="sxs-lookup"><span data-stu-id="689e5-142">This feature evaluates all actions for multi-SKU location directives.</span></span> <span data-ttu-id="689e5-143">Ha szüksége van erre a funkcióra, használja a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőséget a funkció bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="689e5-143">If you require this feature, use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn it on.</span></span>

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a><span data-ttu-id="689e5-144">A raktári alkalmazás nem használható részleges kitárolásra.</span><span class="sxs-lookup"><span data-stu-id="689e5-144">I can't use the warehouse app to do partial picking.</span></span>

### <a name="issue-description"></a><span data-ttu-id="689e5-145">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="689e5-145">Issue description</span></span>

<span data-ttu-id="689e5-146">Az értékesítési és átmozgatási rendelések esetében nem lehet kihagyni a cikkeket, és a részleges kitárolást.</span><span class="sxs-lookup"><span data-stu-id="689e5-146">For sales and transfer orders, you can't skip items and do partial picking.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="689e5-147">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="689e5-147">Issue resolution</span></span>

<span data-ttu-id="689e5-148">A **Mobileszköz menüpontjai** lapon az értékesítési rendelések és átmozgatási rendelések feldolgozására beállított menüelemekhez állítsa be az **Általános** gyorslap **Munka felosztásának engedélyezése** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="689e5-148">On the **Mobile device menu items** page, for each menu item that is set up to process sales orders or transfer orders, set the **Allow splitting of work** option on the **General** FastTab to *Yes*.</span></span>

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a><span data-ttu-id="689e5-149">Hogyan lehet létrehozni egy készletállapot módosítást a részleges mennyiségi munkához?</span><span class="sxs-lookup"><span data-stu-id="689e5-149">How can I do an inventory status change for partial quantity work?</span></span>

### <a name="issue-description"></a><span data-ttu-id="689e5-150">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="689e5-150">Issue description</span></span>

<span data-ttu-id="689e5-151">Egy köteg részleges mennyiségéről szeretne létrehozni egy készletállapot módosítást.</span><span class="sxs-lookup"><span data-stu-id="689e5-151">You want to do an inventory status change for a partial quantity of a batch.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="689e5-152">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="689e5-152">Issue resolution</span></span>

<span data-ttu-id="689e5-153">Ha engedélyezni szeretné, hogy a dolgozók elvégezzék ezt a módosítást, akkor létrehozhat egy menüelemet a raktári alkalmazás számára.</span><span class="sxs-lookup"><span data-stu-id="689e5-153">To enable workers to make this change, you can create a menu item for the warehouse app.</span></span> <span data-ttu-id="689e5-154">A **Mobileszköz menüpontok** oldalon hozzon létre (vagy szerkesszen) egy menüpontot a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="689e5-154">On the **Mobile device menu items** page, create (or edit) a menu item that has the following settings:</span></span>

- <span data-ttu-id="689e5-155">**Mód:** *Munka*</span><span class="sxs-lookup"><span data-stu-id="689e5-155">**Mode:** *Work*</span></span>
- <span data-ttu-id="689e5-156">**Meglévő munka használata:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="689e5-156">**Use existing work:** *No*</span></span>
- <span data-ttu-id="689e5-157">**Munkalétrehozási folyamat:** *Áthelyezés*</span><span class="sxs-lookup"><span data-stu-id="689e5-157">**Work creation process:** *Movement*</span></span>
- <span data-ttu-id="689e5-158">**Készletállapot megjelenítése:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="689e5-158">**Display inventory status:** *Yes*</span></span>

<span data-ttu-id="689e5-159">A lapon szükség szerint megadhat más mezőket is.</span><span class="sxs-lookup"><span data-stu-id="689e5-159">You can set other fields on the page as you require.</span></span>

## <a name="the-dock-management-profile-of-a-location-profile-is-not-preventing-inventory-types-from-being-mixed"></a><span data-ttu-id="689e5-160">A helyprofilok kikötőkezelési profilja nem akadályozza meg a készlettípusok vegyes kezelését.</span><span class="sxs-lookup"><span data-stu-id="689e5-160">The dock management profile of a location profile is not preventing inventory types from being mixed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="689e5-161">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="689e5-161">Issue description</span></span>

<span data-ttu-id="689e5-162">*Szállítmánykonszolidációs irányelveket* használ.</span><span class="sxs-lookup"><span data-stu-id="689e5-162">You are using *shipment consolidation policies*.</span></span> <span data-ttu-id="689e5-163">*Kikötőkezelési profilt* állított be egy *helyprofilhoz*, de a munka létrehozásakor a készlettípusok vegyesek a végleges helyen.</span><span class="sxs-lookup"><span data-stu-id="689e5-163">You have set up a *dock management profile* for a *location profile*, but when work is created, the inventory types are mixed at the final location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="689e5-164">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="689e5-164">Issue resolution</span></span>

<span data-ttu-id="689e5-165">A kikötőkezelési profilokhoz szükség van a munka előzetes felosztására.</span><span class="sxs-lookup"><span data-stu-id="689e5-165">Dock management profiles require work to be split up front.</span></span> <span data-ttu-id="689e5-166">Más szóval a kikötőkezelési profil azt várja, hogy egy munkafejlécben ne legyen több betárolási hely.</span><span class="sxs-lookup"><span data-stu-id="689e5-166">In other words, the dock management profile expects that a work header won't have multiple put locations.</span></span>

<span data-ttu-id="689e5-167">Ahhoz, hogy a kikötőkezelési profil hatékonyan kezelje a készletkötegek vegyítését, munkafejléc-törést kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="689e5-167">For the dock management profile to effectively manage the mixing of inventory, a work header break must be set up.</span></span>

<span data-ttu-id="689e5-168">Ebben a példában a kikötőkezelési profil úgy van beállítva, hogy a **Nem vegyíthető készlettípusok** értéke *Szállítmány azonosítója*, és ehhez munkafejléc-törést állítunk be:</span><span class="sxs-lookup"><span data-stu-id="689e5-168">In this example our dock management profile is configured such that **Inventory types that should not be mixed** is set to *Shipment ID*, and we'll set up a work header break for it:</span></span>

1. <span data-ttu-id="689e5-169">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="689e5-169">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="689e5-170">Válassza ki a szerkeszteni kívánt **Munkarendelés típusa** lehetőséget (például *Beszerzési rendelések*).</span><span class="sxs-lookup"><span data-stu-id="689e5-170">Select the **Work order type** to edit (for example, *Purchase orders*).</span></span>
1. <span data-ttu-id="689e5-171">Válassza ki a szerkeszteni kívánt munkasablont.</span><span class="sxs-lookup"><span data-stu-id="689e5-171">Select the work template to edit.</span></span>
1. <span data-ttu-id="689e5-172">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="689e5-172">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="689e5-173">Nyissa meg a **Rendezés** lapot, és adjon hozzá egy sort a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="689e5-173">Open the **Sorting** tab and add a row with the following settings:</span></span>
    - <span data-ttu-id="689e5-174">**Tábla** - *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="689e5-174">**Table** - *Temporary work transactions*</span></span>
    - <span data-ttu-id="689e5-175">**Származtatott tábla** - *Ideiglenes munkatranzakciók*</span><span class="sxs-lookup"><span data-stu-id="689e5-175">**Derived table** - *Temporary work transactions*</span></span>
    - <span data-ttu-id="689e5-176">**Mező** - *Szállítmány azonosítója*</span><span class="sxs-lookup"><span data-stu-id="689e5-176">**Field** - *Shipment ID*</span></span>
1. <span data-ttu-id="689e5-177">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="689e5-177">Select **OK**.</span></span>
1. <span data-ttu-id="689e5-178">Visszatér a **Munkasablonok** oldalra.</span><span class="sxs-lookup"><span data-stu-id="689e5-178">You return to the **Work templates** page.</span></span> <span data-ttu-id="689e5-179">A Műveleti ablaktáblán kattintson a **Munkafejléc-törések** elemre.</span><span class="sxs-lookup"><span data-stu-id="689e5-179">On the Action Pane, select **Work header breaks**.</span></span>
1. <span data-ttu-id="689e5-180">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="689e5-180">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="689e5-181">Jelölje be a **Mezőnév** *Szállítmány azonosítója* mezőhöz tartozó jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="689e5-181">Select the check box associated with the **Field name** *Shipment ID*.</span></span>
1. <span data-ttu-id="689e5-182">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="689e5-182">On the Action Pane, select **Save**.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
