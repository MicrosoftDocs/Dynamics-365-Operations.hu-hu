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
ms.openlocfilehash: 09b5770190fea9591f422b61ce6deedb2b9fa790
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994003"
---
# <a name="troubleshoot-warehouse-configuration"></a><span data-ttu-id="bb49f-103">Raktár konfigurálása – Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="bb49f-103">Troubleshoot warehouse configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bb49f-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben konfigurálja a Microsoft Dynamics 365 Supply Chain Management szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="bb49f-104">This topic describes how to fix common issues that you might encounter while you configure Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a><span data-ttu-id="bb49f-105">A következő hibaüzenet jelenik meg: „Az azonosítótábla vagy hely nem érvényes”.</span><span class="sxs-lookup"><span data-stu-id="bb49f-105">I receive the following error message: "The license plate or location is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb49f-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb49f-106">Issue description</span></span>

<span data-ttu-id="bb49f-107">Ez a hibaüzenet jelenik meg, amikor beolvas egy azonosítótábla-azonosítót vagy egy helyet.</span><span class="sxs-lookup"><span data-stu-id="bb49f-107">You receive this error message when you scan a license plate ID or location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb49f-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb49f-108">Issue resolution</span></span>

<span data-ttu-id="bb49f-109">Győződjön meg róla, hogy az azonosítótábla azonosítója nincs máshoz lefoglalva.</span><span class="sxs-lookup"><span data-stu-id="bb49f-109">Make sure that the license plate ID isn't reserved by something else.</span></span> <span data-ttu-id="bb49f-110">Ez a probléma akkor szokott előfordulni, ha a raktári alkalmazásban a felhasználó által beolvasott érték egy érvényes hely és egy érvényes azonosítótábla-azonosító.</span><span class="sxs-lookup"><span data-stu-id="bb49f-110">This issue used to occur when the value that a user scanned in the warehouse app was both a valid location and a valid license plate ID.</span></span> <span data-ttu-id="bb49f-111">Ez a probléma azonban a 10.0.11 verzióban ki lett javítva.</span><span class="sxs-lookup"><span data-stu-id="bb49f-111">However, this issue was resolved in version 10.0.11.</span></span>

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a><span data-ttu-id="bb49f-112">A következő hibaüzenet jelenik meg: „Azonosítótáblát meg kell határozni ehhez a helyhez”.</span><span class="sxs-lookup"><span data-stu-id="bb49f-112">I receive the following error message: "License plate must be specified for this location."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb49f-113">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb49f-113">Issue description</span></span>

<span data-ttu-id="bb49f-114">Ez a hibaüzenet akkor jelenik meg, ha egy olyan raktárat hoz létre, amely engedélyezve van a speciális raktárkezelésnél (WMS), majd a munka befejezése után megpróbálja megerősíteni a szállítmányt.</span><span class="sxs-lookup"><span data-stu-id="bb49f-114">You receive this error message if you create a transfer order by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb49f-115">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb49f-115">Issue resolution</span></span>

<span data-ttu-id="bb49f-116">Az **Alapértelmezett bevételezési hely** mező üres a raktár tranzitraktár „érkezési” raktárában.</span><span class="sxs-lookup"><span data-stu-id="bb49f-116">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="bb49f-117">A probléma megoldásához adjon meg egy alapértelmezett bevételezési helyet a tranzitraktárban.</span><span class="sxs-lookup"><span data-stu-id="bb49f-117">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="bb49f-118">Győződjön meg arról, hogy ez a hely azonosítótábla-vezérelt.</span><span class="sxs-lookup"><span data-stu-id="bb49f-118">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a><span data-ttu-id="bb49f-119">A következő hibaüzenet jelenik meg: „Nem hozható létre munkasablonsor a Készletállapot módosításához, mert a munka típusa érvénytelen.</span><span class="sxs-lookup"><span data-stu-id="bb49f-119">I receive the following error message: "You can't create a work template line for Inventory status change because the work type is not valid.</span></span> <span data-ttu-id="bb49f-120">Válasszon másik munkatípust.”</span><span class="sxs-lookup"><span data-stu-id="bb49f-120">Select a different work type."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb49f-121">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb49f-121">Issue description</span></span>

