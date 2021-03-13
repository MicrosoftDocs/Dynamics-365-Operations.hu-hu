---
title: ER Pénzügyi dimenziók használata adatforrásként (3. rész – A jelentés megtervezése)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentési (ER) modellt, amely a pénzügyi dimenziókat használja az ER-jelentések adatforrásaként. (3. rész)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0d6da96850e04d5e975b3febbfae2737c8a86af
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092300"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="47d26-104">ER Pénzügyi dimenziók használata adatforrásként (3. rész – A jelentés megtervezése)</span><span class="sxs-lookup"><span data-stu-id="47d26-104">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="47d26-105">A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="47d26-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="47d26-106">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="47d26-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="47d26-107">A lépések végrehajtásához először hajtsa végre az „ER Pénzügyi dimenziók használata adatforrásként (2. rész: Modell leképezése)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="47d26-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="47d26-108">Tervezzen jelentést a pénzügyi dimenziók megjelenítésére</span><span class="sxs-lookup"><span data-stu-id="47d26-108">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="47d26-109">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="47d26-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="47d26-110">A fastruktúrában válassza a „Pénzügyi dimenziók mintamodell” szöveget.</span><span class="sxs-lookup"><span data-stu-id="47d26-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="47d26-111">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="47d26-111">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="47d26-112">Az Új mezőbe írja be a „ Pénzügyi dimenziók mintamodell adatmodellen alapuló formátum” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="47d26-112">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="47d26-113">Annak a modellnek a használata, amelyet már előre létrehoztak az új jelentés adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="47d26-113">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="47d26-114">A Név mezőbe írja be a „Főkönyvi naplójelentés” szöveget.</span><span class="sxs-lookup"><span data-stu-id="47d26-114">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="47d26-115">Az Adatmodell definíciója mezőben válassza a Bejegyzés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="47d26-115">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="47d26-116">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47d26-116">Click Create configuration.</span></span>
8. <span data-ttu-id="47d26-117">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="47d26-117">Click Designer.</span></span>
9. <span data-ttu-id="47d26-118">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="47d26-118">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="47d26-119">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="47d26-119">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="47d26-120">A Név mezőbe írja be a következőt: „Gyökér”.</span><span class="sxs-lookup"><span data-stu-id="47d26-120">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="47d26-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-121">Click OK.</span></span>
13. <span data-ttu-id="47d26-122">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="47d26-122">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="47d26-123">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="47d26-123">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="47d26-124">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="47d26-124">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="47d26-125">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-125">Click OK.</span></span>
17. <span data-ttu-id="47d26-126">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="47d26-126">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="47d26-127">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="47d26-127">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="47d26-128">A Név mezőbe írja be a következőt: „Napló”.</span><span class="sxs-lookup"><span data-stu-id="47d26-128">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="47d26-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-129">Click OK.</span></span>
21. <span data-ttu-id="47d26-130">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="47d26-130">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="47d26-131">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="47d26-131">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="47d26-132">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="47d26-132">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="47d26-133">A Név mezőbe írja be a következőt: „Köteg”.</span><span class="sxs-lookup"><span data-stu-id="47d26-133">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="47d26-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-134">Click OK.</span></span>
26. <span data-ttu-id="47d26-135">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="47d26-135">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="47d26-136">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="47d26-136">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="47d26-137">A Név mezőbe írja be a „Tranzakció” szöveget.</span><span class="sxs-lookup"><span data-stu-id="47d26-137">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="47d26-138">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-138">Click OK.</span></span>
30. <span data-ttu-id="47d26-139">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="47d26-139">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="47d26-140">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="47d26-140">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="47d26-141">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="47d26-141">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="47d26-142">A Név mezőbe írja be a következőt: „Bizonylat”.</span><span class="sxs-lookup"><span data-stu-id="47d26-142">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="47d26-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-143">Click OK.</span></span>
35. <span data-ttu-id="47d26-144">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47d26-144">Click Add Attribute.</span></span>
36. <span data-ttu-id="47d26-145">A Név mezőbe írja be a következőt: „Dátum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-145">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="47d26-146">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-146">Click OK.</span></span>
38. <span data-ttu-id="47d26-147">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47d26-147">Click Add Attribute.</span></span>
39. <span data-ttu-id="47d26-148">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="47d26-148">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="47d26-149">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-149">Click OK.</span></span>
41. <span data-ttu-id="47d26-150">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47d26-150">Click Add Attribute.</span></span>
42. <span data-ttu-id="47d26-151">A Név mezőbe írja be a következőt: „Dt”.</span><span class="sxs-lookup"><span data-stu-id="47d26-151">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="47d26-152">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-152">Click OK.</span></span>
44. <span data-ttu-id="47d26-153">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47d26-153">Click Add Attribute.</span></span>
45. <span data-ttu-id="47d26-154">A Név mezőbe írja be a következőt: „Ct”.</span><span class="sxs-lookup"><span data-stu-id="47d26-154">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="47d26-155">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-155">Click OK.</span></span>
47. <span data-ttu-id="47d26-156">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="47d26-156">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="47d26-157">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="47d26-157">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="47d26-158">A Név mezőbe írja be a következőt: „Dimenziók”.</span><span class="sxs-lookup"><span data-stu-id="47d26-158">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="47d26-159">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-159">Click OK.</span></span>
51. <span data-ttu-id="47d26-160">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="47d26-160">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="47d26-161">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="47d26-161">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="47d26-162">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="47d26-162">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="47d26-163">A Név mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="47d26-163">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="47d26-164">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-164">Click OK.</span></span>
56. <span data-ttu-id="47d26-165">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47d26-165">Click Add Attribute.</span></span>
57. <span data-ttu-id="47d26-166">A Név mezőbe írja be a következőt: „Érték”.</span><span class="sxs-lookup"><span data-stu-id="47d26-166">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="47d26-167">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-167">Click OK.</span></span>
59. <span data-ttu-id="47d26-168">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="47d26-168">Click Add Attribute.</span></span>
60. <span data-ttu-id="47d26-169">A Név mezőbe írja be a következőt: „Leír.”.</span><span class="sxs-lookup"><span data-stu-id="47d26-169">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="47d26-170">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-170">Click OK.</span></span>
<span data-ttu-id="47d26-171">![ER-művelettervező oldal](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="47d26-171">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="47d26-172">Rendelje hozzá a jelentés elemeit az adatforrásokhoz</span><span class="sxs-lookup"><span data-stu-id="47d26-172">Map report elements to data sources</span></span>
1. <span data-ttu-id="47d26-173">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="47d26-173">Click the Mapping tab.</span></span>
2. <span data-ttu-id="47d26-174">A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell”.</span><span class="sxs-lookup"><span data-stu-id="47d26-174">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="47d26-175">A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="47d26-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="47d26-176">A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="47d26-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="47d26-177">A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="47d26-177">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="47d26-178">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem\Leír.: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-178">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="47d26-179">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista\Leírás: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="47d26-179">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="47d26-180">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-180">Click Bind.</span></span>
9. <span data-ttu-id="47d26-181">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem\Érték: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-181">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="47d26-182">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista\Kód: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="47d26-182">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="47d26-183">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-183">Click Bind.</span></span>
12. <span data-ttu-id="47d26-184">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem\Kód: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-184">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="47d26-185">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista\Név: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="47d26-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="47d26-186">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-186">Click Bind.</span></span>
15. <span data-ttu-id="47d26-187">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="47d26-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="47d26-188">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="47d26-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="47d26-189">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-189">Click Bind.</span></span>
18. <span data-ttu-id="47d26-190">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Ct: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-190">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="47d26-191">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Követel: Valós”.</span><span class="sxs-lookup"><span data-stu-id="47d26-191">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="47d26-192">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-192">Click Bind.</span></span>
21. <span data-ttu-id="47d26-193">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dt: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-193">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="47d26-194">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Tartozik: Valós”.</span><span class="sxs-lookup"><span data-stu-id="47d26-194">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="47d26-195">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-195">Click Bind.</span></span>
24. <span data-ttu-id="47d26-196">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Pénznem: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-196">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="47d26-197">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Pénznem: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="47d26-197">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="47d26-198">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-198">Click Bind.</span></span>
27. <span data-ttu-id="47d26-199">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dátum: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-199">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="47d26-200">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dátum: Dátum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-200">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="47d26-201">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-201">Click Bind.</span></span>
30. <span data-ttu-id="47d26-202">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Bizonylat: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-202">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="47d26-203">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Bizonylat: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="47d26-203">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="47d26-204">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-204">Click Bind.</span></span>
33. <span data-ttu-id="47d26-205">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="47d26-205">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="47d26-206">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="47d26-206">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="47d26-207">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-207">Click Bind.</span></span>
36. <span data-ttu-id="47d26-208">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Köteg: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-208">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="47d26-209">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Köteg: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="47d26-209">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="47d26-210">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-210">Click Bind.</span></span>
39. <span data-ttu-id="47d26-211">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="47d26-211">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="47d26-212">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="47d26-212">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="47d26-213">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-213">Click Bind.</span></span>
42. <span data-ttu-id="47d26-214">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Vállalat: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="47d26-214">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="47d26-215">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Vállalat: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="47d26-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="47d26-216">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-216">Click Bind.</span></span>
45. <span data-ttu-id="47d26-217">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="47d26-217">Click Save.</span></span>
46. <span data-ttu-id="47d26-218">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="47d26-218">Close the page.</span></span>
<span data-ttu-id="47d26-219">![ER-művelettervező oldal](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="47d26-219">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>

