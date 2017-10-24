--- 
title: "Modell és leképezés módosítása alkalmazásadatok módosítását tartalmazó dokumentumok létrehozásához az elektronikus jelentéskészítéshez (ER)"
description: "Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (2. rész: Dokumentumok létrehozása)” eljárást."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.openlocfilehash: a29e273e5ef377826c0002a9a0a956defef6aa77
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="modify-model-and-mapping-to-generate-documents-with-application-data-update-for-electronic-reporting-er"></a><span data-ttu-id="f3f7f-103">Modell és leképezés módosítása alkalmazásadatok módosítását tartalmazó dokumentumok létrehozásához az elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="f3f7f-103">Modify model and mapping to generate documents with application data update for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f3f7f-104">Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (2. rész: Dokumentumok létrehozása)” eljárást.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-104">To complete the steps in this procedure, you must first complete the procedure, “ER Generate documents with application data update (Part 2: Generate documents)”.</span></span> 

<span data-ttu-id="f3f7f-105">Az eljárás lépései az elektronikus dokumentumot létrehozó elektronikus jelentési (ER) konfigurációk megtervezését és az alkalmazásadatok frissítését mutatják be.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="f3f7f-106">Ebben az eljárásban módosítjuk az ER-konfigurációkat, hogy használatba vehessük őket az elektronikus dokumentumok létrehozásához és az alkalmazásadatok frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-106">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="f3f7f-107">Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="f3f7f-108">A lépések a DEMF-adathalmazzal hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-108">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="f3f7f-109">Az adatmodell módosítása</span><span class="sxs-lookup"><span data-stu-id="f3f7f-109">Modify data model</span></span>
1. <span data-ttu-id="f3f7f-110">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="f3f7f-111">A fastruktúrában válassza ki az „Instrastat (model)” elemet.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-111">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="f3f7f-112">Az adatmodell használatát ki fogja terjeszteni.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-112">You will extend how you use the data model.</span></span> <span data-ttu-id="f3f7f-113">Amellett, hogy adatforrásként használjuk az Intrastat-jelentés létrehozásához, az adatmodellt használjuk az Intrastat-jelentési folyamat adatainak összegyűjtésére.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-113">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="f3f7f-114">Az adatokat ezután az alkalmazásadatok frissítéséhez használjuk.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-114">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="f3f7f-115">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-115">Click Designer.</span></span>
4. <span data-ttu-id="f3f7f-116">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-116">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="f3f7f-117">Az Új csomópontként mezőben adja meg a következőt: „Modellgyökér”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-117">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="f3f7f-118">A Név mezőbe írja be a következőt: 'Alkalmazásadatok módosításához'.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-118">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="f3f7f-119">Alkalmazásadatok módosításához</span><span class="sxs-lookup"><span data-stu-id="f3f7f-119">For application data update</span></span>  
7. <span data-ttu-id="f3f7f-120">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-120">Click Add.</span></span>
8. <span data-ttu-id="f3f7f-121">A fában válassza ki ezt: „For application data update”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-121">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="f3f7f-122">Ezt az új gyökérelemet azért adjuk hozzá, hogy meghatározza az adatáramlást az adatok mozgatásához az Intrastat-jelentésből (adatforrásként használt) az alkalmazástáblákba (frissítési cél).</span><span class="sxs-lookup"><span data-stu-id="f3f7f-122">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="f3f7f-123">Ne feledje, hogy különböző gyökérelemeket kell használni a kimenő dokumentumba feladott adatok beolvasásához, valamint az adatok beolvasásához abból a dokumentumból, amely az alkalmazásadatok frissítésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-123">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="f3f7f-124">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="f3f7f-125">A Név mezőbe írja be az „Archive header” szöveget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-125">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="f3f7f-126">Archívumfejléc</span><span class="sxs-lookup"><span data-stu-id="f3f7f-126">Archive header</span></span>  
11. <span data-ttu-id="f3f7f-127">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-127">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="f3f7f-128">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-128">Click Add.</span></span>
    * <span data-ttu-id="f3f7f-129">Mivel minden egyes létrehozott Intrastat-jelentéshez létrehoz egy rekordot, ehhez létre kell hozni egy új elemet.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-129">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="f3f7f-130">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-130">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="f3f7f-131">A Név mezőbe írja be a következőt: „Fájlnév”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-131">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="f3f7f-132">Fájlnév</span><span class="sxs-lookup"><span data-stu-id="f3f7f-132">File name</span></span>  
