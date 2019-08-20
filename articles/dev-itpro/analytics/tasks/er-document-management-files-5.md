---
title: ER Dokumentumkezelési fájlok használata formátumkimenetekben (5. rész – Formátum módosítása és futtatása)
description: A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba9cc4dcdfcfbc1bdb933336e85da9b4b6d97a40
ms.sourcegitcommit: f5556189a80ad9f23f1af3333837eae034ddb247
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/29/2019
ms.locfileid: "1791856"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5-modify-and-run-format"></a><span data-ttu-id="17d9e-103">ER Dokumentumkezelési fájlok használata formátumkimenetekben (5. rész: Formátum módosítása és futtatása)</span><span class="sxs-lookup"><span data-stu-id="17d9e-103">ER Use Document Management files in format outputs (Part 5: Modify and run format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="17d9e-104">A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.</span><span class="sxs-lookup"><span data-stu-id="17d9e-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="17d9e-105">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="17d9e-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="17d9e-106">A lépések végrehajtásához először végre kell hajtani az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (4. rész: formátum futtatása)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="17d9e-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 4: Run format)” procedure.</span></span>

<span data-ttu-id="17d9e-107">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="17d9e-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="17d9e-108">Módosítsa a mellékleteket feltöltő formátumot bináris formátumú üzenetek generálására</span><span class="sxs-lookup"><span data-stu-id="17d9e-108">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="17d9e-109">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="17d9e-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="17d9e-110">A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="17d9e-110">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="17d9e-111">A fastruktúrában bontsa ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).</span><span class="sxs-lookup"><span data-stu-id="17d9e-111">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="17d9e-112">A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni)\Elektronikus számla mintaüzenet.</span><span class="sxs-lookup"><span data-stu-id="17d9e-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="17d9e-113">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-113">Click Designer.</span></span>
    * <span data-ttu-id="17d9e-114">A generált kimenetben a számlaüzenet UNICODE-kódolású XML-fájlként lesz feltöltve.</span><span class="sxs-lookup"><span data-stu-id="17d9e-114">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="17d9e-115">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="17d9e-115">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="17d9e-116">A fában válassza ki a Common\File csomópontot.</span><span class="sxs-lookup"><span data-stu-id="17d9e-116">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="17d9e-117">A Név mezőbe írja be a következőt: „XML-üzenet”.</span><span class="sxs-lookup"><span data-stu-id="17d9e-117">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="17d9e-118">XML-üzenet</span><span class="sxs-lookup"><span data-stu-id="17d9e-118">Xml message</span></span>  
9. <span data-ttu-id="17d9e-119">A Kódolás mezőbe írja be az UTF-8 szót.</span><span class="sxs-lookup"><span data-stu-id="17d9e-119">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="17d9e-120">UTF-8</span><span class="sxs-lookup"><span data-stu-id="17d9e-120">UTF-8</span></span>  
10. <span data-ttu-id="17d9e-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-121">Click OK.</span></span>
    * <span data-ttu-id="17d9e-122">Állítsa be a generált kimenetet tömörített fájlként.</span><span class="sxs-lookup"><span data-stu-id="17d9e-122">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="17d9e-123">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="17d9e-123">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="17d9e-124">A fastruktúrában válassza ki következőt: Közös\Mappa.</span><span class="sxs-lookup"><span data-stu-id="17d9e-124">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="17d9e-125">A Név mezőbe írja be a következőt: „Zip-kimenet”.</span><span class="sxs-lookup"><span data-stu-id="17d9e-125">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="17d9e-126">Zip-kimenet</span><span class="sxs-lookup"><span data-stu-id="17d9e-126">Zip output</span></span>  
