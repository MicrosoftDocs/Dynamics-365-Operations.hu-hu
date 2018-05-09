--- 
title: "Azonosítótábla-címke nyomtatásának engedélyezése"
description: "Ez az eljárás lehetővé teszi a Konténer sorszáma (SSCC) címke automatikus nyomtatását, miután az utolsó cikk készletből való kitárolása is megtörtént az értékesítési kiválasztási munkafolyamat során."
author: perlynne
manager: AnnBe
ms.date: 11/03/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0c0515d61f651b9244525fc20c242f3d31eb3a20
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="4d96d-103">Azonosítótábla-címke nyomtatásának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="4d96d-103">Enable license plate label printing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4d96d-104">Ez az eljárás lehetővé teszi a Konténer sorszáma (SSCC) címke automatikus nyomtatását, miután az utolsó cikk készletből való kitárolása is megtörtént az értékesítési kiválasztási munkafolyamat során.</span><span class="sxs-lookup"><span data-stu-id="4d96d-104">This procedure enables the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="4d96d-105">Ezt a folyamatot lefuttathatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="4d96d-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="4d96d-106">Ha a saját adatok használatával futtatja le, akkor szüksége lesz egy az azonosítótáblákhoz beállított számsorozatra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-106">If you’re run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="4d96d-107">A feladat megkezdése előtt be kell állítania egy címkenyomtatót.</span><span class="sxs-lookup"><span data-stu-id="4d96d-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="4d96d-108">Lépjen a Szervezetadminisztráció > Beállítás > Hálózati nyomtatókra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="4d96d-109">A Műveleti ablakban kattintson az Opciókra, majd a Dokumentumirányítási ügynök telepítőjének letöltése gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-109">On the Action pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="4d96d-110">Futtassa a telepítőt, és győződjön meg arról, hogy van-e működő hálózati nyomtató, amely aktív, mielőtt folytatná a műveletet.</span><span class="sxs-lookup"><span data-stu-id="4d96d-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="4d96d-111">GS1 vállalatelőtag felállítása.</span><span class="sxs-lookup"><span data-stu-id="4d96d-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="4d96d-112">Ugorjon a Raktárkezelés > Beállítás > Raktárkezelési paraméterekre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-112">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="4d96d-113">Az GS1 vállalatelőtag mezőbe írja be vállalata 7-jegyű GS1 számát.</span><span class="sxs-lookup"><span data-stu-id="4d96d-113">In the GS1 company prefix field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="4d96d-114">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-114">Click Save.</span></span>
4. <span data-ttu-id="4d96d-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4d96d-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="4d96d-116">SSCC azonosítótábla számsorozat beállítása</span><span class="sxs-lookup"><span data-stu-id="4d96d-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="4d96d-117">Ugorjon a Szervezeti adminisztráció > Számsorozatok > Számsorozatokra pontra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-117">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="4d96d-118">Egy lehetőség kiválasztása a Terület mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d96d-118">In the Area field, select an option.</span></span>
3. <span data-ttu-id="4d96d-119">Egy lehetőség kiválasztása a Hivatkozás mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d96d-119">In the Reference field, select an option.</span></span>
4. <span data-ttu-id="4d96d-120">Írjon be egy értéket a Vállalat mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d96d-120">In the Company field, type a value.</span></span>
5. <span data-ttu-id="4d96d-121">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="4d96d-121">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="4d96d-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="4d96d-123">Bontsa ki a Szegmensek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4d96d-123">Expand the Segments section.</span></span>
8. <span data-ttu-id="4d96d-124">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-124">Click Edit.</span></span>
9. <span data-ttu-id="4d96d-125">A Szegmens táblában válassza ki az első sort.</span><span class="sxs-lookup"><span data-stu-id="4d96d-125">In the Segments table, select the first row</span></span>
10. <span data-ttu-id="4d96d-126">Kattintson az Eltávolítás gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-126">Click Remove.</span></span>
11. <span data-ttu-id="4d96d-127">Kattintson az Eltávolítás gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-127">Click Remove.</span></span>
12. <span data-ttu-id="4d96d-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-128">Click Save.</span></span>
13. <span data-ttu-id="4d96d-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4d96d-129">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="4d96d-130">Dokumentum útvonal-elrendezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="4d96d-130">Create the document route layout</span></span>
1. <span data-ttu-id="4d96d-131">Ugrás a Raktárkezelés > Beállítás > Dokumentumirányítás > Dokumentumirányító elrendezésekre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-131">Go to Warehouse management > Setup > Document routing > Document routing layouts.</span></span>
    * <span data-ttu-id="4d96d-132">SSCC-elrendezés engedélyezése.</span><span class="sxs-lookup"><span data-stu-id="4d96d-132">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="4d96d-133">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-133">Click New.</span></span>
