--- 
title: "Formátumok létrehozása dokumentumkezelési fájlok használatára ER-kimenetekben"
description: "A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés formátumot a dokumentumkezelési fájlok használatához az ER-kimenetben."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 1815a0004eee6734b3c7d2c2f9e75ce5fe16af1c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---

# <a name="create-formats-to-use-document-management-files-in-er-output"></a><span data-ttu-id="91031-103">Formátumok létrehozása dokumentumkezelési fájlok használatára ER-kimenetekben</span><span class="sxs-lookup"><span data-stu-id="91031-103">Create formats to use Document Management files in ER output</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="91031-104">A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.</span><span class="sxs-lookup"><span data-stu-id="91031-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="91031-105">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="91031-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="91031-106">A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (2. rész: Adatmodell előkészítése)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="91031-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 2: Extend data model” procedure.</span></span>

<span data-ttu-id="91031-107">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="91031-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-to-process-invoices"></a><span data-ttu-id="91031-108">Formátum létrehozása számlák feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="91031-108">Create a format to process invoices</span></span>
1. <span data-ttu-id="91031-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="91031-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="91031-110">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91031-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="91031-111">A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="91031-112">A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).</span><span class="sxs-lookup"><span data-stu-id="91031-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="91031-113">Létre fog hozni egy formátumot olyan elektronikus üzenetek generálásához, amelyek információkat tartalmaznak az összes olyan fájlról, amelyeket az elektronikusan feldolgozott számlához kapcsolódó értékesítési rendelésekhez mellékeltek.</span><span class="sxs-lookup"><span data-stu-id="91031-113">You will create a format to generate electronic messages with information about any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
5. <span data-ttu-id="91031-114">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="91031-114">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="91031-115">Az Új mezőbe írja be a „Formátum alapja a következő adatmodell: Vevői számlamodell (egyéni)” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="91031-115">In the New field, enter 'Format based on data model Customer invoice model (custom)'.</span></span>
7. <span data-ttu-id="91031-116">A Név mezőbe írja be a következőt: „Elektronikus számla mintaüzenet”.</span><span class="sxs-lookup"><span data-stu-id="91031-116">In the Name field, type 'Electronic invoice sample message'.</span></span>
    * <span data-ttu-id="91031-117">Elektronikus számla mintaüzenet</span><span class="sxs-lookup"><span data-stu-id="91031-117">Electronic invoice sample message</span></span>  
8. <span data-ttu-id="91031-118">Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="91031-118">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="91031-119">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="91031-119">InvoiceCustomer</span></span>  
9. <span data-ttu-id="91031-120">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91031-120">Click Create configuration.</span></span>

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a><span data-ttu-id="91031-121">Tervezzen a mellékleteket feltöltő formátumot MIME-formátumú üzenetek generálására</span><span class="sxs-lookup"><span data-stu-id="91031-121">Design a format to populate attachments into generating a message in MIME format</span></span>
1. <span data-ttu-id="91031-122">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="91031-122">Click Designer.</span></span>
2. <span data-ttu-id="91031-123">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="91031-123">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="91031-124">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="91031-124">In the tree, select 'XML\Element'.</span></span>
4. <span data-ttu-id="91031-125">A Név mezőbe írja be a következőt: „Számla”.</span><span class="sxs-lookup"><span data-stu-id="91031-125">In the Name field, type 'Invoice'.</span></span>
    * <span data-ttu-id="91031-126">Számla</span><span class="sxs-lookup"><span data-stu-id="91031-126">Invoice</span></span>  
5. <span data-ttu-id="91031-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-127">Click OK.</span></span>
6. <span data-ttu-id="91031-128">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="91031-128">Click Add to open the drop dialog.</span></span>
7. <span data-ttu-id="91031-129">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="91031-129">In the tree, select 'XML\Attribute'.</span></span>
8. <span data-ttu-id="91031-130">A Név mezőbe írja be a következőt: „SalesOrder”.</span><span class="sxs-lookup"><span data-stu-id="91031-130">In the Name field, type 'SalesOrder'.</span></span>
    * <span data-ttu-id="91031-131">SalesOrder</span><span class="sxs-lookup"><span data-stu-id="91031-131">SalesOrder</span></span>  
