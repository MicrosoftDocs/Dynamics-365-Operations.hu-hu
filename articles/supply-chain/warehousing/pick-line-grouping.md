---
title: Kitárolási sor csoportosítása
description: Ez a témakör a kitárolási sor csoportosításáról nyújt áttekintést.
author: Mirzaab
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1b1d0135d450bc9be7b1303240a9ca70f95ae38e
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906268"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="4b6e8-103">Kitárolási sor csoportosítása</span><span class="sxs-lookup"><span data-stu-id="4b6e8-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b6e8-104">A kitárolási sor csoportosításával ugyanazzal a cikkel és hellyel rendelkező több munka összevonható egyetlen kitárolássá, amelyet a felhasználó mobileszközön kap meg.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-104">In pick line grouping, multiple work lines that have the same item and location can be combined into a single pick that is presented to the user on a mobile device.</span></span> <span data-ttu-id="4b6e8-105">A raktári dolgozók így a lehető leghatékonyabb utasításokat kapják, de továbbra is fennmarad a rendszerben a sorok szükséges elválasztása (például különböző tárolókban és rendeléseknél).</span><span class="sxs-lookup"><span data-stu-id="4b6e8-105">Therefore, warehouse workers can receive the most efficient instructions that are possible, but the required separation of work lines in the system is also maintained (for example, for different containers and orders).</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="4b6e8-106">Kitárolási sor csoportosításának beállítása</span><span class="sxs-lookup"><span data-stu-id="4b6e8-106">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="4b6e8-107">Mobileszköz-menüpont létrehozása</span><span class="sxs-lookup"><span data-stu-id="4b6e8-107">Create a mobile device menu item</span></span>

1. <span data-ttu-id="4b6e8-108">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menüpontjai** területre, és hozzon létre egy új menüelemet **Értékesítési csoport sorkitárolása – Felhasználó által irányított** névvel.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-108">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**, and create a new menu item that is named **Sales group line picking – User directed**.</span></span>
2. <span data-ttu-id="4b6e8-109">A **Mobileszköz menüpontjai** alatt állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="4b6e8-109">Under **Mobile device menu items**, set the following values:</span></span>

    - <span data-ttu-id="4b6e8-110">A **Menüelem neve** mezőbe írja be az **Értékesítési kitárolás – Sor csoportosítása** értéket.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-110">In the **Menu item name** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="4b6e8-111">A **Cím** mezőbe írja be az **Értékesítési kitárolás – Sor csoportosítása** értéket.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-111">In the **Title** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="4b6e8-112">A **Mód** mezőben válassza ki a **Munka** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-112">In the **Mode** field, select **Work**.</span></span>
    - <span data-ttu-id="4b6e8-113">A **Meglévő munka használata** lehetőséget állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-113">Set the **Use existing work** option to **Yes**.</span></span>

3. <span data-ttu-id="4b6e8-114">Az **Általános** gyorslapon beállíthatja a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="4b6e8-114">On the **General** FastTab, you can set the following values:</span></span>

    - <span data-ttu-id="4b6e8-115">Az **Irányítja** mezőben válassza a **Felhasználó által irányított** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-115">In the **Directed by** field, select **User directed**.</span></span>
    - <span data-ttu-id="4b6e8-116">Állítsa az **Azonosítótábla előállítása** beállítást **Igen** értékűre.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-116">Set the **Generate license plate** option to **Yes**.</span></span>
    - <span data-ttu-id="4b6e8-117">Állítsa a **Kitárolás csoportosítása** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-117">Set the **Group pick** option to **Yes**.</span></span>

