---
title: Cikkárak tárhelyének összehasonlítása jelentés
description: Útmutató a Cikkárak tárhelyének összehasonlítása jelentés létrehozásához, majd az eredmény böngészéséhez és/vagy exportálásához.
author: AndersGirke
manager: tfehr
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 6c8c72a631d361d7dffb8d18e00636e51e7998d3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201939"
---
# <a name="compare-item-prices-storage-report"></a><span data-ttu-id="5afdc-103">Cikkárak tárhelyének összehasonlítása jelentés</span><span class="sxs-lookup"><span data-stu-id="5afdc-103">Compare item prices storage report</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5afdc-104">Ez a témakör mutatja be a **Cikkárak tárhelyének összehasonlítása** jelentés futtatását, és a kimenet digitális elérhetővé tételét, vagy interaktív oldalként a Dynamics 365 Supply Chain Management szolgáltatásban, vagy exportált dokumentumként számos formátum egyikében.</span><span class="sxs-lookup"><span data-stu-id="5afdc-104">This topic explains how to run a **Compare item prices storage** report and make the output available digitally, either as an interactive page in Dynamics 365 Supply Chain Management, or as an exported document in any of several formats.</span></span>

<span data-ttu-id="5afdc-105">Ha a jelentést a böngészőben tekinti meg, az oszlopok és az összesítő egyenlegek dinamikusan módosulnak, attól függően, hogy milyen elrendezés van beállítva.</span><span class="sxs-lookup"><span data-stu-id="5afdc-105">When you view the report in your browser, columns and aggregate balances are dynamically adjusted, depending on your configured layout.</span></span> <span data-ttu-id="5afdc-106">Lehetőség van az eredmények rendezésére, szűrésére, az adatok leásására és további részletekre.</span><span class="sxs-lookup"><span data-stu-id="5afdc-106">You can sort the results, filter them, drill down into the data, and more.</span></span>

<span data-ttu-id="5afdc-107">A jelentés eredményeit a rendszer a **Cikkárak összehasonlítása** adatentitásban tárolja, amelyet szűrhet és exportálhatja az eredményeket CSV vagy Microsoft Excel-formátumban.</span><span class="sxs-lookup"><span data-stu-id="5afdc-107">Report results are stored in the **Compare item prices** data entity, which lets you filter and export the results to a format such as CSV or Microsoft Excel.</span></span>

<span data-ttu-id="5afdc-108">A **Cikkárak tárhelyének összehasonlítása** jelentése olyan esetekben hasznos, amikor a kimenet sok sort tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="5afdc-108">The **Compare item prices storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="5afdc-109">Például a kimenet számos sort tartalmaz, ha több mint 40 000 cikk van, amelynek cikkára függőben van a költségszámítási verzióban.</span><span class="sxs-lookup"><span data-stu-id="5afdc-109">For example, the output will contain many lines if you have more than 40,000 items holding a pending item price in the costing version.</span></span>

## <a name="enable-compare-item-prices-storage"></a><span data-ttu-id="5afdc-110">Cikkárak tárhelyének összehasonlításának engedélyezése</span><span class="sxs-lookup"><span data-stu-id="5afdc-110">Enable compare item prices storage</span></span>

<span data-ttu-id="5afdc-111">A funkció használata előtt engedélyeznie kell azt saját rendszerében.</span><span class="sxs-lookup"><span data-stu-id="5afdc-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="5afdc-112">A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="5afdc-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="5afdc-113">Itt a funkció a következőként szerepel:</span><span class="sxs-lookup"><span data-stu-id="5afdc-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="5afdc-114">**Modul** – Költségkezelés</span><span class="sxs-lookup"><span data-stu-id="5afdc-114">**Module** - Cost management</span></span>
- <span data-ttu-id="5afdc-115">**Funkció neve** – Cikkárak tárhelyének összehasonlítása</span><span class="sxs-lookup"><span data-stu-id="5afdc-115">**Feature name** - Compare item price storage</span></span>

## <a name="generate-a-compare-item-prices-storage-report"></a><span data-ttu-id="5afdc-116">Cikkárak tárhelyének összehasonlítása jelentés létrehozása</span><span class="sxs-lookup"><span data-stu-id="5afdc-116">Generate a Compare item prices storage report</span></span>

