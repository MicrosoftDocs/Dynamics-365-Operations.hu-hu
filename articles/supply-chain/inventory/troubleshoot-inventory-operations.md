---
title: Készletműveletekkel kapcsolatos hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet javítani a készletműveletek használata során felmerülő problémákat.
author: sherry-zheng
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: ee1bfbf1b5aa736e1ee5bd38403b6c94c2bd036b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225002"
---
# <a name="troubleshoot-inventory-operations"></a><span data-ttu-id="26cc3-103">Készletműveletekkel kapcsolatos hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="26cc3-103">Troubleshoot inventory operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26cc3-104">Ez a témakör azt mutatja be, hogyan lehet javítani a készletműveletek használata során felmerülő problémákat.</span><span class="sxs-lookup"><span data-stu-id="26cc3-104">This topic describes how to fix issues that you might encounter while you work with inventory operations.</span></span>

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a><span data-ttu-id="26cc3-105">Nem található a "Munkafolyamat" legördülő párbeszédpanel a készletnaplókhoz.</span><span class="sxs-lookup"><span data-stu-id="26cc3-105">I can't find the "Workflow" drop-down dialog box for inventory journals.</span></span>

### <a name="issue-description"></a><span data-ttu-id="26cc3-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="26cc3-106">Issue description</span></span>

<span data-ttu-id="26cc3-107">A naplóoldalon nem található a **Munkafolyamat** legördülő párbeszédpanel, vagy a kapcsolód munkafolyamat-műveletek nem érhetők el.</span><span class="sxs-lookup"><span data-stu-id="26cc3-107">You can't find the **Workflow** drop-down dialog box on the journal page, or related workflow operations aren't available.</span></span>

<span data-ttu-id="26cc3-108">Ez a probléma három okból fordulhat elő, az alábbi alszakaszok szerint.</span><span class="sxs-lookup"><span data-stu-id="26cc3-108">This issue can occur for three reasons, as described in the following subsections.</span></span>

### <a name="issue-resolution-1"></a><span data-ttu-id="26cc3-109">Probléma 1. megoldása</span><span class="sxs-lookup"><span data-stu-id="26cc3-109">Issue resolution 1</span></span>

<span data-ttu-id="26cc3-110">Ha a probléma az összes felhasználóra vonatkozik, akkor előfordulhat, hogy a jóváhagyási munkafolyamat nincs hozzárendelve a naplónévhez.</span><span class="sxs-lookup"><span data-stu-id="26cc3-110">If the issue applies to all users, it might be occurring because the approval workflow hasn't been assigned to the journal name.</span></span> <span data-ttu-id="26cc3-111">Egy hiba javításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="26cc3-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="26cc3-112">Ugorjon a **Készletkezelés &gt; Beállítás &gt; Naplónevek &gt; Készlet** pontra.</span><span class="sxs-lookup"><span data-stu-id="26cc3-112">Go to **Inventory Management &gt; Setup &gt; Journal names &gt; Inventory**.</span></span>
1. <span data-ttu-id="26cc3-113">A beállítások megnyitásához válassza ki a napló nevét a lista paneljén.</span><span class="sxs-lookup"><span data-stu-id="26cc3-113">In the list pane, select a journal name to open its settings.</span></span>
1. <span data-ttu-id="26cc3-114">Az **Általános** gyorslapon állítsa a **Jóváhagyási munkafolyamat** beállítást *Igen* értékre.</span><span class="sxs-lookup"><span data-stu-id="26cc3-114">On the **General** FastTab, set the **Approval workflow** option to *Yes*.</span></span> <span data-ttu-id="26cc3-115">Kattintson az **Igen** gombra, ha a rendszer a módosítás megerősítését kéri.</span><span class="sxs-lookup"><span data-stu-id="26cc3-115">If you're prompted to confirm the change, select **Yes**.</span></span>
1. <span data-ttu-id="26cc3-116">A **Munkafolyamat** mezőben válassza ki azt a munkafolyamatot, amelyet a kiválasztott naplónévhez használni szeretne.</span><span class="sxs-lookup"><span data-stu-id="26cc3-116">In the **Workflow** field, select the workflow that you want to use for the selected journal name.</span></span>