<span data-ttu-id="bb49f-122">Egy munkasablon esetében nem lehet kiválasztani a *Készletállapot módosítás* lehetőséget a **Munkasablon részletei** szakasz **Munka típusa** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="bb49f-122">For a work template, you can't select *Inventory status change* in the **Work type** column of the **Work template details** section.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb49f-123">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb49f-123">Issue resolution</span></span>

<span data-ttu-id="bb49f-124">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="bb49f-124">This behavior is by design.</span></span> <span data-ttu-id="bb49f-125">A *Készletállapot módosítás* munkatípust csak rendszerfolyamatok használják.</span><span class="sxs-lookup"><span data-stu-id="bb49f-125">The *Inventory status change* work type is used only by system processes.</span></span> <span data-ttu-id="bb49f-126">Ezt nem lehet konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="bb49f-126">It can't be configured.</span></span> <span data-ttu-id="bb49f-127">Mivel a munkatípusok listája számbavételként van rögzítve, a program nem tudja kiszűrni a **Munka típusa** legördülő menüből a felesleges bejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="bb49f-127">Because the list of work types is fixed as an enumeration, the extra entries can't be filtered out of the **Work type** drop-down menu.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="bb49f-128">A következő hibaüzenet jelenik meg: „A mennyiség nem érvényes az 1% egységre”.</span><span class="sxs-lookup"><span data-stu-id="bb49f-128">I receive the following error message: "The Quantity is not valid for unit 1%."</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb49f-129">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb49f-129">Issue description</span></span>

<span data-ttu-id="bb49f-130">A mennyiség nem érvényes az *ea* egységre, amikor olyan kitárolási munka van, amelynek egy helyén több azonosítótábla szerepel.</span><span class="sxs-lookup"><span data-stu-id="bb49f-130">The quantity isn't valid for the *ea* unit when there is picking work that has multiple license plates in one location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb49f-131">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb49f-131">Issue resolution</span></span>

<span data-ttu-id="bb49f-132">Ellenőrizze, hogy a kiadott termék vagy termék változatának **Egységszekvenciacsoport-azonosítója** és **Egységek átváltása** mezők helyesen vannak beállítva.</span><span class="sxs-lookup"><span data-stu-id="bb49f-132">Verify that the **Unit sequence group ID** and **Unit conversions** fields on the released product or product variant are set correctly.</span></span>

