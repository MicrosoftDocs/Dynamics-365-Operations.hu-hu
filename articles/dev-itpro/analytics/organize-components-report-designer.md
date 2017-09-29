---
title: "Jelentés-összetevők rendezése a jelentéstervezőben"
description: "Miután elkészítette az építőelemeket és létrehozta a jelentéseket, hasznos ezeknek a rendezése, hogy a felhasználók könnyebben megtalálják őket. Ez a cikk ismerteti a jelentéstervezőben meglévő jelentések, építőelemek és objektumok rendezését."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Management Reporter, UnifiedOperations, Core
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: fade9e2acdb94daa6a908d949c578fd7ed439882
ms.contentlocale: hu-hu
ms.lasthandoff: 07/18/2017

---

# <a name="organize-report-components-in-report-designer"></a><span data-ttu-id="0f778-104">Jelentés-összetevők rendezése a jelentéstervezőben</span><span class="sxs-lookup"><span data-stu-id="0f778-104">Organize report components in report designer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0f778-105">Miután elkészítette az építőelemeket és létrehozta a jelentéseket, hasznos ezeknek a rendezése, hogy a felhasználók könnyebben megtalálják őket.</span><span class="sxs-lookup"><span data-stu-id="0f778-105">After you've designed building blocks and generated reports, it's helpful to organize these objects so that they are easier for users to locate.</span></span> <span data-ttu-id="0f778-106">Ez a cikk ismerteti a jelentéstervezőben meglévő jelentések, építőelemek és objektumok rendezését.</span><span class="sxs-lookup"><span data-stu-id="0f778-106">This article explains how to organize existing reports, building blocks, and objects in report designer.</span></span>

<span data-ttu-id="0f778-107">Átnevezheti a mappákat, jelentéseket, építőelemeket és más objektumokat jelentéstervezőben a fájlok rendszerezése érdekében.</span><span class="sxs-lookup"><span data-stu-id="0f778-107">You can rename folders, reports, building blocks, and other objects in report designer to help organize your files.</span></span> <span data-ttu-id="0f778-108">Attól függően, hogy milyen típusú objektumot nevez át, előfordulhat, hogy frissítenie kell az objektummal kapcsolatos társításokat.</span><span class="sxs-lookup"><span data-stu-id="0f778-108">Depending on the type of object that you rename, you might have to update associations with that object.</span></span>

## <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="0f778-109">Nevezze át a mappát vagy az építőelemet a Jelentés Tervezőben</span><span class="sxs-lookup"><span data-stu-id="0f778-109">Rename a folder or building block in Report Designer</span></span>
<span data-ttu-id="0f778-110">A Jelentés Tervezőben átnevezheti a mappákat, a jelentésdefinicókat, sor meghatározásokat, az oszlopdefiníciókat és a szervezeti diagram meghatározásokat.</span><span class="sxs-lookup"><span data-stu-id="0f778-110">In Report Designer, you can rename folders, report definitions, row definitions, column definitions, and reporting tree definitions.</span></span> <span data-ttu-id="0f778-111">**Megjegyzés:** Építőelem átnevezésekor frissítenie kell minden jelentési definíciót, amely azt az építőelemet használja.</span><span class="sxs-lookup"><span data-stu-id="0f778-111">**Note:** When you rename a building block, you must update any reporting definitions that use the building block.</span></span> <span data-ttu-id="0f778-112">Ellenkező esetben nem hozható létre új jelentés.</span><span class="sxs-lookup"><span data-stu-id="0f778-112">Otherwise, a new report can't be generated.</span></span>

### <a name="rename-a-folder-or-building-block-in-report-designer"></a><span data-ttu-id="0f778-113">Nevezze át a mappát vagy az építőelemet a Jelentés Tervezőben</span><span class="sxs-lookup"><span data-stu-id="0f778-113">Rename a folder or building block in Report Designer</span></span>

