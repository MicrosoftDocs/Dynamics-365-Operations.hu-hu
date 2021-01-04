---
title: ER Pénzügyi dimenziók használata adatforrásként (3. rész – A jelentés megtervezése)
description: A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.
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
ms.openlocfilehash: a12f88f1e8b5e451bc8a5c5486d820da61bf3ad0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684787"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="97a54-103">ER Pénzügyi dimenziók használata adatforrásként (3. rész – A jelentés megtervezése)</span><span class="sxs-lookup"><span data-stu-id="97a54-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="97a54-104">A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="97a54-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="97a54-105">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="97a54-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="97a54-106">A lépések végrehajtásához először hajtsa végre az „ER Pénzügyi dimenziók használata adatforrásként (2. rész: Modell leképezése)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="97a54-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="97a54-107">Tervezzen jelentést a pénzügyi dimenziók megjelenítésére</span><span class="sxs-lookup"><span data-stu-id="97a54-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="97a54-108">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="97a54-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="97a54-109">A fastruktúrában válassza a „Pénzügyi dimenziók mintamodell” szöveget.</span><span class="sxs-lookup"><span data-stu-id="97a54-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="97a54-110">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="97a54-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="97a54-111">Az Új mezőbe írja be a „ Pénzügyi dimenziók mintamodell adatmodellen alapuló formátum” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="97a54-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="97a54-112">Annak a modellnek a használata, amelyet már előre létrehoztak az új jelentés adatforrásaként.</span><span class="sxs-lookup"><span data-stu-id="97a54-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="97a54-113">A Név mezőbe írja be a „Főkönyvi naplójelentés” szöveget.</span><span class="sxs-lookup"><span data-stu-id="97a54-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="97a54-114">Az Adatmodell definíciója mezőben válassza a Bejegyzés lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97a54-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="97a54-115">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="97a54-115">Click Create configuration.</span></span>
8. <span data-ttu-id="97a54-116">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="97a54-116">Click Designer.</span></span>
9. <span data-ttu-id="97a54-117">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="97a54-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="97a54-118">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="97a54-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="97a54-119">A Név mezőbe írja be a következőt: „Gyökér”.</span><span class="sxs-lookup"><span data-stu-id="97a54-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="97a54-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-120">Click OK.</span></span>
13. <span data-ttu-id="97a54-121">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="97a54-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="97a54-122">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="97a54-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="97a54-123">A Név mezőbe írja be a Vállalat szót.</span><span class="sxs-lookup"><span data-stu-id="97a54-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="97a54-124">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-124">Click OK.</span></span>
17. <span data-ttu-id="97a54-125">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="97a54-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="97a54-126">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="97a54-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="97a54-127">A Név mezőbe írja be a következőt: „Napló”.</span><span class="sxs-lookup"><span data-stu-id="97a54-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="97a54-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-128">Click OK.</span></span>
21. <span data-ttu-id="97a54-129">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="97a54-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="97a54-130">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="97a54-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="97a54-131">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="97a54-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="97a54-132">A Név mezőbe írja be a következőt: „Köteg”.</span><span class="sxs-lookup"><span data-stu-id="97a54-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="97a54-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-133">Click OK.</span></span>
26. <span data-ttu-id="97a54-134">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="97a54-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="97a54-135">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="97a54-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="97a54-136">A Név mezőbe írja be a „Tranzakció” szöveget.</span><span class="sxs-lookup"><span data-stu-id="97a54-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="97a54-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-137">Click OK.</span></span>
30. <span data-ttu-id="97a54-138">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="97a54-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="97a54-139">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="97a54-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="97a54-140">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="97a54-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="97a54-141">A Név mezőbe írja be a következőt: „Bizonylat”.</span><span class="sxs-lookup"><span data-stu-id="97a54-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="97a54-142">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-142">Click OK.</span></span>
35. <span data-ttu-id="97a54-143">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="97a54-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="97a54-144">A Név mezőbe írja be a következőt: „Dátum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="97a54-145">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-145">Click OK.</span></span>
38. <span data-ttu-id="97a54-146">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="97a54-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="97a54-147">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="97a54-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="97a54-148">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-148">Click OK.</span></span>
41. <span data-ttu-id="97a54-149">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="97a54-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="97a54-150">A Név mezőbe írja be a következőt: „Dt”.</span><span class="sxs-lookup"><span data-stu-id="97a54-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="97a54-151">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-151">Click OK.</span></span>
44. <span data-ttu-id="97a54-152">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="97a54-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="97a54-153">A Név mezőbe írja be a következőt: „Ct”.</span><span class="sxs-lookup"><span data-stu-id="97a54-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="97a54-154">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-154">Click OK.</span></span>
47. <span data-ttu-id="97a54-155">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="97a54-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="97a54-156">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="97a54-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="97a54-157">A Név mezőbe írja be a következőt: „Dimenziók”.</span><span class="sxs-lookup"><span data-stu-id="97a54-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="97a54-158">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-158">Click OK.</span></span>
51. <span data-ttu-id="97a54-159">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="97a54-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="97a54-160">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="97a54-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="97a54-161">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="97a54-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="97a54-162">A Név mezőbe írja be a következőt: „Kód”.</span><span class="sxs-lookup"><span data-stu-id="97a54-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="97a54-163">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-163">Click OK.</span></span>
56. <span data-ttu-id="97a54-164">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="97a54-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="97a54-165">A Név mezőbe írja be a következőt: „Érték”.</span><span class="sxs-lookup"><span data-stu-id="97a54-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="97a54-166">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-166">Click OK.</span></span>
59. <span data-ttu-id="97a54-167">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="97a54-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="97a54-168">A Név mezőbe írja be a következőt: „Leír.”.</span><span class="sxs-lookup"><span data-stu-id="97a54-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="97a54-169">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-169">Click OK.</span></span>
<span data-ttu-id="97a54-170">![ER-művelettervező oldal](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="97a54-170">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="97a54-171">Rendelje hozzá a jelentés elemeit az adatforrásokhoz</span><span class="sxs-lookup"><span data-stu-id="97a54-171">Map report elements to data sources</span></span>
1. <span data-ttu-id="97a54-172">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="97a54-172">Click the Mapping tab.</span></span>
2. <span data-ttu-id="97a54-173">A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell”.</span><span class="sxs-lookup"><span data-stu-id="97a54-173">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="97a54-174">A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="97a54-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="97a54-175">A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="97a54-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="97a54-176">A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="97a54-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="97a54-177">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem\Leír.: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-177">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="97a54-178">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista\Leírás: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="97a54-178">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="97a54-179">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-179">Click Bind.</span></span>
9. <span data-ttu-id="97a54-180">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem\Érték: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-180">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="97a54-181">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista\Kód: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="97a54-181">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="97a54-182">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-182">Click Bind.</span></span>
12. <span data-ttu-id="97a54-183">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem\Kód: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-183">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="97a54-184">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista\Név: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="97a54-184">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="97a54-185">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-185">Click Bind.</span></span>
15. <span data-ttu-id="97a54-186">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="97a54-186">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="97a54-187">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="97a54-187">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="97a54-188">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-188">Click Bind.</span></span>
18. <span data-ttu-id="97a54-189">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Ct: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-189">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="97a54-190">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Követel: Valós”.</span><span class="sxs-lookup"><span data-stu-id="97a54-190">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="97a54-191">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-191">Click Bind.</span></span>
21. <span data-ttu-id="97a54-192">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dt: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-192">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="97a54-193">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Tartozik: Valós”.</span><span class="sxs-lookup"><span data-stu-id="97a54-193">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="97a54-194">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-194">Click Bind.</span></span>
24. <span data-ttu-id="97a54-195">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Pénznem: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-195">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="97a54-196">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Pénznem: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="97a54-196">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="97a54-197">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-197">Click Bind.</span></span>
27. <span data-ttu-id="97a54-198">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dátum: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-198">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="97a54-199">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dátum: Dátum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-199">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="97a54-200">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-200">Click Bind.</span></span>
30. <span data-ttu-id="97a54-201">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Bizonylat: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-201">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="97a54-202">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Bizonylat: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="97a54-202">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="97a54-203">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-203">Click Bind.</span></span>
33. <span data-ttu-id="97a54-204">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="97a54-204">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="97a54-205">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="97a54-205">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="97a54-206">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-206">Click Bind.</span></span>
36. <span data-ttu-id="97a54-207">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Köteg: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-207">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="97a54-208">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Köteg: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="97a54-208">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="97a54-209">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-209">Click Bind.</span></span>
39. <span data-ttu-id="97a54-210">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem”.</span><span class="sxs-lookup"><span data-stu-id="97a54-210">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="97a54-211">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista”.</span><span class="sxs-lookup"><span data-stu-id="97a54-211">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="97a54-212">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-212">Click Bind.</span></span>
42. <span data-ttu-id="97a54-213">A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Vállalat: XML-attribútum”.</span><span class="sxs-lookup"><span data-stu-id="97a54-213">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="97a54-214">A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Vállalat: Karakterlánc”.</span><span class="sxs-lookup"><span data-stu-id="97a54-214">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="97a54-215">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-215">Click Bind.</span></span>
45. <span data-ttu-id="97a54-216">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="97a54-216">Click Save.</span></span>
46. <span data-ttu-id="97a54-217">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="97a54-217">Close the page.</span></span>
<span data-ttu-id="97a54-218">![ER-művelettervező oldal](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="97a54-218">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>

