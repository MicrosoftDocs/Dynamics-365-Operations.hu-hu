---
title: Jelentés-összetevők rendezése a jelentéstervezőben
description: Miután elkészítette az építőelemeket és létrehozta a jelentéseket, hasznos ezeknek a rendezése, hogy a felhasználók könnyebben megtalálják őket. Ez a cikk ismerteti a jelentéstervezőben meglévő jelentések, építőelemek és objektumok rendezését.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4a4733dc4da7a8713ac7ddec5c96ae18c91edc18
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185290"
---
# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="3f03d-104">Jelentés-összetevők rendezése a jelentéstervezőben</span><span class="sxs-lookup"><span data-stu-id="3f03d-104">Organize report components in report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3f03d-105">Miután elkészítette az építőelemeket és létrehozta a jelentéseket, hasznos ezeknek a rendezése, hogy a felhasználók könnyebben megtalálják őket.</span><span class="sxs-lookup"><span data-stu-id="3f03d-105">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="3f03d-106">Ez a cikk ismerteti a jelentéstervezőben meglévő jelentések, építőelemek és objektumok rendezését.</span><span class="sxs-lookup"><span data-stu-id="3f03d-106">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="3f03d-107">Átnevezheti a mappákat, jelentéseket, építőelemeket és más objektumokat jelentéstervezőben a fájlok rendszerezése érdekében.</span><span class="sxs-lookup"><span data-stu-id="3f03d-107">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="3f03d-108">Attól függően, hogy milyen típusú objektumot nevez át, előfordulhat, hogy frissítenie kell az objektummal kapcsolatos társításokat.</span><span class="sxs-lookup"><span data-stu-id="3f03d-108">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="3f03d-109">Nevezze át a mappát vagy az építőelemet a Jelentés Tervezőben</span><span class="sxs-lookup"><span data-stu-id="3f03d-109">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="3f03d-110">A Report Designer eszközben átnevezheti a mappákat, valamint a jelentés-, sor-, oszlop- és jelentésfa-definíciókat is.</span><span class="sxs-lookup"><span data-stu-id="3f03d-110">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="3f03d-111">Mappa vagy építőelem átnevezése a Report Designer eszközben</span><span class="sxs-lookup"><span data-stu-id="3f03d-111">Rename a folder or building block in Report Designer</span></span>

1. <span data-ttu-id="3f03d-112">A Report Designer alkalmazás navigációs ablaktábláján keresse meg az átnevezni kívánt mappát vagy objektumot.</span><span class="sxs-lookup"><span data-stu-id="3f03d-112">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2. <span data-ttu-id="3f03d-113">Kattintson jobb gombbal a mappára vagy az objektumra, és kattintson a **Átnevezésre**.</span><span class="sxs-lookup"><span data-stu-id="3f03d-113">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="3f03d-114">A navigációs ablakban lévő **Név** mező elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="3f03d-114">The **Name** field in the navigation pane becomes available.</span></span>
3. <span data-ttu-id="3f03d-115">Írja be az új nevet, majd nyomja le az Entert.</span><span class="sxs-lookup"><span data-stu-id="3f03d-115">Type a new name, and then press Enter.</span></span>
4. <span data-ttu-id="3f03d-116">Ha az építőelem egy sordefiníció, oszlopdefiníció vagy jelentési fa definíció, akkor frissítenie kell a többi építőelemet, amelyek társítva vannak hozzá.</span><span class="sxs-lookup"><span data-stu-id="3f03d-116">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="3f03d-117">Kattintson jobb gombbal arra az építőelemre, amelyet a 3. lépésben átnevezett, válassza ki a **Társítások** lehetőséget, majd válasszon ki egy cikket a listában, hogy frissítse.</span><span class="sxs-lookup"><span data-stu-id="3f03d-117">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5. <span data-ttu-id="3f03d-118">Ismételje meg a 4. lépést addig, amíg be nem fejeződik az összes kapcsolódó elem frissítése.</span><span class="sxs-lookup"><span data-stu-id="3f03d-118">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="3f03d-119">Jelentés csoportok létrehozása és kezelése</span><span class="sxs-lookup"><span data-stu-id="3f03d-119">Create and manage report groups</span></span>
<span data-ttu-id="3f03d-120">Ezzel egy időben a jelentésdefiníciókat csoportosíthatja több jelentés készítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="3f03d-120">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="3f03d-121">Jelentéscsoportok létrehozásához, módosításához, törléséhez és készítéséhez tervező vagy rendszergazda szerepkörrel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="3f03d-121">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="3f03d-122">A jelentéskészítő szerepkörrel rendelkező felhasználók létrehozhatnak jelentéscsoportokat, és módosíthatják a felhasználók jelentéscsoportokhoz tartozó jelentésdefinícióinak beállítását.</span><span class="sxs-lookup"><span data-stu-id="3f03d-122">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="3f03d-123">Jelentés csoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="3f03d-123">Create a report group</span></span>

