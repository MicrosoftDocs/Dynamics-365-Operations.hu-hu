---
title: Modellek és leképezések módosítása dokumentumoknak alkalmazásadatokkal történő létrehozásához
description: Ez a témakör egy elektronikus dokumentumot létrehozó és alkalmazásadatokat frissítő jelentéskészítési konfigurációk megtervezését mutatja be. (2. rész – Dokumentumok létrehozása).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 025429c8e6775d20634703853df04d63c0651b98
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092897"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a><span data-ttu-id="42607-104">Modellek és leképezések módosítása dokumentumoknak alkalmazásadatokkal történő létrehozásához</span><span class="sxs-lookup"><span data-stu-id="42607-104">Modify models and mappings to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="42607-105">Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (2. rész: Dokumentumok létrehozása)” eljárást.</span><span class="sxs-lookup"><span data-stu-id="42607-105">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 2: Generate documents)".</span></span> 

<span data-ttu-id="42607-106">Az eljárás lépései az elektronikus dokumentumot létrehozó elektronikus jelentési (ER) konfigurációk megtervezését és az alkalmazásadatok frissítését mutatják be.</span><span class="sxs-lookup"><span data-stu-id="42607-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="42607-107">Ebben az eljárásban módosítjuk az ER-konfigurációkat, hogy használatba vehessük őket az elektronikus dokumentumok létrehozásához és az alkalmazásadatok frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="42607-107">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="42607-108">Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült.</span><span class="sxs-lookup"><span data-stu-id="42607-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="42607-109">A lépések a DEMF-adathalmazzal hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="42607-109">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="42607-110">Az adatmodell módosítása</span><span class="sxs-lookup"><span data-stu-id="42607-110">Modify data model</span></span>
1. <span data-ttu-id="42607-111">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="42607-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="42607-112">A fastruktúrában válassza ki az „Instrastat (model)” elemet.</span><span class="sxs-lookup"><span data-stu-id="42607-112">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="42607-113">Az adatmodell használatát ki fogja terjeszteni.</span><span class="sxs-lookup"><span data-stu-id="42607-113">You will extend how you use the data model.</span></span> <span data-ttu-id="42607-114">Amellett, hogy adatforrásként használjuk az Intrastat-jelentés létrehozásához, az adatmodellt használjuk az Intrastat-jelentési folyamat adatainak összegyűjtésére.</span><span class="sxs-lookup"><span data-stu-id="42607-114">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="42607-115">Az adatokat ezután az alkalmazásadatok frissítéséhez használjuk.</span><span class="sxs-lookup"><span data-stu-id="42607-115">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="42607-116">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="42607-116">Click Designer.</span></span>
4. <span data-ttu-id="42607-117">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="42607-117">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="42607-118">Az Új csomópontként mezőben adja meg a következőt: „Modellgyökér”.</span><span class="sxs-lookup"><span data-stu-id="42607-118">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="42607-119">A Név mezőbe írja be a következőt: 'Alkalmazásadatok módosításához'.</span><span class="sxs-lookup"><span data-stu-id="42607-119">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="42607-120">Alkalmazásadatok módosításához</span><span class="sxs-lookup"><span data-stu-id="42607-120">For application data update</span></span>  
7. <span data-ttu-id="42607-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-121">Click Add.</span></span>
8. <span data-ttu-id="42607-122">A fában válassza ki ezt: „For application data update”.</span><span class="sxs-lookup"><span data-stu-id="42607-122">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="42607-123">Ezt az új gyökérelemet azért adjuk hozzá, hogy meghatározza az adatáramlást az adatok mozgatásához az Intrastat-jelentésből (adatforrásként használt) az alkalmazástáblákba (frissítési cél).</span><span class="sxs-lookup"><span data-stu-id="42607-123">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="42607-124">Ne feledje, hogy különböző gyökérelemeket kell használni a kimenő dokumentumba feladott adatok beolvasásához, valamint az adatok beolvasásához abból a dokumentumból, amely az alkalmazásadatok frissítésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="42607-124">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="42607-125">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="42607-125">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="42607-126">A Név mezőbe írja be az „Archive header” szöveget.</span><span class="sxs-lookup"><span data-stu-id="42607-126">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="42607-127">Archívumfejléc</span><span class="sxs-lookup"><span data-stu-id="42607-127">Archive header</span></span>  
11. <span data-ttu-id="42607-128">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-128">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="42607-129">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-129">Click Add.</span></span>
    * <span data-ttu-id="42607-130">Mivel minden egyes létrehozott Intrastat-jelentéshez létrehoz egy rekordot, ehhez létre kell hozni egy új elemet.</span><span class="sxs-lookup"><span data-stu-id="42607-130">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="42607-131">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="42607-131">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="42607-132">A Név mezőbe írja be a következőt: „Fájlnév”.</span><span class="sxs-lookup"><span data-stu-id="42607-132">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="42607-133">Fájlnév</span><span class="sxs-lookup"><span data-stu-id="42607-133">File name</span></span>  
