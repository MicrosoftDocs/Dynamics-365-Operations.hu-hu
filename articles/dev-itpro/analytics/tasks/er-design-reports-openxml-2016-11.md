--- 
title: "Konfiguráció tervezése OpenXML formátumú jelentések létrehozására elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy új Elektronikus jelentés (ER) konfigurációt, amely tartalmazza az elektronikus dokumentumok létrehozására vonatkozó sablont az OPENXML formátumban."
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 04def14ddf9b079005bf11acbcaf64b21aa80fdb
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="design-a-configuration-for-generating-reports-in-openxml-format-for-electronic-reporting-er"></a><span data-ttu-id="81a39-103">Konfiguráció tervezése OpenXML formátumú jelentések létrehozására elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="81a39-103">Design a configuration for generating reports in OpenXML format for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="81a39-104">A következő lépések leírják, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy új Elektronikus jelentés (ER) konfigurációt, amely tartalmazza az elektronikus dokumentumok létrehozására vonatkozó sablont az OPENXML formátumban.</span><span class="sxs-lookup"><span data-stu-id="81a39-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="81a39-105">Ezt a konfigurációt a szállítói kifizetések feldolgozására használják.</span><span class="sxs-lookup"><span data-stu-id="81a39-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="81a39-106">Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket a GBSI vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="81a39-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="81a39-107">Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="81a39-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="81a39-108">Egy Excel-fájllal is rendelkeznie kell, amelyet importálni kell a sablon létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="81a39-108">You must also have an Excel file which will be imported when creating the template.</span></span> <span data-ttu-id="81a39-109">A fájl elérési helye: https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx</span><span class="sxs-lookup"><span data-stu-id="81a39-109">This file can be accessed from:  https://msdynamics.blob.core.windows.net/media/2016/04/SampleVendPaymWsReport.xlsx</span></span>


## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="81a39-110">A Fizetési adatmodell-konfiguráció feltöltése</span><span class="sxs-lookup"><span data-stu-id="81a39-110">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="81a39-111">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="81a39-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="81a39-112">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="81a39-112">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="81a39-113">Válassza ki a konfigurációs szolgáltatót a Litware, Inc. minta vállalatra vonatkozóan. Ha nem látja a konfigurációs szolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="81a39-113">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="81a39-114">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="81a39-114">Click Set active.</span></span>
4. <span data-ttu-id="81a39-115">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-115">Click Repositories.</span></span>
    * <span data-ttu-id="81a39-116">Ha rendelkezésre áll, válassza ki az üzemi erőforrások típusának tárolóját.</span><span class="sxs-lookup"><span data-stu-id="81a39-116">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="81a39-117">Ha rendelkezésre áll, hagyja ki a következő, az új tárház létrehozására vonatkozó lépéseket.</span><span class="sxs-lookup"><span data-stu-id="81a39-117">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="81a39-118">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="81a39-118">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="81a39-119">A Konfiguráció tárházának típusa mezőbe írja be az „Üzemi erőforrások” szöveget.</span><span class="sxs-lookup"><span data-stu-id="81a39-119">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="81a39-120">Kattintson a Tárház létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-120">Click Create repository.</span></span>
8. <span data-ttu-id="81a39-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-121">Click OK.</span></span>
9. <span data-ttu-id="81a39-122">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-122">Click Open.</span></span>
10. <span data-ttu-id="81a39-123">A fastruktúrában válassza ki a „Fizetési modell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-123">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="81a39-124">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-124">Click Import.</span></span>
    * <span data-ttu-id="81a39-125">Ezen adatmodell importálása.</span><span class="sxs-lookup"><span data-stu-id="81a39-125">Import this data model.</span></span> <span data-ttu-id="81a39-126">Ezt a rendszer az új konfigurációban szereplő adatforrásként használja.</span><span class="sxs-lookup"><span data-stu-id="81a39-126">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="81a39-127">Hagyja ki ezt a lépést, ha ezt a konfigurációt már importálta.</span><span class="sxs-lookup"><span data-stu-id="81a39-127">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="81a39-128">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-128">Click Yes.</span></span>
