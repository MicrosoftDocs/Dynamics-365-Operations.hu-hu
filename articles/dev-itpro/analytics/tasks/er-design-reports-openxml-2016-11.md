--- 
title: "ER konfigurációk tervezése jelentések OpenXML-formátumú előállításához"
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b42cfe36c57a9526e585bbad0fcd31ff60b90397
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---
# <a name="design-er-configurations-to-generate-reports-in-openxml-format"></a><span data-ttu-id="0e010-103">ER konfigurációk tervezése jelentések OpenXML-formátumú előállításához</span><span class="sxs-lookup"><span data-stu-id="0e010-103">Design ER configurations to generate reports in OpenXML format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0e010-104">A következő lépések leírják, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy új Elektronikus jelentés (ER) konfigurációt, amely tartalmazza az elektronikus dokumentumok létrehozására vonatkozó sablont az OPENXML formátumban.</span><span class="sxs-lookup"><span data-stu-id="0e010-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains a template for generating electronic documents in OPENXML format.</span></span> <span data-ttu-id="0e010-105">Ezt a konfigurációt a szállítói kifizetések feldolgozására használják.</span><span class="sxs-lookup"><span data-stu-id="0e010-105">This configuration will be used for processing vendor payments.</span></span>



<span data-ttu-id="0e010-106">Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket a GBSI vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="0e010-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in GBSI company.</span></span>



