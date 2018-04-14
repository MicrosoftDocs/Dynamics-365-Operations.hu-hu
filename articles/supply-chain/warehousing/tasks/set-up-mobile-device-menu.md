--- 
title: "Mobileszköz-menüelem beállítása a beszerzési rendelés munkájának befejezéséhez"
description: "Ez az eljárás bemutatja, hogy hogyan kerül sor a mobileszköz menüelemeinek beállítására."
author: BibiSp
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 37010003ad638e068ed7650532da29c6dbc033cb
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-in-a-purchase-order"></a><span data-ttu-id="d0c7c-103">Mobileszköz-menüelem beállítása a beszerzési rendelés munkájának befejezéséhez</span><span class="sxs-lookup"><span data-stu-id="d0c7c-103">Set up a mobile device menu item for completing work in a purchase order</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d0c7c-104">Ez az eljárás bemutatja, hogy hogyan kerül sor a mobileszköz menüelemeinek beállítására.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-104">This procedure shows how to set up a Mobile device menu item.</span></span> <span data-ttu-id="d0c7c-105">Ebben a példában, ez a menüpont a Beszerzési rendelés típusú munkák végrehajtásához használatos.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-105">In this example, the menu item is used for performing work of type Purchase order.</span></span> <span data-ttu-id="d0c7c-106">A menüponthoz társított munkaosztály határozza meg, hogy melyik munka érvényes.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-106">The work class that’s associated with the menu item determines which work is valid.</span></span> <span data-ttu-id="d0c7c-107">Ezt az útmutatót használhatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="d0c7c-108">Ezt az eljárást általában a raktárvezető követi nyomon.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-108">This procedure is typically carried out by a warehouse manager.</span></span>


## <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="d0c7c-109">Mobileszköz-menüpont létrehozása</span><span class="sxs-lookup"><span data-stu-id="d0c7c-109">Create a mobile device menu item</span></span>
1. <span data-ttu-id="d0c7c-110">Ugrás a Mobileszköz menüpontokhoz.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-110">Go to Mobile device menu items.</span></span>
2. <span data-ttu-id="d0c7c-111">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-111">Click New.</span></span>
3. <span data-ttu-id="d0c7c-112">Írjon be egy értéket a Menüelem neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-112">In the Menu item name field, type a value.</span></span>
    * <span data-ttu-id="d0c7c-113">Egyedi érték megadása.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-113">Enter a unique value.</span></span> <span data-ttu-id="d0c7c-114">Ha például beírhatja a „Beszerzési rendelés áthelyezés” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-114">For example, you could type POMove.</span></span> <span data-ttu-id="d0c7c-115">Jegyezze meg az értéket, később szüksége lesz rá.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-115">Remember the value, you'll need it later.</span></span>  
4. <span data-ttu-id="d0c7c-116">Érték beírása a Címmezőbe.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-116">In the Title field, type a value.</span></span>
    * <span data-ttu-id="d0c7c-117">Ez az a cím, amely a felhasználók mobileszközein a jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-117">This is the title which will be displayed on the mobile device.</span></span> <span data-ttu-id="d0c7c-118">Ha például beírhatja a „Beszerzési rendelés áthelyezés” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-118">For example, you could type PO Move.</span></span>  
5. <span data-ttu-id="d0c7c-119">A Mód mezőben válassza ki a „Munka” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-119">In the Mode field, select 'Work'.</span></span>
6. <span data-ttu-id="d0c7c-120">A Meglévő munka használata mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-120">Select Yes in the Use existing work field.</span></span>
    * <span data-ttu-id="d0c7c-121">A mobileszköz-menüpont meglévő munkához használatos.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-121">This mobile device menu item is used to perform existing work.</span></span> <span data-ttu-id="d0c7c-122">Ezért ennek az értéknek Igennek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-122">Therefore you must set this value to Yes.</span></span>  
    * <span data-ttu-id="d0c7c-123">A Készletállapot megjelenítése mező meghatározza, hogy az aktuális készlet készletállapota megjelenjen raktári dolgozó mobileszközén.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-123">The Display inventory status field determines whether the inventory status of the on-hand inventory will be displayed to the warehouse worker on the mobile device.</span></span>  
