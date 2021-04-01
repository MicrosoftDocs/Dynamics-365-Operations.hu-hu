---
title: Kitárolási sor csoportosítása
description: Ez a témakör a kitárolási sor csoportosításáról nyújt áttekintést.
author: Mirzaab
manager: tfehr
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 7ab8cdd7cad5420aca0de53e59220da9e230d411
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234633"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="0a4c3-103">Kitárolási sor csoportosítása</span><span class="sxs-lookup"><span data-stu-id="0a4c3-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a4c3-104">A kitárolási sor csoportosításával ugyanazzal a cikkel és hellyel rendelkező több munka összevonható egyetlen kitárolássá, amelyet a felhasználó mobileszközön kap meg.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-104">Pick line grouping enables multiple work lines that have the same item and location to be combined into a single pick that is presented to the user on the mobile device.</span></span> <span data-ttu-id="0a4c3-105">A raktári dolgozók így a lehető leghatékonyabb utasításokat kapják, de továbbra is fenntartható a rendszerben (például különböző tárolókban és rendeléseknél) a sorok szükséges elválasztása.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-105">Therefore, warehouse workers can receive the most efficient instructions, but required work line separation (for different containers, orders, and so on) can still be maintained in the system.</span></span>

## <a name="turn-on-the-pick-line-grouping-feature"></a><span data-ttu-id="0a4c3-106">A kitárolási sor csoportosítása funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="0a4c3-106">Turn on the pick line grouping feature</span></span>

<span data-ttu-id="0a4c3-107">A funkció használata előtt be kell azt kapcsolnia saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-107">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="0a4c3-108">A rendszergazdák használhatják a [Funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterület a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="0a4c3-109">A funkció a következő módon jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="0a4c3-109">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="0a4c3-110">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="0a4c3-110">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="0a4c3-111">**Funkció neve:** *Kitárolási sor csoportosítása*</span><span class="sxs-lookup"><span data-stu-id="0a4c3-111">**Feature name:** *Pick line grouping*</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="0a4c3-112">Kitárolási sor csoportosításának beállítása</span><span class="sxs-lookup"><span data-stu-id="0a4c3-112">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="0a4c3-113">Mobileszköz-menüpont létrehozása</span><span class="sxs-lookup"><span data-stu-id="0a4c3-113">Create a mobile device menu item</span></span>

1. <span data-ttu-id="0a4c3-114">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-114">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="0a4c3-115">A Műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-115">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="0a4c3-116">A **Menüelem neve** mezőbe írja be az *Értékesítési csoport sorának kitárolása* értéket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-116">In the **Menu item name** field, enter *Sales group line picking*.</span></span>
1. <span data-ttu-id="0a4c3-117">A **Cím** mezőbe írja be az *Értékesítési csoport sorának kitárolása* értéket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-117">In the **Title** field, enter *Sales group line picking*.</span></span> <span data-ttu-id="0a4c3-118">Ez a cím jelenik meg a mobileszköz menüjén.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-118">This title will be shown on the mobile device menu.</span></span>
1. <span data-ttu-id="0a4c3-119">A **Mód** mezőben válassza ki a *Munka* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-119">In the **Mode** field, select *Work*.</span></span>
1. <span data-ttu-id="0a4c3-120">A **Meglévő munka használata** lehetőséget állítsa *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-120">Set the **Use existing work** option to *Yes*.</span></span>
1. <span data-ttu-id="0a4c3-121">Az **Általános** gyorslapon állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="0a4c3-121">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="0a4c3-122">Az **Irányítja** mezőben válassza a *Felhasználó által irányított* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-122">In the **Directed by** field, select *User directed*.</span></span>
    - <span data-ttu-id="0a4c3-123">Állítsa az **Azonosítótábla előállítása** beállítást *Igen* értékűre.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-123">Set the **Generate license plate** option to *Yes*.</span></span>
    - <span data-ttu-id="0a4c3-124">Állítsa a **Kitárolás csoportosítása** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-124">Set the **Group pick** option to *Yes*.</span></span>
    - <span data-ttu-id="0a4c3-125">A fennmaradó opcióknál hagyja meg az alapértelmezett értékeket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-125">Accept the default values for the remaining options.</span></span>

