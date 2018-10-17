--- 
title: "ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész – Számlálások használata a kimenet elkészítéséhez)"
description: "Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 5c870c134a9dae81cd619268bed7ce545bdd5f52
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="er-configure-format-to-do-counting-and-summing-part-3-use-computations-to-make-the-output"></a><span data-ttu-id="b518c-103">ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész: Számlálások használata a kimenet elkészítéséhez)</span><span class="sxs-lookup"><span data-stu-id="b518c-103">ER Configure format to do counting and summing (Part 3: Use computations to make the output)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b518c-104">Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján.</span><span class="sxs-lookup"><span data-stu-id="b518c-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="b518c-105">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="b518c-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="b518c-106">A lépések végrehajtásához először végre kell hajtania az „ER Számláláshoz és összegzéshez használt formátum konfigurálása (2. rész: Számlálások konfigurálása)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="b518c-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 2: Configure computations)” procedure.</span></span>

<span data-ttu-id="b518c-107">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="b518c-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="b518c-108">A jelentéssel konfigurálása a számlálási és összegzési információk konfigurálásához</span><span class="sxs-lookup"><span data-stu-id="b518c-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="b518c-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="b518c-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b518c-110">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b518c-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="b518c-111">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="b518c-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="b518c-112">A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="b518c-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="b518c-113">A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.</span><span class="sxs-lookup"><span data-stu-id="b518c-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="b518c-114">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="b518c-114">Click Designer.</span></span>
7. <span data-ttu-id="b518c-115">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b518c-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="b518c-116">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b518c-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="b518c-117">Adjon hozzá újra adatforrást a memorizált blokkok listájának lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="b518c-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="b518c-118">A fán válassza ki a „Functions\Calculated mező” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b518c-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="b518c-119">A Név mezőbe írja be a következőt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="b518c-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="b518c-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="b518c-120">$BlocksList</span></span>  
11. <span data-ttu-id="b518c-121">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b518c-121">Click Edit formula.</span></span>
12. <span data-ttu-id="b518c-122">A fastruktúrában válassza ki a következőt: „Adatgyűjtési függvények\COLLECTEDLIST”.</span><span class="sxs-lookup"><span data-stu-id="b518c-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="b518c-123">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-123">Click Add function.</span></span>
14. <span data-ttu-id="b518c-124">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b518c-124">Click Add data source.</span></span>
15. <span data-ttu-id="b518c-125">A Képlet mezőbe írja be a következőt: „COLLECTEDLIST('$BlockName', ”.</span><span class="sxs-lookup"><span data-stu-id="b518c-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="b518c-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="b518c-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="b518c-127">A Képlet mezőbe írja be a következőt: „COLLECTEDLIST('$BlockName', "\*")”.</span><span class="sxs-lookup"><span data-stu-id="b518c-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="b518c-128">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="b518c-128">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="b518c-129">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-129">Click Save.</span></span>
    * <span data-ttu-id="b518c-130">A „\*” minta azt jelenti, hogy minden blokk szerepelni fog a rekord listáján.</span><span class="sxs-lookup"><span data-stu-id="b518c-130">The pattern “\*” means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="b518c-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b518c-131">Close the page.</span></span>
19. <span data-ttu-id="b518c-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-132">Click OK.</span></span>
20. <span data-ttu-id="b518c-133">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="b518c-133">Click the Format tab.</span></span>
21. <span data-ttu-id="b518c-134">Válassza ki az „Intrastat\Adat” lehetőséget a fastruktúrában.</span><span class="sxs-lookup"><span data-stu-id="b518c-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="b518c-135">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b518c-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="b518c-136">A fastruktúrában válassza ki ezt: „Szöveg\Sorozat”.</span><span class="sxs-lookup"><span data-stu-id="b518c-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="b518c-137">A Név mezőbe írja be a „Összegek blokkok szerint” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b518c-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="b518c-138">Összegek blokkok szerint</span><span class="sxs-lookup"><span data-stu-id="b518c-138">Totals by blocks</span></span>  
25. <span data-ttu-id="b518c-139">A Különleges karakterek mezőben válassza ki az „Új sor – Windows (CR LF)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b518c-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="b518c-140">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-140">Click OK.</span></span>
27. <span data-ttu-id="b518c-141">A fastruktúrában bontsa ki az „Instrastat\Adat\Összegek blokkok szerint” elemet.</span><span class="sxs-lookup"><span data-stu-id="b518c-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="b518c-142">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b518c-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="b518c-143">A fában válassza ki ezt: „Text\String”.</span><span class="sxs-lookup"><span data-stu-id="b518c-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="b518c-144">A Név mezőbe írja be a „Blokk kód” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b518c-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="b518c-145">Blokk kód</span><span class="sxs-lookup"><span data-stu-id="b518c-145">Block code</span></span>  
31. <span data-ttu-id="b518c-146">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-146">Click OK.</span></span>
32. <span data-ttu-id="b518c-147">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b518c-147">Click Add String.</span></span>
33. <span data-ttu-id="b518c-148">A Név mezőbe írja be a „Sorszámlálás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b518c-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="b518c-149">Sorszámlálás</span><span class="sxs-lookup"><span data-stu-id="b518c-149">Lines counting</span></span>  
34. <span data-ttu-id="b518c-150">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-150">Click OK.</span></span>
35. <span data-ttu-id="b518c-151">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b518c-151">Click Add String.</span></span>
36. <span data-ttu-id="b518c-152">A Név mezőbe írja be a „Teljes összeg” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b518c-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="b518c-153">Teljes összeg</span><span class="sxs-lookup"><span data-stu-id="b518c-153">Total amount</span></span>  
37. <span data-ttu-id="b518c-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-154">Click OK.</span></span>
38. <span data-ttu-id="b518c-155">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b518c-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="b518c-156">A fastruktúrában válassza ki ezt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="b518c-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="b518c-157">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-157">Click Bind.</span></span>
    * <span data-ttu-id="b518c-158">Hozzon létre összegző sort minden memorizált blokkhoz.</span><span class="sxs-lookup"><span data-stu-id="b518c-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="b518c-159">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="b518c-159">Click the Format tab.</span></span>
42. <span data-ttu-id="b518c-160">A fastruktúrában válassza ki az „Instrastat\Adat\Összegek blokkok szerint\Blokk kód” elemet.</span><span class="sxs-lookup"><span data-stu-id="b518c-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="b518c-161">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b518c-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="b518c-162">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b518c-162">Click Edit formula.</span></span>
45. <span data-ttu-id="b518c-163">A Képlet mezőbe írja be a következőt: „„Blokkazonosító:” és ”.</span><span class="sxs-lookup"><span data-stu-id="b518c-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="b518c-164">„Blokk azonosítója:” és</span><span class="sxs-lookup"><span data-stu-id="b518c-164">"Block id: " &</span></span>  
46. <span data-ttu-id="b518c-165">A fastruktúrában bontsa ki ezt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="b518c-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="b518c-166">A fastruktúrában válassza ki a következőt: „$BlocksList\Érték”.</span><span class="sxs-lookup"><span data-stu-id="b518c-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="b518c-167">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b518c-167">Click Add data source.</span></span>
49. <span data-ttu-id="b518c-168">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-168">Click Save.</span></span>
50. <span data-ttu-id="b518c-169">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b518c-169">Close the page.</span></span>
51. <span data-ttu-id="b518c-170">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="b518c-170">Click the Format tab.</span></span>
52. <span data-ttu-id="b518c-171">A fastruktúrában válassza ki a következőt: „Instrastat\Adat\Összegek blokkok szerint\Sorszámlálás”.</span><span class="sxs-lookup"><span data-stu-id="b518c-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="b518c-172">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b518c-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="b518c-173">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b518c-173">Click Edit formula.</span></span>
    * <span data-ttu-id="b518c-174">Hozzon létre kimenetet a jelentésben szereplő minden egyes blokk sorainak számához.</span><span class="sxs-lookup"><span data-stu-id="b518c-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="b518c-175">A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és ”.</span><span class="sxs-lookup"><span data-stu-id="b518c-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="b518c-176">„Sorok száma ebben a blokkban:” és</span><span class="sxs-lookup"><span data-stu-id="b518c-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="b518c-177">A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT ”.</span><span class="sxs-lookup"><span data-stu-id="b518c-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="b518c-178">„Sorok száma ebben a blokkban:” és TEXT(</span><span class="sxs-lookup"><span data-stu-id="b518c-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="b518c-179">A fastruktúrában válassza ki a következőt: „Adatgyűjtési függvények\COUNTIFS”.</span><span class="sxs-lookup"><span data-stu-id="b518c-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="b518c-180">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-180">Click Add function.</span></span>
59. <span data-ttu-id="b518c-181">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b518c-181">Click Add data source.</span></span>
60. <span data-ttu-id="b518c-182">A képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', ".</span><span class="sxs-lookup"><span data-stu-id="b518c-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="b518c-183">„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="b518c-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="b518c-184">A fastruktúrában bontsa ki ezt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="b518c-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="b518c-185">A fastruktúrában válassza ki a következőt: „$BlocksList\Érték”.</span><span class="sxs-lookup"><span data-stu-id="b518c-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="b518c-186">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b518c-186">Click Add data source.</span></span>
64. <span data-ttu-id="b518c-187">A képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, ".</span><span class="sxs-lookup"><span data-stu-id="b518c-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="b518c-188">„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="b518c-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="b518c-189">A fastruktúrában válassza ki a következőt: „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="b518c-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="b518c-190">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b518c-190">Click Add data source.</span></span>
67. <span data-ttu-id="b518c-191">A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))”.</span><span class="sxs-lookup"><span data-stu-id="b518c-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="b518c-192">„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="b518c-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="b518c-193">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-193">Click Save.</span></span>
69. <span data-ttu-id="b518c-194">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b518c-194">Close the page.</span></span>
70. <span data-ttu-id="b518c-195">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="b518c-195">Click the Format tab.</span></span>
71. <span data-ttu-id="b518c-196">A fastruktúrában válassza ki a következőt: „Instrastat\Adat\Összegek blokkok szerint\Teljes összeg”.</span><span class="sxs-lookup"><span data-stu-id="b518c-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="b518c-197">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b518c-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="b518c-198">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b518c-198">Click Edit formula.</span></span>
    * <span data-ttu-id="b518c-199">Hozzon létre kimenetet, amely a számlázott összegek összegzése lesz a jelentésben szereplő összes blokk esetében.</span><span class="sxs-lookup"><span data-stu-id="b518c-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="b518c-200">A Képlet mezőben adja meg a következőt: „Számlázott összeg összegzése:” és TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))”.</span><span class="sxs-lookup"><span data-stu-id="b518c-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="b518c-201">„Számlázott összeg összegzése:” és TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="b518c-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="b518c-202">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-202">Click Save.</span></span>
76. <span data-ttu-id="b518c-203">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b518c-203">Close the page.</span></span>
77. <span data-ttu-id="b518c-204">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b518c-204">Click Save.</span></span>
78. <span data-ttu-id="b518c-205">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b518c-205">Close the page.</span></span>