### <a name="issue-resolution-2"></a><span data-ttu-id="26cc3-117">Probléma 2. megoldása</span><span class="sxs-lookup"><span data-stu-id="26cc3-117">Issue resolution 2</span></span>

<span data-ttu-id="26cc3-118">Ha a munkafolyamat egyedi kódot használ, problémák léphetnek fel a rendszer frissítése után.</span><span class="sxs-lookup"><span data-stu-id="26cc3-118">If your workflow uses customized code, issues might occur after you upgrade the system.</span></span> <span data-ttu-id="26cc3-119">Például a napló munkafolyamatában a **Küldés** gomb szürke színnel jelenhet meg, így nem jelölheti ki a küldés jóváhagyásához.</span><span class="sxs-lookup"><span data-stu-id="26cc3-119">For example, in the journal workflow, the **Submit** button might be grayed out so you can't select it to approve a submission.</span></span>

<span data-ttu-id="26cc3-120">Ha a **Küldés** gomb szürke színű, lehet, hogy testre szabták munkafolyamatot, ami azt jelenti, hogy a munkafolyamat módszere – a `canSubmitToWorkflow()` a `FormDataUtil` értékben – meg lett hosszabbítva.</span><span class="sxs-lookup"><span data-stu-id="26cc3-120">If the **Submit** button is grayed out, your workflow might have been customized, which means the method of the workflow, `canSubmitToWorkflow()` in `FormDataUtil`, has been extended.</span></span> <span data-ttu-id="26cc3-121">A probléma megoldásához módosítsa a `canSubmitToWorkflow()` módszer hosszabbításának módját, hogy a következő példában szereplő szerkezetet használja.</span><span class="sxs-lookup"><span data-stu-id="26cc3-121">To fix this issue, change the way that you extend the method of the `canSubmitToWorkflow()` to use the structure in the following example.</span></span>

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a><span data-ttu-id="26cc3-122">Probléma 3. megoldása</span><span class="sxs-lookup"><span data-stu-id="26cc3-122">Issue resolution 3</span></span>

<span data-ttu-id="26cc3-123">Ha a probléma csak néhány konkrét felhasználóra vonatkozik, akkor lehet, hogy ezeknek a felhasználóknak nincsenek meg a készletnaplókban a munkafolyamat-műveletek futtatásához szükséges biztonsági jogosultságai.</span><span class="sxs-lookup"><span data-stu-id="26cc3-123">If the issue applies only to a few specific users, those users might not have the security privileges that are required to run workflow operations on inventory journals.</span></span> <span data-ttu-id="26cc3-124">Ellenőrizze, hogy minden érintett felhasználó rendelkezik-e a *Készletnapló munkafolyamatának karbantartása* biztonsági jogosultsággal.</span><span class="sxs-lookup"><span data-stu-id="26cc3-124">Verify that each affected user has the *Maintain inventory journal workflow* security privilege.</span></span> <span data-ttu-id="26cc3-125">Alapértelmezés szerint ez a jogosultság ugyanolyan nevű feladathoz van hozzárendelve, és ez a feladat a *Raktári dolgozó* és *Raktárvezető* szerepkörre vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="26cc3-125">By default, this privilege is assigned to a duty that has same name, and that duty is applied to the *Warehouse worker* and *Warehouse manager* roles.</span></span>

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a><span data-ttu-id="26cc3-126">A készletnapló rendszer által zárolt állapotú marad, és a munkafolyamat kötegelt feladata nem működik.</span><span class="sxs-lookup"><span data-stu-id="26cc3-126">My inventory journal remains in system-locked status, and the workflow batch job doesn't work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="26cc3-127">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="26cc3-127">Issue description</span></span>