13. <span data-ttu-id="81a39-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="81a39-129">Close the page.</span></span>
14. <span data-ttu-id="81a39-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="81a39-130">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="81a39-131">Új formátumkonfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="81a39-131">Create a new format configuration</span></span>
1. <span data-ttu-id="81a39-132">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-132">Click Reporting configurations.</span></span>
2. <span data-ttu-id="81a39-133">A fastruktúrában válassza ki a „Fizetési modell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-133">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="81a39-134">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="81a39-134">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="81a39-135">Az Új mezőbe írja be a „PaymentModel modellen alapuló formátum” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="81a39-135">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="81a39-136">Hozzon létre egy PaymentModel adatmodellen alapuló formátumot.</span><span class="sxs-lookup"><span data-stu-id="81a39-136">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="81a39-137">A Név mezőbe írja be a „Minta munkalap jelentés” szöveget.</span><span class="sxs-lookup"><span data-stu-id="81a39-137">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="81a39-138">Minta munkalap jelentés</span><span class="sxs-lookup"><span data-stu-id="81a39-138">Sample worksheet report</span></span>  
6. <span data-ttu-id="81a39-139">A Leírás mezőben írja be a „Minta munkalap jelentés a szállítók kifizetéseihez” szöveget.</span><span class="sxs-lookup"><span data-stu-id="81a39-139">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="81a39-140">Minta munkalap jelentés a szállítók kifizetéseihez.</span><span class="sxs-lookup"><span data-stu-id="81a39-140">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="81a39-141">Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="81a39-141">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="81a39-142">Válassza ki a „CustomerCreditTransferInitiation” definíciót.</span><span class="sxs-lookup"><span data-stu-id="81a39-142">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="81a39-143">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-143">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="81a39-144">Új dokumentum tervezése az OPENXML munkalapformátumban</span><span class="sxs-lookup"><span data-stu-id="81a39-144">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="81a39-145">A fastruktúrában válassza ki a „Fizetési modell\Minta munkalap jelentés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-145">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="81a39-146">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="81a39-146">Click Designer.</span></span>
3. <span data-ttu-id="81a39-147">A Művelet panelen kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-147">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="81a39-148">Kattintson az Importálás a Microsoft Excel programból lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-148">Click Import from Excel.</span></span>
5. <span data-ttu-id="81a39-149">Kattintson a Mellékletek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-149">Click Attachments.</span></span>
    * <span data-ttu-id="81a39-150">A meglévő Excel dokumentum sablonként történő csatolása.</span><span class="sxs-lookup"><span data-stu-id="81a39-150">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="81a39-151">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-151">Click New.</span></span>
7. <span data-ttu-id="81a39-152">Kattintson a Fájlra.</span><span class="sxs-lookup"><span data-stu-id="81a39-152">Click File.</span></span>
    * <span data-ttu-id="81a39-153">Mutasson a meglévő Excel-fájlra.</span><span class="sxs-lookup"><span data-stu-id="81a39-153">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="81a39-154">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="81a39-154">Close the page.</span></span>
9. <span data-ttu-id="81a39-155">A Sablon mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="81a39-155">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="81a39-156">Válassza ki a sablonként használandó csatolt Excel-fájlt.</span><span class="sxs-lookup"><span data-stu-id="81a39-156">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="81a39-157">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-157">Click OK.</span></span>
    * <span data-ttu-id="81a39-158">Vegye figyelembe, hogy az ER-formátum összetevőit a rendszer a hivatkozó Microsoft Excel-dokumentum (más néven tartományok) struktúráján alapuló tervezési formátumban hozta létre.</span><span class="sxs-lookup"><span data-stu-id="81a39-158">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="81a39-159">Egy új adatforrás létrehozása a pénznemkódok alapján történő összesítés kiszámításához</span><span class="sxs-lookup"><span data-stu-id="81a39-159">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="81a39-160">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="81a39-160">Click the Mapping tab.</span></span>
