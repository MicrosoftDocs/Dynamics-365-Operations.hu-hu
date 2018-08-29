--- 
title: "Modell-leképezési konfigurációk használata összesítő számítások létrehozásához az adatbázis szintjén"
description: "A folyamat révén új, elektronikus jelentésen (ER) alapuló modell-leképezési konfigurációt tervezhet meg, és a beépített ER-funkciók segítségével hatékony összesített számításokat végezhet."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: a462a3997644a494b5cea89c9530ddba67c32450
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a><span data-ttu-id="431fa-103">Modell-leképezési konfigurációk használata összesítő számítások létrehozásához az adatbázis szintjén</span><span class="sxs-lookup"><span data-stu-id="431fa-103">Use model mapping configurations for aggregate calculations at the database level</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="431fa-104">A folyamat révén új, elektronikus jelentésen (ER) alapuló modell-leképezési konfigurációt tervezhet meg, és a beépített ER-funkciók segítségével hatékony összesített számításokat végezhet.</span><span class="sxs-lookup"><span data-stu-id="431fa-104">This procedure provides information about how to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="431fa-105">Ebben a folyamatban egy konfigurációt hoz létre a Litware, Inc. példavállalatra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="431fa-105">In this procedure you will create a configuration for the sample company, Litware, Inc.</span></span> 

<span data-ttu-id="431fa-106">Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült.</span><span class="sxs-lookup"><span data-stu-id="431fa-106">This procedure is created for users with the assigned role of System administrator or Electronic reporting developer.</span></span> <span data-ttu-id="431fa-107">Ezek a lépések bármely adathalmazzal végrehajthatók.</span><span class="sxs-lookup"><span data-stu-id="431fa-107">These steps can be completed using any dataset.</span></span>

 <span data-ttu-id="431fa-108">A jelenlegi lépések végrehajtásához előbb „Az ER javítja az aggregált számítások hatékonyságát ezek adatbázis szintjén történő végrehajtásával (1. rész: Konfigurációk előkészítése)” folyamat lépéseit kell végrehajtania.</span><span class="sxs-lookup"><span data-stu-id="431fa-108">To complete these steps, you must first complete the steps in the procedure, “ER improves the efficiency of aggregate calculations by performing them on database level (Part 1: Prepare configurations).”</span></span>

1. <span data-ttu-id="431fa-109">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="431fa-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="431fa-110">A fastruktúrában bontsa ki az „Instrastat modell” elemet.</span><span class="sxs-lookup"><span data-stu-id="431fa-110">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="431fa-111">A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat sample mapping”.</span><span class="sxs-lookup"><span data-stu-id="431fa-111">In the tree, select 'Intrastat model\Intrastat sample mapping'.</span></span>
4. <span data-ttu-id="431fa-112">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="431fa-112">Click Designer.</span></span>
5. <span data-ttu-id="431fa-113">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="431fa-113">Click Designer.</span></span>
6. <span data-ttu-id="431fa-114">A fán válassza ki a „Dynamics 365 for Operations\Table records” pontot.</span><span class="sxs-lookup"><span data-stu-id="431fa-114">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
7. <span data-ttu-id="431fa-115">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-115">Click Add root.</span></span>
    * <span data-ttu-id="431fa-116">Adja hozzá a csoportosítani kívánt rekordokat jelző új adatforrást.</span><span class="sxs-lookup"><span data-stu-id="431fa-116">Add a new data source representing records you want to group.</span></span>  
8. <span data-ttu-id="431fa-117">A Név mezőbe írja be a „Transactions” szöveget.</span><span class="sxs-lookup"><span data-stu-id="431fa-117">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="431fa-118">Tranzakciók</span><span class="sxs-lookup"><span data-stu-id="431fa-118">Transactions</span></span>  
9. <span data-ttu-id="431fa-119">Írja be a Tábla mezőbe az „Intrastat” szöveget.</span><span class="sxs-lookup"><span data-stu-id="431fa-119">In the Table field, type 'Intrastat'.</span></span>
    * <span data-ttu-id="431fa-120">Intrastat</span><span class="sxs-lookup"><span data-stu-id="431fa-120">Intrastat</span></span>  