1. <span data-ttu-id="3f03d-124">A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f03d-124">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="3f03d-125">A **Fájl** menüben kattintson az **Új** &gt; **Jelentéscsoport-definíció** lehetőségre, hogy megnyisson egy új jelentéscsoportot a megjelenítő ablakban.</span><span class="sxs-lookup"><span data-stu-id="3f03d-125">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="3f03d-126">Másik lehetőségként kattintson a **Jelentéscsoport** gombra ![Jelentéscsoport](media/report-group.gif "Jelentéscsoport") az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="3f03d-126">Alternatively, click the **Report Group** button ![Report Group](media/report-group.gif "Report Group") on the toolbar.</span></span>
3. <span data-ttu-id="3f03d-127">Kattintson a **Jelentéscsoport** lapra. Ha felül szeretné bírálni ennek a jelentés létrehozásának egyes jelentésdefinícióban lévő információkat, jelölje be a **Az egyes jelentésdefiníciókból a vállalat, adat és dátumbeállítások felülbírálása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="3f03d-127">Click the **Report Group** tab. To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="3f03d-128">A vállalat nevét, a részletezési szintet, az ideiglenes beállítást és dátum információkat automatikusan feltölti a rendszer, de végezhet rajtuk frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="3f03d-128">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4. <span data-ttu-id="3f03d-129">Több jelentés létrehozásához, amelyek megmutatják a jelentési pénznemeket válassza ki a **Minden jelentési pénznem szerepeltetése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="3f03d-129">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="3f03d-130">Ezután több nézethez férhet hozzá, ha a **Pénznem** gombra kattint a böngészőben, a jelentés megtekintésekkor.</span><span class="sxs-lookup"><span data-stu-id="3f03d-130">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5. <span data-ttu-id="3f03d-131">A **Jelentések a csoportban** mezőben, kattintson a **Hozzáadás** gombra a jelentéscsoportba felvenni kívánt jelentések kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="3f03d-131">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="3f03d-132">Több jelentés kijelöléséhez a **Hozzáadás** párbeszédablakban, tartsa lenyomva a Ctrl billentyűt, miközben kiválasztja az elemeket.</span><span class="sxs-lookup"><span data-stu-id="3f03d-132">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="3f03d-133">Befejezése után jelölje ki a jelentéseket, és kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="3f03d-133">When you've finished selecting reports, click **OK**.</span></span>
6. <span data-ttu-id="3f03d-134">Kattintson a **Fájl** &gt; **Mentés** elemre az új jelentéscsoport mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="3f03d-134">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="3f03d-135">Jelentéscsoport módosítása</span><span class="sxs-lookup"><span data-stu-id="3f03d-135">Modify a report group</span></span>

1. <span data-ttu-id="3f03d-136">A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f03d-136">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="3f03d-137">Kattintson duplán a módosítani kívánt jelentéscsoportra.</span><span class="sxs-lookup"><span data-stu-id="3f03d-137">Double-click the report group to modify.</span></span>
3. <span data-ttu-id="3f03d-138">A **Jelentéscsoport** lapon, végezze el a kívánt módosításokat.</span><span class="sxs-lookup"><span data-stu-id="3f03d-138">On the **Report Group** tab, make the changes that you want.</span></span>
4. <span data-ttu-id="3f03d-139">A **Fájl** menüben kattintson a **Mentés** lehetőségre a módosított jelentéscsoport mentéséhez, vagy kattintson a **Mentés** gombra ![Mentés](media/save.gif "Mentés") az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="3f03d-139">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](media/save.gif "Save") on the toolbar.</span></span>

> <span data-ttu-id="3f03d-140">[MEGJEGYZÉS] Ha meghatározott időközönként létrehozott jelentéseket ütemezett, felülírhatja ezeket a beállításokat, és azonnal jelentéseket készíthet.</span><span class="sxs-lookup"><span data-stu-id="3f03d-140">[NOTE] If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="3f03d-141">Jelentéscsoportról szóló jelentés készítése</span><span class="sxs-lookup"><span data-stu-id="3f03d-141">Generate a report group report</span></span>

