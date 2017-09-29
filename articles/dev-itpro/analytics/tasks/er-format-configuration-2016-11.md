--- 
title: "Elektronikus jelentéskészítés (ER) formátumkonfigurációjának létrehozása"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre formátum konfigurációt az Elektronikus jelentéshez (ER)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 04817d1f1851e43679995641e8b0ff99edaa83ad
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-format-configuration-for-electronic-reporting-er"></a><span data-ttu-id="b26ce-103">Elektronikus jelentéskészítés (ER) formátumkonfigurációjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="b26ce-103">Create a format configuration for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b26ce-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre formátum konfigurációt az Elektronikus jelentéshez (ER).</span><span class="sxs-lookup"><span data-stu-id="b26ce-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="b26ce-105">Ez a formátum konfiguráció határozza meg a kifizetések feldolgozására használt elektronikus dokumentumok formátumát.</span><span class="sxs-lookup"><span data-stu-id="b26ce-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="b26ce-106">Ebben a példában létrehoz egy formátum konfigurációt a mintavállalatra, a Litware, Inc.-re vonatkozóan. Hajtsa végre az alábbi lépéseket: Először végezze el a „Modell leképezése a kiválasztott adatforrásokhoz” műveletsorban ismertetett lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b26ce-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="b26ce-107">Új formátumkonfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="b26ce-107">Create a new format configuration</span></span>
1. <span data-ttu-id="b26ce-108">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b26ce-109">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-109">Click Reporting configurations.</span></span>
3. <span data-ttu-id="b26ce-110">A fán válassza ki a következőt: „Payments (simplified model)”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-110">In the tree, select 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="b26ce-111">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="b26ce-111">Click Create configuration to open the drop dialog.</span></span>
5. <span data-ttu-id="b26ce-112">Az Új mezőbe írja be a „PaymentModel modellen alapuló formátum” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="b26ce-112">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
6. <span data-ttu-id="b26ce-113">A Név mezőbe írja be a „BACS (UK fictitious)” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-113">In the Name field, type 'BACS (UK fictitious)'.</span></span>
    * <span data-ttu-id="b26ce-114">BACS (UK fiktív)</span><span class="sxs-lookup"><span data-stu-id="b26ce-114">BACS (UK fictitious)</span></span>  
7. <span data-ttu-id="b26ce-115">A Leírás mezőbe írja be a „BACS vendor payment format (UK fictitious)” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-115">In the Description field, type 'BACS vendor payment format (UK fictitious)'.</span></span>
    * <span data-ttu-id="b26ce-116">BACS szállítói kifizetés formátum (UK fiktív)</span><span class="sxs-lookup"><span data-stu-id="b26ce-116">BACS vendor payment format (UK fictitious)</span></span>  
    * <span data-ttu-id="b26ce-117">Az aktív konfigurációs szolgáltató automatikusan megjelenik itt.</span><span class="sxs-lookup"><span data-stu-id="b26ce-117">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="b26ce-118">Ez a szolgáltató tartja majd karban ezt a konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="b26ce-118">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="b26ce-119">Más szolgáltatók is használhatják ezt a konfigurációt, de nem tudják majd karbantartani.</span><span class="sxs-lookup"><span data-stu-id="b26ce-119">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="b26ce-120">Elektronikusdokumentum-formátum definiálható.</span><span class="sxs-lookup"><span data-stu-id="b26ce-120">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="b26ce-121">Ezt a mezőt hagyja üresen, ha azt szeretné, hogy futásidőben választhassa ki a formátumot.</span><span class="sxs-lookup"><span data-stu-id="b26ce-121">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="b26ce-122">Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b26ce-122">In the Data model definition field, enter or select a value.</span></span>