10. <span data-ttu-id="431fa-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-121">Click OK.</span></span>
11. <span data-ttu-id="431fa-122">A fastruktúrában válassza ki a „Funkciók\Csoportosítás alapja ” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-122">In the tree, select 'Functions\Group by'.</span></span>
    * <span data-ttu-id="431fa-123">Ezen adatforrástípussal futásidőben vezethet be új adatforrásokat a rekordok csoportosításához és szükséges aggregációk kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="431fa-123">This data source type is used to introduce a new data source at run-time to group records and to calculate required aggregations.</span></span>  
12. <span data-ttu-id="431fa-124">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-124">Click Add root.</span></span>
13. <span data-ttu-id="431fa-125">A Név mezőbe írja be „TransactionsGroups” szöveget.</span><span class="sxs-lookup"><span data-stu-id="431fa-125">In the Name field, type 'TransactionsGroups'.</span></span>
    * <span data-ttu-id="431fa-126">TranzakcióCsoportok</span><span class="sxs-lookup"><span data-stu-id="431fa-126">TransactionsGroups</span></span>  
14. <span data-ttu-id="431fa-127">Kattintson a Csoport szerkesztési szempontja lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-127">Click Edit group by.</span></span>
15. <span data-ttu-id="431fa-128">A fastruktúrában válassza ki a Tranzakciók pontot.</span><span class="sxs-lookup"><span data-stu-id="431fa-128">In the tree, select 'Transactions'.</span></span>
    * <span data-ttu-id="431fa-129">Válassza ki azt a hozzáadott adatforrást a „Rekordlista” típusban, amely a csoportosításához használni kívánt rekordjait képviseli.</span><span class="sxs-lookup"><span data-stu-id="431fa-129">Select the added data source of the ‘Record list’ type that represents the records that you want to group.</span></span>  
16. <span data-ttu-id="431fa-130">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-130">Click Add field to.</span></span>
17. <span data-ttu-id="431fa-131">Kattintson a Csoportosítandó lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-131">Click What to group.</span></span>
18. <span data-ttu-id="431fa-132">A fában bontsa ki a Tranzakciók csomópontot.</span><span class="sxs-lookup"><span data-stu-id="431fa-132">In the tree, expand 'Transactions'.</span></span>
19. <span data-ttu-id="431fa-133">A fastruktúrában válassza ki a „Transactions\Direction” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-133">In the tree, select 'Transactions\Direction'.</span></span>
20. <span data-ttu-id="431fa-134">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-134">Click Add field to.</span></span>
21. <span data-ttu-id="431fa-135">Kattintson a Csoportosított mezők lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-135">Click Grouped fields.</span></span>
    * <span data-ttu-id="431fa-136">Jelölje ki a mezőt a csoportosítási szint megadásához.</span><span class="sxs-lookup"><span data-stu-id="431fa-136">Select the field to specify the grouping level.</span></span> <span data-ttu-id="431fa-137">A kiválasztás alapján az adatforrás futásidejében annyi tranzakciócsoport jelenik meg, ahány iránykód érvényesül az Intrastat-táblában.</span><span class="sxs-lookup"><span data-stu-id="431fa-137">Based on this selection, the data source will return at run-time as many groups of transactions as there are direction codes that will be met in the Intrastat table.</span></span>  
22. <span data-ttu-id="431fa-138">A fán jelölje be a „Tranzakciók\Számla összege(AmountMST)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-138">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
    * <span data-ttu-id="431fa-139">Válassza ki a mezőt az aggregációs számítás forrásának megadásához.</span><span class="sxs-lookup"><span data-stu-id="431fa-139">Select the field to specify the source for aggregation calculation.</span></span>  
