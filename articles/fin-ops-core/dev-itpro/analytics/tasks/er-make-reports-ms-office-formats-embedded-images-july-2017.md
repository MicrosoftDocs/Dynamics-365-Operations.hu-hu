---
title: Konfigurációk tervezése jelentések készítéséshez Office formátumban, beágyazott képekkel
description: Ez a témakör azt mutatja be, hogyan tervezhetők konfigurációk beágyazott képeket tartalmazó Excel- és Word-formátumú elektronikus dokumentumok létrehozására.
author: NickSelin
ms.date: 01/23/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e1bafc919d73c9e603935398563bb26e8fb277d3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751058"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="7e393-103">Konfigurációk tervezése jelentések készítéséshez Office formátumban, beágyazott képekkel</span><span class="sxs-lookup"><span data-stu-id="7e393-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7e393-104">A jelen eljárás lépéseinek lezáráshoz először hajtsa végre az „ER – Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="7e393-104">To complete the steps in this procedure, first complete the procedure, "ER Create a configuration provider and mark it as active."</span></span> <span data-ttu-id="7e393-105">Ez az eljárás bemutatja, hogyan tervezhetők elektronikus jelentési (ER) konfigurációk beágyazott képeket tartalmazó Microsoft Excel vagy Word-dokumentumok létrehozására.</span><span class="sxs-lookup"><span data-stu-id="7e393-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="7e393-106">Ebben az eljárásban a szükséges ER konfigurációkat a Litware, Inc. mintavállalathoz hozza létre. Ezek a lépések az USMF adatkészlet segítségével tölthetők be.</span><span class="sxs-lookup"><span data-stu-id="7e393-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="7e393-107">Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült.</span><span class="sxs-lookup"><span data-stu-id="7e393-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="7e393-108">Mielőtt elkezdené, töltse le és mentse el a [Képek és alakzatok beágyazása az ER használatával generált dokumentumokba](../electronic-reporting-embed-images-shapes.md) súgótémában felsorolt fájlokat.</span><span class="sxs-lookup"><span data-stu-id="7e393-108">Before you begin, download and save the files listed in the Help topic, [Embed images and shapes in documents that you generate by using ER](../electronic-reporting-embed-images-shapes.md).</span></span> <span data-ttu-id="7e393-109">A fájlok: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png és Cheque template Word.docx.</span><span class="sxs-lookup"><span data-stu-id="7e393-109">The files are: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png, and Cheque template Word.docx.</span></span>