<span data-ttu-id="0e010-107">Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="0e010-107">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span> <span data-ttu-id="0e010-108">Le kell töltenie és mentenie kell a következő Microsoft Excel-fájlt: [Kifizetési jelentés sablonja](https://go.microsoft.com/fwlink/?linkid=862266).</span><span class="sxs-lookup"><span data-stu-id="0e010-108">You must also download and save the Microsoft Excel file, [Template of Payment Report](https://go.microsoft.com/fwlink/?linkid=862266).</span></span> 

## <a name="upload-the-payments-data-model-configuration"></a><span data-ttu-id="0e010-109">A Fizetési adatmodell-konfiguráció feltöltése</span><span class="sxs-lookup"><span data-stu-id="0e010-109">Upload the Payments data model configuration</span></span>
1. <span data-ttu-id="0e010-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="0e010-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="0e010-111">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0e010-111">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0e010-112">Válassza ki a konfigurációs szolgáltatót a Litware, Inc. minta vállalatra vonatkozóan. Ha nem látja a konfigurációs szolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0e010-112">Select the configuration provider for sample company, Litware, Inc. If you don’t see this configuration provider, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>  
3. <span data-ttu-id="0e010-113">Kattintson erre: Beállítás aktívként.</span><span class="sxs-lookup"><span data-stu-id="0e010-113">Click Set active.</span></span>
4. <span data-ttu-id="0e010-114">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-114">Click Repositories.</span></span>
    * <span data-ttu-id="0e010-115">Ha rendelkezésre áll, válassza ki az üzemi erőforrások típusának tárolóját.</span><span class="sxs-lookup"><span data-stu-id="0e010-115">Select a repository for the Operations Resources type, if available.</span></span> <span data-ttu-id="0e010-116">Ha rendelkezésre áll, hagyja ki a következő, az új tárház létrehozására vonatkozó lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0e010-116">If its available, skip the following steps about creating a new repository.</span></span>  
5. <span data-ttu-id="0e010-117">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="0e010-117">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="0e010-118">A Konfiguráció tárházának típusa mezőbe írja be az „Üzemi erőforrások” szöveget.</span><span class="sxs-lookup"><span data-stu-id="0e010-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
7. <span data-ttu-id="0e010-119">Kattintson a Tárház létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-119">Click Create repository.</span></span>
8. <span data-ttu-id="0e010-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-120">Click OK.</span></span>
9. <span data-ttu-id="0e010-121">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-121">Click Open.</span></span>
10. <span data-ttu-id="0e010-122">A fastruktúrában válassza ki a „Fizetési modell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-122">In the tree, select 'Payment model'.</span></span>
11. <span data-ttu-id="0e010-123">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-123">Click Import.</span></span>
    * <span data-ttu-id="0e010-124">Ezen adatmodell importálása.</span><span class="sxs-lookup"><span data-stu-id="0e010-124">Import this data model.</span></span> <span data-ttu-id="0e010-125">Ezt a rendszer az új konfigurációban szereplő adatforrásként használja.</span><span class="sxs-lookup"><span data-stu-id="0e010-125">It will be used as a data source in a new format configuration.</span></span> <span data-ttu-id="0e010-126">Hagyja ki ezt a lépést, ha ezt a konfigurációt már importálta.</span><span class="sxs-lookup"><span data-stu-id="0e010-126">Skip this step if this configuration has been already imported.</span></span>  
12. <span data-ttu-id="0e010-127">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-127">Click Yes.</span></span>
13. <span data-ttu-id="0e010-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e010-128">Close the page.</span></span>
14. <span data-ttu-id="0e010-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e010-129">Close the page.</span></span>

## <a name="create-a-new-format-configuration"></a><span data-ttu-id="0e010-130">Új formátumkonfiguráció létrehozása</span><span class="sxs-lookup"><span data-stu-id="0e010-130">Create a new format configuration</span></span>
1. <span data-ttu-id="0e010-131">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-131">Click Reporting configurations.</span></span>
2. <span data-ttu-id="0e010-132">A fastruktúrában válassza ki a „Fizetési modell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-132">In the tree, select 'Payment model'.</span></span>
3. <span data-ttu-id="0e010-133">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="0e010-133">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="0e010-134">Az Új mezőbe írja be a „PaymentModel modellen alapuló formátum” kifejezést.</span><span class="sxs-lookup"><span data-stu-id="0e010-134">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
    * <span data-ttu-id="0e010-135">Hozzon létre egy PaymentModel adatmodellen alapuló formátumot.</span><span class="sxs-lookup"><span data-stu-id="0e010-135">Create a format that is based on the PaymentModel data model.</span></span>  
5. <span data-ttu-id="0e010-136">A Név mezőbe írja be a „Minta munkalap jelentés” szöveget.</span><span class="sxs-lookup"><span data-stu-id="0e010-136">In the Name field, type 'Sample worksheet report'.</span></span>
    * <span data-ttu-id="0e010-137">Minta munkalap jelentés</span><span class="sxs-lookup"><span data-stu-id="0e010-137">Sample worksheet report</span></span>  
6. <span data-ttu-id="0e010-138">A Leírás mezőben írja be a „Minta munkalap jelentés a szállítók kifizetéseihez” szöveget.</span><span class="sxs-lookup"><span data-stu-id="0e010-138">In the Description field, type 'Sample worksheet report for vendors’ payments'.</span></span>
    * <span data-ttu-id="0e010-139">Minta munkalap jelentés a szállítók kifizetéseihez.</span><span class="sxs-lookup"><span data-stu-id="0e010-139">Sample worksheet report for vendors’ payments.</span></span>  
7. <span data-ttu-id="0e010-140">Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e010-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="0e010-141">Válassza ki a „CustomerCreditTransferInitiation” definíciót.</span><span class="sxs-lookup"><span data-stu-id="0e010-141">Select the 'CustomerCreditTransferInitiation' definition.</span></span>  
8. <span data-ttu-id="0e010-142">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-142">Click Create configuration.</span></span>

## <a name="design-a-new-document-in-openxml-worksheet-format"></a><span data-ttu-id="0e010-143">Új dokumentum tervezése az OPENXML munkalapformátumban</span><span class="sxs-lookup"><span data-stu-id="0e010-143">Design a new document in OPENXML worksheet format</span></span>
1. <span data-ttu-id="0e010-144">A fastruktúrában válassza ki a „Fizetési modell\Minta munkalap jelentés” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-144">In the tree, select 'Payment model\Sample worksheet report'.</span></span>
2. <span data-ttu-id="0e010-145">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="0e010-145">Click Designer.</span></span>
3. <span data-ttu-id="0e010-146">A Művelet panelen kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-146">On the Action Pane, click Import.</span></span>
4. <span data-ttu-id="0e010-147">Kattintson az Importálás a Microsoft Excel programból lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-147">Click Import from Excel.</span></span>
5. <span data-ttu-id="0e010-148">Kattintson a Mellékletek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-148">Click Attachments.</span></span>
    * <span data-ttu-id="0e010-149">A meglévő Excel dokumentum sablonként történő csatolása.</span><span class="sxs-lookup"><span data-stu-id="0e010-149">Attach the existing Excel document as a template.</span></span>  
6. <span data-ttu-id="0e010-150">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-150">Click New.</span></span>
7. <span data-ttu-id="0e010-151">Kattintson a Fájlra.</span><span class="sxs-lookup"><span data-stu-id="0e010-151">Click File.</span></span>
    * <span data-ttu-id="0e010-152">Mutasson a meglévő Excel-fájlra.</span><span class="sxs-lookup"><span data-stu-id="0e010-152">Point to the existing Excel file.</span></span>  
8. <span data-ttu-id="0e010-153">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e010-153">Close the page.</span></span>
9. <span data-ttu-id="0e010-154">A Sablon mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e010-154">In the Template field, enter or select a value.</span></span>
    * <span data-ttu-id="0e010-155">Válassza ki a sablonként használandó csatolt Excel-fájlt.</span><span class="sxs-lookup"><span data-stu-id="0e010-155">Select the attached Excel file to be used as a template.</span></span>  
10. <span data-ttu-id="0e010-156">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-156">Click OK.</span></span>
    * <span data-ttu-id="0e010-157">Vegye figyelembe, hogy az ER-formátum összetevőit a rendszer a hivatkozó Microsoft Excel-dokumentum (más néven tartományok) struktúráján alapuló tervezési formátumban hozta létre.</span><span class="sxs-lookup"><span data-stu-id="0e010-157">Note that ER format components have been created in the designing format based on the structure of the referring MS Excel document (named ranges).</span></span>  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a><span data-ttu-id="0e010-158">Egy új adatforrás létrehozása a pénznemkódok alapján történő összesítés kiszámításához</span><span class="sxs-lookup"><span data-stu-id="0e010-158">Create a new data source to calculate totals by currency codes</span></span>
1. <span data-ttu-id="0e010-159">Kattintson a Hozzárendelés fülre.</span><span class="sxs-lookup"><span data-stu-id="0e010-159">Click the Mapping tab.</span></span>
2. <span data-ttu-id="0e010-160">Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0e010-160">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="0e010-161">A fastruktúrában válassza ki a „Funkciók\Csoportosítás alapja ” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-161">In the tree, select 'Functions\Group by'.</span></span>
4. <span data-ttu-id="0e010-162">A Név mezőbe írja be a „Kifizetés pénzneme” szöveget.</span><span class="sxs-lookup"><span data-stu-id="0e010-162">In the Name field, type 'PaymentByCurrency'.</span></span>
    * <span data-ttu-id="0e010-163">Kifizetés pénzneme</span><span class="sxs-lookup"><span data-stu-id="0e010-163">PaymentByCurrency</span></span>  
5. <span data-ttu-id="0e010-164">Kattintson a Csoport szerkesztési szempontja lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-164">Click Edit group by.</span></span>
6. <span data-ttu-id="0e010-165">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-165">In the tree, expand 'model'.</span></span>
7. <span data-ttu-id="0e010-166">A fán válassza ki a következőt: „model\Payments”.</span><span class="sxs-lookup"><span data-stu-id="0e010-166">In the tree, select 'model\Payments'.</span></span>
8. <span data-ttu-id="0e010-167">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-167">Click Add field to.</span></span>
9. <span data-ttu-id="0e010-168">Kattintson a Csoportosítandó lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-168">Click What to group.</span></span>
10. <span data-ttu-id="0e010-169">A fában bontsa ki a „model\Payments” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-169">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="0e010-170">A fastruktúrában válassza ki a „Modell\Kifizetések\Pénznem” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-170">In the tree, select 'model\Payments\Currency'.</span></span>
12. <span data-ttu-id="0e010-171">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-171">Click Add field to.</span></span>
13. <span data-ttu-id="0e010-172">Kattintson a Csoportosított mezők lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-172">Click Grouped fields.</span></span>
14. <span data-ttu-id="0e010-173">A fastruktúrában válassza ki a „Modell\Kifizetések\Rendelkezésben megadott összeg (InstructedAmount)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-173">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
15. <span data-ttu-id="0e010-174">Kattintson a Mező hozzáadása a következőhöz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-174">Click Add field to.</span></span>
16. <span data-ttu-id="0e010-175">Kattintson az Aggregációs mezők lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-175">Click Aggregation fields.</span></span>
17. <span data-ttu-id="0e010-176">Válassza ki valamelyik lehetőséget a Módszer mezőben.</span><span class="sxs-lookup"><span data-stu-id="0e010-176">In the Method field, select an option.</span></span>
    * <span data-ttu-id="0e010-177">Válassza az Összeg aggregáció funkciót.</span><span class="sxs-lookup"><span data-stu-id="0e010-177">Select the SUM aggregation function.</span></span>  
18. <span data-ttu-id="0e010-178">A Név mezőbe írja be a „TotalInstructuredAmount” szöveget.</span><span class="sxs-lookup"><span data-stu-id="0e010-178">In the Name field, type 'TotalInstructuredAmount'.</span></span>
    * <span data-ttu-id="0e010-179">TotalInstructuredAmount</span><span class="sxs-lookup"><span data-stu-id="0e010-179">TotalInstructuredAmount</span></span>  
19. <span data-ttu-id="0e010-180">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-180">Click Save.</span></span>
20. <span data-ttu-id="0e010-181">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e010-181">Close the page.</span></span>
21. <span data-ttu-id="0e010-182">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-182">Click OK.</span></span>

## <a name="map-format-components-to-data-sources"></a><span data-ttu-id="0e010-183">Formátum-összetevők leképezése az adatforrásokhoz</span><span class="sxs-lookup"><span data-stu-id="0e010-183">Map format components to data sources</span></span>
1. <span data-ttu-id="0e010-184">A fában bontsa ki a „model” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-184">In the tree, expand 'model'.</span></span>
2. <span data-ttu-id="0e010-185">A fában bontsa ki a „model\Payments” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-185">In the tree, expand 'model\Payments'.</span></span>
3. <span data-ttu-id="0e010-186">A fastruktúrában bontsa ki a „Modell\Kifizetések\Kezdeményező fél(InitiatingParty)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-186">In the tree, expand 'model\Payments\Initiating Party(InitiatingParty)'.</span></span>
4. <span data-ttu-id="0e010-187">A fastruktúrában válassza ki a „Modell\Kifizetések\Kezdeményező fél(InitiatingParty)\Név” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-187">In the tree, select 'model\Payments\Initiating Party(InitiatingParty)\Name'.</span></span>
5. <span data-ttu-id="0e010-188">A fában bontsa ki az „Excel\Jelentésfejléc” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-188">In the tree, expand 'Excel\ReportHeader'.</span></span>
6. <span data-ttu-id="0e010-189">A fában bontsa ki az „Excel\ReportHeader\CompanyName” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-189">In the tree, select 'Excel\ReportHeader\CompanyName'.</span></span>
7. <span data-ttu-id="0e010-190">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-190">Click Bind.</span></span>
8. <span data-ttu-id="0e010-191">A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-191">In the tree, expand 'model\Payments\Creditor'.</span></span>
9. <span data-ttu-id="0e010-192">A fastruktúrában bontsa ki a „modell\Kifizetések\Hitelező\Azonosító” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-192">In the tree, expand 'model\Payments\Creditor\Identification'.</span></span>
10. <span data-ttu-id="0e010-193">A fastruktúrában bontsa ki a „modell\Kifizetések\Hitelező\Azonosító\Forrásazonosító” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-193">In the tree, select 'model\Payments\Creditor\Identification\Source ID(SourceID)'.</span></span>
11. <span data-ttu-id="0e010-194">A fában bontsa ki az „Excel\PaymLines” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-194">In the tree, expand 'Excel\PaymLines'.</span></span>
12. <span data-ttu-id="0e010-195">A fában bontsa ki az „Excel\PaymLines\VendAccountName” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-195">In the tree, select 'Excel\PaymLines\VendAccountName'.</span></span>
13. <span data-ttu-id="0e010-196">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-196">Click Bind.</span></span>
14. <span data-ttu-id="0e010-197">A fán válassza ki „model\Kifizetések = Transactions\Creditor\Name” pontot.</span><span class="sxs-lookup"><span data-stu-id="0e010-197">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
15. <span data-ttu-id="0e010-198">A fában válassza ki az „Excel\PaymLines\VendName” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-198">In the tree, select 'Excel\PaymLines\VendName'.</span></span>
16. <span data-ttu-id="0e010-199">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-199">Click Bind.</span></span>
17. <span data-ttu-id="0e010-200">A fastruktúrában bontsa ki a „modell\kifizetések\Hitelező ügynöke(CreditorAccount)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-200">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
18. <span data-ttu-id="0e010-201">A fastruktúrában válassza ki a „modell\kifizetések\Hitelező ügynöke(CreditorAccount)\Név” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-201">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Name'.</span></span>
19. <span data-ttu-id="0e010-202">A fában válassza ki az „Excel\PaymLines\Bank” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-202">In the tree, select 'Excel\PaymLines\Bank'.</span></span>
20. <span data-ttu-id="0e010-203">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-203">Click Bind.</span></span>
21. <span data-ttu-id="0e010-204">A fastruktúrában válassza ki „modell\Kifizetések\Hitelező ügynöke(CreditorAgent)\Útvonalszám(RoutingNumber)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-204">In the tree, select 'model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)'.</span></span>
22. <span data-ttu-id="0e010-205">A fában válassza ki az „Excel\PaymLines\RoutingNumber” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-205">In the tree, select 'Excel\PaymLines\RoutingNumber'.</span></span>
23. <span data-ttu-id="0e010-206">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-206">Click Bind.</span></span>
24. <span data-ttu-id="0e010-207">A fában bontsa ki a következőt: „model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="0e010-207">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
25. <span data-ttu-id="0e010-208">A fában bontsa ki a következőt: „model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="0e010-208">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)\Identification'.</span></span>
26. <span data-ttu-id="0e010-209">A fastruktúrában válassza ki a „modell\Kifizetések\Hitelező számlája(CreditorAccount)\Azonosító\Szám” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-209">In the tree, select 'model\Payments\Creditor Account(CreditorAccount)\Identification\Number'.</span></span>
27. <span data-ttu-id="0e010-210">A fában válassza ki az „Excel\PaymLines\AccountNumber” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-210">In the tree, select 'Excel\PaymLines\AccountNumber'.</span></span>
28. <span data-ttu-id="0e010-211">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-211">Click Bind.</span></span>
29. <span data-ttu-id="0e010-212">A fastruktúrában válassza ki a „Modell\Kifizetések\Rendelkezésben megadott összeg (InstructedAmount)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-212">In the tree, select 'model\Payments\Instructed Amount(InstructedAmount)'.</span></span>
30. <span data-ttu-id="0e010-213">A fában válassza ki az „Excel\PaymLines\Tartozik” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-213">In the tree, select 'Excel\PaymLines\Debit'.</span></span>
31. <span data-ttu-id="0e010-214">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-214">Click Bind.</span></span>
32. <span data-ttu-id="0e010-215">A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-215">In the tree, expand 'model\Payments\Creditor'.</span></span>
33. <span data-ttu-id="0e010-216">A fában bontsa ki a következőt: „model\Payments\Creditor Account(CreditorAccount)”.</span><span class="sxs-lookup"><span data-stu-id="0e010-216">In the tree, expand 'model\Payments\Creditor Account(CreditorAccount)'.</span></span>
34. <span data-ttu-id="0e010-217">A fastruktúrában bontsa ki a „modell\kifizetések\Hitelező ügynöke(CreditorAccount)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-217">In the tree, expand 'model\Payments\Creditor Agent(CreditorAgent)'.</span></span>
35. <span data-ttu-id="0e010-218">A fastruktúrában válassza ki a „Modell\Kifizetések\Pénznem” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-218">In the tree, select 'model\Payments\Currency'.</span></span>
36. <span data-ttu-id="0e010-219">A fában válassza ki az „Excel\PaymLines\Pénznem” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-219">In the tree, select 'Excel\PaymLines\Currency'.</span></span>
37. <span data-ttu-id="0e010-220">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-220">Click Bind.</span></span>
38. <span data-ttu-id="0e010-221">Bontsa ki a fastruktúrában a „Kifizetés pénzneme” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-221">In the tree, expand 'PaymentByCurrency'.</span></span>
39. <span data-ttu-id="0e010-222">Bontsa ki a fastruktúrában a „Kifizetés pénzneme\Csoportosítva” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-222">In the tree, expand 'PaymentByCurrency\grouped'.</span></span>
40. <span data-ttu-id="0e010-223">A fastruktúrában válassza ki a „Kifizetés pénzneme\Csoportosítva\Pénznem” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-223">In the tree, select 'PaymentByCurrency\grouped\Currency'.</span></span>
41. <span data-ttu-id="0e010-224">A fában bontsa ki az „Excel\SummaryLines” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-224">In the tree, expand 'Excel\SummaryLines'.</span></span>
42. <span data-ttu-id="0e010-225">A fában válassza ki az „Excel\SummaryLines\SummaryCurrency” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-225">In the tree, select 'Excel\SummaryLines\SummaryCurrency'.</span></span>
43. <span data-ttu-id="0e010-226">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-226">Click Bind.</span></span>
44. <span data-ttu-id="0e010-227">Bontsa ki a fastruktúrában a„Kifizetés pénzneme\Összesített” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-227">In the tree, expand 'PaymentByCurrency\aggregated'.</span></span>
45. <span data-ttu-id="0e010-228">A fastruktúrában válassza ki a „Kifizetés pénzneme\Összesített\TotalInstructuredAmount” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-228">In the tree, select 'PaymentByCurrency\aggregated\TotalInstructuredAmount'.</span></span>
46. <span data-ttu-id="0e010-229">A fában válassza ki az „Excel\SummaryLines\SummaryAmount” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-229">In the tree, select 'Excel\SummaryLines\SummaryAmount'.</span></span>
47. <span data-ttu-id="0e010-230">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-230">Click Bind.</span></span>
48. <span data-ttu-id="0e010-231">A fastruktúrában válassza ki a „Kifizetés pénzneme” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0e010-231">In the tree, select 'PaymentByCurrency'.</span></span>
49. <span data-ttu-id="0e010-232">A fastruktúrában válassza ki a következőt: „Excel\SummaryLines”.</span><span class="sxs-lookup"><span data-stu-id="0e010-232">In the tree, select 'Excel\SummaryLines'.</span></span>
50. <span data-ttu-id="0e010-233">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-233">Click Bind.</span></span>
51. <span data-ttu-id="0e010-234">A fán válassza ki a következőt: „model\Payments”.</span><span class="sxs-lookup"><span data-stu-id="0e010-234">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="0e010-235">A fában válassza ki az „Excel\PaymLines” elemet.</span><span class="sxs-lookup"><span data-stu-id="0e010-235">In the tree, select 'Excel\PaymLines'.</span></span>
53. <span data-ttu-id="0e010-236">Kattintson a Kötés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-236">Click Bind.</span></span>
54. <span data-ttu-id="0e010-237">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-237">Click Save.</span></span>
55. <span data-ttu-id="0e010-238">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e010-238">Close the page.</span></span>