15. <span data-ttu-id="42607-134">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-134">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="42607-135">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-135">Click Add.</span></span>
17. <span data-ttu-id="42607-136">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="42607-136">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="42607-137">A Név mezőbe írja be a „Sorok száma” szöveget.</span><span class="sxs-lookup"><span data-stu-id="42607-137">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="42607-138">Sorok száma</span><span class="sxs-lookup"><span data-stu-id="42607-138">Number of lines</span></span>  
19. <span data-ttu-id="42607-139">A Cikktípus mezőben válassza ki az „Integer” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-139">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="42607-140">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-140">Click Add.</span></span>
    * <span data-ttu-id="42607-141">Adja hozzá ezt az elemet, amely az aktuális jelentési folyamat során jelentett Intrastat-tranzakciók számát jelöli.</span><span class="sxs-lookup"><span data-stu-id="42607-141">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="42607-142">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="42607-142">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="42607-143">A Név mezőbe írja be a „Archív sorok” szöveget.</span><span class="sxs-lookup"><span data-stu-id="42607-143">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="42607-144">Archívum sorai</span><span class="sxs-lookup"><span data-stu-id="42607-144">Archive lines</span></span>  
23. <span data-ttu-id="42607-145">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-145">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="42607-146">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-146">Click Add.</span></span>
    * <span data-ttu-id="42607-147">Adja hozzá ezt az elemet, amely az aktuális jelentési folyamat során jelentett Intrastat-tranzakciók listáját jelöli.</span><span class="sxs-lookup"><span data-stu-id="42607-147">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="42607-148">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="42607-148">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="42607-149">A Név mezőbe írja be az 'Amount' szöveget.</span><span class="sxs-lookup"><span data-stu-id="42607-149">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="42607-150">Összeg</span><span class="sxs-lookup"><span data-stu-id="42607-150">Amount</span></span>  
