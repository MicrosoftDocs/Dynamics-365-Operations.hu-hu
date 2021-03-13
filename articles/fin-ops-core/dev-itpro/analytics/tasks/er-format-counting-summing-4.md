---
title: ER Számláláshoz és összegzéshez használt formátum konfigurálása (4. rész – Formátum futtatása)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni az Elektronikus jelentéskészítési formátumokat a már létrehozott szövegkimenet adatai alapján. (4. rész)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5576229e8b81824dff6d0b38b8ab5483e04ade8
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092947"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a><span data-ttu-id="5835a-104">ER Számláláshoz és összegzéshez használt formátum konfigurálása (4. rész – Formátum futtatása)</span><span class="sxs-lookup"><span data-stu-id="5835a-104">ER Configure format to do counting and summing (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5835a-105">Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján.</span><span class="sxs-lookup"><span data-stu-id="5835a-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="5835a-106">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="5835a-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="5835a-107">A lépések végrehajtásához először végre kell hajtania az „ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész: Számítások használata a kimenet elkészítéséhez)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="5835a-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 3: Use computations to make the output)" procedure.</span></span>

<span data-ttu-id="5835a-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="5835a-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="5835a-109">A konfiguráció tesztelése az Intrastat-jelentések létrehozása céljából</span><span class="sxs-lookup"><span data-stu-id="5835a-109">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="5835a-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="5835a-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="5835a-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5835a-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="5835a-112">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="5835a-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="5835a-113">A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="5835a-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="5835a-114">A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.</span><span class="sxs-lookup"><span data-stu-id="5835a-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="5835a-115">Kattintson a Konfigurációk lehetőségre a Művelet Panelen.</span><span class="sxs-lookup"><span data-stu-id="5835a-115">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="5835a-116">Kattintson a Felhasználói paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5835a-116">Click User parameters.</span></span>
8. <span data-ttu-id="5835a-117">Válassza az Igen lehetőséget a Beállítások futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="5835a-117">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="5835a-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5835a-118">Click OK.</span></span>
10. <span data-ttu-id="5835a-119">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5835a-119">Click Edit.</span></span>
11. <span data-ttu-id="5835a-120">Válassza az Igen lehetőséget a Vázlat futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="5835a-120">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="5835a-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5835a-121">Click Save.</span></span>
13. <span data-ttu-id="5835a-122">Ugorjon az Adó > Beállítás > Külkereskedelmi > Külkereskedelmi paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="5835a-122">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="5835a-123">Bontsa ki az elektronikus jelentéskészítés szakaszát.</span><span class="sxs-lookup"><span data-stu-id="5835a-123">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="5835a-124">Válassza az „Intrastat (DE) számolással és összegzéssel” konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="5835a-124">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
16. <span data-ttu-id="5835a-125">Válassza az „Intrastat (DE) számolással és összegzéssel” konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="5835a-125">Select the "Intrastat (DE) with counting & summing" configuration.</span></span>
17. <span data-ttu-id="5835a-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5835a-126">Click Save.</span></span>
18. <span data-ttu-id="5835a-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5835a-127">Close the page.</span></span>
19. <span data-ttu-id="5835a-128">Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.</span><span class="sxs-lookup"><span data-stu-id="5835a-128">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="5835a-129">Kattintson a Kimenet lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5835a-129">Click Output.</span></span>
21. <span data-ttu-id="5835a-130">Kattintson a Jelentésre.</span><span class="sxs-lookup"><span data-stu-id="5835a-130">Click Report.</span></span>
    * <span data-ttu-id="5835a-131">Az Intrastat jelentéslétrehozási folyamat futtatása.</span><span class="sxs-lookup"><span data-stu-id="5835a-131">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="5835a-132">A Kezdő dátum mezőben állítsa „2000-01-01” értékűre a dátumot.</span><span class="sxs-lookup"><span data-stu-id="5835a-132">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="5835a-133">A jelentési időszak kezdő és záró dátumának beállítása, amelyek tartalmazzák a meglévő űrlaptranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="5835a-133">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="5835a-134">A Befejező dátum mezőben állítsa „2022-12-31” értékűre a dátumot.</span><span class="sxs-lookup"><span data-stu-id="5835a-134">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="5835a-135">A jelentési időszak kezdő és záró dátumának beállítása, amelyek tartalmazzák a meglévő űrlaptranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="5835a-135">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="5835a-136">Az Irány mezőben válassza az „Érkezések” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5835a-136">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="5835a-137">Válassza az Igen lehetőséget a Fájl létrehozása mezőben.</span><span class="sxs-lookup"><span data-stu-id="5835a-137">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="5835a-138">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5835a-138">Click OK.</span></span>
    * <span data-ttu-id="5835a-139">Tekintse át a létrehozott kimenetet, a végén az összesítő sorokkal.</span><span class="sxs-lookup"><span data-stu-id="5835a-139">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="5835a-140">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5835a-140">Click New.</span></span>