<span data-ttu-id="bb49f-133">Ne felejtse el, hogy a 10.0.15 (lásd: [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)) verzióban ki lett javítva a hibaüzenet.</span><span class="sxs-lookup"><span data-stu-id="bb49f-133">Note that the error message has been improved in version 10.0.15 (see [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span></span> <span data-ttu-id="bb49f-134">Az új hibaüzenet: „A mennyiség érvénytelen.</span><span class="sxs-lookup"><span data-stu-id="bb49f-134">The new error message is, "The quantity is not valid.</span></span> <span data-ttu-id="bb49f-135">Elvárt %1 %2.”</span><span class="sxs-lookup"><span data-stu-id="bb49f-135">Expected %1 %2."</span></span>

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a><span data-ttu-id="bb49f-136">Az értékesítési rendelés kitárolására szolgáló hely irányelveiben a több termékváltozat beállítás nem értékeli a több helyen utasítási műveleteket.</span><span class="sxs-lookup"><span data-stu-id="bb49f-136">In location directives for sales order put work, the multiple SKU option doesn't evaluate multiple location directive actions.</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb49f-137">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb49f-137">Issue description</span></span>

<span data-ttu-id="bb49f-138">Az *Értékesítési rendelések* munkarendelési típusának és a *Kitárolás* munkatípusnak nem kell több helyre vonatkozó irányelv-műveleteket kiértékelnie, ha a **Több termékváltozat** beállítás van kiválasztva.</span><span class="sxs-lookup"><span data-stu-id="bb49f-138">Location directives of the *Sales orders* work order type and the *Put* work type don't evaluate multiple location directive actions when the **Multiple SKU** option is selected.</span></span> <span data-ttu-id="bb49f-139">Csak az első hely irányelv-művelet van kiértékelve.</span><span class="sxs-lookup"><span data-stu-id="bb49f-139">Only the first location directive action is evaluated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb49f-140">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb49f-140">Issue resolution</span></span>

<span data-ttu-id="bb49f-141">Egy új funkció, a *Több termékváltozatos helyirányelvek összes műveletének kiértékelése* hozzá lett adva a 10.0.15 verzióhoz (lásd: [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span><span class="sxs-lookup"><span data-stu-id="bb49f-141">A new feature, *Evaluate all actions for Multi SKU location directives*, has been added in version 10.0.15 (see [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span></span> <span data-ttu-id="bb49f-142">Ez a funkció kiértékeli a több termékváltozatos helyirányelvek összes műveletét.</span><span class="sxs-lookup"><span data-stu-id="bb49f-142">This feature evaluates all actions for multi-SKU location directives.</span></span> <span data-ttu-id="bb49f-143">Ha szüksége van erre a funkcióra, használja a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőséget a funkció bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="bb49f-143">If you require this feature, use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn it on.</span></span>

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a><span data-ttu-id="bb49f-144">A raktári alkalmazás nem használható részleges kitárolásra.</span><span class="sxs-lookup"><span data-stu-id="bb49f-144">I can't use the warehouse app to do partial picking.</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb49f-145">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb49f-145">Issue description</span></span>

<span data-ttu-id="bb49f-146">Az értékesítési és átmozgatási rendelések esetében nem lehet kihagyni a cikkeket, és a részleges kitárolást.</span><span class="sxs-lookup"><span data-stu-id="bb49f-146">For sales and transfer orders, you can't skip items and do partial picking.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb49f-147">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb49f-147">Issue resolution</span></span>

<span data-ttu-id="bb49f-148">A **Mobileszköz menüpontjai** lapon az értékesítési rendelések és átmozgatási rendelések feldolgozására beállított menüelemekhez állítsa be az **Általános** gyorslap **Munka felosztásának engedélyezése** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="bb49f-148">On the **Mobile device menu items** page, for each menu item that is set up to process sales orders or transfer orders, set the **Allow splitting of work** option on the **General** FastTab to *Yes*.</span></span>

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a><span data-ttu-id="bb49f-149">Hogyan lehet létrehozni egy készletállapot módosítást a részleges mennyiségi munkához?</span><span class="sxs-lookup"><span data-stu-id="bb49f-149">How can I do an inventory status change for partial quantity work?</span></span>

### <a name="issue-description"></a><span data-ttu-id="bb49f-150">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="bb49f-150">Issue description</span></span>

<span data-ttu-id="bb49f-151">Egy köteg részleges mennyiségéről szeretne létrehozni egy készletállapot módosítást.</span><span class="sxs-lookup"><span data-stu-id="bb49f-151">You want to do an inventory status change for a partial quantity of a batch.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="bb49f-152">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="bb49f-152">Issue resolution</span></span>

<span data-ttu-id="bb49f-153">Ha engedélyezni szeretné, hogy a dolgozók elvégezzék ezt a módosítást, akkor létrehozhat egy menüelemet a raktári alkalmazás számára.</span><span class="sxs-lookup"><span data-stu-id="bb49f-153">To enable workers to make this change, you can create a menu item for the warehouse app.</span></span> <span data-ttu-id="bb49f-154">A **Mobileszköz menüpontok** oldalon hozzon létre (vagy szerkesszen) egy menüpontot a következő beállításokkal:</span><span class="sxs-lookup"><span data-stu-id="bb49f-154">On the **Mobile device menu items** page, create (or edit) a menu item that has the following settings:</span></span>

- <span data-ttu-id="bb49f-155">**Mód:** *Munka*</span><span class="sxs-lookup"><span data-stu-id="bb49f-155">**Mode:** *Work*</span></span>
- <span data-ttu-id="bb49f-156">**Meglévő munka használata:** *Nem*</span><span class="sxs-lookup"><span data-stu-id="bb49f-156">**Use existing work:** *No*</span></span>
- <span data-ttu-id="bb49f-157">**Munkalétrehozási folyamat:** *Áthelyezés*</span><span class="sxs-lookup"><span data-stu-id="bb49f-157">**Work creation process:** *Movement*</span></span>
- <span data-ttu-id="bb49f-158">**Készletállapot megjelenítése:** *Igen*</span><span class="sxs-lookup"><span data-stu-id="bb49f-158">**Display inventory status:** *Yes*</span></span>

<span data-ttu-id="bb49f-159">A lapon szükség szerint megadhat más mezőket is.</span><span class="sxs-lookup"><span data-stu-id="bb49f-159">You can set other fields on the page as you require.</span></span>