27. <span data-ttu-id="42607-151">A Cikktípus mezőben válassza ki a „Valós” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-151">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="42607-152">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-152">Click Add.</span></span>
29. <span data-ttu-id="42607-153">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="42607-153">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="42607-154">A Név mezőben írja be az „Árucikk rekordazonosító” szöveget.</span><span class="sxs-lookup"><span data-stu-id="42607-154">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="42607-155">Árucikk rekordazonosító</span><span class="sxs-lookup"><span data-stu-id="42607-155">Commodity rec id</span></span>  
31. <span data-ttu-id="42607-156">A Cikktípus mezőben válassza ki az „Int64” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-156">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="42607-157">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-157">Click Add.</span></span>
33. <span data-ttu-id="42607-158">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="42607-158">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="42607-159">A Név mezőbe írja be a „Cikkszám” szöveget.</span><span class="sxs-lookup"><span data-stu-id="42607-159">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="42607-160">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="42607-160">Item number</span></span>  
35. <span data-ttu-id="42607-161">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-161">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="42607-162">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-162">Click Add.</span></span>
37. <span data-ttu-id="42607-163">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-163">Click Save.</span></span>
38. <span data-ttu-id="42607-164">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42607-164">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="42607-165">A modell-hozzárendelés módosítása</span><span class="sxs-lookup"><span data-stu-id="42607-165">Modify model mapping</span></span>
1. <span data-ttu-id="42607-166">A fastruktúrában bontsa ki az „Instrastat (model)” elemet.</span><span class="sxs-lookup"><span data-stu-id="42607-166">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="42607-167">A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat (mapping)”.</span><span class="sxs-lookup"><span data-stu-id="42607-167">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="42607-168">Módosítsa a meglévő modell-hozzárendelést a használatba vételéhez az alkalmazásadatok frissítésére és az Intrastat-jelentés részleteinek archiválásához.</span><span class="sxs-lookup"><span data-stu-id="42607-168">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="42607-169">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="42607-169">Click Designer.</span></span>
4. <span data-ttu-id="42607-170">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="42607-170">Click New.</span></span>
5. <span data-ttu-id="42607-171">A Név mezőbe írja be a „Archívum frissítése” szöveget.</span><span class="sxs-lookup"><span data-stu-id="42607-171">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="42607-172">Archívum frissítése</span><span class="sxs-lookup"><span data-stu-id="42607-172">Update archive</span></span>  
6. <span data-ttu-id="42607-173">Az Irány mezőben válassza a „Célhoz” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-173">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="42607-174">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-174">Click Save.</span></span>
    * <span data-ttu-id="42607-175">Ezt az új hozzárendelés meghatározza az adatáramlást az adatok (Intrastat-jelentés részletei) mozgatásához az adatforrásból az alkalmazástáblákba (frissítési cél).</span><span class="sxs-lookup"><span data-stu-id="42607-175">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="42607-176">Vegye figyelembe, hogy különböző gyökérelemeket kell használni az adatok beolvasásához az alkalmazásból a jelentési folyamathoz, és ezután az adatmodellből származó adatok használatához az alkalmazásadatok frissítésére.</span><span class="sxs-lookup"><span data-stu-id="42607-176">Note that different model's root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="42607-177">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="42607-177">Click Designer.</span></span>
9. <span data-ttu-id="42607-178">A fastruktúrában válassza ki az „Data model\Data model” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-178">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="42607-179">Adja meg a kötelező adatforrást.</span><span class="sxs-lookup"><span data-stu-id="42607-179">Add the required data source.</span></span> <span data-ttu-id="42607-180">Ez az adatmodell tartalmazza a jelentett Intrastat-tranzakciók részleteit, amelyeket archiválni kell.</span><span class="sxs-lookup"><span data-stu-id="42607-180">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="42607-181">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-181">Click Add root.</span></span>
11. <span data-ttu-id="42607-182">A Név mezőbe írja be ezt: 'model'.</span><span class="sxs-lookup"><span data-stu-id="42607-182">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="42607-183">modell</span><span class="sxs-lookup"><span data-stu-id="42607-183">model</span></span>  
12. <span data-ttu-id="42607-184">A Definíció mezőben adja meg vagy válassza ki az „Alkalmazásadatok frissítéséhez” értékét.</span><span class="sxs-lookup"><span data-stu-id="42607-184">In the Definition field, enter or select the value 'For application data update'.</span></span>
    * <span data-ttu-id="42607-185">Alkalmazásadatok módosításához</span><span class="sxs-lookup"><span data-stu-id="42607-185">For application data update</span></span>  
13. <span data-ttu-id="42607-186">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-186">Click OK.</span></span>
14. <span data-ttu-id="42607-187">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="42607-187">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="42607-188">A fán válassza ki a „Functions\Calculated mező” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-188">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="42607-189">A fában válassza ki a „model\Archive header” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-189">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="42607-190">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-190">Click Add.</span></span>
    * <span data-ttu-id="42607-191">Mivel fel kell sorolni a jelentett Intrastat-tranzakciókat archiválás céljából, hozzá kell adni a megfelelő adatforrást.</span><span class="sxs-lookup"><span data-stu-id="42607-191">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="42607-192">A Név mezőbe írja be a „Felsorolt sorok” szöveget.</span><span class="sxs-lookup"><span data-stu-id="42607-192">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="42607-193">Felsorolt sorok</span><span class="sxs-lookup"><span data-stu-id="42607-193">Enumerated lines</span></span>  