## <a name="use-the-created-configuration-for-payments-processing"></a><span data-ttu-id="0e010-239">A létrehozott konfiguráció használata a fizetések feldolgozásához</span><span class="sxs-lookup"><span data-stu-id="0e010-239">Use the created configuration for payments processing</span></span>
1. <span data-ttu-id="0e010-240">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="0e010-240">Click Change status.</span></span>
2. <span data-ttu-id="0e010-241">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-241">Click Complete.</span></span>
3. <span data-ttu-id="0e010-242">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-242">Click OK.</span></span>
4. <span data-ttu-id="0e010-243">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e010-243">Close the page.</span></span>
5. <span data-ttu-id="0e010-244">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e010-244">Close the page.</span></span>
6. <span data-ttu-id="0e010-245">Ugorjon a Kötelezettségek > Kifizetés beállítása > Fizetési módok pontra.</span><span class="sxs-lookup"><span data-stu-id="0e010-245">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
7. <span data-ttu-id="0e010-246">A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Fizetési mezőben az „Elektronikus” érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="0e010-246">Use the Quick Filter to filter on the Method of payment field with a value of 'Electronic'.</span></span>
    * <span data-ttu-id="0e010-247">Elektronikus</span><span class="sxs-lookup"><span data-stu-id="0e010-247">Electronic</span></span>  