1. <span data-ttu-id="3f03d-142">A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f03d-142">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="3f03d-143">Nyissa meg a jelentéscsoportot a jelentés készítéséhez.</span><span class="sxs-lookup"><span data-stu-id="3f03d-143">Open the report group to generate.</span></span>
3. <span data-ttu-id="3f03d-144">Kattintson a **Jelentés készítése** gombra ![Jelentés készítése](media/generate-report.gif "Jelentés készítése") jelentések készítéséhez.</span><span class="sxs-lookup"><span data-stu-id="3f03d-144">Click the **Generate Report** button ![Generate Report](media/generate-report.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="3f03d-145">Jelentéscsoport törlése</span><span class="sxs-lookup"><span data-stu-id="3f03d-145">Delete a report group</span></span>

1. <span data-ttu-id="3f03d-146">A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3f03d-146">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2. <span data-ttu-id="3f03d-147">A törléshez kattintson jobb gombbal a jelentés csoportra, és válassza **Törlés**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3f03d-147">Right-click the report group to delete, and then select **Delete**.</span></span>
3. <span data-ttu-id="3f03d-148">Ha egy megerősítő üzenet jelenik meg, kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="3f03d-148">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="3f03d-149">Jelentéscsoport-lap vezérlők</span><span class="sxs-lookup"><span data-stu-id="3f03d-149">Report Group tab controls</span></span>
<span data-ttu-id="3f03d-150">Az alábbi táblázat ismerteti a **Jelentéscsoport** lap vezérlőit.</span><span class="sxs-lookup"><span data-stu-id="3f03d-150">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="3f03d-151">Vezérlő</span><span class="sxs-lookup"><span data-stu-id="3f03d-151">Control</span></span></th>
<th><span data-ttu-id="3f03d-152">Leírás</span><span class="sxs-lookup"><span data-stu-id="3f03d-152">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="3f03d-153">Az egyes jelentésdefiníciókból a vállalat-, adat- és dátumbeállítások felülbírálása</span><span class="sxs-lookup"><span data-stu-id="3f03d-153">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="3f03d-154">Jelölje be ezt a jelölőnégyzetet, ha felül szeretné bírálni a jelentések egyéni jelentésdefinícióit a csak ezeknek a jelentéseknek az előállítására szolgáló jelentéscsoportban.</span><span class="sxs-lookup"><span data-stu-id="3f03d-154">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3f03d-155">Vállalat neve</span><span class="sxs-lookup"><span data-stu-id="3f03d-155">Company name</span></span></td>
<td><span data-ttu-id="3f03d-156">A jelentésekhez használt vállalat kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="3f03d-156">Select the company to use for the reports.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3f03d-157">Részletezési szint</span><span class="sxs-lookup"><span data-stu-id="3f03d-157">Detail level</span></span></td>
<td><span data-ttu-id="3f03d-158">Adja meg, hogy milyen részletes jelentést szeretne készíteni.</span><span class="sxs-lookup"><span data-stu-id="3f03d-158">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="3f03d-159"><strong>Pénzügyi</strong> − Átfogó összefoglaló jelentés.</span><span class="sxs-lookup"><span data-stu-id="3f03d-159"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="3f03d-160">Nem lehet számlákra és dimenziókra lebontani, kivéve az olyan számláknál és dimenzióknál, amelyeket a jelentési fán keresztül adtak hozzá.</span><span class="sxs-lookup"><span data-stu-id="3f03d-160">You can&#39;t drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="3f03d-161"><strong>Pénzügy és Számla</strong> – Egy jelentés, amely átfogó összegzést és részletes számlaadatokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="3f03d-161"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="3f03d-162"><strong>Pénzügy, Számla és Tranzakció</strong> – Egy jelentés, amely átfogó összegzést és a tranzakció részletes adatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="3f03d-162"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="3f03d-163">Fedezetek</span><span class="sxs-lookup"><span data-stu-id="3f03d-163">Provisional</span></span></td>
<td><span data-ttu-id="3f03d-164">Adja meg, hogy milyen típusú tevékenységeket tartalmazzon a jelentés.</span><span class="sxs-lookup"><span data-stu-id="3f03d-164">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="3f03d-165"><strong>Csak feladott tevékenység</strong> − Csak a pénzügyi adatokba feladott tranzakciókat és egyenlegeket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="3f03d-165"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="3f03d-166"><strong>Feladott és fel nem adott tevékenység</strong> − A pénzügyi adatokba felvett és feladott összes tranzakciót és egyenleget tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="3f03d-166"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="3f03d-167"><strong>Csak feladatlan tevékenység</strong> − Csak a pénzügyi adatokba felvett, de még fel nem adott tranzakciókat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="3f03d-167"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="3f03d-168">Minden jelentési pénznemmel együtt</span><span class="sxs-lookup"><span data-stu-id="3f03d-168">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="3f03d-169">Bármely további jelentési pénznem, amely be van állítva a Microsoft Dynamics ERP rendszeréhez itt kerül felsorolásra.</span><span class="sxs-lookup"><span data-stu-id="3f03d-169">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="3f03d-170">Jelölje ki ezt a jelölőnégyzetet, hogy további jelentéseket hozzon létre a jelölt pénznemekkel.</span><span class="sxs-lookup"><span data-stu-id="3f03d-170">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="3f03d-171">Ezen jelentések megtekinthetők a Web Viewer eszközben, ha a <strong>Pénznem</strong> gombra kattint és kiválaszt egy pénznemet.</span><span class="sxs-lookup"><span data-stu-id="3f03d-171">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3f03d-172">A dátummal kapcsolatos adatok mentése nem történik meg a jelentésdefiníciójával</span><span class="sxs-lookup"><span data-stu-id="3f03d-172">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="3f03d-173">Bázisidőszak</span><span class="sxs-lookup"><span data-stu-id="3f03d-173">Base period</span></span></li>
<li><span data-ttu-id="3f03d-174">Bázisév</span><span class="sxs-lookup"><span data-stu-id="3f03d-174">Base year</span></span></li>
<li><span data-ttu-id="3f03d-175">Érintett időszakok</span><span class="sxs-lookup"><span data-stu-id="3f03d-175">Period covered</span></span></li>
</ul>
<span data-ttu-id="3f03d-176">Csak az alapértelmezett alapidőszak beállításainak mentése történik a jelentésdefinícióval.</span><span class="sxs-lookup"><span data-stu-id="3f03d-176">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="3f03d-177">A dátummal kapcsolatos adatok mentődnek a jelentésdefiníciójával</span><span class="sxs-lookup"><span data-stu-id="3f03d-177">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="3f03d-178">Jelentés dátuma</span><span class="sxs-lookup"><span data-stu-id="3f03d-178">Report date</span></span></li>
<li><span data-ttu-id="3f03d-179">Alapértelmezett alap időtartam</span><span class="sxs-lookup"><span data-stu-id="3f03d-179">Default base period</span></span></li>
</ul></td>
</tr>
<tr>
<td><span data-ttu-id="3f03d-180">Jelentések a csoportokban</span><span class="sxs-lookup"><span data-stu-id="3f03d-180">Reports in group</span></span></td>
<td><span data-ttu-id="3f03d-181">Jelentések hozzáadása, eltávolítása és újrarendezése jelentéscsoportban.</span><span class="sxs-lookup"><span data-stu-id="3f03d-181">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="3f03d-182">Ha jelentésdefiníciókat szeretne adni a jelentéscsoporthoz, dupla kattintással nyissa meg a csoportot, majd kattintson a <strong>Hozzáadás</strong> parancsra.</span><span class="sxs-lookup"><span data-stu-id="3f03d-182">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="3f03d-183">Jelölje ki a jelentéscsoportba felvenni kívánt jelentéseket, majd kattintson az <strong>OK</strong> gombra.</span><span class="sxs-lookup"><span data-stu-id="3f03d-183">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="3f03d-184">Ha szeretne eltávolítani egy jelentést a jelentéscsoportból, jelölje ki, majd kattintson az <strong>Eltávolítás</strong> parancsra.</span><span class="sxs-lookup"><span data-stu-id="3f03d-184">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="3f03d-185">A létrehozott jelentések sorrendjének módosításához válasszon ki a listából egy jelentést, majd kattintson <strong>Mozgatás felfelé</strong> vagy <strong>Mozgatás lefelé</strong> gombra.</span><span class="sxs-lookup"><span data-stu-id="3f03d-185">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="3f03d-186">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="3f03d-186">Additional resources</span></span>

[<span data-ttu-id="3f03d-187">Pénzügyi jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="3f03d-187">Financial reporting</span></span>](financial-reporting-intro.md)