9. <span data-ttu-id="b26ce-123">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-123">Click Create configuration.</span></span>
    * <span data-ttu-id="b26ce-124">Új konfiguráció létrehozása megtörtént.</span><span class="sxs-lookup"><span data-stu-id="b26ce-124">A new configuration has been created.</span></span> <span data-ttu-id="b26ce-125">Egy vázlat verzió használható a tervezési formátum tárolására az elektronikus dokumentumok kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="b26ce-125">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-format-of-electronic-document"></a><span data-ttu-id="b26ce-126">Elektronikus dokumentumok tervezési formátuma</span><span class="sxs-lookup"><span data-stu-id="b26ce-126">Design format of electronic document</span></span>
1. <span data-ttu-id="b26ce-127">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-127">Click Designer.</span></span>
2. <span data-ttu-id="b26ce-128">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b26ce-128">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="b26ce-129">A fában válassza ki a Common\File csomópontot.</span><span class="sxs-lookup"><span data-stu-id="b26ce-129">In the tree, select 'Common\File'.</span></span>
4. <span data-ttu-id="b26ce-130">A Név mezőbe írja be az Xml szót.</span><span class="sxs-lookup"><span data-stu-id="b26ce-130">In the Name field, type 'Xml'.</span></span>
    * <span data-ttu-id="b26ce-131">Xml</span><span class="sxs-lookup"><span data-stu-id="b26ce-131">Xml</span></span>  
5. <span data-ttu-id="b26ce-132">A Kódolás mezőbe írja be az UTF-8 szót.</span><span class="sxs-lookup"><span data-stu-id="b26ce-132">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="b26ce-133">UTF-8</span><span class="sxs-lookup"><span data-stu-id="b26ce-133">UTF-8</span></span>  
6. <span data-ttu-id="b26ce-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-134">Click OK.</span></span>
7. <span data-ttu-id="b26ce-135">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b26ce-135">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="b26ce-136">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="b26ce-136">In the tree, select 'XML\Element'.</span></span>
9. <span data-ttu-id="b26ce-137">A Név mezőbe írja be a Message szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-137">In the Name field, type 'Message'.</span></span>
    * <span data-ttu-id="b26ce-138">Üzenet</span><span class="sxs-lookup"><span data-stu-id="b26ce-138">Message</span></span>  
10. <span data-ttu-id="b26ce-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-139">Click OK.</span></span>
11. <span data-ttu-id="b26ce-140">A fastruktúrában válassza ki ezt: „Xml\Üzenet”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-140">In the tree, select 'Xml\Message'.</span></span>
12. <span data-ttu-id="b26ce-141">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-141">Click Add Element.</span></span>
13. <span data-ttu-id="b26ce-142">A Név mezőbe írja be a ProcessingDate szót.</span><span class="sxs-lookup"><span data-stu-id="b26ce-142">In the Name field, type 'ProcessingDate'.</span></span>
    * <span data-ttu-id="b26ce-143">Feldolgozás dátuma</span><span class="sxs-lookup"><span data-stu-id="b26ce-143">ProcessingDate</span></span>  
14. <span data-ttu-id="b26ce-144">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-144">Click OK.</span></span>
15. <span data-ttu-id="b26ce-145">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-145">Click Add Element.</span></span>
16. <span data-ttu-id="b26ce-146">A Név mezőbe írja be a MessageId szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-146">In the Name field, type 'MessageId'.</span></span>
    * <span data-ttu-id="b26ce-147">Üzenetazonosító</span><span class="sxs-lookup"><span data-stu-id="b26ce-147">MessageId</span></span>  