<span data-ttu-id="5afdc-117">A következő lépéseket követve létrehozhatja és tárolhatja a **Cikkárak tárhelyének összehasonlítása** jelentést:</span><span class="sxs-lookup"><span data-stu-id="5afdc-117">Follow these steps to generate and store a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="5afdc-118">Lépjen a **Költségkezelés > Lekérdezések és jelentések > Előre megadott költségjelentések > Cikkárak tárhelyének összehasonlítása** pontra.</span><span class="sxs-lookup"><span data-stu-id="5afdc-118">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="5afdc-119">Válassza az **Új** parancsot a **cikkek árának összehasonlítása** panel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5afdc-119">Select **New** to open the **Compare item prices** pane.</span></span> <span data-ttu-id="5afdc-120">A következő beállítások megadásával meghatározhatja, hogy mely árakat kell összehasonlítani a jelentésben:</span><span class="sxs-lookup"><span data-stu-id="5afdc-120">Set the following options to define which prices to compare in your report:</span></span>

    - <span data-ttu-id="5afdc-121">A **Paraméterek** gyorslapon adjon meg egy egyedi **nevet** a jelentésnek, és használja a **Összehasonlítandó függő árak** és az **Összehasonlításban használt árak** szakaszok mezőit, és határozza meg, hogy mely árak és dátumok összehasonlíthatók.</span><span class="sxs-lookup"><span data-stu-id="5afdc-121">On the **Parameters** FastTab, give the report a unique **Name** and use the fields in the **Pending prices to compare** and **Prices used for comparison** sections to define which prices and dates to compare.</span></span>
    - <span data-ttu-id="5afdc-122">A **szerepeltetni kívánt rekordok** gyorslapján állítson be szűrőket és korlátokat a jelentésben szerepeltetni kívánt adatok meghatározásához.</span><span class="sxs-lookup"><span data-stu-id="5afdc-122">On the **Records to include** FastTab, set up filters and constraints to define which data to include in the report.</span></span>
    - <span data-ttu-id="5afdc-123">A **Futtatás a háttérben** gyorslapon állítsa be a jelentés létrehozásának módját, idejét és gyakoriságát.</span><span class="sxs-lookup"><span data-stu-id="5afdc-123">On the **Run in the background** FastTab, set up how, when, and the frequency at which you want to generate the report.</span></span>
    > [!NOTE]
    > <span data-ttu-id="5afdc-124">Ez a jelentés mindig a kötegelt feladat részeként hajtható végre.</span><span class="sxs-lookup"><span data-stu-id="5afdc-124">This report is always executed as part of a batch job.</span></span>

1. <span data-ttu-id="5afdc-125">Az **ok** gombra kattintva alkalmazza a beállításokat, és zárja be az ablakot.</span><span class="sxs-lookup"><span data-stu-id="5afdc-125">Select **OK** to apply your settings and close the pane.</span></span>

1. <span data-ttu-id="5afdc-126">A kötegelt feladat befejezése után megjelenik a **Cikkárak tárhelyének összehasonlítása** oldal listájában.</span><span class="sxs-lookup"><span data-stu-id="5afdc-126">After the batch job is completed, it will be listed on the **Compare item prices storage** page.</span></span> <span data-ttu-id="5afdc-127">A jelentés megtekintéséhez előfordulhat, hogy frissítenie kell a lapot.</span><span class="sxs-lookup"><span data-stu-id="5afdc-127">You may need to refresh the page to see the report.</span></span>

## <a name="explore-the-compare-item-prices-storage-report"></a><span data-ttu-id="5afdc-128">Cikkárak összehasonlítása tárolási jelentés megismerése</span><span class="sxs-lookup"><span data-stu-id="5afdc-128">Explore the Compare item prices storage report</span></span>

<span data-ttu-id="5afdc-129">Miután létrehozta a jelentést, a következők szerint bármikor megtekintheti és kivizsgálhatja:</span><span class="sxs-lookup"><span data-stu-id="5afdc-129">After you've generated a report, you can view and explore it at any time as follows:</span></span>

1. <span data-ttu-id="5afdc-130">Lépjen a **Költségkezelés > Lekérdezések és jelentések > Előre megadott költségjelentések > Cikkárak tárhelyének összehasonlítása** pontra.</span><span class="sxs-lookup"><span data-stu-id="5afdc-130">Go to **Cost management > Inquiries and reports > Predetermined cost reports > Compare item prices storage**.</span></span>

