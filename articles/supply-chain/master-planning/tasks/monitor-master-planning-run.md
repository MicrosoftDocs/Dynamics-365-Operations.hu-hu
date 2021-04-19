---
title: Alaptervezés futtatásának megfigyelése
description: Ez a témakör azt mutatja be, hogy a termeléstervező hogyan látja azt, hogy éppen folyamatban van-e az alaptervezés futtatása.
author: josaw1
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1733562768b3fe869f326bbfb47b6135a91b5cb
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829642"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="f42fb-103">Alaptervezés futtatásának megfigyelése</span><span class="sxs-lookup"><span data-stu-id="f42fb-103">Monitor a master planning run</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a><span data-ttu-id="f42fb-104">Gantt-diagram használata az Alaptervezési folyamat megjelenítéséhez</span><span class="sxs-lookup"><span data-stu-id="f42fb-104">Use a Gantt chart to visualize master planning progress</span></span>

<span data-ttu-id="f42fb-105">Az **Alaptervezési folyamat megtekintése** lapon megtekintheti a múltbeli Alaptervezés futtatások adatait Gantt-diagramként.</span><span class="sxs-lookup"><span data-stu-id="f42fb-105">From the **View master planning progress** page, you can view details of historical master planning runs as a Gantt chart.</span></span> <span data-ttu-id="f42fb-106">Ez a funkció segít megérteni az Alaptervezés különböző fázisaiban töltött időt.</span><span class="sxs-lookup"><span data-stu-id="f42fb-106">This functionality can help you understand the time that is spent on the various phases of master planning.</span></span> <span data-ttu-id="f42fb-107">Egy aktuális aktív tervezési feladathoz az **Alaptervezési folyamat megtekintése** lapon nyomon követheti az előrehaladást, és megtekintheti a becsült hátralévő időt.</span><span class="sxs-lookup"><span data-stu-id="f42fb-107">For a current active planning job, the **View master planning progress** page can be used to track progress and view the estimated remaining time.</span></span>

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a><span data-ttu-id="f42fb-108">Az alaptervezés folyamatmegjelenítési funkciójának bekapcsolása és használata</span><span class="sxs-lookup"><span data-stu-id="f42fb-108">Turn on and use the Master plan progress visualization feature</span></span>

<span data-ttu-id="f42fb-109">A funkció használatához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f42fb-109">To use this functionality, follow these steps.</span></span>

1. <span data-ttu-id="f42fb-110">A **funkciókezelés** munkaterületen az **új** lapon válassza ki a listában az **Alaptervezés folyamatmegjelenítése** elemet.</span><span class="sxs-lookup"><span data-stu-id="f42fb-110">In the **Feature management** workspace, on the **New** tab, select **Master planning progress visualization** in the list.</span></span> <span data-ttu-id="f42fb-111">Ha a funkció nem jelenik meg az **új** lapon, akkor keresse a **nem engedélyezett és** az **Összes** lapon.</span><span class="sxs-lookup"><span data-stu-id="f42fb-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="f42fb-112">Válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f42fb-112">Select **Enable now**.</span></span> <span data-ttu-id="f42fb-113">Azt is megteheti, hogy az **ütemezés** elemet választja, majd azt az időpontot, amikor be kívánja kapcsolni a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="f42fb-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

<span data-ttu-id="f42fb-114">Az **Alaptervezés folyamatmegjelenítése** lap a múltbeli tervezési feladatok és az aktív tervezési feladatok megjelenítésére is képes.</span><span class="sxs-lookup"><span data-stu-id="f42fb-114">The **View master planning progress** page can display both historical planning jobs and active planning jobs.</span></span> 

<span data-ttu-id="f42fb-115">A korábbi tervezési feladatok megtekintéséhez két lehetőség közül választhat.</span><span class="sxs-lookup"><span data-stu-id="f42fb-115">To view historical planning jobs, there are two options.</span></span> 