7. <span data-ttu-id="d0c7c-124">Az Irányítja mezőben válassza a „Rendszercsoportosítás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-124">In the Directed by field, select 'System grouping'.</span></span>
    * <span data-ttu-id="d0c7c-125">Ha valamit kijelöl az Irányítja mezőben, további mezők jelennek meg ezen a lapon az Általános szakaszban.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-125">When you select something in the Directed by field, additional fields appear in the General section on this page.</span></span> <span data-ttu-id="d0c7c-126">A megjelenő mezők attól függenek, hogy Ön mit jelölt ki.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-126">The fields that appear depend on what you selected.</span></span> <span data-ttu-id="d0c7c-127">A Rendszercsoportosítás kijelölésekor 2 új mező kerül hozzáadásra.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-127">When you select System grouping, two new fields are added.</span></span> <span data-ttu-id="d0c7c-128">Ezek magyarázata alább látható.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-128">These are explained below.</span></span>  
8. <span data-ttu-id="d0c7c-129">Írja be a Rendszer-csoportosítás mezőbe a „WorkPoolId” szöveget.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-129">In the System grouping field, select 'WorkPoolId'.</span></span>
    * <span data-ttu-id="d0c7c-130">Amikor a raktári dolgozók megnyitják a menüpontot, a munkagyűjtő azonosító ellenőrzése szükséges lesz.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-130">When warehouse workers open this menu item, they’ll be asked to scan a Work pool ID.</span></span> <span data-ttu-id="d0c7c-131">Minden, ehhez a menüponthoz rendelt munkarendelés ezzel a Munkagyűjtő azonosítóval és minden Megnyitott munkarendeléssor munkaosztálya a felhasználóhoz kerül.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-131">All work orders with this Work pool ID and open work order lines with one of the work classes added to this menu item will be pushed to the user.</span></span>  
9. <span data-ttu-id="d0c7c-132">Írjon be egy értéket a Rendszer-csoportosítási címke mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-132">In the System grouping label field, type a value.</span></span>
    * <span data-ttu-id="d0c7c-133">Ez a szöveg jelenik meg a mobileszköz-felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-133">This is the text displayed to the user on the mobile device.</span></span> <span data-ttu-id="d0c7c-134">Például beírhatja a „Munkagyűjtő” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-134">For example, you could type Work pool.</span></span>  
10. <span data-ttu-id="d0c7c-135">Válassza az Igen lehetőséget az Azonosítótábla felülbírálása betároláskor mezőben.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-135">Select Yes in the Override license plate during put field.</span></span>
    * <span data-ttu-id="d0c7c-136">Ez a beállítás lehetővé teszi, hogy a raktárosok felülírják a cél azonosítótáblát, amikor azonosítótáblás szabályozású helyre kerülnek elemek.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-136">This option allows warehouse workers to override the target license plate when items are put down on a license plate controlled location.</span></span>  
11. <span data-ttu-id="d0c7c-137">Válassza az Igen lehetőséget a Csoportos betárolás mezőben.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-137">Select Yes in the Group put away field.</span></span>
    * <span data-ttu-id="d0c7c-138">Ha a betárolási sorok a munkarendelésen ugyanazon a helyen találhatók, a felhasználó egy összevont Elhelyezési utasítást fog kapni az összes sorhoz.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-138">If all the Put lines on the work order share the same location, the user will receive one combined Put instruction for all lines.</span></span>  
    * <span data-ttu-id="d0c7c-139">Vizsgálati sablon azonosítója: Egy munkavizsgálati sablon lehetővé teszi egy menüpont munkafolyamatának megszakítását más művelet végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-139">Audit template ID: A work audit template allows you to specify that the work process for a menu item should be interrupted so that another operation can be performed.</span></span> <span data-ttu-id="d0c7c-140">Például ha ez a menüpont a bejövő munkához áll rendelkezésre, a vizsgálati sablon megkövetelheti, hogy a dolgozó ellenőrizze a hőmérsékletet.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-140">For example, if this menu item is for inbound work, the audit template might require that the worker checks the temperature.</span></span> <span data-ttu-id="d0c7c-141">A vizsgálati sablonban van megadva az a pont ahol a folyamat megszakad – ez lehet például a munka kezdése vagy befejezése, illetve az állapot megváltozása.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-141">The point at which the process is interrupted is specified on the audit template and can be, for example, when work is started or completed, or when its status changes.</span></span>  
