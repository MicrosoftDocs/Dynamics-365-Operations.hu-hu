---
title: 'Ciklikus leltározás meghatározása '
description: A ciklikus leltározás egy olyan raktározási folyamat, amelyet az aktuális készlet cikkeinek ellenőrzésére használhat.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2832547f81b0153d42ac4664184f18bd66f1acdd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571678"
---
# <a name="define-cycle-counting"></a><span data-ttu-id="d826a-103">Ciklikus leltározás meghatározása </span><span class="sxs-lookup"><span data-stu-id="d826a-103">Define cycle counting</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d826a-104">A ciklikus leltározás egy olyan raktározási folyamat, amelyet az aktuális készlet cikkeinek ellenőrzésére használhat.</span><span class="sxs-lookup"><span data-stu-id="d826a-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="d826a-105">A feladatrögzítés megmutatja, hogy miként: állíthatja be az alapértelmezett leltározási feladat prioritását; engedélyezhet egy mobileszköz menüpontot a kitárolási és leltározási műveletekhez, engedélyezhet egy leltározási küszöbértéket, ha egy hely üressé válik, engedélyezhet egy ciklikus leltározási tervet egy adott raktárban található adott cikkhez.</span><span class="sxs-lookup"><span data-stu-id="d826a-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="d826a-106">Általában a raktárvezető végzi el ezeket a feladatokat.</span><span class="sxs-lookup"><span data-stu-id="d826a-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="d826a-107">Ezt a folyamatot az USMF bemutatócégen vagy saját adatain is elvégezheti.</span><span class="sxs-lookup"><span data-stu-id="d826a-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="d826a-108">A leltározási munka prioritásának beállítása</span><span class="sxs-lookup"><span data-stu-id="d826a-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="d826a-109">Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési paraméterekre.</span><span class="sxs-lookup"><span data-stu-id="d826a-109">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="d826a-110">Kattintson a Ciklikus leltározás lapra.</span><span class="sxs-lookup"><span data-stu-id="d826a-110">Click the Cycle counting tab.</span></span>
3. <span data-ttu-id="d826a-111">A Ciklikus leltározási munka alapértelmezett prioritása mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="d826a-111">In the Default cycle count work priority field, enter a number.</span></span>
    * <span data-ttu-id="d826a-112">Ez a lépés megváltoztatja a ciklikus leltározási munka prioritását a raktárban folyó más típusú munkákhoz képest.</span><span class="sxs-lookup"><span data-stu-id="d826a-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="d826a-113">Ha kisebb számot ad meg a többi típusú munkához megadott számoknál, növeli a ciklikus leltározási feladat prioritását.</span><span class="sxs-lookup"><span data-stu-id="d826a-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="d826a-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d826a-114">Click Save.</span></span>
5. <span data-ttu-id="d826a-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d826a-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="d826a-116">Mobileszköz engedélyezése</span><span class="sxs-lookup"><span data-stu-id="d826a-116">Enable the mobile device</span></span>
1. <span data-ttu-id="d826a-117">Ugrás a Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menü elemekre.</span><span class="sxs-lookup"><span data-stu-id="d826a-117">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="d826a-118">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-118">Click New.</span></span>
3. <span data-ttu-id="d826a-119">Írjon be egy értéket a Menüelem neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d826a-119">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="d826a-120">Érték beírása a Címmezőbe.</span><span class="sxs-lookup"><span data-stu-id="d826a-120">In the Title field, type a value.</span></span>
5. <span data-ttu-id="d826a-121">A Mód mezőben válassza ki a „Munka” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d826a-121">In the Mode field, select 'Work'.</span></span>
6. <span data-ttu-id="d826a-122">A Meglévő munka használata lehetőséget állítsa Igenre.</span><span class="sxs-lookup"><span data-stu-id="d826a-122">Set the Use existing work option to Yes.</span></span>
    * <span data-ttu-id="d826a-123">Ha az Igen lehetőséget választja, a mobileszköz menüpont használata esetén a rendszer megvizsgálja a meglévő munkát.</span><span class="sxs-lookup"><span data-stu-id="d826a-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="d826a-124">Az Irányítja mezőben válassza a „Rendszer által irányított” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d826a-124">In the Directed by field, select 'System directed'.</span></span>
    * <span data-ttu-id="d826a-125">Amikor a „Rendszer által irányított” lehetőség van kijelölve, a rendszer a raktári dolgozót a munkaosztályokban megadott nyitott munkákhoz irányítja.</span><span class="sxs-lookup"><span data-stu-id="d826a-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="d826a-126">(Ezeket a munkaosztályokat a későbbiekben hozzuk létre.)</span><span class="sxs-lookup"><span data-stu-id="d826a-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="d826a-127">Bontsa ki vagy csukja össze a Munkaosztályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="d826a-127">Expand or collapse the Work classes section.</span></span>
    * <span data-ttu-id="d826a-128">Most létrehozunk két felhasználható munkaosztályt, amelyeket ezzel a mobileszköz menüponttal használ.</span><span class="sxs-lookup"><span data-stu-id="d826a-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="d826a-129">A menüpont használata esetén megtörténik a munkaosztályok lekérdezése, és a legmagasabb prioritású munka megjelenik a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="d826a-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="d826a-130">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-130">Click New.</span></span>