2. <span data-ttu-id="81a39-161">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="81a39-161">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="81a39-162">A fastruktúrában válassza ki a „Funkciók\Csoportosítás alapja ” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-162">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="81a39-163">A Név mezőbe írja be a „Kifizetés pénzneme” szöveget.</span><span class="sxs-lookup"><span data-stu-id="81a39-163">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="81a39-164">Kifizetés pénzneme</span><span class="sxs-lookup"><span data-stu-id="81a39-164">PaymentByCurrency</span></span>  
5. <span data-ttu-id="81a39-165">Kattintson a Csoport szerkesztési szempontja lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-165">Click Edit group by.</span></span>
6. <span data-ttu-id="81a39-166">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-166">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="81a39-167">A fán válassza ki a következőt: „model\Payments”.</span><span class="sxs-lookup"><span data-stu-id="81a39-167">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="81a39-168">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-168">Click Add field to.</span></span>
9. <span data-ttu-id="81a39-169">Kattintson a Csoportosítandó lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-169">Click What to group.</span></span>
10. <span data-ttu-id="81a39-170">A fában bontsa ki a „model\Payments” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-170">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="81a39-171">A fastruktúrában válassza ki a „Modell\Kifizetések\Pénznem” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-171">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="81a39-172">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-172">Click Add field to.</span></span>
13. <span data-ttu-id="81a39-173">Kattintson a Csoportosított mezők lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-173">Click Grouped fields.</span></span>
14. <span data-ttu-id="81a39-174">A fastruktúrában válassza ki a „Modell\Kifizetések\Rendelkezésben megadott összeg (InstructedAmount)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-174">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="81a39-175">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-175">Click Add field to.</span></span>
16. <span data-ttu-id="81a39-176">Kattintson az Aggregációs mezők lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-176">Click Aggregation fields.</span></span>
17. <span data-ttu-id="81a39-177">Válassza ki valamelyik lehetőséget a Módszer mezőben.</span><span class="sxs-lookup"><span data-stu-id="81a39-177">In the Method field, select an option.</span></span>
    * <span data-ttu-id="81a39-178">Válassza az Összeg aggregáció funkciót.</span><span class="sxs-lookup"><span data-stu-id="81a39-178">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="81a39-179">A Név mezőbe írja be a „TotalInstructuredAmount” szöveget.</span><span class="sxs-lookup"><span data-stu-id="81a39-179">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="81a39-180">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="81a39-180">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="81a39-181">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-181">Click Save.</span></span>
