---
title: ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész – Számlálások használata a kimenet elkészítéséhez)
description: Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fbdff413edf942b99e11412902abb7589a754c2d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182370"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3-use-computations-to-make-the-output"></a><span data-ttu-id="b81aa-103">ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész: Számlálások használata a kimenet elkészítéséhez)</span><span class="sxs-lookup"><span data-stu-id="b81aa-103">ER Configure format to do counting and summing (Part 3: Use computations to make the output)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b81aa-104">Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján.</span><span class="sxs-lookup"><span data-stu-id="b81aa-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="b81aa-105">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="b81aa-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="b81aa-106">A lépések végrehajtásához először végre kell hajtania az „ER Számláláshoz és összegzéshez használt formátum konfigurálása (2. rész: Számlálások konfigurálása)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="b81aa-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 2: Configure computations)” procedure.</span></span>

<span data-ttu-id="b81aa-107">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="b81aa-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="b81aa-108">A jelentéssel konfigurálása a számlálási és összegzési információk konfigurálásához</span><span class="sxs-lookup"><span data-stu-id="b81aa-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="b81aa-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b81aa-110">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="b81aa-111">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="b81aa-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="b81aa-112">A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="b81aa-113">A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="b81aa-114">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-114">Click Designer.</span></span>
7. <span data-ttu-id="b81aa-115">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="b81aa-116">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b81aa-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="b81aa-117">Adjon hozzá újra adatforrást a memorizált blokkok listájának lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="b81aa-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="b81aa-118">A fán válassza ki a „Functions\Calculated mező” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b81aa-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="b81aa-119">A Név mezőbe írja be a következőt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="b81aa-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="b81aa-120">$BlocksList</span></span>  
11. <span data-ttu-id="b81aa-121">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-121">Click Edit formula.</span></span>
12. <span data-ttu-id="b81aa-122">A fastruktúrában válassza ki a következőt: „Adatgyűjtési függvények\COLLECTEDLIST”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="b81aa-123">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-123">Click Add function.</span></span>
14. <span data-ttu-id="b81aa-124">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-124">Click Add data source.</span></span>
15. <span data-ttu-id="b81aa-125">A Képlet mezőbe írja be a következőt: „COLLECTEDLIST('$BlockName', ”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="b81aa-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="b81aa-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="b81aa-127">A Képlet mezőbe írja be a következőt: „COLLECTEDLIST('$BlockName', "\*")”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="b81aa-128">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="b81aa-128">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="b81aa-129">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-129">Click Save.</span></span>
    * <span data-ttu-id="b81aa-130">A „\*” minta azt jelenti, hogy minden blokk szerepelni fog a rekord listáján.</span><span class="sxs-lookup"><span data-stu-id="b81aa-130">The pattern “\*” means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="b81aa-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b81aa-131">Close the page.</span></span>
19. <span data-ttu-id="b81aa-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-132">Click OK.</span></span>
20. <span data-ttu-id="b81aa-133">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-133">Click the Format tab.</span></span>
21. <span data-ttu-id="b81aa-134">Válassza ki az „Intrastat\Adat” lehetőséget a fastruktúrában.</span><span class="sxs-lookup"><span data-stu-id="b81aa-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="b81aa-135">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b81aa-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="b81aa-136">A fastruktúrában válassza ki ezt: „Szöveg\Sorozat”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="b81aa-137">A Név mezőbe írja be a „Összegek blokkok szerint” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b81aa-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="b81aa-138">Összegek blokkok szerint</span><span class="sxs-lookup"><span data-stu-id="b81aa-138">Totals by blocks</span></span>  
25. <span data-ttu-id="b81aa-139">A Különleges karakterek mezőben válassza ki az „Új sor – Windows (CR LF)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b81aa-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="b81aa-140">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-140">Click OK.</span></span>
27. <span data-ttu-id="b81aa-141">A fastruktúrában bontsa ki az „Instrastat\Adat\Összegek blokkok szerint” elemet.</span><span class="sxs-lookup"><span data-stu-id="b81aa-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="b81aa-142">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b81aa-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="b81aa-143">A fában válassza ki ezt: „Text\String”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="b81aa-144">A Név mezőbe írja be a „Blokk kód” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b81aa-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="b81aa-145">Blokk kód</span><span class="sxs-lookup"><span data-stu-id="b81aa-145">Block code</span></span>  
31. <span data-ttu-id="b81aa-146">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-146">Click OK.</span></span>
32. <span data-ttu-id="b81aa-147">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-147">Click Add String.</span></span>
33. <span data-ttu-id="b81aa-148">A Név mezőbe írja be a „Sorszámlálás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b81aa-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="b81aa-149">Sorszámlálás</span><span class="sxs-lookup"><span data-stu-id="b81aa-149">Lines counting</span></span>  
34. <span data-ttu-id="b81aa-150">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-150">Click OK.</span></span>
35. <span data-ttu-id="b81aa-151">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-151">Click Add String.</span></span>
36. <span data-ttu-id="b81aa-152">A Név mezőbe írja be a „Teljes összeg” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b81aa-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="b81aa-153">Teljes összeg</span><span class="sxs-lookup"><span data-stu-id="b81aa-153">Total amount</span></span>  
37. <span data-ttu-id="b81aa-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-154">Click OK.</span></span>
38. <span data-ttu-id="b81aa-155">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="b81aa-156">A fastruktúrában válassza ki ezt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="b81aa-157">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-157">Click Bind.</span></span>
    * <span data-ttu-id="b81aa-158">Hozzon létre összegző sort minden memorizált blokkhoz.</span><span class="sxs-lookup"><span data-stu-id="b81aa-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="b81aa-159">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-159">Click the Format tab.</span></span>
42. <span data-ttu-id="b81aa-160">A fastruktúrában válassza ki az „Instrastat\Adat\Összegek blokkok szerint\Blokk kód” elemet.</span><span class="sxs-lookup"><span data-stu-id="b81aa-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="b81aa-161">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="b81aa-162">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-162">Click Edit formula.</span></span>
45. <span data-ttu-id="b81aa-163">A Képlet mezőbe írja be a következőt: „„Blokkazonosító:” és ”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="b81aa-164">„Blokk azonosítója:” és</span><span class="sxs-lookup"><span data-stu-id="b81aa-164">"Block id: " &</span></span>  
46. <span data-ttu-id="b81aa-165">A fastruktúrában bontsa ki ezt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="b81aa-166">A fastruktúrában válassza ki a következőt: „$BlocksList\Érték”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="b81aa-167">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-167">Click Add data source.</span></span>
49. <span data-ttu-id="b81aa-168">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-168">Click Save.</span></span>
50. <span data-ttu-id="b81aa-169">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b81aa-169">Close the page.</span></span>
51. <span data-ttu-id="b81aa-170">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-170">Click the Format tab.</span></span>
52. <span data-ttu-id="b81aa-171">A fastruktúrában válassza ki a következőt: „Instrastat\Adat\Összegek blokkok szerint\Sorszámlálás”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="b81aa-172">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="b81aa-173">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-173">Click Edit formula.</span></span>
    * <span data-ttu-id="b81aa-174">Hozzon létre kimenetet a jelentésben szereplő minden egyes blokk sorainak számához.</span><span class="sxs-lookup"><span data-stu-id="b81aa-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="b81aa-175">A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és ”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="b81aa-176">„Sorok száma ebben a blokkban:” és</span><span class="sxs-lookup"><span data-stu-id="b81aa-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="b81aa-177">A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT ”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="b81aa-178">„Sorok száma ebben a blokkban:” és TEXT(</span><span class="sxs-lookup"><span data-stu-id="b81aa-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="b81aa-179">A fastruktúrában válassza ki a következőt: „Adatgyűjtési függvények\COUNTIFS”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="b81aa-180">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-180">Click Add function.</span></span>
59. <span data-ttu-id="b81aa-181">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-181">Click Add data source.</span></span>
60. <span data-ttu-id="b81aa-182">A képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', ".</span><span class="sxs-lookup"><span data-stu-id="b81aa-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="b81aa-183">„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="b81aa-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="b81aa-184">A fastruktúrában bontsa ki ezt: „$BlocksList”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="b81aa-185">A fastruktúrában válassza ki a következőt: „$BlocksList\Érték”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="b81aa-186">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-186">Click Add data source.</span></span>
64. <span data-ttu-id="b81aa-187">A képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, ".</span><span class="sxs-lookup"><span data-stu-id="b81aa-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="b81aa-188">„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="b81aa-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="b81aa-189">A fastruktúrában válassza ki a következőt: „$RecName”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="b81aa-190">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-190">Click Add data source.</span></span>
67. <span data-ttu-id="b81aa-191">A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="b81aa-192">„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="b81aa-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="b81aa-193">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-193">Click Save.</span></span>
69. <span data-ttu-id="b81aa-194">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b81aa-194">Close the page.</span></span>
70. <span data-ttu-id="b81aa-195">Kattintson a Formátum fülre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-195">Click the Format tab.</span></span>
71. <span data-ttu-id="b81aa-196">A fastruktúrában válassza ki a következőt: „Instrastat\Adat\Összegek blokkok szerint\Teljes összeg”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="b81aa-197">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="b81aa-198">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b81aa-198">Click Edit formula.</span></span>
    * <span data-ttu-id="b81aa-199">Hozzon létre kimenetet, amely a számlázott összegek összegzése lesz a jelentésben szereplő összes blokk esetében.</span><span class="sxs-lookup"><span data-stu-id="b81aa-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="b81aa-200">A Képlet mezőben adja meg a következőt: „Számlázott összeg összegzése:” és TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))”.</span><span class="sxs-lookup"><span data-stu-id="b81aa-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="b81aa-201">„Számlázott összeg összegzése:” és TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="b81aa-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="b81aa-202">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-202">Click Save.</span></span>
76. <span data-ttu-id="b81aa-203">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b81aa-203">Close the page.</span></span>
77. <span data-ttu-id="b81aa-204">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b81aa-204">Click Save.</span></span>
78. <span data-ttu-id="b81aa-205">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b81aa-205">Close the page.</span></span>