8. <span data-ttu-id="0e010-248">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-248">Click Edit.</span></span>
9. <span data-ttu-id="0e010-249">Bontsa ki a Fájlformátumok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0e010-249">Expand the File formats section.</span></span>
10. <span data-ttu-id="0e010-250">Válassza az Igen beállítást az Általános elektronikus jelentéskészítés mezőben.</span><span class="sxs-lookup"><span data-stu-id="0e010-250">Select Yes in the Generic electronic reporting field.</span></span>
11. <span data-ttu-id="0e010-251">Az Exportformátum konfigurációja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0e010-251">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="0e010-252">Válassza ki a "Minta munkalap jelentés" konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="0e010-252">Select the ‘Sample worksheet report’ configuration.</span></span>  
12. <span data-ttu-id="0e010-253">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-253">Click Save.</span></span>
13. <span data-ttu-id="0e010-254">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="0e010-254">Close the page.</span></span>

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a><span data-ttu-id="0e010-255">A létrehozott konfiguráció használata a Kifizetési naplók feldolgozásának vizsgálatához</span><span class="sxs-lookup"><span data-stu-id="0e010-255">Use the created configuration for testing of payment journals processing</span></span>
1. <span data-ttu-id="0e010-256">Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.</span><span class="sxs-lookup"><span data-stu-id="0e010-256">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="0e010-257">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-257">Click New.</span></span>
    * <span data-ttu-id="0e010-258">Hozzon létre egy új kifizetési naplót.</span><span class="sxs-lookup"><span data-stu-id="0e010-258">Create a new payment journal.</span></span>  