19. <span data-ttu-id="42607-194">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="42607-194">Click Edit formula.</span></span>
20. <span data-ttu-id="42607-195">A fastruktúrában válassza ki a következőt: „List\ENUMERATE”.</span><span class="sxs-lookup"><span data-stu-id="42607-195">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="42607-196">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-196">Click Add function.</span></span>
22. <span data-ttu-id="42607-197">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="42607-197">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="42607-198">A fában bontsa ki a „model\Archive header” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-198">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="42607-199">A fában válassza ki a „model\Archive header\Archive lines” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-199">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="42607-200">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="42607-200">Click Add data source.</span></span>
26. <span data-ttu-id="42607-201">A Képlet mezőben adja meg a következőt: 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span><span class="sxs-lookup"><span data-stu-id="42607-201">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="42607-202">ENUMERATE(model.'Archive header'.'Archive lines')</span><span class="sxs-lookup"><span data-stu-id="42607-202">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="42607-203">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-203">Click Save.</span></span>
28. <span data-ttu-id="42607-204">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42607-204">Close the page.</span></span>
29. <span data-ttu-id="42607-205">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-205">Click OK.</span></span>
30. <span data-ttu-id="42607-206">Kattintson a Cél hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="42607-206">Click Add destination.</span></span>
    * <span data-ttu-id="42607-207">Alkalmazástáblák hozzáadása szükséges célként, amely megköveteli a frissítéseket a jelentett Intrastat-tranzakciók archiválásához.</span><span class="sxs-lookup"><span data-stu-id="42607-207">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="42607-208">A Név mezőbe írja be a következőt: 'Archiváló'.</span><span class="sxs-lookup"><span data-stu-id="42607-208">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="42607-209">Archiválás</span><span class="sxs-lookup"><span data-stu-id="42607-209">Archive</span></span>  
32. <span data-ttu-id="42607-210">A Tábla neve mezőbe írja be ezt: 'IntrastatArchiveGeneral'.</span><span class="sxs-lookup"><span data-stu-id="42607-210">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="42607-211">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="42607-211">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="42607-212">Tartsa meg a „Beszúrás” rekordműveletet, hogy minden egyes Intrastat-jelentési folyamat részletes archiválásakor rekordokat tudjon hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="42607-212">Keep the record action 'Insert' so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="42607-213">Válassza az Igen lehetőséget a Rekordinformációs napló mezőben.</span><span class="sxs-lookup"><span data-stu-id="42607-213">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="42607-214">Válassza az Igen lehetőséget az alkalmazásadatok frissítésével kapcsolatos problémákra vonatkozó információk lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="42607-214">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="42607-215">A Rekordművelet ellenőrzésének kihagyása mezőben válassza az Igen beállítást.</span><span class="sxs-lookup"><span data-stu-id="42607-215">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="42607-216">Válassza az Igen lehetőséget az üres „Intrastat archívum azonosítója” mezőre vonatkozó ellenőrzési hibák figyelmen kívül hagyásához.</span><span class="sxs-lookup"><span data-stu-id="42607-216">Select Yes to suppress validation errors about the empty 'Intrastat archive ID' field.</span></span> <span data-ttu-id="42607-217">Ez a rekordok hozzáadását követően történik meg, a táblához a Külkereskedelmi paraméterek űrlapon beállított számsorozat-beállítások alapján.</span><span class="sxs-lookup"><span data-stu-id="42607-217">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="42607-218">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-218">Click OK.</span></span>
    * <span data-ttu-id="42607-219">A hozzáadott adatforrás (a szűrt modell a kijelölt gyökérelem alapján) elemeit kösse össze a hozzáadott cél elemeivel.</span><span class="sxs-lookup"><span data-stu-id="42607-219">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="42607-220">A fastruktúrában bontsa ki ezt: „Archive”.</span><span class="sxs-lookup"><span data-stu-id="42607-220">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="42607-221">A fában bontsa ki az „Archive\<Relations” elemet.</span><span class="sxs-lookup"><span data-stu-id="42607-221">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="42607-222">A fastruktúrában bontsa ki ezt: „Archive\<Relations\Intrastat\ArchiveDetail”.</span><span class="sxs-lookup"><span data-stu-id="42607-222">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="42607-223">A fában jelölje ki ezt: „Archive\<Relations\Intrastat\ArchiveDetail\Amount(AmountMST)”.</span><span class="sxs-lookup"><span data-stu-id="42607-223">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="42607-224">A fában bontsa ki ezt: „model\Archive header\Enumerated lines”.</span><span class="sxs-lookup"><span data-stu-id="42607-224">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="42607-225">A fában bontsa ki ezt: „model\Archive header\Enumerated lines\Value”.</span><span class="sxs-lookup"><span data-stu-id="42607-225">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="42607-226">A fában válassza ki ezt: „model\Archive header\Enumerated lines\Value\Amount”.</span><span class="sxs-lookup"><span data-stu-id="42607-226">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="42607-227">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-227">Click Bind.</span></span>
