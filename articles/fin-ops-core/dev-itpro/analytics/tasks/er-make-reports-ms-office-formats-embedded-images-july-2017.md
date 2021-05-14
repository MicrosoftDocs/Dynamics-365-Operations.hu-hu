---
title: Konfigurációk tervezése jelentések készítéséshez Office formátumban, beágyazott képekkel
description: Ez a témakör azt mutatja be, hogyan tervezhetők konfigurációk beágyazott képeket tartalmazó Excel- és Word-formátumú elektronikus dokumentumok létrehozására.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5eea178a351716425706f481ae66c5b5183a52e5
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944557"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="9ee9e-103">Konfigurációk tervezése jelentések készítéséshez Office formátumban, beágyazott képekkel</span><span class="sxs-lookup"><span data-stu-id="9ee9e-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9ee9e-104">A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az „ER – Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-104">To complete the steps in this procedure, first complete the procedure, "ER Create a configuration provider and mark it as active."</span></span> <span data-ttu-id="9ee9e-105">Ez az eljárás bemutatja, hogyan tervezhetők elektronikus jelentési (ER) konfigurációk beágyazott képeket tartalmazó Microsoft Excel vagy Word-dokumentumok létrehozására.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="9ee9e-106">Ebben az eljárásban a szükséges ER konfigurációkat a Litware, Inc. mintavállalathoz hozza létre. Ezek a lépések az USMF adatkészlet segítségével tölthetők be.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="9ee9e-107">Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="9ee9e-108">Mielőtt belekezdene, a következő fájlokat is le kell töltenie és mentenie kell:</span><span class="sxs-lookup"><span data-stu-id="9ee9e-108">Before you begin, download and save the following files:</span></span> 