20. <span data-ttu-id="81a39-182">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="81a39-182">Close the page.</span></span>
21. <span data-ttu-id="81a39-183">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-183">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="81a39-184">Formátum-összetevők leképezése az adatforrásokhoz</span><span class="sxs-lookup"><span data-stu-id="81a39-184">Map format components to data sources</span></span>
1. <span data-ttu-id="81a39-185">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-185">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="81a39-186">A fában bontsa ki a „model\Payments” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-186">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="81a39-187">A fastruktúrában bontsa ki a „Modell\Kifizetések\Kezdeményező fél(InitiatingParty)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-187">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="81a39-188">A fastruktúrában válassza ki a „Modell\Kifizetések\Kezdeményező fél(InitiatingParty)\Név” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-188">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="81a39-189">A fában bontsa ki az „Excel\Jelentésfejléc” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-189">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="81a39-190">A fában bontsa ki az „Excel\ReportHeader\CompanyName” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-190">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="81a39-191">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-191">Click Bind.</span></span>
8. <span data-ttu-id="81a39-192">A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-192">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="81a39-193">A fastruktúrában bontsa ki a „modell\Kifizetések\Hitelező\Azonosító” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-193">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="81a39-194">A fastruktúrában bontsa ki a „modell\Kifizetések\Hitelező\Azonosító\Forrásazonosító” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-194">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="81a39-195">A fában bontsa ki az „Excel\PaymLines” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-195">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="81a39-196">A fában bontsa ki az „Excel\PaymLines\VendAccountName” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-196">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="81a39-197">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-197">Click Bind.</span></span>
14. <span data-ttu-id="81a39-198">A fán válassza ki „model\Kifizetések = Transactions\Creditor\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="81a39-198">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="81a39-199">A fában válassza ki az „Excel\PaymLines\VendName” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-199">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="81a39-200">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-200">Click Bind.</span></span>
17. <span data-ttu-id="81a39-201">A fastruktúrában bontsa ki a „modell\kifizetések\Hitelező ügynöke(CreditorAccount)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-201">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="81a39-202">A fastruktúrában válassza ki a „modell\kifizetések\Hitelező ügynöke(CreditorAccount)\Név” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-202">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="81a39-203">A fában válassza ki az „Excel\PaymLines\Bank” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-203">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="81a39-204">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-204">Click Bind.</span></span>
21. <span data-ttu-id="81a39-205">A fastruktúrában válassza ki „modell\Kifizetések\Hitelező ügynöke(CreditorAgent)\Útvonalszám(RoutingNumber)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-205">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="81a39-206">A fában válassza ki az „Excel\PaymLines\RoutingNumber” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-206">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="81a39-207">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-207">Click Bind.</span></span>
24. <span data-ttu-id="81a39-208">A fában bontsa ki a következőt: „model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="81a39-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="81a39-209">A fában bontsa ki a következőt: „model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="81a39-209">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="81a39-210">A fastruktúrában válassza ki a „modell\Kifizetések\Hitelező számlája(CreditorAccount)\Azonosító\Szám” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-210">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="81a39-211">A fában válassza ki az „Excel\PaymLines\AccountNumber” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-211">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="81a39-212">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-212">Click Bind.</span></span>
29. <span data-ttu-id="81a39-213">A fastruktúrában válassza ki a „Modell\Kifizetések\Rendelkezésben megadott összeg (InstructedAmount)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-213">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="81a39-214">A fában válassza ki az „Excel\PaymLines\Tartozik” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-214">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="81a39-215">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-215">Click Bind.</span></span>
32. <span data-ttu-id="81a39-216">A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-216">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="81a39-217">A fában bontsa ki a következőt: „model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="81a39-217">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="81a39-218">A fastruktúrában bontsa ki a „modell\kifizetések\Hitelező ügynöke(CreditorAccount)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-218">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="81a39-219">A fastruktúrában válassza ki a „Modell\Kifizetések\Pénznem” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-219">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="81a39-220">A fában válassza ki az „Excel\PaymLines\Pénznem” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-220">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="81a39-221">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-221">Click Bind.</span></span>
38. <span data-ttu-id="81a39-222">Bontsa ki a fastruktúrában a „Kifizetés pénzneme” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-222">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="81a39-223">Bontsa ki a fastruktúrában a „Kifizetés pénzneme\Csoportosítva” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-223">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="81a39-224">A fastruktúrában válassza ki a „Kifizetés pénzneme\Csoportosítva\Pénznem” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-224">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="81a39-225">A fában bontsa ki az „Excel\SummaryLines” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-225">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="81a39-226">A fában válassza ki az „Excel\SummaryLines\SummaryCurrency” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-226">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="81a39-227">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-227">Click Bind.</span></span>
44. <span data-ttu-id="81a39-228">Bontsa ki a fastruktúrában a„Kifizetés pénzneme\Összesített” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-228">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="81a39-229">A fastruktúrában válassza ki a „Kifizetés pénzneme\Összesített\TotalInstructuredAmount” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-229">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="81a39-230">A fában válassza ki az „Excel\SummaryLines\SummaryAmount” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-230">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="81a39-231">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-231">Click Bind.</span></span>
48. <span data-ttu-id="81a39-232">A fastruktúrában válassza ki a „Kifizetés pénzneme” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="81a39-232">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="81a39-233">A fastruktúrában válassza ki a következőt: „Excel\SummaryLines”.</span><span class="sxs-lookup"><span data-stu-id="81a39-233">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="81a39-234">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-234">Click Bind.</span></span>
51. <span data-ttu-id="81a39-235">A fán válassza ki a következőt: „model\Payments”.</span><span class="sxs-lookup"><span data-stu-id="81a39-235">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="81a39-236">A fában válassza ki az „Excel\PaymLines” elemet.</span><span class="sxs-lookup"><span data-stu-id="81a39-236">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="81a39-237">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-237">Click Bind.</span></span>
54. <span data-ttu-id="81a39-238">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-238">Click Save.</span></span>
55. <span data-ttu-id="81a39-239">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="81a39-239">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="81a39-240">A létrehozott konfiguráció használata a fizetések feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="81a39-240">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="81a39-241">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="81a39-241">Click Change status.</span></span>
2. <span data-ttu-id="81a39-242">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-242">Click Complete.</span></span>
3. <span data-ttu-id="81a39-243">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-243">Click OK.</span></span>
4. <span data-ttu-id="81a39-244">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="81a39-244">Close the page.</span></span>
5. <span data-ttu-id="81a39-245">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="81a39-245">Close the page.</span></span>
6. <span data-ttu-id="81a39-246">Ugorjon a Kötelezettségek > Kifizetés beállítása > Fizetési módok pontra.</span><span class="sxs-lookup"><span data-stu-id="81a39-246">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="81a39-247">A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Fizetési mezőben az „Elektronikus” érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="81a39-247">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="81a39-248">Elektronikus</span><span class="sxs-lookup"><span data-stu-id="81a39-248">Electronic</span></span>  
8. <span data-ttu-id="81a39-249">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-249">Click Edit.</span></span>
9. <span data-ttu-id="81a39-250">Bontsa ki a Fájlformátumok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="81a39-250">Expand the File formats section.</span></span>
10. <span data-ttu-id="81a39-251">Válassza az Igen beállítást az Általános elektronikus jelentéskészítés mezőben.</span><span class="sxs-lookup"><span data-stu-id="81a39-251">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="81a39-252">Az Exportformátum konfigurációja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="81a39-252">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="81a39-253">Válassza ki a "Minta munkalap jelentés" konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="81a39-253">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="81a39-254">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-254">Click Save.</span></span>
13. <span data-ttu-id="81a39-255">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="81a39-255">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="81a39-256">A létrehozott konfiguráció használata a Kifizetési naplók feldolgozásának vizsgálatához</span><span class="sxs-lookup"><span data-stu-id="81a39-256">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="81a39-257">Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.</span><span class="sxs-lookup"><span data-stu-id="81a39-257">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="81a39-258">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-258">Click New.</span></span>
    * <span data-ttu-id="81a39-259">Hozzon létre egy új kifizetési naplót.</span><span class="sxs-lookup"><span data-stu-id="81a39-259">Create a new payment journal.</span></span>  
