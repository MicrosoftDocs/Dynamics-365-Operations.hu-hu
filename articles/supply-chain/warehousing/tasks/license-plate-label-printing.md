---
title: Azonosítótábla-címke nyomtatásának engedélyezése
description: Ez az eljárás bemutatja a Konténer sorszáma (SSCC) címke automatikus nyomtatásának engedélyezését, miután az utolsó cikk készletből való kitárolása is megtörtént az értékesítési kiválasztási munkafolyamat során.
author: perlynne
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 545f1c15888bcd0b46e1028f58cbe3a274846c92
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146031"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="fc00e-103">Azonosítótábla-címke nyomtatásának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="fc00e-103">Enable license plate label printing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fc00e-104">Ez az eljárás bemutatja a Konténer sorszáma (SSCC) címke automatikus nyomtatásának engedélyezését, miután az utolsó cikk készletből való kitárolása is megtörtént az értékesítési kiválasztási munkafolyamat során.</span><span class="sxs-lookup"><span data-stu-id="fc00e-104">This topic shows how to enable the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="fc00e-105">Ezt a folyamatot lefuttathatja az USMF bemutatócégen.</span><span class="sxs-lookup"><span data-stu-id="fc00e-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="fc00e-106">Ha a saját adatok használatával futtatja le, akkor szüksége lesz egy az azonosítótáblákhoz beállított számsorozatra.</span><span class="sxs-lookup"><span data-stu-id="fc00e-106">If you're run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="fc00e-107">A feladat megkezdése előtt be kell állítania egy címkenyomtatót.</span><span class="sxs-lookup"><span data-stu-id="fc00e-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="fc00e-108">Lépjen a Szervezetadminisztráció > Beállítás > Hálózati nyomtatókra.</span><span class="sxs-lookup"><span data-stu-id="fc00e-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="fc00e-109">A Műveleti ablakban kattintson az Opciókra, majd a Dokumentumirányítási ügynök telepítőjének letöltése gombra.</span><span class="sxs-lookup"><span data-stu-id="fc00e-109">On the Action pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="fc00e-110">Futtassa a telepítőt, és győződjön meg arról, hogy van-e működő hálózati nyomtató, amely aktív, mielőtt folytatná a műveletet.</span><span class="sxs-lookup"><span data-stu-id="fc00e-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="fc00e-111">GS1 vállalatelőtag felállítása.</span><span class="sxs-lookup"><span data-stu-id="fc00e-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="fc00e-112">Ugrás a **Navigációs ablaktábla > Modulok > Raktárkezelés > Beállítás > Raktárkezelési paraméterekre**</span><span class="sxs-lookup"><span data-stu-id="fc00e-112">Go to **Navigation pane > Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="fc00e-113">Az **GS1 vállalatelőtag** mezőbe írja be vállalata 7-jegyű GS1 számát.</span><span class="sxs-lookup"><span data-stu-id="fc00e-113">In the **GS1 company prefix** field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="fc00e-114">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-114">Select **Save**.</span></span>
4. <span data-ttu-id="fc00e-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fc00e-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="fc00e-116">SSCC azonosítótábla számsorozat beállítása</span><span class="sxs-lookup"><span data-stu-id="fc00e-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="fc00e-117">Ugorjon a **Navigációs ablaktábla > Modulok > Szervezeti adminisztráció > Számsorozatok > Számsorozatok** elemre.</span><span class="sxs-lookup"><span data-stu-id="fc00e-117">Go to **Navigation pane > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="fc00e-118">Egy lehetőség kiválasztása a **Terület** mezőben.</span><span class="sxs-lookup"><span data-stu-id="fc00e-118">In the **Area** field, select an option.</span></span>
3. <span data-ttu-id="fc00e-119">Egy lehetőség kiválasztása a **Hivatkozás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="fc00e-119">In the **Reference** field, select an option.</span></span>
4. <span data-ttu-id="fc00e-120">Írjon be egy értéket a **Vállalat** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="fc00e-120">In the **Company** field, type a value.</span></span>
5. <span data-ttu-id="fc00e-121">Bontsa ki a **Szegmensek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="fc00e-121">Expand the **Segments** section.</span></span>
6. <span data-ttu-id="fc00e-122">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="fc00e-122">Select **Edit**.</span></span>
7. <span data-ttu-id="fc00e-123">A **Szegmensek** táblában válassza ki az első sort.</span><span class="sxs-lookup"><span data-stu-id="fc00e-123">In the **Segments** table, select the first row</span></span>
8. <span data-ttu-id="fc00e-124">Válassza az **Eltávolítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-124">Select **Remove**.</span></span>
9. <span data-ttu-id="fc00e-125">Válassza az **Eltávolítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-125">Select **Remove**.</span></span>
10. <span data-ttu-id="fc00e-126">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-126">Select **Save**.</span></span>
11. <span data-ttu-id="fc00e-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fc00e-127">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="fc00e-128">Dokumentum útvonal-elrendezés létrehozása</span><span class="sxs-lookup"><span data-stu-id="fc00e-128">Create the document route layout</span></span>
1. <span data-ttu-id="fc00e-129">Ugrás a **Raktárkezelés > Beállítás > Dokumentumirányítás > Dokumentumirányító elrendezésekre**.</span><span class="sxs-lookup"><span data-stu-id="fc00e-129">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing layouts**.</span></span> <span data-ttu-id="fc00e-130">SSCC-elrendezés engedélyezése.</span><span class="sxs-lookup"><span data-stu-id="fc00e-130">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="fc00e-131">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-131">Select **New**.</span></span>
3. <span data-ttu-id="fc00e-132">Írjon be egy értéket az **Elrendezésazonosító** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="fc00e-132">In the **Layout ID** field, type a value.</span></span>
4. <span data-ttu-id="fc00e-133">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="fc00e-133">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="fc00e-134">Válassza a **Beszúrás szöveg végére** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-134">Select **Insert at end of text**.</span></span>
6. <span data-ttu-id="fc00e-135">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-135">Select **Save**.</span></span>
7. <span data-ttu-id="fc00e-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fc00e-136">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="fc00e-137">Dokumentumirányítás beállítása</span><span class="sxs-lookup"><span data-stu-id="fc00e-137">Set up the document routing</span></span>
1. <span data-ttu-id="fc00e-138">Ugrás a **Raktárkezelés > Beállítás > Dokumentumirányítás > Dokumentumirányítás** helyre.</span><span class="sxs-lookup"><span data-stu-id="fc00e-138">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing**.</span></span>
2. <span data-ttu-id="fc00e-139">A **Munkarendelés típusa** mezőben válasszon ki egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-139">In the **Work order type** field, select an option.</span></span>
3. <span data-ttu-id="fc00e-140">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-140">Select **New**.</span></span>
4. <span data-ttu-id="fc00e-141">Érték beírása a **Raktár** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="fc00e-141">In the **Warehouse** field, type a value.</span></span>
5. <span data-ttu-id="fc00e-142">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="fc00e-142">In the **Name** field, type a value.</span></span>
6. <span data-ttu-id="fc00e-143">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-143">Select **New**.</span></span>
7. <span data-ttu-id="fc00e-144">Az **Elrendezésazonosító** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fc00e-144">In the **Layout ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="fc00e-145">A **Név** mezőben adja meg a használni kívánt nyomtató nevét.</span><span class="sxs-lookup"><span data-stu-id="fc00e-145">In the **Name** field, enter the printer name that you want to use.</span></span>
9. <span data-ttu-id="fc00e-146">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-146">Select **Save**.</span></span>
10. <span data-ttu-id="fc00e-147">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fc00e-147">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="fc00e-148">Mobileszköz menüjének létrehozása</span><span class="sxs-lookup"><span data-stu-id="fc00e-148">Create mobile device menu</span></span>
1. <span data-ttu-id="fc00e-149">A **Navigációs ablaktáblán ugorjon a Modulok > Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menüpontjai** elemre.</span><span class="sxs-lookup"><span data-stu-id="fc00e-149">Go to **Navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="fc00e-150">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-150">Select **New**.</span></span>
3. <span data-ttu-id="fc00e-151">Írjon be egy értéket a **Menüelem neve** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="fc00e-151">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="fc00e-152">Érték beírása a **Cím** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="fc00e-152">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="fc00e-153">Egy lehetőség kiválasztása a **Mód** mezőben.</span><span class="sxs-lookup"><span data-stu-id="fc00e-153">In the **Mode** field, select an option.</span></span>
6. <span data-ttu-id="fc00e-154">A **Meglévő munka használata** mezőben válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-154">Select **Yes** in the **Use existing work** field.</span></span>
7. <span data-ttu-id="fc00e-155">Válassza az **Igen** lehetőséget az **Azonosítótábla előállítása** mezőben.</span><span class="sxs-lookup"><span data-stu-id="fc00e-155">Select **Yes** in the **Generate license plate** field.</span></span>
8. <span data-ttu-id="fc00e-156">Bontsa ki a **Munkaosztályok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="fc00e-156">Expand the **Work classes** section.</span></span>
9. <span data-ttu-id="fc00e-157">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-157">Select **New**.</span></span>
10. <span data-ttu-id="fc00e-158">Írjon be egy értéket a **Munkaosztály** azonosítója mezőbe.</span><span class="sxs-lookup"><span data-stu-id="fc00e-158">In the **Work class ID** field, type a value.</span></span>
11. <span data-ttu-id="fc00e-159">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-159">Select **Save**.</span></span>
12. <span data-ttu-id="fc00e-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fc00e-160">Close the page.</span></span>
13. <span data-ttu-id="fc00e-161">A **Navigációs ablaktáblán ugorjon a Modulok > Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menü** elemre.</span><span class="sxs-lookup"><span data-stu-id="fc00e-161">Go to **navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
14. <span data-ttu-id="fc00e-162">A fán válassza ki az előzőleg létrehozott menüpontot.</span><span class="sxs-lookup"><span data-stu-id="fc00e-162">In the tree, select the menu item that you created before.</span></span>
15. <span data-ttu-id="fc00e-163">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="fc00e-163">Select **Edit**.</span></span>
16. <span data-ttu-id="fc00e-164">Kattintson a nyílra a menüpont menühöz való hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="fc00e-164">Select the arrow to add the menu item to the menu.</span></span>
17. <span data-ttu-id="fc00e-165">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-165">Select **Save**.</span></span>
18. <span data-ttu-id="fc00e-166">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fc00e-166">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="fc00e-167">Munkasablon frissítése</span><span class="sxs-lookup"><span data-stu-id="fc00e-167">Update a work template</span></span>
1. <span data-ttu-id="fc00e-168">A **Navigációs ablaktáblán > ugorjon a Modulok > Raktárkezelés > Beállítás > Munka > Munkasablonok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="fc00e-168">Go to **Navigation pane > Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="fc00e-169">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="fc00e-169">Select **Edit**.</span></span>
3. <span data-ttu-id="fc00e-170">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-170">Select **New**.</span></span>
4. <span data-ttu-id="fc00e-171">A **Munkatípus** mezőben válassza a **Nyomtatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-171">In the **Work type** field, select **Print**.</span></span>
5. <span data-ttu-id="fc00e-172">A **Munkaosztály-azonosító** mezőben írjon be vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="fc00e-172">In the **Work class ID** field, enter or select a value.</span></span>
6. <span data-ttu-id="fc00e-173">Válassza a **Feljebb** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-173">Select **Move up**.</span></span>
7. <span data-ttu-id="fc00e-174">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fc00e-174">Select **Save**.</span></span>
8. <span data-ttu-id="fc00e-175">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="fc00e-175">Close the page.</span></span>