1. <span data-ttu-id="5afdc-131">Válasszon ki egy jelentést a listából.</span><span class="sxs-lookup"><span data-stu-id="5afdc-131">Select a report from the list.</span></span>

1. <span data-ttu-id="5afdc-132">Válasszon az alábbi lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="5afdc-132">Do one of the following:</span></span>

    - <span data-ttu-id="5afdc-133">Ha áttekintést szeretne kapni a jelentés eredményeiről, válassza az **áttekintés** elemet.</span><span class="sxs-lookup"><span data-stu-id="5afdc-133">Select **Overview** to get an overview of your report results.</span></span>
    - <span data-ttu-id="5afdc-134">Válassza a **Részletek megtekintése** elemet a jelentés részletesebb nézetéhez.</span><span class="sxs-lookup"><span data-stu-id="5afdc-134">Select **View details** to get a more detailed view of your report</span></span>

1. <span data-ttu-id="5afdc-135">A kijelölt nézet megnyitása után a következőket teheti:</span><span class="sxs-lookup"><span data-stu-id="5afdc-135">After the selected view opens, you can do the following:</span></span>

    - <span data-ttu-id="5afdc-136">Válassza ki majdnem bármely oszlop fejlécét úgy, hogy az adott oszlopban szereplő értékek alapján rendezze vagy szűrje a táblát, ugyanúgy, mint az Supply Chain Management legtöbb szabványos képernyőjén.</span><span class="sxs-lookup"><span data-stu-id="5afdc-136">Select almost any column heading to sort or filter the table by values in that column, just as with most standard forms in Supply Chain Management.</span></span> <span data-ttu-id="5afdc-137">Ne feledje, hogy a **nettó módosítási ár %** oszlopot nem lehet rendezni vagy szűrni, mert egy számított mező.</span><span class="sxs-lookup"><span data-stu-id="5afdc-137">Note, you can't sort or filter the **Net change price %** column because it's a calculated field.</span></span>
    - <span data-ttu-id="5afdc-138">A **dimenziók megjelenítésének** kiválasztásával megnyithatja azt a képernyőt, ahol megadhatja, hogy mely dimenzió oszlop szerepeljen a képernyőn.</span><span class="sxs-lookup"><span data-stu-id="5afdc-138">Select **Dimension display** to open a pane where you can choose which dimension column to include on the form.</span></span> <span data-ttu-id="5afdc-139">Ha menteni szeretné ezeket a beállításokat, állítsa **Igen** értékre a **Mentés beállítását**, hogy a rendszer a jelentés következő megnyitásakor megőrződik.</span><span class="sxs-lookup"><span data-stu-id="5afdc-139">Set **Save setup** to **Yes** if you'd like to save these settings so they will be preserved the next time you open the report.</span></span> <span data-ttu-id="5afdc-140">Az **ok** gombra kattintva alkalmazza a beállításokat, és zárja be.</span><span class="sxs-lookup"><span data-stu-id="5afdc-140">Select **OK** to apply your settings and close.</span></span>
    - <span data-ttu-id="5afdc-141">Jelöljön ki egy sort a képernyőn, majd válassza a **Részletek megtekintése** parancsot a kiválasztott cikk további adatainak megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="5afdc-141">Select any row in the form and then select **View details** to see more information about the selected item.</span></span> <span data-ttu-id="5afdc-142">Innen leáshat az adatokba.</span><span class="sxs-lookup"><span data-stu-id="5afdc-142">You'll be able to drill down into the data from here.</span></span>
    - <span data-ttu-id="5afdc-143">Jelöljön ki egy sort a képernyőn, majd válassza az **Összehasonlítási diagram megtekintése** lehetőséget, ha a kiválasztott cikkhez kapcsolódóan az eredmények interaktív grafikus ábrázolását szeretné látni.</span><span class="sxs-lookup"><span data-stu-id="5afdc-143">Select any row in the form and then select **View comparison chart** to see an interactive graphical representation of your results as they relate to your selected item.</span></span> <span data-ttu-id="5afdc-144">Ezek az eredmények a diagramok és diagramok jelmagyarázatának különböző grafikus elemeinek kiválasztásával tekinthetők meg.</span><span class="sxs-lookup"><span data-stu-id="5afdc-144">You can explore these results by selecting various graphical elements in the chart and chart legend.</span></span>
    - <span data-ttu-id="5afdc-145">Jelöljön ki egy sort a képernyőn, majd válassza a **Számítási részletek megtekintése** parancsot a kiválasztott cikkhez kapcsolódó számítások megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="5afdc-145">Select any row in the form and then select **View calculation details** to see more information about calculations related to the selected item.</span></span> <span data-ttu-id="5afdc-146">Innen leáshat az adatokba.</span><span class="sxs-lookup"><span data-stu-id="5afdc-146">You'll be able to drill down into the data from here.</span></span>

