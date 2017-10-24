--- 
title: "Formátum futtatása számláláshoz és összegzéshez az elektronikus jelentéskészítéshez (ER)"
description: "Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 9f5520dc4e1eddc2fc52a05e5dc386b982d8f5ad
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="run-the-format-to-do-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="4d7e2-103">Formátum futtatása számláláshoz és összegzéshez az elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="4d7e2-103">Run the format to do counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4d7e2-104">Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="4d7e2-105">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="4d7e2-106">A lépések végrehajtásához először végre kell hajtania az „ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész: Számlálások használata a kimenet elkészítéséhez)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 3: Use computations to make the output)” procedure.</span></span>

<span data-ttu-id="4d7e2-107">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a><span data-ttu-id="4d7e2-108">A konfiguráció tesztelése az Intrastat-jelentések létrehozása céljából</span><span class="sxs-lookup"><span data-stu-id="4d7e2-108">Test this configuration for generation of the Intrastat reports</span></span>
1. <span data-ttu-id="4d7e2-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="4d7e2-110">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="4d7e2-111">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="4d7e2-112">A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="4d7e2-113">A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="4d7e2-114">Kattintson a Konfigurációk lehetőségre a Művelet Panelen.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-114">On the Action Pane, click Configurations.</span></span>
7. <span data-ttu-id="4d7e2-115">Kattintson a Felhasználói paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-115">Click User parameters.</span></span>
8. <span data-ttu-id="4d7e2-116">Válassza az Igen lehetőséget a Beállítások futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-116">Select Yes in the Run settings field.</span></span>
9. <span data-ttu-id="4d7e2-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-117">Click OK.</span></span>
10. <span data-ttu-id="4d7e2-118">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-118">Click Edit.</span></span>
11. <span data-ttu-id="4d7e2-119">Válassza az Igen lehetőséget a Vázlat futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-119">Select Yes in the Run Draft field.</span></span>
12. <span data-ttu-id="4d7e2-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-120">Click Save.</span></span>
13. <span data-ttu-id="4d7e2-121">Ugorjon az Adó > Beállítás > Külkereskedelmi > Külkereskedelmi paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-121">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
14. <span data-ttu-id="4d7e2-122">Bontsa ki az elektronikus jelentéskészítés szakaszát.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-122">Expand the Electronic reporting section.</span></span>
15. <span data-ttu-id="4d7e2-123">Válassza az „Intrastat (DE) számolással és összegzéssel” konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-123">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
16. <span data-ttu-id="4d7e2-124">Válassza az „Intrastat (DE) számolással és összegzéssel” konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-124">Select the “Intrastat (DE) with counting & summing” configuration.</span></span>
17. <span data-ttu-id="4d7e2-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-125">Click Save.</span></span>
18. <span data-ttu-id="4d7e2-126">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-126">Close the page.</span></span>
19. <span data-ttu-id="4d7e2-127">Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-127">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
20. <span data-ttu-id="4d7e2-128">Kattintson a Kimenet lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-128">Click Output.</span></span>
21. <span data-ttu-id="4d7e2-129">Kattintson a Jelentésre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-129">Click Report.</span></span>
    * <span data-ttu-id="4d7e2-130">Az Intrastat jelentéslétrehozási folyamat futtatása.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-130">Run the Intrastat report generation process.</span></span>  
22. <span data-ttu-id="4d7e2-131">A Kezdő dátum mezőben állítsa „2000-01-01” értékűre a dátumot.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-131">In the From date field, set the date to '2000-01-01'.</span></span>
    * <span data-ttu-id="4d7e2-132">A jelentési időszak kezdő és záró dátumának beállítása, amelyek tartalmazzák a meglévő űrlaptranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-132">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
23. <span data-ttu-id="4d7e2-133">A Befejező dátum mezőben állítsa „2022-12-31” értékűre a dátumot.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-133">In the To date field, set the date to '2022-12-31'.</span></span>
    * <span data-ttu-id="4d7e2-134">A jelentési időszak kezdő és záró dátumának beállítása, amelyek tartalmazzák a meglévő űrlaptranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-134">Define start and end dates for the reporting period that include the existing on the form transactions.</span></span>  
24. <span data-ttu-id="4d7e2-135">Az Irány mezőben válassza az „Érkezések” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-135">In the Direction field, select 'Arrivals'.</span></span>
25. <span data-ttu-id="4d7e2-136">Válassza az Igen lehetőséget a Fájl létrehozása mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-136">Select Yes in the Generate file field.</span></span>
26. <span data-ttu-id="4d7e2-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-137">Click OK.</span></span>
    * <span data-ttu-id="4d7e2-138">Tekintse át a létrehozott kimenetet, a végén az összesítő sorokkal.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-138">Review the created output with the summary lines in the end.</span></span>  