1. <span data-ttu-id="f42fb-116">Nyissa meg az **Alaptervezés \> Beállítás \> Tervek \> Alaptervek** elemet, majd kattintson a műveleti ablak **előzmények** elemére.</span><span class="sxs-lookup"><span data-stu-id="f42fb-116">Go to **Master planning \> Setup \> Plans \> Master plans**, and then, on the Action Pane, select **History**.</span></span> <span data-ttu-id="f42fb-117">Válassza ki a kívánt feladatot, válassza ki a **Lekérdezések** elemet, majd válassza a **Folyamatjelző megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f42fb-117">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>
1. <span data-ttu-id="f42fb-118">Lépjen az **Alaptervezés \> Munkaterületek \> Alaptervezés** elemre, az Alaptervezés mozaikján kattintson az **Előzmények** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f42fb-118">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **History**.</span></span> <span data-ttu-id="f42fb-119">Válassza ki a kívánt feladatot, válassza ki a **Lekérdezések** elemet, majd válassza a **Folyamatjelző megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f42fb-119">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="f42fb-120">Az aktív tervezési feladatok megtekintéséhez két lehetőség közül választhat.</span><span class="sxs-lookup"><span data-stu-id="f42fb-120">To view active planning jobs, there are two options.</span></span> 
1. <span data-ttu-id="f42fb-121">Lépjen az **Alaptervezés \> Munkaterületek \> Alaptervezés** elemre, a műveleti ablaktáblán kattintson a **Befejezetlen tervezési folyamat** elemre.</span><span class="sxs-lookup"><span data-stu-id="f42fb-121">Go to **Master planning \> Workspaces \> Master planning**, on the Action Pane, select **Unfinished planning process**.</span></span> <span data-ttu-id="f42fb-122">Válassza ki a kívánt feladatot, válassza ki a **Lekérdezések** elemet, majd válassza a **Folyamatjelző megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f42fb-122">With the desired job selected, select **Inquiries**,  and then select **View progress**.</span></span>
1. <span data-ttu-id="f42fb-123">Lépjen az **Alaptervezés \> Munkaterületek \> Alaptervezés** elemre, az Alaptervezés mozaikján kattintson az **Folyamatjelző megtekintése** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f42fb-123">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **View progress**.</span></span> <span data-ttu-id="f42fb-124">Válassza ki a kívánt feladatot, válassza ki a **Lekérdezések** elemet, majd válassza a **Folyamatjelző megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f42fb-124">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="f42fb-125">Ne feledje, hogy csak egy tervezési feladat feldolgozása során tekinthetők meg az aktív feladatok.</span><span class="sxs-lookup"><span data-stu-id="f42fb-125">Note you can view active jobs only when a planning job is processing.</span></span>

### <a name="analyze-a-master-planning-job"></a><span data-ttu-id="f42fb-126">Alaptervezési feladat elemzése</span><span class="sxs-lookup"><span data-stu-id="f42fb-126">Analyze a master planning job</span></span>

<span data-ttu-id="f42fb-127">A Gantt-diagramban a következő tervezési folyamatok kibontásával megjelenítheti az eltöltött idő további adatait:</span><span class="sxs-lookup"><span data-stu-id="f42fb-127">In the Gantt chart, you can expand each of the following planning processes to view additional details about the time that is spent:</span></span>

- <span data-ttu-id="f42fb-128">Inicializálás</span><span class="sxs-lookup"><span data-stu-id="f42fb-128">Initializing</span></span>
- <span data-ttu-id="f42fb-129">Adatok törlése és beszúrása</span><span class="sxs-lookup"><span data-stu-id="f42fb-129">Deleting and inserting data</span></span>
- <span data-ttu-id="f42fb-130">Fedezettervezés</span><span class="sxs-lookup"><span data-stu-id="f42fb-130">Coverage planning</span></span>
- <span data-ttu-id="f42fb-131">Késések</span><span class="sxs-lookup"><span data-stu-id="f42fb-131">Delays</span></span>
- <span data-ttu-id="f42fb-132">Műveletkérő üzenetek</span><span class="sxs-lookup"><span data-stu-id="f42fb-132">Action messages</span></span>
- <span data-ttu-id="f42fb-133">Véglegesítés</span><span class="sxs-lookup"><span data-stu-id="f42fb-133">Finalization</span></span>
- <span data-ttu-id="f42fb-134">Automatikus megerősítés</span><span class="sxs-lookup"><span data-stu-id="f42fb-134">Auto-firming</span></span>

<span data-ttu-id="f42fb-135">A Gantt-diagram hasznos eszköz, ha meg szeretné tekinteni a műveletkérő üzenetek használatával járó hatásokat.</span><span class="sxs-lookup"><span data-stu-id="f42fb-135">The Gantt chart is a useful tool if you want to view the impact of using action messages.</span></span>

#### <a name="navigation-in-the-gantt-chart"></a><span data-ttu-id="f42fb-136">Navigálás a Gantt-diagramon</span><span class="sxs-lookup"><span data-stu-id="f42fb-136">Navigation in the Gantt chart</span></span>