## <a name="export-the-compare-item-prices-storage-report"></a><span data-ttu-id="5afdc-147">Cikkárak összehasonlítása tárolási jelentés exportálása</span><span class="sxs-lookup"><span data-stu-id="5afdc-147">Export the Compare item prices storage report</span></span>

<span data-ttu-id="5afdc-148">A rendszer minden létrehozott jelentést a **Cikkárak összehasonlítása** adatentitásban tárol.</span><span class="sxs-lookup"><span data-stu-id="5afdc-148">Each report that you generate is stored in the **Compare item prices** data entity.</span></span> <span data-ttu-id="5afdc-149">A Supply Chain Management szabványos adatkezelési funkcióival exportálhat adatokat ebből az entitásból bármely támogatott adatformátumba, például CSV- vagy Microsoft Excel-formátumba.</span><span class="sxs-lookup"><span data-stu-id="5afdc-149">You can use the standard data management features of Supply Chain Management to export data from this entity to any supported data format, including CSV or Microsoft Excel.</span></span>

<span data-ttu-id="5afdc-150">A következő példa bemutatja, hogyan lehet exportálni egy **Cikkárak tárhelyének összehasonlítása** jelentést:</span><span class="sxs-lookup"><span data-stu-id="5afdc-150">The following is an example of how to export a **Compare item prices storage** report:</span></span>

1. <span data-ttu-id="5afdc-151">Lépjen a **Rendszerfelügyelet > Munkaterületek > Adatkezelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="5afdc-151">Go to **System administration > Workspaces > Data management**.</span></span>

1. <span data-ttu-id="5afdc-152">Válassza az **exportálás** gombot az **Adatkezelés** részben.</span><span class="sxs-lookup"><span data-stu-id="5afdc-152">Select the **Export** button in the **Data management** section.</span></span>

1. <span data-ttu-id="5afdc-153">Megjelenik az **Exportálás** lap, amelyen beállíthatja az exportálási feladatot.</span><span class="sxs-lookup"><span data-stu-id="5afdc-153">The **Export** page opens, which you'll use to set up your export job.</span></span> <span data-ttu-id="5afdc-154">A kezdő művelet a **csoport nevének**megadása.</span><span class="sxs-lookup"><span data-stu-id="5afdc-154">Start by giving your job a **Group name**.</span></span>

1. <span data-ttu-id="5afdc-155">A **Kiválasztott entitások** szakaszban válassza az **Entitás hozzáadása** lehetőséget a párbeszédpanel megnyitásához, amelyen beállíthatja a következő beállításokat:</span><span class="sxs-lookup"><span data-stu-id="5afdc-155">In the **Selected entities** section, select **Add entity** to open a dialog box where you can set the following options:</span></span>

    - <span data-ttu-id="5afdc-156">**Entitás neve** – Válassza a **Cikkárak összehasonlítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5afdc-156">**Entity name** - Select **Compare item prices**.</span></span>
    - <span data-ttu-id="5afdc-157">**Cél-adatformátum** – válassza ki az exportáláshoz használni kívánt formátumot.</span><span class="sxs-lookup"><span data-stu-id="5afdc-157">**Target data format** - Choose the format that you want to export to.</span></span>

1. <span data-ttu-id="5afdc-158">A **Hozzáadás** gomb kiválasztásával új sort adhat hozzá, majd a **Bezárás** paranccsal bezárhatja a párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="5afdc-158">Select **Add** to add the new row and then select **Close** to close the dialog box.</span></span>