1.  <span data-ttu-id="0f778-114">A Jelentés Tervezőben használja a navigációs ablakot a mappa megkeresésére vagy az objektum átnevezésére.</span><span class="sxs-lookup"><span data-stu-id="0f778-114">In Report Designer, use the navigation pane to locate the folder or object to rename.</span></span>
2.  <span data-ttu-id="0f778-115">Kattintson jobb gombbal a mappára vagy az objektumra, és kattintson a **Átnevezésre**.</span><span class="sxs-lookup"><span data-stu-id="0f778-115">Right-click the folder or object, and then click **Rename**.</span></span> <span data-ttu-id="0f778-116">A navigációs ablakban lévő **Név** mező elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="0f778-116">The **Name** field in the navigation pane becomes available.</span></span>
3.  <span data-ttu-id="0f778-117">Írja be az új nevet, majd nyomja le az Entert.</span><span class="sxs-lookup"><span data-stu-id="0f778-117">Type a new name, and then press Enter.</span></span>
4.  <span data-ttu-id="0f778-118">Ha az építőelem egy sordefiníció, oszlopdefiníció vagy jelentési fa definíció, akkor frissítenie kell a többi építőelemet, amelyek társítva vannak hozzá.</span><span class="sxs-lookup"><span data-stu-id="0f778-118">If the building block is a row definition, column definition, or reporting tree definition, you must update other building blocks that are associated with it.</span></span> <span data-ttu-id="0f778-119">Kattintson jobb gombbal arra az építőelemre, amelyet a 3. lépésben átnevezett, válassza ki a **Társítások** lehetőséget, majd válasszon ki egy cikket a listában, hogy frissítse.</span><span class="sxs-lookup"><span data-stu-id="0f778-119">Right-click the building block that you renamed in step 3, select **Associations**, and then select an item in the list to update it.</span></span>
5.  <span data-ttu-id="0f778-120">Ismételje meg a 4. lépést addig, amíg be nem fejeződik az összes kapcsolódó elem frissítése.</span><span class="sxs-lookup"><span data-stu-id="0f778-120">Repeat step 4 until all associated items are updated.</span></span>

## <a name="create-and-manage-report-groups"></a><span data-ttu-id="0f778-121">Jelentés csoportok létrehozása és kezelése</span><span class="sxs-lookup"><span data-stu-id="0f778-121">Create and manage report groups</span></span>
<span data-ttu-id="0f778-122">Ezzel egy időben a jelentésdefiníciókat csoportosíthatja több jelentés készítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="0f778-122">You can group report definitions to generate multiple reports at the same time.</span></span> <span data-ttu-id="0f778-123">Jelentéscsoportok létrehozásához, módosításához, törléséhez és készítéséhez tervező vagy rendszergazda szerepkörrel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="0f778-123">To create, modify, delete, and generate report groups, you must have the designer or administrator role.</span></span> <span data-ttu-id="0f778-124">A jelentéskészítő szerepkörrel rendelkező felhasználók létrehozhatnak jelentéscsoportokat, és módosíthatják a felhasználók jelentéscsoportokhoz tartozó jelentésdefinícióinak beállítását.</span><span class="sxs-lookup"><span data-stu-id="0f778-124">Users who have the generator role can generate report groups and can also modify the user report definitions setting for report groups.</span></span>

### <a name="create-a-report-group"></a><span data-ttu-id="0f778-125">Jelentés csoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="0f778-125">Create a report group</span></span>