- <span data-ttu-id="f42fb-137">A kiválasztott csoport kibontásához és a részletek megjelenítéséhez válassza ki a fanézetben a pluszjelet (**+**).</span><span class="sxs-lookup"><span data-stu-id="f42fb-137">To expand the selected group and show the details, select the plus sign (**+**) in the tree view.</span></span>
- <span data-ttu-id="f42fb-138">A kiválasztott csoport összecsukásához válassza ki a mínusz jelet (**–**) a fanézetben.</span><span class="sxs-lookup"><span data-stu-id="f42fb-138">To collapse the selected group, select the minus sign (**–**) in the tree view.</span></span>
- <span data-ttu-id="f42fb-139">A billentyűzetet navigálásra használhatja.</span><span class="sxs-lookup"><span data-stu-id="f42fb-139">You can use your keyboard for navigation.</span></span> <span data-ttu-id="f42fb-140">A **Felfelé nyíl** és **Lefelé nyíl** billentyűk segítségével mozoghat a sorok között.</span><span class="sxs-lookup"><span data-stu-id="f42fb-140">Use the **Up arrow** and **Down arrow** keys to move between rows.</span></span> <span data-ttu-id="f42fb-141">A **Jobbra nyíl** és a **Balra nyíl** billentyűk segítségével bonthatja ki és csukhatja össze a csoportokat.</span><span class="sxs-lookup"><span data-stu-id="f42fb-141">Use the **Right arrow** and **Left arrow** keys to expand and collapse groups.</span></span>
- <span data-ttu-id="f42fb-142">A Gantt-diagram minden szintjének megnyitásához vagy bezárásához válassza az **Összes kibontása** vagy **Össze összecsukása** elemet.</span><span class="sxs-lookup"><span data-stu-id="f42fb-142">To open or close all levels in the Gantt chart, select **Expand all** or **Collapse all**.</span></span>
- <span data-ttu-id="f42fb-143">A kapcsolódó feldolgozási idő megtekintéséhez vigye a mutatót egy feladatra.</span><span class="sxs-lookup"><span data-stu-id="f42fb-143">To view the related processing time, hover over a task.</span></span> <span data-ttu-id="f42fb-144">(A feladatok a Gantt-diagram legalacsonyabb szintje.)</span><span class="sxs-lookup"><span data-stu-id="f42fb-144">(Tasks are the lowest level in the Gantt chart.)</span></span>

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a><span data-ttu-id="f42fb-145">További alaptervezési futtatás megtekintése a feladatok összehasonlításához</span><span class="sxs-lookup"><span data-stu-id="f42fb-145">View an additional master planning run to compare jobs</span></span>

<span data-ttu-id="f42fb-146">Ha kijelöl egy Alaptervezési feladatot a **További alaptervezés-futtatás megjelenítése** mezőben, akkor a Gantt-diagramban megtekinthet egy másik alaptervezés-futtatást és összehasonlíthatja a két feladatot.</span><span class="sxs-lookup"><span data-stu-id="f42fb-146">By selecting a master planning job on field **Show additional master planning run**, you can view an additional master planning run in the Gantt chart and compare the two jobs.</span></span>

#### <a name="bom-level-display"></a><span data-ttu-id="f42fb-147">Anyagjegyzék szintű megjelenítés</span><span class="sxs-lookup"><span data-stu-id="f42fb-147">BOM-level display</span></span>

<span data-ttu-id="f42fb-148">A fedezeti tervezés, a késések, a műveletek és a megerősítés esetén a megjelenített anyagjegyzékszint különböző.</span><span class="sxs-lookup"><span data-stu-id="f42fb-148">Bill of materials (BOM) levels are shown differently for coverage planning, delays, actions, and firming.</span></span>

- <span data-ttu-id="f42fb-149">**Fedezeti tervezés** – az anyagjegyzékszintek a várakozásnak megfelelően jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="f42fb-149">**Coverage planning** – BOM levels are shown as expected.</span></span> <span data-ttu-id="f42fb-150">Ezek a fentről lefelé haladva kerülnek kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="f42fb-150">They are calculated from the top down.</span></span>

    <span data-ttu-id="f42fb-151">**Példa:** AJ-szint 0, 1, 2</span><span class="sxs-lookup"><span data-stu-id="f42fb-151">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="f42fb-152">**Késések** – az AJ-szintek a fedezeti tervezés AJ-szintjének a –1-gyel való szorzatával jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="f42fb-152">**Delays** – BOM levels are shown as the coverage planning BOM levels multiplied by –1.</span></span> <span data-ttu-id="f42fb-153">(Más szóval negatív előjellel rendelkeznek.)</span><span class="sxs-lookup"><span data-stu-id="f42fb-153">(In other words, they have a negative sign.)</span></span>

    <span data-ttu-id="f42fb-154">**Példa:** AJ-szint -2, -1, 0</span><span class="sxs-lookup"><span data-stu-id="f42fb-154">**Example:** BOM level –2, –1, 0</span></span>