4. <span data-ttu-id="4b6e8-118">A **Munkaosztályok** gyorslapon a következő lépések végrehajtásával állíthatja be a mobileszköz menüelemének érvényes munkaosztályait:</span><span class="sxs-lookup"><span data-stu-id="4b6e8-118">On the **Work classes** FastTab, follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="4b6e8-119">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-119">Select **New**.</span></span>
    2. <span data-ttu-id="4b6e8-120">A **Munkaosztály azonosítója** mezőben válassza az **Értékesítés** vagy az **SO kitárolás** lehetőséget attól függően, hogy milyen raktárt fog használni.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-120">In the **Work class ID** field, select **Sales** or **SO Pick**, depending on the warehouse that you will use.</span></span>
    3. <span data-ttu-id="4b6e8-121">A **Munkarendelés típusa** mezőben válassza ki az **Értékesítési rendelések** elemet.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-121">In the **Work order type** field, select **Sales orders**.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="4b6e8-122">Mobileszköz-menü beállítása</span><span class="sxs-lookup"><span data-stu-id="4b6e8-122">Set up a mobile device menu</span></span>

1. <span data-ttu-id="4b6e8-123">Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-123">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span> 
1. <span data-ttu-id="4b6e8-124">Adja hozzá az imént létrehozott menüelemet a kívánt menühöz.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-124">Add the menu item that you just created to the desired menu.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="4b6e8-125">Munkasablon beállítása</span><span class="sxs-lookup"><span data-stu-id="4b6e8-125">Set up a work template</span></span>

1. <span data-ttu-id="4b6e8-126">Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-126">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="4b6e8-127">Keresse meg a függvényhez használandó munkasablont.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-127">Find the work template that should be used with this function.</span></span> <span data-ttu-id="4b6e8-128">Ebben a példában válassza ki az **51 Kitárolás szakaszhoz** Contoso munkasablont.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-128">For this example, select the standard **51 Pick to stage** Contoso work template.</span></span>
1. <span data-ttu-id="4b6e8-129">A menüben válassza a **Lekérdezés szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-129">On the menu, select **Edit query**.</span></span>
1. <span data-ttu-id="4b6e8-130">A **Rendezés** lapon jelölje be a **Hozzáadás** lehetőséget, majd állítsa be a következő értékeket:</span><span class="sxs-lookup"><span data-stu-id="4b6e8-130">On the **Sorting** tab, select **Add**, and then set the following values:</span></span>

    - <span data-ttu-id="4b6e8-131">A **Táblázat** mezőben válassza az **Ideiglenes munkatranzakciók** opciót.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-131">In the **Table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="4b6e8-132">A **Származtatott tábla** mezőben válassza az **Ideiglenes munkatranzakciók** opciót.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-132">In the **Derived table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="4b6e8-133">A **Mező** mezőben válassza ki a **Cikkszám** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-133">In the **Field** field, select **Item number**.</span></span>
    - <span data-ttu-id="4b6e8-134">A **Keresés iránya** mezőben válassza a **Növekvő** értéket.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-134">In the **Search direction** field, select **Ascending**.</span></span>

> [!NOTE]
> <span data-ttu-id="4b6e8-135">A kitárolási sor csoportosítása funkcióhoz működéséhez a munkasorokat cikkazonosító szerint kell rendezni.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-135">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="4b6e8-136">Ha az azonos tételeket tartalmazó sorok nem egymás után lesznek sorba rendezve, a csoportosítás nem történik meg.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-136">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="4b6e8-137">Példa</span><span class="sxs-lookup"><span data-stu-id="4b6e8-137">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="4b6e8-138">Kitárolási munka létrehozása</span><span class="sxs-lookup"><span data-stu-id="4b6e8-138">Create picking work</span></span>

