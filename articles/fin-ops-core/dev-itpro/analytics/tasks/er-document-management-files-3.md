---
title: ER Dokumentumkezelési fájlok használata formátumkimenetekben (3. rész –Formátum létrehozása)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentéskészítési formátumot a dokumentumkezelési fájlok használatára az ER-kimenetben. (3. rész)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99a286b4e40ddeb7f4ff37c1ece3c678b26c838b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755010"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a><span data-ttu-id="45f70-104">ER Dokumentumkezelési fájlok használata formátumkimenetekben (3. rész –Formátum létrehozása)</span><span class="sxs-lookup"><span data-stu-id="45f70-104">ER Use Document Management files in format outputs (Part 3 - Create format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="45f70-105">A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.</span><span class="sxs-lookup"><span data-stu-id="45f70-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="45f70-106">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="45f70-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="45f70-107">A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (2. rész: Adatmodell előkészítése)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="45f70-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 2: Extend data model" procedure.</span></span>

<span data-ttu-id="45f70-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="45f70-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="45f70-109">Formátum létrehozása számlák feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="45f70-109">Create a format to process invoices</span></span>
1. <span data-ttu-id="45f70-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="45f70-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="45f70-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="45f70-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="45f70-112">A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="45f70-113">A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).</span><span class="sxs-lookup"><span data-stu-id="45f70-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="45f70-114">Létre fog hozni egy formátumot olyan elektronikus üzenetek generálásához, amelyek információkat tartalmaznak az összes olyan fájlról, amelyeket az elektronikusan feldolgozott számlához kapcsolódó értékesítési rendelésekhez mellékeltek.</span><span class="sxs-lookup"><span data-stu-id="45f70-114">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="45f70-115">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="45f70-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="45f70-116">Az Új mezőbe írja be a „Formátum alapja a következő adatmodell: Vevői számlamodell (egyéni)” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="45f70-116">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="45f70-117">A Név mezőbe írja be a következőt: „Elektronikus számla mintaüzenet”.</span><span class="sxs-lookup"><span data-stu-id="45f70-117">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="45f70-118">Elektronikus számla mintaüzenet</span><span class="sxs-lookup"><span data-stu-id="45f70-118">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="45f70-119">Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="45f70-119">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="45f70-120">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="45f70-120">InvoiceCustomer</span></span>  
9. <span data-ttu-id="45f70-121">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="45f70-121">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="45f70-122">Tervezzen a mellékleteket feltöltő formátumot MIME-formátumú üzenetek generálására</span><span class="sxs-lookup"><span data-stu-id="45f70-122">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="45f70-123">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="45f70-123">Click Designer.</span></span>
2. <span data-ttu-id="45f70-124">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="45f70-124">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="45f70-125">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="45f70-125">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="45f70-126">A Név mezőbe írja be a következőt: „Számla”.</span><span class="sxs-lookup"><span data-stu-id="45f70-126">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="45f70-127">Számla</span><span class="sxs-lookup"><span data-stu-id="45f70-127">Invoice</span></span>  
5. <span data-ttu-id="45f70-128">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-128">Click OK.</span></span>
6. <span data-ttu-id="45f70-129">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="45f70-129">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="45f70-130">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="45f70-130">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="45f70-131">A Név mezőbe írja be a következőt: „SalesOrder”.</span><span class="sxs-lookup"><span data-stu-id="45f70-131">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="45f70-132">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="45f70-132">SalesOrder</span></span>  
9. <span data-ttu-id="45f70-133">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-133">Click OK.</span></span>
10. <span data-ttu-id="45f70-134">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="45f70-134">Click Add Attribute.</span></span>
11. <span data-ttu-id="45f70-135">A Név mezőbe írja be a következőt: „InvoiceNumber”.</span><span class="sxs-lookup"><span data-stu-id="45f70-135">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="45f70-136">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="45f70-136">InvoiceNumber</span></span>  
12. <span data-ttu-id="45f70-137">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-137">Click OK.</span></span>
13. <span data-ttu-id="45f70-138">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="45f70-138">Click Add Attribute.</span></span>
14. <span data-ttu-id="45f70-139">A Név mezőbe írja be a következőt: „InvoiceAmount”.</span><span class="sxs-lookup"><span data-stu-id="45f70-139">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="45f70-140">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="45f70-140">InvoiceAmount</span></span>  
15. <span data-ttu-id="45f70-141">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-141">Click OK.</span></span>
16. <span data-ttu-id="45f70-142">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="45f70-142">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="45f70-143">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="45f70-143">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="45f70-144">A Név mezőbe írja be a következőt: „EnclosedDocs”.</span><span class="sxs-lookup"><span data-stu-id="45f70-144">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="45f70-145">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="45f70-145">EnclosedDocs</span></span>  
19. <span data-ttu-id="45f70-146">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-146">Click OK.</span></span>
20. <span data-ttu-id="45f70-147">A fastruktúrában válassza ki a „Számla\EnclosedDocs” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-147">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="45f70-148">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="45f70-148">Click Add Element.</span></span>
22. <span data-ttu-id="45f70-149">A Név mezőbe írja be a következőt: „Dokumentum”.</span><span class="sxs-lookup"><span data-stu-id="45f70-149">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="45f70-150">Bizonylat</span><span class="sxs-lookup"><span data-stu-id="45f70-150">Document</span></span>  
23. <span data-ttu-id="45f70-151">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-151">Click OK.</span></span>
24. <span data-ttu-id="45f70-152">A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-152">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="45f70-153">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="45f70-153">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="45f70-154">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="45f70-154">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="45f70-155">A Név mezőbe írja be a következőt: „FileName”.</span><span class="sxs-lookup"><span data-stu-id="45f70-155">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="45f70-156">FileName</span><span class="sxs-lookup"><span data-stu-id="45f70-156">FileName</span></span>  
28. <span data-ttu-id="45f70-157">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-157">Click OK.</span></span>
29. <span data-ttu-id="45f70-158">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="45f70-158">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="45f70-159">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="45f70-159">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="45f70-160">A Név mezőbe írja be a következőt: „FileContent”.</span><span class="sxs-lookup"><span data-stu-id="45f70-160">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="45f70-161">FileContent</span><span class="sxs-lookup"><span data-stu-id="45f70-161">FileContent</span></span>  
32. <span data-ttu-id="45f70-162">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-162">Click OK.</span></span>
33. <span data-ttu-id="45f70-163">A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum\FileContent” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-163">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="45f70-164">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="45f70-164">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="45f70-165">A fastruktúrában válassza ki ezt: „Szöveg\Base64”.</span><span class="sxs-lookup"><span data-stu-id="45f70-165">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="45f70-166">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-166">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="45f70-167">Formátumelemek leképezése az adatmodellre adatforrásként</span><span class="sxs-lookup"><span data-stu-id="45f70-167">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="45f70-168">A fastruktúrában válassza ki a „Számla\SalesOrder” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-168">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="45f70-169">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="45f70-169">Click the Mapping tab.</span></span>
3. <span data-ttu-id="45f70-170">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="45f70-170">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="45f70-171">A fastruktúrában válassza ki a következőt: „modell\Értékesítési rendelés száma(SalesId)”.</span><span class="sxs-lookup"><span data-stu-id="45f70-171">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="45f70-172">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-172">Click Bind.</span></span>
6. <span data-ttu-id="45f70-173">A fastruktúrában válassza ki a „Számla\InvoiceNumber” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-173">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="45f70-174">A fastruktúrában bontsa ki a „modell\Számlaalap(InvoiceBase)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-174">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="45f70-175">A fastruktúrában válassza ki a következőt: „modell\Számlaalap(InvoiceBase) \Számlaszám(Id)”.</span><span class="sxs-lookup"><span data-stu-id="45f70-175">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="45f70-176">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-176">Click Bind.</span></span>
10. <span data-ttu-id="45f70-177">A fastruktúrában válassza ki a „Számla\InvoiceAmount” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-177">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="45f70-178">A fastruktúrában válassza ki a következőt: „modell\Számlaalap(InvoiceBase) \Számlaösszeg(Amount)”.</span><span class="sxs-lookup"><span data-stu-id="45f70-178">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="45f70-179">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-179">Click Bind.</span></span>
13. <span data-ttu-id="45f70-180">A fastruktúrában bontsa ki a „modell\Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-180">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="45f70-181">A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájltartalom” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-181">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="45f70-182">A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum\FileContent\Base64” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-182">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="45f70-183">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-183">Click Bind.</span></span>
17. <span data-ttu-id="45f70-184">A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájlnév” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-184">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="45f70-185">A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum\FileName” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-185">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="45f70-186">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-186">Click Bind.</span></span>
20. <span data-ttu-id="45f70-187">A fastruktúrában válassza ki a „modell\Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-187">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="45f70-188">A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="45f70-188">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="45f70-189">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-189">Click Bind.</span></span>
23. <span data-ttu-id="45f70-190">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="45f70-190">Click Save.</span></span>
24. <span data-ttu-id="45f70-191">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="45f70-191">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]