23. <span data-ttu-id="431fa-140">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-140">Click Add field to.</span></span>
24. <span data-ttu-id="431fa-141">Kattintson az Aggregációs mezők lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-141">Click Aggregation fields.</span></span>
25. <span data-ttu-id="431fa-142">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="431fa-142">In the list, mark the selected row.</span></span>
26. <span data-ttu-id="431fa-143">A Módszer mezőben válassza az „Összeg” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-143">In the Method field, select 'Sum'.</span></span>
    * <span data-ttu-id="431fa-144">Itt adhatja meg az aggregáció típusát.</span><span class="sxs-lookup"><span data-stu-id="431fa-144">Select the aggregation type.</span></span>  
27. <span data-ttu-id="431fa-145">A Név mezőbe írja be a SumOfAmountMSTn szöveget.</span><span class="sxs-lookup"><span data-stu-id="431fa-145">In the Name field, type 'SumOfAmountMST'.</span></span>
    * <span data-ttu-id="431fa-146">Adja meg az aggregáció nevét a konfigurált adatforrásban.</span><span class="sxs-lookup"><span data-stu-id="431fa-146">Specify the name of this aggregation in the configured data source.</span></span>  
28. <span data-ttu-id="431fa-147">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-147">Click Save.</span></span>
    * <span data-ttu-id="431fa-148">Vegye figyelembe, hogy a Végrehajtás helye mező mutatja, hogy a csoportosítás futásidőben történik az SQL-adatbázisban.</span><span class="sxs-lookup"><span data-stu-id="431fa-148">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in the SQL database.</span></span>  
