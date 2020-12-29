---
title: Felosztott munka
description: Ez a témakör a munkafelosztási funkcióval kapcsolatban tartalmaz információkat. Ez a funkció lehetővé teszi, hogy a nagy munkarendeléseket több kisebb munkarendelésre ossza fel, amelyeket azután több raktári dolgozóhoz rendelhet. Ily módon ugyanazt a munkát egyszerre több raktári dolgozó is kiválaszthatja.
author: mirzaab
manager: tfehr
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e74b630e72d70829938f0f34efd624509b1ba7c3
ms.sourcegitcommit: 531be324bf706ca727d777720df899d6ddd3c2d7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/05/2020
ms.locfileid: "4429992"
---
# <a name="work-split"></a><span data-ttu-id="c097a-105">Felosztott munka</span><span class="sxs-lookup"><span data-stu-id="c097a-105">Work split</span></span>

<span data-ttu-id="c097a-106">A munkafelosztás lehetővé teszi, hogy a nagy munkaazonosítókat (azaz több soros munkarendeléseket) több kisebb munkarendelésazonosítóra ossza fel, amelyeket azután több raktári dolgozóhoz rendelhet.</span><span class="sxs-lookup"><span data-stu-id="c097a-106">Work split functionality lets you split large work IDs (that is, work orders that have several lines) into several smaller work IDs that you can then assign to multiple warehouse workers.</span></span> <span data-ttu-id="c097a-107">Ily módon ugyanazt a munkátlétrehozási számot egyszerre több raktári dolgozó is kiválaszthatja.</span><span class="sxs-lookup"><span data-stu-id="c097a-107">In this way, the same work creation number can be picked simultaneously by several warehouse workers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c097a-108">Csak a *Nyitott* vagy *Folyamatban lévő* állapotú munkarendeléseket oszthatja fel.</span><span class="sxs-lookup"><span data-stu-id="c097a-108">You can split only work orders that have a status of *Open* or *In-progress*.</span></span>

## <a name="turn-on-the-work-split-functionality"></a><span data-ttu-id="c097a-109">A munkafelosztási funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="c097a-109">Turn on the work split functionality</span></span>

<span data-ttu-id="c097a-110">A munkafelosztási funkció használata előtt be kell kapcsolnia a funkciót és az annak előfeltételként szolgáló funkciót a rendszerében.</span><span class="sxs-lookup"><span data-stu-id="c097a-110">Before you can use the work split functionality, you must turn on the feature and its prerequisite feature in your system.</span></span> <span data-ttu-id="c097a-111">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkciók állapotának ellenőrzéséhez, és szükség esetén bekapcsolásukhoz.</span><span class="sxs-lookup"><span data-stu-id="c097a-111">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on as required.</span></span>

<span data-ttu-id="c097a-112">Először kapcsolja be a *Szervezet szintű munkazárolás* előfeltétel funkciót, ha még nincs bekapcsolva.</span><span class="sxs-lookup"><span data-stu-id="c097a-112">First, turn on the prerequisite *Organization-wide work blocking* feature if it isn't already turned on.</span></span> <span data-ttu-id="c097a-113">A **Funkció kezelése** munkaterületen ez a funkció a következő módon van listázva:</span><span class="sxs-lookup"><span data-stu-id="c097a-113">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="c097a-114">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="c097a-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="c097a-115">**Funkció neve:** *Szervezeti szintű munkazárolás*</span><span class="sxs-lookup"><span data-stu-id="c097a-115">**Feature name:** *Organization-wide work blocking*</span></span>

> [!NOTE]
> <span data-ttu-id="c097a-116">Ha ez a funkció aktiválva van, az adatfrissítés automatikusan érvénybe lép, miután a szolgáltatás be lett kapcsolva az összes jogi személynél.</span><span class="sxs-lookup"><span data-stu-id="c097a-116">When this feature is activated, a data upgrade is automatically applied after the feature is turned on across all legal entities.</span></span>

<span data-ttu-id="c097a-117">Ezután kapcsolja be a *Munkafelosztás* funkciót, amely a következőképpen jelenik meg:</span><span class="sxs-lookup"><span data-stu-id="c097a-117">Next, turn on the *Work split* feature, which is listed in the following way:</span></span>