14. <span data-ttu-id="17d9e-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-127">Click OK.</span></span>
15. <span data-ttu-id="17d9e-128">A fastruktúrában válassza ki ezt: „Zip-kimenet”.</span><span class="sxs-lookup"><span data-stu-id="17d9e-128">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="17d9e-129">Adja hozzá a mellékleteket a generált tömörített fájlhoz az eredeti nevükkel és kiterjesztésükkel rendelkező fájlokként.</span><span class="sxs-lookup"><span data-stu-id="17d9e-129">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="17d9e-130">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="17d9e-130">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="17d9e-131">A fában válassza ki a Common\File csomópontot.</span><span class="sxs-lookup"><span data-stu-id="17d9e-131">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="17d9e-132">A Név mezőbe írja be a következőt: „Csatolt fájl”.</span><span class="sxs-lookup"><span data-stu-id="17d9e-132">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="17d9e-133">Csatolt fájl</span><span class="sxs-lookup"><span data-stu-id="17d9e-133">Attached file</span></span>  
19. <span data-ttu-id="17d9e-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-134">Click OK.</span></span>
20. <span data-ttu-id="17d9e-135">A fastruktúrában válassza ki ezt: „Zip-kimenet\Csatolt fájl”.</span><span class="sxs-lookup"><span data-stu-id="17d9e-135">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="17d9e-136">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="17d9e-136">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="17d9e-137">A fastruktúrában válassza ki ezt: „Szöveg\Base64”.</span><span class="sxs-lookup"><span data-stu-id="17d9e-137">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="17d9e-138">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-138">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="17d9e-139">Új formátum-összetevők leképezése az adatmodellre</span><span class="sxs-lookup"><span data-stu-id="17d9e-139">Map new format elements to data model</span></span>
1. <span data-ttu-id="17d9e-140">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="17d9e-140">Click the Mapping tab.</span></span>
2. <span data-ttu-id="17d9e-141">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="17d9e-141">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="17d9e-142">A fastruktúrában bontsa ki a „modell\Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="17d9e-142">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="17d9e-143">A fastruktúrában válassza ki ezt: „Zip-kimenet\Csatolt fájl\Base64”.</span><span class="sxs-lookup"><span data-stu-id="17d9e-143">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="17d9e-144">A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájltartalom” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="17d9e-144">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="17d9e-145">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-145">Click Bind.</span></span>
7. <span data-ttu-id="17d9e-146">A fastruktúrában válassza ki ezt: „Zip-kimenet\Csatolt fájl”.</span><span class="sxs-lookup"><span data-stu-id="17d9e-146">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="17d9e-147">Kattintson a Fájlnév szerkesztése elemre.</span><span class="sxs-lookup"><span data-stu-id="17d9e-147">Click Edit filename.</span></span>
9. <span data-ttu-id="17d9e-148">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="17d9e-148">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="17d9e-149">A fastruktúrában bontsa ki a „modell\Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="17d9e-149">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="17d9e-150">A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájlnév” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="17d9e-150">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="17d9e-151">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-151">Click Add data source.</span></span>
13. <span data-ttu-id="17d9e-152">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-152">Click Save.</span></span>
14. <span data-ttu-id="17d9e-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="17d9e-153">Close the page.</span></span>
15. <span data-ttu-id="17d9e-154">A fastruktúrában válassza ki a „modell\Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="17d9e-154">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="17d9e-155">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-155">Click Bind.</span></span>
17. <span data-ttu-id="17d9e-156">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-156">Click Save.</span></span>
18. <span data-ttu-id="17d9e-157">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="17d9e-157">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="17d9e-158">A tervezett jelentés futtatása a kijelölt számlához</span><span class="sxs-lookup"><span data-stu-id="17d9e-158">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="17d9e-159">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="17d9e-159">Click Run.</span></span>
2. <span data-ttu-id="17d9e-160">Bontsa ki a Belefoglalandó rekordok () szakaszt.</span><span class="sxs-lookup"><span data-stu-id="17d9e-160">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="17d9e-161">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-161">Click Filter.</span></span>
4. <span data-ttu-id="17d9e-162">Válassza ki a Vevői számlanapló sorát és a Értékesítési rendelés mezőt.</span><span class="sxs-lookup"><span data-stu-id="17d9e-162">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="17d9e-163">A Feltétel mezőben, az „Eladási rendelés” feltétel mezőjébe írja be a 000148 rendelési számot.</span><span class="sxs-lookup"><span data-stu-id="17d9e-163">In the Criteria field, In the criteria “Sales order” field, type the order number 000148.</span></span>
    * <span data-ttu-id="17d9e-164">000148</span><span class="sxs-lookup"><span data-stu-id="17d9e-164">000148</span></span>  
6. <span data-ttu-id="17d9e-165">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-165">Click OK.</span></span>
7. <span data-ttu-id="17d9e-166">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="17d9e-166">Click OK.</span></span>
    * <span data-ttu-id="17d9e-167">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="17d9e-167">Review the generated output.</span></span> <span data-ttu-id="17d9e-168">Megjegyzendő, hogy az XML-formátumú számlaüzeneten kívül az összes melléklet számára létrejön egy fájl.</span><span class="sxs-lookup"><span data-stu-id="17d9e-168">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="17d9e-169">A mellékletfájlok feltöltése a tömörített kimenettel bináris formátumban történik.</span><span class="sxs-lookup"><span data-stu-id="17d9e-169">The attachment files are populated with the zipped output in binary format.</span></span>  

