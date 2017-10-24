--- 
title: "Formátum módosítása és futtatása dokumentumkezelési fájlok használatára formátumkimenetekben elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 76915a7294e078d76ed3ca9c41755e12b0791f3c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="modify-and-run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="10971-103">Formátum módosítása és futtatása dokumentumkezelési fájlok használatára formátumkimenetekben elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="10971-103">Modify and run format to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="10971-104">A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.</span><span class="sxs-lookup"><span data-stu-id="10971-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="10971-105">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="10971-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="10971-106">A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (4. rész): Formátum futtatása” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="10971-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 4): Run format” procedure.</span></span>

<span data-ttu-id="10971-107">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="10971-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a><span data-ttu-id="10971-108">Módosítsa a mellékleteket feltöltő formátumot bináris formátumú üzenetek generálására</span><span class="sxs-lookup"><span data-stu-id="10971-108">Modify the format to populate attachments into generating messages in binary format</span></span>
1. <span data-ttu-id="10971-109">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="10971-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="10971-110">A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10971-110">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="10971-111">A fastruktúrában bontsa ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).</span><span class="sxs-lookup"><span data-stu-id="10971-111">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="10971-112">A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni)\Elektronikus számla mintaüzenet.</span><span class="sxs-lookup"><span data-stu-id="10971-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="10971-113">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="10971-113">Click Designer.</span></span>
    * <span data-ttu-id="10971-114">A generált kimenetben a számlaüzenet UNICODE-kódolású XML-fájlként lesz feltöltve.</span><span class="sxs-lookup"><span data-stu-id="10971-114">You will populate the invoice message in the generating output as an XML file using UNICODE encoding.</span></span>  
6. <span data-ttu-id="10971-115">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="10971-115">Click Add root to open the drop dialog.</span></span>
7. <span data-ttu-id="10971-116">A fában válassza ki a Common\File csomópontot.</span><span class="sxs-lookup"><span data-stu-id="10971-116">In the tree, select 'Common\File'.</span></span>
8. <span data-ttu-id="10971-117">A Név mezőbe írja be a következőt: „XML-üzenet”.</span><span class="sxs-lookup"><span data-stu-id="10971-117">In the Name field, type 'Xml message'.</span></span>
    * <span data-ttu-id="10971-118">XML-üzenet</span><span class="sxs-lookup"><span data-stu-id="10971-118">Xml message</span></span>  
9. <span data-ttu-id="10971-119">A Kódolás mezőbe írja be az UTF-8 szót.</span><span class="sxs-lookup"><span data-stu-id="10971-119">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="10971-120">UTF-8</span><span class="sxs-lookup"><span data-stu-id="10971-120">UTF-8</span></span>  
10. <span data-ttu-id="10971-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="10971-121">Click OK.</span></span>
    * <span data-ttu-id="10971-122">Állítsa be a generált kimenetet tömörített fájlként.</span><span class="sxs-lookup"><span data-stu-id="10971-122">Configure the generating output as a zipped file.</span></span>  
11. <span data-ttu-id="10971-123">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="10971-123">Click Add root to open the drop dialog.</span></span>
12. <span data-ttu-id="10971-124">A fastruktúrában válassza ki következőt: Közös\Mappa.</span><span class="sxs-lookup"><span data-stu-id="10971-124">In the tree, select 'Common\Folder'.</span></span>
13. <span data-ttu-id="10971-125">A Név mezőbe írja be a következőt: „Zip-kimenet”.</span><span class="sxs-lookup"><span data-stu-id="10971-125">In the Name field, type 'Zip output'.</span></span>
    * <span data-ttu-id="10971-126">Zip-kimenet</span><span class="sxs-lookup"><span data-stu-id="10971-126">Zip output</span></span>  
14. <span data-ttu-id="10971-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="10971-127">Click OK.</span></span>
15. <span data-ttu-id="10971-128">A fastruktúrában válassza ki ezt: „Zip-kimenet”.</span><span class="sxs-lookup"><span data-stu-id="10971-128">In the tree, select 'Zip output'.</span></span>
    * <span data-ttu-id="10971-129">Adja hozzá a mellékleteket a generált tömörített fájlhoz az eredeti nevükkel és kiterjesztésükkel rendelkező fájlokként.</span><span class="sxs-lookup"><span data-stu-id="10971-129">Add attachments to the generating zipped file as files with original names and extensions.</span></span>  
16. <span data-ttu-id="10971-130">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="10971-130">Click Add to open the drop dialog.</span></span>
17. <span data-ttu-id="10971-131">A fában válassza ki a Common\File csomópontot.</span><span class="sxs-lookup"><span data-stu-id="10971-131">In the tree, select 'Common\File'.</span></span>
18. <span data-ttu-id="10971-132">A Név mezőbe írja be a következőt: „Csatolt fájl”.</span><span class="sxs-lookup"><span data-stu-id="10971-132">In the Name field, type 'Attached file'.</span></span>
    * <span data-ttu-id="10971-133">Csatolt fájl</span><span class="sxs-lookup"><span data-stu-id="10971-133">Attached file</span></span>  