10. <span data-ttu-id="d826a-131">A Munkaosztály-azonosító mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d826a-131">In the Work class ID field, select a value.</span></span>
11. <span data-ttu-id="d826a-132">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-132">Click New.</span></span>
12. <span data-ttu-id="d826a-133">A Munkaosztály-azonosító mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d826a-133">In the Work class ID field, select a value.</span></span>
13. <span data-ttu-id="d826a-134">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d826a-134">Click Save.</span></span>
14. <span data-ttu-id="d826a-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d826a-135">Close the page.</span></span>
15. <span data-ttu-id="d826a-136">Ugrás a Raktárkezelés > Beállítás Mobileszköz > Mobileszköz menüre.</span><span class="sxs-lookup"><span data-stu-id="d826a-136">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
16. <span data-ttu-id="d826a-137">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="d826a-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="d826a-138">A fán válassza ki az „éppen létrehozott menüpont” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d826a-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="d826a-139">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-139">Click Edit.</span></span>
19. <span data-ttu-id="d826a-140">Kattintson a nyílra a menüpont menühöz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="d826a-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="d826a-141">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d826a-141">Click Save.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="d826a-142">Leltározási küszöbérték létrehozása</span><span class="sxs-lookup"><span data-stu-id="d826a-142">Create a counting threshold</span></span>
1. <span data-ttu-id="d826a-143">Ugorjon a Raktárkezelés > Beállítás > Ciklikus leltározás > Ciklikus leltározási küszöbértékei menüpontra.</span><span class="sxs-lookup"><span data-stu-id="d826a-143">Go to Warehouse management > Setup > Cycle counting > Cycle count thresholds.</span></span>
2. <span data-ttu-id="d826a-144">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-144">Click New.</span></span>
3. <span data-ttu-id="d826a-145">A Ciklikus leltározási küszöbérték azonosítója mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d826a-145">In the Cycle counting threshold ID field, type a value.</span></span>
4. <span data-ttu-id="d826a-146">A Ciklikus leltározás végrehajtása azonnal lehetőséget állítsa Igenre.</span><span class="sxs-lookup"><span data-stu-id="d826a-146">Set the Process cycle counting immediately option to Yes.</span></span>
5. <span data-ttu-id="d826a-147">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d826a-147">In the Description field, type a value.</span></span>
6. <span data-ttu-id="d826a-148">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d826a-148">Click Save.</span></span>
7. <span data-ttu-id="d826a-149">Kattintson a Hely kiválasztása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-149">Click Select locations.</span></span>
8. <span data-ttu-id="d826a-150">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d826a-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="d826a-151">A Feltételek mezőben válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d826a-151">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="d826a-152">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d826a-152">Click OK.</span></span>
11. <span data-ttu-id="d826a-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d826a-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="d826a-154">Ciklikus leltározási terv létrehozása</span><span class="sxs-lookup"><span data-stu-id="d826a-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="d826a-155">Ugorjon a Raktárkezelés > Beállítás > Ciklikus leltározás > Ciklikus leltározási tervek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-155">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="d826a-156">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-156">Click New.</span></span>
3. <span data-ttu-id="d826a-157">A Ciklikus leltározási terv azonosítója mezőbe írjon be egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d826a-157">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="d826a-158">Írjon egy értéket a „Leírás” mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d826a-158">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d826a-159">A Ciklikus leltározások maximális száma mezőbe írjon be egy számot.</span><span class="sxs-lookup"><span data-stu-id="d826a-159">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="d826a-160">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d826a-160">Click Save.</span></span>
7. <span data-ttu-id="d826a-161">Kattintson a Hely kiválasztása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-161">Click Select locations.</span></span>
8. <span data-ttu-id="d826a-162">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d826a-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="d826a-163">A Feltételek mezőben válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d826a-163">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="d826a-164">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d826a-164">Click OK.</span></span>
11. <span data-ttu-id="d826a-165">A Ciklikus leltárok közötti idő mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="d826a-165">In the Days between cycle counting field, enter a number.</span></span>
    * <span data-ttu-id="d826a-166">Ha például a Ciklikus leltárok közötti idő mező megadott beállítása 5, a ciklikus leltározási munka ötnaponként készül.</span><span class="sxs-lookup"><span data-stu-id="d826a-166">For example, if the Days between cycle counting field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="d826a-167">Azonban ha a ciklikus leltári munka a harmadik napon kerül feldolgozásra, a rendszer a következő leltározási munkát öt nappal az utolsó ciklikus leltár feldolgozása után, a 8. napon hozza létre.</span><span class="sxs-lookup"><span data-stu-id="d826a-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="d826a-168">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d826a-168">Click Save.</span></span>
13. <span data-ttu-id="d826a-169">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-169">Click New.</span></span>
14. <span data-ttu-id="d826a-170">Adjon meg egy számot a Sorozatszám mezőben.</span><span class="sxs-lookup"><span data-stu-id="d826a-170">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="d826a-171">A rendezési sorrend a legkisebb számtól a legnagyobb számig tart.</span><span class="sxs-lookup"><span data-stu-id="d826a-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="d826a-172">Az értéknek nullánál (0) nagyobbnak kell lennie.</span><span class="sxs-lookup"><span data-stu-id="d826a-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="d826a-173">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d826a-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="d826a-174">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d826a-174">In the Description field, type a value.</span></span>
17. <span data-ttu-id="d826a-175">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="d826a-175">Click Save.</span></span>
18. <span data-ttu-id="d826a-176">Kattintson a Terméklekérdezés megadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d826a-176">Click Define product query.</span></span>
19. <span data-ttu-id="d826a-177">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="d826a-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="d826a-178">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d826a-178">In the Criteria field, enter or select a value.</span></span>
21. <span data-ttu-id="d826a-179">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="d826a-179">Click OK.</span></span>
22. <span data-ttu-id="d826a-180">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d826a-180">Close the page.</span></span>