| <span data-ttu-id="9ee9e-109">Leírás</span><span class="sxs-lookup"><span data-stu-id="9ee9e-109">Description</span></span>                                          | <span data-ttu-id="9ee9e-110">Fájlnév</span><span class="sxs-lookup"><span data-stu-id="9ee9e-110">File name</span></span>                   |
|------------------------------------------------------|-----------------------------|
| <span data-ttu-id="9ee9e-111">ER-adatmodell konfigurációja</span><span class="sxs-lookup"><span data-stu-id="9ee9e-111">ER data model configuration</span></span>                          | [<span data-ttu-id="9ee9e-112">Model for cheques.xml</span><span class="sxs-lookup"><span data-stu-id="9ee9e-112">Model for cheques.xml</span></span>](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| <span data-ttu-id="9ee9e-113">ER-formátum konfigurációja</span><span class="sxs-lookup"><span data-stu-id="9ee9e-113">ER format configuration</span></span>                              | [<span data-ttu-id="9ee9e-114">Cheques printing format.xml</span><span class="sxs-lookup"><span data-stu-id="9ee9e-114">Cheques printing format.xml</span></span>](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| <span data-ttu-id="9ee9e-115">Vállalati embléma képe</span><span class="sxs-lookup"><span data-stu-id="9ee9e-115">Company logo image</span></span>                                   | [<span data-ttu-id="9ee9e-116">Company logo.png</span><span class="sxs-lookup"><span data-stu-id="9ee9e-116">Company logo.png</span></span>](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| <span data-ttu-id="9ee9e-117">Aláírás képe</span><span class="sxs-lookup"><span data-stu-id="9ee9e-117">Signature image</span></span>                                      | [<span data-ttu-id="9ee9e-118">Signature image.png</span><span class="sxs-lookup"><span data-stu-id="9ee9e-118">Signature image.png</span></span>](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| <span data-ttu-id="9ee9e-119">Alternatív aláírási kép</span><span class="sxs-lookup"><span data-stu-id="9ee9e-119">Alternative signature image</span></span>                          | [<span data-ttu-id="9ee9e-120">Signature image 2.png</span><span class="sxs-lookup"><span data-stu-id="9ee9e-120">Signature image 2.png</span></span>](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| <span data-ttu-id="9ee9e-121">Microsoft Word sablon a kifizetési csekkek nyomtatásához</span><span class="sxs-lookup"><span data-stu-id="9ee9e-121">Microsoft Word template for printing payment checks</span></span>  | [<span data-ttu-id="9ee9e-122">Cheque template Word.docx</span><span class="sxs-lookup"><span data-stu-id="9ee9e-122">Cheque template Word.docx</span></span>](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a><span data-ttu-id="9ee9e-123">Az előfeltételek ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="9ee9e-123">Verify prerequisites</span></span>  
 1. <span data-ttu-id="9ee9e-124">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-124">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="9ee9e-125">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-125">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="9ee9e-126">Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-126">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>   
 3. <span data-ttu-id="9ee9e-127">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-127">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="9ee9e-128">Új ER-modellkonfiguráció hozzáadása</span><span class="sxs-lookup"><span data-stu-id="9ee9e-128">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="9ee9e-129">Új modell létrehozása esetén betöltheti a korábban mentett ER modellkonfigurációs fájlt (Model for cheques.xml).</span><span class="sxs-lookup"><span data-stu-id="9ee9e-129">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="9ee9e-130">Ez a fájl tartalmazza a fizetési csekkek mintaadatmodelljét és az adatmodell Dynamics 365 for Operations alkalmazás adatösszetevőire való leképezését.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-130">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="9ee9e-131">A verzió gyorslapon kattintson az Átváltás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-131">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="9ee9e-132">Kattintson a Betöltés XML-fájlból lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-132">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="9ee9e-133">Kattintson a Tallózás gombra, majd válassza ki a Model for cheques.xml dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-133">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="9ee9e-134">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-134">Click OK.</span></span>  
 6. <span data-ttu-id="9ee9e-135">A rendszer a betöltött modellt használja információforrásként a képeket tartalmazó Excel- és Word-dokumentumok létrehozására.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-135">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="9ee9e-136">Új ER-formátum hozzáadása</span><span class="sxs-lookup"><span data-stu-id="9ee9e-136">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="9ee9e-137">Új formátum létrehozása esetén betöltheti a korábban mentett ER-formátumkonfigurációs fájlt (Cheques printing format.xml).</span><span class="sxs-lookup"><span data-stu-id="9ee9e-137">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="9ee9e-138">A fájl a csekkek nyomtatásához használt formátum mintaelrendezését tartalmazza egy előre nyomtatott űrlap segítségével, valamint a formátum „Model for cheques” adatmodellre való leképezését.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-138">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the 'Model for cheques' data model.</span></span>   
 2. <span data-ttu-id="9ee9e-139">Kattintson az Átváltás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-139">Click Exchange.</span></span>  
 3. <span data-ttu-id="9ee9e-140">Kattintson a Betöltés XML-fájlból lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-140">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="9ee9e-141">Kattintson a Tallózás gombra, és válassza ki a Cheques printing format.xml fájlt.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-141">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="9ee9e-142">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-142">Click OK.</span></span>  
 6. <span data-ttu-id="9ee9e-143">A fastruktúrában bontsa ki ezt: „Model for cheques”.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-143">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="9ee9e-144">A fában válassza ki ezt: „Model for cheques\Cheques printing format”.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-144">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="9ee9e-145">A rendszer a betöltött formátumot használja képeket tartalmazó Excel- és Word-dokumentumok létrehozására.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-145">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="9ee9e-146">ER felhasználói paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9ee9e-146">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="9ee9e-147">Kattintson a Konfigurációk lehetőségre a Művelet Panelen.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-147">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="9ee9e-148">Kattintson a Felhasználói paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-148">Click User parameters.</span></span>  
 3. <span data-ttu-id="9ee9e-149">Válassza az Igen lehetőséget a Beállítások futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-149">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="9ee9e-150">Kapcsolja be a „Vázlat futtatása” jelzőt a kijelölt formátum piszkozatverziójának elindításához a befejezett verzió helyett.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-150">Turn on the 'Run draft' flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="9ee9e-151">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-151">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="9ee9e-152">Készpénz- és bankkezelési paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9ee9e-152">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="9ee9e-153">Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-153">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="9ee9e-154">A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „USMF OPER” értékkel.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-154">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="9ee9e-155">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-155">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="9ee9e-156">Kattintson az ellenőrzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-156">Click Check.</span></span>  
 5. <span data-ttu-id="9ee9e-157">Bontsa ki a Beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-157">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="9ee9e-158">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-158">Click Edit.</span></span>  
 7. <span data-ttu-id="9ee9e-159">Válassza ki az Igen lehetőséget a Vállalat emblémája mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-159">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="9ee9e-160">Kattintson a Vállalat emblémája lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-160">Click Company logo.</span></span>  
 9. <span data-ttu-id="9ee9e-161">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-161">Click Change.</span></span>  
 10. <span data-ttu-id="9ee9e-162">Kattintson a Tallózás gombra, és válassza ki a korábban letöltött fájlt: Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-162">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="9ee9e-163">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-163">Click Save.</span></span>  
 12. <span data-ttu-id="9ee9e-164">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-164">Close the page.</span></span>  
 13. <span data-ttu-id="9ee9e-165">Bontsa ki az Aláírás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-165">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="9ee9e-166">Válassza az Igen lehetőséget az Első aláírás nyomtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-166">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="9ee9e-167">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-167">Click Change.</span></span>  
 16. <span data-ttu-id="9ee9e-168">Kattintson a Tallózás gombra, és válassza ki a korábban letöltött fájlt: Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-168">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="9ee9e-169">Bontsa ki a Példányok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-169">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="9ee9e-170">A Vízjel mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-170">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="9ee9e-171">Válassza az Igen beállítást az Exportálási formátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-171">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="9ee9e-172">Válassza a „Csekkek nyomtatása képernyő” konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-172">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="9ee9e-173">Ekkor a rendszer a kijelölt ER-formátumot használja csekkek nyomtatására.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-173">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="9ee9e-174">Kattintson a Csatolás elemre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-174">Click Attach.</span></span>  
 23. <span data-ttu-id="9ee9e-175">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-175">Click New.</span></span>  
 24. <span data-ttu-id="9ee9e-176">Kattintson a Fájlra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-176">Click File.</span></span>  
 25. <span data-ttu-id="9ee9e-177">Kattintson a Tallózás gombra, és válassza ki a korábban letöltött fájlt: Signature image2.png.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-177">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="9ee9e-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-178">Close the page.</span></span>  
 27. <span data-ttu-id="9ee9e-179">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-179">Close the page.</span></span>  
 28. <span data-ttu-id="9ee9e-180">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-180">Close the page.</span></span>  
 29. <span data-ttu-id="9ee9e-181">Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-181">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="9ee9e-182">AZ Ellenőrző tranzakció létrehozásának engedélyezése az inaktív bankszámláknál: mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-182">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="9ee9e-183">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-183">Click Save.</span></span>  
 32. <span data-ttu-id="9ee9e-184">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="9ee9e-184">Close the page.</span></span>  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