44. <span data-ttu-id="42607-228">A faszerkezetben válassza ki ezt: „Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)”.</span><span class="sxs-lookup"><span data-stu-id="42607-228">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="42607-229">A fában válassza ki ezt: „model\Archive header\Enumerated lines\Value\Commodity rec id”.</span><span class="sxs-lookup"><span data-stu-id="42607-229">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="42607-230">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-230">Click Bind.</span></span>
47. <span data-ttu-id="42607-231">A fában jelölje ki ezt: „Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)”.</span><span class="sxs-lookup"><span data-stu-id="42607-231">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="42607-232">A fában válassza ki ezt: „model\Archive header\Enumerated lines\Value\Item number”.</span><span class="sxs-lookup"><span data-stu-id="42607-232">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="42607-233">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-233">Click Bind.</span></span>
50. <span data-ttu-id="42607-234">A fában jelölje ki ezt: „Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)”.</span><span class="sxs-lookup"><span data-stu-id="42607-234">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="42607-235">A fában válassza ki ezt: „model\Archive header\Enumerated lines\Number”.</span><span class="sxs-lookup"><span data-stu-id="42607-235">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="42607-236">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-236">Click Bind.</span></span>
53. <span data-ttu-id="42607-237">A fastruktúrában válassza ki ezt: „Archive\<Relations\IntrastatArchiveDetail”.</span><span class="sxs-lookup"><span data-stu-id="42607-237">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="42607-238">A fában válassza ki ezt: „model\Archive header\Enumerated lines”.</span><span class="sxs-lookup"><span data-stu-id="42607-238">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="42607-239">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-239">Click Bind.</span></span>
56. <span data-ttu-id="42607-240">A fastruktúrában válassza ki ezt: „Archive\File name(FileName)”.</span><span class="sxs-lookup"><span data-stu-id="42607-240">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="42607-241">A fában válassza ki ezt: „model\Archive header\File name”.</span><span class="sxs-lookup"><span data-stu-id="42607-241">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="42607-242">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-242">Click Bind.</span></span>
59. <span data-ttu-id="42607-243">A fában válassza ki ezt: „Archive\Number of lines(NumberOfLines)”.</span><span class="sxs-lookup"><span data-stu-id="42607-243">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="42607-244">A fában válassza ki ezt: „model\Archive header\Number of lines”.</span><span class="sxs-lookup"><span data-stu-id="42607-244">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="42607-245">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-245">Click Bind.</span></span>
62. <span data-ttu-id="42607-246">A fastruktúrában válassza ki ezt: „Archive”.</span><span class="sxs-lookup"><span data-stu-id="42607-246">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="42607-247">A fában válassza ki a „model\Archive header” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42607-247">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="42607-248">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-248">Click Bind.</span></span>
65. <span data-ttu-id="42607-249">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="42607-249">Click Save.</span></span>
66. <span data-ttu-id="42607-250">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42607-250">Close the page.</span></span>
67. <span data-ttu-id="42607-251">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="42607-251">Close the page.</span></span>