1. <span data-ttu-id="0a4c3-126">A következő lépések végrehajtásával állíthatja be a mobileszköz menüelemének érvényes munkaosztályait:</span><span class="sxs-lookup"><span data-stu-id="0a4c3-126">Follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="0a4c3-127">A **Munkaosztályok** gyorslapon válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-127">On the **Work classes** FastTab, elect **New**.</span></span>
    2. <span data-ttu-id="0a4c3-128">A **Munkaosztály azonosítója** mezőben kiválaszthatja az *Értékesítés* vagy az *SO kitárolás* lehetőséget attól függően, hogy milyen raktárt fog használni.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-128">In the **Work class ID** field, you can select either *Sales* or *SO Pick*, depending on the warehouse that you will use.</span></span> <span data-ttu-id="0a4c3-129">Erre az esetre válassza az *SO kitárolás* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-129">For this scenario, select *SO Pick*.</span></span>

        <span data-ttu-id="0a4c3-130">A **Munkarendelés típusa** mező automatikusan a *Beszerzési rendelések* értékre áll.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-130">The **Work order type** field is automatically set to *Sales orders*.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="0a4c3-131">Mobileszköz-menü beállítása</span><span class="sxs-lookup"><span data-stu-id="0a4c3-131">Set up a mobile device menu</span></span>

<span data-ttu-id="0a4c3-132">A következő lépések szerint hozzáadhatja az előbb létrehozott menüelemet a **Kimenő** menühöz.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-132">Follow these steps to add the menu item that you just created to the **Outbound** menu.</span></span>

1. <span data-ttu-id="0a4c3-133">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-133">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="0a4c3-134">A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-134">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="0a4c3-135">A listaablak az összes meglévő mobileszköz-menüt mutatja.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-135">The list pane shows all existing mobile device menus.</span></span> <span data-ttu-id="0a4c3-136">Jelölje ki a *Kimenő* elemet a listán.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-136">Select *Outbound* in the list.</span></span>
1. <span data-ttu-id="0a4c3-137">A **Rendelkezésre álló menük és menüelemek** listában keresse meg és válassza ki a létrehozott *Értékesítési csoport sorának kitárolása* menüelemet.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-137">In the **Available menus and menu items** list, find and select the *Sales group line picking* menu item that you created.</span></span>
1. <span data-ttu-id="0a4c3-138">Válassza a jobbra mutató nyílgombot a *Értékesítési csoport sorának kitárolása* menüelem **Menüstruktúra** listában való elhelyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-138">Select the right arrow button to move the *Sales group line picking* menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="0a4c3-139">A felfelé és lefelé mutató nyíllal a menüben mozgathatja a menüelemet a kívánt struktúrában.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-139">Use the up arrow and down arrow buttons to move the menu item into the desired position in the menu structure.</span></span>
1. <span data-ttu-id="0a4c3-140">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-140">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="0a4c3-141">Munkasablon beállítása</span><span class="sxs-lookup"><span data-stu-id="0a4c3-141">Set up a work template</span></span>

1. <span data-ttu-id="0a4c3-142">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-142">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="0a4c3-143">A **Munkarendelés típusa** mezőben válassza ki az *Értékesítési rendelések* elemet.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-143">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="0a4c3-144">Az  **Áttekintés** rácsban keresse meg és válassza ki az ezzel a funkcióval használni kívánt munkasablont.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-144">In the **Overview** grid, find and select the work template that should be used with this function.</span></span> <span data-ttu-id="0a4c3-145">Ehhez a helyzethez válassza az *51 Kitárolás szakaszhoz* sablont.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-145">For this scenario, select the *51 Pick to stage* template.</span></span>
1. <span data-ttu-id="0a4c3-146">A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-146">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="0a4c3-147">A lekérdezés szerkesztőpanel **Rendezés** lapján válassza a **Hozzáadás** parancsot az új sorhoz, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="0a4c3-147">In the query editor dialog box, on the **Sorting** tab, select **Add**, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="0a4c3-148">A **Táblázat** oszlopban válassza az *Ideiglenes munkatranzakciók* opciót.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-148">In the **Table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="0a4c3-149">A **Származtatott tábla** oszlopban válassza az *Ideiglenes munkatranzakciók* opciót.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-149">In the **Derived table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="0a4c3-150">A **Mező** oszlopban válassza ki a *Cikkszám* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-150">In the **Field** column, select *Item number*.</span></span>
    - <span data-ttu-id="0a4c3-151">A **Keresés iránya** oszlopban válassza a *Növekvő* értéket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-151">In the **Search direction** column, select *Ascending*.</span></span>