## <a name="verify-prerequisites"></a><span data-ttu-id="7e393-110">Az előfeltételek ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="7e393-110">Verify prerequisites</span></span>  
 1. <span data-ttu-id="7e393-111">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="7e393-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="7e393-112">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és aktívként van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="7e393-112">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="7e393-113">Ha nem látja a konfigurációszolgáltatót, végezze el a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="7e393-113">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>   
 3. <span data-ttu-id="7e393-114">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e393-114">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="7e393-115">Új ER-modellkonfiguráció hozzáadása</span><span class="sxs-lookup"><span data-stu-id="7e393-115">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="7e393-116">Új modell létrehozása esetén betöltheti a korábban mentett ER modellkonfigurációs fájlt (Model for cheques.xml).</span><span class="sxs-lookup"><span data-stu-id="7e393-116">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="7e393-117">Ez a fájl tartalmazza a fizetési csekkek mintaadatmodelljét és az adatmodell Dynamics 365 for Operations alkalmazás adatösszetevőire való leképezését.</span><span class="sxs-lookup"><span data-stu-id="7e393-117">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="7e393-118">A verzió gyorslapon kattintson az Átváltás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e393-118">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="7e393-119">Kattintson a Betöltés XML-fájlból lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e393-119">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="7e393-120">Kattintson a Tallózás gombra, majd válassza ki a Model for cheques.xml dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="7e393-120">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="7e393-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7e393-121">Click OK.</span></span>  
 6. <span data-ttu-id="7e393-122">A rendszer a betöltött modellt használja információforrásként a képeket tartalmazó Excel- és Word-dokumentumok létrehozására.</span><span class="sxs-lookup"><span data-stu-id="7e393-122">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="7e393-123">Új ER-formátum hozzáadása</span><span class="sxs-lookup"><span data-stu-id="7e393-123">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="7e393-124">Új formátum létrehozása esetén betöltheti a korábban mentett ER-formátumkonfigurációs fájlt (Cheques printing format.xml).</span><span class="sxs-lookup"><span data-stu-id="7e393-124">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="7e393-125">A fájl a csekkek nyomtatásához használt formátum mintaelrendezését tartalmazza egy előre nyomtatott űrlap segítségével, valamint a formátum „Model for cheques” adatmodellre való leképezését.</span><span class="sxs-lookup"><span data-stu-id="7e393-125">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the 'Model for cheques' data model.</span></span>   
 2. <span data-ttu-id="7e393-126">Kattintson az Átváltás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e393-126">Click Exchange.</span></span>  
 3. <span data-ttu-id="7e393-127">Kattintson a Betöltés XML-fájlból lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e393-127">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="7e393-128">Kattintson a Tallózás gombra, és válassza ki a Cheques printing format.xml fájlt.</span><span class="sxs-lookup"><span data-stu-id="7e393-128">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="7e393-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7e393-129">Click OK.</span></span>  
 6. <span data-ttu-id="7e393-130">A fastruktúrában bontsa ki ezt: „Model for cheques”.</span><span class="sxs-lookup"><span data-stu-id="7e393-130">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="7e393-131">A fában válassza ki ezt: „Model for cheques\Cheques printing format”.</span><span class="sxs-lookup"><span data-stu-id="7e393-131">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="7e393-132">A rendszer a betöltött formátumot használja képeket tartalmazó Excel- és Word-dokumentumok létrehozására.</span><span class="sxs-lookup"><span data-stu-id="7e393-132">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="7e393-133">ER felhasználói paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="7e393-133">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="7e393-134">Kattintson a Konfigurációk lehetőségre a Művelet Panelen.</span><span class="sxs-lookup"><span data-stu-id="7e393-134">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="7e393-135">Kattintson a Felhasználói paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e393-135">Click User parameters.</span></span>  
 3. <span data-ttu-id="7e393-136">Válassza az Igen lehetőséget a Beállítások futtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="7e393-136">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="7e393-137">Kapcsolja be a „Vázlat futtatása” jelzőt a kijelölt formátum piszkozatverziójának elindításához a befejezett verzió helyett.</span><span class="sxs-lookup"><span data-stu-id="7e393-137">Turn on the 'Run draft' flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="7e393-138">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7e393-138">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="7e393-139">Készpénz- és bankkezelési paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="7e393-139">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="7e393-140">Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.</span><span class="sxs-lookup"><span data-stu-id="7e393-140">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="7e393-141">A gyorsszűrő használatával szűrjön rá a Bankszámla mezőre a „USMF OPER” értékkel.</span><span class="sxs-lookup"><span data-stu-id="7e393-141">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="7e393-142">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="7e393-142">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="7e393-143">Kattintson az ellenőrzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e393-143">Click Check.</span></span>  
 5. <span data-ttu-id="7e393-144">Bontsa ki a Beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7e393-144">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="7e393-145">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e393-145">Click Edit.</span></span>  
 7. <span data-ttu-id="7e393-146">Válassza ki az Igen lehetőséget a Vállalat emblémája mezőben.</span><span class="sxs-lookup"><span data-stu-id="7e393-146">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="7e393-147">Kattintson a Vállalat emblémája lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e393-147">Click Company logo.</span></span>  
 9. <span data-ttu-id="7e393-148">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="7e393-148">Click Change.</span></span>  
 10. <span data-ttu-id="7e393-149">Kattintson a Tallózás gombra, és válassza ki a korábban letöltött fájlt: Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="7e393-149">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="7e393-150">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7e393-150">Click Save.</span></span>  
 12. <span data-ttu-id="7e393-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7e393-151">Close the page.</span></span>  
 13. <span data-ttu-id="7e393-152">Bontsa ki az Aláírás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7e393-152">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="7e393-153">Válassza az Igen lehetőséget az Első aláírás nyomtatása mezőben.</span><span class="sxs-lookup"><span data-stu-id="7e393-153">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="7e393-154">Kattintson a Módosítás gombra.</span><span class="sxs-lookup"><span data-stu-id="7e393-154">Click Change.</span></span>  
 16. <span data-ttu-id="7e393-155">Kattintson a Tallózás gombra, és válassza ki a korábban letöltött fájlt: Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="7e393-155">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="7e393-156">Bontsa ki a Példányok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7e393-156">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="7e393-157">A Vízjel mezőben válasszon egy lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e393-157">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="7e393-158">Válassza az Igen beállítást az Exportálási formátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="7e393-158">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="7e393-159">Válassza a „Csekkek nyomtatása képernyő” konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="7e393-159">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="7e393-160">Ekkor a rendszer a kijelölt ER-formátumot használja csekkek nyomtatására.</span><span class="sxs-lookup"><span data-stu-id="7e393-160">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="7e393-161">Kattintson a Csatolás elemre.</span><span class="sxs-lookup"><span data-stu-id="7e393-161">Click Attach.</span></span>  
 23. <span data-ttu-id="7e393-162">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7e393-162">Click New.</span></span>  
 24. <span data-ttu-id="7e393-163">Kattintson a Fájlra.</span><span class="sxs-lookup"><span data-stu-id="7e393-163">Click File.</span></span>  
 25. <span data-ttu-id="7e393-164">Kattintson a Tallózás gombra, és válassza ki a korábban letöltött fájlt: Signature image2.png.</span><span class="sxs-lookup"><span data-stu-id="7e393-164">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="7e393-165">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7e393-165">Close the page.</span></span>  
 27. <span data-ttu-id="7e393-166">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7e393-166">Close the page.</span></span>  
 28. <span data-ttu-id="7e393-167">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7e393-167">Close the page.</span></span>  
 29. <span data-ttu-id="7e393-168">Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="7e393-168">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="7e393-169">AZ Ellenőrző tranzakció létrehozásának engedélyezése az inaktív bankszámláknál: mezőben válassza az Igen lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7e393-169">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="7e393-170">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="7e393-170">Click Save.</span></span>  
 32. <span data-ttu-id="7e393-171">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7e393-171">Close the page.</span></span>  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]