3. <span data-ttu-id="0e010-259">A Név mezőbe írja be: „VendPay”.</span><span class="sxs-lookup"><span data-stu-id="0e010-259">In the Name field, type 'VendPay'.</span></span>
    * <span data-ttu-id="0e010-260">VendPay</span><span class="sxs-lookup"><span data-stu-id="0e010-260">VendPay</span></span>  
4. <span data-ttu-id="0e010-261">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="0e010-261">Click Lines.</span></span>
5. <span data-ttu-id="0e010-262">A Számla mezőben adja meg a „GB_SI_000001” értékeket.</span><span class="sxs-lookup"><span data-stu-id="0e010-262">In the Account field, specify the values 'GB_SI_000001'.</span></span>
    * <span data-ttu-id="0e010-263">GB_SI_000001</span><span class="sxs-lookup"><span data-stu-id="0e010-263">GB_SI_000001</span></span>  
6. <span data-ttu-id="0e010-264">Állítsa a Terhelést „1000” értékre.</span><span class="sxs-lookup"><span data-stu-id="0e010-264">Set Debit to '1000'.</span></span>
7. <span data-ttu-id="0e010-265">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0e010-265">Click New.</span></span>
8. <span data-ttu-id="0e010-266">A Számla mezőben adja meg a „GB_SI_000005” értékeket.</span><span class="sxs-lookup"><span data-stu-id="0e010-266">In the Account field, specify the values 'GB_SI_000005'.</span></span>
    * <span data-ttu-id="0e010-267">GB_SI_000005</span><span class="sxs-lookup"><span data-stu-id="0e010-267">GB_SI_000005</span></span>  