<span data-ttu-id="26cc3-128">Valamelyik készletnaplót valamilyen művelet zárolta, ezért nem lesz kiadva.</span><span class="sxs-lookup"><span data-stu-id="26cc3-128">One of your inventory journals is locked by some operation and isn't being released.</span></span> <span data-ttu-id="26cc3-129">Ha például a feladás során (amely rendszerzárolási művelet) ismeretlen hiba történik, a napló zárolt állapotú maradhat a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="26cc3-129">For example, if an unknown error occurs during posting (which is a system lock operation), the journal might remain in system-locked status.</span></span> <span data-ttu-id="26cc3-130">Ebben az esetben a munkafolyamat munkatétel-kezelője hibát jelez, miközben zárolja az ellenőrzést.</span><span class="sxs-lookup"><span data-stu-id="26cc3-130">In this case, the workflow work item handler will throw an error while it does lock validation.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="26cc3-131">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="26cc3-131">Issue resolution</span></span>

<span data-ttu-id="26cc3-132">Jelentkezzen be a Supply Chain Management SQL Server példányába, és ellenőrizze, hogy az **InventJournalTable.SystemBlocked** beállítása *1*-e.</span><span class="sxs-lookup"><span data-stu-id="26cc3-132">Sign in to the SQL Server instance for Supply Chain Management, and check whether **InventJournalTable.SystemBlocked** is set to *1*.</span></span> <span data-ttu-id="26cc3-133">Ha igen, győződjön meg róla, hogy a napló nem lehet zárolt állapotú, majd állítsa vissza az **InventJournalTable.SystemBlocked** értékét *0*-ra.</span><span class="sxs-lookup"><span data-stu-id="26cc3-133">If it is, make sure that the journal should not be in locked status, and then reset **InventJournalTable.SystemBlocked** to *0*.</span></span>

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a><span data-ttu-id="26cc3-134">A készletnapló munkafolyamata soha nem befejezett, és a napló nem szerkeszthető és nem is feladható.</span><span class="sxs-lookup"><span data-stu-id="26cc3-134">My inventory journal workflow is never completed, and the journal can't be edited or posted.</span></span>

### <a name="issue-description"></a><span data-ttu-id="26cc3-135">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="26cc3-135">Issue description</span></span>

<span data-ttu-id="26cc3-136">A napló-jóváhagyási munkafolyamat elküldése után a munkafolyamat feldolgozása leáll, és a naplókat nem lehet szerkeszteni és feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="26cc3-136">After you submit a journal approval workflow, workflow processing stops responding, and you can't edit or process your journals.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="26cc3-137">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="26cc3-137">Issue resolution</span></span>

<span data-ttu-id="26cc3-138">Több oka is lehet annak, hogy miért nem fejeződött be a munkafolyamat feldolgozása.</span><span class="sxs-lookup"><span data-stu-id="26cc3-138">There are several reasons why workflow processing might not be completed.</span></span> <span data-ttu-id="26cc3-139">Ellenőrizze a következő problémákat:</span><span class="sxs-lookup"><span data-stu-id="26cc3-139">Check for the following issues:</span></span>