15. <span data-ttu-id="f3f7f-133">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-133">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="f3f7f-134">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-134">Click Add.</span></span>
17. <span data-ttu-id="f3f7f-135">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-135">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="f3f7f-136">A Név mezőbe írja be a „Sorok száma” szöveget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-136">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="f3f7f-137">Sorok száma</span><span class="sxs-lookup"><span data-stu-id="f3f7f-137">Number of lines</span></span>  
19. <span data-ttu-id="f3f7f-138">A Cikktípus mezőben válassza ki az „Integer” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-138">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="f3f7f-139">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-139">Click Add.</span></span>
    * <span data-ttu-id="f3f7f-140">Adja hozzá ezt az elemet, amely az aktuális jelentési folyamat során jelentett Intrastat-tranzakciók számát jelöli.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-140">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="f3f7f-141">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-141">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="f3f7f-142">A Név mezőbe írja be a „Archív sorok” szöveget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-142">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="f3f7f-143">Archívum sorai</span><span class="sxs-lookup"><span data-stu-id="f3f7f-143">Archive lines</span></span>  
23. <span data-ttu-id="f3f7f-144">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-144">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="f3f7f-145">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-145">Click Add.</span></span>
    * <span data-ttu-id="f3f7f-146">Adja hozzá ezt az elemet, amely az aktuális jelentési folyamat során jelentett Intrastat-tranzakciók listáját jelöli.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-146">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="f3f7f-147">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-147">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="f3f7f-148">A Név mezőbe írja be az 'Amount' szöveget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-148">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="f3f7f-149">Összeg</span><span class="sxs-lookup"><span data-stu-id="f3f7f-149">Amount</span></span>  
27. <span data-ttu-id="f3f7f-150">A Cikktípus mezőben válassza ki a „Valós” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-150">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="f3f7f-151">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-151">Click Add.</span></span>
29. <span data-ttu-id="f3f7f-152">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-152">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="f3f7f-153">A Név mezőben írja be az „Árucikk rekordazonosító” szöveget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-153">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="f3f7f-154">Árucikk rekordazonosító</span><span class="sxs-lookup"><span data-stu-id="f3f7f-154">Commodity rec id</span></span>  
31. <span data-ttu-id="f3f7f-155">A Cikktípus mezőben válassza ki az „Int64” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-155">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="f3f7f-156">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-156">Click Add.</span></span>
33. <span data-ttu-id="f3f7f-157">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-157">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="f3f7f-158">A Név mezőbe írja be a „Cikkszám” szöveget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-158">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="f3f7f-159">Cikkszám</span><span class="sxs-lookup"><span data-stu-id="f3f7f-159">Item number</span></span>  
35. <span data-ttu-id="f3f7f-160">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-160">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="f3f7f-161">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-161">Click Add.</span></span>
37. <span data-ttu-id="f3f7f-162">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-162">Click Save.</span></span>
38. <span data-ttu-id="f3f7f-163">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-163">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="f3f7f-164">A modell-hozzárendelés módosítása</span><span class="sxs-lookup"><span data-stu-id="f3f7f-164">Modify model mapping</span></span>
1. <span data-ttu-id="f3f7f-165">A fastruktúrában bontsa ki az „Instrastat (model)” elemet.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-165">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="f3f7f-166">A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat (mapping)”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-166">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="f3f7f-167">Módosítsa a meglévő modell-hozzárendelést a használatba vételéhez az alkalmazásadatok frissítésére és az Intrastat-jelentés részleteinek archiválásához.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-167">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="f3f7f-168">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-168">Click Designer.</span></span>
4. <span data-ttu-id="f3f7f-169">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-169">Click New.</span></span>
5. <span data-ttu-id="f3f7f-170">A Név mezőbe írja be a „Archívum frissítése” szöveget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-170">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="f3f7f-171">Archívum frissítése</span><span class="sxs-lookup"><span data-stu-id="f3f7f-171">Update archive</span></span>  
6. <span data-ttu-id="f3f7f-172">Az Irány mezőben válassza a „Célhoz” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-172">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="f3f7f-173">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-173">Click Save.</span></span>
    * <span data-ttu-id="f3f7f-174">Ezt az új hozzárendelés meghatározza az adatáramlást az adatok (Intrastat-jelentés részletei) mozgatásához az adatforrásból az alkalmazástáblákba (frissítési cél).</span><span class="sxs-lookup"><span data-stu-id="f3f7f-174">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="f3f7f-175">Vegye figyelembe, hogy különböző gyökérelemeket kell használni az adatok beolvasásához az alkalmazásból a jelentési folyamathoz, és ezután az adatmodellből származó adatok használatához az alkalmazásadatok frissítésére.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-175">Note that different model’s root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="f3f7f-176">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-176">Click Designer.</span></span>