1. <span data-ttu-id="0a4c3-152">Az **OK** gombra kattintva zárja be a párbeszédpanelt, és mentse a beállításokat.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-152">Select **OK** to close the dialog box and save your selection.</span></span>
1. <span data-ttu-id="0a4c3-153">A következő üzenet jelenik meg: „A csoportosítás alaphelyzetbe kerül, folytatja?”</span><span class="sxs-lookup"><span data-stu-id="0a4c3-153">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="0a4c3-154">A folytatáshoz kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-154">Select **Yes** to continue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a4c3-155">A kitárolási sor csoportosítása funkcióhoz működéséhez a munkasorokat cikkazonosító szerint kell rendezni.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-155">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="0a4c3-156">Ha az azonos tételeket tartalmazó sorok nem egymás után lesznek sorba rendezve, a csoportosítás nem történik meg.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-156">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="0a4c3-157">Példa</span><span class="sxs-lookup"><span data-stu-id="0a4c3-157">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="0a4c3-158">Kitárolási munka létrehozása</span><span class="sxs-lookup"><span data-stu-id="0a4c3-158">Create picking work</span></span>

<span data-ttu-id="0a4c3-159">A kitárolási sor csoportosításának beállítása előtt létre kell hoznia néhány alkalmas kimenő munkát.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-159">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="0a4c3-160">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-160">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="0a4c3-161">Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-161">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="0a4c3-162">A **Vevői számla** mezőben válassza a következőt: *US-004*.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-162">In the **Customer account** field, select *US-004*.</span></span>
1. <span data-ttu-id="0a4c3-163">Az **Általános** gyorslap **Raktár** mezőjében válassza ki a *51* értéket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-163">On the **General** FastTab, in the **Warehouse** field, select *51*.</span></span>
1. <span data-ttu-id="0a4c3-164">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-164">Select **OK**.</span></span>
1. <span data-ttu-id="0a4c3-165">Az **Értékesítési rendelés sorai** gyorslapon adja hozzá a következő hat sort:</span><span class="sxs-lookup"><span data-stu-id="0a4c3-165">On the **Sales order lines** FastTab, add the following six lines:</span></span>

    - <span data-ttu-id="0a4c3-166">**1. sor:** A **Cikkszám** mezőben válassza az *M9200* értéket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-166">**Line 1:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="0a4c3-167">Írja be a *3* értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-167">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="0a4c3-168">**2. sor:** A **Cikkszám** mezőben válassza az *M9201* értéket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-168">**Line 2:** In the **Item number** field, select *M9201*.</span></span> <span data-ttu-id="0a4c3-169">Írja be a *3* értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-169">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="0a4c3-170">**3. sor:** A **Cikkszám** mezőben válassza az *M9202* értéket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-170">**Line 3:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="0a4c3-171">Írja be a *2* értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-171">In the **Quantity** field, enter *2*.</span></span>
    - <span data-ttu-id="0a4c3-172">**4. sor:** A **Cikkszám** mezőben válassza az *M9200* értéket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-172">**Line 4:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="0a4c3-173">Írja be a *1* értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-173">In the **Quantity** field, enter *1*.</span></span>
    - <span data-ttu-id="0a4c3-174">**5. sor:** A **Cikkszám** mezőben válassza az *M9200* értéket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-174">**Line 5:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="0a4c3-175">Írja be a *3* értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-175">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="0a4c3-176">**6. sor:** A **Cikkszám** mezőben válassza az *M9202* értéket.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-176">**Line 6:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="0a4c3-177">Írja be a *7* értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-177">In the **Quantity** field, enter *7*.</span></span>

    <span data-ttu-id="0a4c3-178">Az egyes cikkek teljes mennyiségének összegzése:</span><span class="sxs-lookup"><span data-stu-id="0a4c3-178">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="0a4c3-179">**M9200 cikk:** *7* egyenként</span><span class="sxs-lookup"><span data-stu-id="0a4c3-179">**Item M9200:** *7* each</span></span>
    - <span data-ttu-id="0a4c3-180">**M9201 cikk:** *3* egyenként</span><span class="sxs-lookup"><span data-stu-id="0a4c3-180">**Item M9201:** *3* each</span></span>
    - <span data-ttu-id="0a4c3-181">**M9202 cikk:** *9* egyenként</span><span class="sxs-lookup"><span data-stu-id="0a4c3-181">**Item M9202:** *9* each</span></span>