- <span data-ttu-id="f42fb-155">**Műveletkérő üzenet** – az anyagjegyzékszintek a várakozásnak megfelelően jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="f42fb-155">**Action message** – BOM levels are shown as expected.</span></span> <span data-ttu-id="f42fb-156">Ezek a fentről lefelé haladva kerülnek kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="f42fb-156">They are calculated from the top down.</span></span>

    <span data-ttu-id="f42fb-157">**Példa:** AJ-szint 0, 1, 2</span><span class="sxs-lookup"><span data-stu-id="f42fb-157">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="f42fb-158">**Automatikus megerősítés** – Az anyagjegyzék szintje 999 mínusz a fedezeti tervezés anyagjegyzék-szintje.</span><span class="sxs-lookup"><span data-stu-id="f42fb-158">**Auto-firming** – BOM levels are shown as 999 minus the coverage planning BOM level.</span></span>

    <span data-ttu-id="f42fb-159">**Példa:** AJ-szint 999, 998, 997</span><span class="sxs-lookup"><span data-stu-id="f42fb-159">**Example:** BOM level 999, 998, 997</span></span>

<span data-ttu-id="f42fb-160">A következő táblázat összegzi a viselkedést.</span><span class="sxs-lookup"><span data-stu-id="f42fb-160">The following table summarizes the behavior.</span></span>

| <span data-ttu-id="f42fb-161">A megjelenített AJ-szint</span><span class="sxs-lookup"><span data-stu-id="f42fb-161">BOM level that is shown</span></span> | <span data-ttu-id="f42fb-162">Végtermék</span><span class="sxs-lookup"><span data-stu-id="f42fb-162">End item</span></span> | <span data-ttu-id="f42fb-163">Részösszetevő</span><span class="sxs-lookup"><span data-stu-id="f42fb-163">Subcomponent</span></span> | <span data-ttu-id="f42fb-164">Nyersanyag</span><span class="sxs-lookup"><span data-stu-id="f42fb-164">Raw material</span></span> |
|---|---|---|---|
| <span data-ttu-id="f42fb-165">Fedezettervezés</span><span class="sxs-lookup"><span data-stu-id="f42fb-165">Coverage planning</span></span> | <span data-ttu-id="f42fb-166">0</span><span class="sxs-lookup"><span data-stu-id="f42fb-166">0</span></span> | <span data-ttu-id="f42fb-167">1</span><span class="sxs-lookup"><span data-stu-id="f42fb-167">1</span></span> | <span data-ttu-id="f42fb-168">2</span><span class="sxs-lookup"><span data-stu-id="f42fb-168">2</span></span> |
| <span data-ttu-id="f42fb-169">Késések</span><span class="sxs-lookup"><span data-stu-id="f42fb-169">Delays</span></span> | <span data-ttu-id="f42fb-170">0</span><span class="sxs-lookup"><span data-stu-id="f42fb-170">0</span></span> | <span data-ttu-id="f42fb-171">–1</span><span class="sxs-lookup"><span data-stu-id="f42fb-171">–1</span></span> | <span data-ttu-id="f42fb-172">–2</span><span class="sxs-lookup"><span data-stu-id="f42fb-172">–2</span></span> |
| <span data-ttu-id="f42fb-173">Műveletkérő üzenet</span><span class="sxs-lookup"><span data-stu-id="f42fb-173">Action message</span></span> | <span data-ttu-id="f42fb-174">0</span><span class="sxs-lookup"><span data-stu-id="f42fb-174">0</span></span> | <span data-ttu-id="f42fb-175">1</span><span class="sxs-lookup"><span data-stu-id="f42fb-175">1</span></span> | <span data-ttu-id="f42fb-176">2</span><span class="sxs-lookup"><span data-stu-id="f42fb-176">2</span></span> |
| <span data-ttu-id="f42fb-177">Automatikus megerősítés</span><span class="sxs-lookup"><span data-stu-id="f42fb-177">Auto-firming</span></span> | <span data-ttu-id="f42fb-178">999</span><span class="sxs-lookup"><span data-stu-id="f42fb-178">999</span></span> | <span data-ttu-id="f42fb-179">998</span><span class="sxs-lookup"><span data-stu-id="f42fb-179">998</span></span> | <span data-ttu-id="f42fb-180">997</span><span class="sxs-lookup"><span data-stu-id="f42fb-180">997</span></span> |