9. <span data-ttu-id="f3f7f-177">A fastruktúrában válassza ki az „Data model\Data model” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-177">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="f3f7f-178">Adja meg a kötelező adatforrást.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-178">Add the required data source.</span></span> <span data-ttu-id="f3f7f-179">Ez az adatmodell tartalmazza a jelentett Intrastat-tranzakciók részleteit, amelyeket archiválni kell.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-179">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="f3f7f-180">Kattintson a Gyökér hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-180">Click Add root.</span></span>
11. <span data-ttu-id="f3f7f-181">A Név mezőbe írja be ezt: 'model'.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-181">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="f3f7f-182">modell</span><span class="sxs-lookup"><span data-stu-id="f3f7f-182">model</span></span>  
12. <span data-ttu-id="f3f7f-183">A Definíció mezőben adja meg vagy válassza ki az 'Alkalmazásadatok frissítéséhez' értékét.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-183">In the Definition field, enter or select the value ‘For application data update’.</span></span>
    * <span data-ttu-id="f3f7f-184">Alkalmazásadatok módosításához</span><span class="sxs-lookup"><span data-stu-id="f3f7f-184">For application data update</span></span>  
13. <span data-ttu-id="f3f7f-185">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-185">Click OK.</span></span>
14. <span data-ttu-id="f3f7f-186">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-186">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="f3f7f-187">A fán válassza ki a „Functions\Calculated mező” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-187">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="f3f7f-188">A fában válassza ki a „model\Archive header” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-188">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="f3f7f-189">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-189">Click Add.</span></span>
    * <span data-ttu-id="f3f7f-190">Mivel fel kell sorolni a jelentett Intrastat-tranzakciókat archiválás céljából, hozzá kell adni a megfelelő adatforrást.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-190">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="f3f7f-191">A Név mezőbe írja be a „Felsorolt sorok” szöveget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-191">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="f3f7f-192">Felsorolt sorok</span><span class="sxs-lookup"><span data-stu-id="f3f7f-192">Enumerated lines</span></span>  
19. <span data-ttu-id="f3f7f-193">Kattintson a Receptúra szerkesztése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-193">Click Edit formula.</span></span>
20. <span data-ttu-id="f3f7f-194">A fastruktúrában válassza ki a következőt: „List\ENUMERATE”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-194">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="f3f7f-195">Kattintson a Függvény hozzáadása gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-195">Click Add function.</span></span>
22. <span data-ttu-id="f3f7f-196">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-196">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="f3f7f-197">A fában bontsa ki a „model\Archive header” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-197">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="f3f7f-198">A fában válassza ki a „model\Archive header\Archive lines” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-198">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="f3f7f-199">Kattintson az Adatforrás hozzáadása pontra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-199">Click Add data source.</span></span>
26. <span data-ttu-id="f3f7f-200">A Képlet mezőben adja meg a következőt: 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-200">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="f3f7f-201">ENUMERATE(model.'Archive header'.'Archive lines')</span><span class="sxs-lookup"><span data-stu-id="f3f7f-201">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="f3f7f-202">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-202">Click Save.</span></span>
28. <span data-ttu-id="f3f7f-203">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-203">Close the page.</span></span>
29. <span data-ttu-id="f3f7f-204">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-204">Click OK.</span></span>
30. <span data-ttu-id="f3f7f-205">Kattintson a Cél hozzáadása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-205">Click Add destination.</span></span>
    * <span data-ttu-id="f3f7f-206">Alkalmazástáblák hozzáadása szükséges célként, amely megköveteli a frissítéseket a jelentett Intrastat-tranzakciók archiválásához.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-206">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="f3f7f-207">A Név mezőbe írja be a következőt: 'Archiváló'.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-207">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="f3f7f-208">Archiválás</span><span class="sxs-lookup"><span data-stu-id="f3f7f-208">Archive</span></span>  