9. <span data-ttu-id="91031-132">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-132">Click OK.</span></span>
10. <span data-ttu-id="91031-133">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91031-133">Click Add Attribute.</span></span>
11. <span data-ttu-id="91031-134">A Név mezőbe írja be a következőt: „InvoiceNumber”.</span><span class="sxs-lookup"><span data-stu-id="91031-134">In the Name field, type 'InvoiceNumber'.</span></span>
    * <span data-ttu-id="91031-135">InvoiceNumber</span><span class="sxs-lookup"><span data-stu-id="91031-135">InvoiceNumber</span></span>  
12. <span data-ttu-id="91031-136">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-136">Click OK.</span></span>
13. <span data-ttu-id="91031-137">Kattintson az Attribútum hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91031-137">Click Add Attribute.</span></span>
14. <span data-ttu-id="91031-138">A Név mezőbe írja be a következőt: „InvoiceAmount”.</span><span class="sxs-lookup"><span data-stu-id="91031-138">In the Name field, type 'InvoiceAmount'.</span></span>
    * <span data-ttu-id="91031-139">InvoiceAmount</span><span class="sxs-lookup"><span data-stu-id="91031-139">InvoiceAmount</span></span>  
15. <span data-ttu-id="91031-140">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-140">Click OK.</span></span>
16. <span data-ttu-id="91031-141">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="91031-141">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="91031-142">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="91031-142">In the tree, select 'XML\Element'.</span></span>
18. <span data-ttu-id="91031-143">A Név mezőbe írja be a következőt: „EnclosedDocs”.</span><span class="sxs-lookup"><span data-stu-id="91031-143">In the Name field, type 'EnclosedDocs'.</span></span>
    * <span data-ttu-id="91031-144">EnclosedDocs</span><span class="sxs-lookup"><span data-stu-id="91031-144">EnclosedDocs</span></span>  
19. <span data-ttu-id="91031-145">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-145">Click OK.</span></span>
20. <span data-ttu-id="91031-146">A fastruktúrában válassza ki a „Számla\EnclosedDocs” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-146">In the tree, select 'Invoice\EnclosedDocs'.</span></span>
21. <span data-ttu-id="91031-147">Kattintson az Elem hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="91031-147">Click Add Element.</span></span>
22. <span data-ttu-id="91031-148">A Név mezőbe írja be a következőt: „Dokumentum”.</span><span class="sxs-lookup"><span data-stu-id="91031-148">In the Name field, type 'Document'.</span></span>
    * <span data-ttu-id="91031-149">Bizonylat</span><span class="sxs-lookup"><span data-stu-id="91031-149">Document</span></span>  
23. <span data-ttu-id="91031-150">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-150">Click OK.</span></span>
24. <span data-ttu-id="91031-151">A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-151">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
25. <span data-ttu-id="91031-152">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="91031-152">Click Add to open the drop dialog.</span></span>
26. <span data-ttu-id="91031-153">A fastruktúrában válassza ki az XML\Attribute elemet.</span><span class="sxs-lookup"><span data-stu-id="91031-153">In the tree, select 'XML\Attribute'.</span></span>
27. <span data-ttu-id="91031-154">A Név mezőbe írja be a következőt: „FileName”.</span><span class="sxs-lookup"><span data-stu-id="91031-154">In the Name field, type 'FileName'.</span></span>
    * <span data-ttu-id="91031-155">FileName</span><span class="sxs-lookup"><span data-stu-id="91031-155">FileName</span></span>  
28. <span data-ttu-id="91031-156">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-156">Click OK.</span></span>
29. <span data-ttu-id="91031-157">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="91031-157">Click Add to open the drop dialog.</span></span>
30. <span data-ttu-id="91031-158">A fában válassza ki az XML\Element csomópontot.</span><span class="sxs-lookup"><span data-stu-id="91031-158">In the tree, select 'XML\Element'.</span></span>
31. <span data-ttu-id="91031-159">A Név mezőbe írja be a következőt: „FileContent”.</span><span class="sxs-lookup"><span data-stu-id="91031-159">In the Name field, type 'FileContent'.</span></span>
    * <span data-ttu-id="91031-160">FileContent</span><span class="sxs-lookup"><span data-stu-id="91031-160">FileContent</span></span>  