29. <span data-ttu-id="431fa-149">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="431fa-149">Close the page.</span></span>
30. <span data-ttu-id="431fa-150">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-150">Click OK.</span></span>
31. <span data-ttu-id="431fa-151">A fastruktúrában bontsa ki az Összegek pontot.</span><span class="sxs-lookup"><span data-stu-id="431fa-151">In the tree, expand 'Totals'.</span></span>
32. <span data-ttu-id="431fa-152">A fában bontsa ki a TransactionsGroups elemet.</span><span class="sxs-lookup"><span data-stu-id="431fa-152">In the tree, expand 'TransactionsGroups'.</span></span>
33. <span data-ttu-id="431fa-153">A fában bontsa ki a „TransactionsGroups\aggregated” elemet.</span><span class="sxs-lookup"><span data-stu-id="431fa-153">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
34. <span data-ttu-id="431fa-154">A fán jelölje be a „TransactionsGroups\aggregated\SumOfAmountMST” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-154">In the tree, select 'TransactionsGroups\aggregated\SumOfAmountMST'.</span></span>
35. <span data-ttu-id="431fa-155">A fán jelölje be az „Összegek\Teljes számlaérték(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-155">In the tree, select 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.</span></span>
36. <span data-ttu-id="431fa-156">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-156">Click Bind.</span></span>
    * <span data-ttu-id="431fa-157">Ezen beállítás alapján ez az adatforrás kiszámítja az AmountMST mező minden egyes tranzakciócsoportjának összértékét.</span><span class="sxs-lookup"><span data-stu-id="431fa-157">Based on this setting, this data source will calculate the sum of values of the ‘AmountMST’ field for each groups of transactions.</span></span> <span data-ttu-id="431fa-158">Ez az aggregált számítás a TransactionsGroups.aggregated.TotalAmount cikként érhető el.</span><span class="sxs-lookup"><span data-stu-id="431fa-158">This aggregation calculation will be available as TransactionsGroups.aggregated.TotalAmount item.</span></span>  
37. <span data-ttu-id="431fa-159">A fában bontsa ki a TransactionsGroups elemet.</span><span class="sxs-lookup"><span data-stu-id="431fa-159">In the tree, expand 'TransactionsGroups'.</span></span>
38. <span data-ttu-id="431fa-160">A fastruktúrában válassza ki a TransactionsGroups lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-160">In the tree, select 'TransactionsGroups'.</span></span>
39. <span data-ttu-id="431fa-161">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-161">Click Edit.</span></span>
40. <span data-ttu-id="431fa-162">Kattintson a Csoport szerkesztési szempontja lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-162">Click Edit group by.</span></span>
41. <span data-ttu-id="431fa-163">A fában bontsa ki a Tranzakciók csomópontot.</span><span class="sxs-lookup"><span data-stu-id="431fa-163">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="431fa-164">A fán jelölje be a „Tranzakciók\Számla összege(AmountMST)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-164">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
43. <span data-ttu-id="431fa-165">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-165">Click Add field to.</span></span>
44. <span data-ttu-id="431fa-166">Kattintson az Aggregációs mezők lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-166">Click Aggregation fields.</span></span>
45. <span data-ttu-id="431fa-167">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="431fa-167">In the list, mark the selected row.</span></span>
46. <span data-ttu-id="431fa-168">A Módszer mezőben válassza a „Max” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-168">In the Method field, select 'Max'.</span></span>
47. <span data-ttu-id="431fa-169">A Név mezőbe írja be a MaxOfAmountMST szöveget.</span><span class="sxs-lookup"><span data-stu-id="431fa-169">In the Name field, type 'MaxOfAmountMST'.</span></span>
48. <span data-ttu-id="431fa-170">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-170">Click Save.</span></span>
    * <span data-ttu-id="431fa-171">Jelenleg a GROUPBY adatforrások végrehajtását bizonyos korlátozásokkal át lehet számítani az SQL-adatbázis szintjére.</span><span class="sxs-lookup"><span data-stu-id="431fa-171">Currently, the execution of GROUPBY data sources can be translated to the SQL database level with some limitations.</span></span> <span data-ttu-id="431fa-172">Az átszámítást a Rekordlista típus adatforrásai számára kifejezésként megjelenő adatforrásokra végezheti a SZŰRŐ funkció használatával.</span><span class="sxs-lookup"><span data-stu-id="431fa-172">Translation can be done for either data sources of the ‘Record list’ type or data sources represented as an expression using the FILTER function.</span></span> <span data-ttu-id="431fa-173">Ez akkor is megtehető, ha az egyetlen aggregáció a csoportosítási rekordok egyetlen mezőjére van konfigurálva.</span><span class="sxs-lookup"><span data-stu-id="431fa-173">It can also be done when the only one aggregation is configured for a single field of the grouping records.</span></span>  
    * <span data-ttu-id="431fa-174">Vegye figyelembe, hogy annak ellenére, hogy az AmountMST mezőben egynél több aggregáció lett beállítva, a Végrehajtás helye mező továbbra is jelzi, hogy a csoportosítást futásidőben történik az SQL-adatbázisban.</span><span class="sxs-lookup"><span data-stu-id="431fa-174">Note that even though more than one aggregation was configured for the AmountMST field, the ‘Execution at’ field still indicates that this grouping will be performed at run-time in the SQL database.</span></span> <span data-ttu-id="431fa-175">Ennek oka, hogy csak egy aggregáció kötődik az adatmodellcikkhez, és futásidőben használják az adatforrás adatainak lekérésére.</span><span class="sxs-lookup"><span data-stu-id="431fa-175">This is because only one aggregation is bound to the data model item and will be used at run-time to pull data from this data source.</span></span>  
49. <span data-ttu-id="431fa-176">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="431fa-176">Close the page.</span></span>
50. <span data-ttu-id="431fa-177">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-177">Click OK.</span></span>
51. <span data-ttu-id="431fa-178">A fában bontsa ki a TransactionsGroups elemet.</span><span class="sxs-lookup"><span data-stu-id="431fa-178">In the tree, expand 'TransactionsGroups'.</span></span>
52. <span data-ttu-id="431fa-179">A fában bontsa ki a „TransactionsGroups\aggregated” elemet.</span><span class="sxs-lookup"><span data-stu-id="431fa-179">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
53. <span data-ttu-id="431fa-180">A fán jelölje be a „TransactionsGroups\aggregated\MaxOfAmountMST” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-180">In the tree, select 'TransactionsGroups\aggregated\MaxOfAmountMST'.</span></span>
54. <span data-ttu-id="431fa-181">A fán jelölje be az „Összegek\Teljes statisztikai érték(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-181">In the tree, select 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.</span></span>
55. <span data-ttu-id="431fa-182">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-182">Click Bind.</span></span>
56. <span data-ttu-id="431fa-183">A fában bontsa ki a TransactionsGroups elemet.</span><span class="sxs-lookup"><span data-stu-id="431fa-183">In the tree, expand 'TransactionsGroups'.</span></span>
57. <span data-ttu-id="431fa-184">A fastruktúrában válassza ki a TransactionsGroups lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="431fa-184">In the tree, select 'TransactionsGroups'.</span></span>
58. <span data-ttu-id="431fa-185">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-185">Click Edit.</span></span>
59. <span data-ttu-id="431fa-186">Kattintson a Csoport szerkesztési szempontja lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-186">Click Edit group by.</span></span>
    * <span data-ttu-id="431fa-187">Vegye figyelembe, hogy a Végrehajtás helye mező azt jelzi, hogy a csoportosításra a memória futásidőben kerül sor, mivel ugyanazon mező mindkét aggregációja az adatmodellcikkekhez kötődik.</span><span class="sxs-lookup"><span data-stu-id="431fa-187">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in memory because both aggregations of the same field are bound to the data model items.</span></span>   
60. <span data-ttu-id="431fa-188">A listában jelölje meg az összes sort, vagy törölje a jelölésüket.</span><span class="sxs-lookup"><span data-stu-id="431fa-188">In the list, mark or unmark all rows.</span></span>
61. <span data-ttu-id="431fa-189">Kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-189">Click Delete.</span></span>
62. <span data-ttu-id="431fa-190">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-190">Click Yes.</span></span>
63. <span data-ttu-id="431fa-191">Kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-191">Click Delete.</span></span>
64. <span data-ttu-id="431fa-192">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-192">Click Yes.</span></span>
65. <span data-ttu-id="431fa-193">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-193">Click Add field to.</span></span>
66. <span data-ttu-id="431fa-194">Kattintson a Csoportosítandó lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="431fa-194">Click What to group.</span></span>
67. <span data-ttu-id="431fa-195">A fastruktúrában bontsa ki az Árucikkrekord(Instrastat) elemet.</span><span class="sxs-lookup"><span data-stu-id="431fa-195">In the tree, expand 'Commodity record(Intrastat)'.</span></span>
68. <span data-ttu-id="431fa-196">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="431fa-196">Click Save.</span></span>
    * <span data-ttu-id="431fa-197">Vegye figyelembe, hogy a Végrehajtás helye mező azt mutatja, hogy a csoportosításra a memória futásidőben kerül sor annak ellenére, hogy nincsenek definiálva aggregációk, és a Tábla rekordjai típus az Intrastat tábla megfelelő értékeire vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="431fa-197">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in memory even though there are no aggregations defined and the selected data source of ‘Table records’ type refers to the same ‘Intrastat’ table.</span></span> <span data-ttu-id="431fa-198">Ennek oka az, hogy az adatforrás tartalmaz néhány olyan számított mezőt, amelyeket még nem lehet átszámítani az SQL-adatbázis szintjére.</span><span class="sxs-lookup"><span data-stu-id="431fa-198">This is because the data source contains some calculated fields which can’t yet be translated to the SQL database level.</span></span>  