- <span data-ttu-id="c097a-118">**Modul:** *Raktárkezelés*</span><span class="sxs-lookup"><span data-stu-id="c097a-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="c097a-119">**Szolgáltatás neve:** *Munkafelosztás*</span><span class="sxs-lookup"><span data-stu-id="c097a-119">**Feature name:** *Work split*</span></span>

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a><span data-ttu-id="c097a-120">A Munka részleteinek és az Összes munkaoldalnak a továbbfejlesztései</span><span class="sxs-lookup"><span data-stu-id="c097a-120">Enhancements to the Work details and All work pages</span></span>

<span data-ttu-id="c097a-121">A *Munkafelosztás* funkció a következő két gombot adja hozzá a **Munka részletei** és az **Összes munka** oldalak munkatábla **Munka** füléhez:</span><span class="sxs-lookup"><span data-stu-id="c097a-121">The *Work split* feature adds the following two buttons to the **Work** tab on the Action Pane of the **Work details** and **All work** pages:</span></span>

- <span data-ttu-id="c097a-122">**Munkafelosztás** – Ossza fel a munkaazonosítót több kisebb munkaazonosítóra, amelyet különböző dolgozók feldolgozhatnak.</span><span class="sxs-lookup"><span data-stu-id="c097a-122">**Split work** – Split the current work ID into multiple smaller work IDs that can be processed by separate workers.</span></span>
- <span data-ttu-id="c097a-123">**Munkafelosztási munkamenet megszakítása** – A munkafelosztási munkamenet megszakítása és a munka feldolgozásra való elérhetővé tétele.</span><span class="sxs-lookup"><span data-stu-id="c097a-123">**Cancel work split session** – Cancel the work split session, and make the work available for processing.</span></span>