17. <span data-ttu-id="b26ce-148">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-148">Click OK.</span></span>
18. <span data-ttu-id="b26ce-149">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-149">Click Add Element.</span></span>
19. <span data-ttu-id="b26ce-150">A Név mezőbe írja be a „Fizetések” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-150">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="b26ce-151">Kifizetések</span><span class="sxs-lookup"><span data-stu-id="b26ce-151">Payments</span></span>  
20. <span data-ttu-id="b26ce-152">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-152">Click OK.</span></span>
21. <span data-ttu-id="b26ce-153">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-153">In the tree, select 'Xml\Message\Payments'.</span></span>
22. <span data-ttu-id="b26ce-154">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-154">Click Add Element.</span></span>
23. <span data-ttu-id="b26ce-155">A Név mezőbe írja be az Item szót.</span><span class="sxs-lookup"><span data-stu-id="b26ce-155">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="b26ce-156">Tétel</span><span class="sxs-lookup"><span data-stu-id="b26ce-156">Item</span></span>  
24. <span data-ttu-id="b26ce-157">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-157">Click OK.</span></span>
25. <span data-ttu-id="b26ce-158">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-158">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
26. <span data-ttu-id="b26ce-159">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b26ce-159">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="b26ce-160">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="b26ce-160">In the tree, select 'XML\Attribute'.</span></span>
28. <span data-ttu-id="b26ce-161">A Név mezőbe írja be az Id szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-161">In the Name field, type 'Id'.</span></span>
    * <span data-ttu-id="b26ce-162">Azonosító</span><span class="sxs-lookup"><span data-stu-id="b26ce-162">Id</span></span>  
29. <span data-ttu-id="b26ce-163">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-163">Click OK.</span></span>
30. <span data-ttu-id="b26ce-164">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b26ce-164">Click Add to open the drop dialog.</span></span>
31. <span data-ttu-id="b26ce-165">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="b26ce-165">In the tree, select 'XML\Element'.</span></span>
32. <span data-ttu-id="b26ce-166">A Név mezőbe írja be a Vendor szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-166">In the Name field, type 'Vendor'.</span></span>
    * <span data-ttu-id="b26ce-167">Szállító</span><span class="sxs-lookup"><span data-stu-id="b26ce-167">Vendor</span></span>  
33. <span data-ttu-id="b26ce-168">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-168">Click OK.</span></span>
34. <span data-ttu-id="b26ce-169">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-169">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
35. <span data-ttu-id="b26ce-170">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-170">Click Add Element.</span></span>
36. <span data-ttu-id="b26ce-171">A Név mezőbe írja be a „Név” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-171">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="b26ce-172">Név</span><span class="sxs-lookup"><span data-stu-id="b26ce-172">Name</span></span>  
37. <span data-ttu-id="b26ce-173">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-173">Click OK.</span></span>
38. <span data-ttu-id="b26ce-174">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-174">Click Add Element.</span></span>
39. <span data-ttu-id="b26ce-175">A Név mezőbe írja be a Bank szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-175">In the Name field, type 'Bank'.</span></span>
    * <span data-ttu-id="b26ce-176">Bank</span><span class="sxs-lookup"><span data-stu-id="b26ce-176">Bank</span></span>  
40. <span data-ttu-id="b26ce-177">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-177">Click OK.</span></span>
41. <span data-ttu-id="b26ce-178">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-178">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
42. <span data-ttu-id="b26ce-179">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-179">Click Add Element.</span></span>
43. <span data-ttu-id="b26ce-180">A Név mezőbe írja be a „RoutingNumber” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-180">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="b26ce-181">Útvonalszám</span><span class="sxs-lookup"><span data-stu-id="b26ce-181">RoutingNumber</span></span>  
44. <span data-ttu-id="b26ce-182">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-182">Click OK.</span></span>
45. <span data-ttu-id="b26ce-183">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-183">Click Add Element.</span></span>
46. <span data-ttu-id="b26ce-184">A Név mezőbe írja be az „AccountNumber” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-184">In the Name field, type 'AccountNumber'.</span></span>
    * <span data-ttu-id="b26ce-185">Számlaszám</span><span class="sxs-lookup"><span data-stu-id="b26ce-185">AccountNumber</span></span>  