#### <a name="visualize-progress"></a><span data-ttu-id="f42fb-181">Folyamatjelző megjelenítése</span><span class="sxs-lookup"><span data-stu-id="f42fb-181">Visualize progress</span></span>

<span data-ttu-id="f42fb-182">Ha éppen futó alaptervezési feladatot jelenít meg, a folyamat a Gantt-diagram színeivel jeleníthető meg.</span><span class="sxs-lookup"><span data-stu-id="f42fb-182">If you view a master planning job that is currently running, progress is shown through colors in the Gantt chart.</span></span> <span data-ttu-id="f42fb-183">A kék témára a következő színek érvényesek:</span><span class="sxs-lookup"><span data-stu-id="f42fb-183">The following colors apply to the blue theme.</span></span> <span data-ttu-id="f42fb-184">Más színtémák esetében a színek különböznek.</span><span class="sxs-lookup"><span data-stu-id="f42fb-184">For other color themes, the colors will differ.</span></span>

- <span data-ttu-id="f42fb-185">**Sötétkék** – Befejezett tervezési feladatok.</span><span class="sxs-lookup"><span data-stu-id="f42fb-185">**Dark blue** – Completed planning tasks.</span></span>
- <span data-ttu-id="f42fb-186">**Narancs** – a jelenleg folyamatban lévő feladat.</span><span class="sxs-lookup"><span data-stu-id="f42fb-186">**Orange** – The task that is currently in progress.</span></span>
- <span data-ttu-id="f42fb-187">**Világoskék** – a hátralévő feladatok becslése.</span><span class="sxs-lookup"><span data-stu-id="f42fb-187">**Light blue** – The estimate for remaining tasks.</span></span>

<span data-ttu-id="f42fb-188">A szín csak a Gantt-diagram legalacsonyabb szintjén jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="f42fb-188">The color is shown only on the lowest level in the Gantt chart.</span></span> <span data-ttu-id="f42fb-189">Az **összes kibontása** parancsra kattintva megtekintheti az Alaptervezési feladat összes feladatát.</span><span class="sxs-lookup"><span data-stu-id="f42fb-189">Select **Expand all** to view all tasks in the master planning job.</span></span> <span data-ttu-id="f42fb-190">A fennmaradó feladatok becslése a múltbeli Alaptervezési feladatok alapján történik.</span><span class="sxs-lookup"><span data-stu-id="f42fb-190">The estimate of remaining tasks is based on historical master planning jobs.</span></span>

## <a name="run-master-planning-and-track-processing-time"></a><span data-ttu-id="f42fb-191">Alaptervezés futtatása és a feldolgozási idő nyomon követése</span><span class="sxs-lookup"><span data-stu-id="f42fb-191">Run master planning and track processing time</span></span>

1. <span data-ttu-id="f42fb-192">Az alapértelmezett irányítópulton válassza az **Alaptervezés** elemet.</span><span class="sxs-lookup"><span data-stu-id="f42fb-192">On the default dashboard, select **Master planning**.</span></span>
1. <span data-ttu-id="f42fb-193">A **Terv** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f42fb-193">In the **Plan** field, enter or select a value.</span></span>
1. <span data-ttu-id="f42fb-194">Válassza a **Futtatás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="f42fb-194">Select **Run**.</span></span>
1. <span data-ttu-id="f42fb-195">Állítsa be a **Feldolgozási idő nyomon követése** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="f42fb-195">Set the **Track processing time** option to **Yes**.</span></span>
1. <span data-ttu-id="f42fb-196">Adjon meg egy számot a **Szálak száma** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f42fb-196">In the **Number of threads** field, enter a number.</span></span>
1. <span data-ttu-id="f42fb-197">**A szerepeltetni kívánt rekordok** gyorslapján válassza a **szűrő** elemet.</span><span class="sxs-lookup"><span data-stu-id="f42fb-197">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="f42fb-198">A rácsban válassza ki azt a sort, amelyben a **Mező** mezője a **Cikkszám** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="f42fb-198">In the grid, select the row where the **Field** field is set to **Item number**.</span></span>
1. <span data-ttu-id="f42fb-199">A **Feltétel** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f42fb-199">In the **Criteria** field, enter a value.</span></span>
1. <span data-ttu-id="f42fb-200">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f42fb-200">Select **OK**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]