9. <span data-ttu-id="0e010-268">Állítsa a Terhelést „2000” értékre.</span><span class="sxs-lookup"><span data-stu-id="0e010-268">Set Debit to '2000'.</span></span>
10. <span data-ttu-id="0e010-269">A Pénznem mezőben írja be az „EUR” szöveget.</span><span class="sxs-lookup"><span data-stu-id="0e010-269">In the Currency field, type 'EUR'.</span></span>
    * <span data-ttu-id="0e010-270">HUF</span><span class="sxs-lookup"><span data-stu-id="0e010-270">EUR</span></span>  
11. <span data-ttu-id="0e010-271">Az Ellenszámla mezőben adja meg a „GBSI OPER” értékeket.</span><span class="sxs-lookup"><span data-stu-id="0e010-271">In the Offset account field, specify the values 'GBSI OPER'.</span></span>
    * <span data-ttu-id="0e010-272">GBSI MŰV.</span><span class="sxs-lookup"><span data-stu-id="0e010-272">GBSI OPER</span></span>  
12. <span data-ttu-id="0e010-273">A Fizetési mód mezőbe írja be az „Elektronikus” szöveget.</span><span class="sxs-lookup"><span data-stu-id="0e010-273">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="0e010-274">Elektronikus</span><span class="sxs-lookup"><span data-stu-id="0e010-274">Electronic</span></span>  
13. <span data-ttu-id="0e010-275">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-275">Click Save.</span></span>
14. <span data-ttu-id="0e010-276">Kattintson a Kifizetések létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="0e010-276">Click Generate payments.</span></span>
15. <span data-ttu-id="0e010-277">A Fizetési mód mezőbe írja be az „Elektronikus” szöveget.</span><span class="sxs-lookup"><span data-stu-id="0e010-277">In the Method of payment field, type 'Electronic'.</span></span>
    * <span data-ttu-id="0e010-278">Elektronikus</span><span class="sxs-lookup"><span data-stu-id="0e010-278">Electronic</span></span>  