3. <span data-ttu-id="4d96d-134">Írjon be egy értéket az Elrendezésazonosító mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d96d-134">In the Layout ID field, type a value.</span></span>
4. <span data-ttu-id="4d96d-135">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d96d-135">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4d96d-136">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4d96d-136">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="4d96d-137">Kattintson a Beszúrás a szöveg végére lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-137">Click Insert at end of text.</span></span>
7. <span data-ttu-id="4d96d-138">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-138">Click Save.</span></span>
8. <span data-ttu-id="4d96d-139">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4d96d-139">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="4d96d-140">Dokumentumirányítás beállítása</span><span class="sxs-lookup"><span data-stu-id="4d96d-140">Set up the document routing</span></span>
1. <span data-ttu-id="4d96d-141">Ugrás a Raktárkezelés > Beállítás > Dokumentumirányítás > Dokumentumirányítás pontra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-141">Go to Warehouse management > Setup > Document routing > Document routing.</span></span>
2. <span data-ttu-id="4d96d-142">A Munkarendelés típusa mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4d96d-142">In the Work order type field, select an option.</span></span>
3. <span data-ttu-id="4d96d-143">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-143">Click New.</span></span>
4. <span data-ttu-id="4d96d-144">Érték beírása a Raktár mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d96d-144">In the Warehouse field, type a value.</span></span>
5. <span data-ttu-id="4d96d-145">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d96d-145">In the Name field, type a value.</span></span>
6. <span data-ttu-id="4d96d-146">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-146">Click New.</span></span>
7. <span data-ttu-id="4d96d-147">Az Elrendezésazonosító mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d96d-147">In the Layout ID field, enter or select a value.</span></span>
8. <span data-ttu-id="4d96d-148">A Név mezőben adja meg a használni kívánt nyomtató nevét.</span><span class="sxs-lookup"><span data-stu-id="4d96d-148">In the Name field, enter the printer name that you want to use..</span></span>
9. <span data-ttu-id="4d96d-149">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-149">Click Save.</span></span>
10. <span data-ttu-id="4d96d-150">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4d96d-150">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="4d96d-151">Mobileszköz menüjének létrehozása</span><span class="sxs-lookup"><span data-stu-id="4d96d-151">Create mobile device menu</span></span>
1. <span data-ttu-id="4d96d-152">Ugrás a Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menü elemekre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-152">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="4d96d-153">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-153">Click New.</span></span>
3. <span data-ttu-id="4d96d-154">Írjon be egy értéket a Menüelem neve mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d96d-154">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="4d96d-155">Érték beírása a Címmezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d96d-155">In the Title field, type a value.</span></span>
5. <span data-ttu-id="4d96d-156">Egy lehetőség kiválasztása a Mód mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d96d-156">In the Mode field, select an option.</span></span>
6. <span data-ttu-id="4d96d-157">A Meglévő munka használata mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4d96d-157">Select Yes in the Use existing work field.</span></span>
7. <span data-ttu-id="4d96d-158">Válassza az Igen lehetőséget az Azonosítótábla előállítása mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d96d-158">Select Yes in the Generate license plate field.</span></span>
8. <span data-ttu-id="4d96d-159">Bontsa ki a Munkaosztályok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4d96d-159">Expand the Work classes section.</span></span>
9. <span data-ttu-id="4d96d-160">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-160">Click New.</span></span>
10. <span data-ttu-id="4d96d-161">Írjon be egy értéket a Munkaosztály azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4d96d-161">In the Work class ID field, type a value.</span></span>
11. <span data-ttu-id="4d96d-162">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-162">Click Save.</span></span>
12. <span data-ttu-id="4d96d-163">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4d96d-163">Close the page.</span></span>
13. <span data-ttu-id="4d96d-164">Ugrás a Raktárkezelés > Beállítás Mobileszköz > Mobileszköz menüre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-164">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
14. <span data-ttu-id="4d96d-165">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4d96d-165">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="4d96d-166">A fán válassza ki az „A fán válassza ki a menüelemet, amelyet korábban hozott létre.” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4d96d-166">In the tree, select 'In the tree, select the menu item that you created before.'.</span></span>
16. <span data-ttu-id="4d96d-167">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-167">Click Edit.</span></span>
17. <span data-ttu-id="4d96d-168">Kattintson a nyílra a menüpont menühöz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="4d96d-168">Click on the arrow to add the menu item to the menu.</span></span>
18. <span data-ttu-id="4d96d-169">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-169">Click Save.</span></span>
19. <span data-ttu-id="4d96d-170">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4d96d-170">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="4d96d-171">Munkasablon frissítése</span><span class="sxs-lookup"><span data-stu-id="4d96d-171">Update a work template</span></span>
1. <span data-ttu-id="4d96d-172">Ugrás a Raktárkezelés > Beállítás > Munka > Munkasablonokra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-172">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="4d96d-173">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4d96d-173">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="4d96d-174">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-174">Click Edit.</span></span>
4. <span data-ttu-id="4d96d-175">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="4d96d-175">Click New.</span></span>
5. <span data-ttu-id="4d96d-176">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="4d96d-176">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="4d96d-177">A Munkatípus mezőben válassza a „Nyomtatás” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4d96d-177">In the Work type field, select 'Print'.</span></span>
7. <span data-ttu-id="4d96d-178">A Munkaosztály-azonosító mezőben írjon be vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d96d-178">In the Work class ID field, enter or select a value.</span></span>
8. <span data-ttu-id="4d96d-179">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-179">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="4d96d-180">Kattintson a Felfelé gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-180">Click Move up.</span></span>
10. <span data-ttu-id="4d96d-181">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4d96d-181">Click Save.</span></span>
11. <span data-ttu-id="4d96d-182">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4d96d-182">Close the page.</span></span>