32. <span data-ttu-id="91031-161">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-161">Click OK.</span></span>
33. <span data-ttu-id="91031-162">A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum\FileContent” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-162">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent'.</span></span>
34. <span data-ttu-id="91031-163">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="91031-163">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="91031-164">A fastruktúrában válassza ki ezt: „Szöveg\Base64”.</span><span class="sxs-lookup"><span data-stu-id="91031-164">In the tree, select 'Text\Base64'.</span></span>
36. <span data-ttu-id="91031-165">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-165">Click OK.</span></span>

## <a name="map-format-elements-to-data-model-as-data-source"></a><span data-ttu-id="91031-166">Formátumelemek leképezése az adatmodellre adatforrásként</span><span class="sxs-lookup"><span data-stu-id="91031-166">Map format elements to data model as data source</span></span>
1. <span data-ttu-id="91031-167">A fastruktúrában válassza ki a „Számla\SalesOrder” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-167">In the tree, select 'Invoice\SalesOrder'.</span></span>
2. <span data-ttu-id="91031-168">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="91031-168">Click the Mapping tab.</span></span>
3. <span data-ttu-id="91031-169">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="91031-169">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="91031-170">A fastruktúrában válassza ki a következőt: „modell\Értékesítési rendelés száma(SalesId)”.</span><span class="sxs-lookup"><span data-stu-id="91031-170">In the tree, select 'model\Sales order number(SalesId)'.</span></span>
5. <span data-ttu-id="91031-171">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-171">Click Bind.</span></span>
6. <span data-ttu-id="91031-172">A fastruktúrában válassza ki a „Számla\InvoiceNumber” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-172">In the tree, select 'Invoice\InvoiceNumber'.</span></span>
7. <span data-ttu-id="91031-173">A fastruktúrában bontsa ki a „modell\Számlaalap(InvoiceBase)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-173">In the tree, expand 'model\Base invoice(InvoiceBase)'.</span></span>
8. <span data-ttu-id="91031-174">A fastruktúrában válassza ki a következőt: „modell\Számlaalap(InvoiceBase) \Számlaszám(Id)”.</span><span class="sxs-lookup"><span data-stu-id="91031-174">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice number(Id)'.</span></span>
9. <span data-ttu-id="91031-175">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-175">Click Bind.</span></span>
10. <span data-ttu-id="91031-176">A fastruktúrában válassza ki a „Számla\InvoiceAmount” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-176">In the tree, select 'Invoice\InvoiceAmount'.</span></span>
11. <span data-ttu-id="91031-177">A fastruktúrában válassza ki a következőt: „modell\Számlaalap(InvoiceBase) \Számlaösszeg(Amount)”.</span><span class="sxs-lookup"><span data-stu-id="91031-177">In the tree, select 'model\Base invoice(InvoiceBase)\Invoice amount(Amount)'.</span></span>
12. <span data-ttu-id="91031-178">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-178">Click Bind.</span></span>
13. <span data-ttu-id="91031-179">A fastruktúrában bontsa ki a „modell\Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-179">In the tree, expand 'model\Invoice attachments'.</span></span>
14. <span data-ttu-id="91031-180">A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájltartalom” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-180">In the tree, select 'model\Invoice attachments\File content'.</span></span>
15. <span data-ttu-id="91031-181">A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum\FileContent\Base64” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-181">In the tree, select 'Invoice\EnclosedDocs\Document\FileContent\Base64'.</span></span>
16. <span data-ttu-id="91031-182">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-182">Click Bind.</span></span>
17. <span data-ttu-id="91031-183">A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájlnév” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-183">In the tree, select 'model\Invoice attachments\File name'.</span></span>
18. <span data-ttu-id="91031-184">A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum\FileName” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-184">In the tree, select 'Invoice\EnclosedDocs\Document\FileName'.</span></span>
19. <span data-ttu-id="91031-185">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-185">Click Bind.</span></span>
20. <span data-ttu-id="91031-186">A fastruktúrában válassza ki a „modell\Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-186">In the tree, select 'model\Invoice attachments'.</span></span>
21. <span data-ttu-id="91031-187">A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91031-187">In the tree, select 'Invoice\EnclosedDocs\Document'.</span></span>
22. <span data-ttu-id="91031-188">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-188">Click Bind.</span></span>
23. <span data-ttu-id="91031-189">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="91031-189">Click Save.</span></span>
24. <span data-ttu-id="91031-190">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="91031-190">Close the page.</span></span>