16. <span data-ttu-id="0e010-279">A Fájlnév mezőbe írja be a következőt: „Fizetések”.</span><span class="sxs-lookup"><span data-stu-id="0e010-279">In the File name field, type 'Payments'.</span></span>
    * <span data-ttu-id="0e010-280">Például írja be a Kifizetések szöveget.</span><span class="sxs-lookup"><span data-stu-id="0e010-280">For example, type Payments.</span></span>  
17. <span data-ttu-id="0e010-281">A Bankszámla mezőben írja be a „GBSI OPER” szöveget.</span><span class="sxs-lookup"><span data-stu-id="0e010-281">In the Bank account field, type 'GBSI OPER'.</span></span>
    * <span data-ttu-id="0e010-282">GBSI MŰV.</span><span class="sxs-lookup"><span data-stu-id="0e010-282">GBSI OPER</span></span>  
18. <span data-ttu-id="0e010-283">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-283">Click OK.</span></span>
19. <span data-ttu-id="0e010-284">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0e010-284">Click OK.</span></span>
    * <span data-ttu-id="0e010-285">Tekintse át a létrehozott munkalapot, többek között a kifizetési sorok részleteit, valamint az ebben a fizetési üzenetben használt pénznemkódra vonatkozó összegeket is.</span><span class="sxs-lookup"><span data-stu-id="0e010-285">Review the created worksheet, including details of payment lines as well as totals for each currency code used in this payment message.</span></span>  