1.  <span data-ttu-id="0f778-126">A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0f778-126">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="0f778-127">A **Fájl** menüben kattintson az **Új** &gt; **Jelentéscsoport-definíció** lehetőségre, hogy megnyisson egy új jelentéscsoportot a megjelenítő ablakban.</span><span class="sxs-lookup"><span data-stu-id="0f778-127">On the **File** menu, click **New** &gt; **Report Group Definition** to open a new report group in the viewer window.</span></span> <span data-ttu-id="0f778-128">Másik lehetőségként kattintson a **Jelentéscsoport** gombra ![Jelentéscsoport](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Jelentéscsoport") az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="0f778-128">Alternatively, click the **Report Group** button ![Report Group](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "Report Group") on the toolbar.</span></span>
3.  <span data-ttu-id="0f778-129">Kattintson a **Jelentés Csoport** lapra.</span><span class="sxs-lookup"><span data-stu-id="0f778-129">Click the **Report Group** tab.</span></span> <span data-ttu-id="0f778-130">Ha felül szeretné bírálni ennek a jelentés létrehozásának egyes jelentésdefinícióban lévő információkat, jelölje be a **Az egyes jelentésdefiníciókból a vállalat, adat és dátumbeállítások felülbírálása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="0f778-130">To override the information on the individual report definitions for the generation of this report, select the **Override company, detail, and date settings from individual report definitions** check box.</span></span> <span data-ttu-id="0f778-131">A vállalat nevét, a részletezési szintet, az ideiglenes beállítást és dátum információkat automatikusan feltölti a rendszer, de végezhet rajtuk frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="0f778-131">The company name, detail level, provisional setting, and date information are entered automatically, but you can make updates.</span></span>
4.  <span data-ttu-id="0f778-132">Több jelentés létrehozásához, amelyek megmutatják a jelentési pénznemeket válassza ki a **Minden jelentési pénznem szerepeltetése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="0f778-132">To generate multiple reports that show the reporting currencies, select the **Include all reporting currencies** check box.</span></span> <span data-ttu-id="0f778-133">Ezután több nézethez férhet hozzá, ha a **Pénznem** gombra kattint a böngészőben, a jelentés megtekintésekkor.</span><span class="sxs-lookup"><span data-stu-id="0f778-133">You can then access multiple views by clicking the **Currency** button in the Web Viewer when you view the report.</span></span>
5.  <span data-ttu-id="0f778-134">A **Jelentések a csoportban** mezőben, kattintson a **Hozzáadás** gombra a jelentéscsoportba felvenni kívánt jelentések kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="0f778-134">In the **Reports in group** field, click **Add** to select the reports to include in the report group.</span></span> <span data-ttu-id="0f778-135">Több jelentés kijelöléséhez a **Hozzáadás** párbeszédablakban, tartsa lenyomva a Ctrl billentyűt, miközben kiválasztja az elemeket.</span><span class="sxs-lookup"><span data-stu-id="0f778-135">To select multiple reports in the **Add** dialog box, hold down the Ctrl key while you select reports.</span></span> <span data-ttu-id="0f778-136">Befejezése után jelölje ki a jelentéseket, és kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="0f778-136">When you've finished selecting reports, click **OK**.</span></span>
6.  <span data-ttu-id="0f778-137">Kattintson a **Fájl** &gt; **Mentés** elemre az új jelentéscsoport mentéséhez.</span><span class="sxs-lookup"><span data-stu-id="0f778-137">Click **File** &gt; **Save** to save the new report group.</span></span>

### <a name="modify-a-report-group"></a><span data-ttu-id="0f778-138">Jelentéscsoport módosítása</span><span class="sxs-lookup"><span data-stu-id="0f778-138">Modify a report group</span></span>