47. <span data-ttu-id="b26ce-186">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-186">Click OK.</span></span>
48. <span data-ttu-id="b26ce-187">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-187">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
49. <span data-ttu-id="b26ce-188">Kattintson a Másolás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-188">Click Copy.</span></span>
50. <span data-ttu-id="b26ce-189">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-189">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="b26ce-190">Kattintson a Beillesztés parancsra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-190">Click Paste.</span></span>
52. <span data-ttu-id="b26ce-191">A Név mezőbe írja be a Payer szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-191">In the Name field, type 'Payer'.</span></span>
    * <span data-ttu-id="b26ce-192">Fizető</span><span class="sxs-lookup"><span data-stu-id="b26ce-192">Payer</span></span>  
53. <span data-ttu-id="b26ce-193">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-193">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
54. <span data-ttu-id="b26ce-194">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-194">Click Add Element.</span></span>
55. <span data-ttu-id="b26ce-195">A név mezőbe írja be a „Pénznem” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-195">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="b26ce-196">Pénznem</span><span class="sxs-lookup"><span data-stu-id="b26ce-196">Currency</span></span>  
56. <span data-ttu-id="b26ce-197">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-197">Click OK.</span></span>
57. <span data-ttu-id="b26ce-198">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-198">Click Add Element.</span></span>
58. <span data-ttu-id="b26ce-199">A Név mezőbe írja be a „Leírás” szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-199">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="b26ce-200">Leírás</span><span class="sxs-lookup"><span data-stu-id="b26ce-200">Description</span></span>  
59. <span data-ttu-id="b26ce-201">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-201">Click OK.</span></span>
60. <span data-ttu-id="b26ce-202">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-202">Click Add Element.</span></span>
61. <span data-ttu-id="b26ce-203">A Név mezőbe írja be a 'TransDate' szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-203">In the Name field, type 'TransDate'.</span></span>
    * <span data-ttu-id="b26ce-204">Tranzakció dátuma</span><span class="sxs-lookup"><span data-stu-id="b26ce-204">TransDate</span></span>  