<span data-ttu-id="4b6e8-139">A kitárolási sor csoportosításának beállítása előtt létre kell hoznia néhány alkalmas kimenő munkát.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-139">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="4b6e8-140">Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-140">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
2. <span data-ttu-id="4b6e8-141">Új értékesítési rendelés létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-141">Select **New** to create a sales order.</span></span> 
3. <span data-ttu-id="4b6e8-142">Válasszon ki egy tetszőleges vevőt a **Vevői számla** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-142">In the **Customer account** field, select any customer.</span></span> 
4. <span data-ttu-id="4b6e8-143">Az **Általános** gyorslap **Raktár** mezőjében válassza ki a **51** értéket.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-143">On the **General** FastTab, in the **Warehouse** field, select **51**.</span></span> <span data-ttu-id="4b6e8-144">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-144">Then select **OK**.</span></span>
5. <span data-ttu-id="4b6e8-145">Az **Értékesítési rendelés sorai** területen adja hozzá a következő hat sort:</span><span class="sxs-lookup"><span data-stu-id="4b6e8-145">Under **Sales order lines**, add the following six lines:</span></span>

    - <span data-ttu-id="4b6e8-146">**1. sor:** A **Cikkszám** mezőben válassza az **M9200** értéket.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-146">**Line 1:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="4b6e8-147">Írja be a **3** értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-147">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="4b6e8-148">**2. sor:** A **Cikkszám** mezőben válassza az **M9201** értéket.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-148">**Line 2:** In the **Item number** field, select **M9201**.</span></span> <span data-ttu-id="4b6e8-149">Írja be a **3** értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-149">In the **Quantity** field, enter **3**.</span></span> 
    - <span data-ttu-id="4b6e8-150">**3. sor:** A **Cikkszám** mezőben válassza az **M9202** értéket.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-150">**Line 3:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="4b6e8-151">Írja be a **2** értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-151">In the **Quantity** field, enter **2**.</span></span> 
    - <span data-ttu-id="4b6e8-152">**4. sor:** A **Cikkszám** mezőben válassza az **M9200** értéket.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-152">**Line 4:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="4b6e8-153">Írja be a **1** értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-153">In the **Quantity** field, enter **1**.</span></span> 
    - <span data-ttu-id="4b6e8-154">**5. sor:** A **Cikkszám** mezőben válassza az **M9200** értéket.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-154">**Line 5:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="4b6e8-155">Írja be a **3** értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-155">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="4b6e8-156">**6. sor:** A **Cikkszám** mezőben válassza az **M9202** értéket.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-156">**Line 6:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="4b6e8-157">Írja be a **7** értéket a **Mennyiség** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-157">In the **Quantity** field, enter **7**.</span></span> 

    <span data-ttu-id="4b6e8-158">Az egyes cikkek teljes mennyiségének összegzése:</span><span class="sxs-lookup"><span data-stu-id="4b6e8-158">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="4b6e8-159">**M9200 cikk:** egyenként 7</span><span class="sxs-lookup"><span data-stu-id="4b6e8-159">**Item M9200:** 7 each</span></span>
    - <span data-ttu-id="4b6e8-160">**M9201 cikk:** egyenként 3</span><span class="sxs-lookup"><span data-stu-id="4b6e8-160">**Item M9201:** 3 each</span></span>
    - <span data-ttu-id="4b6e8-161">**M9202 cikk:** egyenként 9</span><span class="sxs-lookup"><span data-stu-id="4b6e8-161">**Item M9202:** 9 each</span></span>

6. <span data-ttu-id="4b6e8-162">Mielőtt kiadja a rendeléseket a raktárba, meg kell győződnie arról, hogy a kitárolási helyek elegendő készlettel rendelkeznek az összes rendelés minden cikkéhez.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-162">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="4b6e8-163">A **Helyutasítás** beállítás áttekintésével határozza meg, hogy melyik kitárolási helyeket használja az értékesítési rendelések kitároláshoz.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-163">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span>
7. <span data-ttu-id="4b6e8-164">Foglalja le a készletet, és adja ki a raktárba.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-164">Reserve the inventory, and release it to the warehouse.</span></span> <span data-ttu-id="4b6e8-165">Létrejön egy hat sort tartalmazó munkaazonosító.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-165">A work ID that has six lines is created.</span></span> <span data-ttu-id="4b6e8-166">A sorok cikkszám szerint vannak rendezve.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-166">The lines are sorted by item number.</span></span>