3. <span data-ttu-id="81a39-260">A Név mezőbe írja be: „VendPay”.</span><span class="sxs-lookup"><span data-stu-id="81a39-260">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="81a39-261">VendPay</span><span class="sxs-lookup"><span data-stu-id="81a39-261">VendPay</span></span>  
4. <span data-ttu-id="81a39-262">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="81a39-262">Click Lines.</span></span>
5. <span data-ttu-id="81a39-263">A Számla mezőben adja meg a „GB_SI_000001” értékeket.</span><span class="sxs-lookup"><span data-stu-id="81a39-263">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="81a39-264">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="81a39-264">GB_SI_000001</span></span>  
6. <span data-ttu-id="81a39-265">Állítsa a Terhelést „1000” értékre.</span><span class="sxs-lookup"><span data-stu-id="81a39-265">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="81a39-266">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="81a39-266">Click New.</span></span>
8. <span data-ttu-id="81a39-267">A Számla mezőben adja meg a „GB_SI_000005” értékeket.</span><span class="sxs-lookup"><span data-stu-id="81a39-267">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="81a39-268">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="81a39-268">GB_SI_000005</span></span>  
9. <span data-ttu-id="81a39-269">Állítsa a Terhelést „2000” értékre.</span><span class="sxs-lookup"><span data-stu-id="81a39-269">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="81a39-270">A Pénznem mezőben írja be az „EUR” szöveget.</span><span class="sxs-lookup"><span data-stu-id="81a39-270">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="81a39-271">HUF</span><span class="sxs-lookup"><span data-stu-id="81a39-271">EUR</span></span>  
11. <span data-ttu-id="81a39-272">Az Ellenszámla mezőben adja meg a „GBSI OPER” értékeket.</span><span class="sxs-lookup"><span data-stu-id="81a39-272">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="81a39-273">GBSI MŰV.</span><span class="sxs-lookup"><span data-stu-id="81a39-273">GBSI OPER</span></span>  
12. <span data-ttu-id="81a39-274">A Fizetési mód mezőbe írja be az „Elektronikus” szöveget.</span><span class="sxs-lookup"><span data-stu-id="81a39-274">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="81a39-275">Elektronikus</span><span class="sxs-lookup"><span data-stu-id="81a39-275">Electronic</span></span>  
13. <span data-ttu-id="81a39-276">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-276">Click Save.</span></span>
14. <span data-ttu-id="81a39-277">Kattintson a Kifizetések létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="81a39-277">Click Generate payments.</span></span>
15. <span data-ttu-id="81a39-278">A Fizetési mód mezőbe írja be az „Elektronikus” szöveget.</span><span class="sxs-lookup"><span data-stu-id="81a39-278">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="81a39-279">Elektronikus</span><span class="sxs-lookup"><span data-stu-id="81a39-279">Electronic</span></span>  
16. <span data-ttu-id="81a39-280">A Fájlnév mezőbe írja be a következőt: „Fizetések”.</span><span class="sxs-lookup"><span data-stu-id="81a39-280">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="81a39-281">Például írja be a Kifizetések szöveget.</span><span class="sxs-lookup"><span data-stu-id="81a39-281">For example, type Payments.</span></span>  
17. <span data-ttu-id="81a39-282">A Bankszámla mezőben írja be a „GBSI OPER” szöveget.</span><span class="sxs-lookup"><span data-stu-id="81a39-282">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="81a39-283">GBSI MŰV.</span><span class="sxs-lookup"><span data-stu-id="81a39-283">GBSI OPER</span></span>  
18. <span data-ttu-id="81a39-284">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-284">Click OK.</span></span>
19. <span data-ttu-id="81a39-285">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="81a39-285">Click OK.</span></span>
    * <span data-ttu-id="81a39-286">Tekintse át a létrehozott munkalapot, többek között a kifizetési sorok részleteit, valamint az ebben a fizetési üzenetben használt pénznemkódra vonatkozó összegeket is.</span><span class="sxs-lookup"><span data-stu-id="81a39-286">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  