- <span data-ttu-id="26cc3-140">Ugorjon a **Készletkezelés &gt; Beállítás &gt; Készletkezelési munkafolyamatok** elemhez, és tekintse át az érintett munkafolyamat konfigurációját.</span><span class="sxs-lookup"><span data-stu-id="26cc3-140">Go to **Inventory management &gt; Setup &gt; Inventory management workflows**, and review the configuration of the affected workflow.</span></span> <span data-ttu-id="26cc3-141">A további tudnivalókat lásd: [Készletnapló-jóváhagyási munkafolyamatok](inventory-journal-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="26cc3-141">For more information, see [Inventory journal approval workflows](inventory-journal-workflow.md).</span></span>
- <span data-ttu-id="26cc3-142">Lehet, hogy a munkafolyamat kivételt vagy hibát észlelt.</span><span class="sxs-lookup"><span data-stu-id="26cc3-142">The workflow might be encountering an exception or error.</span></span> <span data-ttu-id="26cc3-143">Tekintse át az érintett munkafolyamat munkatétel-előzményeit, és ellenőrizze, hogy tartalmaz-e olyan alkalmazáshibát, amely megszakítja a munkafolyamatot.</span><span class="sxs-lookup"><span data-stu-id="26cc3-143">Review the work item history of the affected workflow to see whether it includes an application error that terminates the workflow.</span></span>
- <span data-ttu-id="26cc3-144">A készletnapló csak jóváhagyás után frissíthető vagy szerkeszthető.</span><span class="sxs-lookup"><span data-stu-id="26cc3-144">The inventory journal can be updated or edited only if it's approved.</span></span> <span data-ttu-id="26cc3-145">Ha a visszahívás aktív, megpróbálhatja visszahívni a naplót.</span><span class="sxs-lookup"><span data-stu-id="26cc3-145">If recall is active, you can try to recall the journal.</span></span> <span data-ttu-id="26cc3-146">A munkafolyamat kötegelt feladatának végrehajtása több okból is felfüggeszthető.</span><span class="sxs-lookup"><span data-stu-id="26cc3-146">Execution of the workflow batch job might be suspended for multiple reasons.</span></span> <span data-ttu-id="26cc3-147">Ezeknek az okoknak egy részét a munkafolyamat-keretrendszer problémája okozhatja.</span><span class="sxs-lookup"><span data-stu-id="26cc3-147">Some of these reasons might be caused by the workflow framework issue.</span></span>

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a><span data-ttu-id="26cc3-148">A készletnapló munkafolyamat-feltételei csak a napló szintjén érvényesek, a sor szintjén nem</span><span class="sxs-lookup"><span data-stu-id="26cc3-148">Inventory journal workflow conditions apply only at the journal level, not at the line level</span></span>

### <a name="issue-description"></a><span data-ttu-id="26cc3-149">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="26cc3-149">Issue description</span></span>

<span data-ttu-id="26cc3-150">Ezt a problémát például akkor tapasztalhatja, ha a költség összegére egy készletnapló-munkafolyamati feltételt próbál beállítani.</span><span class="sxs-lookup"><span data-stu-id="26cc3-150">You might experience this issue if, for example, you try to set up an inventory journal workflow condition on the cost amount.</span></span> <span data-ttu-id="26cc3-151">Úgy állítsa be a feltételt, hogy az 1. lépés csak akkor fusson, ha a költség összege kisebb, mint 100.</span><span class="sxs-lookup"><span data-stu-id="26cc3-151">You set up the condition so that step 1 is run only when the cost amount is less than 100.</span></span> <span data-ttu-id="26cc3-152">Ezután úgy állítson be egy másik feltételt, hogy az 2. lépés csak akkor fusson, ha a költség összege több, mint 100 vagy azzal egyenlő.</span><span class="sxs-lookup"><span data-stu-id="26cc3-152">You then set up another condition so that step 2 is run only when the cost amount is more than or equal to 100.</span></span> <span data-ttu-id="26cc3-153">Ezután a munkafolyamat futtatásakor a munkafolyamat előzményei csak egy sort mutatnak, és az első feltétel kiértékelése mindig *igaz*, függetlenül az elküldött értéktől.</span><span class="sxs-lookup"><span data-stu-id="26cc3-153">Then, when the workflow is run, the workflow history shows only one line, and the first condition is always evaluated as *true*, regardless of the value that is submitted.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="26cc3-154">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="26cc3-154">Issue workaround</span></span>

<span data-ttu-id="26cc3-155">A jelenlegi verzióban a készlet munkafolyamat-feltételei csak a napló szintjén érvényesek, a sor szintjén nem.</span><span class="sxs-lookup"><span data-stu-id="26cc3-155">In the current release, inventory workflow conditions apply only at the journal level, not at the line level.</span></span> <span data-ttu-id="26cc3-156">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="26cc3-156">This behavior is by design.</span></span> <span data-ttu-id="26cc3-157">Azt ajánljuk, hogy csak naplószintű attribútumokkal állítsa be a feltételi kritériumokat.</span><span class="sxs-lookup"><span data-stu-id="26cc3-157">We recommend that you set your condition criteria only on journal-level attributes.</span></span>

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a><span data-ttu-id="26cc3-158">Az Aktuális listaoldal szűrőablaka nem úgy szűri az eredményeket, ahogyan azt elvárom.</span><span class="sxs-lookup"><span data-stu-id="26cc3-158">The filter pane on the On-hand list page doesn't filter results as I expect.</span></span>

### <a name="issue-description"></a><span data-ttu-id="26cc3-159">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="26cc3-159">Issue description</span></span>

<span data-ttu-id="26cc3-160">Az **Aktuális lista** oldal szűrőablakának szűrői nem úgy szűrik az eredményeket, ahogyan azt ön elvárja.</span><span class="sxs-lookup"><span data-stu-id="26cc3-160">The filters in the filter pane on the **On-hand list** page don't filter results as you expect.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="26cc3-161">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="26cc3-161">Issue resolution</span></span>

<span data-ttu-id="26cc3-162">Ez szándékosan van.</span><span class="sxs-lookup"><span data-stu-id="26cc3-162">This behavior is by design.</span></span>

<span data-ttu-id="26cc3-163">Az **Aktuális lista** lap egy részletes aktuális készlettáblából van összeállítva, amely az összes elérhető dimenziót tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="26cc3-163">The **On-hand list** page is assembled from a detailed on-hand inventory table that includes all available dimensions.</span></span> <span data-ttu-id="26cc3-164">A lap listája azonban összesítés jellegű.</span><span class="sxs-lookup"><span data-stu-id="26cc3-164">However, the list on this page is a summary.</span></span> <span data-ttu-id="26cc3-165">Így előfordulhat, hogy a forrástábla sorait egyesíti a megjelenített dimenzióknak megfelelő értékek összesítésével.</span><span class="sxs-lookup"><span data-stu-id="26cc3-165">Therefore, it might combine rows from the source table by aggregating values according to the dimensions that are shown.</span></span>

<span data-ttu-id="26cc3-166">A szűrők ablaktáblán beállított szűrők a forrástáblára vonatkoznak, nem az összesített listára.</span><span class="sxs-lookup"><span data-stu-id="26cc3-166">Filters that are set up in the filter pane apply to the source table, not to the aggregated list.</span></span> <span data-ttu-id="26cc3-167">Ez a viselkedés időnként nem várt eredményt hoz, ahogy [ezek a példák](inventory-on-hand-list.md#examples) mutatják.</span><span class="sxs-lookup"><span data-stu-id="26cc3-167">This behavior can sometimes produce unexpected results, as shown in [these examples](inventory-on-hand-list.md#examples).</span></span>

<span data-ttu-id="26cc3-168">Azonban a  [rácsban megadott szűrők](inventory-on-hand-list.md#grid-filters) *nem* alkalmazandók az összesített listára.</span><span class="sxs-lookup"><span data-stu-id="26cc3-168">However, the [filters that are provided in the grid](inventory-on-hand-list.md#grid-filters) *do* apply to the aggregated list.</span></span> <span data-ttu-id="26cc3-169">Ezek a szűrők egyaránt tartalmazzák a rács felső részén található GyorsSzűrő, valamint az egyes oszlopok fejlécének szűrőjét.</span><span class="sxs-lookup"><span data-stu-id="26cc3-169">These filters include both the QuickFilter at the top of the grid and the filter for each column heading.</span></span>

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a><span data-ttu-id="26cc3-170">Az egység- és egységmennyiség nem megfelelően működik a készletnaplóban.</span><span class="sxs-lookup"><span data-stu-id="26cc3-170">The unit and unit quantity aren't working correctly in the inventory journal.</span></span>

### <a name="issue-description"></a><span data-ttu-id="26cc3-171">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="26cc3-171">Issue description</span></span>

<span data-ttu-id="26cc3-172">Ha készletnapló egységekkel és mennyiségekkel dolgozik, a következő problémák valamelyike vagy mindkettő előfordulhat:</span><span class="sxs-lookup"><span data-stu-id="26cc3-172">You might encounter one or both of the following issues when you work with units and quantities in an inventory journal:</span></span>

- <span data-ttu-id="26cc3-173">Ha a kiadott termékhez be van állítva az átváltás egysége, akkor nem látja a készletnaplóban az egységeket és az egységmennyiségeket, és nem lehet benne módosítani az egységet.</span><span class="sxs-lookup"><span data-stu-id="26cc3-173">You don't see units or unit quantities in the inventory journal while a unit of conversion is set up for the released product, and you can't change the unit in the inventory journal.</span></span>
- <span data-ttu-id="26cc3-174">A készletnaplóban a **Mennyiség** és az **Egység** mezők láthatók, az **Egység mennyisége** mező azonban nem.</span><span class="sxs-lookup"><span data-stu-id="26cc3-174">You see the **Quantity** and **Unit** fields in the inventory journal, but you don't see the **Unit quantity** field.</span></span> <span data-ttu-id="26cc3-175">Ha módosítja az egységet, adjon meg egy mennyiséget, majd adja fel a naplót – a naplóban továbbra is látható az adott mennyiség eredeti mértékegysége.</span><span class="sxs-lookup"><span data-stu-id="26cc3-175">If you change the unit, enter a quantity, and post the journal, the journal still shows the original unit of measurement for that quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="26cc3-176">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="26cc3-176">Issue resolution</span></span>

<span data-ttu-id="26cc3-177">Ezen hiba javításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="26cc3-177">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="26cc3-178">A **Szolgáltatáskezelés** munkaterületen győződjön meg arról, hogy be van kapcsolva a *Mértékegység és az egységmennyiség használata a készletnaplókban* funkció.</span><span class="sxs-lookup"><span data-stu-id="26cc3-178">In the **Feature management** workspace, make sure that the *Using unit of measure and unit quantity in inventory journals* feature is turned on.</span></span> <span data-ttu-id="26cc3-179">Ez a funkció hozzáadja az **Egység** és az **Egységmennyiség** mezőket a naplóhoz.</span><span class="sxs-lookup"><span data-stu-id="26cc3-179">This feature adds the **Unit** and **Unit quantity** fields to the journal.</span></span>
1. <span data-ttu-id="26cc3-180">A funkció bekapcsolás után használja a következő módon a **Mennyiség**, **Egységmennyiség** és **Egység** mezőket:</span><span class="sxs-lookup"><span data-stu-id="26cc3-180">After the feature is turned on, use the **Quantity**, **Unit quantity**, and **Unit** fields in the following way:</span></span>

    - <span data-ttu-id="26cc3-181">**Mennyiség** – Határozza meg a mennyiséget a kiadott termékre meghatározott alapértelmezett egység használatával.</span><span class="sxs-lookup"><span data-stu-id="26cc3-181">**Quantity** – Specify the quantity by using the default unit that is defined for the released product.</span></span> <span data-ttu-id="26cc3-182">Ugyanakkor maga az alapértelmezett egység nem jelenik meg itt.</span><span class="sxs-lookup"><span data-stu-id="26cc3-182">However, the default unit itself isn't shown here.</span></span> <span data-ttu-id="26cc3-183">Ha az alapértelmezett egység és az **Egység** mezőben kiválasztott egység között átváltás van beállítva, akkor a **Mennyiség** mező automatikusan frissül az **Egységmennyiség** és az **Egység** mezőben megadott beállításoknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="26cc3-183">If a conversion is set up between the default unit and the unit that is selected in the **Unit** field, the **Quantity** field is automatically updated, based on the selections in the **Unit quantity** and **Unit** fields.</span></span>
    - <span data-ttu-id="26cc3-184">**Egységmennyiség** – Adja meg a mennyiséget az **Egység** mezőben kiválasztott egység használatával.</span><span class="sxs-lookup"><span data-stu-id="26cc3-184">**Unit quantity** – Specify the quantity by using the unit that is selected in the **Unit** field.</span></span>
    - <span data-ttu-id="26cc3-185">**Egység** – Válassza ki az **Egységmennyiség** mezőben szereplő értékre alkalmazandó egységet.</span><span class="sxs-lookup"><span data-stu-id="26cc3-185">**Unit** – Select the unit to apply to the value in the **Unit quantity** field.</span></span>

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a><span data-ttu-id="26cc3-186">A következő hibaüzenet jelenik meg: "A termékraktározási egységben a tizedesjegyek maximális száma 0."</span><span class="sxs-lookup"><span data-stu-id="26cc3-186">I receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

### <a name="issue-description"></a><span data-ttu-id="26cc3-187">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="26cc3-187">Issue description</span></span>

<span data-ttu-id="26cc3-188">Készlettranzakció vagy készletfoglalás feladása során a következő hibaüzenet jelenik meg: "A termékraktározási egységnél a tizedesjegyek maximális száma 0."</span><span class="sxs-lookup"><span data-stu-id="26cc3-188">When you try to post an inventory transaction or an inventory reservation, you receive the following error message: "Maximum number of decimals for the stock keeping unit is 0."</span></span>

<span data-ttu-id="26cc3-189">Ez a probléma akkor fordul elő, ha a készlettranzakció mennyisége olyan tizedesértékként van megadva, amely a mező által támogatott pontosság szintje alatti.</span><span class="sxs-lookup"><span data-stu-id="26cc3-189">This issue occurs when the inventory transaction quantity is specified as a decimal value that is below the level of precision that the field supports.</span></span> <span data-ttu-id="26cc3-190">Például egy készlettranzakcióhoz *0,5* mennyiséget adott meg, de csak egész számok támogatottak.</span><span class="sxs-lookup"><span data-stu-id="26cc3-190">For example, a quantity of *0.5* has been specified for an inventory transaction, but only integer quantities are supported.</span></span> <span data-ttu-id="26cc3-191">Ezért az értéknek *1-nek* kell lennie *0,5* helyett.</span><span class="sxs-lookup"><span data-stu-id="26cc3-191">Therefore, the value should be *1* instead of *0.5*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="26cc3-192">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="26cc3-192">Issue resolution</span></span>

1. <span data-ttu-id="26cc3-193">Futtassa a következő parancsfájlt az SQL Server-példányon a készlettranzakciók mennyiségének kerekítéséhez.</span><span class="sxs-lookup"><span data-stu-id="26cc3-193">Run the following script on your SQL Server instance to round quantities in the inventory transactions.</span></span> <span data-ttu-id="26cc3-194">Ez a parancsfájl korrigálja az **inventTrans** táblában található értékeket.</span><span class="sxs-lookup"><span data-stu-id="26cc3-194">This script will correct values in the **inventTrans** table.</span></span>

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. <span data-ttu-id="26cc3-195">Futtassa az adott anyagon az aktuális konzisztencia-ellenőrzést, ha a **hibajavítás** beállítás be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="26cc3-195">Run an on-hand consistency check where the **fix error** option is turned on.</span></span> <span data-ttu-id="26cc3-196">Ez az ellenőrzés korrigálja az **inventSum** táblában található értékeket.</span><span class="sxs-lookup"><span data-stu-id="26cc3-196">This check will correct values in the **inventSum** table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26cc3-197">Kifejezetten ajánljuk, hogy a környezetnek megfelelően körültekintően szerkessze a parancsfájlt, tesztelje tesztkörnyezetben, majd ellenőrizze az így kapott adatokat, mielőtt éles környezetben futtatja a parancsfájlt.</span><span class="sxs-lookup"><span data-stu-id="26cc3-197">We strongly recommend that you carefully edit the script as required for your environment, test it in a test environment, and then check the resulting data before you run the script in a production environment.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]