12. <span data-ttu-id="d0c7c-142">Bontsa ki a Munkaosztályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-142">Expand the Work classes section.</span></span>
13. <span data-ttu-id="d0c7c-143">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-143">Click New.</span></span>
14. <span data-ttu-id="d0c7c-144">Írja be a Munkaosztály azonosítója mezőbe a „Beszerzés” szöveget.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-144">In the Work class ID field, type 'Purchase'.</span></span>
    * <span data-ttu-id="d0c7c-145">A munkagyűjtő korlátozza a munkát, amelyre a menüelem használható.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-145">The work pool restricts the work that the menu item can be used for.</span></span> <span data-ttu-id="d0c7c-146">Ebben az esetben a Munkaosztály azonosító beszerzése ponttal rendelkező megnyitott munkarendeléssorok fogják használni.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-146">In this case it will be used for open work order lines that have the Purchase work class ID.</span></span>  
15. <span data-ttu-id="d0c7c-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-147">Click Save.</span></span>

## <a name="set-up-work-confirmation"></a><span data-ttu-id="d0c7c-148">Munkamegerősítés beállítása</span><span class="sxs-lookup"><span data-stu-id="d0c7c-148">Set up work confirmation</span></span>
1. <span data-ttu-id="d0c7c-149">Kattintson a Munka-visszaigazolás beállítására.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-149">Click Work confirmation setup.</span></span>
2. <span data-ttu-id="d0c7c-150">A Munkatípus mezőben válassza a „Kitárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-150">In the Work type field, select 'Pick'.</span></span>
3. <span data-ttu-id="d0c7c-151">Válassza ki az Automatikus megerősítés jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-151">Select the Auto confirm check box.</span></span>
    * <span data-ttu-id="d0c7c-152">A Kitárolás munkatípusú munkautasítás automatikus megerősítésre kerül.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-152">The work instruction with work type Pick will be auto-confirmed.</span></span> <span data-ttu-id="d0c7c-153">A felhasználónak ez az utasítás nem fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-153">This instruction will not be presented to the user.</span></span>  
4. <span data-ttu-id="d0c7c-154">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-154">Click New.</span></span>
5. <span data-ttu-id="d0c7c-155">A Munkatípus mezőben válassza a „Betárolás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-155">In the Work type field, select 'Put'.</span></span>
6. <span data-ttu-id="d0c7c-156">Válassza ki a Helymegerősítés jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-156">Select the Location confirmation check box.</span></span>
    * <span data-ttu-id="d0c7c-157">A cikk elhelyezése előtt a raktári dolgozónak meg kell erősítenie a hely átvizsgálását.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-157">The warehouse worker will be asked to perform a confirmation scan of the location, when the item is put down.</span></span>  
7. <span data-ttu-id="d0c7c-158">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-158">Click Save.</span></span>
8. <span data-ttu-id="d0c7c-159">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-159">Close the page.</span></span>
9. <span data-ttu-id="d0c7c-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-160">Close the page.</span></span>

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="d0c7c-161">A menüelem hozzáadása a mobileszköz menühöz</span><span class="sxs-lookup"><span data-stu-id="d0c7c-161">Add the menu item to a mobile device menu</span></span>
1. <span data-ttu-id="d0c7c-162">Ugrás a Mobileszköz menübe.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-162">Go to Mobile device menu.</span></span>
2. <span data-ttu-id="d0c7c-163">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-163">Click Edit.</span></span>
3. <span data-ttu-id="d0c7c-164">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-164">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d0c7c-165">Például szűkítsen a „Név” mezővel a „bejövő” szót beírva.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-165">For example, filter on the Name field with a value of 'inbound'.</span></span>
    * <span data-ttu-id="d0c7c-166">Szeretné megtalálni bejövő menüpontokhoz használt menüt.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-166">You want to find the menu you use for inbound menu items.</span></span> <span data-ttu-id="d0c7c-167">Az USMF rendszerben ennek a mezőnek a neve: Bejövő.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-167">In USMF this is called Inbound.</span></span>  
4. <span data-ttu-id="d0c7c-168">A fában válassza ki az „egy érték” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-168">In the tree, select 'a value'.</span></span>
5. <span data-ttu-id="d0c7c-169">Kattintson a jobbra mutató nyílra.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-169">Click on the arrow that points to the right.</span></span>
6. <span data-ttu-id="d0c7c-170">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-170">Click Save.</span></span>
7. <span data-ttu-id="d0c7c-171">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d0c7c-171">Close the page.</span></span>