### <a name="run-the-mobile-device-flow"></a><span data-ttu-id="4b6e8-167">Futtassa a mobileszközön a folyamatot</span><span class="sxs-lookup"><span data-stu-id="4b6e8-167">Run the mobile device flow</span></span>

1. <span data-ttu-id="4b6e8-168">A mobileszközön válassza ki azt a menüt, amely az új mobileszköz-menüelemet tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-168">On the mobile device, select the menu that includes the new mobile device menu item.</span></span>
1. <span data-ttu-id="4b6e8-169">Válassza az **Értékesítési kitárolás – Sor csoportosítása** menüelemet, és kezdeményezzen egy kitárolást.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-169">Select the **Sales Pick – Group line** menu item, and initiate the pick.</span></span>

    <span data-ttu-id="4b6e8-170">Miután kiválasztotta a menüt, és beírta a munkaazonosítót, a kitárolási lépést láthatja, amelyben a M9200 cikk összes kitárolási sora csoportosítva van.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-170">After you select the menu and enter the work ID, you see the pick step where all pick lines for item M9200 are grouped.</span></span> <span data-ttu-id="4b6e8-171">Utasítást kap, hogy tároljon ki egyenként 7 darabot az M9200 számú cikkből.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-171">You receive an instruction to pick 7 each of item M9200.</span></span>

1. <span data-ttu-id="4b6e8-172">Erősítse meg a kitárolási lépést.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-172">Confirm the pick step.</span></span> 
1. <span data-ttu-id="4b6e8-173">Lépjen a folyamatban lévő munka ügyfélképernyőjére, és figyelje meg, hogy az M9200 számú cikk mindhárom kitárolási sora egyszerre lett lezárva.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-173">Go to the client screen of the work in process, and notice that all three pick lines for item M9200 were closed simultaneously.</span></span>

    <span data-ttu-id="4b6e8-174">Megjelenik a 4. munkasor.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-174">Work line 4 is presented.</span></span>

1. <span data-ttu-id="4b6e8-175">Erősítse meg a kitárolási lépést.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-175">Confirm the pick step.</span></span>

    <span data-ttu-id="4b6e8-176">A mobileszközön az utolsó kitárolási lépés a munkarendelésből származó utolsó két kitárolási sort összesíti.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-176">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>

1. <span data-ttu-id="4b6e8-177">Hajtsa végre az egyenként 9 darab M9202 számú cikkhez tartozó kitárolási lépést.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-177">Complete the pick step for 9 each of item M9202.</span></span>
1. <span data-ttu-id="4b6e8-178">Erősítse meg a betárolási lépést, valamint minden további kitárolás/betárolás párt a munka befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-178">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!NOTE]
> - <span data-ttu-id="4b6e8-179">A munkasorokat csak akkor lehet csoportosítani, ha azok sorrendben vannak.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-179">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="4b6e8-180">A következő funkciók nem támogatottak:</span><span class="sxs-lookup"><span data-stu-id="4b6e8-180">The following functionality isn't supported:</span></span>
>
>    - <span data-ttu-id="4b6e8-181">Tényleges súllyal rendelkező cikkek.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-181">Catch-weight items.</span></span> <span data-ttu-id="4b6e8-182">Ha a munkán vannak tényleges súlyú cikkek, hibaüzenet jelenik meg a kitárolás megkezdése előtt.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-182">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>    - <span data-ttu-id="4b6e8-183">Darab kitárolása.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-183">Piece picking.</span></span>
>    - <span data-ttu-id="4b6e8-184">Befejezetlen feltöltési munkával rendelkező munkasorok.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-184">Work lines that have unfinished replenishment work.</span></span>
>    - <span data-ttu-id="4b6e8-185">Előírtnál nagyobb mennyiség kitárolása.</span><span class="sxs-lookup"><span data-stu-id="4b6e8-185">Over-picking.</span></span>