19. <span data-ttu-id="10971-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="10971-134">Click OK.</span></span>
20. <span data-ttu-id="10971-135">A fastruktúrában válassza ki ezt: „Zip-kimenet\Csatolt fájl”.</span><span class="sxs-lookup"><span data-stu-id="10971-135">In the tree, select 'Zip output\Attached file'.</span></span>
21. <span data-ttu-id="10971-136">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="10971-136">Click Add to open the drop dialog.</span></span>
22. <span data-ttu-id="10971-137">A fastruktúrában válassza ki ezt: „Szöveg\Base64”.</span><span class="sxs-lookup"><span data-stu-id="10971-137">In the tree, select 'Text\Base64'.</span></span>
23. <span data-ttu-id="10971-138">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="10971-138">Click OK.</span></span>

## <a name="map-new-format-elements-to-data-model"></a><span data-ttu-id="10971-139">Új formátum-összetevők leképezése az adatmodellre</span><span class="sxs-lookup"><span data-stu-id="10971-139">Map new format elements to data model</span></span>
1. <span data-ttu-id="10971-140">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="10971-140">Click the Mapping tab.</span></span>
2. <span data-ttu-id="10971-141">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="10971-141">In the tree, expand 'model'.</span></span>
3. <span data-ttu-id="10971-142">A fastruktúrában bontsa ki a „modell\Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10971-142">In the tree, expand 'model\Invoice attachments'.</span></span>
4. <span data-ttu-id="10971-143">A fastruktúrában válassza ki ezt: „Zip-kimenet\Csatolt fájl\Base64”.</span><span class="sxs-lookup"><span data-stu-id="10971-143">In the tree, select 'Zip output\Attached file\Base64'.</span></span>
5. <span data-ttu-id="10971-144">A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájltartalom” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10971-144">In the tree, select 'model\Invoice attachments\File content'.</span></span>
6. <span data-ttu-id="10971-145">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="10971-145">Click Bind.</span></span>
7. <span data-ttu-id="10971-146">A fastruktúrában válassza ki ezt: „Zip-kimenet\Csatolt fájl”.</span><span class="sxs-lookup"><span data-stu-id="10971-146">In the tree, select 'Zip output\Attached file'.</span></span>
8. <span data-ttu-id="10971-147">Kattintson a Fájlnév szerkesztése elemre.</span><span class="sxs-lookup"><span data-stu-id="10971-147">Click Edit filename.</span></span>
9. <span data-ttu-id="10971-148">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="10971-148">In the tree, expand 'model'.</span></span>
10. <span data-ttu-id="10971-149">A fastruktúrában bontsa ki a „modell\Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10971-149">In the tree, expand 'model\Invoice attachments'.</span></span>
11. <span data-ttu-id="10971-150">A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájlnév” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10971-150">In the tree, select 'model\Invoice attachments\File name'.</span></span>
12. <span data-ttu-id="10971-151">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="10971-151">Click Add data source.</span></span>
13. <span data-ttu-id="10971-152">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="10971-152">Click Save.</span></span>
14. <span data-ttu-id="10971-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="10971-153">Close the page.</span></span>
15. <span data-ttu-id="10971-154">A fastruktúrában válassza ki a „modell\Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="10971-154">In the tree, select 'model\Invoice attachments'.</span></span>
16. <span data-ttu-id="10971-155">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="10971-155">Click Bind.</span></span>
17. <span data-ttu-id="10971-156">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="10971-156">Click Save.</span></span>
18. <span data-ttu-id="10971-157">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="10971-157">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="10971-158">A tervezett jelentés futtatása a kijelölt számlához</span><span class="sxs-lookup"><span data-stu-id="10971-158">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="10971-159">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="10971-159">Click Run.</span></span>
2. <span data-ttu-id="10971-160">Bontsa ki a Belefoglalandó rekordok () szakaszt.</span><span class="sxs-lookup"><span data-stu-id="10971-160">Expand the Records to include () section.</span></span>
3. <span data-ttu-id="10971-161">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="10971-161">Click Filter.</span></span>
4. <span data-ttu-id="10971-162">Válassza ki a Vevői számlanapló sorát és a Értékesítési rendelés mezőt.</span><span class="sxs-lookup"><span data-stu-id="10971-162">Select the row of the Customer invoice journal and the Sales order field.</span></span>
5. <span data-ttu-id="10971-163">A Feltétel mezőben, az „Eladási rendelés” feltétel mezőjébe írja be a 000148 rendelési számot.</span><span class="sxs-lookup"><span data-stu-id="10971-163">In the Criteria field, In the criteria “Sales order” field, type the order number 000148.</span></span>
    * <span data-ttu-id="10971-164">000148</span><span class="sxs-lookup"><span data-stu-id="10971-164">000148</span></span>  
6. <span data-ttu-id="10971-165">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="10971-165">Click OK.</span></span>
7. <span data-ttu-id="10971-166">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="10971-166">Click OK.</span></span>
    * <span data-ttu-id="10971-167">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="10971-167">Review the generated output.</span></span> <span data-ttu-id="10971-168">Megjegyzendő, hogy az XML-formátumú számlaüzeneten kívül az összes melléklet számára létrejön egy fájl.</span><span class="sxs-lookup"><span data-stu-id="10971-168">Note,that in addition to the invoice message in XML format, a single file has been created for each attachment.</span></span> <span data-ttu-id="10971-169">A mellékletfájlok feltöltése a tömörített kimenettel bináris formátumban történik.</span><span class="sxs-lookup"><span data-stu-id="10971-169">The attachment files are populated with the zipped output in binary format.</span></span>  

