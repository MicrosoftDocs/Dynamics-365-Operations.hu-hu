---
title: ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész – Számlálások használata a kimenet elkészítéséhez)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni az Elektronikus jelentéskészítési formátumokat a már létrehozott szövegkimenet adatai alapján. (3. rész)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af95399118b9059b9bead3a1b84203cf3b6e74c2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567116"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="3b325-104">ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész – Számlálások használata a kimenet elkészítéséhez)</span><span class="sxs-lookup"><span data-stu-id="3b325-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3b325-105">Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján.</span><span class="sxs-lookup"><span data-stu-id="3b325-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="3b325-106">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="3b325-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="3b325-107">A lépések végrehajtásához először végre kell hajtania az „ER Számláláshoz és összegzéshez használt formátum konfigurálása (2. rész: Számlálások konfigurálása)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="3b325-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="3b325-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="3b325-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="3b325-109">A jelentéssel konfigurálása a számlálási és összegzési információk konfigurálásához</span><span class="sxs-lookup"><span data-stu-id="3b325-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="3b325-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="3b325-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="3b325-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b325-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="3b325-112">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="3b325-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="3b325-113">A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="3b325-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="3b325-114">A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.</span><span class="sxs-lookup"><span data-stu-id="3b325-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="3b325-115">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="3b325-115">Click Designer.</span></span>
7. <span data-ttu-id="3b325-116">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="3b325-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="3b325-117">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3b325-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="3b325-118">Adjon hozzá újra adatforrást a memorizált blokkok listájának lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="3b325-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="3b325-119">A fán válassza ki a „Functions\Calculated mező” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b325-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="3b325-120">A Név mezőbe írja be a következőt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="3b325-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="3b325-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="3b325-121">$BlocksList</span></span>  
11. <span data-ttu-id="3b325-122">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b325-122">Click Edit formula.</span></span>
12. <span data-ttu-id="3b325-123">A fastruktúrában válassza ki a következőt: „Adatgyűjtési függvények\COLLECTEDLIST”.</span><span class="sxs-lookup"><span data-stu-id="3b325-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="3b325-124">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-124">Click Add function.</span></span>
14. <span data-ttu-id="3b325-125">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="3b325-125">Click Add data source.</span></span>
15. <span data-ttu-id="3b325-126">A Képlet mezőbe írja be a következőt: „COLLECTEDLIST('$BlockName', ”.</span><span class="sxs-lookup"><span data-stu-id="3b325-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="3b325-127">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="3b325-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="3b325-128">A Képlet mezőbe írja be a következőt: „COLLECTEDLIST('$BlockName', "\*")”.</span><span class="sxs-lookup"><span data-stu-id="3b325-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="3b325-129">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="3b325-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="3b325-130">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-130">Click Save.</span></span>
    * <span data-ttu-id="3b325-131">A „\*” minta azt jelenti, hogy minden blokk szerepelni fog a rekord listáján.</span><span class="sxs-lookup"><span data-stu-id="3b325-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="3b325-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3b325-132">Close the page.</span></span>
19. <span data-ttu-id="3b325-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-133">Click OK.</span></span>
20. <span data-ttu-id="3b325-134">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="3b325-134">Click the Format tab.</span></span>
21. <span data-ttu-id="3b325-135">Válassza ki az „Intrastat\Adat” lehetőséget a fastruktúrában.</span><span class="sxs-lookup"><span data-stu-id="3b325-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="3b325-136">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="3b325-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="3b325-137">A fastruktúrában válassza ki ezt: „Szöveg\Sorozat”.</span><span class="sxs-lookup"><span data-stu-id="3b325-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="3b325-138">A Név mezőbe írja be a „Összegek blokkok szerint” szöveget.</span><span class="sxs-lookup"><span data-stu-id="3b325-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="3b325-139">Összegek blokkok szerint</span><span class="sxs-lookup"><span data-stu-id="3b325-139">Totals by blocks</span></span>  
25. <span data-ttu-id="3b325-140">A Különleges karakterek mezőben válassza ki az „Új sor – Windows (CR LF)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3b325-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="3b325-141">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-141">Click OK.</span></span>
27. <span data-ttu-id="3b325-142">A fastruktúrában bontsa ki az „Instrastat\Adat\Összegek blokkok szerint” elemet.</span><span class="sxs-lookup"><span data-stu-id="3b325-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="3b325-143">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="3b325-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="3b325-144">A fában válassza ki ezt: „Text\String”.</span><span class="sxs-lookup"><span data-stu-id="3b325-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="3b325-145">A Név mezőbe írja be a „Blokk kód” szöveget.</span><span class="sxs-lookup"><span data-stu-id="3b325-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="3b325-146">Blokk kód</span><span class="sxs-lookup"><span data-stu-id="3b325-146">Block code</span></span>  
31. <span data-ttu-id="3b325-147">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-147">Click OK.</span></span>
32. <span data-ttu-id="3b325-148">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b325-148">Click Add String.</span></span>
33. <span data-ttu-id="3b325-149">A Név mezőbe írja be a „Sorszámlálás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="3b325-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="3b325-150">Sorszámlálás</span><span class="sxs-lookup"><span data-stu-id="3b325-150">Lines counting</span></span>  
34. <span data-ttu-id="3b325-151">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-151">Click OK.</span></span>
35. <span data-ttu-id="3b325-152">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b325-152">Click Add String.</span></span>
36. <span data-ttu-id="3b325-153">A Név mezőbe írja be a „Teljes összeg” szöveget.</span><span class="sxs-lookup"><span data-stu-id="3b325-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="3b325-154">Teljes összeg</span><span class="sxs-lookup"><span data-stu-id="3b325-154">Total amount</span></span>  
37. <span data-ttu-id="3b325-155">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-155">Click OK.</span></span>
38. <span data-ttu-id="3b325-156">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="3b325-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="3b325-157">A fastruktúrában válassza ki ezt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="3b325-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="3b325-158">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-158">Click Bind.</span></span>
    * <span data-ttu-id="3b325-159">Hozzon létre összegző sort minden memorizált blokkhoz.</span><span class="sxs-lookup"><span data-stu-id="3b325-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="3b325-160">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="3b325-160">Click the Format tab.</span></span>
42. <span data-ttu-id="3b325-161">A fastruktúrában válassza ki az „Instrastat\Adat\Összegek blokkok szerint\Blokk kód” elemet.</span><span class="sxs-lookup"><span data-stu-id="3b325-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="3b325-162">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="3b325-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="3b325-163">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b325-163">Click Edit formula.</span></span>
45. <span data-ttu-id="3b325-164">A Képlet mezőbe írja be a következőt: „„Blokkazonosító:” és ”.</span><span class="sxs-lookup"><span data-stu-id="3b325-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="3b325-165">„Blokk azonosítója:” és</span><span class="sxs-lookup"><span data-stu-id="3b325-165">"Block id: " &</span></span>  
46. <span data-ttu-id="3b325-166">A fastruktúrában bontsa ki ezt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="3b325-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="3b325-167">A fastruktúrában válassza ki a következőt: „$BlocksList\Érték”.</span><span class="sxs-lookup"><span data-stu-id="3b325-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="3b325-168">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="3b325-168">Click Add data source.</span></span>
49. <span data-ttu-id="3b325-169">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-169">Click Save.</span></span>
50. <span data-ttu-id="3b325-170">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3b325-170">Close the page.</span></span>
51. <span data-ttu-id="3b325-171">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="3b325-171">Click the Format tab.</span></span>
52. <span data-ttu-id="3b325-172">A fastruktúrában válassza ki a következőt: „Instrastat\Adat\Összegek blokkok szerint\Sorszámlálás”.</span><span class="sxs-lookup"><span data-stu-id="3b325-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="3b325-173">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="3b325-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="3b325-174">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b325-174">Click Edit formula.</span></span>
    * <span data-ttu-id="3b325-175">Hozzon létre kimenetet a jelentésben szereplő minden egyes blokk sorainak számához.</span><span class="sxs-lookup"><span data-stu-id="3b325-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="3b325-176">A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és ”.</span><span class="sxs-lookup"><span data-stu-id="3b325-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="3b325-177">„Sorok száma ebben a blokkban:” és</span><span class="sxs-lookup"><span data-stu-id="3b325-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="3b325-178">A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT ”.</span><span class="sxs-lookup"><span data-stu-id="3b325-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="3b325-179">„Sorok száma ebben a blokkban:” és TEXT(</span><span class="sxs-lookup"><span data-stu-id="3b325-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="3b325-180">A fastruktúrában válassza ki a következőt: „Adatgyűjtési függvények\COUNTIFS”.</span><span class="sxs-lookup"><span data-stu-id="3b325-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="3b325-181">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-181">Click Add function.</span></span>
59. <span data-ttu-id="3b325-182">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="3b325-182">Click Add data source.</span></span>
60. <span data-ttu-id="3b325-183">A képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', ".</span><span class="sxs-lookup"><span data-stu-id="3b325-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="3b325-184">„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="3b325-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="3b325-185">A fastruktúrában bontsa ki ezt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="3b325-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="3b325-186">A fastruktúrában válassza ki a következőt: „$BlocksList\Érték”.</span><span class="sxs-lookup"><span data-stu-id="3b325-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="3b325-187">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="3b325-187">Click Add data source.</span></span>
64. <span data-ttu-id="3b325-188">A képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, ".</span><span class="sxs-lookup"><span data-stu-id="3b325-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="3b325-189">„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="3b325-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="3b325-190">A fastruktúrában válassza ki a következőt: „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="3b325-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="3b325-191">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="3b325-191">Click Add data source.</span></span>
67. <span data-ttu-id="3b325-192">A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))”.</span><span class="sxs-lookup"><span data-stu-id="3b325-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="3b325-193">„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="3b325-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="3b325-194">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-194">Click Save.</span></span>
69. <span data-ttu-id="3b325-195">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3b325-195">Close the page.</span></span>
70. <span data-ttu-id="3b325-196">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="3b325-196">Click the Format tab.</span></span>
71. <span data-ttu-id="3b325-197">A fastruktúrában válassza ki a következőt: „Instrastat\Adat\Összegek blokkok szerint\Teljes összeg”.</span><span class="sxs-lookup"><span data-stu-id="3b325-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="3b325-198">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="3b325-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="3b325-199">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3b325-199">Click Edit formula.</span></span>
    * <span data-ttu-id="3b325-200">Hozzon létre kimenetet, amely a számlázott összegek összegzése lesz a jelentésben szereplő összes blokk esetében.</span><span class="sxs-lookup"><span data-stu-id="3b325-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="3b325-201">A Képlet mezőben adja meg a következőt: „Számlázott összeg összegzése:” és TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))”.</span><span class="sxs-lookup"><span data-stu-id="3b325-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="3b325-202">„Számlázott összeg összegzése:” és TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="3b325-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="3b325-203">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-203">Click Save.</span></span>
76. <span data-ttu-id="3b325-204">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3b325-204">Close the page.</span></span>
77. <span data-ttu-id="3b325-205">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3b325-205">Click Save.</span></span>
78. <span data-ttu-id="3b325-206">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3b325-206">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]