28. <span data-ttu-id="5835a-141">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="5835a-141">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="5835a-142">Az Irány mezőben válassza a „Feladások” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5835a-142">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="5835a-143">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5835a-143">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="5835a-144">Az Árucikk mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5835a-144">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="5835a-145">A Tömeget állítsa a „10” értékre.</span><span class="sxs-lookup"><span data-stu-id="5835a-145">Set Weight to '10'.</span></span>
33. <span data-ttu-id="5835a-146">A Számlaösszeget állítsa a „10000” értékre.</span><span class="sxs-lookup"><span data-stu-id="5835a-146">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="5835a-147">A Statisztikai összeget állítsa a „10000” értékre.</span><span class="sxs-lookup"><span data-stu-id="5835a-147">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="5835a-148">Kattintson a Kimenet lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5835a-148">Click Output.</span></span>
36. <span data-ttu-id="5835a-149">Kattintson a Jelentésre.</span><span class="sxs-lookup"><span data-stu-id="5835a-149">Click Report.</span></span>
37. <span data-ttu-id="5835a-150">Az Irány mezőben válassza a „Feladások” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5835a-150">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="5835a-151">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5835a-151">Click OK.</span></span>
    * <span data-ttu-id="5835a-152">Tekintse át a létrehozott kimenetet, a végén az összesítő sorokkal.</span><span class="sxs-lookup"><span data-stu-id="5835a-152">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="5835a-153">Fontos megjegyezni, hogy megváltozott az első futtatással összehasonlítva.</span><span class="sxs-lookup"><span data-stu-id="5835a-153">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="5835a-154">A konfiguráció futtatása hibakeresési módban az összegyűjtött számlálási és összegzési adatok felülvizsgálatához</span><span class="sxs-lookup"><span data-stu-id="5835a-154">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="5835a-155">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="5835a-155">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="5835a-156">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="5835a-156">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="5835a-157">A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="5835a-157">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="5835a-158">A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.</span><span class="sxs-lookup"><span data-stu-id="5835a-158">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="5835a-159">Kattintson a Konfigurációk lehetőségre a Művelet Panelen.</span><span class="sxs-lookup"><span data-stu-id="5835a-159">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="5835a-160">Kattintson a Felhasználói paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5835a-160">Click User parameters.</span></span>
7. <span data-ttu-id="5835a-161">Válassza az Igen lehetőséget a Futtatás hibakeresési módban mezőben.</span><span class="sxs-lookup"><span data-stu-id="5835a-161">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="5835a-162">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5835a-162">Click OK.</span></span>
9. <span data-ttu-id="5835a-163">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5835a-163">Close the page.</span></span>
10. <span data-ttu-id="5835a-164">Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.</span><span class="sxs-lookup"><span data-stu-id="5835a-164">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="5835a-165">Kattintson a Kimenet lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5835a-165">Click Output.</span></span>
12. <span data-ttu-id="5835a-166">Kattintson a Jelentésre.</span><span class="sxs-lookup"><span data-stu-id="5835a-166">Click Report.</span></span>
13. <span data-ttu-id="5835a-167">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="5835a-167">Click OK.</span></span>
14. <span data-ttu-id="5835a-168">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5835a-168">Close the page.</span></span>
15. <span data-ttu-id="5835a-169">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="5835a-169">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="5835a-170">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="5835a-170">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="5835a-171">A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="5835a-171">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="5835a-172">A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.</span><span class="sxs-lookup"><span data-stu-id="5835a-172">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="5835a-173">Kattintson a Hibakeresési naplók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5835a-173">Click Debug logs.</span></span>
    * <span data-ttu-id="5835a-174">Fontos megjegyezni, hogy hibakeresési naplóbejegyzés lett létrehozva a kijelölt konfiguráció végrehajtási folyamatához.</span><span class="sxs-lookup"><span data-stu-id="5835a-174">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="5835a-175">Kattintson a Csatolás elemre.</span><span class="sxs-lookup"><span data-stu-id="5835a-175">Click Attach.</span></span>
21. <span data-ttu-id="5835a-176">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="5835a-176">Click Open.</span></span>
    * <span data-ttu-id="5835a-177">Tekintse át a létrehozott XML-fájlt, amely tartalmazza a kijelölt konfiguráció végrehajtása során gyűjtött számlálási és összegzési adatokat.</span><span class="sxs-lookup"><span data-stu-id="5835a-177">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  