<span data-ttu-id="c097a-124">![Munkafelosztás és Munkafelosztási munkamenet megszakítási gombok](media/Work_split_buttons.png "Munkafelosztás és Munkafelosztási munkamenet megszakítási gombok")</span><span class="sxs-lookup"><span data-stu-id="c097a-124">![Split work and Cancel work split session buttons](media/Work_split_buttons.png "Split work and Cancel work split session buttons")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c097a-125">A **Munkafelosztás** gomb nem érhető el, ha az alábbi feltételek bármelyike teljesül:</span><span class="sxs-lookup"><span data-stu-id="c097a-125">The **Split work** button won't be available if any of the following conditions are met:</span></span>
>
> - <span data-ttu-id="c097a-126">A munka állapota nem *Nyitott* vagy *Folyamatban lévő*.</span><span class="sxs-lookup"><span data-stu-id="c097a-126">The work status is something other than *Open* or *In progress*.</span></span>
> - <span data-ttu-id="c097a-127">A munkaazonosítóhoz tárolóazonosító van társítva.</span><span class="sxs-lookup"><span data-stu-id="c097a-127">A container ID is associated with the work ID.</span></span> <span data-ttu-id="c097a-128">(A tároló nem osztható fel szisztematikusan, mert fizikai műveleteket igényel.)</span><span class="sxs-lookup"><span data-stu-id="c097a-128">(A container can't be systematically split, because it requires physical actions.)</span></span>
> - <span data-ttu-id="c097a-129">A munka fürthöz van társítva.</span><span class="sxs-lookup"><span data-stu-id="c097a-129">The work is associated with a cluster.</span></span>
> - <span data-ttu-id="c097a-130">A munkarendelés típusa eltér az alábbi típusoktól:</span><span class="sxs-lookup"><span data-stu-id="c097a-130">The work order type is something other than one of the following types:</span></span>
>
>    - <span data-ttu-id="c097a-131">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="c097a-131">Sales orders</span></span>
>    - <span data-ttu-id="c097a-132">Nyersanyag kitárolása</span><span class="sxs-lookup"><span data-stu-id="c097a-132">Raw material picking</span></span>
>    - <span data-ttu-id="c097a-133">Átmozgatási probléma</span><span class="sxs-lookup"><span data-stu-id="c097a-133">Transfer issue</span></span>
>
> - <span data-ttu-id="c097a-134">A munkát jelenleg egy másik felhasználó osztja fel.</span><span class="sxs-lookup"><span data-stu-id="c097a-134">The work is currently being split by another user.</span></span> <span data-ttu-id="c097a-135">Ha megpróbálja megnyitni a felosztási lapot egy másik felhasználó által már felosztott munkához, a következő hibaüzenet jelenik meg: „A(z) \#\#\#\# azonosítójú munkát jelenleg felosztják.</span><span class="sxs-lookup"><span data-stu-id="c097a-135">If you try to open the splitting page for work that is already being split by another user, you receive the following error message: "The work with ID \#\#\#\# is currently being split.</span></span> <span data-ttu-id="c097a-136">Próbálja meg újra néhány perc múlva.</span><span class="sxs-lookup"><span data-stu-id="c097a-136">Retry in a few minutes.</span></span> <span data-ttu-id="c097a-137">Ha továbbra is ezt az üzenetet kapja, forduljon a feletteséhez.”</span><span class="sxs-lookup"><span data-stu-id="c097a-137">If you continue to receive this message, contact a supervisor."</span></span>

<span data-ttu-id="c097a-138">Egy új munkazárolási ok, a *Munkafelosztás* azt jelzi, hogy a munkaazonosító éppen felosztási folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="c097a-138">A new work blocking reason, *Split work*, indicates when the work ID is in the process of being split.</span></span> <span data-ttu-id="c097a-139">A **Munkafelosztás** lapon és a raktári alkalmazásban is megjelenik, ha a felhasználó megpróbálja futtatni a munkát.</span><span class="sxs-lookup"><span data-stu-id="c097a-139">It's shown both on the **Split work** page and in the warehouse app if a user tries to run the work.</span></span> <span data-ttu-id="c097a-140">Zárolási okok esetén a Munkaazonosítóban lévő **Zárolt hullám** mező neve a **Zárolt** értékre változik.</span><span class="sxs-lookup"><span data-stu-id="c097a-140">When blocking reasons are used, the name of the **Blocked wave** field from the work ID is changed to **Blocked**.</span></span>

## <a name="initiate-a-work-split"></a><span data-ttu-id="c097a-141">Munkafelosztás kezdeményezése</span><span class="sxs-lookup"><span data-stu-id="c097a-141">Initiate a work split</span></span>

<span data-ttu-id="c097a-142">A funkció hozzáad egy új **Munkafelosztás** oldalt, amely lehetővé teszi a felhasználók számára, hogy felosszák a munkasorokat a munkaazonosítóból.</span><span class="sxs-lookup"><span data-stu-id="c097a-142">The feature adds a new **Split work** page that lets users split work lines from the work ID.</span></span> <span data-ttu-id="c097a-143">Az oldal első megnyitásakor olyan sorok jelennek meg, amelyek munkaállapota *Nyitott* és amelyek feloszthatók.</span><span class="sxs-lookup"><span data-stu-id="c097a-143">When the page is first opened, it shows lines that have a work status of *Open* and that are available to be split.</span></span> <span data-ttu-id="c097a-144">A Művelet panelen válassza a **Munkafelosztás** lehetőséget a kijelölt munka feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="c097a-144">On the Action Pane, select **Split work** to process the selected work.</span></span>

<span data-ttu-id="c097a-145">A munka felosztásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c097a-145">To split work, follow these steps.</span></span>

1. <span data-ttu-id="c097a-146">Nyissa meg az alábbiak közül valamelyik lapot:</span><span class="sxs-lookup"><span data-stu-id="c097a-146">Open one of the following work pages:</span></span>

    - <span data-ttu-id="c097a-147">**Munka részletei** (**Raktárkezelés \> Munka \> Munka részletei**)</span><span class="sxs-lookup"><span data-stu-id="c097a-147">**Work details** (**Warehouse management \> Work \> Work details**)</span></span>
    - <span data-ttu-id="c097a-148">**Összes munka** (**Raktárkezelés \> Munka \> Összes munka**)</span><span class="sxs-lookup"><span data-stu-id="c097a-148">**All work** (**Warehouse management \> Work \> All work**)</span></span>

1. <span data-ttu-id="c097a-149">A rácsban válassza ki a felosztandó munkaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="c097a-149">In the grid, select a work ID to split.</span></span> <span data-ttu-id="c097a-150">A **Munkarendelés típusa** mezőt a következő értékek egyikére kell beállítani:</span><span class="sxs-lookup"><span data-stu-id="c097a-150">The **Work order type** field must be set to one of the following values:</span></span>

    - <span data-ttu-id="c097a-151">Értékesítési rendelés</span><span class="sxs-lookup"><span data-stu-id="c097a-151">Sales orders</span></span>
    - <span data-ttu-id="c097a-152">Nyersanyag kitárolása</span><span class="sxs-lookup"><span data-stu-id="c097a-152">Raw material picking</span></span>
    - <span data-ttu-id="c097a-153">Átmozgatási probléma</span><span class="sxs-lookup"><span data-stu-id="c097a-153">Transfer issue</span></span>

1. <span data-ttu-id="c097a-154">A Művelet ablaktábla **Munka** lapjának **Munka** csoportjában válassza a **Munkafelosztás** elemet.</span><span class="sxs-lookup"><span data-stu-id="c097a-154">On the Action Pane, on the **Work** tab, in the **Work** group, select **Split work**.</span></span>

    <span data-ttu-id="c097a-155">Megjelenik a **Munkafelosztás** lap, amely a megnyitott és felosztható munkasorokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="c097a-155">The **Split work** page appears and shows the work lines that are open and available to be split.</span></span> <span data-ttu-id="c097a-156">Alapértelmezés szerint csak az elérhető munkasorok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="c097a-156">By default, only available work lines are shown.</span></span> <span data-ttu-id="c097a-157">A munkaazonosító összes sorának megtekintéséhez (például olyan sorok, amelyek *Eltárolás* munkatípusúak), jelölje be az **Összes sor megjelenítése** jelölőnégyzetet a rács felett.</span><span class="sxs-lookup"><span data-stu-id="c097a-157">To view all lines for the work ID (for example, lines that have a work type of *Put*), select the **Show all lines** check box above the grid.</span></span>

    <span data-ttu-id="c097a-158">A következő üzenet jelenik meg: „A felhasználók nem tudják feldolgozni a munka sorait, amíg be nem fejezi a felosztást és be nem zárja ezt az oldalt.”</span><span class="sxs-lookup"><span data-stu-id="c097a-158">The following message is shown: "Users can't process lines of the work until you finish splitting and close this page."</span></span>

    <span data-ttu-id="c097a-159">Az aktuális munka **Munkazárolási ok** mezője a *Munkafelosztás* értékre lesz állítva, és a munka zárolva lesz.</span><span class="sxs-lookup"><span data-stu-id="c097a-159">The **Work blocking reason** field for the current work will be set to *Split work*, and the work will be blocked.</span></span>

    <span data-ttu-id="c097a-160">![Zárolás oka](media/Blocking_reason.png "Zárolás oka")</span><span class="sxs-lookup"><span data-stu-id="c097a-160">![Blocking reason](media/Blocking_reason.png "Blocking reason")</span></span>

1. <span data-ttu-id="c097a-161">Jelölje ki azokat a sorokat, amelyeket el szeretne távolítani az aktuális munkaazonosítóból, és hozzá szeretné adni egy új munkaazonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="c097a-161">Select the lines to remove from the current work ID and add to a new work ID.</span></span> <span data-ttu-id="c097a-162">A következő események zajlanak le:</span><span class="sxs-lookup"><span data-stu-id="c097a-162">The following events occur:</span></span>

    - <span data-ttu-id="c097a-163">A munka felosztásakor a kijelölt sor vagy sorok az eredeti munkaazonosítóból megszakadnak, majd átmásolódnak egy új munkaazonosítóba.</span><span class="sxs-lookup"><span data-stu-id="c097a-163">When you split the work, the selected line or lines from the original work ID are canceled and then copied to a new work ID.</span></span>
    - <span data-ttu-id="c097a-164">A meglévő munkasablon-szerkezete és az eltárolási helye (és a jövőbeli kitárolási/betárolási párok) megmarad.</span><span class="sxs-lookup"><span data-stu-id="c097a-164">The existing work template structure and the location of the put (and also future pick/put pairs) are preserved.</span></span> <span data-ttu-id="c097a-165">A következő munkaazonosító-mezők értékeit a program az eredeti munkából az új munkába másolja:</span><span class="sxs-lookup"><span data-stu-id="c097a-165">Values for the following work ID fields are copied from the original work to the new work:</span></span>

        - <span data-ttu-id="c097a-166">Rakományazonosító</span><span class="sxs-lookup"><span data-stu-id="c097a-166">Load ID</span></span>
        - <span data-ttu-id="c097a-167">Szállítmány azonosítója</span><span class="sxs-lookup"><span data-stu-id="c097a-167">Shipment ID</span></span>
        - <span data-ttu-id="c097a-168">Munkarendelés típusa</span><span class="sxs-lookup"><span data-stu-id="c097a-168">Work order type</span></span>
        - <span data-ttu-id="c097a-169">Rendelésszám</span><span class="sxs-lookup"><span data-stu-id="c097a-169">Order number</span></span>
        - <span data-ttu-id="c097a-170">Hely</span><span class="sxs-lookup"><span data-stu-id="c097a-170">Site</span></span>
        - <span data-ttu-id="c097a-171">Raktár</span><span class="sxs-lookup"><span data-stu-id="c097a-171">Warehouse</span></span>
        - <span data-ttu-id="c097a-172">Munka prioritása</span><span class="sxs-lookup"><span data-stu-id="c097a-172">Work priority</span></span>
        - <span data-ttu-id="c097a-173">Munkagyűjtő azonosítója</span><span class="sxs-lookup"><span data-stu-id="c097a-173">Work pool ID</span></span>
        - <span data-ttu-id="c097a-174">Hullámazonosító</span><span class="sxs-lookup"><span data-stu-id="c097a-174">Wave ID</span></span>
        - <span data-ttu-id="c097a-175">Munka létrehozási száma</span><span class="sxs-lookup"><span data-stu-id="c097a-175">Work creation number</span></span>

    - <span data-ttu-id="c097a-176">A következő mezők nem lesznek átmásolva az új munkaazonosítóba:</span><span class="sxs-lookup"><span data-stu-id="c097a-176">The following fields aren't copied to the new work ID:</span></span>

        - <span data-ttu-id="c097a-177">**Munkaazonosító** – A megfelelő számsorozatból új munkaazonosító jön létre.</span><span class="sxs-lookup"><span data-stu-id="c097a-177">**Work ID** – A new work ID is generated from the appropriate number sequence.</span></span>
        - <span data-ttu-id="c097a-178">**Munka állapota** – Ez a mező *Nyitott* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="c097a-178">**Work status** – This field is set to *Open*.</span></span>
        - <span data-ttu-id="c097a-179">**Zárolta:** – Ez a mező kezdetben üresre van állítva.</span><span class="sxs-lookup"><span data-stu-id="c097a-179">**Locked by** – This field is initially set to blank.</span></span>
        - <span data-ttu-id="c097a-180">**Cél azonosítótábla-azonosító** – Ez a mező üresen marad.</span><span class="sxs-lookup"><span data-stu-id="c097a-180">**Target license plate ID** – This field is left blank.</span></span>
        - <span data-ttu-id="c097a-181">**Létrehozott dátum és idő** – Ez a mező az aktuális dátumra és időre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="c097a-181">**Created date and time** – This field is set to the current date and time.</span></span>
        - <span data-ttu-id="c097a-182">**Zárolt hullám/befagyasztva** – Ez a mező újra kiszámításra kerül az eredeti és az új munkaazonosítóhoz.</span><span class="sxs-lookup"><span data-stu-id="c097a-182">**Blocked wave/frozen** – This field is recomputed for the original work ID and the new work ID.</span></span>

1. <span data-ttu-id="c097a-183">A Műveleti ablaktáblán kattintson a **Munkafelosztás** elemre.</span><span class="sxs-lookup"><span data-stu-id="c097a-183">On the Action Pane, select **Split work**.</span></span>

<span data-ttu-id="c097a-184">A munka felosztása közben a következő üzenet jelenik meg: „Feldolgozási művelet – Munka felosztása”.</span><span class="sxs-lookup"><span data-stu-id="c097a-184">While the work is being split, the following message is shown: "Processing operation - Split work".</span></span> <span data-ttu-id="c097a-185">Amíg ez az üzenet látható, a műveletet az üzenetmezőben a **Mégse** lehetőség kiválasztásával szakíthatja meg.</span><span class="sxs-lookup"><span data-stu-id="c097a-185">While this message is visible, you can cancel the operation by selecting **Cancel** in the message box.</span></span>

<span data-ttu-id="c097a-186">Ha az **Összes sor megjelenítése** jelölőnégyzet nincs bejelölve, a felosztott és megszakított sor a továbbiakban nem jelenik meg a rácsban.</span><span class="sxs-lookup"><span data-stu-id="c097a-186">If the **Show all lines** check box is cleared, the line that was split off and canceled will no longer appear in the grid.</span></span> <span data-ttu-id="c097a-187">Ha a jelölőnégyzet be van jelölve, látnia kell, hogy a sor **Munkaállapot** mezője *Érvénytelenítve* értékre változott.</span><span class="sxs-lookup"><span data-stu-id="c097a-187">If the check box is selected, you should see that the value of the **Work status** field for that line has changed to *Canceled*.</span></span>

<span data-ttu-id="c097a-188">A következő értesítés jelzi, hogy az új munkaazonosító létrejött: „A(z) \#\#\#\# munka az eredeti \#\#\#\# munkától való leválasztással jött létre."</span><span class="sxs-lookup"><span data-stu-id="c097a-188">The following notification is shown to indicate that the new work ID has been created: "Work \#\#\#\# has been created by splitting off from original work \#\#\#\#."</span></span>

<span data-ttu-id="c097a-189">Az eredeti munkaazonosító egyéb munkasorai (például *Kitárolás* sorok) szükség szerint módosulnak, hogy tükrözzék az érvénytelenített munkasorokat.</span><span class="sxs-lookup"><span data-stu-id="c097a-189">Other work lines from the original work ID (such as *Put* lines) will be adjusted as required to reflect the lines of work that have been canceled.</span></span> <span data-ttu-id="c097a-190">Ha például az eredeti munkaazonosító *Eltárolás* 15-ös mennyiségre vonatkozó *Kitárolás* sorral rendelkezett, és a 10 teljes mennyiséggel rendelkező érvénytelenített sorokat visszavonták, akkor az eredeti munkaazonosító új *Eltárolás* mennyisége mostantól 5 lesz.</span><span class="sxs-lookup"><span data-stu-id="c097a-190">For example, if the original work ID had a *Put* line for a quantity of 15, and *Pick* lines that have a total quantity of 10 were canceled, the new *Put* quantity on the original work ID will now be 5.</span></span>

<span data-ttu-id="c097a-191">Az új munka nem lesz azonnal hozzárendelve egyetlen felhasználóhoz sem.</span><span class="sxs-lookup"><span data-stu-id="c097a-191">The new work won't immediately be assigned to any user.</span></span> <span data-ttu-id="c097a-192">A **Munka részletei** lap standard funkciójával azonban most már hozzárendelheti egy felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="c097a-192">However, you can assign it to a user now, as required, by using the standard functionality of the **Work details** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c097a-193">Csak két vagy több elérhető munkasort tartalmazó munkaazonosítókat oszthat fel.</span><span class="sxs-lookup"><span data-stu-id="c097a-193">You can split only work IDs that contain two or more available work lines.</span></span> <span data-ttu-id="c097a-194">Ha a **Munkafelosztás** lehetőséget választja, amikor csak egy munkasor van, a következő hibaüzenet jelenik meg: „Legalább egy munkasornak a kezdeti munkában kell maradnia.”</span><span class="sxs-lookup"><span data-stu-id="c097a-194">If you select **Split work** when there is only one work line, you will receive the following error message: "At least one work line must remain on initial work."</span></span> <span data-ttu-id="c097a-195">Ebben az esetben nem történik felosztás.</span><span class="sxs-lookup"><span data-stu-id="c097a-195">In this case, no splitting will occur.</span></span>

## <a name="finish-a-work-split"></a><span data-ttu-id="c097a-196">Munkafelosztás befejezése</span><span class="sxs-lookup"><span data-stu-id="c097a-196">Finish a work split</span></span>

<span data-ttu-id="c097a-197">A *Munkafelosztás* befejezéséhez el kell távolítani a felosztási munka zárolási okát.</span><span class="sxs-lookup"><span data-stu-id="c097a-197">To finish splitting work, the *Split work* blocking reason must be removed.</span></span> <span data-ttu-id="c097a-198">Ezt a lépést kétféleképpen lehet befejezeni:</span><span class="sxs-lookup"><span data-stu-id="c097a-198">There are two ways to complete this step:</span></span>

- <span data-ttu-id="c097a-199">Az a felhasználó, aki felosztja a munkát, a jobb felső sarokban lévő **Bezárás** gombbal (**X**) zárja be a **Munkafelosztás** oldalt.</span><span class="sxs-lookup"><span data-stu-id="c097a-199">The user who is splitting the work closes the **Split work** page by selecting the **Close** button (**X**) in the upper-right corner.</span></span> <span data-ttu-id="c097a-200">Amikor az oldal be van zárva, a *Munkafelosztás* zárolási ok törlődik.</span><span class="sxs-lookup"><span data-stu-id="c097a-200">When the page is closed, the *Split Work* blocking reason will be removed.</span></span> <span data-ttu-id="c097a-201">A munka *Zárolt* állapota a újra lesz számítva, és ha nincs több zárolási oka ennek a munkának, akkor a munka fel lesz oldva.</span><span class="sxs-lookup"><span data-stu-id="c097a-201">The *Blocked* state of this work will be recomputed and, if there are no remaining blocking reasons for this work, the work will be unblocked.</span></span>
- <span data-ttu-id="c097a-202">Bármely felhasználó megnyithatja a munkaazonosítót, és kiválaszthatja a **Munkafelosztási munkamenet megszakítása** gombot a Művelet panelen.</span><span class="sxs-lookup"><span data-stu-id="c097a-202">Any user opens the work ID and selects the **Cancel work split session** button on the Action Pane.</span></span> <span data-ttu-id="c097a-203">A *Munkafelosztás* zárolásának oka eltávolításra kerül, és a munka *Zárolt* állapota újraszámításra kerül, ugyanúgy, mint amikor a **Munkafelosztás** oldal bezárul.</span><span class="sxs-lookup"><span data-stu-id="c097a-203">The *Split work* blocking reason will be removed, and the *Blocked* state of this work will be recomputed, just as when the **Split work** page is closed.</span></span>

<span data-ttu-id="c097a-204">A *Munkafelosztás* zárolási okának eltávolítása után a munka futtatható a mobileszközön, feltéve, hogy a **Zárolt** állapot *Nem* értékre van állítva a munkaazonosítón.</span><span class="sxs-lookup"><span data-stu-id="c097a-204">After the *Split work* blocking reason is removed, the work can be run on the mobile device, provided that the **Blocked** state is set to *No* on the work ID.</span></span>

## <a name="user-blocking-on-the-warehouse-app"></a><span data-ttu-id="c097a-205">Felhasználó zárolása a raktáralkalmazásban</span><span class="sxs-lookup"><span data-stu-id="c097a-205">User blocking on the warehouse app</span></span>

<span data-ttu-id="c097a-206">Ha megpróbálja használni a raktári alkalmazást a kitárolási munka felosztott munkával való összevetéséhez, a következő hibaüzenet jelenik meg: „A(z) \#\#\#\# azonosítójú munkát jelenleg felosztják.”</span><span class="sxs-lookup"><span data-stu-id="c097a-206">If you try to use the warehouse app to run picking work against a work ID that is being split, you will receive the following error message: "The work with ID \#\#\#\# is currently being split."</span></span> <span data-ttu-id="c097a-207">Ha ez az üzenet jelenik meg, válassza a **Mégse** gombot.</span><span class="sxs-lookup"><span data-stu-id="c097a-207">If you receive this message, select **Cancel**.</span></span> <span data-ttu-id="c097a-208">Ezután folytathatja más munka feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="c097a-208">You can then continue to process other work.</span></span>

## <a name="other-blocked-operations"></a><span data-ttu-id="c097a-209">Egyéb zárolt műveletek</span><span class="sxs-lookup"><span data-stu-id="c097a-209">Other blocked operations</span></span>

<span data-ttu-id="c097a-210">A munkasorokat, a munkakészlet-tranzakciókat vagy a felosztott munkához kapcsolódó feltöltési hivatkozásokat módosító műveletek sikertelenek lesznek, és a következő hibaüzenet jelenik meg: „A(z) \#\#\#\# azonosítóval végzett munka jelenleg felosztás alatt áll."</span><span class="sxs-lookup"><span data-stu-id="c097a-210">Any operations that modify work lines, work inventory transactions, or replenishment links that are related to work that is being split will fail, and the following error message will be shown: "The work with ID \#\#\#\# is currently being split."</span></span>