1. <span data-ttu-id="0a4c3-182">Mielőtt kiadja a rendeléseket a raktárba, meg kell győződnie arról, hogy a kitárolási helyek elegendő készlettel rendelkeznek az összes rendelés minden cikkéhez.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-182">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="0a4c3-183">A **Helyutasítás** beállítás áttekintésével határozza meg, hogy melyik kitárolási helyeket használja az értékesítési rendelések kitároláshoz.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-183">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span> <span data-ttu-id="0a4c3-184">Ha a Contoso bemutató adatkörnyezetét használja az *51-es* raktárhoz, erősítse meg, hogy van-e elérhető készlet.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-184">If you're using the Contoso demo data environment for warehouse *51*, confirm that there is available inventory.</span></span>

    <span data-ttu-id="0a4c3-185">A készletet minden sorhoz le kell foglalnia.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-185">You must now reserve the inventory for each line.</span></span>

1. <span data-ttu-id="0a4c3-186">Válassza ki a lefoglalni kívánt sorok egyikét az **Értékesítési rendelési sorok** gyorslapon.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-186">On the **Sales order lines** FastTab, select one of the lines that must be reserved.</span></span>
1. <span data-ttu-id="0a4c3-187">A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-187">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="0a4c3-188">A **Foglalás** oldalon, a műveleti panelen válassza az **Adag foglalása** elemet a foglalás alkalmazásához.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-188">On the **Reservation** page, on the Action Pane, select **Reserve lot** to apply the reservation.</span></span> <span data-ttu-id="0a4c3-189">Ezután zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-189">Then close the page.</span></span>
1. <span data-ttu-id="0a4c3-190">Ismételje meg a 8–10. lépést a fennmaradó foglalandó sorokkal.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-190">Repeat steps 8 through 10 for the remaining lines that must be reserved.</span></span>

    <span data-ttu-id="0a4c3-191">Most ki kell adnia az értékesítési rendelést a raktárnak.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-191">You must now release the sales order to the warehouse.</span></span>

1. <span data-ttu-id="0a4c3-192">Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-192">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="0a4c3-193">Egy üzenet jelenik meg, amely szerint létrejött egy szállítmány és egy hullám, és a hullám egy kötegben való futtatásra lett elküldve.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-193">You receive a message that states that a shipment and a wave have been created, and that the wave has been submitted to run in a batch.</span></span>

    <span data-ttu-id="0a4c3-194">Ha a hullám és az összes lefelé irányuló feladat befejeződött, egy munkaazonosító jön létre a hat sorból álló munkához.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-194">When the wave and all downstream jobs have been completed, a work ID is created for work that has six lines.</span></span> <span data-ttu-id="0a4c3-195">A sorok cikkszám szerint vannak rendezve.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-195">The lines are sorted by item number.</span></span>

1. <span data-ttu-id="0a4c3-196">Ugorjon a **Raktárkezelés \> Munka \> Minden munka** elemre a létrehozott munka megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-196">Go to **Warehouse management \> Work \> All work** to view the work that was created.</span></span> <span data-ttu-id="0a4c3-197">Jegyezze fel a **Munkaazonosító** értékét, mert a következő eljárásban is szüksége lesz rá.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-197">Make a note of the **Work ID** value, because you will need it in the next procedure.</span></span>

### <a name="initiate-picking-from-the-mobile-device"></a><span data-ttu-id="0a4c3-198">Kitárolás kezdeményezése mobileszközről</span><span class="sxs-lookup"><span data-stu-id="0a4c3-198">Initiate picking from the mobile device</span></span>