27. <span data-ttu-id="4d7e2-139">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-139">Click New.</span></span>
28. <span data-ttu-id="4d7e2-140">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-140">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="4d7e2-141">Az Irány mezőben válassza a „Feladások” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-141">In the Direction field, select 'Dispatches'.</span></span>
30. <span data-ttu-id="4d7e2-142">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-142">In the Item number field, enter or select a value.</span></span>
31. <span data-ttu-id="4d7e2-143">Az Árucikk mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-143">In the Commodity field, enter or select a value.</span></span>
32. <span data-ttu-id="4d7e2-144">A Tömeget állítsa a „10” értékre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-144">Set Weight to '10'.</span></span>
33. <span data-ttu-id="4d7e2-145">A Számlaösszeget állítsa a „10000” értékre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-145">Set Invoice amount to '10000'.</span></span>
34. <span data-ttu-id="4d7e2-146">A Statisztikai összeget állítsa a „10000” értékre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-146">Set Statistical amount to '10000'.</span></span>
35. <span data-ttu-id="4d7e2-147">Kattintson a Kimenet lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-147">Click Output.</span></span>
36. <span data-ttu-id="4d7e2-148">Kattintson a Jelentésre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-148">Click Report.</span></span>
37. <span data-ttu-id="4d7e2-149">Az Irány mezőben válassza a „Feladások” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-149">In the Direction field, select 'Dispatches'.</span></span>
38. <span data-ttu-id="4d7e2-150">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-150">Click OK.</span></span>
    * <span data-ttu-id="4d7e2-151">Tekintse át a létrehozott kimenetet, a végén az összesítő sorokkal.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-151">Review the created output with the summary lines in the end.</span></span> <span data-ttu-id="4d7e2-152">Fontos megjegyezni, hogy megváltozott az első futtatással összehasonlítva.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-152">Note that it has been changed in comparison to the first run.</span></span>  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a><span data-ttu-id="4d7e2-153">A konfiguráció futtatása hibakeresési módban az összegyűjtött számlálási és összegzési adatok felülvizsgálatához</span><span class="sxs-lookup"><span data-stu-id="4d7e2-153">Run this configuration in debug mode to review the collected counting & summing data</span></span>
1. <span data-ttu-id="4d7e2-154">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-154">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="4d7e2-155">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-155">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="4d7e2-156">A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-156">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
4. <span data-ttu-id="4d7e2-157">A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-157">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
5. <span data-ttu-id="4d7e2-158">Kattintson a Konfigurációk lehetőségre a Művelet Panelen.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-158">On the Action Pane, click Configurations.</span></span>
6. <span data-ttu-id="4d7e2-159">Kattintson a Felhasználói paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-159">Click User parameters.</span></span>
7. <span data-ttu-id="4d7e2-160">Válassza az Igen lehetőséget a Futtatás hibakeresési módban mezőben.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-160">Select Yes in the Run in debug mode field.</span></span>
8. <span data-ttu-id="4d7e2-161">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-161">Click OK.</span></span>
9. <span data-ttu-id="4d7e2-162">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-162">Close the page.</span></span>
10. <span data-ttu-id="4d7e2-163">Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-163">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
11. <span data-ttu-id="4d7e2-164">Kattintson a Kimenet lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-164">Click Output.</span></span>
12. <span data-ttu-id="4d7e2-165">Kattintson a Jelentésre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-165">Click Report.</span></span>
13. <span data-ttu-id="4d7e2-166">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-166">Click OK.</span></span>
14. <span data-ttu-id="4d7e2-167">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-167">Close the page.</span></span>
15. <span data-ttu-id="4d7e2-168">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-168">Go to Organization administration > Electronic reporting > Configurations.</span></span>
16. <span data-ttu-id="4d7e2-169">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-169">In the tree, expand 'Intrastat model'.</span></span>
17. <span data-ttu-id="4d7e2-170">A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-170">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
18. <span data-ttu-id="4d7e2-171">A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-171">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
19. <span data-ttu-id="4d7e2-172">Kattintson a Hibakeresési naplók lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-172">Click Debug logs.</span></span>
    * <span data-ttu-id="4d7e2-173">Fontos megjegyezni, hogy hibakeresési naplóbejegyzés lett létrehozva a kijelölt konfiguráció végrehajtási folyamatához.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-173">Note that a debug log record has been created for the execution process of the selected configuration.</span></span>  
20. <span data-ttu-id="4d7e2-174">Kattintson a Csatolás elemre.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-174">Click Attach.</span></span>
21. <span data-ttu-id="4d7e2-175">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-175">Click Open.</span></span>
    * <span data-ttu-id="4d7e2-176">Tekintse át a létrehozott XML-fájlt, amely tartalmazza a kijelölt konfiguráció végrehajtása során gyűjtött számlálási és összegzési adatokat.</span><span class="sxs-lookup"><span data-stu-id="4d7e2-176">Review the created XML file that contains counting and summing details that were collected during the execution of the selected configuration.</span></span>  