62. <span data-ttu-id="b26ce-205">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-205">Click OK.</span></span>
63. <span data-ttu-id="b26ce-206">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-206">Click Add Element.</span></span>
64. <span data-ttu-id="b26ce-207">A Név mezőbe írja be az 'Amount' szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-207">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="b26ce-208">Összeg</span><span class="sxs-lookup"><span data-stu-id="b26ce-208">Amount</span></span>  
65. <span data-ttu-id="b26ce-209">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-209">Click OK.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="b26ce-210">Formátum-összetevők előkészítése adatmodell-elemek leképezéséhez</span><span class="sxs-lookup"><span data-stu-id="b26ce-210">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="b26ce-211">A fastruktúrában válassza ki ezt: „Xml\Üzenet\ProcessingDate”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-211">In the tree, select 'Xml\Message\ProcessingDate'.</span></span>
2. <span data-ttu-id="b26ce-212">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b26ce-212">Click Add to open the drop dialog.</span></span>
3. <span data-ttu-id="b26ce-213">A fastruktúrában válassza ki ezt: „Szöveg\Dátum idő”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-213">In the tree, select 'Text\DateTime'.</span></span>
4. <span data-ttu-id="b26ce-214">A Formátum mezőbe írja be az yyyy-MM-dd szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-214">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="b26ce-215">éééé-HH-nn</span><span class="sxs-lookup"><span data-stu-id="b26ce-215">yyyy-MM-dd</span></span>  
5. <span data-ttu-id="b26ce-216">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-216">Click OK.</span></span>
6. <span data-ttu-id="b26ce-217">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\TransDate”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-217">In the tree, select 'Xml\Message\Payments\Item\TransDate'.</span></span>
7. <span data-ttu-id="b26ce-218">Kattintson a Dátum/idő hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-218">Click Add DateTime.</span></span>
8. <span data-ttu-id="b26ce-219">A Formátum mezőbe írja be az yyyy-MM-dd szöveget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-219">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="b26ce-220">éééé-HH-nn</span><span class="sxs-lookup"><span data-stu-id="b26ce-220">yyyy-MM-dd</span></span>  
9. <span data-ttu-id="b26ce-221">A DateTime típus mezőben válassza ki a „Dátum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b26ce-221">In the DateTime type field, select 'Date'.</span></span>
10. <span data-ttu-id="b26ce-222">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-222">Click OK.</span></span>
11. <span data-ttu-id="b26ce-223">A fastruktúrában válassza ki ezt: „Xml\Üzenet\MessageId”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-223">In the tree, select 'Xml\Message\MessageId'.</span></span>
12. <span data-ttu-id="b26ce-224">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="b26ce-224">Click Add to open the drop dialog.</span></span>
13. <span data-ttu-id="b26ce-225">A fában válassza ki ezt: „Text\String”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-225">In the tree, select 'Text\String'.</span></span>
14. <span data-ttu-id="b26ce-226">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-226">Click OK.</span></span>
15. <span data-ttu-id="b26ce-227">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Név”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-227">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name'.</span></span>
16. <span data-ttu-id="b26ce-228">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-228">Click Add String.</span></span>
17. <span data-ttu-id="b26ce-229">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-229">Click OK.</span></span>
18. <span data-ttu-id="b26ce-230">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-230">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber'.</span></span>
19. <span data-ttu-id="b26ce-231">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-231">Click Add String.</span></span>
20. <span data-ttu-id="b26ce-232">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-232">Click OK.</span></span>
21. <span data-ttu-id="b26ce-233">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\Számlaszám”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-233">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber'.</span></span>
22. <span data-ttu-id="b26ce-234">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-234">Click Add String.</span></span>
23. <span data-ttu-id="b26ce-235">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-235">Click OK.</span></span>
24. <span data-ttu-id="b26ce-236">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Név”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-236">In the tree, select 'Xml\Message\Payments\Item\Payer\Name'.</span></span>
25. <span data-ttu-id="b26ce-237">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-237">Click Add String.</span></span>
26. <span data-ttu-id="b26ce-238">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-238">Click OK.</span></span>
27. <span data-ttu-id="b26ce-239">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Bank\RoutingNumber”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-239">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber'.</span></span>
28. <span data-ttu-id="b26ce-240">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-240">Click Add String.</span></span>
29. <span data-ttu-id="b26ce-241">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-241">Click OK.</span></span>
30. <span data-ttu-id="b26ce-242">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Bank\Számlaszám”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-242">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber'.</span></span>
31. <span data-ttu-id="b26ce-243">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-243">Click Add String.</span></span>
32. <span data-ttu-id="b26ce-244">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-244">Click OK.</span></span>
33. <span data-ttu-id="b26ce-245">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Pénznem”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-245">In the tree, select 'Xml\Message\Payments\Item\Currency'.</span></span>
34. <span data-ttu-id="b26ce-246">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-246">Click Add String.</span></span>
35. <span data-ttu-id="b26ce-247">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-247">Click OK.</span></span>
36. <span data-ttu-id="b26ce-248">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Leírás”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-248">In the tree, select 'Xml\Message\Payments\Item\Description'.</span></span>
37. <span data-ttu-id="b26ce-249">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-249">Click Add String.</span></span>
38. <span data-ttu-id="b26ce-250">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-250">Click OK.</span></span>
39. <span data-ttu-id="b26ce-251">A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Összeg”.</span><span class="sxs-lookup"><span data-stu-id="b26ce-251">In the tree, select 'Xml\Message\Payments\Item\Amount'.</span></span>
40. <span data-ttu-id="b26ce-252">Kattintson a Karakterlánc hozzáadás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b26ce-252">Click Add String.</span></span>
41. <span data-ttu-id="b26ce-253">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-253">Click OK.</span></span>
42. <span data-ttu-id="b26ce-254">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b26ce-254">Click Save.</span></span>
43. <span data-ttu-id="b26ce-255">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b26ce-255">Close the page.</span></span>