1. <span data-ttu-id="5afdc-159">Általában egyszerre csak egy jelentést exportál.</span><span class="sxs-lookup"><span data-stu-id="5afdc-159">Usually you'll export one report at a time.</span></span> <span data-ttu-id="5afdc-160">Ehhez be kell állítania egy **Szűrőt** a **Lekérdezés** ablaktáblához hozzáadott sorhoz.</span><span class="sxs-lookup"><span data-stu-id="5afdc-160">To do this, set up a **Filter** for the row you just added to the **Inquiry** pane.</span></span> <span data-ttu-id="5afdc-161">Ezzel megadhatja, hogy mely jelentések szerepeljenek az exportban szerepeltetni kívánt **Cikkárak összehasonlítása** entitásban.</span><span class="sxs-lookup"><span data-stu-id="5afdc-161">This will let you define which reports from the **Compare item prices** entity that you want to include in your export.</span></span> <span data-ttu-id="5afdc-162">Egyetlen jelentés exportálásához adja meg a következő szűrőbeállításokat:</span><span class="sxs-lookup"><span data-stu-id="5afdc-162">Set the following filter options to export a single report:</span></span>

    - <span data-ttu-id="5afdc-163">A **tartomány** lapon válassza a **Hozzáadás** lehetőséget új sor hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="5afdc-163">On the **Range** tab, select **Add** to add a new row.</span></span>
    - <span data-ttu-id="5afdc-164">A **Tábla** beállítást állítsa **Cikkárak összehasonlítása** értékre.</span><span class="sxs-lookup"><span data-stu-id="5afdc-164">Set **Table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="5afdc-165">A **Származtatott tábla** beállítást állítsa **Cikkárak összehasonlítása** értékre.</span><span class="sxs-lookup"><span data-stu-id="5afdc-165">Set **Derived table** to **Compare item prices**.</span></span>
    - <span data-ttu-id="5afdc-166">Állítsa a **Mező** értékét a szűréshez használt mezőre.</span><span class="sxs-lookup"><span data-stu-id="5afdc-166">Set **Field** to the field that you want to filter by.</span></span> <span data-ttu-id="5afdc-167">Általában a **Végrehajtási nevet** vagy a **Végrehajtási időt** fogja használni.</span><span class="sxs-lookup"><span data-stu-id="5afdc-167">Usually you'll use **Execution name** or **Execution time**.</span></span>
    - <span data-ttu-id="5afdc-168">Állítsa a **Feltétel** értékét a megfigyelni kívánt értékre a kiválasztott mezőből (vagy a jelentés neve, vagy a jelentés létrehozási ideje).</span><span class="sxs-lookup"><span data-stu-id="5afdc-168">Set **Criteria** to the value from your selected field that you want to look for (either the name of the report or the time the report was generated).</span></span>
    - <span data-ttu-id="5afdc-169">Ha szükséges, vegyen fel több sort a **Tartomány** táblába addig, amíg nem egyedileg azonosította a keresett jelentést.</span><span class="sxs-lookup"><span data-stu-id="5afdc-169">If necessary, add more rows to the **Range** table until you have uniquely identified the report that you're looking for.</span></span>

1. <span data-ttu-id="5afdc-170">Az **ok** gombra kattintva mentse a beállításokat, és zárja be.</span><span class="sxs-lookup"><span data-stu-id="5afdc-170">Select **OK** to save your settings and close.</span></span>

1. <span data-ttu-id="5afdc-171">Az exportálási beállítások mentéséhez válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="5afdc-171">Select **Save** to save your export setup.</span></span>

1. <span data-ttu-id="5afdc-172">Nyissa meg az **Exportálási beállítások** lapot, és válassza az **Exportálás most** lehetőséget az exportfájl létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="5afdc-172">Open the **Export options** tab and select **Export now** to generate the export file.</span></span>

1. <span data-ttu-id="5afdc-173">Megjelenik a **Végrehajtási összesítés** lap, amelyen megtekintheti az exportálási feladat állapotát, valamint az exportált entitások listáját.</span><span class="sxs-lookup"><span data-stu-id="5afdc-173">The **Execution summary** page opens, where you can see the status of your export job and a list of entities that were exported.</span></span> <span data-ttu-id="5afdc-174">Válassza a **Cikkárak összehasonlítása** entitást az **Entitás feldolgozási állapota** terület listájából, majd válassza a **Fájl letöltése** elemet az adott entitásból exportált adatok letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="5afdc-174">Select the **Compare item prices** entity listed in the **Entity processing status** area and then select **Download file** to download the data exported from that entity.</span></span>

<span data-ttu-id="5afdc-175">Ha további tájékoztatást szeretne arról, hogyan lehet az adatkezelést az adatok exportálására használni, akkor lásd: [Adatimportálási és-exportálási feladatok – áttekintés](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="5afdc-175">For more information about how to use data management to export data, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>