1. <span data-ttu-id="0a4c3-199">Jelentkezzen be a mobileszközbe olyan felhasználóként, aki a *51*. raktárban be van állítva.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-199">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="0a4c3-200">A mobileszközön válassza ki azt a menüt, amely az új mobileszköz-menüelemet tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-200">On the mobile device, select the menu that includes the new mobile device menu item.</span></span> <span data-ttu-id="0a4c3-201">Erre az esetre válassza a **Kimenő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-201">For this scenario, select **Outbound**.</span></span>
1. <span data-ttu-id="0a4c3-202">Válassza az **Értékesítési csoport sorának kitárolása** menüelemet a kitárolás kezdeményezéséhez.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-202">Select the **Sales group line picking** menu item to initiate the pick.</span></span>
1. <span data-ttu-id="0a4c3-203">Adja meg annak a **Munkaazonosítónak** az értékét, amelyről megjegyzést tett az előző eljárás során.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-203">Enter the **Work ID** value that you made a note of in the previous procedure.</span></span>

    <span data-ttu-id="0a4c3-204">Olyan kitárolási lépést kell látnia, ahol az *M9200* cikk minden kiválasztósora csoportosítva van, és utasítást kell kapnia arra, hogy az *M9200* cikkből egyenként *7-et* kell kitárolnia.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-204">You should see a pick step where all pick lines for item *M9200* are grouped, and you should receive an instruction to pick *7* each of item *M9200*.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0a4c3-205">A mobileszközön a három kitárolási munkasor kitárolási munkája egyetlen kitárolási lépésben lett összesítve a felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-205">On the mobile device, the pick work for the three pick work lines has been aggregated into one picking step for the user.</span></span>

1. <span data-ttu-id="0a4c3-206">Erősítse meg a kitárolási lépést.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-206">Confirm the pick step.</span></span>
1. <span data-ttu-id="0a4c3-207">Lépjen a folyamatban lévő munka oldalára a munkaazonosítóért, és figyelje meg, hogy az *M9200* számú cikk mindhárom kitárolási sora egyszerre lett lezárva.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-207">Go to the work page for the work ID, and notice that all three pick lines for item *M9200* were closed simultaneously.</span></span>
1. <span data-ttu-id="0a4c3-208">Menjen vissza a mobileszközhöz, és folytassa a kitárolással.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-208">Go back to the mobile device, and continue to pick.</span></span> <span data-ttu-id="0a4c3-209">Az *M9201 cikk* 4. munkasorának kell megjelennie.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-209">Work line 4 for item *M9201* should be presented.</span></span> <span data-ttu-id="0a4c3-210">Mivel a rendelésen csak egy munkasor volt, nincs mit összesíteni.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-210">Because there was only one work line on the order, there is nothing to aggregate.</span></span>
1. <span data-ttu-id="0a4c3-211">Erősítse meg a kitárolási lépést.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-211">Confirm the pick step.</span></span>
1. <span data-ttu-id="0a4c3-212">A mobileszközön az utolsó kitárolási lépés a munkarendelésből származó utolsó két kitárolási sort összesíti.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-212">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>
1. <span data-ttu-id="0a4c3-213">Hajtsa végre az egyenként *9* darab *M9202* számú cikkhez tartozó kitárolási lépést.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-213">Complete the pick step for *9* each of item *M9202*.</span></span>
1. <span data-ttu-id="0a4c3-214">Erősítse meg a betárolási lépést, valamint minden további kitárolás/betárolás párt a munka befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-214">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="0a4c3-215">A munkasorokat csak akkor lehet csoportosítani, ha azok sorrendben vannak.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-215">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="0a4c3-216">A következő funkciók nem támogatottak:</span><span class="sxs-lookup"><span data-stu-id="0a4c3-216">The following functionality isn't supported:</span></span>
>
>   - <span data-ttu-id="0a4c3-217">Tényleges súllyal rendelkező cikkek</span><span class="sxs-lookup"><span data-stu-id="0a4c3-217">Catch-weight items</span></span>
>
>    <span data-ttu-id="0a4c3-218">Ha a munkán vannak tényleges súlyú cikkek, hibaüzenet jelenik meg a kitárolás megkezdése előtt.</span><span class="sxs-lookup"><span data-stu-id="0a4c3-218">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>
>   - <span data-ttu-id="0a4c3-219">Darab kitárolása</span><span class="sxs-lookup"><span data-stu-id="0a4c3-219">Piece picking</span></span>
>   - <span data-ttu-id="0a4c3-220">Befejezetlen feltöltési munkával rendelkező munkasorok</span><span class="sxs-lookup"><span data-stu-id="0a4c3-220">Work lines that have unfinished replenishment work</span></span>
>   - <span data-ttu-id="0a4c3-221">Előírtnál nagyobb mennyiség kitárolása</span><span class="sxs-lookup"><span data-stu-id="0a4c3-221">Over-picking</span></span>
>   - <span data-ttu-id="0a4c3-222">Rövid kitárolás cikkek újbóli felosztásával</span><span class="sxs-lookup"><span data-stu-id="0a4c3-222">Short picking with item reallocation</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]