32. <span data-ttu-id="f3f7f-209">A Tábla neve mezőbe írja be ezt: 'IntrastatArchiveGeneral'.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-209">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="f3f7f-210">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="f3f7f-210">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="f3f7f-211">Tartsa meg a 'Beszúrás' rekordműveletet, hogy minden egyes Intrastat-jelentési folyamat részletes archiválásakor rekordokat tudjon hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-211">Keep the record action ‘Insert’ so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="f3f7f-212">Válassza az Igen lehetőséget a Rekordinformációs napló mezőben.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-212">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="f3f7f-213">Válassza az Igen lehetőséget az alkalmazásadatok frissítésével kapcsolatos problémákra vonatkozó információk lekéréséhez.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-213">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="f3f7f-214">A Rekordművelet ellenőrzésének kihagyása mezőben válassza az Igen beállítást.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-214">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="f3f7f-215">Válassza az Igen lehetőséget az üres 'Intrastat archívum azonosítója' mezőre vonatkozó ellenőrzési hibák figyelmen kívül hagyásához.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-215">Select Yes to suppress validation errors about the empty ‘Intrastat archive ID’ field.</span></span> <span data-ttu-id="f3f7f-216">Ez a rekordok hozzáadását követően történik meg, a táblához a Külkereskedelmi paraméterek űrlapon beállított számsorozat-beállítások alapján.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-216">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="f3f7f-217">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-217">Click OK.</span></span>
    * <span data-ttu-id="f3f7f-218">A hozzáadott adatforrás (a szűrt modell a kijelölt gyökérelem alapján) elemeit kösse össze a hozzáadott cél elemeivel.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-218">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="f3f7f-219">A fastruktúrában bontsa ki ezt: „Archive”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-219">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="f3f7f-220">A fában bontsa ki az „Archive\<Relations” elemet.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-220">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="f3f7f-221">A fastruktúrában bontsa ki ezt: „Archive\<Relations\Intrastat\ArchiveDetail”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-221">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="f3f7f-222">A fában jelölje ki ezt: „Archive\<Relations\Intrastat\ArchiveDetail\Amount(AmountMST)”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-222">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="f3f7f-223">A fában bontsa ki ezt: „model\Archive header\Enumerated lines”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-223">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="f3f7f-224">A fában bontsa ki ezt: „model\Archive header\Enumerated lines\Value”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-224">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="f3f7f-225">A fában válassza ki ezt: „model\Archive header\Enumerated lines\Value\Amount”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-225">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="f3f7f-226">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-226">Click Bind.</span></span>
44. <span data-ttu-id="f3f7f-227">A faszerkezetben válassza ki ezt: „Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-227">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="f3f7f-228">A fában válassza ki ezt: „model\Archive header\Enumerated lines\Value\Commodity rec id”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-228">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="f3f7f-229">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-229">Click Bind.</span></span>
47. <span data-ttu-id="f3f7f-230">A fában jelölje ki ezt: „Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-230">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="f3f7f-231">A fában válassza ki ezt: „model\Archive header\Enumerated lines\Value\Item number”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-231">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="f3f7f-232">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-232">Click Bind.</span></span>
50. <span data-ttu-id="f3f7f-233">A fában jelölje ki ezt: „Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-233">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="f3f7f-234">A fában válassza ki ezt: „model\Archive header\Enumerated lines\Number”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-234">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="f3f7f-235">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-235">Click Bind.</span></span>
53. <span data-ttu-id="f3f7f-236">A fastruktúrában válassza ki ezt: „Archive\<Relations\IntrastatArchiveDetail”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-236">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="f3f7f-237">A fában válassza ki ezt: „model\Archive header\Enumerated lines”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-237">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="f3f7f-238">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-238">Click Bind.</span></span>
56. <span data-ttu-id="f3f7f-239">A fastruktúrában válassza ki ezt: „Archive\File name(FileName)”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-239">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="f3f7f-240">A fában válassza ki ezt: „model\Archive header\File name”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-240">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="f3f7f-241">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-241">Click Bind.</span></span>
59. <span data-ttu-id="f3f7f-242">A fában válassza ki ezt: „Archive\Number of lines(NumberOfLines)”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-242">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="f3f7f-243">A fában válassza ki ezt: „model\Archive header\Number of lines”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-243">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="f3f7f-244">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-244">Click Bind.</span></span>
62. <span data-ttu-id="f3f7f-245">A fastruktúrában válassza ki ezt: „Archive”.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-245">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="f3f7f-246">A fában válassza ki a „model\Archive header” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-246">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="f3f7f-247">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-247">Click Bind.</span></span>
65. <span data-ttu-id="f3f7f-248">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-248">Click Save.</span></span>
66. <span data-ttu-id="f3f7f-249">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-249">Close the page.</span></span>
67. <span data-ttu-id="f3f7f-250">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f3f7f-250">Close the page.</span></span>