1.  <span data-ttu-id="0f778-139">A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0f778-139">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="0f778-140">Kattintson duplán a módosítani kívánt jelentéscsoportra.</span><span class="sxs-lookup"><span data-stu-id="0f778-140">Double-click the report group to modify.</span></span>
3.  <span data-ttu-id="0f778-141">A **Jelentéscsoport** lapon, végezze el a kívánt módosításokat.</span><span class="sxs-lookup"><span data-stu-id="0f778-141">On the **Report Group** tab, make the changes that you want.</span></span>
4.  <span data-ttu-id="0f778-142">A **Fájl** menüben kattintson a **Mentés** lehetőségre a módosított jelentéscsoport mentéséhez, vagy kattintson a **Mentés** gombra ![Mentés](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Mentés") az eszköztáron.</span><span class="sxs-lookup"><span data-stu-id="0f778-142">On the **File** menu, click **Save** to save the modified report group, Alternatively, click the **Save** button ![Save](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "Save") on the toolbar.</span></span>

<span data-ttu-id="0f778-143">**Megjegyzés:** Ha meghatározott időközönként létrehozott jelentéseket ütemezett, felülírhatja ezeket a beállításokat, és azonnal jelentéseket készíthet.</span><span class="sxs-lookup"><span data-stu-id="0f778-143">**Note:** If you've scheduled reports so that they are generated at set intervals, you can override those settings and generate a report immediately.</span></span>

### <a name="generate-a-report-group-report"></a><span data-ttu-id="0f778-144">Jelentéscsoportról szóló jelentés készítése</span><span class="sxs-lookup"><span data-stu-id="0f778-144">Generate a report group report</span></span>

1.  <span data-ttu-id="0f778-145">A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0f778-145">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="0f778-146">Nyissa meg a jelentéscsoportot a jelentés készítéséhez.</span><span class="sxs-lookup"><span data-stu-id="0f778-146">Open the report group to generate.</span></span>
3.  <span data-ttu-id="0f778-147">Kattintson a **Jelentés készítése** gombra ![Jelentés készítése](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Jelentés készítése") jelentések készítéséhez.</span><span class="sxs-lookup"><span data-stu-id="0f778-147">Click the **Generate Report** button ![Generate Report](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Generate Report") to generate reports.</span></span>

### <a name="delete-a-report-group"></a><span data-ttu-id="0f778-148">Jelentéscsoport törlése</span><span class="sxs-lookup"><span data-stu-id="0f778-148">Delete a report group</span></span>

1.  <span data-ttu-id="0f778-149">A Jelentéstervező navigációs ablakában kattintson a **Jelentéscsoportok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0f778-149">In Report Designer, in the navigation pane, click **Report Groups**.</span></span>
2.  <span data-ttu-id="0f778-150">A törléshez kattintson jobb gombbal a jelentés csoportra, és válassza **Törlés**lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0f778-150">Right-click the report group to delete, and then select **Delete**.</span></span>
3.  <span data-ttu-id="0f778-151">Ha egy megerősítő üzenet jelenik meg, kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="0f778-151">When a confirmation message appears, click **Yes**.</span></span>

## <a name="report-group-tab-controls"></a><span data-ttu-id="0f778-152">Jelentéscsoport-lap vezérlők</span><span class="sxs-lookup"><span data-stu-id="0f778-152">Report Group tab controls</span></span>
<span data-ttu-id="0f778-153">Az alábbi táblázat ismerteti a **Jelentéscsoport** lap vezérlőit.</span><span class="sxs-lookup"><span data-stu-id="0f778-153">The following table describes the controls on the **Report Group** tab.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f778-154">Vezérlő</span><span class="sxs-lookup"><span data-stu-id="0f778-154">Control</span></span></th>
<th><span data-ttu-id="0f778-155">Leírás</span><span class="sxs-lookup"><span data-stu-id="0f778-155">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0f778-156">Az egyes jelentésdefiníciókból a vállalat-, adat- és dátumbeállítások felülbírálása</span><span class="sxs-lookup"><span data-stu-id="0f778-156">Override company, detail, and date settings from individual report definitions</span></span></td>
<td><span data-ttu-id="0f778-157">Jelölje be ezt a jelölőnégyzetet, ha felül szeretné bírálni a jelentések egyéni jelentésdefinícióit a csak ezeknek a jelentéseknek az előállítására szolgáló jelentéscsoportban.</span><span class="sxs-lookup"><span data-stu-id="0f778-157">Select this check box to override individual report definitions of the reports in this report group for the generation of these reports only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0f778-158">Vállalat neve</span><span class="sxs-lookup"><span data-stu-id="0f778-158">Company name</span></span></td>
<td><span data-ttu-id="0f778-159">A jelentésekhez használt vállalat kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="0f778-159">Select the company to use for the reports.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0f778-160">Részletezési szint</span><span class="sxs-lookup"><span data-stu-id="0f778-160">Detail level</span></span></td>
<td><span data-ttu-id="0f778-161">Adja meg, hogy milyen részletes jelentést szeretne készíteni.</span><span class="sxs-lookup"><span data-stu-id="0f778-161">Specify the level of detail that the reports include.</span></span>
<ul>
<li><span data-ttu-id="0f778-162"><strong>Pénzügyi</strong>− Átfogó és összegző jelentés.</span><span class="sxs-lookup"><span data-stu-id="0f778-162"><strong>Financial</strong> − A high-level summary report.</span></span> <span data-ttu-id="0f778-163">Nem lehet számlákra és dimenziókra lebontani, kivéve az olyan számláknál és dimenzióknál, amelyeket a jelentési fán keresztül adtak hozzá.</span><span class="sxs-lookup"><span data-stu-id="0f778-163">You can't drill down to accounts and dimensions, except for those accounts and dimensions that have been added through a reporting tree.</span></span></li>
<li><span data-ttu-id="0f778-164"><strong>Pénzügy és Számla</strong> – Egy jelentés, amely átfogó összegzést és részletes számlaadatokat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="0f778-164"><strong>Financial &amp; Account</strong> − A report that contains a high-level summary and account details.</span></span></li>
<li><span data-ttu-id="0f778-165"><strong>Pénzügy, Számla és Tranzakció</strong> – Egy jelentés, amely átfogó összegzést és a tranzakció részletes adatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="0f778-165"><strong>Financial, Account, &amp; Transaction</strong> − A report that contains a high-level summary and transaction details.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0f778-166">Fedezetek</span><span class="sxs-lookup"><span data-stu-id="0f778-166">Provisional</span></span></td>
<td><span data-ttu-id="0f778-167">Adja meg, hogy milyen típusú tevékenységeket tartalmazzon a jelentés.</span><span class="sxs-lookup"><span data-stu-id="0f778-167">Specify the types of activity that the reports include.</span></span>
<ul>
<li><span data-ttu-id="0f778-168"><strong>Csak a feltüntetett tevékenység</strong> − Csak az olyan tranzakciókat és az egyenlegeket tartalmazza, amelyek a pénzügyi adataiban fel vannak tüntetve.</span><span class="sxs-lookup"><span data-stu-id="0f778-168"><strong>Posted activity only</strong> − Include only the transactions and balances that are posted in your financial data.</span></span></li>
<li><span data-ttu-id="0f778-169"><strong>Feltüntetett és nem feltüntetett tevékenység</strong> − Az összes tranzakció és egyenleg, amely meg van adva és fel van tüntetve a pénzügyi adataiban.</span><span class="sxs-lookup"><span data-stu-id="0f778-169"><strong>Posted and unposted activity</strong> − Include all the transactions and balances that are entered and posted in your financial data.</span></span></li>
<li><span data-ttu-id="0f778-170"><strong>Csak a nem feltüntetett tevékenység</strong> − Csak azokat a tranzakciókat tartalmazza, amelyek fel vannak jegyezve, de még nincsenek feltüntetve a pénzügyi adataiban.</span><span class="sxs-lookup"><span data-stu-id="0f778-170"><strong>Unposted activity only</strong> − Include only the transactions that are entered, but not yet posted, in your financial data.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0f778-171">Minden jelentési pénznemmel együtt</span><span class="sxs-lookup"><span data-stu-id="0f778-171">Include all reporting currencies</span></span></td>
<td><span data-ttu-id="0f778-172">Bármely további jelentési pénznem, amely be van állítva a Microsoft Dynamics ERP rendszeréhez itt kerül felsorolásra.</span><span class="sxs-lookup"><span data-stu-id="0f778-172">Any additional reporting currencies that are configured in your Microsoft Dynamics ERP system are listed here.</span></span> <span data-ttu-id="0f778-173">Jelölje ki ezt a jelölőnégyzetet, hogy további jelentéseket hozzon létre a jelölt pénznemekkel.</span><span class="sxs-lookup"><span data-stu-id="0f778-173">Select this check box to generate additional reports in the currencies that are indicated.</span></span> <span data-ttu-id="0f778-174">Ezen jelentések megtekintéséhez a böngészőben kattintson a <strong>Pénznem</strong> gombra, majd válassza ki a pénznemet.</span><span class="sxs-lookup"><span data-stu-id="0f778-174">To view these reports in the Web Viewer, click the <strong>Currency</strong> button, and then select a currency.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0f778-175">A dátummal kapcsolatos adatok mentése nem történik meg a jelentésdefiníciójával</span><span class="sxs-lookup"><span data-stu-id="0f778-175">Date information not saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="0f778-176">Bázisidőszak</span><span class="sxs-lookup"><span data-stu-id="0f778-176">Base period</span></span></li>
<li><span data-ttu-id="0f778-177">Bázisév</span><span class="sxs-lookup"><span data-stu-id="0f778-177">Base year</span></span></li>
<li><span data-ttu-id="0f778-178">Érintett időszakok</span><span class="sxs-lookup"><span data-stu-id="0f778-178">Period covered</span></span></li>
</ul>
<span data-ttu-id="0f778-179">Csak az alapértelmezett alapidőszak beállításainak mentése történik a jelentésdefinícióval.</span><span class="sxs-lookup"><span data-stu-id="0f778-179">Only default base period settings are saved with the report definition.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0f778-180">A dátummal kapcsolatos adatok mentődnek a jelentésdefiníciójával</span><span class="sxs-lookup"><span data-stu-id="0f778-180">Date information saved with report definition</span></span></td>
<td><ul>
<li><span data-ttu-id="0f778-181">Jelentés dátuma</span><span class="sxs-lookup"><span data-stu-id="0f778-181">Report date</span></span></li>
<li><span data-ttu-id="0f778-182">Alapértelmezett alap időtartam</span><span class="sxs-lookup"><span data-stu-id="0f778-182">Default base period</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0f778-183">Jelentések a csoportokban</span><span class="sxs-lookup"><span data-stu-id="0f778-183">Reports in group</span></span></td>
<td><span data-ttu-id="0f778-184">Jelentések hozzáadása, eltávolítása és újrarendezése jelentéscsoportban.</span><span class="sxs-lookup"><span data-stu-id="0f778-184">Add, remove, and re-order reports in the report group.</span></span>
<ul>
<li><span data-ttu-id="0f778-185">A jelentés csoporthoz való jelentésdefiníciók hozzáadásához, kattintson duplán a jelentéscsoport megnyitásához, és kattintson a <strong>Hozzáadásra</strong>.</span><span class="sxs-lookup"><span data-stu-id="0f778-185">To add report definitions to the report group, double-click the report group to open it, and then click <strong>Add</strong>.</span></span> <span data-ttu-id="0f778-186">Válassza ki beleszámítani kívánt jelentéseket a jelentéscsoportban és kattintson az <strong>OK</strong>lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0f778-186">Select the reports to include in the report group, and then click <strong>OK</strong>.</span></span></li>
<li><span data-ttu-id="0f778-187">A jelentés csoportból a jelentés eltávolításához jelölje ki, és kattintson az <strong>Eltávolításra</strong>.</span><span class="sxs-lookup"><span data-stu-id="0f778-187">To remove a report from the report group, select it, and then click <strong>Remove</strong>.</span></span></li>
<li><span data-ttu-id="0f778-188">A létrehozott jelentések sorrendjének módosításához válasszon ki a listából egy jelentést, majd kattintson <strong>Mozgatás felfelé</strong> vagy <strong>Mozgatás lefelé</strong> gombra.</span><span class="sxs-lookup"><span data-stu-id="0f778-188">To modify the order that the reports are generated in, select a report in the list, and then click <strong>Move up</strong> or <strong>Move down</strong>.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="0f778-189">Lásd még</span><span class="sxs-lookup"><span data-stu-id="0f778-189">See also</span></span>
--------

[<span data-ttu-id="0f778-190">Pénzügyi jelentéskészítés</span><span class="sxs-lookup"><span data-stu-id="0f778-190">Financial reporting</span></span>](financial-reporting-intro.md)




